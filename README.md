# Pump-it-Up-Data-Mining-the-Water-Table-Competition
[Pump it Up: Data Mining the Water Table - Competition](https://www.drivendata.org/competitions/7/pump-it-up-data-mining-the-water-table)

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

# Experiments

### Preprocessing Techniques:

* Fix typo errors in the Dataset - `installer`
* Drop duplicated features - `source_class`, `source_type`, `management_group`, `scheme_management`, `quantity_group`, `quality_group`, `payment_type`, `extraction_type_class`, `extraction_type`, `waterpoint_type_group`, `region_code`
* Identify and fix the feature types.
* Handling missing Values 
  * Add a new Category or add to a existing category like 'Unknown'. - For categorical features.
  * Replace 0 which seems to be unknown by mean. - `longitude`, `population`.
  * Replace NaN values by most common value / median value. - `public_meeting`, `permit`
* Remove features with less details.
  * `wpt_name`, `scheme_name` - Lots of None values, & most of the labels in this feature have very low value count.
  * `amount_tsh` - Most of the data (70%) is 0.0. 
  * `date_recorded` - Most of the dates are beetween 2011-2013 & seems to be non-informative.
  * `num_private` - Most of the data (99%) is 0.
  * `sub_village` - Very low value count.
  * `recorded_by` - One unique value for all.
* Reduce feature's category counts - Only keep few categories & group other categories to Other, for the features having large number of categories - `installer`, `funder`
* Converting target values to ternary values. - `status_group`

### Feature Engineering Techniques:

* Check Mutual Information
* Binning to groups - `year`
* Clustering - `longitude`, `latitude`
* Principal Component Analysis - `gps_height`, `population`
* Target Encoding - `ward`

### Experimented Models:

* [Random Forest Classifier](https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestClassifier.html)
* [XGBoost Classifier](https://xgboost.readthedocs.io/en/latest/python/python_api.html)

### Submission
