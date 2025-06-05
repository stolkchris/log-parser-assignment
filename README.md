# Log parser

## Context

A distributed target execution system has just been launched and taken into production as an improvement to the existing CI/CD system.
This means that each job now runs multiple targets. With this new feature, a need was exposed for more log parsing to
expose which of the targets executed in a job failed, including associative information such as the job branch and commit SHA.

## Assignment

The assignment is to create a script that parses each of the log files that are found in the `/var/log` directory. The script
must aggregate all failed targets and print the following about each target:

* Target name
* Target start time
* Target end time
* Target duration
* Reason of failure
* Job ID
* Job commit SHA
* Job branch

All failed targets must be grouped based on job branch and ordered by start time so that the most recent failed target is printed first.

## Constraints

* Assume that the log files are located in the `/var/log` directory.
* Assume that the log files are named in the following format: `job_${TIMESTAMP}.log`.
* Assume that each log file follows the same format
* Assume that the environment in which you are processing these log files is memory starved and only has 256mb of memory available.
* Assume that the environment in which you are processing these log files is CPU starved and only has 100ms of CPU available.

You are free to use the programming language in which you feel most comfortable, so long as it fits within the constraints listed above.
