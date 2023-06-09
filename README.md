

# iCaly Task Scheduler // Currently Borked

iCaly is a task scheduler tool that helps you manage your daily tasks and create an optimized schedule based on task priorities and due dates. It takes a CSV file containing task names, priorities, due dates, and durations and outputs an iCalendar (.ics) file that can be imported into most calendar applications.

## Installation

1. Clone the repository to your local machine.
   ```
   git clone https://github.com/RealVishy/iCaly-Task-Scheduler.git
   ```
2. Navigate to the project directory.
   ```
   cd iCaly-Task-Scheduler
   ```
3. Install the required packages using pip.
   ```
   pip install -r requirements.txt
   ```

## Usage

1. Create a CSV file named tasks.csv with columns for task name, priority (on a scale of 1-3 with 1 being the lowest and 3 being the highest), due date (in the format of YYYY-MM-DD), and duration in hours.

For example, a table like this:


| Task                     | Duration | Due Date   | Priority |
| ------------------------| --------:| :--------: | :-------: |
| Programming Week 8 Notes | 1.5      | 2023-05-01 | 1        |
| Programming Week 8 Labs  | 1        | 2023-05-01 | 2        |

Would become this:

```
Task,Duration,Due Date,Priority
Programming Week 8 Notes,1.5,2023-05-01,1
Programming Week 8 Labs,1,2023-05-01,2
```

Note: If a task's duration exceeds the remaining time in the day, it will not be included in the schedule. The tool assumes that tasks can be scheduled from 9:00 AM to 11:00 PM. Tasks are sorted by due date and priority, with higher priority tasks taking precedence.

2. Run the script `icaly.py`.
   ```
   python icaly.py
   ```
3. The tool will output an iCalendar file named `schedule.ics` in the project directory.
4. Import the iCalendar file into your preferred calendar application by selecting "Import Calendar" and selecting the file.

## Example Files

To help you get started with iCaly Task Scheduler, example `tasks.csv` and `schedule.ics` files are included in the repository. You can use these files as a template to create your own task list and import the schedule into your preferred calendar application.

The `tasks.csv` file contains sample tasks with their names, durations, due dates, and priorities. The `schedule.ics` file is the iCalendar file generated by the tool for the sample tasks.

Feel free to modify the example files or create your own based on your needs.

## Example Output

Here's an example of what the iCalendar file generated by the iCaly Scheduler might look like:

```
BEGIN:VCALENDAR
BEGIN:VEVENT
SUMMARY:Programming Week 8 Labs
DTSTART:20230426T215528
DTEND:20230426T225528
PRIORITY:2
END:VEVENT
END:VCALENDAR
```

In addition to the iCalendar file, the iCaly Scheduler will also print out your tasks for quick review:

```
Schedule:
1. Programming Week 8 Labs (1 hours) from 9:36 PM to 10:36 PM
```

## Contributions

Contributions to the iCaly Task Scheduler project are always welcome! If you find a bug or have a suggestion for a new feature, please open an issue on the GitHub repository or create a pull request with your proposed changes.

## License

This project is licensed under the MIT License. See the `LICENSE` file for more information.
