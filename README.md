# iloginr

**Version 4.1** - Web-based Single Sign-On (SSO) password generator

[![License: GPL](https://img.shields.io/badge/License-GPL-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)

## Overview

iloginr is a web-based password generation tool that creates unique, service-specific passwords derived from a single master password. Your passwords are **never stored anywhere** - they are generated on-demand using a deterministic algorithm, meaning the same inputs will always produce the same password.

Think of it as similar to Google Application Specific Passwords, but completely client-side and under your control.

## Features

- **Zero Storage**: Passwords are generated algorithmically and never stored
- **Service-Specific**: Each service/URL gets a unique password
- **Deterministic**: Same inputs always generate the same password
- **Customizable**: Advanced options for password complexity and format
- **Version Control**: Support for multiple algorithm versions (1.0, 2.0, 3.0)
- **Password Versioning**: Increment password version when you need to change a password
- **Client-Side**: All processing happens in your browser - no server required

## How It Works

iloginr uses SHA-256 or SHA-512 hashing (depending on the version) to generate passwords based on:
- Service name/URL
- Your master password
- Password version number (optional)
- Algorithm version

The algorithm is deterministic, so you can regenerate the same password anytime by entering the same information.

## Usage

### Basic Usage

1. Enter the **Service/URL** (e.g., "github.com", "facebook", etc.)
2. Enter your **Master Password**
3. Click **ilogin** to generate your password

The generated password will appear below the form, formatted with pipes (`|`) for easier reading.

### Advanced Options

Click the "Advanced option" checkbox to access:

- **App Version**: Choose algorithm version (3.0, 2.0, or 1.0)
  - Version 3.0 (default): Uses SHA-512, most secure
  - Version 2.0: Uses SHA-512 with slightly different character set
  - Version 1.0: Uses SHA-256, legacy support

- **Use capital letters**: Include uppercase characters in the password
- **Use numbers**: Include numeric digits in the password
- **Use special characters**: Include special symbols in the password
- **Password length**: Set the desired password length (default: 16)
- **Password version**: Increment this when you need to change a password for a service (default: 1)

## Installation

### Hosted Version

Simply visit [https://iloginr.com](https://iloginr.com) (or your hosted instance)

### Self-Hosting

1. Clone this repository:
   ```bash
   git clone https://github.com/iloginr/ilogin.git
   ```

2. Serve the files using any web server:
   ```bash
   # Using Python's built-in server
   python -m http.server 8000

   # Or using Node.js
   npx http-server
   ```

3. Open your browser to `http://localhost:8000`

## Security Considerations

### Strengths
- **No password storage**: Passwords cannot be leaked from a database
- **Offline capable**: Can be used without internet connection
- **Open source**: Code can be audited for security
- **Client-side**: Master password never leaves your device

### Important Notes
- Your **master password** is critical - if forgotten, you cannot recover your generated passwords
- The **service name** must be entered exactly the same way each time
- Consider backing up your service names/settings if using custom configurations
- While deterministic generation is convenient, if your master password is compromised, all service passwords are potentially compromised

## Browser Compatibility

Works in all modern browsers that support:
- ES5 JavaScript
- SHA-256/SHA-512 hashing (via jsSHA library)

## Related Projects

This is the web-based version of iLogin. For a command-line Python version, see:
- [ilogin on PyPI](https://pypi.python.org/pypi/ilogin)
- [ilogin on GitHub](https://github.com/iloginr/ilogin)

## License

GPL - Copyright Alin Voinea

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## Changelog

### Version 4.1
- Web-based interface
- Mobile-friendly responsive design
- Advanced password customization options
- Support for legacy algorithm versions

## Support

For issues, questions, or contributions, please visit the [GitHub repository](https://github.com/iloginr/ilogin).
