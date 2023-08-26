# Online SSB calculator
Author: Dustin_Chen Email: Dustin_Chen@compal.com or chuhpsdustin@gmail.com

● ssb_basic: https://dustinchen26.github.io/ssb_calculate/

● ssb_advance: https://dustinchen26.github.io/ssb_calculator_advance/

● ssb_xml: https://dustinchen26.github.io/ssb_xml/

## freq to arfcn convert
ex:
Input freq(Hz): 3603840 => Output arfcn = 640256.00

## arfcn to freq convert
ex:
Input arfcn: 640256.00 => Output Freq = 3603840.00 Hz

## gscn calculator
```
[Purpose]: Input (band, carrierBw(RB), freq_low, freq_high), then it will calculate the valid (gscn /absFreqPointA /absArfcnPointA /absFreqSsb /absArfcnSsb /dlEarfcn /nDlCenterFreq /Kssb /offsetToPointA )
	n41 => freq range [2496000, 2690000]
	n48 => freq range [3550000, 3700000]
	n78 => freq range [3300000, 3800000]
	n79 => freq range [4400000, 5000000]
(RadiSys code):For n79, CORESET0 use 38.213 Table 13-6 Index 4.
(RadiSys code):For others, if BW>=48, CORESET0 use Table 13-4 Index 10. // Try to have 48 RB size for CS-0 to avoid allocation failure for SIB1 during SSB(20RBs) overlap
(RadiSys code):For others, if BW<48, CORESET0 use Table Index 0. // if 48 RB is not available, get the best fit CS0
```
## Example
```
● Please input
ex:(band, carrierBw(RB), freq_low, freq_high)=(78, 273, 3603840, 3603840) / (79, 273, 4849860, 4849860) / (41, 273, 2565750, 2565750)
band: 78
carrierBw(RB): 273
freq_low: 3603840
freq_high: 3603840

Calculate
gscn=7890, absFreqPointA=3554700, absArfcnPointA=636980, absFreqSsb=3563040, absArfcnSsb=637536, dlEarfcn=640256, nDlCenterFreq=3603840, Kssb=4, offsetToPointA=26
                 <dlBwpCfg>
                    <mu>KHz30</mu>
                    <numRb>273</numRb>
                 </dlBwpCfg>
                 <dlFreqInfo>
                    <absFreqPointA>3554700</absFreqPointA>
                    <absArfcnPointA>636980</absArfcnPointA>
                    <absFreqSsb>3563040</absFreqSsb>
                    <absArfcnSsb>637536</absArfcnSsb>
                    <nrFreqBand>78</nrFreqBand>
                    <subCarrierCfg>
                       <offsetToCarrier>0</offsetToCarrier>
                       <subCarrierSpacing>KHz30</subCarrierSpacing>
                       <carrierBw>273</carrierBw>
                    </subCarrierCfg>
                    <bSChannelBwDL>100MHZ</bSChannelBwDL>
                    <dlEarfcn>640256</dlEarfcn>
                 </dlFreqInfo>  
                 <ulBwpCfg>
                    <mu>KHz30</mu>
                    <numRb>273</numRb>
                 </ulBwpCfg>
                 <ulFreqInfo>
                    <absFreqPointA>3554700</absFreqPointA>
                    <absArfcnPointA>636980</absArfcnPointA>
                    <nrFreqBand>78</nrFreqBand>
                    <subCarrierCfg>
                       <offsetToCarrier>0</offsetToCarrier>
                       <subCarrierSpacing>KHz30</subCarrierSpacing>
                       <carrierBw>273</carrierBw>
                    </subCarrierCfg>
                    <bSChannelBwUl>100MHZ</bSChannelBwUl>
                    <ulEarfcn>640256</ulEarfcn>
                 </ulFreqInfo>
                 <nDlCenterFreq>3603840</nDlCenterFreq>
                 <nUlCenterFreq>3603840</nUlCenterFreq>
                 <nDlBw>100</nDlBw>
                 <nUlBw>100</nUlBw>
```
