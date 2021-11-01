# Lab 5: Tomáš Kříčka

### My repository
[https://github.com/TomasKricka/Digital-electronic-2](https://github.com/TomasKricka/Digital-electronics-2)

<br>

### 7-segment library

1. In your words, describe the difference between Common Cathode and Common Anode 7-segment display.
   * CC SSD - pin is connected to GND, display is controlled by hight value
   * CA SSD - pin is connected to VCC, display is controlled by low value

<br>

2. Code listing with syntax highlighting of two interrupt service routines (`TIMER0_OVF_vect`, `TIMER0_OVF_vect`) from counter application with at least two digits, ie. values from 00 to 59:

```c
/**********************************************************************
 * Function: Timer/Counter1 overflow interrupt
 * Purpose:  Increment counter value from 00 to 59.
 **********************************************************************/
ISR(TIMER1_OVF_vect)
{
    // WRITE YOUR CODE HERE
    
    if(num0 =< 9){
        num0++;
        num1++;
        if(num1 =< 5){
            num1 = 0;
        }
    }
    else{
        num1 = 0;
    }
    SEG_update_shift_regs(num0, 0);
}



/**********************************************************************
 * Function: Timer/Counter0 overflow interrupt
 * Purpose:  Display tens and units of a counter at SSD.
 **********************************************************************/
ISR(TIMER0_OVF_vect)
{
    static uint8_t pos = 0;
    // WRITE YOUR CODE HERE

    if(pos =< 1){
        pos++;
        if(pos >= 1){
            pos = 0;
            SEG_update_shift_regs(num0, pos);
        }
    }
    else{
        SEG_update_shift_regs(num1, pos);
    }
}
```
<br>

3. Flowchart figure for function `SEG_clk_2us()` which generates one clock period on `SEG_CLK` pin with a duration of 2&nbsp;us. The image can be drawn on a computer or by hand. Use clear descriptions of the individual steps of the algorithms.

   ![your figure](images/flow_chart.svg)

<br>

### Kitchen alarm

Consider a kitchen alarm with a 7-segment display, one LED and three push buttons: start, +1 minute, -1 minute. Use the +1/-1 minute buttons to increment/decrement the timer value. After pressing the Start button, the countdown starts. The countdown value is shown on the display in the form of mm.ss (minutes.seconds). At the end of the countdown, the LED will start blinking.

<br>

1. Scheme of kitchen alarm; do not forget the supply voltage. The image can be drawn on a computer or by hand. Always name all components and their values.

   ![your figure](images/schema1.PNG)

   <br>
   <br>
   <br>

### Segment table

<br>

| **Digit** | **A** | **B** | **C** | **D** | **E** | **F** | **G** | **DP** |
| :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: |
| 0 | 0  | 0  | 0  | 0  | 0  | 0  | 1  | 1  |
| 1 | 1  | 0  | 0  | 1  | 1  | 1  | 1  | 1  |
| 2 | 0  | 0  | 1  | 0  | 0  | 1  | 0  | 1  |
| 3 | 0  | 0  | 0  | 0  | 1  | 1  | 0  | 1  |
| 4 | 1  | 0  | 0  | 1  | 1  | 0  | 0  | 1  |
| 5 | 0  | 1  | 0  | 0  | 1  | 0  | 0  | 1  |
| 6 | 0  | 1  | 0  | 0  | 0  | 0  | 0  | 1  |
| 7 | 0  | 0  | 0  | 1  | 1  | 1  | 1  | 1  |
| 8 | 0  | 0  | 0  | 0  | 0  | 0  | 0  | 1  |
| 9 | 0  | 0  | 0  | 0  | 1  | 0  | 0  | 1  |