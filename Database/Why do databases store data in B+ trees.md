
If we store our data in a file sequentially then for find, insert, update, and range query operation it requires O(n) time complexity. 

In B+ tree data are stored in leaves node, all the internal nodes keeps the range information. In the leaves node, there is a block of rows. Every block of different nodes are connected to each other, which makes the range query faster. For find, insert, update, and range operation it requires O(logn) time complexity.