# mcp3208

//Original Work of node-red-node-pi-mcp3008
//modified code for my project

node-red-node-pi-mcp3208
========================

A <a href="http://nodered.org" target="_new">Node-RED</a> node to read from
the MCP3208 Analogue to Digital Converter,
such as the <a href="http://rasp.io/analogzero" target="_new">Rasp.io analogzero</a>, though it will work with breadboard versions also.

It will appear in the menu as ` A/D Converter `.

**Warning**: Input voltages must not exceed 3.3V or 5V, check <a href="http://ww1.microchip.com/downloads/en/DeviceDoc/21298c.pdf" target="_new">MCP3208 DataSheet</a>

### Pre-requisites

You must ensure that SPI is enabled. For recent (2016) versions of Raspbian you can do this

 - Run `sudo raspi-config`
 - Select `5 - Interfacing Options`
 - Select `P4 - SPI`
 - Select `yes` to enable SPI
 - Select `OK` to confirm
 - Select the `Finish` button

### Install

copy paste the folder in `~/.node-red` directory

**Note**: It will appear in the menu as ` MCP3208 `.

### Usage

Reads from an MCP3208 Analogue to Digital (ADC) chip on the Pi SPI connection.

You can either set a channel in the edit dialogue, or you can set the `msg.payload` to
select the channel dynamically. If so then the payload must be a value from 0 to 7.

You can also select device id 0 or 1 (CE0 or CE1) depending on how you have wired up your device. Defaults to CE0.

Outputs a numeric `msg.payload` with a range of 0 to 4095, where 0 = 0V and 1023 = 3.3V / 5V (assuming you use the default 3.3V voltage reference).

**Hint**: use a `range` node to adjust the values to the range you want.

Also sets `msg.topic` to `adc/{the pin number}`
