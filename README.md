# Multi_buadrate_GMSK_Decoder
# Description
This GNURadio's Recipe is the Multi Buadrate GMSK Decoder(Demodulater) for Micro Satellite and CubeSat.

# Functions
* Multi Buadrate
  1. 1200bps
  1. 4800bps
  1. 9600bps
  1. 19200bps
* Multi SDR
  1. LimeSDR / LimeSDR mini
  1. PlutoSDR
  1. RTL-SDR
* Auto Doppler Shift
* Save & Load a Raw IQ file
* Calibration
* Gain Controller
* Tune Center Frequency
* Adjustment of Each Parameters
  * Data Sensitive(GMSK Demodulation)
  * Cut Noise
  * Auto Doppler Shift

# How to use
## Settings
* Change Files Path
  * Raw IQ File & Header File
  * Data File
* Each SDR
  1. Enable using SDR & Disable not using others.
    * LimeSDR
      1. Serial Number
      1. Calibration
    * Load Raw IQ File
      1. File Path
* Variables
  1. "RF_freq"
        * Target frequency
  1. "samp_rate"
        * Sampling rate.
          1. Multiples of 1200
          1. Over Multiples of 4 of Target Buadrate

## Adjustment of Each Parameters
### Data Sensitive(GMSK Demodulation)
* Variables
  1. "RF_GAIN"
      * Adjust Max Gain to  "-20" to "-40" in the Gain(dB) of "Frequency Display" Tab of "Spectrum Wave" Sink.
        * This uses the Hardware Gain controller.
  1. "CENTER_TUNE_FREQ"
      * Set Difference of the Frequency of a Real Center Frequency and a Received Center Frequency.
  1. "AGC_rate"
      *  Adjust Max Amplitude to "-1" to "1" in the Amplitude of "Time Domain Display" Tab of "Data Wave" Sink.
  1. "samp_rate"
      * The higher, the more sensitive.
### Cut Noise
* Variables
  1. "LPF_cut_magnification"
      * This maximum noise immunity value is "1.0". But this value is the minimum Data Sensitive.
### Auto Doppler Shift
* Variables
  1. "DS_cut_rate"
      * This maximum noise immunity value is "twice Buadrate".
  1. "DS_TUNE_AVG"
      * The doppler shift frequency is averaged by the number of times.
  1. "DS_cut_threshold_rate"
      * If the doppler shift frequency of 1ms ago and the present doppler shift frequency are except this rate, it uses the doppler shift frequency of 1ms ago.

## Running's Parameters
* Gain Level(dB)
* Tune Center Frequency(Step:1000Hz)
* Enable saving the Raw IQ File
* Enable the Auto Doppler Shift Function

# License
The Multi Buadrate GMSK Decoder
Copyright (c) 2006-2019 SIProp.org Noritsuna Imamura(noritsuna@siprop.org)
Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at (http://www.apache.org/licenses/LICENSE-2.0)
Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and limitations under the License.
