---
layout: post
title:  "Compressed Air System Data Extraction: Stage 1"
date:   2015-07-27 19:23:33
categories: modbus
---
Last week the first installation stage of a data extraction solution for our group’s compressed air system test site was completed.

The compressed air system on site is comprised of:

- 30 kW fixed speed (FS) rotary tooth Compressor
- 37 kW variable speed (VS) rotary tooth Compressor
- 180 kg heatless dessicant compressed air dryer
- 1.5 m3 receiver

From these items of equipment 50 data points are available to be extracted through Modbus. A comprehensive list of these points is available [here]({{ seanmhayes.github.io }}/assets/ModbusPoints.xlsx).

Following discussion with a controls company, it was decided that a [JACE box](http://www.niagaraax.com/cs/products/jace) was the best solution to extract data through Modbus. The compressors themselves are not Modbus enabled, but require a proprietary gateway for Modbus communication.

Last week the JACE box was installed, and the necessary cabling run between the compressed air equipment, the JACE box, and the proposed site of the proprietary gateway. Two-pair cable (i.e. 4 wires with shields) was run between the various locations in daisy-chain configuration, as shown in the diagram below. Only two wires from each cable will be used. The dryer is connected to the VS machine with two wires. The VS machine is then connected to the FS machine with two wires. The VS machine is connected to the FS machine with two wires, which is connected with two wires to the proprietary gateway. The gateway acts as a Modbus bridge and is then connected to the JACE box with two wires. The JACE box acts as the Modbus master in the network.

![Compressed Air System Modbus Network]({{ seanmhayes.github.io }}/assets/PharmacyModbusNetwork.png)

There is a spare RS485 port on the JACE box. This is to be used in future projects to create a bare bones method of data extraction, e.g. through a Raspberry Pi. At this point it is understood that any device connected to this spare port will be a slave on a separate Modbus network to the compressed air system, but that it will be able to pass requests about the compressed air network to the JACE box and receive data through it.

The proprietary gateway is expected for delivery next week. Once this is installed it can be connected to the JACE box. Supplementary to the JACE box a mobile modem was installed. This will allow dialling into the JACE box remotely via a webpage for data download.


[jekyll]:      http://jekyllrb.com
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-help]: https://github.com/jekyll/jekyll-help
