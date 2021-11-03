# Lab 7: Tomáš Kříčka

### My repository
[https://github.com/TomasKricka/Digital-electronic-2](https://github.com/TomasKricka/Digital-electronics-2)










<br>
<br>

   | **Push button** | **PC0[A0] voltage** | **ADC value (calculated)** | **ADC value (measured)** |
   | :-: | :-: | :-: | :-: |
   | Right  | 0&nbsp;V          | 0         |  |
   | Up     | 0.495&nbsp;V   ne   | 63        |  |
   | Down   |   1.256&nbsp;V  ne  |  101      |  |
   | Left   |   1.999&nbsp;V  ne  |  199      |  |
   | Select |   3.1&nbsp;V    ne  |  280      |  |
   | none   |   5&nbsp;V      ne  |  1023     |  |

<br>
<br>

DATASHEET page 259, registres

<br>
<br>


   | **Operation** | **Register(s)** | **Bit(s)** | **Description** |
   | :-- | :-: | :-: | :-- |
   | Voltage reference    | ADMUX | REFS1:0 | 00: ..., 01: AVcc voltage reference (5V), ... |
   | Input channel        | ADMUX | MUX3:0 | 0000: ADC0, 0001: ADC1, ... |
   | ADC enable           | ADCSRA | ADEN7:0 |  |
   | Start conversion     | ADCSRA | ADSC6:0 |  |
   | ADC interrupt enable | ADCSRA | ADIE3:0 |  |
   | ADC clock prescaler  | ADCSRA | ADPS2:0 | 000: Division factor 2, 001: 2, 010: 4, ...|
   | ADC 10-bit result    |  |  |  |