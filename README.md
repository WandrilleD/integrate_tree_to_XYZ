A python script to integrate a tree structure among a set of points.

requirements: 
 - [ete3](http://etetoolkit.org/download/)
 - [pandas](https://pandas.pydata.org/)

basic usage: 
`python integrate_tree_to_XYZ.py -i mammal_groups.xy.csv -t mammal_groups.ncbi_taxonomy.timetree.nwk -o test`

which should create 3 files:
 - test.leaves.csv
 - test.internal.csv
 - test.branches.csv

Containing coordinates for the leaves (ie. the points in the coordinate file), the internal nodes of the tree, and the branches of the tree


upscale the z-axis:
`python integrate_tree_to_XYZ.py -i mammal_groups.xy.csv -t mammal_groups.ncbi_taxonomy.timetree.nwk -o test2 --z-scale 3`


ignore the tree heights and use the Z-axis found in the coordinate file:
`python integrate_tree_to_XYZ.py -i mammal_groups.xyz.csv -t mammal_groups.ncbi_taxonomy.timetree.nwk -o test3 --use-z-from-file `

play with drag of internal node toward their parents.
no drag:
`python integrate_tree_to_XYZ.py -i mammal_groups.xyz.csv -t mammal_groups.ncbi_taxonomy.timetree.nwk -o test4 --use-z-from-file --drag 0`

more drag:
`python integrate_tree_to_XYZ.py -i mammal_groups.xyz.csv -t mammal_groups.ncbi_taxonomy.timetree.nwk -o test5 --use-z-from-file --drag 0.8`

using a spherical layout instead of the z-axis for the tree:
`python integrate_tree_to_XYZ.py -i mammal_groups.xy.csv -t mammal_groups.ncbi_taxonomy.timetree.nwk -o test6 --spherical-layout`


The `quick_3D_tree_viz` ipython notebook uses plotly can be used to quickly check out the results and also to get an idea about how the output files should be used.


