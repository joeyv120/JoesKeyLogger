# Joe's Key Logger
This is a simple keylogger that runs in the background and records keystrokes to `key_log.txt`, which is located in the same directory as the program.

The intended purpose is to study personal key usage for optimizing a custom keyboard layout. This software is not to be used for unlawful or nefarious activities, or without the knowledge and explicit consent of the keyboard operator.

As long as the program is open the keystrokes are being recorded. Recording stops as soon as the program is closed.

> ## Do not run this program while typing sensitive information including, but not limited to usernames, passwords, account numbers, banking information.

All keystrokes are appended to `key_log.txt` and saved in no other location. This file can be deleted at any time. Individual lines can be deleted if desired.

# Output format
After running for the first time `key_log.txt` is created in the same directory as the program. This file stores all of the recorded keystrokes. It can be deleted at any time if desired, and a new file will be created the next time the program is executed.

Each line in the log is a seperate key or combination of keys. The program will attempt to parse key combinations such as `Key.alt+Key.tab` or `Key.ctrl+s`. Combinations that include modifications by holding [shift] will be suffixed with the unmodified (canonical) character; for example a quesiton mark (?) is recorded as `Key.shift+/`

>Note: buffering occurs on key presses, but they are not recorded until a key is released. This allows for parsing of key combinations to a single line.

See example_log.txt for an example.


# To-Do:
    The expected squence is LIFO. If the sequence is FIFO then the keys are not properly popped from the dictionary. For example, pressing `a+s+d+f`, then releasing in FIFO order produces duplicate results.