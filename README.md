# smps_measurement_gallery
This gallery presents a selection of measurements obtained with the automated measurement framework described in my paper [link to paper], which I presented at APEC 2026.


## DC/DC Converters

## LM25116 Family

The LM25116 is a popular controller for medium-power step-down converter modules commonly found on online marketplaces. In contrast to simpler regulators with an integrated power switch such as the LM2596 family, the LM25116 is a synchronous buck controller intended for more demanding applications with higher current capability and improved efficiency.

The particular module shown here is one of the generic LM25116-based boards frequently sold as a 20 A / 300 W DC-DC buck converter. All measurements in this section were performed with the output set to 12 V.


### LM25116 Stock Configuration

This section shows the measurement results obtained with the unmodified module in its stock configuration.

#### Results

**Efficiency**
![LM25116 stock efficiency](LM25116/12V_stock/LM25116_12V_buck_stock_efficiency.png)

**Power Loss**
![LM25116 stock power loss](LM25116/12V_stock/LM25116_12V_buck_stock_Ploss.png)

**Switching Frequency**
![LM25116 stock switching frequency](LM25116/12V_stock/LM25116_12V_buck_stock_f_sw.png)

#### Output Voltage Ripple (peak-to-peak)
![LM25116 stock output ripple peak-to-peak](LM25116/12V_stock/LM25116_12V_buck_stock_Vout_pkpk.png)

The measured output voltage ripple of the stock configuration exceeds the design specification of 1% of the output voltage. At 12 V output, this corresponds to a limit of 120 mV peak-to-peak. This limit is exceeded in parts of the operating range, as indicated by the marker lines in the [plot above](#output-voltage-ripple-peak-to-peak).


### LM25116 with Additional 3 µF Output Capacitance

In order to investigate whether this issue can be improved with a minimal hardware modification, three additional 1 µF MLCCs were added at the output. Apart from this added output capacitance, the module and test conditions remained unchanged.

#### Results

**Efficiency**
![LM25116 3 uF efficiency](LM25116/12V_extra_3uF_Cout/LM25116_12V_buck_3uF_efficiency.png)

**Power Loss**
![LM25116 3 uF power loss](LM25116/12V_extra_3uF_Cout/LM25116_12V_buck_3uF_Ploss.png)

**Switching Frequency**
![LM25116 3 uF switching frequency](LM25116/12V_extra_3uF_Cout/LM25116_12V_buck_3uF_f_sw.png)

**Output Voltage Ripple (peak-to-peak)**
![LM25116 3 uF output ripple peak-to-peak](LM25116/12V_extra_3uF_Cout/LM25116_12V_buck_3uF_Vout_pkpk.png)

The additional 3 µF output capacitance reduces the magnitude of the output ripple, but does not fully resolve the issue. The ripple is improved compared to the stock configuration, yet it still remains above the 1% target in part of the operating range.



## AC/DC Converters

Content will be added here.

