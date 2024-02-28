# A simple countdown script for CTFd

### This script displays a countdown timer and loops between two provided dates, indicating whether it's counting down to the start or end of a CTF event. 

Here's a breakdown of its functionality:

1. The script defines two variables, countDownDate1 and countDownDate2, which are set to the start and end dates of the CTF event using placeholder values ({{ctf_start}} and {{ctf_end}}).

2. If the time is remaining:
        The remaining time is displayed in the format "Xd Yh Xm Xs" (days, hours, minutes, seconds) if days is greater than 0, otherwise only hours, minutes, and seconds are shown.
3. If meaning the countdown has passed:
        The message "Wait for the next announcement!" is displayed.

### Overall, this script continuously displays a countdown timer for the CTF event, switching between the start and end dates, and showing a message when the current countdown has ended.

![alt text](ctfd.png)
