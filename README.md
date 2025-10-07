<img width="1918" height="1078" alt="image" src="https://github.com/user-attachments/assets/9f5eca7c-eb4d-4a42-9c9d-9b48cdf89012" />
# Serial Transfer of Single Byte / Character using 8051 (Keil)

## AIM
To write and execute an Embedded C Program for Serial Transfer of Single Byte / Character using 8051 in Keil.

## APPARATUS REQUIRED
- Personal Computer  
- Keil µVision Software  

## PROGRAM

### (i) Serial Port Transfer a Single Character

```
#include <reg51.h>

void main(void)
{
    TMOD = 0x20;
    TH1  = 0xFA;
    SCON = 0x50;
    TR1  = 1;

    SBUF = 'A';
    while(TI == 0);
    TI = 0;

    while(1);
}


```
### (ii) Serial Port to Transfer a Message

```
#include <reg51.h>
void main(void)
{
    unsigned char msg[] = "TARUN";
    unsigned char i;
    TMOD = 0x20;
    TH1  = 0xFA;
    SCON = 0x50;
    TR1  = 1;
    for(i = 0; msg[i] != '\0'; i++)
    {
        SBUF = msg[i];
        while(TI == 0);
        TI = 0;
    }

    while(1);
}
```

### OUTPUT:
<img width="1918" height="1078" alt="image" src="https://github.com/user-attachments/assets/51a6865b-b017-438b-9372-e7151c5e8588" />

<img width="1918" height="1078" alt="image" src="https://github.com/user-attachments/assets/4e78ff2e-bcf3-4cb6-a3da-99623ce1cc00" />

### RESULT:
Thus the Serial transfer of Single Byte / Character using 8051 KEIL was done and shown the output.
