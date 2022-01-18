A few notes and instructions:

- When chaining together the steps, the output artifact of a step should be the input artifact of the next one (when applicable). Also use the artifact_type options so that the final visualization of the pipeline highlights the different steps. For example, you can use raw_data for the artifact containing the downloaded data, preprocessed_data for the artifact containing the data after the preprocessing, and so on.

- For testing, set the project_name to exercise_14. Once you are done developing, do a production run by changing the project_name to genre_classification_prod. This way the visualization of the pipeline will not contain all your trials and errors. Remember to tag the produced model export as prod (we are going to use it in the next exercise)

- When developing, you can override the parameter main.execute_steps to only execute one or more steps of the pipeline, instead of the entire pipeline. This is useful for debugging. For example, this only executes the random_forest step:

`mlflow run . -P hydra_options="main.execute_steps='random_forest'"`
and this executes download and preprocess:

`mlflow run . -P hydra_options="main.execute_steps='download,preprocess'"`