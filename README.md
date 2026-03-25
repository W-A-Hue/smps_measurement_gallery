# smps_measurement_gallery
This gallery presents a selection of measurements obtained with the automated measurement framework described in my paper [link to paper], which I presented at APEC 2026.

The gallery is divided into two main sections:
- DC/DC converters
- AC/DC converters

## Contents

- [DC/DC Converters](#dcdc-converters)
  - [LM25116 Family](#lm25116-family)
    - [LM25116 Stock Configuration](#lm25116-stock-configuration)
    - [LM25116 with Additional 3uF Output Capacitance](#lm25116-with-additional-3uf-output-capacitance)
- [AC/DC Converters](#acdc-converters)

## DC/DC Converters

## LM25116 Family

The LM25116 is a popular controller for medium-power step-down converter modules commonly found on online marketplaces. In contrast to simpler regulators with an integrated power switch such as the LM2596 family, the LM25116 is a synchronous buck controller intended for more demanding applications with higher current capability and improved efficiency.

The particular module shown here is one of the generic LM25116-based boards frequently sold as a 20 A / 300 W DC-DC buck converter. All measurements in this section were performed with the output set to 12 V.


### LM25116 Stock Configuration

This section shows the measurement results obtained with the unmodified module in its stock configuration.


#### Stock Efficiency
![LM25116 stock efficiency](LM25116/12V_stock/LM25116_12V_buck_stock_efficiency.png)

#### Stock Power Loss
![LM25116 stock power loss](LM25116/12V_stock/LM25116_12V_buck_stock_Ploss.png)

#### Stock Switching Frequency
![LM25116 stock switching frequency](LM25116/12V_stock/LM25116_12V_buck_stock_f_sw.png)

#### Stock Output Voltage Ripple (peak-to-peak)
![LM25116 stock output ripple peak-to-peak](LM25116/12V_stock/LM25116_12V_buck_stock_Vout_pkpk.png)

The [stock efficiency plot](#stock-efficiency) exhibits the typical contour pattern commonly observed for buck converters. As indicated by the marker lines, the converter enters the >90% efficiency region already at moderate load current.

At the same time, the [stock output voltage ripple plot](#stock-output-voltage-ripple-peak-to-peak) shows that the ripple performance is still problematic. At 12 V output, the 1% design specification corresponds to 120 mV peak-to-peak, and this limit is exceeded in parts of the operating range marked by the guide lines.

### LM25116 with Additional 3 uF Output Capacitance

In order to investigate whether this issue can be improved with a minimal hardware modification, three additional 1 uF MLCCs were added at the output. Apart from this added output capacitance, the module and test conditions remained unchanged.

#### Efficiency with Additional 3 uF Output Capacitance
![LM25116 3 uF efficiency](LM25116/12V_additional_3uF_Cout/LM25116_12V_buck_3uF_efficiency.png)

#### Power Loss with Additional 3 uF Output Capacitance
![LM25116 3 uF power loss](LM25116/12V_additional_3uF_Cout/LM25116_12V_buck_3uF_Ploss.png)

#### Switching Frequency with Additional 3 uF Output Capacitance
![LM25116 3 uF switching frequency](LM25116/12V_additional_3uF_Cout/LM25116_12V_buck_3uF_f_sw.png)

#### Output Voltage Ripple (peak-to-peak) with Additional 3 uF Output Capacitance
![LM25116 3 uF output ripple peak-to-peak](LM25116/12V_additional_3uF_Cout/LM25116_12V_buck_3uF_Vout_pkpk.png)

The additional 3 uF output capacitance reduces the magnitude of the output ripple, but does not fully resolve the issue. The ripple is improved compared to the stock configuration, yet it still remains above the 1% target in part of the operating range.

However, the absolute plots alone do not show whether this modification improves the output ripple uniformly across the full operating range, or how large the local changes actually are. To examine this in more detail, the stock and modified configurations are compared directly using differential plots.


### Differential Comparison: Stock Configuration vs. Additional 3 uF Output Capacitance

The following plots differ from the absolute plots shown above. Instead of showing the absolute value of each measured parameter, they show the differential change between the stock configuration and the modified variant with additional output capacitance, thus allowing to directly isolate the impact of a changed component.

In these differential plots, green indicates operating regions in which the parameter improved from the first variant to the second, white indicates little or no relevant change, and red indicates regions in which the plotted parameter became worse.

#### Differential Efficiency
![LM25116 stock vs 3 uF efficiency](LM25116/stock_vs_3uF/LM25116_12V_buck_stock_vs_3uF_efficiency.png)

#### Differential Power Loss
![LM25116 stock vs 3 uF power loss](LM25116/stock_vs_3uF/LM25116_12V_buck_stock_vs_3uF_ploss.png)

#### Differential Switching Frequency
![LM25116 stock vs 3 uF switching frequency](LM25116/stock_vs_3uF/LM25116_12V_buck_stock_vs_3uF_f_sw.png)

#### Differential Output Voltage Ripple (peak-to-peak)
![LM25116 stock vs 3 uF output ripple peak-to-peak](LM25116/stock_vs_3uF/LM25116_12V_buck_stock_vs_3uF_Vout_ripple_pkpk.png)

Overall, the differential plots show that the modification improves the output voltage ripple in some parts of the operating range, while in other regions the ripple becomes slightly worse. This suggests that the additional output capacitance did not simply reduce ripple uniformly, but also altered the overall system control behavior.


## AC/DC Converters

Content will be added here.

