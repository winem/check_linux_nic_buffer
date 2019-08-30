# check_linux_nic_buffer
Nagios and Icinga2 plugin to check the `pkts_rx_OOB` and `ring_full` counter of Linux interfaces.

## Dependencies
This plugin requires:
  - Python3

## How it works
The plugin executes `ethtool -S` to get the device statistics.

## Performance data
This plugin provides the following metrics:
  - `pkts_rx_OOB`
  - `ring_full`

Only the metric specified by `-m|--metric` will be reported. Thresholds are optional and will be appended.

## Usage
See the examples below or execute the plugin with -h/--help.

## Examples
Check the `ring_full` counter for eth0 with a warning threshold of 300 and a critical threshold of 1000:
```
./check_linux_nic_buffer -i eth0 -m ring_full -w 300 -c 1000
```

Check the `pkts_rx_OOB` counter for eth0 with a critical threshold of 500:
```
./check_linux_nic_buffer -i eth0 -m pkts_rx_OOB
```
