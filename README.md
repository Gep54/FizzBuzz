# Fizz Buzz Console

A hardware Fizz Buzz game for the STM32G431KB. Numbers count up on an 8-digit MAX7219 display; you press **Fizz** and **Buzz** in time with the classic rules.

## The game

Fizz Buzz is a counting game. Numbers appear in order, and for each one you must answer correctly:

- multiples of **3** → press **Fizz**
- multiples of **5** → press **Buzz**
- multiples of **both** (15, 30, …) → press **Fizz** and **Buzz**
- anything else → press nothing

Miss a required press, or press when you should not, and the round ends. Your score is the last number you survived.

## The console

This firmware drives a small physical console:

- **STM32G431KB** microcontroller (STM32CubeIDE / CubeMX project `LPS_fizz_buzz`)
- **MAX7219** 8-digit 7-segment display over SPI (current number, countdown, and score)
- **Fizz**, **Buzz**, and **Start** buttons, each with a matching LED
- a heartbeat LED that blinks as the counter advances
- optional **USART2** serial output at 9600 baud for start, shout, and game-over messages (currently commented out in `Core/Src/main.c`)

Press **Start** after boot. The display counts down from 3, then the round begins. After game over, the score is shown and you can start again.
