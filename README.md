# Time Offset Checker for Embedded Devices

This script checks the time offset of an embedded device by comparing its system and RTC (hardware clock) times with the real time retrieved from a reliable time API. It identifies and displays any drift between these times in a tabular format.

## Prerequisites

- The device must support the `date`, `hwclock`, and `curl` commands.
- Internet access to reach the real time API at `http://worldtimeapi.org/api/ip`.

## Configuration

Before using the script, ensure the following tools are installed and accessible on your device:

- `curl`: For fetching real time from the web API.
- `hwclock`: For accessing the hardware clock.
- `date`: For managing and formatting timestamps.

## Usage

1. **Clone the script to your device**:

    ```sh
    git clone https://github.com/yourrepo/time-offset-checker.git
    cd time-offset-checker
    ```

2. **Make the script executable**:

    ```sh
    chmod +x check_time_offset.sh
    ```

3. **Run the script**:

    ```sh
    ./check_time_offset.sh
    ```

## Output

The script provides output in a tabular format, displaying the current real time, system time, RTC time, and the detected drifts in seconds:

| Real Time                  | System Time                | RTC Time                   | Drift (Sys - Real)         | Drift (Sys - RTC)          | Drift (RTC - Real)         |
|----------------------------|----------------------------|----------------------------|----------------------------|----------------------------|----------------------------|
| 2023-09-10 17:32:18        | 2023-09-10 17:32:18        | 2023-09-10 17:32:18        | 0                          | 0                          | 0                          |

Note: If the script fails to fetch the real time, it will skip the iteration and retry after 60 seconds.

## Troubleshooting

- Ensure that `curl`, `hwclock`, and `date` commands are installed and accessible in your device's PATH.
- Verify that your device can connect to `http://worldtimeapi.org/api/ip`.

## License

This project is licensed under the MIT License.
