# Caf.js

Co-design cloud assistants with your web app and IoT devices.

See https://www.cafjs.com

## Raspberry Pi Library for Accessing GPIO Pins

[![Build Status](https://github.com/cafjs/caf_rpi_gpio/actions/workflows/push.yml/badge.svg)](https://github.com/cafjs/caf_rpi_gpio/actions/workflows/push.yml)


This library provides access to GPIO pins in a Raspberry Pi. It runs in the device not in the cloud.

## API

See {@link module:caf_rpi_gpio/proxy_iot_gpio}

## Configuration Example

### iot.json

See {@link module:caf_rpi_gpio/plug_iot_gpio}
```
    {
            "module": "caf_rpi_gpio#plug_iot",
            "name": "gpio",
            "description": "Access to GPIO pins for this device.",
            "env" : {
                "maxRetries" : "$._.env.maxRetries",
                "retryDelay" : "$._.env.retryDelay",
                "gpiomem" : "process.env.GPIO_MEM||true",
                "mapping" : "process.env.MAPPING||physical",
                "allowMock" : "process.env.ALLOW_MOCK||true",
                "mockRootDir" : "process.env.MOCK_ROOT_DIR||/tmp/gpio"
            },
            "components" : [
                {
                    "module": "caf_rpi_gpio#proxy_iot",
                    "name": "proxy",
                    "description": "Proxy to access GPIO pins",
                    "env" : {
                    }
                }
            ]
    }
```
