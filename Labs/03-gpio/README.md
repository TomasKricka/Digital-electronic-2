# 03-gpio

### My repository
[My git - Tomáš Kříčka, 223283](https://github.com/TomasKricka/Digital-electronics-2)

<br>

## Preparation tasks

### 1. Table with deta types

| **Data type** | **Number of bits** | **Range** | **Description** |
| :-: | :-: | :-: | :-- | 
| `uint8_t`  | 8 | 0, 1, ..., 255 | Unsigned 8-bit integer |
| `int8_t`   | 8 | -128, ..., 127 | Signed 8-bit integer |
| `uint16_t` | 16 | 0, 1, ..., 65 535 | Unsigned 16-bit integer |
| `int16_t`  | 16 | -32768, ..., 32767 | Signed 16-bit integer |
| `float`    | 32 | -3.4e+38, ..., 3.4e+38 | Single-precision floating-point |
| `void`     |  |  | Pointer to unknown type of data |

<br>

### 2. Funcion
```c
#include <avr/io.h>

// Function declaration (prototype)
uint16_t calculate(uint8_t a, uint8_t b );      
int main(void)
{
    uint8_t a = 156;
    uint8_t b = 14;
    uint16_t c;

    // Function call
    c = calculate (a, b);
    printf("c = %d", c )

    while (1)
    {
    }
    return 0;
}

// Function definition (body)
int calculate(uint8_t x, uint8_t y)
{
    uint16_t result;    // result = x^2 + 2xy + y^2

    result = x*x + 2*x*y + y*y;
    
    return result;
}
```

