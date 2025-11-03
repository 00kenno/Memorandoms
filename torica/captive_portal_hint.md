# CaptivePortalに関するヒント
## CaptivePortal.ino (ESPAsyncWebServer example)
```
// SPDX-License-Identifier: LGPL-3.0-or-later
// Copyright 2016-2025 Hristo Gochkov, Mathieu Carbou, Emil Muratov

#include <DNSServer.h>
#if defined(ESP32) || defined(LIBRETINY)
#include <AsyncTCP.h>
#include <WiFi.h>
#elif defined(ESP8266)
#include <ESP8266WiFi.h>
#include <ESPAsyncTCP.h>
#elif defined(TARGET_RP2040) || defined(TARGET_RP2350) || defined(PICO_RP2040) || defined(PICO_RP2350)
#include <RPAsyncTCP.h>
#include <WiFi.h>
#endif
#include "ESPAsyncWebServer.h"

static DNSServer dnsServer;
static AsyncWebServer server(80);

class CaptiveRequestHandler : public AsyncWebHandler {
public:
  bool canHandle(__unused AsyncWebServerRequest *request) const override {
    return true;
  }

  void handleRequest(AsyncWebServerRequest *request) {
    AsyncResponseStream *response = request->beginResponseStream("text/html");
    response->print("<!DOCTYPE html><html><head><title>Captive Portal</title></head><body>");
    response->print("<p>This is our captive portal front page.</p>");
    response->printf("<p>You were trying to reach: http://%s%s</p>", request->host().c_str(), request->url().c_str());
#if SOC_WIFI_SUPPORTED || CONFIG_ESP_WIFI_REMOTE_ENABLED || LT_ARD_HAS_WIFI
    response->printf("<p>Try opening <a href='http://%s'>this link</a> instead</p>", WiFi.softAPIP().toString().c_str());
#endif
    response->print("</body></html>");
    request->send(response);
  }
};

void setup() {
  Serial.begin(115200);
  Serial.println();
  Serial.println("Configuring access point...");

#if SOC_WIFI_SUPPORTED || CONFIG_ESP_WIFI_REMOTE_ENABLED || LT_ARD_HAS_WIFI
  if (!WiFi.softAP("esp-captive")) {
    Serial.println("Soft AP creation failed.");
    while (1);
  }

  dnsServer.start(53, "*", WiFi.softAPIP());
#endif

  server.addHandler(new CaptiveRequestHandler()).setFilter(ON_AP_FILTER);  // only when requested from AP
  // more handlers...
  server.begin();
}

void loop() {
  dnsServer.processNextRequest();
}
```
## SD.cpp (Singleton hint)
```
namespace SDLib {

// Used by `getNextPathComponent`
#define MAX_COMPONENT_LEN 12
#define PATH_COMPONENT_BUFFER_LEN (MAX_COMPONENT_LEN + 1)
// BASENAME:char(8) + '.':char(1) + EXT:char(3) = 12 (a.k.a short 8.3 name)
// And an extra space for '\0' for path buffer
    :
    :
    :
  void File::rewindDirectory(void) {
    if (isDirectory()) {
      _file->rewind();
    }
  }

  SDClass SD;

};
```
