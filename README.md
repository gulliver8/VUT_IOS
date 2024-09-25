# IOS - Operating system -Tradelog

Tradelog is a script for analyzing trading system records. The script filters records and provides statistics according to the user's specifications.

## Contributors

*Lucia Makaiová*  [xmakai00]

## Usage specification

Script analyzes records from a stock trading system. It filters data and provides statistics based on the user input. Records can be supplied as `.log` files or multiple `.log` files compressed in `gzip` format. If no log files are provided, the script expects logs from standard input.
Logs are in CSV format where ; is a separator. Every line represents one transaction in format:
`DATE TIME;TICKER;TRANSACTION TYPE;UNIT PRICE;CURRENCY;QUANTITY;TRANSACTION ID`

### Usage
  * `tradelog [-h|--help]`          
  * `tradelog [FILTER] [COMMAND] [LOG [LOG2 [...]]`

### Commands 
  * `list-tick`
  * `profit`
  * `pos`
  * `last-price`
  * `hist-ord`
  * `graph-pos`   
### Filters  
  * `-a DATETIME`	**Format:**	`[YYYY-MM-DD HH:MM:SS]`  
  * `-b DATETIME`	**Format:**	`[YYYY-MM-DD HH:MM:SS]`
  * `-t TICKER`
  * `-w WIDTH` **Format:** `[natural number]`
`-w WIDTH` **Format:** `[natural number]`

## Examples
``$ ./tradelog -t TSLA -t GOOG stock.log
2021-07-29 11:30:42;TSLA;buy;680.00;USD;50;78dac354-7943-11eb-929d-8c85906a18fd
2021-07-29 14:45:33;GOOG;sell;2725.80;USD;20;89acbd43-7943-11eb-929d-8c85906a19aa
2021-07-30 09:00:25;TSLA;sell;690.50;USD;50;90cad123-7943-11eb-929d-8c85906a1a5b
2021-07-31 08:45:10;TSLA;buy;700.00;USD;25;ccfdea23-7943-11eb-929d-8c85906a1e5a
2021-07-31 12:10:20;GOOG;buy;2740.15;USD;10;ddbad234-7943-11eb-929d-8c85906a1f6b
``

``$ ./tradelog list-tick stock-2.log
AAPL
TSLA
GOOG
MSFT
AMZN
NFLX
``
