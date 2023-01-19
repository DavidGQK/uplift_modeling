# Uplift modeling campaign
We need to select a part of clients so that the total profit of the campaign with such an offer would be as big as possible. <br/>
Source data - information about sales for the last 250 days, basic information about customers, history of launched campaigns. <br/>
`main.py` - main code file <br/>
`featurelib.py` - auxiliary file for preprocessing data <br/>
## Data description
### Data files
 - `customers.csv` - customer description <br/>
 - `receipts.parquet` - purchase history <br/>
 - `campaigns.csv` - history of campaigns <br/>
### Field description
**customers.csv** <br/>
 - `customer_id` - customer ID <br/>
 - `age` - customer age <br/>
 - `location` - customer's place of living

**receipts.parquet**[^1] <br/>
 - `customer_id` - customer ID <br/>
 - `date` - purchase date <br/>
 - `purchase_amt` - amount of purchase (in grams) <br/>
 - `purchase_sum` - purchase price (in units) <br/>

[^1]: a customer doesn't purchase more than once a day

**customer_id.csv** <br/>
 - `customer_id` - customer ID <br/>
 - `date` - the first day of discount <br/>
 - `n_offer_days` - discount duration (in days) <br/>
 - `target_group_flag` - target (1) / control (0) group flag <br/>

During the evaluation the metrics are calculated for a period of 30 days from the beginning of the discount.  
The output will be a generated .csv file with the list of customers who should make an offer for the next day