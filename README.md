## Swatch ##
```
python -m vskit.scripts.swatch --input_table=<input_table> --database_name=<clientdb> --output_table=<output_table>
```

## TrendAnalysis ##
```
1) Activate virtualenv where vskit is installed ( i am using prod_vskit_361 ).
2) To run trend analysis for ruroc, navigate to '/home/vantena/ruroc_workspace/trend_analysis' 
3) Make sure you have trend_configs created for the client in json format ( i am using '/home/vantena/ruroc_workspace/trend_analysis/trend_configs' ).
4) Run the following command: 
  python -m vskit.scripts.trend_analysis --given_timeframe=<timeframe> --trend_config_json_path='/home/vantena/ruroc_workspace/trend_analysis/trend_configs/' run

"""
sample given_timeframe:
	given_timeframe = '[
   {
      "end_date":"2021-02-28",
      "name":"T1",
      "start_date":"2020-03-01"
   },
   {
      "end_date":"2020-02-28",
      "name":"T2",
      "start_date":"2019-09-01"
   },
   {
      "end_date":"2019-08-31",
      "name":"T3",
      "start_date":"2017-08-01"
   }
]'
"""
```

## PurchaseProb ##
```
python -m vskit.scripts.prob_to_purchase --config=<config> run

"""
sample config:
	config = "{'input_data':{'features_data':
	{
	  'dataset_name': 'purchase_prob_demo',
	  'source_type': 'bq',
	  'table_name': 'CLUSTERING_FEATURES_MATRIX',
	  
	},'cluster_data':{
	  'dataset_name': 'purchase_prob_demo',
	  'source_type': 'bq',
	  'table_name': 'CLUSTERING_CLUSTERS_ASSIGNMENT_TEMP',
	  'columns':['account_id','cluster','features_id']
	}},
	'output_params': {'create_if_not_exists': True,
	'dataset_name': 'purchase_prob_demo',
	'drop_if_exists': True,
	'table_name': 'CLUSTERING_EXPERTS_PROB'}}"
"""

```

## Warehouse ##
```
python -m vskit.scripts.warehouse --config=<config> run

"""
sample config:
	config = "{'input_data':{'feature_lookup':
        {
          'dataset_name': 'warehouse_utility_dev',
          'source_type': 'bq',
          'table_name': 'feature_lookup',
          'private_key': '/home/vantena/google/testing_dev.json',
        },'level_lookup':{
          'dataset_name': 'warehouse_utility_dev',
          'source_type': 'bq',
          'table_name': 'level_lookup',
          'private_key': '/home/vantena/google/testing_dev.json',
        }},
     	'input_database_name':'warehouse_utility_dev',
	    'env_private_key':'/home/vantena/google/testing_dev.json',
	    'output_params': {'create_if_not_exists': True,
	    'dataset_name': 'warehouse_utility_dev',
	    'drop_if_exists': True,
	    'private_key': '/home/vantena/google/testing_dev.json',
	    'table_name': 'warehouse_output'}}""
"""

```
