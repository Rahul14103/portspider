# portspider

Scanning a single host is easy; scanning an entire CIDR range and checking which services answer takes more work. portspider provides a command-line workflow for scanning network ranges, then passing discovered ports to service-specific modules.

## Features

- Scan CIDR network ranges with multiple threads.
- Check HTTP ports and record page titles.
- Inspect MySQL, MongoDB, SSH, printer, and game-server ports with dedicated modules.
- Scan custom port lists with the `manual` module.
- Configure a module, run it, and save results under `logs/`.

## Installation

Clone the repository and install its Python dependencies in a virtual environment:

```sh
git clone https://github.com/your-org/portspider.git
cd portspider
python3 -m venv .venv
. .venv/bin/activate
python3 -m pip install -r requirements.txt
```

Use a Python 3 installation. The original project targeted Python 3.3 through 3.6, so older dependencies may require an environment that matches those versions.

## Usage

Start the interactive console:

```sh
python3 portspider.py
```

Choose a module, set its network, then run the scan:

```text
portSpider $> use http
portSpider/http $> options
portSpider/http $> set network 192.168.0.0/24
portSpider/http $> run
```

The console prints scan results and writes them to a text file in the `logs/` directory. Use `modules` to list available modules, `back` to leave the selected module, and `exit` to close the program.

Only scan systems and networks that you own or have explicit permission to test. Service checks such as default-credential tests can affect remote systems.

## License

portspider is released under the MIT License. This project is based on [xdavidhu/portSpider](https://github.com/xdavidhu/portSpider), originally created by David Schütz and contributors. See the `LICENSE` file for the complete license text and attribution details.
