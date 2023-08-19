# Olympic_data_analytics

This project is done by using the Azure. Azure is one of the major data anlytics platform

Main Azure functions can be used here.

1) Data Factory      -  This is used to create, schedule and manage data pipelines for efficient data 
                        movement.   In this project the data factory is olympic_tokyo_tf  and pipeline is data-ingestion. Here data factory copy and uploads data to containers to the source and creates a pipeline. After that the                                    transformend data will be uploaded to the database.
                        ![image](https://github.com/priyanthan07/Olympic_data_analytics/assets/129021635/dba8d39d-bb1f-4869-918c-32efd54ad0fd)

                       

   
2) Data lake Gen 2   -  This used to store analyse large volumes of structured and unstructured data with enhanced performance, security and analytics capabilities. 
3) Azure Databricks  -  This the analytics platform build on top of apache spark. first of all the source need to be configured
                         => athletes = spark.read.format("csv").option("header","true").option("inferSchema","true").load("/mnt/olympic-tokyo/raw-data/athletes.csv")
                            # option("inferSchema","true") ===> spark has this facility to go to the csv and understand the schema
                         => athletes.show()  - will show all table
                         => athletes.printSchema() - will print the columns and datatypes.
                         => EntriesGender = EntriesGender.withColumn("Female", col("Female").cast(IntegerType())).withColumn("Male", col("Male").cast(IntegerType())).withColumn("Total", col("Total").cast(IntegerType()))
                            #  this code converts the datatype of the columns.
                         Likewise all the data transformed and uploaded to new folder called transformed data.
                          
6) Synapse Analytics -  This provides all the services showed in above.  All the storage, pipeline construction and analytics work can be done here.
8) Key vault         -  This properly access & secure keys. 
