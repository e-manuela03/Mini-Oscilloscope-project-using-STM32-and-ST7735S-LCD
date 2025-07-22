# Mini-Oscilloscope-project-using-STM32-and-ST7735S-LCD

To address the overall theme, we made the following implementation decisions. The ST7735S display was chosen because of its resolution (128x160 pixels). The internal ADC a1 of the STM32 microcontroller is used to read the signal. The display is done by plotting the points corresponding to the ADC values on the vertical axis of the display, moving horizontally. Thus, the signal is rendered graphically, similar to a real oscilloscope.
The operating logic is as follows. The signal generator produces an analog signal that we want to measure. 
The analog signal goes to the input of the microcontroller's ADC (Analog-to-Digital Converter). The ADC-u1 converts the analog voltage to a digital numeric (12-bit) value.
The microcontroller takes quick readings of the digital values from the ADC at regular intervals (sampling rate). Thisstep is crucial to capture the waveform as accurately as possible. The read digital values are temporarily stored in abuffer (a vector) so that they can be processed and displayed. The processed values are transformed into X,Ycoordinates on the ST7735S display. A continuous loop is made: read ADC -+ process -+ display -' read ADC -+ ... so thatthe signal is displayed in real time, like a classic oscilloscope.

For more details read Documentatie -en.
