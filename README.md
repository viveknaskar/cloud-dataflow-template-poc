# cloud-dataflow-template-poc

Code to create cloud Dataflow template in Java. This is worked upon Apache Beam's WordCount example. The pipeline will read data from a textfile which is stored in a GCS bucket and it will output the number of each words in another GCS bucket.

## Run the below maven command to run the example dataflow pipeline

```
 mvn archetype:generate \
     -DarchetypeArtifactId=google-cloud-dataflow-java-archetypes-examples \
     -DarchetypeGroupId=com.google.cloud.dataflow \
     -DarchetypeVersion=2.5.0 \
     -DgroupId=com.viveknaskar \
     -DartifactId=dataflow-template-poc \
     -Dversion="0.1" \
     -DinteractiveMode=false \
     -Dpackage=com.viveknaskar
 ```
    
 This generates some sample code, including the Dataflow standard WordCount. You can edit that code for creating a template.
 
 ## Run the below command to create the template
 
 ```
  mvn compile exec:java \
      -Dexec.mainClass=com.viveknaskar.WordCount \
      -Dexec.args="--project=<your-project-id> \
      --stagingLocation=gs://dataflow-pipeline-staging/staging \
      --dataflowJobFile=gs://dataflow-pipeline-staging/templates/dataflow-template \
      --gcpTempLocation=gs://dataflow-pipeline-staging/tmp \
      --output=gs://dataflow-pipelines-output \
      --runner=DataflowRunner"
  ```
    
  Before running the above maven command, you'll need some GCS buckets in your GCP account.
  
