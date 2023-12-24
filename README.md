# STM32-MORSE-ENCODER
Morse encoder for embedded devices with STM32. Written in C language with STM32CubeIDE.

The device communicates via serial port with a PC, from which it receives messages that are reprocessed and returned encoded. Specifically, the entry of a new message must be made from the PC keyboard and then sent to the embedded device, via the serial port and following the pressing of the "send" character.

The system can receive messages consisting of ASCII-coded text, limited to characters between A-Z and numbers in the range 0-9 (in the case of a plaintext message), and meets the following specifications:
+Upon receiving a message in "plain text," the device encodes it in Morse code (dots and dashes) and returns it to the PC via serial port.
The encoded message transmitted to the PC is contextually displayed by exploiting the green LED on board the board.
+It uses the Producer/Consumer paradigm for encoding message characters. Specifically, the embedded system initiates the encoding and returns the corresponding encoding on the serial as soon as the first character is received from the PC.
+Receipt/encoding/retransmission management is done through the use of Tasks and a shared queue.
