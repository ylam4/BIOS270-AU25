While the job is running, answer the following questions:

Examine create_bacteria_db.sh, how many tables will be created in the database? 

- 3 tables will be made
  
In the insert_gff_table.py script you submitted, explain the logic of using try and except. Why is this necessary?
while try_num < max_retries:
    try_num += 1
    try:
        df.to_sql(gff_table_name, conn, if_exists="append", index=False)
        break
    except (pd.errors.DatabaseError, sqlite3.OperationalError) as e:
        if "database is locked" in str(e):
            logging.info(f"Database is locked, retrying {try_num}/{max_retries}")
            time.sleep(1)
        else:
            raise e

- try and except handles database locking errors
- necessary because a Slurm array job may try to write to bacteri.db at the same time 



ylam4@rice-02:~/repos/BIOS270-AU25/Data$ $RUN python query_bacteria_db.py --database_path bacteria.db

Total number of record ids:  4100
Processed 0 record ids in 7.199815273284912 seconds
Processed 10 record ids in 39.23487734794617 seconds
Processed 20 record ids in 71.35831952095032 seconds
Processed 30 record ids in 103.99629592895508 seconds
Processed 40 record ids in 137.9407000541687 seconds
Processed 50 record ids in 171.70500922203064 seconds
