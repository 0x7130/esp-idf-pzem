# ESPZEM Sensor Driver

## Features

  * Read sensor specific sensor values
  * Reset energy counter for a specific address

## Usage

Here is the sensor's data structure definition:

```
typedef struct pzem_sensor_t {
  float voltage;
  float current;
  float power;
  float energy;
  float frequency;
  float pf;
  uint16_t alarms;
} pzem_sensor_t;
```

First of all the driver have to be properly configured using following 
options:

  * config `PZEM_UART_PORT_NUM` - Number of device's uart port (for an instance: 2)
  * config `PZEM_UART_RXD` and `PZEM_UART_RXD`
  * config `PZEM_DEBUG_ENABLE` enables debug output and embedds additional code.

## API

```
int pzem_sensor_init();                   // Initializes the UART port
void pzem_sensor_request(pzem_sensor_t *, uint8_t addr);   // Read values into `pzem_sensor`
int pzem_reset(uint8_t addr);             // Resets energy counter for specific device
```

## License

GPLv2

