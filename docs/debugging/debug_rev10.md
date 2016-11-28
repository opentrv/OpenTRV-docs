# REV10 BHR Debugging

CONFIG_REV10_SECURE_BHR as at 2016/11/15 eg tag 20161115-RC2b

## Debugging the SIM900 and OTSIM900Link
### Basic Debug Using LEDs On SIM900 Module
| LED | Status | Meaning | Expected Behaviour |
| :--- | :--- | :--- | :--- |
| Green, next to headers. | Solid on/off | LED on means the SIM900 has power. |  On when power applied to REV10. |
| Red, near board corner. | Solid on/off | LED on means SIM900 is switched on. | On during normal operation* |
| Green, near board corner. | Fast flashing** | SIM900 searching for a network. | When newly switched on, or know signal. |
| Green, near board corner. | Slow flashing*** | SIM900 registered to a network. | This is the expected behaviour during normal operation. |

\*   On startup will turn off briefly for a couple of seconds. During normal operation it will infrequently be turned off for a couple of seconds.

\**  Flashing multiple times a second.

\*\** Flashing ~once a second or slower.

### Sniffing the REV10-SIM900 Serial Connection
#### Physical Connection and Serial Settings
1. Connect hookup leads to the GND (black wire) and RX (yellow wire) lines of an FTDI cable, as shown:
![alt text](https://raw.githubusercontent.com/opentrv/OpenTRV-docs/master/docs/debugging/debug_ftdi_listenWithNoReset.jpg "FTDI cable connections")
1. Connect the GND lead to the REV10 ground and the RX lead to one of the pins shown:
    1. To read the REV10 Tx line:
    ![alt text](https://raw.githubusercontent.com/opentrv/OpenTRV-docs/master/docs/debugging/debug_rev10_rev10Tx.jpg "REV10 Tx connection")
    1. To read the SIM900 Tx line:
    ![alt text](https://raw.githubusercontent.com/opentrv/OpenTRV-docs/master/docs/debugging/debug_rev10_sim900Tx.jpg "SIM900 Tx connection")
1. Connect the FTDI cable to a computer.
1. Start up prefered serial monitor (Arduino serial monitor, minicom, screen, teraterm etc.) and set to 9600 baud, 8n1.
1. The radio is used infrequently during normal operation an so it may take several minutes before an output appears.

#### Example Outputs During Normal Operation
##### Startup
*TBA*

##### Sending Packets
**REV10:**
```
�AT+CIPSTATUS
AT+CIPSEND=62
������ ~@�`�b��{����$��;\xB/��/j�
```

**SIM900:**
```
AT+CIPSTATUS

OK

STATE: CONNECT OK
AT+CIPSEND=62

> �Ҥ�� .d(1�3���u.[��k������@����w�
```
