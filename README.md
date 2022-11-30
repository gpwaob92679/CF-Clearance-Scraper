# CF-Clearance-Scraper

A simple program for fetching cf_clearance cookies from websites issuing cloudflare challenges to users. This program works on JavaScript and managed challenges. 

## Clearance Cookie Usage
In order to bypass cloudflare challenges with the clearance cookies, you must make sure of two things:

- The user agent used to fetch the clearance cookie must match the user agent being used within the requests that use the clearance cookie
    > **Note**:
    > You can edit the user agent used by the scraper by changing the `USER_AGENT` variable. Depending on the user agent used, it may affect your ability to solve the cloudflare challenge
- The IP address used to fetch the clearance cookie must match the IP address being used to make the requests that use the clearance cookie

```mermaid
flowchart
	N14e["cf_clearance"]
	N14f["IP Address"]
	N150["User Agent"]
	N14e --> N14f
	N14e --> N150
```

## Installation

    $ pip install -r requirements.txt
    $ python -m playwright install --with-deps webkit


## Usage
```
usage: main.py [-h] [-v] [-d] -u URL [-f FILE] [-t TIMEOUT] [-p PROXY]

Fetches cf_clearance cookies from websites issuing cloudflare challenges to users

options:
  -h, --help            show this help message and exit
  -v, --verbose         Increase output verbosity
  -d, --debug           Run the browser in headed mode
  -u URL, --url URL     URL to fetch cf_clearance cookie from
  -f FILE, --file FILE  File to write the cf_clearance cookie to
  -t TIMEOUT, --timeout TIMEOUT
                        Request timeout (seconds)
  -p PROXY, --proxy PROXY
                        Proxy server to use for requests (SOCKS5 proxy authentication not supported)
```
```
Example: python main.py -u https://nowsecure.nl -f cookies.txt -v
```