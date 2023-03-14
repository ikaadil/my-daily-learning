Today I learnt how parquet actually works. 

In traditional file format data are orgnanized in row format or column format.


lets say the file looks like this
| a1 | b1  | c1  |
| ------- | --- | --- |
| a2 | b2 | c2 | 
| a3 | b3 | c3 |   
| a4 | b4 | c4 |    

# row-wise format
| a1 | b1  | c1  |  a2 | b2 | c2  |
| ------- | --- | --- |  ------- | --- | --- |
| a3 | b3  | c3  |  a4 | b4 | c4  |

# columnar format

| a1 | a2  | a3  |  a4 | b1 | b2  |
| ------- | --- | --- |  ------- | --- | --- |
| b3 | b4  | c1  |  c2 | c3 | c4  |

# hybrid format

| a1 | a2  | b1  |  b2 | c1 | c2 |
| ------- | --- | --- |  ------- | --- | --- |
| a3 | a4  | b3  |  b4 | c3| c4  |



                                

But in parquet data are organized in both row and file format.

Let’s say a file contains 100 lines. So it will divide the file into 10 row groups and each of which group contains 10 rows. The groups keep the rows in column format and each group contains meta information like min, max, count. For a targeted query it does not require to see the whole data of a group.


