# alarm-clock-project
#  Console Alarm Clock

A simple, command-line alarm or timer application built in Python. This script allows the user to set a timer in minutes and seconds, which then counts down on the console and plays a sound file when the time is up.

##  Features

* **User Input:** Easily set the duration in minutes and seconds.
* **Real-time Countdown:** Displays the remaining time (MM:SS) in the console, updating every second.
* **Clear Display:** Uses ANSI escape codes to clear the screen and continuously update the time display in the same spot.
* **Sound Notification:** Plays a local sound file (`alarm.mp3`) when the timer reaches zero.

## 🛠️ Prerequisites

Before running the script, ensure you have **Python 3** installed on your system.

You also need the following external Python libraries:

1.  **`playsound`**: For playing the alarm sound file.

### Installation

Install the required library using **pip**:

```bash
pip install playsound
 Getting Started
1. Project Setup
Save the provided Python code into a file named, for example, timer.py.

Obtain an audio file (e.g., a short, loud sound) and save it in the same directory as the Python script.

Crucially, rename the audio file to alarm.mp3.

2. Running the Alarm
Open your terminal or command prompt, navigate to the directory where you saved the files, and run the script:

Bash

python timer.py
3. Usage
The script will immediately prompt you for the time:

how many minutes to wait: Enter the desired minutes (e.g., 5).

how many seconds to wait: Enter the desired seconds (e.g., 30).

The countdown will begin, and the console will display the time remaining. When the timer hits 00:00, the alarm.mp3 file will play.

Code Breakdown
The alarm(seconds) Function
The core logic resides here:

time_elapsed = 0: Initializes a counter for how long the alarm has been running.

print(CLEAR): Clears the entire console screen.

while time_elapsed < seconds:: The main loop that runs for the duration of the timer.

time.sleep(1): Pauses execution for exactly 1 second, controlling the update rate.

Time Calculation:

time_left = seconds - time_elapsed

minutes_left = time_left // 60 (Integer division to get minutes)

seconds_left = time_left % 60 (Modulo operator to get remaining seconds)

Display Update:

print(f"{CLEAR_AND_RETURN}Alarm will sound in: {minutes_left:02d}:{seconds_left:02d}")

CLEAR_AND_RETURN (\033[H): This ANSI Escape Code moves the cursor back to the top-left corner of the terminal, allowing the new time string to overwrite the previous one, creating the illusion of an updating counter.

{:02d}: Formats the minutes and seconds with a leading zero if the number is less than 10 (e.g., 9 becomes 09).

Alarm Sound: Once the loop finishes, playsound("alarm.mp3") is called.

Global Variables
CLEAR = "\033[2J": ANSI code to clear the entire screen.

CLEAR_AND_RETURN = "\033[H": ANSI code to move the cursor to the home position (top-left).

Known Issues / Notes
Sound File Path: Ensure alarm.mp3 is in the same directory as the script, or provide the full path to the file in the playsound() function.

ANSI Support: The screen clearing and cursor movement features rely on ANSI escape codes. While most modern terminals (Linux, macOS, and newer Windows 10/11 terminals) support this, older or non-standard environments might display garbled text or simply print the countdown without overwriting the previous lines.

Blocking: The playsound function might block execution, depending on the length of your sound file and the operating system.
