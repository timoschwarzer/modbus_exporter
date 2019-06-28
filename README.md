# Modbus exporter

Prometheus exporter which retrieves stats from a modbus tcp system and exports
them via HTTP for Prometheus consumption.


## Building

```bash
make build
```


## Getting Started

The modbus exporter needs to be passed the *target* and *module* as parameters
by Prometheus, this can be done with relabelling (see
[prometheus.yml](prometheus.yml)).

Once Prometheus is properly configured, run the exporter via:

```bash
./modbus_exporter [flags]
```

Supported flags:

[embedmd]:# (help.txt)
```txt
Usage of ./modbus_exporter:
  -config.file string
    	Sets the configuration file. (default "modbus.yml")
  -modbus-listen-address string
    	The address to listen on for HTTP requests exposing modbus metrics. (default ":9602")
  -telemetry-listen-address string
    	The address to listen on for HTTP requests exposing telemetry metrics about the exporter itself. (default ":9011")
```


## Configuration File

Check out [`modbus.yml`](/modbus.yml) for more details on the configuration file
format.


## TODO

- Rework logging.

- Revisit bit parsing.


---


Support for serial modbus was dropped in git commit
d06573828793094fd2bdf3e7c5d072e7a4fd381b.
