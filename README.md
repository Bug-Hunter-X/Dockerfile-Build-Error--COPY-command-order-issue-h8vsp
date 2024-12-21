# Dockerfile Build Error: Incorrect COPY command order

This repository demonstrates a common error in Dockerfiles where the order of `COPY` commands leads to build failure. The `requirements.txt` file is copied before the `app.py`, resulting in an error when the build attempts to run `pip install`.

## Bug
The original `Dockerfile` demonstrates the issue:  The `requirements.txt` file is copied before the application code that depends on it, leading to a failure during the `pip install` step.

## Solution
The `Dockerfile_solution` shows the corrected version with the `COPY` commands rearranged, solving the build error.  This ensures that the application code and dependencies are available at the correct stage of the build process.