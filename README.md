# BigData-handson

cat birdstrikes.csv | cut -d , -f 6 | head | sort
cat birdstrikes.csv | head -n 2 | cut -d , - f 1,2,3  -- more column
 
cat birdstrikes.csv | sort -n -r -t , -k 10| head  -- sort by one column

HDFS is just a filestore method( with Name node and many Data nodes
YARN: works with like HDFS , Resource Manager, and Node managers, U install the RM on Name node
this is the usual setup
to begin a hadoop cluster:
start-all.sh
and also start: 
start-historyserver.sh
for stabli workaround

list root directoy on HDFS (within hadoop)
hadoop fs -ls /
def. directories: tmp for internal operations
user/xxxx  the given user name (xxxx) of the computer user

the distributed filesyst:
hadoop dfsadmin -report

missing block> serious problem
underrepl. > unsuccessful replicatied blocks

copy from HDFS to local>
hadoop fs -get /user/bigdata/birdstrikes.csv b.csv
in HDFS there is no header!!!! because of distr.splitting
for this reason U will never see big zip files
LZO - each block replicates the compressed data header info

hadoop fs -put b.csv /user/bigdata

basically puts into user dir, but U can put in a new dir, but U cannot overwrite

hadoop fs 
-cp (copy)
-mv (move)
-rm -r -skippTrash birddir  (trash configuration - skipp)



