# co2-logger

Gets readings from a big round NDIR CO2 logger via UART (sold as Green Eye, Wöhler CDL 210, Extech CO210).

Tested on Mac OS and Linux.

Assumes only one USB serial adapter is connected.
The script tries to find USB serial cable as:

  - /dev/tty.usbserial* (newer macOS)
  - /dev/tty.SLAB_USBtoUART (older OS X)
  - /dev/ttyUSB* (Linux).

Submits data via a webhook to influxdb to be used with Grafana.

Expects the webhook URL in `config.yaml`:
```
url: "https://server_address:port/write?db=db_name&u=user_name&p=password"
```
