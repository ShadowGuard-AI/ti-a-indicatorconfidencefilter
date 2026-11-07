# ti-a-IndicatorConfidenceFilter

Filters threat intelligence indicators based on confidence scores. The tool is fully local: it reads a JSON list of indicators from a local file, keeps the records whose integer confidence score is at or above the minimum threshold given on the command line, and writes the filtered list to a local output file or stdout. It does not contact VirusTotal, AlienVault OTX, or any other feed or service, and it does not aggregate external feeds.

A record whose confidence is a JSON boolean (true or false) or any other non-integer type is rejected as malformed and cannot pass the filter. A record whose confidence is an integer outside the 0 to 100 range is also rejected as malformed. An empty input list exits non-zero with a no-indicators message, so a run over zero input is not reported as a completed filter. If the output file cannot be written, the run exits non-zero.

## Install
`git clone https://github.com/ShadowGuard-AI/ti-a-indicatorconfidencefilter`

## Usage
`python3 main.py -i input.json -c 50 -o output.json`

## Parameters
- `-h`: Show help message and exit
- `-i`: Path to the input JSON file containing threat intelligence indicators.
- `-c`: Minimum confidence score (0-100) for indicators to be included. Default is 50.
- `-o`: Path to the output JSON file to store the filtered indicators. If not specified, prints to stdout.

## License
MIT License. See LICENSE.
