# OrbitalDump

### A simple multi-threaded distributed SSH brute-forcing tool written in Python

## How it Works

When the script is executed without the `--proxies` switch, it acts just like any other multi-threaded SSH brute-forcing scripts. When the `--proxies` switch is added, the script pulls a list (usually thousands) of SOCKS4 proxies from [ProxyScrape](https://proxyscrape.com/) and launch all brute-force attacks over the SOCKS4 proxies so brute-force attempts will be less likely to be rate-limited by the target host.

## Installation

You can install OrbitalDump through pip.

```shell
pip install -U --user orbitaldump
orbitaldump
```

Alternatively, you can clone this repository and run the source code directly.

```shell
git clone https://github.com/mehdirzfx/orbitaldump.git
cd orbitaldump
python -m orbitaldump
```
##Install Libraries

Run below command in Command line
```shell
pip install -r requirements.txt
```
or **Run as administrator** file ```install-library.bat```

## Usages

A simple usage is shown below. This command below:

- `-t 10`: launch 10 brute-forcing threads
- `-u user.txt`: read usernames from user.txt (one username per line)
- `-p pass.txt`: read passwords from pass.txt (one password per line)
- `-h ip.txt`: set brute-forcing target to `ip.txt`
- `--proxies`: launch attacks over proxies from ProxyScrape

```shell
python -m orbitaldump -t 10 -u users.txt -p pass.txt -h ip.txt --proxies
```

## Full Usages

You can obtain the full usages by executing OrbitalDump with the `--help` switch. The section below might be out-of-date.

```console
usage: orbitaldump [--help] [-t THREADS] [-u USERNAME] [-p PASSWORD] [-h HOSTNAME] [--port PORT] [--timeout TIMEOUT] [--proxies]

optional arguments:
  --help                show this help message and exit
  -t THREADS, --threads THREADS
                        number of threads to use (default: 5)
  -u USERNAME, --username USERNAME
                        username file path (default: None)
  -p PASSWORD, --password PASSWORD
                        password file path (default: None)
  -h HOSTNAME, --hostname HOSTNAME
                        target hostname file path (default: None)
  --port PORT           target port (default: 22)
  --timeout TIMEOUT     SSH timeout (default: 6)
  --proxies             use SOCKS proxies from ProxyScrape (default: False)
```
