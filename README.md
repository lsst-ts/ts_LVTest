# ts_LVTest
The Test CSC in LabVIEW.

This application polls the following commands:
- disable - Executed in the enabled state, transitions to the disabled state
- enable - Executed in the disabled state, transitions to the enabled state
- exitControl - Executed in the standby state, transitions to the offline state
- standby - Executed in the disabled state, transitions to the standby state
- start - Executed in the standby state, transitions to the start state
- fault - Executed in any state, transitions to the fault state
- setArrays - Executed in the enabled state, publishes the arrays event and telemetry
- setScalars - Executed in the enabled state, publishes the scalars event and telemetry
- wait - Executed in the enabled state, waits the specified amount of time

# Notes
- The test csc doesn't execute commands in parallel so if you issue the wait command that must complete before the next command is executed. This differs from the python implementation which can execute the wait command and then while the wait command is executing run another command.
- You can use the LVTEST_INDEX environment variable to change the index used. Currently this is bugged and doesn't work on the SALLV side of things with the monitor application.
