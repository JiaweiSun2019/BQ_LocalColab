# BQ_LocalColab

## Here are the steps to connect with BQ datasets in Colab local runtime.

Step 1: Get a JSON file by following this instruction. 
https://cloud.google.com/bigquery/docs/reference/libraries#client-libraries-install-python

Step 2: Save the JSON file in the notebook subdirectory where you colab Dockerfile lives

Step 3: In Colab, modify and run following Sample Script:

```
import os
os.environ["GOOGLE_APPLICATION_CREDENTIALS"] = "/ds_stack/notebooks/GoodRx-data-ga-dev-xxxxxx.json"
project_id = 'goodrx-data-ga-dev'


from google.cloud import bigquery
client = bigquery.Client(project=project_id)

SQL= '''
  SELECT 
    * 
  FROM `XXXXXXX`
  '''

df = client.query(SQL).to_dataframe()```
