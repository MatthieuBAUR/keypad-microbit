# keypad-microbit
ACCES CONTROL KEYPAD FOR MICRO:BIT

Send a number though bluetooth (UART) to the micro:bit card.

The following code must be loaded in the card:

Python:

```
def on_uart_data_received():
    global texte
    texte = bluetooth.uart_read_until("\n")
    basic.show_string(texte)
bluetooth.on_uart_data_received("\n", on_uart_data_received)

texte = ""
bluetooth.start_uart_service()
basic.show_icon(IconNames.SMALL_SQUARE)
```
