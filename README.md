## EDF Inspector
This support script provides a quick way to inspect and preview EDF (European Data Format) files. It extracts metadata (file duration, start date, number of signals) and prints a small chunk of signal data for each channel into a text file.

## Features
- Reads .edf files using pyEDFlib.
- Extracts basic EDF metadata:
   - File duration
   - Start date/time
   - Number of signals

- Loops through all channels to:
    - Print channel labels
    - Show the first N data points (default = 10)
    - Show total signal length

- Saves output to edf_output_preview.txt for easy review.

## Requirements
Install the required package:

    pip install pyedflib

## Usage
1. Update the script with your EDF file path:

        edf_file = "C:/path/to/your/file.edf"

(Optional) Change the number of sample points per signal by modifying:

    data_chunk_size = 10

2. Run the script:

        python edf_inspector.py

3. The results will be saved in edf_output_preview.txt.

## Example Output

      ========== EDF File Information ==========
      File Duration: 600 seconds
      Start Date: 2025-09-14 10:30:00
      Number of Signals: 6

      ========== Signal Data ==========
      Reading Signal 0: F4:M1
      Data chunk: [5.0, 4.8, 4.9, 5.1, 4.7, 4.9, 5.0, 5.2, 5.0, 4.9]
      Signal Length: 3000

## Notes
- This script is intended as a support tool for inspecting EDF files before deeper analysis.
- Useful for checking channel availability, verifying signal lengths, and confirming data quality before running EEG processing pipelines.
