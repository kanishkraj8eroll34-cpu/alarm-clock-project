Python Alarm Clock
This is a simple Python script that functions as a command-line alarm or countdown timer.

Features
Countdown Display: Shows the remaining time in MM:SS format directly in the terminal.

Simple Setup: Requires only a single external library.

Sound Alert: Plays a sound file (alarm.mp3) when the countdown reaches zero.

Prerequisites
You need Python 3 installed on your system.

This script requires the playsound library. Install it using pip:

Bash

pip install playsound
You will also need an MP3 file named alarm.mp3 in the same directory as the script. This file will be played when the timer is finished.

How to Run
Save the Code: Save the provided Python code into a file, for example, alarm_timer.py.

Place Sound File: Ensure your desired alarm sound, named alarm.mp3, is in the same folder.

Execute: Open your terminal or command prompt, navigate to the directory where you saved the files, and run the script:

Bash

python alarm_timer.py
Set Timer: The script will prompt you to enter the number of minutes and seconds to wait.

Example:

how many minutes to wait: 0
how many seconds to wait: 10
Countdown: The terminal will display the live countdown.

Alarm: When the timer finishes, the alarm.mp3 file will play.
Code Overview
The main functionality is within the alarm function:

alarm(seconds):

Takes the total waiting time in seconds as input.

Uses ANSI escape codes (\033[2J for CLEAR and \033[H for CLEAR_AND_RETURN) to clear the terminal and move the cursor to the top, allowing the countdown to update in place.

The while loop runs for the duration specified by seconds, sleeping for one second in each iteration (time.sleep(1)).

It calculates the minutes and seconds remaining and prints the formatted countdown string (e.g., 00:10).

Finally, it calls playsound("alarm.mp3") to trigger the alarm.

The script then takes user input for minutes and seconds, calculates the total_seconds, and calls the alarm function.