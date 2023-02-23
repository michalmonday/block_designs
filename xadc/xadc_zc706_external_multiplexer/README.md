
![](../images/external_multiplexer.png)

External multiplexer is enabled but not plugged in yet when this waveform was captured, so all channels are reading the same value.  

![](../images/external_multiplexer_mode.png)

https://www.amazon.co.uk/DollaTek-CD74HC4067-Channel-Multiplexer-Breakout/dp/B07PPKRVGW/ref=sr_1_6

![](../images/mux.png)

TXS0108E (HW221) logic level converter can be used to convert the 1.5V XADC GPIO output (used for mux select pins) to 3.3V or 5V for the multiplexer.
https://www.amazon.co.uk/XTVTX-TXS0108E-Converter-Bi-Directional-Compatible/dp/B09P87R16M/ref=sr_1_8

![](../images/hw221.png)

When using external multiplexer, I had issues when using high conversion rate (KSPS), changing it to 39 KSPS solved the issue (while using 50MHz clock).

![](../images/external_multiplexer_settings.png)  

![](../images/external_multiplexer_settings2.png)  

![](../images/external_multiplexer_settings3.png)  

![](../images/external_multiplexer_settings4.png)  


Example use in a project is shown below. Lots of debug probes are outputted, but the circutry around xadc wizard isn't too compicated, subtraction is used to write the first sensor into the first location in memory (because xadc wizard keeps register of the first auxliary sensor at address 0x10, so 0x10 is subtracted).

![](../images/example_use.png)