# The pupose of this repo

When working in a large notebook, it is sometimes helpful to save intermediate results and load from a specific starting point.

The data is pulled from this repo as opposed to storing the data locally, as the free tier of Colab notebooks will eventually timeout and reset the container running the notebook, which will also delete any temp files.


## Example code for pulling from this repo
```
import os
temp_store_for_properties="https://raw.githubusercontent.com/dphiggs01/data_store/main/boston_prop_51_plus_scores.csv"

# Set this variable 'load_from_temp' to False if you want to load the data from the Notebook Proper
########################
load_from_temp = True
########################

if load_from_temp:
    print("Loading from temporary storage!!!\n Be sure that this is what you want.\n If not sure Set 'load_from_temp' = False and retry.")
    boston_prop_w_scores = pd.read_csv(temp_store_for_properties, dtype={'GIS_ID': 'str'})
else:
  try:
    boston_prop_w_scores = prop_assess_list_3[(prop_assess_list_3["TOTAL_SCORE"]>=52) & (prop_assess_list_3["TOTAL_SCORE"]<=100)]
  except:
    print("The full Notebook must be run to make this variable 'mprop_assess_list_3' accessible")
```