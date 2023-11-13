# DS-json-parsing

I am D.Harshita, junior at VIT-AP University
I designed this repository to streamline the machine learning process based on a JSON configuration, . The code is flexible, allowing parsing of any JSON file following a specific format. This workflow covers feature handling, feature generation, model building using Grid Search, and hyperparameter tuning.

JSON Configuration
1. Target Specification
json
Copy code
"target": {
  "prediction_type": "Regression",
  "target": "petal_width",
  "type": "regression",
  "partitioning": true
}
I specifed the target variable, prediction type, and regression type.

2. Feature Handling
json
Copy code
"feature_handling": {
  "sepal_length": {
    "feature_name": "sepal_length",
    "is_selected": true,
    "feature_variable_type": "numerical",
    "feature_details": {
      "numerical_handling": "Keep as regular numerical feature",
      "rescaling": "No rescaling",
      "make_derived_feats": false,
      "missing_values": "Impute",
      "impute_with": "Average of values",
      "impute_value": 0
    }
  }
}
I handled features by specifying various parameters such as numerical handling, rescaling, and missing value imputation.

3. Feature Reduction
json
Copy code
"feature_reduction": {
  "feature_reduction_method": "Correlation with target",
  "No Reduction": {},
  "is_selected": true,
  "num_of_features_to_keep": 5,
  "Correlation with target": {},
  "is_selected": false,
  "num_of_features_to_keep": 0,
  "Tree-based": {},
  "is_selected": false,
  "num_of_features_to_keep": 0,
  "depth_of_trees": 0,
  "num_of_trees": 0,
  "Principal Component Analysis": {},
  "is_selected": false,
  "num_of_features_to_keep": 0
}
I reduced features based on methods like correlation with the target, tree-based, or Principal Component Analysis (PCA).

4. Model Creation
json
Copy code
"LogisticRegression": {
  "model_name": "Logistic Regression",
  "is_selected": false,
  "parallelism": 2,
  "min_iter": 30,
  "max_iter": 50,
  "min_regparam": 0.5,
  "max_regparam": 0.8,
  "min_elasticnet": 0.5,
  "max_elasticnet": 0.8
}
I specified the model to create, including its parameters like parallelism, iteration limits, and regularization parameters.

5. Hyperparameter Tuning
json
Copy code
"hyperparameters": {
  "search_method": "Grid Search",
  "Grid Search": {
    "is_selected": true,
    "shuffle_grid": true,
    "random_state": 0,
    "max_iterations": 0,
    "max_search_time": 0,
    "cross_validation_strategy": "Time-based K-fold (with overlap)",
    "Time-based K-fold (with overlap)": {
      "is_selected": true,
      "num_of_folds": 0,
      "split_ratio": 0,
      "stratified": false
    }
  }
}
I performed hyperparameter tuning using Grid Search, including options for shuffling the grid and time-based K-fold cross-validation, for all the algorithms provided in json file.

Execution
Parse JSON: The code parses the provided JSON to understand the target, features, feature handling, reduction, model creation, and hyperparameter tuning details.

Feature Handling and Reduction: Utilizing scikit-learn pipelines, I handled features based on the specified parameters and reduce features using the chosen method.

Model Training and Hyperparameter Tuning: I instantiated the selected model and perform hyperparameter tuning using Grid Search.

Console Logging: Standard model metrics are logged to the console, providing insights into the model's performance.
