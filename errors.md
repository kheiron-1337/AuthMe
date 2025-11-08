## Troubleshooting Guide: Common Errors & Causes
- This document outlines common errors and their technical causes for educational analysis.
- Note: These errors are errors that were found and resolved as a result of our observations. If you encounter any errors, you can contact us and report them.

## Local (Tool-Side) Errors

- **Error [A1]: "Disconnected" or "Connection Failed" when connecting to localhost.**
> Cause: This typically indicates a local setup issue. The localhost bridge (the fake proxy) may not have started correctly, or another application on your machine is already using the required address.
Analysis: Check that the address is free and restart the tool, potentially with administrative privileges.


- **Error [A2]: The tool crashes, freezes, or shows "File Not Found" errors.**
> Cause: Missing dependencies (e.g., correct Java runtime, required libraries) or the tool lacks the necessary permissions to read/write files or bind to network.
Analysis: Verify all prerequisites are installed and that the tool is not being blocked by a local firewall or antivirus software.
