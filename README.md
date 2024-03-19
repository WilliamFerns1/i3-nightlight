# Nightlight

Nightlight is a script for managing display color temperature to reduce blue light exposure during night-time computer use. This repository provides a simple script to adjust the color temperature of your display and integrate it with your i3 window manager configuration.

## Installation

To install Nightlight, follow these steps:

1. Clone the repository:

    ```bash
    git clone https://github.com/WilliamFerns1/i3-nightlight.git
    ```

2. Change directory into the cloned repository:

    ```bash
    cd i3-nightlight
    ```

3. Move the script to `/usr/local/bin` using sudo:

    ```bash
    sudo mv nightlight /usr/local/bin/nightlight
    ```

4. Add the following line to your i3 configuration file (`~/.config/i3/config`):

    ```text
    # nightlight:
    exec --no-startup-id nightlight start_time end_time interval_minutes >/dev/null 2>&1 &
    ```

    Replace `start_time`, `end_time`, and `interval_minutes` with your desired values. This command ensures that Nightlight starts automatically with your i3 session.
    
    Here is an example of a command that starts Nightlight at 8:00 PM, ends at 6:00 AM, and looks if the current time is inbetween the start and end time, every 30 minutes:

    ```text
    exec --no-startup-id nightlight 20:00 06:00 30 >/dev/null 2>&1 &
    ```

5. Restart your i3 session or reload the configuration file for the changes to take effect. If you don't know how, just restart your computer by running `reboot` in your terminal.

## Customization

You can adjust the start time, end time, and interval for Nightlight by editing the `exec` command in your i3 configuration file. Simply modify the values in the command to match your preferences.

## Usage

Once installed and configured, Nightlight will automatically adjust the color temperature of your display according to the specified schedule. You can also manually run the `nightlight` command in the terminal to activate it outside of the scheduled times.

Just run the command `nightlight` in your terminal to see the usage. 

```bash
# Example:
nightlight 20:00 06:00 30
```

## Contributing

Contributions are welcome! If you encounter any issues or have suggestions for improvements, feel free to open an issue or submit a pull request. It would be an honor if you can make the script use Redshift instead.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
