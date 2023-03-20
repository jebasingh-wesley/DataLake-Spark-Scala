# DataLake_Spark_scala
Calling method to pull employees table data from mysql/any db under empoffice schema


 *Under staging retailstg Database create temporary managed tables, Load the DB imported data into the 
 * below managed table that will be dropped and recreated on daily basis so data will be cleaned when dropped, 
 * if we use external table we have to manage the data cleanup separately as given below using the 
 * truncate statement.
 
 
 *External tables with partition/bucketing usecases : Under retail_curated database create and 
 * load external tables which is partitioned for applying where clauses and bucketed to join with 
 * the other external tables more efficiently. Why we are creating as external table because we may 
 * keep on adding more data in this table or performing more iterative queries without dropping it 
 * as we have to join these tables to produce the final mart.
