![Image](https://github.com/user-attachments/assets/fca3c8ec-1fb6-4a82-a97e-f42ea481ffa1)
# PyTrack
PyTrack is a lightweight, customizable Python library for displaying real-time progress bars, enhancing the user interface of your scripts. Easy to use and perfect for tracking complex tasks.
# Installation 📦
Use the following command to install PyTrack through pip:
``` python
pip install PyTrack
```
# Features 🚀
The loading bar displays much useful info, such as:
- A progress bar with color coding to indicate the completion percentage:
  - 0% - 33% RED
  - 33.01% - 66% YELLOW
  - 66.01% - 100% GREEN
- Current progress displayed as a percentage
- The name of the current operation
- Time elapsed since the start of the operation
- Estimated remaining time, with color changes based on the expected wait time
- Current speed displayed as iterations per second (it/s), with color changes based on speed
- Current CPU usage, shown as a percentage
- Current RAN usage, shown as a percentage
# Implementation in your code ⬇️
Use the following function to create a loading bar
``` python
progress_bar()
```
The loading bar is fully customizable. The function accepts the following arguments:
- current iteration *                          | Indicates the current progress
- total_iterations *                           | Indicates the total amount of operations
- start_time *                                 | Displays the elapsed time since the start of the process.
- bar_lenght                                   | Defines the total length of the loading bar.
- done_character                               | The ASCII character used to display completed progress.
- to_do_character                              | The ASCII character used to represent remaining operations.
- process                                      | The name of the process being tracked.

**Arguments marked by * are _mandatory_. Others can be left blank**
.
**Start time needs to be defined inside your own script, the example below shows how you should do it**

Here's a detailed example that uses every argument:
``` python
import time

total_steps = 100

start_time = time.time()  # Starts the timer

for i in range(total_steps + 1): # Counts to 100

    progress_bar(current_iteration=i, total_iterations=total_steps, start_time=start_time, bar_length=100, done_character="█", to_do_character="_", process="Counting")

    time.sleep(0.05)
```
The output is the following:

[██████████████████████████████████████████████████████████████████__________________________________] 66.0%  |  Counting  |  Time elapsed: 00:03.47  |  Remaining: 00:01.79  |  Speed: 18.99 it/s  |  CPU: 1.6%  |  RAM: 31.8%

**Note: Colors may not be displayed on GitHub. I'm planning to add a .gif to better illustrate how the bar functions.**

