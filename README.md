# check-csp Script

The `check-csp` script is a Bash utility designed to help developers and security analysts check if a specific domain is listed in the Content-Security-Policy (CSP) header of a website. This can be particularly useful for verifying CSP directives during web development or security assessments.

## Prerequisites

- Bash shell
- `curl` command-line tool

## Installation

1. Download the `check-csp` script.
2. Make the script executable:
   ```bash
   chmod +x check-csp
   ```

## Usage

To use the script, you need to provide the website URL, the CSP directive you want to check, and the domain you're searching for within that directive.

```
./check-csp [options] <website URL> <CSP directive> <domain to search>
```

### Options

- `-v` Verbose mode. Print more information about the process.
- `-t` Set timeout in seconds. The default is 10 seconds.
- `-h` Display the help message.

### Example

To check if `otherdomain.com` is included in the `script-src` directive of `https://myapp.com` with verbose output:

```
./check-csp -v -t 5 https://myapp.com script-src otherdomain.com
```

## Features

- **Verbose Mode**: Use the `-v` flag for detailed output during script execution.
- **Custom Timeout**: Specify a custom timeout for the `curl` request with `-t`. Default is 10 seconds.
- **Help Message**: Use `-h` to display usage information.

## Error Handling

- The script checks if `curl` is installed and exits with an error message if it is not found.
- It verifies that all required arguments are provided, or else it shows a usage message.
- The script exits with an error if the CSP header is not found or the website does not respond.

## Contributing

Feel free to fork the repository and submit pull requests to improve the script or add new features.

## License

This script is released under the MIT License. See the LICENSE file for more details.

## Disclaimer

This script is for educational and security assessment purposes only. Always ensure you have permission before testing a website.
