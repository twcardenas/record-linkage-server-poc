# record-linkage-server-poc
A journey to learn about building a record linkage model, cleaning the data, putting that data into a classification and serving that data on AWS

# Questions I'm asking myself

## What is Record Linkage?
Where there is a dataset like below, there can be duplicates. And manually finding duplicates can be time consuming. The address could be spelled different. A person could have multiple addresses. Birthdate might be the same, might've changed name etc. Record Linkage is a way to identify if any two records in a dataset are the same entity. This is pretty easy to do when there are unique identifers.
```
               given_name    surname street_number              address_1                        address_2              suburb postcode state date_of_birth
rec_id
rec-2778-org        sarah      bruhn            44          forbes street                       wintersloe        kellerberrin     4510   vic      19300213  
rec-712-dup-0       jacob     lanyon             5             milne cove                          wellwod  beaconsfield upper     2602   vic      19080712   
rec-1321-org      brinley  efthimiou            35       sturdee crescent                        tremearne         scarborough     5211   qld      19940319  
rec-3004-org      aleisha     hobson            54          oliver street                        inglewood           toowoomba     3175   qld      19290427   
rec-1384-org        ethan    gazzola            49         sheaffe street                       bimby vale          port pirie     3088    sa      19631225 
```

## Saving record linkage compares and how to update?

## What does this process look like on the Cloud?

Figuring this out....

## How do we save our model after training it?

We can use pickle to save our model like so

```
import pickle
file_name = "xgb_reg.pkl"
# save
pickle.dump(model, open(file_name, "wb"))
# load
xgb_model_loaded = pickle.load(open(file_name, "rb"))
```

# Steps

### Resources
* https://towardsdatascience.com/performing-deduplication-with-record-linkage-and-supervised-learning-b01a66cc6882
* https://medium.com/@louis_amon/how-to-build-a-machine-learning-powered-record-linkage-workflow-b1890a0eb4ae
