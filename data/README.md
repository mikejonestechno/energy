# Data Sources

## NemWeb

NemWeb appears to be the official source of AEMO data - detailed and technical.

https://nemweb.com.au/Reports/Current/

### HistDemand
- Daily files of historical demand by state, 48 x 30 min periods

### P5_Reports
- 5 min files (directory contains 2 days worth of 5 min data) w fuel mix for wind and solar, need to learn codes for coal, gas, battery
- there are also FCAS REQUIREMENT files that appear to be summarized bid adjustments, no fuel mix

## OpenNem

OpenNem creates aggregated simplified data sets for the fuel mix and price data.

The [opennem/nemweb](https://github.com/opennem/nemweb) project on GitHub contains a python3 package to directly download and process AEMO files from nemweb into a local sqlite database. 

However `pip install opennem` fails, there are several stale branches and issues, the project has no commits since December 2019, and appears abandoned.

Found `pip install nemweb` succeeds, still limited [doc available](https://nemweb.readthedocs.io/en/latest/index.html) from the GitHub repo. 

The [opennem/opennem](https://github.com/opennem/opennem) project does seem to be active with regular updates.

The OpenNem website does have an option to export data from their site, including 5 min periods with fuel mix and price - exactly what I'm after...

https://opennem.org.au/energy/nem/?range=1d&interval=5m&view=discrete-time

However the export links seem to generate unique urls with guids

https://opennem.org.au/0903bbb8-2ef0-4ade-8d5e-317463728b6e

The API is currently still open without authentication.

### OpenNem API Data

GET list of network and region codes eg NEM, VIC1
- https://api.opennem.org.au/networks

Use the values in subsequent requests

GET historical fueltech data (5 min interval of last 7 days)
- https://api.opennem.org.au/stats/power/network/fueltech/{network_code}/{network_region_code}


https://api.opennem.org.au/stats/power/network/fueltech/NEM/VIC1
redurects to a response here
https://data.opennem.org.au/v3/stats/au/NEM/VIC1/power/7d.json

``` bash
curl -o VIC1.json https://data.opennem.org.au/v3/stats/au/NEM/VIC1/power/7d.json
```

