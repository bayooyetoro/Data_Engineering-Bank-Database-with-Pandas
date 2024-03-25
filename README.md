# Data_Engineering-Project: Orchesrating a Bank Database with Pandas and SQLAlchemy
This is a data engineering project for an imaginary UK-based financial institution called `Mongo Bank`.
The bank aim to leverage data analytics to orchestrate a database for marketing data to handle their upcoming campaigns' data for further analytics.
Solution to this work is in the [`Mongo.ipynb file`]([./mongo.ipynb](https://github.com/bayooyetoro/Data_Engineering-Bank-Database-with-Pandas/blob/main/mongo.ipynb))

## Tasks
As the Bank aim to conduct more campaigns in the future, they’d love you to implement a robust RDBMS database capable of accommodating data from future campaigns, with a schema 
comprising three tables: `"Client", "Campaign", and "Economics"`

Lastly, you will write the SQL code that the bank can execute to create the tables and populate with the data from the csv files.

## Resources and Tools: 
They have supplied you with a csv file called `"bank_marketing.csv"`, which you will need to clean, reformat, and split, to save separate files based on the tables you will create. It was recommended to use `"Pandas", "Jupyter notebook", or "Python"` for these tasks to facilitate integgration with existing tools in the organization.

### client

| column | data type | description | original column in dataset |
|--------|-----------|-------------|----------------------------|
| `id` | `serial` | Client ID - primary key | `client_id` |
| `age` | `integer` | Client's age in years | `age` |
| `job` | `text` | Client's type of job | `job` |
| `marital` | `text` | Client's marital status | `marital` | 
| `education` | `text` | Client's level of education | `education` |
| `credit_default` | `boolean` | Whether the client's credit is in default | `credit_default` |
| `housing` | `boolean` | Whether the client has an existing housing loan (mortgage) | `housing` | 
| `loan` | `boolean` | Whether the client has an existing personal loan | `loan` |

<br>

### campaign

| column | data type | description | original column in dataset |
|--------|-----------|-------------|----------------------------|
| `campaign_id` | `serial` | Campaign ID - primary key | N/A - new column |
| `client_id` | `serial` | Client ID - references `id` in the `client` table | `client_id` |
| `number_contacts` | `integer` | Number of contact attempts to the client in the current campaign | `campaign` |
| `contact_duration` | `integer` | Last contact duration in seconds | `duration` |
| `pdays` | `integer` | Number of days since contact in previous campaign (`999` = not previously contacted) | `pdays` |
| `previous_campaign_contacts` | `integer` | Number of contact attempts to the client in the previous campaign | `previous` |
| `previous_outcome` | `boolean` | Outcome of the previous campaign | `poutcome` |
| `campaign_outcome` | `boolean` | Outcome of the current campaign | `y` |
| `last_contact_date` | `date` | Last date the client was contacted | A combination of `day`, `month`, and the newly created `year` |

<br>

### economics

| column | data type | description | original column in dataset |
|--------|-----------|-------------|----------------------------|
| `client_id` | `serial` | Client ID - references `id` in the `client` table | `client_id` |
| `emp_var_rate` | `float` | Employment variation rate (quarterly indicator) | `emp_var_rate` |
| `cons_price_idx` | `float` | Consumer price index (monthly indicator) | `cons_price_idx` |
| `euribor_three_months` | `float` | Euro Interbank Offered Rate (euribor) three month rate (daily indicator) | `euribor3m` |
| `number_employed` | `float` | Number of employees (quarterly indicator)| `nr_employed` |


## To replicate this work, you need:
1. Jupyter Notebook
2. Dependencies: pip install pandas, numpy, sqlalchemy, socket, pyodbc
3. SQL Server Instance on your local computer
