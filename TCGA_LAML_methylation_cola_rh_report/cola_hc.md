cola Report for Hierarchical Partitioning - 'TCGA_LAML_methylation'
==================

**Date**: 2021-07-22 16:45:57 CEST, **cola version**: 1.9.4

----------------------------------------------------------------

<style type='text/css'>

body, td, th {
   font-family: Arial,Helvetica,sans-serif;
   background-color: white;
   font-size: 13px;
  max-width: 800px;
  margin: auto;
  margin-left:210px;
  padding: 0px 10px 0px 10px;
  border-left: 1px solid #EEEEEE;
  line-height: 150%;
}

tt, code, pre {
   font-family: 'DejaVu Sans Mono', 'Droid Sans Mono', 'Lucida Console', Consolas, Monaco, 

monospace;
}

h1 {
   font-size:2.2em;
}

h2 {
   font-size:1.8em;
}

h3 {
   font-size:1.4em;
}

h4 {
   font-size:1.0em;
}

h5 {
   font-size:0.9em;
}

h6 {
   font-size:0.8em;
}

a {
  text-decoration: none;
  color: #0366d6;
}

a:hover {
  text-decoration: underline;
}

a:visited {
   color: #0366d6;
}

pre, img {
  max-width: 100%;
}
pre {
  overflow-x: auto;
}
pre code {
   display: block; padding: 0.5em;
}

code {
  font-size: 92%;
  border: 1px solid #ccc;
}

code[class] {
  background-color: #F8F8F8;
}

table, td, th {
  border: 1px solid #ccc;
}

blockquote {
   color:#666666;
   margin:0;
   padding-left: 1em;
   border-left: 0.5em #EEE solid;
}

hr {
   height: 0px;
   border-bottom: none;
   border-top-width: thin;
   border-top-style: dotted;
   border-top-color: #999999;
}

@media print {
   * {
      background: transparent !important;
      color: black !important;
      filter:none !important;
      -ms-filter: none !important;
   }

   body {
      font-size:12pt;
      max-width:100%;
   }

   a, a:visited {
      text-decoration: underline;
   }

   hr {
      visibility: hidden;
      page-break-before: always;
   }

   pre, blockquote {
      padding-right: 1em;
      page-break-inside: avoid;
   }

   tr, img {
      page-break-inside: avoid;
   }

   img {
      max-width: 100% !important;
   }

   @page :left {
      margin: 15mm 20mm 15mm 10mm;
   }

   @page :right {
      margin: 15mm 10mm 15mm 20mm;
   }

   p, h2, h3 {
      orphans: 3; widows: 3;
   }

   h2, h3 {
      page-break-after: avoid;
   }
}
</style>




## Summary



First the variable is renamed to `res_rh`.


```r
res_rh = rh
```



The partition hierarchy and all available functions which can be applied to `res_rh` object.


```r
res_rh
```

```
#> A 'HierarchicalPartition' object with 4 combinations of top-value methods and partitioning methods.
#>   On a matrix with 375965 rows and 194 columns.
#>   Performed in total 54600 partitions.
#>   There are 26 groups under the following parameters:
#>     - min_samples: 6
#>     - mean_silhouette_cutoff: 0.9
#>     - min_n_signatures: 1000 (signatures are selected based on:)
#>       - fdr_cutoff: 0.05
#>       - group_diff: 0.25
#> 
#> Hierarchy of the partition:
#>   0, 194 cols
#>   |-- 01, 51 cols, 25188 signatures
#>   |   |-- 011, 14 cols, 3533 signatures
#>   |   |   |-- 0111, 8 cols (b)
#>   |   |   `-- 0112, 6 cols (b)
#>   |   |-- 012, 9 cols (b)
#>   |   |-- 013, 12 cols, 2818 signatures
#>   |   |   |-- 0131, 4 cols (b)
#>   |   |   `-- 0132, 8 cols (b)
#>   |   `-- 014, 16 cols, 3565 signatures
#>   |       |-- 0141, 9 cols (b)
#>   |       `-- 0142, 7 cols (b)
#>   |-- 02, 93 cols, 19218 signatures
#>   |   |-- 021, 26 cols, 10868 signatures
#>   |   |   |-- 0211, 9 cols (b)
#>   |   |   |-- 0212, 9 cols (b)
#>   |   |   `-- 0213, 8 cols (b)
#>   |   |-- 022, 31 cols, 4786 signatures
#>   |   |   |-- 0221, 14 cols, 358 signatures (c)
#>   |   |   `-- 0222, 17 cols, 2995 signatures
#>   |   |       |-- 02221, 10 cols (b)
#>   |   |       |-- 02222, 4 cols (b)
#>   |   |       `-- 02223, 3 cols (b)
#>   |   `-- 023, 36 cols, 22248 signatures
#>   |       |-- 0231, 18 cols, 521 signatures (c)
#>   |       |-- 0232, 4 cols (b)
#>   |       `-- 0233, 14 cols, 90 signatures (c)
#>   `-- 03, 50 cols, 32510 signatures
#>       |-- 031, 12 cols, 426 signatures (c)
#>       |-- 032, 18 cols, 5739 signatures
#>       |   |-- 0321, 6 cols (b)
#>       |   |-- 0322, 3 cols (b)
#>       |   |-- 0323, 3 cols (b)
#>       |   |-- 0324, 4 cols (b)
#>       |   `-- 0325, 2 cols (b)
#>       |-- 033, 12 cols, 3376 signatures
#>       |   |-- 0331, 6 cols (b)
#>       |   `-- 0332, 6 cols (b)
#>       `-- 034, 8 cols (b)
#> Stop reason:
#>   b) Subgroup had too few columns.
#>   c) There were too few signatures.
#> 
#> Following methods can be applied to this 'HierarchicalPartition' object:
#>  [1] "all_leaves"            "all_nodes"             "cola_report"           "collect_classes"      
#>  [5] "colnames"              "compare_signatures"    "dimension_reduction"   "functional_enrichment"
#>  [9] "get_anno_col"          "get_anno"              "get_children_nodes"    "get_classes"          
#> [13] "get_matrix"            "get_signatures"        "is_leaf_node"          "max_depth"            
#> [17] "merge_node"            "ncol"                  "node_info"             "node_level"           
#> [21] "nrow"                  "rownames"              "show"                  "split_node"           
#> [25] "suggest_best_k"        "test_to_known_factors" "top_rows_heatmap"      "top_rows_overlap"     
#> 
#> You can get result for a single node by e.g. object["01"]
```

The call of `hierarchical_partition()` was:


```
#> hierarchical_partition(data = mat, top_n = 1000, top_value_method = c("SD", "ATC"), 
#>     partition_method = c("kmeans", "skmeans"), subset = 500, group_diff = 0.25, min_n_signatures = 1000, 
#>     filter_fun = function(mat) {
#>         s = rowSds(mat)
#>         order(-s)[1:30000]
#>     }, max_k = 8, scale_rows = FALSE, cores = 4)
```

Dimension of the input matrix:


```r
mat = get_matrix(res_rh)
dim(mat)
```

```
#> [1] 375965    194
```

All the methods that were tried:


```r
res_rh@param$combination_method
```

```
#> [[1]]
#> [1] "SD"     "kmeans"
#> 
#> [[2]]
#> [1] "ATC"    "kmeans"
#> 
#> [[3]]
#> [1] "SD"      "skmeans"
#> 
#> [[4]]
#> [1] "ATC"     "skmeans"
```

### Density distribution

The density distribution for each sample is visualized as one column in the following heatmap.
The clustering is based on the distance which is the Kolmogorov-Smirnov statistic between two distributions.




```r
library(ComplexHeatmap)
densityHeatmap(mat, ylab = "value", cluster_columns = TRUE, show_column_names = FALSE,
    mc.cores = 1)
```

![plot of chunk density-heatmap](figure_cola/density-heatmap-1.png)



Some values about the hierarchy:


```r
all_nodes(res_rh)
```

```
#>  [1] "0"     "01"    "011"   "0111"  "0112"  "012"   "013"   "0131"  "0132"  "014"   "0141"  "0142" 
#> [13] "02"    "021"   "0211"  "0212"  "0213"  "022"   "0221"  "0222"  "02221" "02222" "02223" "023"  
#> [25] "0231"  "0232"  "0233"  "03"    "031"   "032"   "0321"  "0322"  "0323"  "0324"  "0325"  "033"  
#> [37] "0331"  "0332"  "034"
```

```r
all_leaves(res_rh)
```

```
#>  [1] "0111"  "0112"  "012"   "0131"  "0132"  "0141"  "0142"  "0211"  "0212"  "0213"  "0221"  "02221"
#> [13] "02222" "02223" "0231"  "0232"  "0233"  "031"   "0321"  "0322"  "0323"  "0324"  "0325"  "0331" 
#> [25] "0332"  "034"
```

```r
node_info(res_rh)
```

```
#>       id best_method depth best_k n_columns n_signatures p_signatures is_leaf
#> 1      0  SD:skmeans     1      3       194         8194     0.021795   FALSE
#> 2     01  ATC:kmeans     2      4        51        25188     0.066996   FALSE
#> 3    011  ATC:kmeans     3      2        14         3533     0.009397   FALSE
#> 4   0111 not applied     4     NA         8           NA           NA    TRUE
#> 5   0112 not applied     4     NA         6           NA           NA    TRUE
#> 6    012 not applied     3     NA         9           NA           NA    TRUE
#> 7    013 ATC:skmeans     3      2        12         2818     0.007495   FALSE
#> 8   0131 not applied     4     NA         4           NA           NA    TRUE
#> 9   0132 not applied     4     NA         8           NA           NA    TRUE
#> 10   014  ATC:kmeans     3      2        16         3565     0.009482   FALSE
#> 11  0141 not applied     4     NA         9           NA           NA    TRUE
#> 12  0142 not applied     4     NA         7           NA           NA    TRUE
#> 13    02  SD:skmeans     2      3        93        19218     0.051116   FALSE
#> 14   021  ATC:kmeans     3      3        26        10868     0.028907   FALSE
#> 15  0211 not applied     4     NA         9           NA           NA    TRUE
#> 16  0212 not applied     4     NA         9           NA           NA    TRUE
#> 17  0213 not applied     4     NA         8           NA           NA    TRUE
#> 18   022  ATC:kmeans     3      2        31         4786     0.012730   FALSE
#> 19  0221  ATC:kmeans     4      2        14          358     0.000952    TRUE
#> 20  0222  ATC:kmeans     4      3        17         2995     0.007966   FALSE
#> 21 02221 not applied     5     NA        10           NA           NA    TRUE
#> 22 02222 not applied     5     NA         4           NA           NA    TRUE
#> 23 02223 not applied     5     NA         3           NA           NA    TRUE
#> 24   023  ATC:kmeans     3      3        36        22248     0.059176   FALSE
#> 25  0231  ATC:kmeans     4      2        18          521     0.001386    TRUE
#> 26  0232 not applied     4     NA         4           NA           NA    TRUE
#> 27  0233 ATC:skmeans     4      3        14           90     0.000239    TRUE
#> 28    03   SD:kmeans     2      4        50        32510     0.086471   FALSE
#> 29   031  ATC:kmeans     3      2        12          426     0.001133    TRUE
#> 30   032 ATC:skmeans     3      5        18         5739     0.015265   FALSE
#> 31  0321 not applied     4     NA         6           NA           NA    TRUE
#> 32  0322 not applied     4     NA         3           NA           NA    TRUE
#> 33  0323 not applied     4     NA         3           NA           NA    TRUE
#> 34  0324 not applied     4     NA         4           NA           NA    TRUE
#> 35  0325 not applied     4     NA         2           NA           NA    TRUE
#> 36   033  ATC:kmeans     3      2        12         3376     0.008980   FALSE
#> 37  0331 not applied     4     NA         6           NA           NA    TRUE
#> 38  0332 not applied     4     NA         6           NA           NA    TRUE
#> 39   034 not applied     3     NA         8           NA           NA    TRUE
```

In the output from `node_info()`, there are the following columns:

- `id`: The node id.
- `best_method`: The best method selected.
- `depth`: Depth of the node in the hierarchy.
- `best_k`: Best number of groups of the partition on that node.
- `n_columns`: Number of columns in the submatrix.
- `n_signatures`: Number of signatures with the `best_k`.
- `p_signatures`: Proportion of hte signatures in total number of rows in the matrix.
- `is_leaf`: Whether the node is a leaf.

Labels of nodes are encoded in a special way. The number of digits
correspond to the depth of the node in the hierarchy and the value of the
digits correspond to the index of the subgroup in the current node, E.g. a label
of “012” means the node is the second subgroup of the partition which is the
first subgroup of the root node.

### Suggest the best k



Following table shows the best `k` (number of partitions) for each node in the
partition hierarchy. Clicking on the node name in the table goes to the
corresponding section for the partitioning on that node.

[The cola vignette](https://jokergoo.github.io/cola_vignettes/cola.html#toc_13)
explains the definition of the metrics used for determining the best
number of partitions.



```r
suggest_best_k(res_rh)
```


|Node                  |Best method                                         |Is leaf   |Best k |1-PAC |Mean silhouette |Concordance | #samples|   |
|:---------------------|:---------------------------------------------------|:---------|:------|:-----|:---------------|:-----------|--------:|:--|
|[Node0](#Node0)       |SD:skmeans                                          |          |3      |1.00  |1.00            |1.00        |      194|** |
|[Node01](#Node01)     |ATC:kmeans                                          |          |4      |1.00  |0.99            |0.99        |       51|** |
|[Node011](#Node011)   |ATC:kmeans                                          |          |2      |1.00  |1.00            |1.00        |       14|** |
|Node0111-leaf         |<span style='color:grey;'><i>not applied</i></span> |✓ (b)     |       |      |                |            |        8|   |
|Node0112-leaf         |<span style='color:grey;'><i>not applied</i></span> |✓ (b)     |       |      |                |            |        6|   |
|Node012-leaf          |<span style='color:grey;'><i>not applied</i></span> |✓ (b)     |       |      |                |            |        9|   |
|[Node013](#Node013)   |ATC:skmeans                                         |          |3      |1.00  |0.91            |1.00        |       12|** |
|Node0131-leaf         |<span style='color:grey;'><i>not applied</i></span> |✓ (b)     |       |      |                |            |        4|   |
|Node0132-leaf         |<span style='color:grey;'><i>not applied</i></span> |✓ (b)     |       |      |                |            |        8|   |
|[Node014](#Node014)   |ATC:kmeans                                          |          |2      |1.00  |1.00            |1.00        |       16|** |
|Node0141-leaf         |<span style='color:grey;'><i>not applied</i></span> |✓ (b)     |       |      |                |            |        9|   |
|Node0142-leaf         |<span style='color:grey;'><i>not applied</i></span> |✓ (b)     |       |      |                |            |        7|   |
|[Node02](#Node02)     |SD:skmeans                                          |          |4      |1.00  |0.95            |0.98        |       93|** |
|[Node021](#Node021)   |ATC:kmeans                                          |          |3      |1.00  |0.98            |0.98        |       26|** |
|Node0211-leaf         |<span style='color:grey;'><i>not applied</i></span> |✓ (b)     |       |      |                |            |        9|   |
|Node0212-leaf         |<span style='color:grey;'><i>not applied</i></span> |✓ (b)     |       |      |                |            |        9|   |
|Node0213-leaf         |<span style='color:grey;'><i>not applied</i></span> |✓ (b)     |       |      |                |            |        8|   |
|[Node022](#Node022)   |ATC:kmeans                                          |          |2      |1.00  |1.00            |1.00        |       31|** |
|Node0221-leaf         |ATC:kmeans                                          |✓ (&#99;) |8      |0.92  |0.53            |0.96        |       14|*  |
|[Node0222](#Node0222) |ATC:kmeans                                          |          |3      |1.00  |1.00            |1.00        |       17|** |
|Node02221-leaf        |<span style='color:grey;'><i>not applied</i></span> |✓ (b)     |       |      |                |            |       10|   |
|Node02222-leaf        |<span style='color:grey;'><i>not applied</i></span> |✓ (b)     |       |      |                |            |        4|   |
|Node02223-leaf        |<span style='color:grey;'><i>not applied</i></span> |✓ (b)     |       |      |                |            |        3|   |
|[Node023](#Node023)   |ATC:kmeans                                          |          |3      |1.00  |0.97            |0.99        |       36|** |
|Node0231-leaf         |ATC:kmeans                                          |✓ (&#99;) |2      |1.00  |1.00            |1.00        |       18|** |
|Node0232-leaf         |<span style='color:grey;'><i>not applied</i></span> |✓ (b)     |       |      |                |            |        4|   |
|Node0233-leaf         |ATC:skmeans                                         |✓ (&#99;) |8      |0.95  |0.64            |0.95        |       14|*  |
|[Node03](#Node03)     |SD:kmeans                                           |          |3      |1.00  |0.99            |0.99        |       50|** |
|Node031-leaf          |ATC:kmeans                                          |✓ (&#99;) |3      |1.00  |0.92            |1.00        |       12|** |
|[Node032](#Node032)   |ATC:skmeans                                         |          |5      |0.99  |0.98            |0.99        |       18|** |
|Node0321-leaf         |<span style='color:grey;'><i>not applied</i></span> |✓ (b)     |       |      |                |            |        6|   |
|Node0322-leaf         |<span style='color:grey;'><i>not applied</i></span> |✓ (b)     |       |      |                |            |        3|   |
|Node0323-leaf         |<span style='color:grey;'><i>not applied</i></span> |✓ (b)     |       |      |                |            |        3|   |
|Node0324-leaf         |<span style='color:grey;'><i>not applied</i></span> |✓ (b)     |       |      |                |            |        4|   |
|Node0325-leaf         |<span style='color:grey;'><i>not applied</i></span> |✓ (b)     |       |      |                |            |        2|   |
|[Node033](#Node033)   |ATC:kmeans                                          |          |2      |1.00  |1.00            |1.00        |       12|** |
|Node0331-leaf         |<span style='color:grey;'><i>not applied</i></span> |✓ (b)     |       |      |                |            |        6|   |
|Node0332-leaf         |<span style='color:grey;'><i>not applied</i></span> |✓ (b)     |       |      |                |            |        6|   |
|Node034-leaf          |<span style='color:grey;'><i>not applied</i></span> |✓ (b)     |       |      |                |            |        8|   |


Stop reason: b) Subgroup had too few columns. c) There were too few signatures. 

\*\*: 1-PAC > 0.95, \*: 1-PAC > 0.9


### Partition hierarchy

The nodes of the hierarchy can be merged by setting the `merge_node` parameters. Here we 
control the hierarchy with the `min_n_signatures` parameter. The value of `min_n_signatures` is
from `node_info()`.





<style type='text/css'>



.ui-helper-hidden {
	display: none;
}
.ui-helper-hidden-accessible {
	border: 0;
	clip: rect(0 0 0 0);
	height: 1px;
	margin: -1px;
	overflow: hidden;
	padding: 0;
	position: absolute;
	width: 1px;
}
.ui-helper-reset {
	margin: 0;
	padding: 0;
	border: 0;
	outline: 0;
	line-height: 1.3;
	text-decoration: none;
	font-size: 100%;
	list-style: none;
}
.ui-helper-clearfix:before,
.ui-helper-clearfix:after {
	content: "";
	display: table;
	border-collapse: collapse;
}
.ui-helper-clearfix:after {
	clear: both;
}
.ui-helper-zfix {
	width: 100%;
	height: 100%;
	top: 0;
	left: 0;
	position: absolute;
	opacity: 0;
	filter:Alpha(Opacity=0); 
}

.ui-front {
	z-index: 100;
}



.ui-state-disabled {
	cursor: default !important;
	pointer-events: none;
}



.ui-icon {
	display: inline-block;
	vertical-align: middle;
	margin-top: -.25em;
	position: relative;
	text-indent: -99999px;
	overflow: hidden;
	background-repeat: no-repeat;
}

.ui-widget-icon-block {
	left: 50%;
	margin-left: -8px;
	display: block;
}




.ui-widget-overlay {
	position: fixed;
	top: 0;
	left: 0;
	width: 100%;
	height: 100%;
}
.ui-accordion .ui-accordion-header {
	display: block;
	cursor: pointer;
	position: relative;
	margin: 2px 0 0 0;
	padding: .5em .5em .5em .7em;
	font-size: 100%;
}
.ui-accordion .ui-accordion-content {
	padding: 1em 2.2em;
	border-top: 0;
	overflow: auto;
}
.ui-autocomplete {
	position: absolute;
	top: 0;
	left: 0;
	cursor: default;
}
.ui-menu {
	list-style: none;
	padding: 0;
	margin: 0;
	display: block;
	outline: 0;
}
.ui-menu .ui-menu {
	position: absolute;
}
.ui-menu .ui-menu-item {
	margin: 0;
	cursor: pointer;
	
	list-style-image: url("data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7");
}
.ui-menu .ui-menu-item-wrapper {
	position: relative;
	padding: 3px 1em 3px .4em;
}
.ui-menu .ui-menu-divider {
	margin: 5px 0;
	height: 0;
	font-size: 0;
	line-height: 0;
	border-width: 1px 0 0 0;
}
.ui-menu .ui-state-focus,
.ui-menu .ui-state-active {
	margin: -1px;
}


.ui-menu-icons {
	position: relative;
}
.ui-menu-icons .ui-menu-item-wrapper {
	padding-left: 2em;
}


.ui-menu .ui-icon {
	position: absolute;
	top: 0;
	bottom: 0;
	left: .2em;
	margin: auto 0;
}


.ui-menu .ui-menu-icon {
	left: auto;
	right: 0;
}
.ui-button {
	padding: .4em 1em;
	display: inline-block;
	position: relative;
	line-height: normal;
	margin-right: .1em;
	cursor: pointer;
	vertical-align: middle;
	text-align: center;
	-webkit-user-select: none;
	-moz-user-select: none;
	-ms-user-select: none;
	user-select: none;

	
	overflow: visible;
}

.ui-button,
.ui-button:link,
.ui-button:visited,
.ui-button:hover,
.ui-button:active {
	text-decoration: none;
}


.ui-button-icon-only {
	width: 2em;
	box-sizing: border-box;
	text-indent: -9999px;
	white-space: nowrap;
}


input.ui-button.ui-button-icon-only {
	text-indent: 0;
}


.ui-button-icon-only .ui-icon {
	position: absolute;
	top: 50%;
	left: 50%;
	margin-top: -8px;
	margin-left: -8px;
}

.ui-button.ui-icon-notext .ui-icon {
	padding: 0;
	width: 2.1em;
	height: 2.1em;
	text-indent: -9999px;
	white-space: nowrap;

}

input.ui-button.ui-icon-notext .ui-icon {
	width: auto;
	height: auto;
	text-indent: 0;
	white-space: normal;
	padding: .4em 1em;
}



input.ui-button::-moz-focus-inner,
button.ui-button::-moz-focus-inner {
	border: 0;
	padding: 0;
}
.ui-controlgroup {
	vertical-align: middle;
	display: inline-block;
}
.ui-controlgroup > .ui-controlgroup-item {
	float: left;
	margin-left: 0;
	margin-right: 0;
}
.ui-controlgroup > .ui-controlgroup-item:focus,
.ui-controlgroup > .ui-controlgroup-item.ui-visual-focus {
	z-index: 9999;
}
.ui-controlgroup-vertical > .ui-controlgroup-item {
	display: block;
	float: none;
	width: 100%;
	margin-top: 0;
	margin-bottom: 0;
	text-align: left;
}
.ui-controlgroup-vertical .ui-controlgroup-item {
	box-sizing: border-box;
}
.ui-controlgroup .ui-controlgroup-label {
	padding: .4em 1em;
}
.ui-controlgroup .ui-controlgroup-label span {
	font-size: 80%;
}
.ui-controlgroup-horizontal .ui-controlgroup-label + .ui-controlgroup-item {
	border-left: none;
}
.ui-controlgroup-vertical .ui-controlgroup-label + .ui-controlgroup-item {
	border-top: none;
}
.ui-controlgroup-horizontal .ui-controlgroup-label.ui-widget-content {
	border-right: none;
}
.ui-controlgroup-vertical .ui-controlgroup-label.ui-widget-content {
	border-bottom: none;
}


.ui-controlgroup-vertical .ui-spinner-input {

	
	width: 75%;
	width: calc( 100% - 2.4em );
}
.ui-controlgroup-vertical .ui-spinner .ui-spinner-up {
	border-top-style: solid;
}

.ui-checkboxradio-label .ui-icon-background {
	box-shadow: inset 1px 1px 1px #ccc;
	border-radius: .12em;
	border: none;
}
.ui-checkboxradio-radio-label .ui-icon-background {
	width: 16px;
	height: 16px;
	border-radius: 1em;
	overflow: visible;
	border: none;
}
.ui-checkboxradio-radio-label.ui-checkboxradio-checked .ui-icon,
.ui-checkboxradio-radio-label.ui-checkboxradio-checked:hover .ui-icon {
	background-image: none;
	width: 8px;
	height: 8px;
	border-width: 4px;
	border-style: solid;
}
.ui-checkboxradio-disabled {
	pointer-events: none;
}
.ui-datepicker {
	width: 17em;
	padding: .2em .2em 0;
	display: none;
}
.ui-datepicker .ui-datepicker-header {
	position: relative;
	padding: .2em 0;
}
.ui-datepicker .ui-datepicker-prev,
.ui-datepicker .ui-datepicker-next {
	position: absolute;
	top: 2px;
	width: 1.8em;
	height: 1.8em;
}
.ui-datepicker .ui-datepicker-prev-hover,
.ui-datepicker .ui-datepicker-next-hover {
	top: 1px;
}
.ui-datepicker .ui-datepicker-prev {
	left: 2px;
}
.ui-datepicker .ui-datepicker-next {
	right: 2px;
}
.ui-datepicker .ui-datepicker-prev-hover {
	left: 1px;
}
.ui-datepicker .ui-datepicker-next-hover {
	right: 1px;
}
.ui-datepicker .ui-datepicker-prev span,
.ui-datepicker .ui-datepicker-next span {
	display: block;
	position: absolute;
	left: 50%;
	margin-left: -8px;
	top: 50%;
	margin-top: -8px;
}
.ui-datepicker .ui-datepicker-title {
	margin: 0 2.3em;
	line-height: 1.8em;
	text-align: center;
}
.ui-datepicker .ui-datepicker-title select {
	font-size: 1em;
	margin: 1px 0;
}
.ui-datepicker select.ui-datepicker-month,
.ui-datepicker select.ui-datepicker-year {
	width: 45%;
}
.ui-datepicker table {
	width: 100%;
	font-size: .9em;
	border-collapse: collapse;
	margin: 0 0 .4em;
}
.ui-datepicker th {
	padding: .7em .3em;
	text-align: center;
	font-weight: bold;
	border: 0;
}
.ui-datepicker td {
	border: 0;
	padding: 1px;
}
.ui-datepicker td span,
.ui-datepicker td a {
	display: block;
	padding: .2em;
	text-align: right;
	text-decoration: none;
}
.ui-datepicker .ui-datepicker-buttonpane {
	background-image: none;
	margin: .7em 0 0 0;
	padding: 0 .2em;
	border-left: 0;
	border-right: 0;
	border-bottom: 0;
}
.ui-datepicker .ui-datepicker-buttonpane button {
	float: right;
	margin: .5em .2em .4em;
	cursor: pointer;
	padding: .2em .6em .3em .6em;
	width: auto;
	overflow: visible;
}
.ui-datepicker .ui-datepicker-buttonpane button.ui-datepicker-current {
	float: left;
}


.ui-datepicker.ui-datepicker-multi {
	width: auto;
}
.ui-datepicker-multi .ui-datepicker-group {
	float: left;
}
.ui-datepicker-multi .ui-datepicker-group table {
	width: 95%;
	margin: 0 auto .4em;
}
.ui-datepicker-multi-2 .ui-datepicker-group {
	width: 50%;
}
.ui-datepicker-multi-3 .ui-datepicker-group {
	width: 33.3%;
}
.ui-datepicker-multi-4 .ui-datepicker-group {
	width: 25%;
}
.ui-datepicker-multi .ui-datepicker-group-last .ui-datepicker-header,
.ui-datepicker-multi .ui-datepicker-group-middle .ui-datepicker-header {
	border-left-width: 0;
}
.ui-datepicker-multi .ui-datepicker-buttonpane {
	clear: left;
}
.ui-datepicker-row-break {
	clear: both;
	width: 100%;
	font-size: 0;
}


.ui-datepicker-rtl {
	direction: rtl;
}
.ui-datepicker-rtl .ui-datepicker-prev {
	right: 2px;
	left: auto;
}
.ui-datepicker-rtl .ui-datepicker-next {
	left: 2px;
	right: auto;
}
.ui-datepicker-rtl .ui-datepicker-prev:hover {
	right: 1px;
	left: auto;
}
.ui-datepicker-rtl .ui-datepicker-next:hover {
	left: 1px;
	right: auto;
}
.ui-datepicker-rtl .ui-datepicker-buttonpane {
	clear: right;
}
.ui-datepicker-rtl .ui-datepicker-buttonpane button {
	float: left;
}
.ui-datepicker-rtl .ui-datepicker-buttonpane button.ui-datepicker-current,
.ui-datepicker-rtl .ui-datepicker-group {
	float: right;
}
.ui-datepicker-rtl .ui-datepicker-group-last .ui-datepicker-header,
.ui-datepicker-rtl .ui-datepicker-group-middle .ui-datepicker-header {
	border-right-width: 0;
	border-left-width: 1px;
}


.ui-datepicker .ui-icon {
	display: block;
	text-indent: -99999px;
	overflow: hidden;
	background-repeat: no-repeat;
	left: .5em;
	top: .3em;
}
.ui-dialog {
	position: absolute;
	top: 0;
	left: 0;
	padding: .2em;
	outline: 0;
}
.ui-dialog .ui-dialog-titlebar {
	padding: .4em 1em;
	position: relative;
}
.ui-dialog .ui-dialog-title {
	float: left;
	margin: .1em 0;
	white-space: nowrap;
	width: 90%;
	overflow: hidden;
	text-overflow: ellipsis;
}
.ui-dialog .ui-dialog-titlebar-close {
	position: absolute;
	right: .3em;
	top: 50%;
	width: 20px;
	margin: -10px 0 0 0;
	padding: 1px;
	height: 20px;
}
.ui-dialog .ui-dialog-content {
	position: relative;
	border: 0;
	padding: .5em 1em;
	background: none;
	overflow: auto;
}
.ui-dialog .ui-dialog-buttonpane {
	text-align: left;
	border-width: 1px 0 0 0;
	background-image: none;
	margin-top: .5em;
	padding: .3em 1em .5em .4em;
}
.ui-dialog .ui-dialog-buttonpane .ui-dialog-buttonset {
	float: right;
}
.ui-dialog .ui-dialog-buttonpane button {
	margin: .5em .4em .5em 0;
	cursor: pointer;
}
.ui-dialog .ui-resizable-n {
	height: 2px;
	top: 0;
}
.ui-dialog .ui-resizable-e {
	width: 2px;
	right: 0;
}
.ui-dialog .ui-resizable-s {
	height: 2px;
	bottom: 0;
}
.ui-dialog .ui-resizable-w {
	width: 2px;
	left: 0;
}
.ui-dialog .ui-resizable-se,
.ui-dialog .ui-resizable-sw,
.ui-dialog .ui-resizable-ne,
.ui-dialog .ui-resizable-nw {
	width: 7px;
	height: 7px;
}
.ui-dialog .ui-resizable-se {
	right: 0;
	bottom: 0;
}
.ui-dialog .ui-resizable-sw {
	left: 0;
	bottom: 0;
}
.ui-dialog .ui-resizable-ne {
	right: 0;
	top: 0;
}
.ui-dialog .ui-resizable-nw {
	left: 0;
	top: 0;
}
.ui-draggable .ui-dialog-titlebar {
	cursor: move;
}
.ui-draggable-handle {
	-ms-touch-action: none;
	touch-action: none;
}
.ui-resizable {
	position: relative;
}
.ui-resizable-handle {
	position: absolute;
	font-size: 0.1px;
	display: block;
	-ms-touch-action: none;
	touch-action: none;
}
.ui-resizable-disabled .ui-resizable-handle,
.ui-resizable-autohide .ui-resizable-handle {
	display: none;
}
.ui-resizable-n {
	cursor: n-resize;
	height: 7px;
	width: 100%;
	top: -5px;
	left: 0;
}
.ui-resizable-s {
	cursor: s-resize;
	height: 7px;
	width: 100%;
	bottom: -5px;
	left: 0;
}
.ui-resizable-e {
	cursor: e-resize;
	width: 7px;
	right: -5px;
	top: 0;
	height: 100%;
}
.ui-resizable-w {
	cursor: w-resize;
	width: 7px;
	left: -5px;
	top: 0;
	height: 100%;
}
.ui-resizable-se {
	cursor: se-resize;
	width: 12px;
	height: 12px;
	right: 1px;
	bottom: 1px;
}
.ui-resizable-sw {
	cursor: sw-resize;
	width: 9px;
	height: 9px;
	left: -5px;
	bottom: -5px;
}
.ui-resizable-nw {
	cursor: nw-resize;
	width: 9px;
	height: 9px;
	left: -5px;
	top: -5px;
}
.ui-resizable-ne {
	cursor: ne-resize;
	width: 9px;
	height: 9px;
	right: -5px;
	top: -5px;
}
.ui-progressbar {
	height: 2em;
	text-align: left;
	overflow: hidden;
}
.ui-progressbar .ui-progressbar-value {
	margin: -1px;
	height: 100%;
}
.ui-progressbar .ui-progressbar-overlay {
	background: url("data:image/gif;base64,R0lGODlhKAAoAIABAAAAAP///yH/C05FVFNDQVBFMi4wAwEAAAAh+QQJAQABACwAAAAAKAAoAAACkYwNqXrdC52DS06a7MFZI+4FHBCKoDeWKXqymPqGqxvJrXZbMx7Ttc+w9XgU2FB3lOyQRWET2IFGiU9m1frDVpxZZc6bfHwv4c1YXP6k1Vdy292Fb6UkuvFtXpvWSzA+HycXJHUXiGYIiMg2R6W459gnWGfHNdjIqDWVqemH2ekpObkpOlppWUqZiqr6edqqWQAAIfkECQEAAQAsAAAAACgAKAAAApSMgZnGfaqcg1E2uuzDmmHUBR8Qil95hiPKqWn3aqtLsS18y7G1SzNeowWBENtQd+T1JktP05nzPTdJZlR6vUxNWWjV+vUWhWNkWFwxl9VpZRedYcflIOLafaa28XdsH/ynlcc1uPVDZxQIR0K25+cICCmoqCe5mGhZOfeYSUh5yJcJyrkZWWpaR8doJ2o4NYq62lAAACH5BAkBAAEALAAAAAAoACgAAAKVDI4Yy22ZnINRNqosw0Bv7i1gyHUkFj7oSaWlu3ovC8GxNso5fluz3qLVhBVeT/Lz7ZTHyxL5dDalQWPVOsQWtRnuwXaFTj9jVVh8pma9JjZ4zYSj5ZOyma7uuolffh+IR5aW97cHuBUXKGKXlKjn+DiHWMcYJah4N0lYCMlJOXipGRr5qdgoSTrqWSq6WFl2ypoaUAAAIfkECQEAAQAsAAAAACgAKAAAApaEb6HLgd/iO7FNWtcFWe+ufODGjRfoiJ2akShbueb0wtI50zm02pbvwfWEMWBQ1zKGlLIhskiEPm9R6vRXxV4ZzWT2yHOGpWMyorblKlNp8HmHEb/lCXjcW7bmtXP8Xt229OVWR1fod2eWqNfHuMjXCPkIGNileOiImVmCOEmoSfn3yXlJWmoHGhqp6ilYuWYpmTqKUgAAIfkECQEAAQAsAAAAACgAKAAAApiEH6kb58biQ3FNWtMFWW3eNVcojuFGfqnZqSebuS06w5V80/X02pKe8zFwP6EFWOT1lDFk8rGERh1TTNOocQ61Hm4Xm2VexUHpzjymViHrFbiELsefVrn6XKfnt2Q9G/+Xdie499XHd2g4h7ioOGhXGJboGAnXSBnoBwKYyfioubZJ2Hn0RuRZaflZOil56Zp6iioKSXpUAAAh+QQJAQABACwAAAAAKAAoAAACkoQRqRvnxuI7kU1a1UU5bd5tnSeOZXhmn5lWK3qNTWvRdQxP8qvaC+/yaYQzXO7BMvaUEmJRd3TsiMAgswmNYrSgZdYrTX6tSHGZO73ezuAw2uxuQ+BbeZfMxsexY35+/Qe4J1inV0g4x3WHuMhIl2jXOKT2Q+VU5fgoSUI52VfZyfkJGkha6jmY+aaYdirq+lQAACH5BAkBAAEALAAAAAAoACgAAAKWBIKpYe0L3YNKToqswUlvznigd4wiR4KhZrKt9Upqip61i9E3vMvxRdHlbEFiEXfk9YARYxOZZD6VQ2pUunBmtRXo1Lf8hMVVcNl8JafV38aM2/Fu5V16Bn63r6xt97j09+MXSFi4BniGFae3hzbH9+hYBzkpuUh5aZmHuanZOZgIuvbGiNeomCnaxxap2upaCZsq+1kAACH5BAkBAAEALAAAAAAoACgAAAKXjI8By5zf4kOxTVrXNVlv1X0d8IGZGKLnNpYtm8Lr9cqVeuOSvfOW79D9aDHizNhDJidFZhNydEahOaDH6nomtJjp1tutKoNWkvA6JqfRVLHU/QUfau9l2x7G54d1fl995xcIGAdXqMfBNadoYrhH+Mg2KBlpVpbluCiXmMnZ2Sh4GBqJ+ckIOqqJ6LmKSllZmsoq6wpQAAAh+QQJAQABACwAAAAAKAAoAAAClYx/oLvoxuJDkU1a1YUZbJ59nSd2ZXhWqbRa2/gF8Gu2DY3iqs7yrq+xBYEkYvFSM8aSSObE+ZgRl1BHFZNr7pRCavZ5BW2142hY3AN/zWtsmf12p9XxxFl2lpLn1rseztfXZjdIWIf2s5dItwjYKBgo9yg5pHgzJXTEeGlZuenpyPmpGQoKOWkYmSpaSnqKileI2FAAACH5BAkBAAEALAAAAAAoACgAAAKVjB+gu+jG4kORTVrVhRlsnn2dJ3ZleFaptFrb+CXmO9OozeL5VfP99HvAWhpiUdcwkpBH3825AwYdU8xTqlLGhtCosArKMpvfa1mMRae9VvWZfeB2XfPkeLmm18lUcBj+p5dnN8jXZ3YIGEhYuOUn45aoCDkp16hl5IjYJvjWKcnoGQpqyPlpOhr3aElaqrq56Bq7VAAAOw==");
	height: 100%;
	filter: alpha(opacity=25); 
	opacity: 0.25;
}
.ui-progressbar-indeterminate .ui-progressbar-value {
	background-image: none;
}
.ui-selectable {
	-ms-touch-action: none;
	touch-action: none;
}
.ui-selectable-helper {
	position: absolute;
	z-index: 100;
	border: 1px dotted black;
}
.ui-selectmenu-menu {
	padding: 0;
	margin: 0;
	position: absolute;
	top: 0;
	left: 0;
	display: none;
}
.ui-selectmenu-menu .ui-menu {
	overflow: auto;
	overflow-x: hidden;
	padding-bottom: 1px;
}
.ui-selectmenu-menu .ui-menu .ui-selectmenu-optgroup {
	font-size: 1em;
	font-weight: bold;
	line-height: 1.5;
	padding: 2px 0.4em;
	margin: 0.5em 0 0 0;
	height: auto;
	border: 0;
}
.ui-selectmenu-open {
	display: block;
}
.ui-selectmenu-text {
	display: block;
	margin-right: 20px;
	overflow: hidden;
	text-overflow: ellipsis;
}
.ui-selectmenu-button.ui-button {
	text-align: left;
	white-space: nowrap;
	width: 14em;
}
.ui-selectmenu-icon.ui-icon {
	float: right;
	margin-top: 0;
}
.ui-slider {
	position: relative;
	text-align: left;
}
.ui-slider .ui-slider-handle {
	position: absolute;
	z-index: 2;
	width: 1.2em;
	height: 1.2em;
	cursor: default;
	-ms-touch-action: none;
	touch-action: none;
}
.ui-slider .ui-slider-range {
	position: absolute;
	z-index: 1;
	font-size: .7em;
	display: block;
	border: 0;
	background-position: 0 0;
}


.ui-slider.ui-state-disabled .ui-slider-handle,
.ui-slider.ui-state-disabled .ui-slider-range {
	filter: inherit;
}

.ui-slider-horizontal {
	height: .8em;
}
.ui-slider-horizontal .ui-slider-handle {
	top: -.3em;
	margin-left: -.6em;
}
.ui-slider-horizontal .ui-slider-range {
	top: 0;
	height: 100%;
}
.ui-slider-horizontal .ui-slider-range-min {
	left: 0;
}
.ui-slider-horizontal .ui-slider-range-max {
	right: 0;
}

.ui-slider-vertical {
	width: .8em;
	height: 100px;
}
.ui-slider-vertical .ui-slider-handle {
	left: -.3em;
	margin-left: 0;
	margin-bottom: -.6em;
}
.ui-slider-vertical .ui-slider-range {
	left: 0;
	width: 100%;
}
.ui-slider-vertical .ui-slider-range-min {
	bottom: 0;
}
.ui-slider-vertical .ui-slider-range-max {
	top: 0;
}
.ui-sortable-handle {
	-ms-touch-action: none;
	touch-action: none;
}
.ui-spinner {
	position: relative;
	display: inline-block;
	overflow: hidden;
	padding: 0;
	vertical-align: middle;
}
.ui-spinner-input {
	border: none;
	background: none;
	color: inherit;
	padding: .222em 0;
	margin: .2em 0;
	vertical-align: middle;
	margin-left: .4em;
	margin-right: 2em;
}
.ui-spinner-button {
	width: 1.6em;
	height: 50%;
	font-size: .5em;
	padding: 0;
	margin: 0;
	text-align: center;
	position: absolute;
	cursor: default;
	display: block;
	overflow: hidden;
	right: 0;
}

.ui-spinner a.ui-spinner-button {
	border-top-style: none;
	border-bottom-style: none;
	border-right-style: none;
}
.ui-spinner-up {
	top: 0;
}
.ui-spinner-down {
	bottom: 0;
}
.ui-tabs {
	position: relative;
	padding: .2em;
}
.ui-tabs .ui-tabs-nav {
	margin: 0;
	padding: .2em .2em 0;
}
.ui-tabs .ui-tabs-nav li {
	list-style: none;
	float: left;
	position: relative;
	top: 0;
	margin: 1px .2em 0 0;
	border-bottom-width: 0;
	padding: 0;
	white-space: nowrap;
}
.ui-tabs .ui-tabs-nav .ui-tabs-anchor {
	float: left;
	padding: .5em 1em;
	text-decoration: none;
}
.ui-tabs .ui-tabs-nav li.ui-tabs-active {
	margin-bottom: -1px;
	padding-bottom: 1px;
}
.ui-tabs .ui-tabs-nav li.ui-tabs-active .ui-tabs-anchor,
.ui-tabs .ui-tabs-nav li.ui-state-disabled .ui-tabs-anchor,
.ui-tabs .ui-tabs-nav li.ui-tabs-loading .ui-tabs-anchor {
	cursor: text;
}
.ui-tabs-collapsible .ui-tabs-nav li.ui-tabs-active .ui-tabs-anchor {
	cursor: pointer;
}
.ui-tabs .ui-tabs-panel {
	display: block;
	border-width: 0;
	padding: 1em 1.4em;
	background: none;
}
.ui-tooltip {
	padding: 8px;
	position: absolute;
	z-index: 9999;
	max-width: 300px;
}
body .ui-tooltip {
	border-width: 2px;
}

.ui-widget {
	font-family: Arial,Helvetica,sans-serif;
	font-size: 1em;
}
.ui-widget .ui-widget {
	font-size: 1em;
}
.ui-widget input,
.ui-widget select,
.ui-widget textarea,
.ui-widget button {
	font-family: Arial,Helvetica,sans-serif;
	font-size: 1em;
}
.ui-widget.ui-widget-content {
	border: 1px solid #c5c5c5;
}
.ui-widget-content {
	border: 1px solid #dddddd;
	background: #ffffff;
	color: #333333;
}
.ui-widget-content a {
	color: #333333;
}
.ui-widget-header {
	border: 1px solid #dddddd;
	background: #e9e9e9;
	color: #333333;
	font-weight: bold;
}
.ui-widget-header a {
	color: #333333;
}


.ui-state-default,
.ui-widget-content .ui-state-default,
.ui-widget-header .ui-state-default,
.ui-button,


html .ui-button.ui-state-disabled:hover,
html .ui-button.ui-state-disabled:active {
	border: 1px solid #c5c5c5;
	background: #f6f6f6;
	font-weight: normal;
	color: #454545;
}
.ui-state-default a,
.ui-state-default a:link,
.ui-state-default a:visited,
a.ui-button,
a:link.ui-button,
a:visited.ui-button,
.ui-button {
	color: #454545;
	text-decoration: none;
}
.ui-state-hover,
.ui-widget-content .ui-state-hover,
.ui-widget-header .ui-state-hover,
.ui-state-focus,
.ui-widget-content .ui-state-focus,
.ui-widget-header .ui-state-focus,
.ui-button:hover,
.ui-button:focus {
	border: 1px solid #cccccc;
	background: #ededed;
	font-weight: normal;
	color: #2b2b2b;
}
.ui-state-hover a,
.ui-state-hover a:hover,
.ui-state-hover a:link,
.ui-state-hover a:visited,
.ui-state-focus a,
.ui-state-focus a:hover,
.ui-state-focus a:link,
.ui-state-focus a:visited,
a.ui-button:hover,
a.ui-button:focus {
	color: #2b2b2b;
	text-decoration: none;
}

.ui-visual-focus {
	box-shadow: 0 0 3px 1px rgb(94, 158, 214);
}
.ui-state-active,
.ui-widget-content .ui-state-active,
.ui-widget-header .ui-state-active,
a.ui-button:active,
.ui-button:active,
.ui-button.ui-state-active:hover {
	border: 1px solid #003eff;
	background: #007fff;
	font-weight: normal;
	color: #ffffff;
}
.ui-icon-background,
.ui-state-active .ui-icon-background {
	border: #003eff;
	background-color: #ffffff;
}
.ui-state-active a,
.ui-state-active a:link,
.ui-state-active a:visited {
	color: #ffffff;
	text-decoration: none;
}


.ui-state-highlight,
.ui-widget-content .ui-state-highlight,
.ui-widget-header .ui-state-highlight {
	border: 1px solid #dad55e;
	background: #fffa90;
	color: #777620;
}
.ui-state-checked {
	border: 1px solid #dad55e;
	background: #fffa90;
}
.ui-state-highlight a,
.ui-widget-content .ui-state-highlight a,
.ui-widget-header .ui-state-highlight a {
	color: #777620;
}
.ui-state-error,
.ui-widget-content .ui-state-error,
.ui-widget-header .ui-state-error {
	border: 1px solid #f1a899;
	background: #fddfdf;
	color: #5f3f3f;
}
.ui-state-error a,
.ui-widget-content .ui-state-error a,
.ui-widget-header .ui-state-error a {
	color: #5f3f3f;
}
.ui-state-error-text,
.ui-widget-content .ui-state-error-text,
.ui-widget-header .ui-state-error-text {
	color: #5f3f3f;
}
.ui-priority-primary,
.ui-widget-content .ui-priority-primary,
.ui-widget-header .ui-priority-primary {
	font-weight: bold;
}
.ui-priority-secondary,
.ui-widget-content .ui-priority-secondary,
.ui-widget-header .ui-priority-secondary {
	opacity: .7;
	filter:Alpha(Opacity=70); 
	font-weight: normal;
}
.ui-state-disabled,
.ui-widget-content .ui-state-disabled,
.ui-widget-header .ui-state-disabled {
	opacity: .35;
	filter:Alpha(Opacity=35); 
	background-image: none;
}
.ui-state-disabled .ui-icon {
	filter:Alpha(Opacity=35); 
}




.ui-icon {
	width: 16px;
	height: 16px;
}
.ui-icon,
.ui-widget-content .ui-icon {
	background-image: url("images/ui-icons_444444_256x240.png");
}
.ui-widget-header .ui-icon {
	background-image: url("images/ui-icons_444444_256x240.png");
}
.ui-state-hover .ui-icon,
.ui-state-focus .ui-icon,
.ui-button:hover .ui-icon,
.ui-button:focus .ui-icon {
	background-image: url("images/ui-icons_555555_256x240.png");
}
.ui-state-active .ui-icon,
.ui-button:active .ui-icon {
	background-image: url("images/ui-icons_ffffff_256x240.png");
}
.ui-state-highlight .ui-icon,
.ui-button .ui-state-highlight.ui-icon {
	background-image: url("images/ui-icons_777620_256x240.png");
}
.ui-state-error .ui-icon,
.ui-state-error-text .ui-icon {
	background-image: url("images/ui-icons_cc0000_256x240.png");
}
.ui-button .ui-icon {
	background-image: url("images/ui-icons_777777_256x240.png");
}


.ui-icon-blank { background-position: 16px 16px; }
.ui-icon-caret-1-n { background-position: 0 0; }
.ui-icon-caret-1-ne { background-position: -16px 0; }
.ui-icon-caret-1-e { background-position: -32px 0; }
.ui-icon-caret-1-se { background-position: -48px 0; }
.ui-icon-caret-1-s { background-position: -65px 0; }
.ui-icon-caret-1-sw { background-position: -80px 0; }
.ui-icon-caret-1-w { background-position: -96px 0; }
.ui-icon-caret-1-nw { background-position: -112px 0; }
.ui-icon-caret-2-n-s { background-position: -128px 0; }
.ui-icon-caret-2-e-w { background-position: -144px 0; }
.ui-icon-triangle-1-n { background-position: 0 -16px; }
.ui-icon-triangle-1-ne { background-position: -16px -16px; }
.ui-icon-triangle-1-e { background-position: -32px -16px; }
.ui-icon-triangle-1-se { background-position: -48px -16px; }
.ui-icon-triangle-1-s { background-position: -65px -16px; }
.ui-icon-triangle-1-sw { background-position: -80px -16px; }
.ui-icon-triangle-1-w { background-position: -96px -16px; }
.ui-icon-triangle-1-nw { background-position: -112px -16px; }
.ui-icon-triangle-2-n-s { background-position: -128px -16px; }
.ui-icon-triangle-2-e-w { background-position: -144px -16px; }
.ui-icon-arrow-1-n { background-position: 0 -32px; }
.ui-icon-arrow-1-ne { background-position: -16px -32px; }
.ui-icon-arrow-1-e { background-position: -32px -32px; }
.ui-icon-arrow-1-se { background-position: -48px -32px; }
.ui-icon-arrow-1-s { background-position: -65px -32px; }
.ui-icon-arrow-1-sw { background-position: -80px -32px; }
.ui-icon-arrow-1-w { background-position: -96px -32px; }
.ui-icon-arrow-1-nw { background-position: -112px -32px; }
.ui-icon-arrow-2-n-s { background-position: -128px -32px; }
.ui-icon-arrow-2-ne-sw { background-position: -144px -32px; }
.ui-icon-arrow-2-e-w { background-position: -160px -32px; }
.ui-icon-arrow-2-se-nw { background-position: -176px -32px; }
.ui-icon-arrowstop-1-n { background-position: -192px -32px; }
.ui-icon-arrowstop-1-e { background-position: -208px -32px; }
.ui-icon-arrowstop-1-s { background-position: -224px -32px; }
.ui-icon-arrowstop-1-w { background-position: -240px -32px; }
.ui-icon-arrowthick-1-n { background-position: 1px -48px; }
.ui-icon-arrowthick-1-ne { background-position: -16px -48px; }
.ui-icon-arrowthick-1-e { background-position: -32px -48px; }
.ui-icon-arrowthick-1-se { background-position: -48px -48px; }
.ui-icon-arrowthick-1-s { background-position: -64px -48px; }
.ui-icon-arrowthick-1-sw { background-position: -80px -48px; }
.ui-icon-arrowthick-1-w { background-position: -96px -48px; }
.ui-icon-arrowthick-1-nw { background-position: -112px -48px; }
.ui-icon-arrowthick-2-n-s { background-position: -128px -48px; }
.ui-icon-arrowthick-2-ne-sw { background-position: -144px -48px; }
.ui-icon-arrowthick-2-e-w { background-position: -160px -48px; }
.ui-icon-arrowthick-2-se-nw { background-position: -176px -48px; }
.ui-icon-arrowthickstop-1-n { background-position: -192px -48px; }
.ui-icon-arrowthickstop-1-e { background-position: -208px -48px; }
.ui-icon-arrowthickstop-1-s { background-position: -224px -48px; }
.ui-icon-arrowthickstop-1-w { background-position: -240px -48px; }
.ui-icon-arrowreturnthick-1-w { background-position: 0 -64px; }
.ui-icon-arrowreturnthick-1-n { background-position: -16px -64px; }
.ui-icon-arrowreturnthick-1-e { background-position: -32px -64px; }
.ui-icon-arrowreturnthick-1-s { background-position: -48px -64px; }
.ui-icon-arrowreturn-1-w { background-position: -64px -64px; }
.ui-icon-arrowreturn-1-n { background-position: -80px -64px; }
.ui-icon-arrowreturn-1-e { background-position: -96px -64px; }
.ui-icon-arrowreturn-1-s { background-position: -112px -64px; }
.ui-icon-arrowrefresh-1-w { background-position: -128px -64px; }
.ui-icon-arrowrefresh-1-n { background-position: -144px -64px; }
.ui-icon-arrowrefresh-1-e { background-position: -160px -64px; }
.ui-icon-arrowrefresh-1-s { background-position: -176px -64px; }
.ui-icon-arrow-4 { background-position: 0 -80px; }
.ui-icon-arrow-4-diag { background-position: -16px -80px; }
.ui-icon-extlink { background-position: -32px -80px; }
.ui-icon-newwin { background-position: -48px -80px; }
.ui-icon-refresh { background-position: -64px -80px; }
.ui-icon-shuffle { background-position: -80px -80px; }
.ui-icon-transfer-e-w { background-position: -96px -80px; }
.ui-icon-transferthick-e-w { background-position: -112px -80px; }
.ui-icon-folder-collapsed { background-position: 0 -96px; }
.ui-icon-folder-open { background-position: -16px -96px; }
.ui-icon-document { background-position: -32px -96px; }
.ui-icon-document-b { background-position: -48px -96px; }
.ui-icon-note { background-position: -64px -96px; }
.ui-icon-mail-closed { background-position: -80px -96px; }
.ui-icon-mail-open { background-position: -96px -96px; }
.ui-icon-suitcase { background-position: -112px -96px; }
.ui-icon-comment { background-position: -128px -96px; }
.ui-icon-person { background-position: -144px -96px; }
.ui-icon-print { background-position: -160px -96px; }
.ui-icon-trash { background-position: -176px -96px; }
.ui-icon-locked { background-position: -192px -96px; }
.ui-icon-unlocked { background-position: -208px -96px; }
.ui-icon-bookmark { background-position: -224px -96px; }
.ui-icon-tag { background-position: -240px -96px; }
.ui-icon-home { background-position: 0 -112px; }
.ui-icon-flag { background-position: -16px -112px; }
.ui-icon-calendar { background-position: -32px -112px; }
.ui-icon-cart { background-position: -48px -112px; }
.ui-icon-pencil { background-position: -64px -112px; }
.ui-icon-clock { background-position: -80px -112px; }
.ui-icon-disk { background-position: -96px -112px; }
.ui-icon-calculator { background-position: -112px -112px; }
.ui-icon-zoomin { background-position: -128px -112px; }
.ui-icon-zoomout { background-position: -144px -112px; }
.ui-icon-search { background-position: -160px -112px; }
.ui-icon-wrench { background-position: -176px -112px; }
.ui-icon-gear { background-position: -192px -112px; }
.ui-icon-heart { background-position: -208px -112px; }
.ui-icon-star { background-position: -224px -112px; }
.ui-icon-link { background-position: -240px -112px; }
.ui-icon-cancel { background-position: 0 -128px; }
.ui-icon-plus { background-position: -16px -128px; }
.ui-icon-plusthick { background-position: -32px -128px; }
.ui-icon-minus { background-position: -48px -128px; }
.ui-icon-minusthick { background-position: -64px -128px; }
.ui-icon-close { background-position: -80px -128px; }
.ui-icon-closethick { background-position: -96px -128px; }
.ui-icon-key { background-position: -112px -128px; }
.ui-icon-lightbulb { background-position: -128px -128px; }
.ui-icon-scissors { background-position: -144px -128px; }
.ui-icon-clipboard { background-position: -160px -128px; }
.ui-icon-copy { background-position: -176px -128px; }
.ui-icon-contact { background-position: -192px -128px; }
.ui-icon-image { background-position: -208px -128px; }
.ui-icon-video { background-position: -224px -128px; }
.ui-icon-script { background-position: -240px -128px; }
.ui-icon-alert { background-position: 0 -144px; }
.ui-icon-info { background-position: -16px -144px; }
.ui-icon-notice { background-position: -32px -144px; }
.ui-icon-help { background-position: -48px -144px; }
.ui-icon-check { background-position: -64px -144px; }
.ui-icon-bullet { background-position: -80px -144px; }
.ui-icon-radio-on { background-position: -96px -144px; }
.ui-icon-radio-off { background-position: -112px -144px; }
.ui-icon-pin-w { background-position: -128px -144px; }
.ui-icon-pin-s { background-position: -144px -144px; }
.ui-icon-play { background-position: 0 -160px; }
.ui-icon-pause { background-position: -16px -160px; }
.ui-icon-seek-next { background-position: -32px -160px; }
.ui-icon-seek-prev { background-position: -48px -160px; }
.ui-icon-seek-end { background-position: -64px -160px; }
.ui-icon-seek-start { background-position: -80px -160px; }

.ui-icon-seek-first { background-position: -80px -160px; }
.ui-icon-stop { background-position: -96px -160px; }
.ui-icon-eject { background-position: -112px -160px; }
.ui-icon-volume-off { background-position: -128px -160px; }
.ui-icon-volume-on { background-position: -144px -160px; }
.ui-icon-power { background-position: 0 -176px; }
.ui-icon-signal-diag { background-position: -16px -176px; }
.ui-icon-signal { background-position: -32px -176px; }
.ui-icon-battery-0 { background-position: -48px -176px; }
.ui-icon-battery-1 { background-position: -64px -176px; }
.ui-icon-battery-2 { background-position: -80px -176px; }
.ui-icon-battery-3 { background-position: -96px -176px; }
.ui-icon-circle-plus { background-position: 0 -192px; }
.ui-icon-circle-minus { background-position: -16px -192px; }
.ui-icon-circle-close { background-position: -32px -192px; }
.ui-icon-circle-triangle-e { background-position: -48px -192px; }
.ui-icon-circle-triangle-s { background-position: -64px -192px; }
.ui-icon-circle-triangle-w { background-position: -80px -192px; }
.ui-icon-circle-triangle-n { background-position: -96px -192px; }
.ui-icon-circle-arrow-e { background-position: -112px -192px; }
.ui-icon-circle-arrow-s { background-position: -128px -192px; }
.ui-icon-circle-arrow-w { background-position: -144px -192px; }
.ui-icon-circle-arrow-n { background-position: -160px -192px; }
.ui-icon-circle-zoomin { background-position: -176px -192px; }
.ui-icon-circle-zoomout { background-position: -192px -192px; }
.ui-icon-circle-check { background-position: -208px -192px; }
.ui-icon-circlesmall-plus { background-position: 0 -208px; }
.ui-icon-circlesmall-minus { background-position: -16px -208px; }
.ui-icon-circlesmall-close { background-position: -32px -208px; }
.ui-icon-squaresmall-plus { background-position: -48px -208px; }
.ui-icon-squaresmall-minus { background-position: -64px -208px; }
.ui-icon-squaresmall-close { background-position: -80px -208px; }
.ui-icon-grip-dotted-vertical { background-position: 0 -224px; }
.ui-icon-grip-dotted-horizontal { background-position: -16px -224px; }
.ui-icon-grip-solid-vertical { background-position: -32px -224px; }
.ui-icon-grip-solid-horizontal { background-position: -48px -224px; }
.ui-icon-gripsmall-diagonal-se { background-position: -64px -224px; }
.ui-icon-grip-diagonal-se { background-position: -80px -224px; }





.ui-corner-all,
.ui-corner-top,
.ui-corner-left,
.ui-corner-tl {
	border-top-left-radius: 3px;
}
.ui-corner-all,
.ui-corner-top,
.ui-corner-right,
.ui-corner-tr {
	border-top-right-radius: 3px;
}
.ui-corner-all,
.ui-corner-bottom,
.ui-corner-left,
.ui-corner-bl {
	border-bottom-left-radius: 3px;
}
.ui-corner-all,
.ui-corner-bottom,
.ui-corner-right,
.ui-corner-br {
	border-bottom-right-radius: 3px;
}


.ui-widget-overlay {
	background: #aaaaaa;
	opacity: .3;
	filter: Alpha(Opacity=30); 
}
.ui-widget-shadow {
	-webkit-box-shadow: 0px 0px 5px #666666;
	box-shadow: 0px 0px 5px #666666;
} 
</style>
<script src='js/jquery-1.12.4.js'></script>
<script src='js/jquery-ui.js'></script>

<script>
$( function() {
	$( '#tabs-collect-classes-from-hierarchical-partition' ).tabs();
} );
</script>
<div id='tabs-collect-classes-from-hierarchical-partition'>
<ul>
<li><a href='#tab-collect-classes-from-hierarchical-partition-1'>n_signatures ≥ 2818</a></li>
<li><a href='#tab-collect-classes-from-hierarchical-partition-2'>n_signatures ≥ 2995</a></li>
<li><a href='#tab-collect-classes-from-hierarchical-partition-3'>n_signatures ≥ 3376</a></li>
<li><a href='#tab-collect-classes-from-hierarchical-partition-4'>n_signatures ≥ 3533</a></li>
<li><a href='#tab-collect-classes-from-hierarchical-partition-5'>n_signatures ≥ 3565</a></li>
<li><a href='#tab-collect-classes-from-hierarchical-partition-6'>n_signatures ≥ 4786</a></li>
<li><a href='#tab-collect-classes-from-hierarchical-partition-7'>n_signatures ≥ 5739</a></li>
<li><a href='#tab-collect-classes-from-hierarchical-partition-8'>n_signatures ≥ 8194</a></li>
<li><a href='#tab-collect-classes-from-hierarchical-partition-9'>n_signatures ≥ 10868</a></li>
<li><a href='#tab-collect-classes-from-hierarchical-partition-10'>n_signatures ≥ 19218</a></li>
<li><a href='#tab-collect-classes-from-hierarchical-partition-11'>n_signatures ≥ 22248</a></li>
<li><a href='#tab-collect-classes-from-hierarchical-partition-12'>n_signatures ≥ 25188</a></li>
<li><a href='#tab-collect-classes-from-hierarchical-partition-13'>n_signatures ≥ 32510</a></li>
</ul>
<div id='tab-collect-classes-from-hierarchical-partition-1'>
<pre><code class="r">collect_classes(res_rh, merge_node = merge_node_param(min_n_signatures = 2818))
</code></pre>

<p><img src="figure_cola/tab-collect-classes-from-hierarchical-partition-1-1.png" alt="plot of chunk tab-collect-classes-from-hierarchical-partition-1"/></p>

</div>
<div id='tab-collect-classes-from-hierarchical-partition-2'>
<pre><code class="r">collect_classes(res_rh, merge_node = merge_node_param(min_n_signatures = 2995))
</code></pre>

<p><img src="figure_cola/tab-collect-classes-from-hierarchical-partition-2-1.png" alt="plot of chunk tab-collect-classes-from-hierarchical-partition-2"/></p>

</div>
<div id='tab-collect-classes-from-hierarchical-partition-3'>
<pre><code class="r">collect_classes(res_rh, merge_node = merge_node_param(min_n_signatures = 3376))
</code></pre>

<p><img src="figure_cola/tab-collect-classes-from-hierarchical-partition-3-1.png" alt="plot of chunk tab-collect-classes-from-hierarchical-partition-3"/></p>

</div>
<div id='tab-collect-classes-from-hierarchical-partition-4'>
<pre><code class="r">collect_classes(res_rh, merge_node = merge_node_param(min_n_signatures = 3533))
</code></pre>

<p><img src="figure_cola/tab-collect-classes-from-hierarchical-partition-4-1.png" alt="plot of chunk tab-collect-classes-from-hierarchical-partition-4"/></p>

</div>
<div id='tab-collect-classes-from-hierarchical-partition-5'>
<pre><code class="r">collect_classes(res_rh, merge_node = merge_node_param(min_n_signatures = 3565))
</code></pre>

<p><img src="figure_cola/tab-collect-classes-from-hierarchical-partition-5-1.png" alt="plot of chunk tab-collect-classes-from-hierarchical-partition-5"/></p>

</div>
<div id='tab-collect-classes-from-hierarchical-partition-6'>
<pre><code class="r">collect_classes(res_rh, merge_node = merge_node_param(min_n_signatures = 4786))
</code></pre>

<p><img src="figure_cola/tab-collect-classes-from-hierarchical-partition-6-1.png" alt="plot of chunk tab-collect-classes-from-hierarchical-partition-6"/></p>

</div>
<div id='tab-collect-classes-from-hierarchical-partition-7'>
<pre><code class="r">collect_classes(res_rh, merge_node = merge_node_param(min_n_signatures = 5739))
</code></pre>

<p><img src="figure_cola/tab-collect-classes-from-hierarchical-partition-7-1.png" alt="plot of chunk tab-collect-classes-from-hierarchical-partition-7"/></p>

</div>
<div id='tab-collect-classes-from-hierarchical-partition-8'>
<pre><code class="r">collect_classes(res_rh, merge_node = merge_node_param(min_n_signatures = 8194))
</code></pre>

<p><img src="figure_cola/tab-collect-classes-from-hierarchical-partition-8-1.png" alt="plot of chunk tab-collect-classes-from-hierarchical-partition-8"/></p>

</div>
<div id='tab-collect-classes-from-hierarchical-partition-9'>
<pre><code class="r">collect_classes(res_rh, merge_node = merge_node_param(min_n_signatures = 10868))
</code></pre>

<pre><code>#&gt; Error in lt[[hierarchy[i, 1]]]$AddChildNode({: attempt to apply non-function
</code></pre>

</div>
<div id='tab-collect-classes-from-hierarchical-partition-10'>
<pre><code class="r">collect_classes(res_rh, merge_node = merge_node_param(min_n_signatures = 19218))
</code></pre>

<pre><code>#&gt; Error in lt[[hierarchy[i, 1]]]$AddChildNode({: attempt to apply non-function
</code></pre>

</div>
<div id='tab-collect-classes-from-hierarchical-partition-11'>
<pre><code class="r">collect_classes(res_rh, merge_node = merge_node_param(min_n_signatures = 22248))
</code></pre>

<pre><code>#&gt; Error in max(children_height): invalid &#39;type&#39; (list) of argument
</code></pre>

</div>
<div id='tab-collect-classes-from-hierarchical-partition-12'>
<pre><code class="r">collect_classes(res_rh, merge_node = merge_node_param(min_n_signatures = 25188))
</code></pre>

<pre><code>#&gt; Error in max(children_height): invalid &#39;type&#39; (list) of argument
</code></pre>

</div>
<div id='tab-collect-classes-from-hierarchical-partition-13'>
<pre><code class="r">collect_classes(res_rh, merge_node = merge_node_param(min_n_signatures = 32510))
</code></pre>

<pre><code>#&gt; Error in max(children_height): invalid &#39;type&#39; (list) of argument
</code></pre>

</div>
</div>

Following shows the table of the partitions (You need to click the **show/hide
code output** link to see it).


<script>
$( function() {
	$( '#tabs-get-classes-from-hierarchical-partition' ).tabs();
} );
</script>
<div id='tabs-get-classes-from-hierarchical-partition'>
<ul>
<li><a href='#tab-get-classes-from-hierarchical-partition-1'>n_signatures ≥ 2818</a></li>
<li><a href='#tab-get-classes-from-hierarchical-partition-2'>n_signatures ≥ 2995</a></li>
<li><a href='#tab-get-classes-from-hierarchical-partition-3'>n_signatures ≥ 3376</a></li>
<li><a href='#tab-get-classes-from-hierarchical-partition-4'>n_signatures ≥ 3533</a></li>
<li><a href='#tab-get-classes-from-hierarchical-partition-5'>n_signatures ≥ 3565</a></li>
<li><a href='#tab-get-classes-from-hierarchical-partition-6'>n_signatures ≥ 4786</a></li>
<li><a href='#tab-get-classes-from-hierarchical-partition-7'>n_signatures ≥ 5739</a></li>
<li><a href='#tab-get-classes-from-hierarchical-partition-8'>n_signatures ≥ 8194</a></li>
<li><a href='#tab-get-classes-from-hierarchical-partition-9'>n_signatures ≥ 10868</a></li>
<li><a href='#tab-get-classes-from-hierarchical-partition-10'>n_signatures ≥ 19218</a></li>
<li><a href='#tab-get-classes-from-hierarchical-partition-11'>n_signatures ≥ 22248</a></li>
<li><a href='#tab-get-classes-from-hierarchical-partition-12'>n_signatures ≥ 25188</a></li>
<li><a href='#tab-get-classes-from-hierarchical-partition-13'>n_signatures ≥ 32510</a></li>
</ul>

<div id='tab-get-classes-from-hierarchical-partition-1'>
<p><a id='tab-get-classes-from-hierarchical-partition-1-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">get_classes(res_rh, merge_node = merge_node_param(min_n_signatures = 2818))
</code></pre>

<pre><code>#&gt; TCGA.AB.2888.03 TCGA.AB.2995.03 TCGA.AB.2884.03 TCGA.AB.2878.03 TCGA.AB.2998.03 TCGA.AB.2913.03 
#&gt;          &quot;0331&quot;          &quot;0213&quot;          &quot;0132&quot;          &quot;0233&quot;          &quot;0321&quot;           &quot;012&quot; 
#&gt; TCGA.AB.2883.03 TCGA.AB.2957.03 TCGA.AB.2984.03 TCGA.AB.2837.03 TCGA.AB.2874.03 TCGA.AB.2836.03 
#&gt;          &quot;0212&quot;          &quot;0331&quot;          &quot;0221&quot;          &quot;0142&quot;          &quot;0221&quot;          &quot;0141&quot; 
#&gt; TCGA.AB.2876.03 TCGA.AB.2830.03 TCGA.AB.2823.03 TCGA.AB.2999.03 TCGA.AB.2940.03 TCGA.AB.2941.03 
#&gt;           &quot;031&quot;          &quot;0211&quot;          &quot;0324&quot;          &quot;0322&quot;           &quot;031&quot;          &quot;0213&quot; 
#&gt; TCGA.AB.2987.03 TCGA.AB.2945.03 TCGA.AB.2963.03 TCGA.AB.2967.03 TCGA.AB.2843.03 TCGA.AB.2807.03 
#&gt;          &quot;0212&quot;          &quot;0132&quot;          &quot;0141&quot;          &quot;0141&quot;          &quot;0231&quot;          &quot;0233&quot; 
#&gt; TCGA.AB.3012.03 TCGA.AB.2971.03 TCGA.AB.2809.03 TCGA.AB.2873.03 TCGA.AB.2802.03 TCGA.AB.2851.03 
#&gt;          &quot;0323&quot;          &quot;0211&quot;          &quot;0112&quot;          &quot;0213&quot;          &quot;0111&quot;          &quot;0132&quot; 
#&gt; TCGA.AB.2853.03 TCGA.AB.2847.03 TCGA.AB.2833.03 TCGA.AB.2814.03 TCGA.AB.2898.03 TCGA.AB.2866.03 
#&gt;          &quot;0111&quot;          &quot;0233&quot;          &quot;0213&quot;          &quot;0233&quot;          &quot;0211&quot;          &quot;0221&quot; 
#&gt; TCGA.AB.2875.03 TCGA.AB.2841.03 TCGA.AB.2922.03 TCGA.AB.3008.03 TCGA.AB.2968.03 TCGA.AB.2811.03 
#&gt;           &quot;034&quot;          &quot;0321&quot;          &quot;0231&quot;           &quot;031&quot;          &quot;0213&quot;          &quot;0111&quot; 
#&gt; TCGA.AB.2895.03 TCGA.AB.2933.03 TCGA.AB.2827.03 TCGA.AB.2942.03 TCGA.AB.2910.03 TCGA.AB.2934.03 
#&gt;          &quot;0112&quot;          &quot;0231&quot;          &quot;0141&quot;          &quot;0332&quot;          &quot;0212&quot;          &quot;0211&quot; 
#&gt; TCGA.AB.2959.03 TCGA.AB.2871.03 TCGA.AB.2907.03 TCGA.AB.2932.03 TCGA.AB.2824.03 TCGA.AB.2972.03 
#&gt;         &quot;02221&quot;         &quot;02222&quot;         &quot;02221&quot;          &quot;0141&quot;          &quot;0131&quot;          &quot;0132&quot; 
#&gt; TCGA.AB.2915.03 TCGA.AB.2970.03 TCGA.AB.2949.03 TCGA.AB.2912.03 TCGA.AB.2838.03 TCGA.AB.2872.03 
#&gt;          &quot;0231&quot;          &quot;0233&quot;          &quot;0231&quot;          &quot;0233&quot;          &quot;0233&quot;          &quot;0323&quot; 
#&gt; TCGA.AB.2897.03 TCGA.AB.2965.03 TCGA.AB.2891.03 TCGA.AB.2921.03 TCGA.AB.2867.03 TCGA.AB.2842.03 
#&gt;          &quot;0321&quot;          &quot;0111&quot;          &quot;0232&quot;           &quot;031&quot;         &quot;02221&quot;          &quot;0131&quot; 
#&gt; TCGA.AB.2862.03 TCGA.AB.2840.03 TCGA.AB.2822.03 TCGA.AB.2832.03 TCGA.AB.2893.03 TCGA.AB.2956.03 
#&gt;          &quot;0321&quot;          &quot;0322&quot;         &quot;02221&quot;          &quot;0212&quot;          &quot;0212&quot;          &quot;0212&quot; 
#&gt; TCGA.AB.2903.03 TCGA.AB.2845.03 TCGA.AB.2948.03 TCGA.AB.2869.03 TCGA.AB.3009.03 TCGA.AB.2944.03 
#&gt;         &quot;02223&quot;           &quot;031&quot;         &quot;02222&quot;          &quot;0132&quot;           &quot;031&quot;          &quot;0232&quot; 
#&gt; TCGA.AB.2886.03 TCGA.AB.2904.03 TCGA.AB.3005.03 TCGA.AB.2861.03 TCGA.AB.2917.03 TCGA.AB.2964.03 
#&gt;           &quot;034&quot;          &quot;0231&quot;          &quot;0212&quot;          &quot;0212&quot;          &quot;0233&quot;         &quot;02223&quot; 
#&gt; TCGA.AB.2955.03 TCGA.AB.2911.03 TCGA.AB.2892.03 TCGA.AB.2817.03 TCGA.AB.2906.03 TCGA.AB.2857.03 
#&gt;           &quot;031&quot;          &quot;0142&quot;          &quot;0332&quot;          &quot;0231&quot;          &quot;0322&quot;          &quot;0231&quot; 
#&gt; TCGA.AB.2805.03 TCGA.AB.2983.03 TCGA.AB.2918.03 TCGA.AB.2990.03 TCGA.AB.2937.03 TCGA.AB.3006.03 
#&gt;         &quot;02221&quot;          &quot;0231&quot;           &quot;012&quot;          &quot;0221&quot;           &quot;034&quot;          &quot;0131&quot; 
#&gt; TCGA.AB.2829.03 TCGA.AB.2848.03 TCGA.AB.2914.03 TCGA.AB.3002.03 TCGA.AB.2877.03 TCGA.AB.2969.03 
#&gt;          &quot;0213&quot;          &quot;0141&quot;           &quot;034&quot;          &quot;0221&quot;          &quot;0221&quot;          &quot;0111&quot; 
#&gt; TCGA.AB.2839.03 TCGA.AB.2835.03 TCGA.AB.2974.03 TCGA.AB.2920.03 TCGA.AB.2980.03 TCGA.AB.2819.03 
#&gt;           &quot;012&quot;          &quot;0141&quot;          &quot;0112&quot;          &quot;0233&quot;          &quot;0325&quot;           &quot;034&quot; 
#&gt; TCGA.AB.2992.03 TCGA.AB.2919.03 TCGA.AB.2928.03 TCGA.AB.2927.03 TCGA.AB.2806.03 TCGA.AB.2885.03 
#&gt;         &quot;02221&quot;          &quot;0221&quot;          &quot;0211&quot;          &quot;0231&quot;           &quot;034&quot;          &quot;0231&quot; 
#&gt; TCGA.AB.2815.03 TCGA.AB.2996.03 TCGA.AB.2936.03 TCGA.AB.2939.03 TCGA.AB.2979.03 TCGA.AB.2986.03 
#&gt;          &quot;0331&quot;         &quot;02222&quot;         &quot;02221&quot;           &quot;031&quot;           &quot;031&quot;           &quot;012&quot; 
#&gt; TCGA.AB.2931.03 TCGA.AB.2896.03 TCGA.AB.2966.03 TCGA.AB.2820.03 TCGA.AB.2808.03 TCGA.AB.2991.03 
#&gt;          &quot;0111&quot;          &quot;0112&quot;          &quot;0232&quot;          &quot;0231&quot;           &quot;031&quot;          &quot;0324&quot; 
#&gt; TCGA.AB.2803.03 TCGA.AB.2900.03 TCGA.AB.2899.03 TCGA.AB.2812.03 TCGA.AB.3011.03 TCGA.AB.2946.03 
#&gt;          &quot;0321&quot;          &quot;0221&quot;          &quot;0233&quot;           &quot;012&quot;          &quot;0131&quot;           &quot;012&quot; 
#&gt; TCGA.AB.3000.03 TCGA.AB.2997.03 TCGA.AB.3001.03 TCGA.AB.2926.03 TCGA.AB.2856.03 TCGA.AB.2977.03 
#&gt;           &quot;031&quot;          &quot;0324&quot;          &quot;0324&quot;          &quot;0221&quot;           &quot;012&quot;          &quot;0221&quot; 
#&gt; TCGA.AB.2879.03 TCGA.AB.2976.03 TCGA.AB.2989.03 TCGA.AB.2849.03 TCGA.AB.2981.03 TCGA.AB.2954.03 
#&gt;          &quot;0142&quot;          &quot;0141&quot;           &quot;012&quot;          &quot;0232&quot;          &quot;0112&quot;          &quot;0332&quot; 
#&gt; TCGA.AB.2973.03 TCGA.AB.2828.03 TCGA.AB.2804.03 TCGA.AB.2818.03 TCGA.AB.2930.03 TCGA.AB.2821.03 
#&gt;          &quot;0142&quot;          &quot;0331&quot;          &quot;0325&quot;          &quot;0142&quot;          &quot;0142&quot;         &quot;02221&quot; 
#&gt; TCGA.AB.2816.03 TCGA.AB.2863.03 TCGA.AB.2950.03 TCGA.AB.2925.03 TCGA.AB.3007.03 TCGA.AB.2882.03 
#&gt;          &quot;0132&quot;         &quot;02221&quot;           &quot;034&quot;          &quot;0111&quot;          &quot;0323&quot;          &quot;0233&quot; 
#&gt; TCGA.AB.2825.03 TCGA.AB.2947.03 TCGA.AB.2916.03 TCGA.AB.2855.03 TCGA.AB.2978.03 TCGA.AB.2952.03 
#&gt;          &quot;0112&quot;          &quot;0111&quot;          &quot;0213&quot;          &quot;0221&quot;          &quot;0211&quot;          &quot;0233&quot; 
#&gt; TCGA.AB.2868.03 TCGA.AB.2908.03 TCGA.AB.2938.03 TCGA.AB.2923.03 TCGA.AB.2890.03 TCGA.AB.2988.03 
#&gt;          &quot;0231&quot;          &quot;0231&quot;          &quot;0213&quot;         &quot;02223&quot;          &quot;0231&quot;          &quot;0132&quot; 
#&gt; TCGA.AB.2985.03 TCGA.AB.2880.03 TCGA.AB.2889.03 TCGA.AB.2887.03 TCGA.AB.2881.03 TCGA.AB.2834.03 
#&gt;          &quot;0132&quot;           &quot;031&quot;          &quot;0331&quot;          &quot;0211&quot;          &quot;0332&quot;          &quot;0221&quot; 
#&gt; TCGA.AB.2943.03 TCGA.AB.2982.03 TCGA.AB.2844.03 TCGA.AB.2870.03 TCGA.AB.2813.03 TCGA.AB.2894.03 
#&gt;          &quot;0231&quot;          &quot;0321&quot;           &quot;012&quot;          &quot;0331&quot;          &quot;0231&quot;          &quot;0212&quot; 
#&gt; TCGA.AB.2909.03 TCGA.AB.2858.03 TCGA.AB.2935.03 TCGA.AB.2929.03 TCGA.AB.2831.03 TCGA.AB.2826.03 
#&gt;           &quot;034&quot;          &quot;0332&quot;          &quot;0231&quot;          &quot;0233&quot;          &quot;0211&quot;          &quot;0221&quot; 
#&gt; TCGA.AB.2993.03 TCGA.AB.2810.03 TCGA.AB.2924.03 TCGA.AB.2901.03 TCGA.AB.2975.03 TCGA.AB.2860.03 
#&gt;          &quot;0142&quot;          &quot;0221&quot;          &quot;0141&quot;         &quot;02221&quot;          &quot;0211&quot;          &quot;0233&quot; 
#&gt; TCGA.AB.2854.03 TCGA.AB.2846.03 
#&gt;         &quot;02222&quot;          &quot;0332&quot;
</code></pre>

<script>
$('#tab-get-classes-from-hierarchical-partition-1-a').parent().next().next().hide();
$('#tab-get-classes-from-hierarchical-partition-1-a').click(function(){
  $('#tab-get-classes-from-hierarchical-partition-1-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-get-classes-from-hierarchical-partition-2'>
<p><a id='tab-get-classes-from-hierarchical-partition-2-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">get_classes(res_rh, merge_node = merge_node_param(min_n_signatures = 2995))
</code></pre>

<pre><code>#&gt; TCGA.AB.2888.03 TCGA.AB.2995.03 TCGA.AB.2884.03 TCGA.AB.2878.03 TCGA.AB.2998.03 TCGA.AB.2913.03 
#&gt;          &quot;0331&quot;          &quot;0213&quot;           &quot;013&quot;          &quot;0233&quot;          &quot;0321&quot;           &quot;012&quot; 
#&gt; TCGA.AB.2883.03 TCGA.AB.2957.03 TCGA.AB.2984.03 TCGA.AB.2837.03 TCGA.AB.2874.03 TCGA.AB.2836.03 
#&gt;          &quot;0212&quot;          &quot;0331&quot;          &quot;0221&quot;          &quot;0142&quot;          &quot;0221&quot;          &quot;0141&quot; 
#&gt; TCGA.AB.2876.03 TCGA.AB.2830.03 TCGA.AB.2823.03 TCGA.AB.2999.03 TCGA.AB.2940.03 TCGA.AB.2941.03 
#&gt;           &quot;031&quot;          &quot;0211&quot;          &quot;0324&quot;          &quot;0322&quot;           &quot;031&quot;          &quot;0213&quot; 
#&gt; TCGA.AB.2987.03 TCGA.AB.2945.03 TCGA.AB.2963.03 TCGA.AB.2967.03 TCGA.AB.2843.03 TCGA.AB.2807.03 
#&gt;          &quot;0212&quot;           &quot;013&quot;          &quot;0141&quot;          &quot;0141&quot;          &quot;0231&quot;          &quot;0233&quot; 
#&gt; TCGA.AB.3012.03 TCGA.AB.2971.03 TCGA.AB.2809.03 TCGA.AB.2873.03 TCGA.AB.2802.03 TCGA.AB.2851.03 
#&gt;          &quot;0323&quot;          &quot;0211&quot;          &quot;0112&quot;          &quot;0213&quot;          &quot;0111&quot;           &quot;013&quot; 
#&gt; TCGA.AB.2853.03 TCGA.AB.2847.03 TCGA.AB.2833.03 TCGA.AB.2814.03 TCGA.AB.2898.03 TCGA.AB.2866.03 
#&gt;          &quot;0111&quot;          &quot;0233&quot;          &quot;0213&quot;          &quot;0233&quot;          &quot;0211&quot;          &quot;0221&quot; 
#&gt; TCGA.AB.2875.03 TCGA.AB.2841.03 TCGA.AB.2922.03 TCGA.AB.3008.03 TCGA.AB.2968.03 TCGA.AB.2811.03 
#&gt;           &quot;034&quot;          &quot;0321&quot;          &quot;0231&quot;           &quot;031&quot;          &quot;0213&quot;          &quot;0111&quot; 
#&gt; TCGA.AB.2895.03 TCGA.AB.2933.03 TCGA.AB.2827.03 TCGA.AB.2942.03 TCGA.AB.2910.03 TCGA.AB.2934.03 
#&gt;          &quot;0112&quot;          &quot;0231&quot;          &quot;0141&quot;          &quot;0332&quot;          &quot;0212&quot;          &quot;0211&quot; 
#&gt; TCGA.AB.2959.03 TCGA.AB.2871.03 TCGA.AB.2907.03 TCGA.AB.2932.03 TCGA.AB.2824.03 TCGA.AB.2972.03 
#&gt;         &quot;02221&quot;         &quot;02222&quot;         &quot;02221&quot;          &quot;0141&quot;           &quot;013&quot;           &quot;013&quot; 
#&gt; TCGA.AB.2915.03 TCGA.AB.2970.03 TCGA.AB.2949.03 TCGA.AB.2912.03 TCGA.AB.2838.03 TCGA.AB.2872.03 
#&gt;          &quot;0231&quot;          &quot;0233&quot;          &quot;0231&quot;          &quot;0233&quot;          &quot;0233&quot;          &quot;0323&quot; 
#&gt; TCGA.AB.2897.03 TCGA.AB.2965.03 TCGA.AB.2891.03 TCGA.AB.2921.03 TCGA.AB.2867.03 TCGA.AB.2842.03 
#&gt;          &quot;0321&quot;          &quot;0111&quot;          &quot;0232&quot;           &quot;031&quot;         &quot;02221&quot;           &quot;013&quot; 
#&gt; TCGA.AB.2862.03 TCGA.AB.2840.03 TCGA.AB.2822.03 TCGA.AB.2832.03 TCGA.AB.2893.03 TCGA.AB.2956.03 
#&gt;          &quot;0321&quot;          &quot;0322&quot;         &quot;02221&quot;          &quot;0212&quot;          &quot;0212&quot;          &quot;0212&quot; 
#&gt; TCGA.AB.2903.03 TCGA.AB.2845.03 TCGA.AB.2948.03 TCGA.AB.2869.03 TCGA.AB.3009.03 TCGA.AB.2944.03 
#&gt;         &quot;02223&quot;           &quot;031&quot;         &quot;02222&quot;           &quot;013&quot;           &quot;031&quot;          &quot;0232&quot; 
#&gt; TCGA.AB.2886.03 TCGA.AB.2904.03 TCGA.AB.3005.03 TCGA.AB.2861.03 TCGA.AB.2917.03 TCGA.AB.2964.03 
#&gt;           &quot;034&quot;          &quot;0231&quot;          &quot;0212&quot;          &quot;0212&quot;          &quot;0233&quot;         &quot;02223&quot; 
#&gt; TCGA.AB.2955.03 TCGA.AB.2911.03 TCGA.AB.2892.03 TCGA.AB.2817.03 TCGA.AB.2906.03 TCGA.AB.2857.03 
#&gt;           &quot;031&quot;          &quot;0142&quot;          &quot;0332&quot;          &quot;0231&quot;          &quot;0322&quot;          &quot;0231&quot; 
#&gt; TCGA.AB.2805.03 TCGA.AB.2983.03 TCGA.AB.2918.03 TCGA.AB.2990.03 TCGA.AB.2937.03 TCGA.AB.3006.03 
#&gt;         &quot;02221&quot;          &quot;0231&quot;           &quot;012&quot;          &quot;0221&quot;           &quot;034&quot;           &quot;013&quot; 
#&gt; TCGA.AB.2829.03 TCGA.AB.2848.03 TCGA.AB.2914.03 TCGA.AB.3002.03 TCGA.AB.2877.03 TCGA.AB.2969.03 
#&gt;          &quot;0213&quot;          &quot;0141&quot;           &quot;034&quot;          &quot;0221&quot;          &quot;0221&quot;          &quot;0111&quot; 
#&gt; TCGA.AB.2839.03 TCGA.AB.2835.03 TCGA.AB.2974.03 TCGA.AB.2920.03 TCGA.AB.2980.03 TCGA.AB.2819.03 
#&gt;           &quot;012&quot;          &quot;0141&quot;          &quot;0112&quot;          &quot;0233&quot;          &quot;0325&quot;           &quot;034&quot; 
#&gt; TCGA.AB.2992.03 TCGA.AB.2919.03 TCGA.AB.2928.03 TCGA.AB.2927.03 TCGA.AB.2806.03 TCGA.AB.2885.03 
#&gt;         &quot;02221&quot;          &quot;0221&quot;          &quot;0211&quot;          &quot;0231&quot;           &quot;034&quot;          &quot;0231&quot; 
#&gt; TCGA.AB.2815.03 TCGA.AB.2996.03 TCGA.AB.2936.03 TCGA.AB.2939.03 TCGA.AB.2979.03 TCGA.AB.2986.03 
#&gt;          &quot;0331&quot;         &quot;02222&quot;         &quot;02221&quot;           &quot;031&quot;           &quot;031&quot;           &quot;012&quot; 
#&gt; TCGA.AB.2931.03 TCGA.AB.2896.03 TCGA.AB.2966.03 TCGA.AB.2820.03 TCGA.AB.2808.03 TCGA.AB.2991.03 
#&gt;          &quot;0111&quot;          &quot;0112&quot;          &quot;0232&quot;          &quot;0231&quot;           &quot;031&quot;          &quot;0324&quot; 
#&gt; TCGA.AB.2803.03 TCGA.AB.2900.03 TCGA.AB.2899.03 TCGA.AB.2812.03 TCGA.AB.3011.03 TCGA.AB.2946.03 
#&gt;          &quot;0321&quot;          &quot;0221&quot;          &quot;0233&quot;           &quot;012&quot;           &quot;013&quot;           &quot;012&quot; 
#&gt; TCGA.AB.3000.03 TCGA.AB.2997.03 TCGA.AB.3001.03 TCGA.AB.2926.03 TCGA.AB.2856.03 TCGA.AB.2977.03 
#&gt;           &quot;031&quot;          &quot;0324&quot;          &quot;0324&quot;          &quot;0221&quot;           &quot;012&quot;          &quot;0221&quot; 
#&gt; TCGA.AB.2879.03 TCGA.AB.2976.03 TCGA.AB.2989.03 TCGA.AB.2849.03 TCGA.AB.2981.03 TCGA.AB.2954.03 
#&gt;          &quot;0142&quot;          &quot;0141&quot;           &quot;012&quot;          &quot;0232&quot;          &quot;0112&quot;          &quot;0332&quot; 
#&gt; TCGA.AB.2973.03 TCGA.AB.2828.03 TCGA.AB.2804.03 TCGA.AB.2818.03 TCGA.AB.2930.03 TCGA.AB.2821.03 
#&gt;          &quot;0142&quot;          &quot;0331&quot;          &quot;0325&quot;          &quot;0142&quot;          &quot;0142&quot;         &quot;02221&quot; 
#&gt; TCGA.AB.2816.03 TCGA.AB.2863.03 TCGA.AB.2950.03 TCGA.AB.2925.03 TCGA.AB.3007.03 TCGA.AB.2882.03 
#&gt;           &quot;013&quot;         &quot;02221&quot;           &quot;034&quot;          &quot;0111&quot;          &quot;0323&quot;          &quot;0233&quot; 
#&gt; TCGA.AB.2825.03 TCGA.AB.2947.03 TCGA.AB.2916.03 TCGA.AB.2855.03 TCGA.AB.2978.03 TCGA.AB.2952.03 
#&gt;          &quot;0112&quot;          &quot;0111&quot;          &quot;0213&quot;          &quot;0221&quot;          &quot;0211&quot;          &quot;0233&quot; 
#&gt; TCGA.AB.2868.03 TCGA.AB.2908.03 TCGA.AB.2938.03 TCGA.AB.2923.03 TCGA.AB.2890.03 TCGA.AB.2988.03 
#&gt;          &quot;0231&quot;          &quot;0231&quot;          &quot;0213&quot;         &quot;02223&quot;          &quot;0231&quot;           &quot;013&quot; 
#&gt; TCGA.AB.2985.03 TCGA.AB.2880.03 TCGA.AB.2889.03 TCGA.AB.2887.03 TCGA.AB.2881.03 TCGA.AB.2834.03 
#&gt;           &quot;013&quot;           &quot;031&quot;          &quot;0331&quot;          &quot;0211&quot;          &quot;0332&quot;          &quot;0221&quot; 
#&gt; TCGA.AB.2943.03 TCGA.AB.2982.03 TCGA.AB.2844.03 TCGA.AB.2870.03 TCGA.AB.2813.03 TCGA.AB.2894.03 
#&gt;          &quot;0231&quot;          &quot;0321&quot;           &quot;012&quot;          &quot;0331&quot;          &quot;0231&quot;          &quot;0212&quot; 
#&gt; TCGA.AB.2909.03 TCGA.AB.2858.03 TCGA.AB.2935.03 TCGA.AB.2929.03 TCGA.AB.2831.03 TCGA.AB.2826.03 
#&gt;           &quot;034&quot;          &quot;0332&quot;          &quot;0231&quot;          &quot;0233&quot;          &quot;0211&quot;          &quot;0221&quot; 
#&gt; TCGA.AB.2993.03 TCGA.AB.2810.03 TCGA.AB.2924.03 TCGA.AB.2901.03 TCGA.AB.2975.03 TCGA.AB.2860.03 
#&gt;          &quot;0142&quot;          &quot;0221&quot;          &quot;0141&quot;         &quot;02221&quot;          &quot;0211&quot;          &quot;0233&quot; 
#&gt; TCGA.AB.2854.03 TCGA.AB.2846.03 
#&gt;         &quot;02222&quot;          &quot;0332&quot;
</code></pre>

<script>
$('#tab-get-classes-from-hierarchical-partition-2-a').parent().next().next().hide();
$('#tab-get-classes-from-hierarchical-partition-2-a').click(function(){
  $('#tab-get-classes-from-hierarchical-partition-2-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-get-classes-from-hierarchical-partition-3'>
<p><a id='tab-get-classes-from-hierarchical-partition-3-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">get_classes(res_rh, merge_node = merge_node_param(min_n_signatures = 3376))
</code></pre>

<pre><code>#&gt; TCGA.AB.2888.03 TCGA.AB.2995.03 TCGA.AB.2884.03 TCGA.AB.2878.03 TCGA.AB.2998.03 TCGA.AB.2913.03 
#&gt;          &quot;0331&quot;          &quot;0213&quot;           &quot;013&quot;          &quot;0233&quot;          &quot;0321&quot;           &quot;012&quot; 
#&gt; TCGA.AB.2883.03 TCGA.AB.2957.03 TCGA.AB.2984.03 TCGA.AB.2837.03 TCGA.AB.2874.03 TCGA.AB.2836.03 
#&gt;          &quot;0212&quot;          &quot;0331&quot;          &quot;0221&quot;          &quot;0142&quot;          &quot;0221&quot;          &quot;0141&quot; 
#&gt; TCGA.AB.2876.03 TCGA.AB.2830.03 TCGA.AB.2823.03 TCGA.AB.2999.03 TCGA.AB.2940.03 TCGA.AB.2941.03 
#&gt;           &quot;031&quot;          &quot;0211&quot;          &quot;0324&quot;          &quot;0322&quot;           &quot;031&quot;          &quot;0213&quot; 
#&gt; TCGA.AB.2987.03 TCGA.AB.2945.03 TCGA.AB.2963.03 TCGA.AB.2967.03 TCGA.AB.2843.03 TCGA.AB.2807.03 
#&gt;          &quot;0212&quot;           &quot;013&quot;          &quot;0141&quot;          &quot;0141&quot;          &quot;0231&quot;          &quot;0233&quot; 
#&gt; TCGA.AB.3012.03 TCGA.AB.2971.03 TCGA.AB.2809.03 TCGA.AB.2873.03 TCGA.AB.2802.03 TCGA.AB.2851.03 
#&gt;          &quot;0323&quot;          &quot;0211&quot;          &quot;0112&quot;          &quot;0213&quot;          &quot;0111&quot;           &quot;013&quot; 
#&gt; TCGA.AB.2853.03 TCGA.AB.2847.03 TCGA.AB.2833.03 TCGA.AB.2814.03 TCGA.AB.2898.03 TCGA.AB.2866.03 
#&gt;          &quot;0111&quot;          &quot;0233&quot;          &quot;0213&quot;          &quot;0233&quot;          &quot;0211&quot;          &quot;0221&quot; 
#&gt; TCGA.AB.2875.03 TCGA.AB.2841.03 TCGA.AB.2922.03 TCGA.AB.3008.03 TCGA.AB.2968.03 TCGA.AB.2811.03 
#&gt;           &quot;034&quot;          &quot;0321&quot;          &quot;0231&quot;           &quot;031&quot;          &quot;0213&quot;          &quot;0111&quot; 
#&gt; TCGA.AB.2895.03 TCGA.AB.2933.03 TCGA.AB.2827.03 TCGA.AB.2942.03 TCGA.AB.2910.03 TCGA.AB.2934.03 
#&gt;          &quot;0112&quot;          &quot;0231&quot;          &quot;0141&quot;          &quot;0332&quot;          &quot;0212&quot;          &quot;0211&quot; 
#&gt; TCGA.AB.2959.03 TCGA.AB.2871.03 TCGA.AB.2907.03 TCGA.AB.2932.03 TCGA.AB.2824.03 TCGA.AB.2972.03 
#&gt;          &quot;0222&quot;          &quot;0222&quot;          &quot;0222&quot;          &quot;0141&quot;           &quot;013&quot;           &quot;013&quot; 
#&gt; TCGA.AB.2915.03 TCGA.AB.2970.03 TCGA.AB.2949.03 TCGA.AB.2912.03 TCGA.AB.2838.03 TCGA.AB.2872.03 
#&gt;          &quot;0231&quot;          &quot;0233&quot;          &quot;0231&quot;          &quot;0233&quot;          &quot;0233&quot;          &quot;0323&quot; 
#&gt; TCGA.AB.2897.03 TCGA.AB.2965.03 TCGA.AB.2891.03 TCGA.AB.2921.03 TCGA.AB.2867.03 TCGA.AB.2842.03 
#&gt;          &quot;0321&quot;          &quot;0111&quot;          &quot;0232&quot;           &quot;031&quot;          &quot;0222&quot;           &quot;013&quot; 
#&gt; TCGA.AB.2862.03 TCGA.AB.2840.03 TCGA.AB.2822.03 TCGA.AB.2832.03 TCGA.AB.2893.03 TCGA.AB.2956.03 
#&gt;          &quot;0321&quot;          &quot;0322&quot;          &quot;0222&quot;          &quot;0212&quot;          &quot;0212&quot;          &quot;0212&quot; 
#&gt; TCGA.AB.2903.03 TCGA.AB.2845.03 TCGA.AB.2948.03 TCGA.AB.2869.03 TCGA.AB.3009.03 TCGA.AB.2944.03 
#&gt;          &quot;0222&quot;           &quot;031&quot;          &quot;0222&quot;           &quot;013&quot;           &quot;031&quot;          &quot;0232&quot; 
#&gt; TCGA.AB.2886.03 TCGA.AB.2904.03 TCGA.AB.3005.03 TCGA.AB.2861.03 TCGA.AB.2917.03 TCGA.AB.2964.03 
#&gt;           &quot;034&quot;          &quot;0231&quot;          &quot;0212&quot;          &quot;0212&quot;          &quot;0233&quot;          &quot;0222&quot; 
#&gt; TCGA.AB.2955.03 TCGA.AB.2911.03 TCGA.AB.2892.03 TCGA.AB.2817.03 TCGA.AB.2906.03 TCGA.AB.2857.03 
#&gt;           &quot;031&quot;          &quot;0142&quot;          &quot;0332&quot;          &quot;0231&quot;          &quot;0322&quot;          &quot;0231&quot; 
#&gt; TCGA.AB.2805.03 TCGA.AB.2983.03 TCGA.AB.2918.03 TCGA.AB.2990.03 TCGA.AB.2937.03 TCGA.AB.3006.03 
#&gt;          &quot;0222&quot;          &quot;0231&quot;           &quot;012&quot;          &quot;0221&quot;           &quot;034&quot;           &quot;013&quot; 
#&gt; TCGA.AB.2829.03 TCGA.AB.2848.03 TCGA.AB.2914.03 TCGA.AB.3002.03 TCGA.AB.2877.03 TCGA.AB.2969.03 
#&gt;          &quot;0213&quot;          &quot;0141&quot;           &quot;034&quot;          &quot;0221&quot;          &quot;0221&quot;          &quot;0111&quot; 
#&gt; TCGA.AB.2839.03 TCGA.AB.2835.03 TCGA.AB.2974.03 TCGA.AB.2920.03 TCGA.AB.2980.03 TCGA.AB.2819.03 
#&gt;           &quot;012&quot;          &quot;0141&quot;          &quot;0112&quot;          &quot;0233&quot;          &quot;0325&quot;           &quot;034&quot; 
#&gt; TCGA.AB.2992.03 TCGA.AB.2919.03 TCGA.AB.2928.03 TCGA.AB.2927.03 TCGA.AB.2806.03 TCGA.AB.2885.03 
#&gt;          &quot;0222&quot;          &quot;0221&quot;          &quot;0211&quot;          &quot;0231&quot;           &quot;034&quot;          &quot;0231&quot; 
#&gt; TCGA.AB.2815.03 TCGA.AB.2996.03 TCGA.AB.2936.03 TCGA.AB.2939.03 TCGA.AB.2979.03 TCGA.AB.2986.03 
#&gt;          &quot;0331&quot;          &quot;0222&quot;          &quot;0222&quot;           &quot;031&quot;           &quot;031&quot;           &quot;012&quot; 
#&gt; TCGA.AB.2931.03 TCGA.AB.2896.03 TCGA.AB.2966.03 TCGA.AB.2820.03 TCGA.AB.2808.03 TCGA.AB.2991.03 
#&gt;          &quot;0111&quot;          &quot;0112&quot;          &quot;0232&quot;          &quot;0231&quot;           &quot;031&quot;          &quot;0324&quot; 
#&gt; TCGA.AB.2803.03 TCGA.AB.2900.03 TCGA.AB.2899.03 TCGA.AB.2812.03 TCGA.AB.3011.03 TCGA.AB.2946.03 
#&gt;          &quot;0321&quot;          &quot;0221&quot;          &quot;0233&quot;           &quot;012&quot;           &quot;013&quot;           &quot;012&quot; 
#&gt; TCGA.AB.3000.03 TCGA.AB.2997.03 TCGA.AB.3001.03 TCGA.AB.2926.03 TCGA.AB.2856.03 TCGA.AB.2977.03 
#&gt;           &quot;031&quot;          &quot;0324&quot;          &quot;0324&quot;          &quot;0221&quot;           &quot;012&quot;          &quot;0221&quot; 
#&gt; TCGA.AB.2879.03 TCGA.AB.2976.03 TCGA.AB.2989.03 TCGA.AB.2849.03 TCGA.AB.2981.03 TCGA.AB.2954.03 
#&gt;          &quot;0142&quot;          &quot;0141&quot;           &quot;012&quot;          &quot;0232&quot;          &quot;0112&quot;          &quot;0332&quot; 
#&gt; TCGA.AB.2973.03 TCGA.AB.2828.03 TCGA.AB.2804.03 TCGA.AB.2818.03 TCGA.AB.2930.03 TCGA.AB.2821.03 
#&gt;          &quot;0142&quot;          &quot;0331&quot;          &quot;0325&quot;          &quot;0142&quot;          &quot;0142&quot;          &quot;0222&quot; 
#&gt; TCGA.AB.2816.03 TCGA.AB.2863.03 TCGA.AB.2950.03 TCGA.AB.2925.03 TCGA.AB.3007.03 TCGA.AB.2882.03 
#&gt;           &quot;013&quot;          &quot;0222&quot;           &quot;034&quot;          &quot;0111&quot;          &quot;0323&quot;          &quot;0233&quot; 
#&gt; TCGA.AB.2825.03 TCGA.AB.2947.03 TCGA.AB.2916.03 TCGA.AB.2855.03 TCGA.AB.2978.03 TCGA.AB.2952.03 
#&gt;          &quot;0112&quot;          &quot;0111&quot;          &quot;0213&quot;          &quot;0221&quot;          &quot;0211&quot;          &quot;0233&quot; 
#&gt; TCGA.AB.2868.03 TCGA.AB.2908.03 TCGA.AB.2938.03 TCGA.AB.2923.03 TCGA.AB.2890.03 TCGA.AB.2988.03 
#&gt;          &quot;0231&quot;          &quot;0231&quot;          &quot;0213&quot;          &quot;0222&quot;          &quot;0231&quot;           &quot;013&quot; 
#&gt; TCGA.AB.2985.03 TCGA.AB.2880.03 TCGA.AB.2889.03 TCGA.AB.2887.03 TCGA.AB.2881.03 TCGA.AB.2834.03 
#&gt;           &quot;013&quot;           &quot;031&quot;          &quot;0331&quot;          &quot;0211&quot;          &quot;0332&quot;          &quot;0221&quot; 
#&gt; TCGA.AB.2943.03 TCGA.AB.2982.03 TCGA.AB.2844.03 TCGA.AB.2870.03 TCGA.AB.2813.03 TCGA.AB.2894.03 
#&gt;          &quot;0231&quot;          &quot;0321&quot;           &quot;012&quot;          &quot;0331&quot;          &quot;0231&quot;          &quot;0212&quot; 
#&gt; TCGA.AB.2909.03 TCGA.AB.2858.03 TCGA.AB.2935.03 TCGA.AB.2929.03 TCGA.AB.2831.03 TCGA.AB.2826.03 
#&gt;           &quot;034&quot;          &quot;0332&quot;          &quot;0231&quot;          &quot;0233&quot;          &quot;0211&quot;          &quot;0221&quot; 
#&gt; TCGA.AB.2993.03 TCGA.AB.2810.03 TCGA.AB.2924.03 TCGA.AB.2901.03 TCGA.AB.2975.03 TCGA.AB.2860.03 
#&gt;          &quot;0142&quot;          &quot;0221&quot;          &quot;0141&quot;          &quot;0222&quot;          &quot;0211&quot;          &quot;0233&quot; 
#&gt; TCGA.AB.2854.03 TCGA.AB.2846.03 
#&gt;          &quot;0222&quot;          &quot;0332&quot;
</code></pre>

<script>
$('#tab-get-classes-from-hierarchical-partition-3-a').parent().next().next().hide();
$('#tab-get-classes-from-hierarchical-partition-3-a').click(function(){
  $('#tab-get-classes-from-hierarchical-partition-3-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-get-classes-from-hierarchical-partition-4'>
<p><a id='tab-get-classes-from-hierarchical-partition-4-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">get_classes(res_rh, merge_node = merge_node_param(min_n_signatures = 3533))
</code></pre>

<pre><code>#&gt; TCGA.AB.2888.03 TCGA.AB.2995.03 TCGA.AB.2884.03 TCGA.AB.2878.03 TCGA.AB.2998.03 TCGA.AB.2913.03 
#&gt;           &quot;033&quot;          &quot;0213&quot;           &quot;013&quot;          &quot;0233&quot;          &quot;0321&quot;           &quot;012&quot; 
#&gt; TCGA.AB.2883.03 TCGA.AB.2957.03 TCGA.AB.2984.03 TCGA.AB.2837.03 TCGA.AB.2874.03 TCGA.AB.2836.03 
#&gt;          &quot;0212&quot;           &quot;033&quot;          &quot;0221&quot;          &quot;0142&quot;          &quot;0221&quot;          &quot;0141&quot; 
#&gt; TCGA.AB.2876.03 TCGA.AB.2830.03 TCGA.AB.2823.03 TCGA.AB.2999.03 TCGA.AB.2940.03 TCGA.AB.2941.03 
#&gt;           &quot;031&quot;          &quot;0211&quot;          &quot;0324&quot;          &quot;0322&quot;           &quot;031&quot;          &quot;0213&quot; 
#&gt; TCGA.AB.2987.03 TCGA.AB.2945.03 TCGA.AB.2963.03 TCGA.AB.2967.03 TCGA.AB.2843.03 TCGA.AB.2807.03 
#&gt;          &quot;0212&quot;           &quot;013&quot;          &quot;0141&quot;          &quot;0141&quot;          &quot;0231&quot;          &quot;0233&quot; 
#&gt; TCGA.AB.3012.03 TCGA.AB.2971.03 TCGA.AB.2809.03 TCGA.AB.2873.03 TCGA.AB.2802.03 TCGA.AB.2851.03 
#&gt;          &quot;0323&quot;          &quot;0211&quot;          &quot;0112&quot;          &quot;0213&quot;          &quot;0111&quot;           &quot;013&quot; 
#&gt; TCGA.AB.2853.03 TCGA.AB.2847.03 TCGA.AB.2833.03 TCGA.AB.2814.03 TCGA.AB.2898.03 TCGA.AB.2866.03 
#&gt;          &quot;0111&quot;          &quot;0233&quot;          &quot;0213&quot;          &quot;0233&quot;          &quot;0211&quot;          &quot;0221&quot; 
#&gt; TCGA.AB.2875.03 TCGA.AB.2841.03 TCGA.AB.2922.03 TCGA.AB.3008.03 TCGA.AB.2968.03 TCGA.AB.2811.03 
#&gt;           &quot;034&quot;          &quot;0321&quot;          &quot;0231&quot;           &quot;031&quot;          &quot;0213&quot;          &quot;0111&quot; 
#&gt; TCGA.AB.2895.03 TCGA.AB.2933.03 TCGA.AB.2827.03 TCGA.AB.2942.03 TCGA.AB.2910.03 TCGA.AB.2934.03 
#&gt;          &quot;0112&quot;          &quot;0231&quot;          &quot;0141&quot;           &quot;033&quot;          &quot;0212&quot;          &quot;0211&quot; 
#&gt; TCGA.AB.2959.03 TCGA.AB.2871.03 TCGA.AB.2907.03 TCGA.AB.2932.03 TCGA.AB.2824.03 TCGA.AB.2972.03 
#&gt;          &quot;0222&quot;          &quot;0222&quot;          &quot;0222&quot;          &quot;0141&quot;           &quot;013&quot;           &quot;013&quot; 
#&gt; TCGA.AB.2915.03 TCGA.AB.2970.03 TCGA.AB.2949.03 TCGA.AB.2912.03 TCGA.AB.2838.03 TCGA.AB.2872.03 
#&gt;          &quot;0231&quot;          &quot;0233&quot;          &quot;0231&quot;          &quot;0233&quot;          &quot;0233&quot;          &quot;0323&quot; 
#&gt; TCGA.AB.2897.03 TCGA.AB.2965.03 TCGA.AB.2891.03 TCGA.AB.2921.03 TCGA.AB.2867.03 TCGA.AB.2842.03 
#&gt;          &quot;0321&quot;          &quot;0111&quot;          &quot;0232&quot;           &quot;031&quot;          &quot;0222&quot;           &quot;013&quot; 
#&gt; TCGA.AB.2862.03 TCGA.AB.2840.03 TCGA.AB.2822.03 TCGA.AB.2832.03 TCGA.AB.2893.03 TCGA.AB.2956.03 
#&gt;          &quot;0321&quot;          &quot;0322&quot;          &quot;0222&quot;          &quot;0212&quot;          &quot;0212&quot;          &quot;0212&quot; 
#&gt; TCGA.AB.2903.03 TCGA.AB.2845.03 TCGA.AB.2948.03 TCGA.AB.2869.03 TCGA.AB.3009.03 TCGA.AB.2944.03 
#&gt;          &quot;0222&quot;           &quot;031&quot;          &quot;0222&quot;           &quot;013&quot;           &quot;031&quot;          &quot;0232&quot; 
#&gt; TCGA.AB.2886.03 TCGA.AB.2904.03 TCGA.AB.3005.03 TCGA.AB.2861.03 TCGA.AB.2917.03 TCGA.AB.2964.03 
#&gt;           &quot;034&quot;          &quot;0231&quot;          &quot;0212&quot;          &quot;0212&quot;          &quot;0233&quot;          &quot;0222&quot; 
#&gt; TCGA.AB.2955.03 TCGA.AB.2911.03 TCGA.AB.2892.03 TCGA.AB.2817.03 TCGA.AB.2906.03 TCGA.AB.2857.03 
#&gt;           &quot;031&quot;          &quot;0142&quot;           &quot;033&quot;          &quot;0231&quot;          &quot;0322&quot;          &quot;0231&quot; 
#&gt; TCGA.AB.2805.03 TCGA.AB.2983.03 TCGA.AB.2918.03 TCGA.AB.2990.03 TCGA.AB.2937.03 TCGA.AB.3006.03 
#&gt;          &quot;0222&quot;          &quot;0231&quot;           &quot;012&quot;          &quot;0221&quot;           &quot;034&quot;           &quot;013&quot; 
#&gt; TCGA.AB.2829.03 TCGA.AB.2848.03 TCGA.AB.2914.03 TCGA.AB.3002.03 TCGA.AB.2877.03 TCGA.AB.2969.03 
#&gt;          &quot;0213&quot;          &quot;0141&quot;           &quot;034&quot;          &quot;0221&quot;          &quot;0221&quot;          &quot;0111&quot; 
#&gt; TCGA.AB.2839.03 TCGA.AB.2835.03 TCGA.AB.2974.03 TCGA.AB.2920.03 TCGA.AB.2980.03 TCGA.AB.2819.03 
#&gt;           &quot;012&quot;          &quot;0141&quot;          &quot;0112&quot;          &quot;0233&quot;          &quot;0325&quot;           &quot;034&quot; 
#&gt; TCGA.AB.2992.03 TCGA.AB.2919.03 TCGA.AB.2928.03 TCGA.AB.2927.03 TCGA.AB.2806.03 TCGA.AB.2885.03 
#&gt;          &quot;0222&quot;          &quot;0221&quot;          &quot;0211&quot;          &quot;0231&quot;           &quot;034&quot;          &quot;0231&quot; 
#&gt; TCGA.AB.2815.03 TCGA.AB.2996.03 TCGA.AB.2936.03 TCGA.AB.2939.03 TCGA.AB.2979.03 TCGA.AB.2986.03 
#&gt;           &quot;033&quot;          &quot;0222&quot;          &quot;0222&quot;           &quot;031&quot;           &quot;031&quot;           &quot;012&quot; 
#&gt; TCGA.AB.2931.03 TCGA.AB.2896.03 TCGA.AB.2966.03 TCGA.AB.2820.03 TCGA.AB.2808.03 TCGA.AB.2991.03 
#&gt;          &quot;0111&quot;          &quot;0112&quot;          &quot;0232&quot;          &quot;0231&quot;           &quot;031&quot;          &quot;0324&quot; 
#&gt; TCGA.AB.2803.03 TCGA.AB.2900.03 TCGA.AB.2899.03 TCGA.AB.2812.03 TCGA.AB.3011.03 TCGA.AB.2946.03 
#&gt;          &quot;0321&quot;          &quot;0221&quot;          &quot;0233&quot;           &quot;012&quot;           &quot;013&quot;           &quot;012&quot; 
#&gt; TCGA.AB.3000.03 TCGA.AB.2997.03 TCGA.AB.3001.03 TCGA.AB.2926.03 TCGA.AB.2856.03 TCGA.AB.2977.03 
#&gt;           &quot;031&quot;          &quot;0324&quot;          &quot;0324&quot;          &quot;0221&quot;           &quot;012&quot;          &quot;0221&quot; 
#&gt; TCGA.AB.2879.03 TCGA.AB.2976.03 TCGA.AB.2989.03 TCGA.AB.2849.03 TCGA.AB.2981.03 TCGA.AB.2954.03 
#&gt;          &quot;0142&quot;          &quot;0141&quot;           &quot;012&quot;          &quot;0232&quot;          &quot;0112&quot;           &quot;033&quot; 
#&gt; TCGA.AB.2973.03 TCGA.AB.2828.03 TCGA.AB.2804.03 TCGA.AB.2818.03 TCGA.AB.2930.03 TCGA.AB.2821.03 
#&gt;          &quot;0142&quot;           &quot;033&quot;          &quot;0325&quot;          &quot;0142&quot;          &quot;0142&quot;          &quot;0222&quot; 
#&gt; TCGA.AB.2816.03 TCGA.AB.2863.03 TCGA.AB.2950.03 TCGA.AB.2925.03 TCGA.AB.3007.03 TCGA.AB.2882.03 
#&gt;           &quot;013&quot;          &quot;0222&quot;           &quot;034&quot;          &quot;0111&quot;          &quot;0323&quot;          &quot;0233&quot; 
#&gt; TCGA.AB.2825.03 TCGA.AB.2947.03 TCGA.AB.2916.03 TCGA.AB.2855.03 TCGA.AB.2978.03 TCGA.AB.2952.03 
#&gt;          &quot;0112&quot;          &quot;0111&quot;          &quot;0213&quot;          &quot;0221&quot;          &quot;0211&quot;          &quot;0233&quot; 
#&gt; TCGA.AB.2868.03 TCGA.AB.2908.03 TCGA.AB.2938.03 TCGA.AB.2923.03 TCGA.AB.2890.03 TCGA.AB.2988.03 
#&gt;          &quot;0231&quot;          &quot;0231&quot;          &quot;0213&quot;          &quot;0222&quot;          &quot;0231&quot;           &quot;013&quot; 
#&gt; TCGA.AB.2985.03 TCGA.AB.2880.03 TCGA.AB.2889.03 TCGA.AB.2887.03 TCGA.AB.2881.03 TCGA.AB.2834.03 
#&gt;           &quot;013&quot;           &quot;031&quot;           &quot;033&quot;          &quot;0211&quot;           &quot;033&quot;          &quot;0221&quot; 
#&gt; TCGA.AB.2943.03 TCGA.AB.2982.03 TCGA.AB.2844.03 TCGA.AB.2870.03 TCGA.AB.2813.03 TCGA.AB.2894.03 
#&gt;          &quot;0231&quot;          &quot;0321&quot;           &quot;012&quot;           &quot;033&quot;          &quot;0231&quot;          &quot;0212&quot; 
#&gt; TCGA.AB.2909.03 TCGA.AB.2858.03 TCGA.AB.2935.03 TCGA.AB.2929.03 TCGA.AB.2831.03 TCGA.AB.2826.03 
#&gt;           &quot;034&quot;           &quot;033&quot;          &quot;0231&quot;          &quot;0233&quot;          &quot;0211&quot;          &quot;0221&quot; 
#&gt; TCGA.AB.2993.03 TCGA.AB.2810.03 TCGA.AB.2924.03 TCGA.AB.2901.03 TCGA.AB.2975.03 TCGA.AB.2860.03 
#&gt;          &quot;0142&quot;          &quot;0221&quot;          &quot;0141&quot;          &quot;0222&quot;          &quot;0211&quot;          &quot;0233&quot; 
#&gt; TCGA.AB.2854.03 TCGA.AB.2846.03 
#&gt;          &quot;0222&quot;           &quot;033&quot;
</code></pre>

<script>
$('#tab-get-classes-from-hierarchical-partition-4-a').parent().next().next().hide();
$('#tab-get-classes-from-hierarchical-partition-4-a').click(function(){
  $('#tab-get-classes-from-hierarchical-partition-4-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-get-classes-from-hierarchical-partition-5'>
<p><a id='tab-get-classes-from-hierarchical-partition-5-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">get_classes(res_rh, merge_node = merge_node_param(min_n_signatures = 3565))
</code></pre>

<pre><code>#&gt; TCGA.AB.2888.03 TCGA.AB.2995.03 TCGA.AB.2884.03 TCGA.AB.2878.03 TCGA.AB.2998.03 TCGA.AB.2913.03 
#&gt;           &quot;033&quot;          &quot;0213&quot;           &quot;013&quot;          &quot;0233&quot;          &quot;0321&quot;           &quot;012&quot; 
#&gt; TCGA.AB.2883.03 TCGA.AB.2957.03 TCGA.AB.2984.03 TCGA.AB.2837.03 TCGA.AB.2874.03 TCGA.AB.2836.03 
#&gt;          &quot;0212&quot;           &quot;033&quot;          &quot;0221&quot;          &quot;0142&quot;          &quot;0221&quot;          &quot;0141&quot; 
#&gt; TCGA.AB.2876.03 TCGA.AB.2830.03 TCGA.AB.2823.03 TCGA.AB.2999.03 TCGA.AB.2940.03 TCGA.AB.2941.03 
#&gt;           &quot;031&quot;          &quot;0211&quot;          &quot;0324&quot;          &quot;0322&quot;           &quot;031&quot;          &quot;0213&quot; 
#&gt; TCGA.AB.2987.03 TCGA.AB.2945.03 TCGA.AB.2963.03 TCGA.AB.2967.03 TCGA.AB.2843.03 TCGA.AB.2807.03 
#&gt;          &quot;0212&quot;           &quot;013&quot;          &quot;0141&quot;          &quot;0141&quot;          &quot;0231&quot;          &quot;0233&quot; 
#&gt; TCGA.AB.3012.03 TCGA.AB.2971.03 TCGA.AB.2809.03 TCGA.AB.2873.03 TCGA.AB.2802.03 TCGA.AB.2851.03 
#&gt;          &quot;0323&quot;          &quot;0211&quot;           &quot;011&quot;          &quot;0213&quot;           &quot;011&quot;           &quot;013&quot; 
#&gt; TCGA.AB.2853.03 TCGA.AB.2847.03 TCGA.AB.2833.03 TCGA.AB.2814.03 TCGA.AB.2898.03 TCGA.AB.2866.03 
#&gt;           &quot;011&quot;          &quot;0233&quot;          &quot;0213&quot;          &quot;0233&quot;          &quot;0211&quot;          &quot;0221&quot; 
#&gt; TCGA.AB.2875.03 TCGA.AB.2841.03 TCGA.AB.2922.03 TCGA.AB.3008.03 TCGA.AB.2968.03 TCGA.AB.2811.03 
#&gt;           &quot;034&quot;          &quot;0321&quot;          &quot;0231&quot;           &quot;031&quot;          &quot;0213&quot;           &quot;011&quot; 
#&gt; TCGA.AB.2895.03 TCGA.AB.2933.03 TCGA.AB.2827.03 TCGA.AB.2942.03 TCGA.AB.2910.03 TCGA.AB.2934.03 
#&gt;           &quot;011&quot;          &quot;0231&quot;          &quot;0141&quot;           &quot;033&quot;          &quot;0212&quot;          &quot;0211&quot; 
#&gt; TCGA.AB.2959.03 TCGA.AB.2871.03 TCGA.AB.2907.03 TCGA.AB.2932.03 TCGA.AB.2824.03 TCGA.AB.2972.03 
#&gt;          &quot;0222&quot;          &quot;0222&quot;          &quot;0222&quot;          &quot;0141&quot;           &quot;013&quot;           &quot;013&quot; 
#&gt; TCGA.AB.2915.03 TCGA.AB.2970.03 TCGA.AB.2949.03 TCGA.AB.2912.03 TCGA.AB.2838.03 TCGA.AB.2872.03 
#&gt;          &quot;0231&quot;          &quot;0233&quot;          &quot;0231&quot;          &quot;0233&quot;          &quot;0233&quot;          &quot;0323&quot; 
#&gt; TCGA.AB.2897.03 TCGA.AB.2965.03 TCGA.AB.2891.03 TCGA.AB.2921.03 TCGA.AB.2867.03 TCGA.AB.2842.03 
#&gt;          &quot;0321&quot;           &quot;011&quot;          &quot;0232&quot;           &quot;031&quot;          &quot;0222&quot;           &quot;013&quot; 
#&gt; TCGA.AB.2862.03 TCGA.AB.2840.03 TCGA.AB.2822.03 TCGA.AB.2832.03 TCGA.AB.2893.03 TCGA.AB.2956.03 
#&gt;          &quot;0321&quot;          &quot;0322&quot;          &quot;0222&quot;          &quot;0212&quot;          &quot;0212&quot;          &quot;0212&quot; 
#&gt; TCGA.AB.2903.03 TCGA.AB.2845.03 TCGA.AB.2948.03 TCGA.AB.2869.03 TCGA.AB.3009.03 TCGA.AB.2944.03 
#&gt;          &quot;0222&quot;           &quot;031&quot;          &quot;0222&quot;           &quot;013&quot;           &quot;031&quot;          &quot;0232&quot; 
#&gt; TCGA.AB.2886.03 TCGA.AB.2904.03 TCGA.AB.3005.03 TCGA.AB.2861.03 TCGA.AB.2917.03 TCGA.AB.2964.03 
#&gt;           &quot;034&quot;          &quot;0231&quot;          &quot;0212&quot;          &quot;0212&quot;          &quot;0233&quot;          &quot;0222&quot; 
#&gt; TCGA.AB.2955.03 TCGA.AB.2911.03 TCGA.AB.2892.03 TCGA.AB.2817.03 TCGA.AB.2906.03 TCGA.AB.2857.03 
#&gt;           &quot;031&quot;          &quot;0142&quot;           &quot;033&quot;          &quot;0231&quot;          &quot;0322&quot;          &quot;0231&quot; 
#&gt; TCGA.AB.2805.03 TCGA.AB.2983.03 TCGA.AB.2918.03 TCGA.AB.2990.03 TCGA.AB.2937.03 TCGA.AB.3006.03 
#&gt;          &quot;0222&quot;          &quot;0231&quot;           &quot;012&quot;          &quot;0221&quot;           &quot;034&quot;           &quot;013&quot; 
#&gt; TCGA.AB.2829.03 TCGA.AB.2848.03 TCGA.AB.2914.03 TCGA.AB.3002.03 TCGA.AB.2877.03 TCGA.AB.2969.03 
#&gt;          &quot;0213&quot;          &quot;0141&quot;           &quot;034&quot;          &quot;0221&quot;          &quot;0221&quot;           &quot;011&quot; 
#&gt; TCGA.AB.2839.03 TCGA.AB.2835.03 TCGA.AB.2974.03 TCGA.AB.2920.03 TCGA.AB.2980.03 TCGA.AB.2819.03 
#&gt;           &quot;012&quot;          &quot;0141&quot;           &quot;011&quot;          &quot;0233&quot;          &quot;0325&quot;           &quot;034&quot; 
#&gt; TCGA.AB.2992.03 TCGA.AB.2919.03 TCGA.AB.2928.03 TCGA.AB.2927.03 TCGA.AB.2806.03 TCGA.AB.2885.03 
#&gt;          &quot;0222&quot;          &quot;0221&quot;          &quot;0211&quot;          &quot;0231&quot;           &quot;034&quot;          &quot;0231&quot; 
#&gt; TCGA.AB.2815.03 TCGA.AB.2996.03 TCGA.AB.2936.03 TCGA.AB.2939.03 TCGA.AB.2979.03 TCGA.AB.2986.03 
#&gt;           &quot;033&quot;          &quot;0222&quot;          &quot;0222&quot;           &quot;031&quot;           &quot;031&quot;           &quot;012&quot; 
#&gt; TCGA.AB.2931.03 TCGA.AB.2896.03 TCGA.AB.2966.03 TCGA.AB.2820.03 TCGA.AB.2808.03 TCGA.AB.2991.03 
#&gt;           &quot;011&quot;           &quot;011&quot;          &quot;0232&quot;          &quot;0231&quot;           &quot;031&quot;          &quot;0324&quot; 
#&gt; TCGA.AB.2803.03 TCGA.AB.2900.03 TCGA.AB.2899.03 TCGA.AB.2812.03 TCGA.AB.3011.03 TCGA.AB.2946.03 
#&gt;          &quot;0321&quot;          &quot;0221&quot;          &quot;0233&quot;           &quot;012&quot;           &quot;013&quot;           &quot;012&quot; 
#&gt; TCGA.AB.3000.03 TCGA.AB.2997.03 TCGA.AB.3001.03 TCGA.AB.2926.03 TCGA.AB.2856.03 TCGA.AB.2977.03 
#&gt;           &quot;031&quot;          &quot;0324&quot;          &quot;0324&quot;          &quot;0221&quot;           &quot;012&quot;          &quot;0221&quot; 
#&gt; TCGA.AB.2879.03 TCGA.AB.2976.03 TCGA.AB.2989.03 TCGA.AB.2849.03 TCGA.AB.2981.03 TCGA.AB.2954.03 
#&gt;          &quot;0142&quot;          &quot;0141&quot;           &quot;012&quot;          &quot;0232&quot;           &quot;011&quot;           &quot;033&quot; 
#&gt; TCGA.AB.2973.03 TCGA.AB.2828.03 TCGA.AB.2804.03 TCGA.AB.2818.03 TCGA.AB.2930.03 TCGA.AB.2821.03 
#&gt;          &quot;0142&quot;           &quot;033&quot;          &quot;0325&quot;          &quot;0142&quot;          &quot;0142&quot;          &quot;0222&quot; 
#&gt; TCGA.AB.2816.03 TCGA.AB.2863.03 TCGA.AB.2950.03 TCGA.AB.2925.03 TCGA.AB.3007.03 TCGA.AB.2882.03 
#&gt;           &quot;013&quot;          &quot;0222&quot;           &quot;034&quot;           &quot;011&quot;          &quot;0323&quot;          &quot;0233&quot; 
#&gt; TCGA.AB.2825.03 TCGA.AB.2947.03 TCGA.AB.2916.03 TCGA.AB.2855.03 TCGA.AB.2978.03 TCGA.AB.2952.03 
#&gt;           &quot;011&quot;           &quot;011&quot;          &quot;0213&quot;          &quot;0221&quot;          &quot;0211&quot;          &quot;0233&quot; 
#&gt; TCGA.AB.2868.03 TCGA.AB.2908.03 TCGA.AB.2938.03 TCGA.AB.2923.03 TCGA.AB.2890.03 TCGA.AB.2988.03 
#&gt;          &quot;0231&quot;          &quot;0231&quot;          &quot;0213&quot;          &quot;0222&quot;          &quot;0231&quot;           &quot;013&quot; 
#&gt; TCGA.AB.2985.03 TCGA.AB.2880.03 TCGA.AB.2889.03 TCGA.AB.2887.03 TCGA.AB.2881.03 TCGA.AB.2834.03 
#&gt;           &quot;013&quot;           &quot;031&quot;           &quot;033&quot;          &quot;0211&quot;           &quot;033&quot;          &quot;0221&quot; 
#&gt; TCGA.AB.2943.03 TCGA.AB.2982.03 TCGA.AB.2844.03 TCGA.AB.2870.03 TCGA.AB.2813.03 TCGA.AB.2894.03 
#&gt;          &quot;0231&quot;          &quot;0321&quot;           &quot;012&quot;           &quot;033&quot;          &quot;0231&quot;          &quot;0212&quot; 
#&gt; TCGA.AB.2909.03 TCGA.AB.2858.03 TCGA.AB.2935.03 TCGA.AB.2929.03 TCGA.AB.2831.03 TCGA.AB.2826.03 
#&gt;           &quot;034&quot;           &quot;033&quot;          &quot;0231&quot;          &quot;0233&quot;          &quot;0211&quot;          &quot;0221&quot; 
#&gt; TCGA.AB.2993.03 TCGA.AB.2810.03 TCGA.AB.2924.03 TCGA.AB.2901.03 TCGA.AB.2975.03 TCGA.AB.2860.03 
#&gt;          &quot;0142&quot;          &quot;0221&quot;          &quot;0141&quot;          &quot;0222&quot;          &quot;0211&quot;          &quot;0233&quot; 
#&gt; TCGA.AB.2854.03 TCGA.AB.2846.03 
#&gt;          &quot;0222&quot;           &quot;033&quot;
</code></pre>

<script>
$('#tab-get-classes-from-hierarchical-partition-5-a').parent().next().next().hide();
$('#tab-get-classes-from-hierarchical-partition-5-a').click(function(){
  $('#tab-get-classes-from-hierarchical-partition-5-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-get-classes-from-hierarchical-partition-6'>
<p><a id='tab-get-classes-from-hierarchical-partition-6-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">get_classes(res_rh, merge_node = merge_node_param(min_n_signatures = 4786))
</code></pre>

<pre><code>#&gt; TCGA.AB.2888.03 TCGA.AB.2995.03 TCGA.AB.2884.03 TCGA.AB.2878.03 TCGA.AB.2998.03 TCGA.AB.2913.03 
#&gt;           &quot;033&quot;          &quot;0213&quot;           &quot;013&quot;          &quot;0233&quot;          &quot;0321&quot;           &quot;012&quot; 
#&gt; TCGA.AB.2883.03 TCGA.AB.2957.03 TCGA.AB.2984.03 TCGA.AB.2837.03 TCGA.AB.2874.03 TCGA.AB.2836.03 
#&gt;          &quot;0212&quot;           &quot;033&quot;          &quot;0221&quot;           &quot;014&quot;          &quot;0221&quot;           &quot;014&quot; 
#&gt; TCGA.AB.2876.03 TCGA.AB.2830.03 TCGA.AB.2823.03 TCGA.AB.2999.03 TCGA.AB.2940.03 TCGA.AB.2941.03 
#&gt;           &quot;031&quot;          &quot;0211&quot;          &quot;0324&quot;          &quot;0322&quot;           &quot;031&quot;          &quot;0213&quot; 
#&gt; TCGA.AB.2987.03 TCGA.AB.2945.03 TCGA.AB.2963.03 TCGA.AB.2967.03 TCGA.AB.2843.03 TCGA.AB.2807.03 
#&gt;          &quot;0212&quot;           &quot;013&quot;           &quot;014&quot;           &quot;014&quot;          &quot;0231&quot;          &quot;0233&quot; 
#&gt; TCGA.AB.3012.03 TCGA.AB.2971.03 TCGA.AB.2809.03 TCGA.AB.2873.03 TCGA.AB.2802.03 TCGA.AB.2851.03 
#&gt;          &quot;0323&quot;          &quot;0211&quot;           &quot;011&quot;          &quot;0213&quot;           &quot;011&quot;           &quot;013&quot; 
#&gt; TCGA.AB.2853.03 TCGA.AB.2847.03 TCGA.AB.2833.03 TCGA.AB.2814.03 TCGA.AB.2898.03 TCGA.AB.2866.03 
#&gt;           &quot;011&quot;          &quot;0233&quot;          &quot;0213&quot;          &quot;0233&quot;          &quot;0211&quot;          &quot;0221&quot; 
#&gt; TCGA.AB.2875.03 TCGA.AB.2841.03 TCGA.AB.2922.03 TCGA.AB.3008.03 TCGA.AB.2968.03 TCGA.AB.2811.03 
#&gt;           &quot;034&quot;          &quot;0321&quot;          &quot;0231&quot;           &quot;031&quot;          &quot;0213&quot;           &quot;011&quot; 
#&gt; TCGA.AB.2895.03 TCGA.AB.2933.03 TCGA.AB.2827.03 TCGA.AB.2942.03 TCGA.AB.2910.03 TCGA.AB.2934.03 
#&gt;           &quot;011&quot;          &quot;0231&quot;           &quot;014&quot;           &quot;033&quot;          &quot;0212&quot;          &quot;0211&quot; 
#&gt; TCGA.AB.2959.03 TCGA.AB.2871.03 TCGA.AB.2907.03 TCGA.AB.2932.03 TCGA.AB.2824.03 TCGA.AB.2972.03 
#&gt;          &quot;0222&quot;          &quot;0222&quot;          &quot;0222&quot;           &quot;014&quot;           &quot;013&quot;           &quot;013&quot; 
#&gt; TCGA.AB.2915.03 TCGA.AB.2970.03 TCGA.AB.2949.03 TCGA.AB.2912.03 TCGA.AB.2838.03 TCGA.AB.2872.03 
#&gt;          &quot;0231&quot;          &quot;0233&quot;          &quot;0231&quot;          &quot;0233&quot;          &quot;0233&quot;          &quot;0323&quot; 
#&gt; TCGA.AB.2897.03 TCGA.AB.2965.03 TCGA.AB.2891.03 TCGA.AB.2921.03 TCGA.AB.2867.03 TCGA.AB.2842.03 
#&gt;          &quot;0321&quot;           &quot;011&quot;          &quot;0232&quot;           &quot;031&quot;          &quot;0222&quot;           &quot;013&quot; 
#&gt; TCGA.AB.2862.03 TCGA.AB.2840.03 TCGA.AB.2822.03 TCGA.AB.2832.03 TCGA.AB.2893.03 TCGA.AB.2956.03 
#&gt;          &quot;0321&quot;          &quot;0322&quot;          &quot;0222&quot;          &quot;0212&quot;          &quot;0212&quot;          &quot;0212&quot; 
#&gt; TCGA.AB.2903.03 TCGA.AB.2845.03 TCGA.AB.2948.03 TCGA.AB.2869.03 TCGA.AB.3009.03 TCGA.AB.2944.03 
#&gt;          &quot;0222&quot;           &quot;031&quot;          &quot;0222&quot;           &quot;013&quot;           &quot;031&quot;          &quot;0232&quot; 
#&gt; TCGA.AB.2886.03 TCGA.AB.2904.03 TCGA.AB.3005.03 TCGA.AB.2861.03 TCGA.AB.2917.03 TCGA.AB.2964.03 
#&gt;           &quot;034&quot;          &quot;0231&quot;          &quot;0212&quot;          &quot;0212&quot;          &quot;0233&quot;          &quot;0222&quot; 
#&gt; TCGA.AB.2955.03 TCGA.AB.2911.03 TCGA.AB.2892.03 TCGA.AB.2817.03 TCGA.AB.2906.03 TCGA.AB.2857.03 
#&gt;           &quot;031&quot;           &quot;014&quot;           &quot;033&quot;          &quot;0231&quot;          &quot;0322&quot;          &quot;0231&quot; 
#&gt; TCGA.AB.2805.03 TCGA.AB.2983.03 TCGA.AB.2918.03 TCGA.AB.2990.03 TCGA.AB.2937.03 TCGA.AB.3006.03 
#&gt;          &quot;0222&quot;          &quot;0231&quot;           &quot;012&quot;          &quot;0221&quot;           &quot;034&quot;           &quot;013&quot; 
#&gt; TCGA.AB.2829.03 TCGA.AB.2848.03 TCGA.AB.2914.03 TCGA.AB.3002.03 TCGA.AB.2877.03 TCGA.AB.2969.03 
#&gt;          &quot;0213&quot;           &quot;014&quot;           &quot;034&quot;          &quot;0221&quot;          &quot;0221&quot;           &quot;011&quot; 
#&gt; TCGA.AB.2839.03 TCGA.AB.2835.03 TCGA.AB.2974.03 TCGA.AB.2920.03 TCGA.AB.2980.03 TCGA.AB.2819.03 
#&gt;           &quot;012&quot;           &quot;014&quot;           &quot;011&quot;          &quot;0233&quot;          &quot;0325&quot;           &quot;034&quot; 
#&gt; TCGA.AB.2992.03 TCGA.AB.2919.03 TCGA.AB.2928.03 TCGA.AB.2927.03 TCGA.AB.2806.03 TCGA.AB.2885.03 
#&gt;          &quot;0222&quot;          &quot;0221&quot;          &quot;0211&quot;          &quot;0231&quot;           &quot;034&quot;          &quot;0231&quot; 
#&gt; TCGA.AB.2815.03 TCGA.AB.2996.03 TCGA.AB.2936.03 TCGA.AB.2939.03 TCGA.AB.2979.03 TCGA.AB.2986.03 
#&gt;           &quot;033&quot;          &quot;0222&quot;          &quot;0222&quot;           &quot;031&quot;           &quot;031&quot;           &quot;012&quot; 
#&gt; TCGA.AB.2931.03 TCGA.AB.2896.03 TCGA.AB.2966.03 TCGA.AB.2820.03 TCGA.AB.2808.03 TCGA.AB.2991.03 
#&gt;           &quot;011&quot;           &quot;011&quot;          &quot;0232&quot;          &quot;0231&quot;           &quot;031&quot;          &quot;0324&quot; 
#&gt; TCGA.AB.2803.03 TCGA.AB.2900.03 TCGA.AB.2899.03 TCGA.AB.2812.03 TCGA.AB.3011.03 TCGA.AB.2946.03 
#&gt;          &quot;0321&quot;          &quot;0221&quot;          &quot;0233&quot;           &quot;012&quot;           &quot;013&quot;           &quot;012&quot; 
#&gt; TCGA.AB.3000.03 TCGA.AB.2997.03 TCGA.AB.3001.03 TCGA.AB.2926.03 TCGA.AB.2856.03 TCGA.AB.2977.03 
#&gt;           &quot;031&quot;          &quot;0324&quot;          &quot;0324&quot;          &quot;0221&quot;           &quot;012&quot;          &quot;0221&quot; 
#&gt; TCGA.AB.2879.03 TCGA.AB.2976.03 TCGA.AB.2989.03 TCGA.AB.2849.03 TCGA.AB.2981.03 TCGA.AB.2954.03 
#&gt;           &quot;014&quot;           &quot;014&quot;           &quot;012&quot;          &quot;0232&quot;           &quot;011&quot;           &quot;033&quot; 
#&gt; TCGA.AB.2973.03 TCGA.AB.2828.03 TCGA.AB.2804.03 TCGA.AB.2818.03 TCGA.AB.2930.03 TCGA.AB.2821.03 
#&gt;           &quot;014&quot;           &quot;033&quot;          &quot;0325&quot;           &quot;014&quot;           &quot;014&quot;          &quot;0222&quot; 
#&gt; TCGA.AB.2816.03 TCGA.AB.2863.03 TCGA.AB.2950.03 TCGA.AB.2925.03 TCGA.AB.3007.03 TCGA.AB.2882.03 
#&gt;           &quot;013&quot;          &quot;0222&quot;           &quot;034&quot;           &quot;011&quot;          &quot;0323&quot;          &quot;0233&quot; 
#&gt; TCGA.AB.2825.03 TCGA.AB.2947.03 TCGA.AB.2916.03 TCGA.AB.2855.03 TCGA.AB.2978.03 TCGA.AB.2952.03 
#&gt;           &quot;011&quot;           &quot;011&quot;          &quot;0213&quot;          &quot;0221&quot;          &quot;0211&quot;          &quot;0233&quot; 
#&gt; TCGA.AB.2868.03 TCGA.AB.2908.03 TCGA.AB.2938.03 TCGA.AB.2923.03 TCGA.AB.2890.03 TCGA.AB.2988.03 
#&gt;          &quot;0231&quot;          &quot;0231&quot;          &quot;0213&quot;          &quot;0222&quot;          &quot;0231&quot;           &quot;013&quot; 
#&gt; TCGA.AB.2985.03 TCGA.AB.2880.03 TCGA.AB.2889.03 TCGA.AB.2887.03 TCGA.AB.2881.03 TCGA.AB.2834.03 
#&gt;           &quot;013&quot;           &quot;031&quot;           &quot;033&quot;          &quot;0211&quot;           &quot;033&quot;          &quot;0221&quot; 
#&gt; TCGA.AB.2943.03 TCGA.AB.2982.03 TCGA.AB.2844.03 TCGA.AB.2870.03 TCGA.AB.2813.03 TCGA.AB.2894.03 
#&gt;          &quot;0231&quot;          &quot;0321&quot;           &quot;012&quot;           &quot;033&quot;          &quot;0231&quot;          &quot;0212&quot; 
#&gt; TCGA.AB.2909.03 TCGA.AB.2858.03 TCGA.AB.2935.03 TCGA.AB.2929.03 TCGA.AB.2831.03 TCGA.AB.2826.03 
#&gt;           &quot;034&quot;           &quot;033&quot;          &quot;0231&quot;          &quot;0233&quot;          &quot;0211&quot;          &quot;0221&quot; 
#&gt; TCGA.AB.2993.03 TCGA.AB.2810.03 TCGA.AB.2924.03 TCGA.AB.2901.03 TCGA.AB.2975.03 TCGA.AB.2860.03 
#&gt;           &quot;014&quot;          &quot;0221&quot;           &quot;014&quot;          &quot;0222&quot;          &quot;0211&quot;          &quot;0233&quot; 
#&gt; TCGA.AB.2854.03 TCGA.AB.2846.03 
#&gt;          &quot;0222&quot;           &quot;033&quot;
</code></pre>

<script>
$('#tab-get-classes-from-hierarchical-partition-6-a').parent().next().next().hide();
$('#tab-get-classes-from-hierarchical-partition-6-a').click(function(){
  $('#tab-get-classes-from-hierarchical-partition-6-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-get-classes-from-hierarchical-partition-7'>
<p><a id='tab-get-classes-from-hierarchical-partition-7-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">get_classes(res_rh, merge_node = merge_node_param(min_n_signatures = 5739))
</code></pre>

<pre><code>#&gt; TCGA.AB.2888.03 TCGA.AB.2995.03 TCGA.AB.2884.03 TCGA.AB.2878.03 TCGA.AB.2998.03 TCGA.AB.2913.03 
#&gt;           &quot;033&quot;          &quot;0213&quot;           &quot;013&quot;          &quot;0233&quot;          &quot;0321&quot;           &quot;012&quot; 
#&gt; TCGA.AB.2883.03 TCGA.AB.2957.03 TCGA.AB.2984.03 TCGA.AB.2837.03 TCGA.AB.2874.03 TCGA.AB.2836.03 
#&gt;          &quot;0212&quot;           &quot;033&quot;           &quot;022&quot;           &quot;014&quot;           &quot;022&quot;           &quot;014&quot; 
#&gt; TCGA.AB.2876.03 TCGA.AB.2830.03 TCGA.AB.2823.03 TCGA.AB.2999.03 TCGA.AB.2940.03 TCGA.AB.2941.03 
#&gt;           &quot;031&quot;          &quot;0211&quot;          &quot;0324&quot;          &quot;0322&quot;           &quot;031&quot;          &quot;0213&quot; 
#&gt; TCGA.AB.2987.03 TCGA.AB.2945.03 TCGA.AB.2963.03 TCGA.AB.2967.03 TCGA.AB.2843.03 TCGA.AB.2807.03 
#&gt;          &quot;0212&quot;           &quot;013&quot;           &quot;014&quot;           &quot;014&quot;          &quot;0231&quot;          &quot;0233&quot; 
#&gt; TCGA.AB.3012.03 TCGA.AB.2971.03 TCGA.AB.2809.03 TCGA.AB.2873.03 TCGA.AB.2802.03 TCGA.AB.2851.03 
#&gt;          &quot;0323&quot;          &quot;0211&quot;           &quot;011&quot;          &quot;0213&quot;           &quot;011&quot;           &quot;013&quot; 
#&gt; TCGA.AB.2853.03 TCGA.AB.2847.03 TCGA.AB.2833.03 TCGA.AB.2814.03 TCGA.AB.2898.03 TCGA.AB.2866.03 
#&gt;           &quot;011&quot;          &quot;0233&quot;          &quot;0213&quot;          &quot;0233&quot;          &quot;0211&quot;           &quot;022&quot; 
#&gt; TCGA.AB.2875.03 TCGA.AB.2841.03 TCGA.AB.2922.03 TCGA.AB.3008.03 TCGA.AB.2968.03 TCGA.AB.2811.03 
#&gt;           &quot;034&quot;          &quot;0321&quot;          &quot;0231&quot;           &quot;031&quot;          &quot;0213&quot;           &quot;011&quot; 
#&gt; TCGA.AB.2895.03 TCGA.AB.2933.03 TCGA.AB.2827.03 TCGA.AB.2942.03 TCGA.AB.2910.03 TCGA.AB.2934.03 
#&gt;           &quot;011&quot;          &quot;0231&quot;           &quot;014&quot;           &quot;033&quot;          &quot;0212&quot;          &quot;0211&quot; 
#&gt; TCGA.AB.2959.03 TCGA.AB.2871.03 TCGA.AB.2907.03 TCGA.AB.2932.03 TCGA.AB.2824.03 TCGA.AB.2972.03 
#&gt;           &quot;022&quot;           &quot;022&quot;           &quot;022&quot;           &quot;014&quot;           &quot;013&quot;           &quot;013&quot; 
#&gt; TCGA.AB.2915.03 TCGA.AB.2970.03 TCGA.AB.2949.03 TCGA.AB.2912.03 TCGA.AB.2838.03 TCGA.AB.2872.03 
#&gt;          &quot;0231&quot;          &quot;0233&quot;          &quot;0231&quot;          &quot;0233&quot;          &quot;0233&quot;          &quot;0323&quot; 
#&gt; TCGA.AB.2897.03 TCGA.AB.2965.03 TCGA.AB.2891.03 TCGA.AB.2921.03 TCGA.AB.2867.03 TCGA.AB.2842.03 
#&gt;          &quot;0321&quot;           &quot;011&quot;          &quot;0232&quot;           &quot;031&quot;           &quot;022&quot;           &quot;013&quot; 
#&gt; TCGA.AB.2862.03 TCGA.AB.2840.03 TCGA.AB.2822.03 TCGA.AB.2832.03 TCGA.AB.2893.03 TCGA.AB.2956.03 
#&gt;          &quot;0321&quot;          &quot;0322&quot;           &quot;022&quot;          &quot;0212&quot;          &quot;0212&quot;          &quot;0212&quot; 
#&gt; TCGA.AB.2903.03 TCGA.AB.2845.03 TCGA.AB.2948.03 TCGA.AB.2869.03 TCGA.AB.3009.03 TCGA.AB.2944.03 
#&gt;           &quot;022&quot;           &quot;031&quot;           &quot;022&quot;           &quot;013&quot;           &quot;031&quot;          &quot;0232&quot; 
#&gt; TCGA.AB.2886.03 TCGA.AB.2904.03 TCGA.AB.3005.03 TCGA.AB.2861.03 TCGA.AB.2917.03 TCGA.AB.2964.03 
#&gt;           &quot;034&quot;          &quot;0231&quot;          &quot;0212&quot;          &quot;0212&quot;          &quot;0233&quot;           &quot;022&quot; 
#&gt; TCGA.AB.2955.03 TCGA.AB.2911.03 TCGA.AB.2892.03 TCGA.AB.2817.03 TCGA.AB.2906.03 TCGA.AB.2857.03 
#&gt;           &quot;031&quot;           &quot;014&quot;           &quot;033&quot;          &quot;0231&quot;          &quot;0322&quot;          &quot;0231&quot; 
#&gt; TCGA.AB.2805.03 TCGA.AB.2983.03 TCGA.AB.2918.03 TCGA.AB.2990.03 TCGA.AB.2937.03 TCGA.AB.3006.03 
#&gt;           &quot;022&quot;          &quot;0231&quot;           &quot;012&quot;           &quot;022&quot;           &quot;034&quot;           &quot;013&quot; 
#&gt; TCGA.AB.2829.03 TCGA.AB.2848.03 TCGA.AB.2914.03 TCGA.AB.3002.03 TCGA.AB.2877.03 TCGA.AB.2969.03 
#&gt;          &quot;0213&quot;           &quot;014&quot;           &quot;034&quot;           &quot;022&quot;           &quot;022&quot;           &quot;011&quot; 
#&gt; TCGA.AB.2839.03 TCGA.AB.2835.03 TCGA.AB.2974.03 TCGA.AB.2920.03 TCGA.AB.2980.03 TCGA.AB.2819.03 
#&gt;           &quot;012&quot;           &quot;014&quot;           &quot;011&quot;          &quot;0233&quot;          &quot;0325&quot;           &quot;034&quot; 
#&gt; TCGA.AB.2992.03 TCGA.AB.2919.03 TCGA.AB.2928.03 TCGA.AB.2927.03 TCGA.AB.2806.03 TCGA.AB.2885.03 
#&gt;           &quot;022&quot;           &quot;022&quot;          &quot;0211&quot;          &quot;0231&quot;           &quot;034&quot;          &quot;0231&quot; 
#&gt; TCGA.AB.2815.03 TCGA.AB.2996.03 TCGA.AB.2936.03 TCGA.AB.2939.03 TCGA.AB.2979.03 TCGA.AB.2986.03 
#&gt;           &quot;033&quot;           &quot;022&quot;           &quot;022&quot;           &quot;031&quot;           &quot;031&quot;           &quot;012&quot; 
#&gt; TCGA.AB.2931.03 TCGA.AB.2896.03 TCGA.AB.2966.03 TCGA.AB.2820.03 TCGA.AB.2808.03 TCGA.AB.2991.03 
#&gt;           &quot;011&quot;           &quot;011&quot;          &quot;0232&quot;          &quot;0231&quot;           &quot;031&quot;          &quot;0324&quot; 
#&gt; TCGA.AB.2803.03 TCGA.AB.2900.03 TCGA.AB.2899.03 TCGA.AB.2812.03 TCGA.AB.3011.03 TCGA.AB.2946.03 
#&gt;          &quot;0321&quot;           &quot;022&quot;          &quot;0233&quot;           &quot;012&quot;           &quot;013&quot;           &quot;012&quot; 
#&gt; TCGA.AB.3000.03 TCGA.AB.2997.03 TCGA.AB.3001.03 TCGA.AB.2926.03 TCGA.AB.2856.03 TCGA.AB.2977.03 
#&gt;           &quot;031&quot;          &quot;0324&quot;          &quot;0324&quot;           &quot;022&quot;           &quot;012&quot;           &quot;022&quot; 
#&gt; TCGA.AB.2879.03 TCGA.AB.2976.03 TCGA.AB.2989.03 TCGA.AB.2849.03 TCGA.AB.2981.03 TCGA.AB.2954.03 
#&gt;           &quot;014&quot;           &quot;014&quot;           &quot;012&quot;          &quot;0232&quot;           &quot;011&quot;           &quot;033&quot; 
#&gt; TCGA.AB.2973.03 TCGA.AB.2828.03 TCGA.AB.2804.03 TCGA.AB.2818.03 TCGA.AB.2930.03 TCGA.AB.2821.03 
#&gt;           &quot;014&quot;           &quot;033&quot;          &quot;0325&quot;           &quot;014&quot;           &quot;014&quot;           &quot;022&quot; 
#&gt; TCGA.AB.2816.03 TCGA.AB.2863.03 TCGA.AB.2950.03 TCGA.AB.2925.03 TCGA.AB.3007.03 TCGA.AB.2882.03 
#&gt;           &quot;013&quot;           &quot;022&quot;           &quot;034&quot;           &quot;011&quot;          &quot;0323&quot;          &quot;0233&quot; 
#&gt; TCGA.AB.2825.03 TCGA.AB.2947.03 TCGA.AB.2916.03 TCGA.AB.2855.03 TCGA.AB.2978.03 TCGA.AB.2952.03 
#&gt;           &quot;011&quot;           &quot;011&quot;          &quot;0213&quot;           &quot;022&quot;          &quot;0211&quot;          &quot;0233&quot; 
#&gt; TCGA.AB.2868.03 TCGA.AB.2908.03 TCGA.AB.2938.03 TCGA.AB.2923.03 TCGA.AB.2890.03 TCGA.AB.2988.03 
#&gt;          &quot;0231&quot;          &quot;0231&quot;          &quot;0213&quot;           &quot;022&quot;          &quot;0231&quot;           &quot;013&quot; 
#&gt; TCGA.AB.2985.03 TCGA.AB.2880.03 TCGA.AB.2889.03 TCGA.AB.2887.03 TCGA.AB.2881.03 TCGA.AB.2834.03 
#&gt;           &quot;013&quot;           &quot;031&quot;           &quot;033&quot;          &quot;0211&quot;           &quot;033&quot;           &quot;022&quot; 
#&gt; TCGA.AB.2943.03 TCGA.AB.2982.03 TCGA.AB.2844.03 TCGA.AB.2870.03 TCGA.AB.2813.03 TCGA.AB.2894.03 
#&gt;          &quot;0231&quot;          &quot;0321&quot;           &quot;012&quot;           &quot;033&quot;          &quot;0231&quot;          &quot;0212&quot; 
#&gt; TCGA.AB.2909.03 TCGA.AB.2858.03 TCGA.AB.2935.03 TCGA.AB.2929.03 TCGA.AB.2831.03 TCGA.AB.2826.03 
#&gt;           &quot;034&quot;           &quot;033&quot;          &quot;0231&quot;          &quot;0233&quot;          &quot;0211&quot;           &quot;022&quot; 
#&gt; TCGA.AB.2993.03 TCGA.AB.2810.03 TCGA.AB.2924.03 TCGA.AB.2901.03 TCGA.AB.2975.03 TCGA.AB.2860.03 
#&gt;           &quot;014&quot;           &quot;022&quot;           &quot;014&quot;           &quot;022&quot;          &quot;0211&quot;          &quot;0233&quot; 
#&gt; TCGA.AB.2854.03 TCGA.AB.2846.03 
#&gt;           &quot;022&quot;           &quot;033&quot;
</code></pre>

<script>
$('#tab-get-classes-from-hierarchical-partition-7-a').parent().next().next().hide();
$('#tab-get-classes-from-hierarchical-partition-7-a').click(function(){
  $('#tab-get-classes-from-hierarchical-partition-7-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-get-classes-from-hierarchical-partition-8'>
<p><a id='tab-get-classes-from-hierarchical-partition-8-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">get_classes(res_rh, merge_node = merge_node_param(min_n_signatures = 8194))
</code></pre>

<pre><code>#&gt; TCGA.AB.2888.03 TCGA.AB.2995.03 TCGA.AB.2884.03 TCGA.AB.2878.03 TCGA.AB.2998.03 TCGA.AB.2913.03 
#&gt;           &quot;033&quot;          &quot;0213&quot;           &quot;013&quot;          &quot;0233&quot;           &quot;032&quot;           &quot;012&quot; 
#&gt; TCGA.AB.2883.03 TCGA.AB.2957.03 TCGA.AB.2984.03 TCGA.AB.2837.03 TCGA.AB.2874.03 TCGA.AB.2836.03 
#&gt;          &quot;0212&quot;           &quot;033&quot;           &quot;022&quot;           &quot;014&quot;           &quot;022&quot;           &quot;014&quot; 
#&gt; TCGA.AB.2876.03 TCGA.AB.2830.03 TCGA.AB.2823.03 TCGA.AB.2999.03 TCGA.AB.2940.03 TCGA.AB.2941.03 
#&gt;           &quot;031&quot;          &quot;0211&quot;           &quot;032&quot;           &quot;032&quot;           &quot;031&quot;          &quot;0213&quot; 
#&gt; TCGA.AB.2987.03 TCGA.AB.2945.03 TCGA.AB.2963.03 TCGA.AB.2967.03 TCGA.AB.2843.03 TCGA.AB.2807.03 
#&gt;          &quot;0212&quot;           &quot;013&quot;           &quot;014&quot;           &quot;014&quot;          &quot;0231&quot;          &quot;0233&quot; 
#&gt; TCGA.AB.3012.03 TCGA.AB.2971.03 TCGA.AB.2809.03 TCGA.AB.2873.03 TCGA.AB.2802.03 TCGA.AB.2851.03 
#&gt;           &quot;032&quot;          &quot;0211&quot;           &quot;011&quot;          &quot;0213&quot;           &quot;011&quot;           &quot;013&quot; 
#&gt; TCGA.AB.2853.03 TCGA.AB.2847.03 TCGA.AB.2833.03 TCGA.AB.2814.03 TCGA.AB.2898.03 TCGA.AB.2866.03 
#&gt;           &quot;011&quot;          &quot;0233&quot;          &quot;0213&quot;          &quot;0233&quot;          &quot;0211&quot;           &quot;022&quot; 
#&gt; TCGA.AB.2875.03 TCGA.AB.2841.03 TCGA.AB.2922.03 TCGA.AB.3008.03 TCGA.AB.2968.03 TCGA.AB.2811.03 
#&gt;           &quot;034&quot;           &quot;032&quot;          &quot;0231&quot;           &quot;031&quot;          &quot;0213&quot;           &quot;011&quot; 
#&gt; TCGA.AB.2895.03 TCGA.AB.2933.03 TCGA.AB.2827.03 TCGA.AB.2942.03 TCGA.AB.2910.03 TCGA.AB.2934.03 
#&gt;           &quot;011&quot;          &quot;0231&quot;           &quot;014&quot;           &quot;033&quot;          &quot;0212&quot;          &quot;0211&quot; 
#&gt; TCGA.AB.2959.03 TCGA.AB.2871.03 TCGA.AB.2907.03 TCGA.AB.2932.03 TCGA.AB.2824.03 TCGA.AB.2972.03 
#&gt;           &quot;022&quot;           &quot;022&quot;           &quot;022&quot;           &quot;014&quot;           &quot;013&quot;           &quot;013&quot; 
#&gt; TCGA.AB.2915.03 TCGA.AB.2970.03 TCGA.AB.2949.03 TCGA.AB.2912.03 TCGA.AB.2838.03 TCGA.AB.2872.03 
#&gt;          &quot;0231&quot;          &quot;0233&quot;          &quot;0231&quot;          &quot;0233&quot;          &quot;0233&quot;           &quot;032&quot; 
#&gt; TCGA.AB.2897.03 TCGA.AB.2965.03 TCGA.AB.2891.03 TCGA.AB.2921.03 TCGA.AB.2867.03 TCGA.AB.2842.03 
#&gt;           &quot;032&quot;           &quot;011&quot;          &quot;0232&quot;           &quot;031&quot;           &quot;022&quot;           &quot;013&quot; 
#&gt; TCGA.AB.2862.03 TCGA.AB.2840.03 TCGA.AB.2822.03 TCGA.AB.2832.03 TCGA.AB.2893.03 TCGA.AB.2956.03 
#&gt;           &quot;032&quot;           &quot;032&quot;           &quot;022&quot;          &quot;0212&quot;          &quot;0212&quot;          &quot;0212&quot; 
#&gt; TCGA.AB.2903.03 TCGA.AB.2845.03 TCGA.AB.2948.03 TCGA.AB.2869.03 TCGA.AB.3009.03 TCGA.AB.2944.03 
#&gt;           &quot;022&quot;           &quot;031&quot;           &quot;022&quot;           &quot;013&quot;           &quot;031&quot;          &quot;0232&quot; 
#&gt; TCGA.AB.2886.03 TCGA.AB.2904.03 TCGA.AB.3005.03 TCGA.AB.2861.03 TCGA.AB.2917.03 TCGA.AB.2964.03 
#&gt;           &quot;034&quot;          &quot;0231&quot;          &quot;0212&quot;          &quot;0212&quot;          &quot;0233&quot;           &quot;022&quot; 
#&gt; TCGA.AB.2955.03 TCGA.AB.2911.03 TCGA.AB.2892.03 TCGA.AB.2817.03 TCGA.AB.2906.03 TCGA.AB.2857.03 
#&gt;           &quot;031&quot;           &quot;014&quot;           &quot;033&quot;          &quot;0231&quot;           &quot;032&quot;          &quot;0231&quot; 
#&gt; TCGA.AB.2805.03 TCGA.AB.2983.03 TCGA.AB.2918.03 TCGA.AB.2990.03 TCGA.AB.2937.03 TCGA.AB.3006.03 
#&gt;           &quot;022&quot;          &quot;0231&quot;           &quot;012&quot;           &quot;022&quot;           &quot;034&quot;           &quot;013&quot; 
#&gt; TCGA.AB.2829.03 TCGA.AB.2848.03 TCGA.AB.2914.03 TCGA.AB.3002.03 TCGA.AB.2877.03 TCGA.AB.2969.03 
#&gt;          &quot;0213&quot;           &quot;014&quot;           &quot;034&quot;           &quot;022&quot;           &quot;022&quot;           &quot;011&quot; 
#&gt; TCGA.AB.2839.03 TCGA.AB.2835.03 TCGA.AB.2974.03 TCGA.AB.2920.03 TCGA.AB.2980.03 TCGA.AB.2819.03 
#&gt;           &quot;012&quot;           &quot;014&quot;           &quot;011&quot;          &quot;0233&quot;           &quot;032&quot;           &quot;034&quot; 
#&gt; TCGA.AB.2992.03 TCGA.AB.2919.03 TCGA.AB.2928.03 TCGA.AB.2927.03 TCGA.AB.2806.03 TCGA.AB.2885.03 
#&gt;           &quot;022&quot;           &quot;022&quot;          &quot;0211&quot;          &quot;0231&quot;           &quot;034&quot;          &quot;0231&quot; 
#&gt; TCGA.AB.2815.03 TCGA.AB.2996.03 TCGA.AB.2936.03 TCGA.AB.2939.03 TCGA.AB.2979.03 TCGA.AB.2986.03 
#&gt;           &quot;033&quot;           &quot;022&quot;           &quot;022&quot;           &quot;031&quot;           &quot;031&quot;           &quot;012&quot; 
#&gt; TCGA.AB.2931.03 TCGA.AB.2896.03 TCGA.AB.2966.03 TCGA.AB.2820.03 TCGA.AB.2808.03 TCGA.AB.2991.03 
#&gt;           &quot;011&quot;           &quot;011&quot;          &quot;0232&quot;          &quot;0231&quot;           &quot;031&quot;           &quot;032&quot; 
#&gt; TCGA.AB.2803.03 TCGA.AB.2900.03 TCGA.AB.2899.03 TCGA.AB.2812.03 TCGA.AB.3011.03 TCGA.AB.2946.03 
#&gt;           &quot;032&quot;           &quot;022&quot;          &quot;0233&quot;           &quot;012&quot;           &quot;013&quot;           &quot;012&quot; 
#&gt; TCGA.AB.3000.03 TCGA.AB.2997.03 TCGA.AB.3001.03 TCGA.AB.2926.03 TCGA.AB.2856.03 TCGA.AB.2977.03 
#&gt;           &quot;031&quot;           &quot;032&quot;           &quot;032&quot;           &quot;022&quot;           &quot;012&quot;           &quot;022&quot; 
#&gt; TCGA.AB.2879.03 TCGA.AB.2976.03 TCGA.AB.2989.03 TCGA.AB.2849.03 TCGA.AB.2981.03 TCGA.AB.2954.03 
#&gt;           &quot;014&quot;           &quot;014&quot;           &quot;012&quot;          &quot;0232&quot;           &quot;011&quot;           &quot;033&quot; 
#&gt; TCGA.AB.2973.03 TCGA.AB.2828.03 TCGA.AB.2804.03 TCGA.AB.2818.03 TCGA.AB.2930.03 TCGA.AB.2821.03 
#&gt;           &quot;014&quot;           &quot;033&quot;           &quot;032&quot;           &quot;014&quot;           &quot;014&quot;           &quot;022&quot; 
#&gt; TCGA.AB.2816.03 TCGA.AB.2863.03 TCGA.AB.2950.03 TCGA.AB.2925.03 TCGA.AB.3007.03 TCGA.AB.2882.03 
#&gt;           &quot;013&quot;           &quot;022&quot;           &quot;034&quot;           &quot;011&quot;           &quot;032&quot;          &quot;0233&quot; 
#&gt; TCGA.AB.2825.03 TCGA.AB.2947.03 TCGA.AB.2916.03 TCGA.AB.2855.03 TCGA.AB.2978.03 TCGA.AB.2952.03 
#&gt;           &quot;011&quot;           &quot;011&quot;          &quot;0213&quot;           &quot;022&quot;          &quot;0211&quot;          &quot;0233&quot; 
#&gt; TCGA.AB.2868.03 TCGA.AB.2908.03 TCGA.AB.2938.03 TCGA.AB.2923.03 TCGA.AB.2890.03 TCGA.AB.2988.03 
#&gt;          &quot;0231&quot;          &quot;0231&quot;          &quot;0213&quot;           &quot;022&quot;          &quot;0231&quot;           &quot;013&quot; 
#&gt; TCGA.AB.2985.03 TCGA.AB.2880.03 TCGA.AB.2889.03 TCGA.AB.2887.03 TCGA.AB.2881.03 TCGA.AB.2834.03 
#&gt;           &quot;013&quot;           &quot;031&quot;           &quot;033&quot;          &quot;0211&quot;           &quot;033&quot;           &quot;022&quot; 
#&gt; TCGA.AB.2943.03 TCGA.AB.2982.03 TCGA.AB.2844.03 TCGA.AB.2870.03 TCGA.AB.2813.03 TCGA.AB.2894.03 
#&gt;          &quot;0231&quot;           &quot;032&quot;           &quot;012&quot;           &quot;033&quot;          &quot;0231&quot;          &quot;0212&quot; 
#&gt; TCGA.AB.2909.03 TCGA.AB.2858.03 TCGA.AB.2935.03 TCGA.AB.2929.03 TCGA.AB.2831.03 TCGA.AB.2826.03 
#&gt;           &quot;034&quot;           &quot;033&quot;          &quot;0231&quot;          &quot;0233&quot;          &quot;0211&quot;           &quot;022&quot; 
#&gt; TCGA.AB.2993.03 TCGA.AB.2810.03 TCGA.AB.2924.03 TCGA.AB.2901.03 TCGA.AB.2975.03 TCGA.AB.2860.03 
#&gt;           &quot;014&quot;           &quot;022&quot;           &quot;014&quot;           &quot;022&quot;          &quot;0211&quot;          &quot;0233&quot; 
#&gt; TCGA.AB.2854.03 TCGA.AB.2846.03 
#&gt;           &quot;022&quot;           &quot;033&quot;
</code></pre>

<script>
$('#tab-get-classes-from-hierarchical-partition-8-a').parent().next().next().hide();
$('#tab-get-classes-from-hierarchical-partition-8-a').click(function(){
  $('#tab-get-classes-from-hierarchical-partition-8-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-get-classes-from-hierarchical-partition-9'>
<p><a id='tab-get-classes-from-hierarchical-partition-9-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">get_classes(res_rh, merge_node = merge_node_param(min_n_signatures = 10868))
</code></pre>

<pre><code>#&gt; TCGA.AB.2888.03 TCGA.AB.2995.03 TCGA.AB.2884.03 TCGA.AB.2878.03 TCGA.AB.2998.03 TCGA.AB.2913.03 
#&gt;              NA          &quot;0213&quot;              NA          &quot;0233&quot;              NA              NA 
#&gt; TCGA.AB.2883.03 TCGA.AB.2957.03 TCGA.AB.2984.03 TCGA.AB.2837.03 TCGA.AB.2874.03 TCGA.AB.2836.03 
#&gt;          &quot;0212&quot;              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2876.03 TCGA.AB.2830.03 TCGA.AB.2823.03 TCGA.AB.2999.03 TCGA.AB.2940.03 TCGA.AB.2941.03 
#&gt;              NA          &quot;0211&quot;              NA              NA              NA          &quot;0213&quot; 
#&gt; TCGA.AB.2987.03 TCGA.AB.2945.03 TCGA.AB.2963.03 TCGA.AB.2967.03 TCGA.AB.2843.03 TCGA.AB.2807.03 
#&gt;          &quot;0212&quot;              NA              NA              NA          &quot;0231&quot;          &quot;0233&quot; 
#&gt; TCGA.AB.3012.03 TCGA.AB.2971.03 TCGA.AB.2809.03 TCGA.AB.2873.03 TCGA.AB.2802.03 TCGA.AB.2851.03 
#&gt;              NA          &quot;0211&quot;              NA          &quot;0213&quot;              NA              NA 
#&gt; TCGA.AB.2853.03 TCGA.AB.2847.03 TCGA.AB.2833.03 TCGA.AB.2814.03 TCGA.AB.2898.03 TCGA.AB.2866.03 
#&gt;              NA          &quot;0233&quot;          &quot;0213&quot;          &quot;0233&quot;          &quot;0211&quot;              NA 
#&gt; TCGA.AB.2875.03 TCGA.AB.2841.03 TCGA.AB.2922.03 TCGA.AB.3008.03 TCGA.AB.2968.03 TCGA.AB.2811.03 
#&gt;              NA              NA          &quot;0231&quot;              NA          &quot;0213&quot;              NA 
#&gt; TCGA.AB.2895.03 TCGA.AB.2933.03 TCGA.AB.2827.03 TCGA.AB.2942.03 TCGA.AB.2910.03 TCGA.AB.2934.03 
#&gt;              NA          &quot;0231&quot;              NA              NA          &quot;0212&quot;          &quot;0211&quot; 
#&gt; TCGA.AB.2959.03 TCGA.AB.2871.03 TCGA.AB.2907.03 TCGA.AB.2932.03 TCGA.AB.2824.03 TCGA.AB.2972.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2915.03 TCGA.AB.2970.03 TCGA.AB.2949.03 TCGA.AB.2912.03 TCGA.AB.2838.03 TCGA.AB.2872.03 
#&gt;          &quot;0231&quot;          &quot;0233&quot;          &quot;0231&quot;          &quot;0233&quot;          &quot;0233&quot;              NA 
#&gt; TCGA.AB.2897.03 TCGA.AB.2965.03 TCGA.AB.2891.03 TCGA.AB.2921.03 TCGA.AB.2867.03 TCGA.AB.2842.03 
#&gt;              NA              NA          &quot;0232&quot;              NA              NA              NA 
#&gt; TCGA.AB.2862.03 TCGA.AB.2840.03 TCGA.AB.2822.03 TCGA.AB.2832.03 TCGA.AB.2893.03 TCGA.AB.2956.03 
#&gt;              NA              NA              NA          &quot;0212&quot;          &quot;0212&quot;          &quot;0212&quot; 
#&gt; TCGA.AB.2903.03 TCGA.AB.2845.03 TCGA.AB.2948.03 TCGA.AB.2869.03 TCGA.AB.3009.03 TCGA.AB.2944.03 
#&gt;              NA              NA              NA              NA              NA          &quot;0232&quot; 
#&gt; TCGA.AB.2886.03 TCGA.AB.2904.03 TCGA.AB.3005.03 TCGA.AB.2861.03 TCGA.AB.2917.03 TCGA.AB.2964.03 
#&gt;              NA          &quot;0231&quot;          &quot;0212&quot;          &quot;0212&quot;          &quot;0233&quot;              NA 
#&gt; TCGA.AB.2955.03 TCGA.AB.2911.03 TCGA.AB.2892.03 TCGA.AB.2817.03 TCGA.AB.2906.03 TCGA.AB.2857.03 
#&gt;              NA              NA              NA          &quot;0231&quot;              NA          &quot;0231&quot; 
#&gt; TCGA.AB.2805.03 TCGA.AB.2983.03 TCGA.AB.2918.03 TCGA.AB.2990.03 TCGA.AB.2937.03 TCGA.AB.3006.03 
#&gt;              NA          &quot;0231&quot;              NA              NA              NA              NA 
#&gt; TCGA.AB.2829.03 TCGA.AB.2848.03 TCGA.AB.2914.03 TCGA.AB.3002.03 TCGA.AB.2877.03 TCGA.AB.2969.03 
#&gt;          &quot;0213&quot;              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2839.03 TCGA.AB.2835.03 TCGA.AB.2974.03 TCGA.AB.2920.03 TCGA.AB.2980.03 TCGA.AB.2819.03 
#&gt;              NA              NA              NA          &quot;0233&quot;              NA              NA 
#&gt; TCGA.AB.2992.03 TCGA.AB.2919.03 TCGA.AB.2928.03 TCGA.AB.2927.03 TCGA.AB.2806.03 TCGA.AB.2885.03 
#&gt;              NA              NA          &quot;0211&quot;          &quot;0231&quot;              NA          &quot;0231&quot; 
#&gt; TCGA.AB.2815.03 TCGA.AB.2996.03 TCGA.AB.2936.03 TCGA.AB.2939.03 TCGA.AB.2979.03 TCGA.AB.2986.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2931.03 TCGA.AB.2896.03 TCGA.AB.2966.03 TCGA.AB.2820.03 TCGA.AB.2808.03 TCGA.AB.2991.03 
#&gt;              NA              NA          &quot;0232&quot;          &quot;0231&quot;              NA              NA 
#&gt; TCGA.AB.2803.03 TCGA.AB.2900.03 TCGA.AB.2899.03 TCGA.AB.2812.03 TCGA.AB.3011.03 TCGA.AB.2946.03 
#&gt;              NA              NA          &quot;0233&quot;              NA              NA              NA 
#&gt; TCGA.AB.3000.03 TCGA.AB.2997.03 TCGA.AB.3001.03 TCGA.AB.2926.03 TCGA.AB.2856.03 TCGA.AB.2977.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2879.03 TCGA.AB.2976.03 TCGA.AB.2989.03 TCGA.AB.2849.03 TCGA.AB.2981.03 TCGA.AB.2954.03 
#&gt;              NA              NA              NA          &quot;0232&quot;              NA              NA 
#&gt; TCGA.AB.2973.03 TCGA.AB.2828.03 TCGA.AB.2804.03 TCGA.AB.2818.03 TCGA.AB.2930.03 TCGA.AB.2821.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2816.03 TCGA.AB.2863.03 TCGA.AB.2950.03 TCGA.AB.2925.03 TCGA.AB.3007.03 TCGA.AB.2882.03 
#&gt;              NA              NA              NA              NA              NA          &quot;0233&quot; 
#&gt; TCGA.AB.2825.03 TCGA.AB.2947.03 TCGA.AB.2916.03 TCGA.AB.2855.03 TCGA.AB.2978.03 TCGA.AB.2952.03 
#&gt;              NA              NA          &quot;0213&quot;              NA          &quot;0211&quot;          &quot;0233&quot; 
#&gt; TCGA.AB.2868.03 TCGA.AB.2908.03 TCGA.AB.2938.03 TCGA.AB.2923.03 TCGA.AB.2890.03 TCGA.AB.2988.03 
#&gt;          &quot;0231&quot;          &quot;0231&quot;          &quot;0213&quot;              NA          &quot;0231&quot;              NA 
#&gt; TCGA.AB.2985.03 TCGA.AB.2880.03 TCGA.AB.2889.03 TCGA.AB.2887.03 TCGA.AB.2881.03 TCGA.AB.2834.03 
#&gt;              NA              NA              NA          &quot;0211&quot;              NA              NA 
#&gt; TCGA.AB.2943.03 TCGA.AB.2982.03 TCGA.AB.2844.03 TCGA.AB.2870.03 TCGA.AB.2813.03 TCGA.AB.2894.03 
#&gt;          &quot;0231&quot;              NA              NA              NA          &quot;0231&quot;          &quot;0212&quot; 
#&gt; TCGA.AB.2909.03 TCGA.AB.2858.03 TCGA.AB.2935.03 TCGA.AB.2929.03 TCGA.AB.2831.03 TCGA.AB.2826.03 
#&gt;              NA              NA          &quot;0231&quot;          &quot;0233&quot;          &quot;0211&quot;              NA 
#&gt; TCGA.AB.2993.03 TCGA.AB.2810.03 TCGA.AB.2924.03 TCGA.AB.2901.03 TCGA.AB.2975.03 TCGA.AB.2860.03 
#&gt;              NA              NA              NA              NA          &quot;0211&quot;          &quot;0233&quot; 
#&gt; TCGA.AB.2854.03 TCGA.AB.2846.03 
#&gt;              NA              NA
</code></pre>

<script>
$('#tab-get-classes-from-hierarchical-partition-9-a').parent().next().next().hide();
$('#tab-get-classes-from-hierarchical-partition-9-a').click(function(){
  $('#tab-get-classes-from-hierarchical-partition-9-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-get-classes-from-hierarchical-partition-10'>
<p><a id='tab-get-classes-from-hierarchical-partition-10-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">get_classes(res_rh, merge_node = merge_node_param(min_n_signatures = 19218))
</code></pre>

<pre><code>#&gt; TCGA.AB.2888.03 TCGA.AB.2995.03 TCGA.AB.2884.03 TCGA.AB.2878.03 TCGA.AB.2998.03 TCGA.AB.2913.03 
#&gt;              NA              NA              NA          &quot;0233&quot;              NA              NA 
#&gt; TCGA.AB.2883.03 TCGA.AB.2957.03 TCGA.AB.2984.03 TCGA.AB.2837.03 TCGA.AB.2874.03 TCGA.AB.2836.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2876.03 TCGA.AB.2830.03 TCGA.AB.2823.03 TCGA.AB.2999.03 TCGA.AB.2940.03 TCGA.AB.2941.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2987.03 TCGA.AB.2945.03 TCGA.AB.2963.03 TCGA.AB.2967.03 TCGA.AB.2843.03 TCGA.AB.2807.03 
#&gt;              NA              NA              NA              NA          &quot;0231&quot;          &quot;0233&quot; 
#&gt; TCGA.AB.3012.03 TCGA.AB.2971.03 TCGA.AB.2809.03 TCGA.AB.2873.03 TCGA.AB.2802.03 TCGA.AB.2851.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2853.03 TCGA.AB.2847.03 TCGA.AB.2833.03 TCGA.AB.2814.03 TCGA.AB.2898.03 TCGA.AB.2866.03 
#&gt;              NA          &quot;0233&quot;              NA          &quot;0233&quot;              NA              NA 
#&gt; TCGA.AB.2875.03 TCGA.AB.2841.03 TCGA.AB.2922.03 TCGA.AB.3008.03 TCGA.AB.2968.03 TCGA.AB.2811.03 
#&gt;              NA              NA          &quot;0231&quot;              NA              NA              NA 
#&gt; TCGA.AB.2895.03 TCGA.AB.2933.03 TCGA.AB.2827.03 TCGA.AB.2942.03 TCGA.AB.2910.03 TCGA.AB.2934.03 
#&gt;              NA          &quot;0231&quot;              NA              NA              NA              NA 
#&gt; TCGA.AB.2959.03 TCGA.AB.2871.03 TCGA.AB.2907.03 TCGA.AB.2932.03 TCGA.AB.2824.03 TCGA.AB.2972.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2915.03 TCGA.AB.2970.03 TCGA.AB.2949.03 TCGA.AB.2912.03 TCGA.AB.2838.03 TCGA.AB.2872.03 
#&gt;          &quot;0231&quot;          &quot;0233&quot;          &quot;0231&quot;          &quot;0233&quot;          &quot;0233&quot;              NA 
#&gt; TCGA.AB.2897.03 TCGA.AB.2965.03 TCGA.AB.2891.03 TCGA.AB.2921.03 TCGA.AB.2867.03 TCGA.AB.2842.03 
#&gt;              NA              NA          &quot;0232&quot;              NA              NA              NA 
#&gt; TCGA.AB.2862.03 TCGA.AB.2840.03 TCGA.AB.2822.03 TCGA.AB.2832.03 TCGA.AB.2893.03 TCGA.AB.2956.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2903.03 TCGA.AB.2845.03 TCGA.AB.2948.03 TCGA.AB.2869.03 TCGA.AB.3009.03 TCGA.AB.2944.03 
#&gt;              NA              NA              NA              NA              NA          &quot;0232&quot; 
#&gt; TCGA.AB.2886.03 TCGA.AB.2904.03 TCGA.AB.3005.03 TCGA.AB.2861.03 TCGA.AB.2917.03 TCGA.AB.2964.03 
#&gt;              NA          &quot;0231&quot;              NA              NA          &quot;0233&quot;              NA 
#&gt; TCGA.AB.2955.03 TCGA.AB.2911.03 TCGA.AB.2892.03 TCGA.AB.2817.03 TCGA.AB.2906.03 TCGA.AB.2857.03 
#&gt;              NA              NA              NA          &quot;0231&quot;              NA          &quot;0231&quot; 
#&gt; TCGA.AB.2805.03 TCGA.AB.2983.03 TCGA.AB.2918.03 TCGA.AB.2990.03 TCGA.AB.2937.03 TCGA.AB.3006.03 
#&gt;              NA          &quot;0231&quot;              NA              NA              NA              NA 
#&gt; TCGA.AB.2829.03 TCGA.AB.2848.03 TCGA.AB.2914.03 TCGA.AB.3002.03 TCGA.AB.2877.03 TCGA.AB.2969.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2839.03 TCGA.AB.2835.03 TCGA.AB.2974.03 TCGA.AB.2920.03 TCGA.AB.2980.03 TCGA.AB.2819.03 
#&gt;              NA              NA              NA          &quot;0233&quot;              NA              NA 
#&gt; TCGA.AB.2992.03 TCGA.AB.2919.03 TCGA.AB.2928.03 TCGA.AB.2927.03 TCGA.AB.2806.03 TCGA.AB.2885.03 
#&gt;              NA              NA              NA          &quot;0231&quot;              NA          &quot;0231&quot; 
#&gt; TCGA.AB.2815.03 TCGA.AB.2996.03 TCGA.AB.2936.03 TCGA.AB.2939.03 TCGA.AB.2979.03 TCGA.AB.2986.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2931.03 TCGA.AB.2896.03 TCGA.AB.2966.03 TCGA.AB.2820.03 TCGA.AB.2808.03 TCGA.AB.2991.03 
#&gt;              NA              NA          &quot;0232&quot;          &quot;0231&quot;              NA              NA 
#&gt; TCGA.AB.2803.03 TCGA.AB.2900.03 TCGA.AB.2899.03 TCGA.AB.2812.03 TCGA.AB.3011.03 TCGA.AB.2946.03 
#&gt;              NA              NA          &quot;0233&quot;              NA              NA              NA 
#&gt; TCGA.AB.3000.03 TCGA.AB.2997.03 TCGA.AB.3001.03 TCGA.AB.2926.03 TCGA.AB.2856.03 TCGA.AB.2977.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2879.03 TCGA.AB.2976.03 TCGA.AB.2989.03 TCGA.AB.2849.03 TCGA.AB.2981.03 TCGA.AB.2954.03 
#&gt;              NA              NA              NA          &quot;0232&quot;              NA              NA 
#&gt; TCGA.AB.2973.03 TCGA.AB.2828.03 TCGA.AB.2804.03 TCGA.AB.2818.03 TCGA.AB.2930.03 TCGA.AB.2821.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2816.03 TCGA.AB.2863.03 TCGA.AB.2950.03 TCGA.AB.2925.03 TCGA.AB.3007.03 TCGA.AB.2882.03 
#&gt;              NA              NA              NA              NA              NA          &quot;0233&quot; 
#&gt; TCGA.AB.2825.03 TCGA.AB.2947.03 TCGA.AB.2916.03 TCGA.AB.2855.03 TCGA.AB.2978.03 TCGA.AB.2952.03 
#&gt;              NA              NA              NA              NA              NA          &quot;0233&quot; 
#&gt; TCGA.AB.2868.03 TCGA.AB.2908.03 TCGA.AB.2938.03 TCGA.AB.2923.03 TCGA.AB.2890.03 TCGA.AB.2988.03 
#&gt;          &quot;0231&quot;          &quot;0231&quot;              NA              NA          &quot;0231&quot;              NA 
#&gt; TCGA.AB.2985.03 TCGA.AB.2880.03 TCGA.AB.2889.03 TCGA.AB.2887.03 TCGA.AB.2881.03 TCGA.AB.2834.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2943.03 TCGA.AB.2982.03 TCGA.AB.2844.03 TCGA.AB.2870.03 TCGA.AB.2813.03 TCGA.AB.2894.03 
#&gt;          &quot;0231&quot;              NA              NA              NA          &quot;0231&quot;              NA 
#&gt; TCGA.AB.2909.03 TCGA.AB.2858.03 TCGA.AB.2935.03 TCGA.AB.2929.03 TCGA.AB.2831.03 TCGA.AB.2826.03 
#&gt;              NA              NA          &quot;0231&quot;          &quot;0233&quot;              NA              NA 
#&gt; TCGA.AB.2993.03 TCGA.AB.2810.03 TCGA.AB.2924.03 TCGA.AB.2901.03 TCGA.AB.2975.03 TCGA.AB.2860.03 
#&gt;              NA              NA              NA              NA              NA          &quot;0233&quot; 
#&gt; TCGA.AB.2854.03 TCGA.AB.2846.03 
#&gt;              NA              NA
</code></pre>

<script>
$('#tab-get-classes-from-hierarchical-partition-10-a').parent().next().next().hide();
$('#tab-get-classes-from-hierarchical-partition-10-a').click(function(){
  $('#tab-get-classes-from-hierarchical-partition-10-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-get-classes-from-hierarchical-partition-11'>
<p><a id='tab-get-classes-from-hierarchical-partition-11-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">get_classes(res_rh, merge_node = merge_node_param(min_n_signatures = 22248))
</code></pre>

<pre><code>#&gt; TCGA.AB.2888.03 TCGA.AB.2995.03 TCGA.AB.2884.03 TCGA.AB.2878.03 TCGA.AB.2998.03 TCGA.AB.2913.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2883.03 TCGA.AB.2957.03 TCGA.AB.2984.03 TCGA.AB.2837.03 TCGA.AB.2874.03 TCGA.AB.2836.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2876.03 TCGA.AB.2830.03 TCGA.AB.2823.03 TCGA.AB.2999.03 TCGA.AB.2940.03 TCGA.AB.2941.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2987.03 TCGA.AB.2945.03 TCGA.AB.2963.03 TCGA.AB.2967.03 TCGA.AB.2843.03 TCGA.AB.2807.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.3012.03 TCGA.AB.2971.03 TCGA.AB.2809.03 TCGA.AB.2873.03 TCGA.AB.2802.03 TCGA.AB.2851.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2853.03 TCGA.AB.2847.03 TCGA.AB.2833.03 TCGA.AB.2814.03 TCGA.AB.2898.03 TCGA.AB.2866.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2875.03 TCGA.AB.2841.03 TCGA.AB.2922.03 TCGA.AB.3008.03 TCGA.AB.2968.03 TCGA.AB.2811.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2895.03 TCGA.AB.2933.03 TCGA.AB.2827.03 TCGA.AB.2942.03 TCGA.AB.2910.03 TCGA.AB.2934.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2959.03 TCGA.AB.2871.03 TCGA.AB.2907.03 TCGA.AB.2932.03 TCGA.AB.2824.03 TCGA.AB.2972.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2915.03 TCGA.AB.2970.03 TCGA.AB.2949.03 TCGA.AB.2912.03 TCGA.AB.2838.03 TCGA.AB.2872.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2897.03 TCGA.AB.2965.03 TCGA.AB.2891.03 TCGA.AB.2921.03 TCGA.AB.2867.03 TCGA.AB.2842.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2862.03 TCGA.AB.2840.03 TCGA.AB.2822.03 TCGA.AB.2832.03 TCGA.AB.2893.03 TCGA.AB.2956.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2903.03 TCGA.AB.2845.03 TCGA.AB.2948.03 TCGA.AB.2869.03 TCGA.AB.3009.03 TCGA.AB.2944.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2886.03 TCGA.AB.2904.03 TCGA.AB.3005.03 TCGA.AB.2861.03 TCGA.AB.2917.03 TCGA.AB.2964.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2955.03 TCGA.AB.2911.03 TCGA.AB.2892.03 TCGA.AB.2817.03 TCGA.AB.2906.03 TCGA.AB.2857.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2805.03 TCGA.AB.2983.03 TCGA.AB.2918.03 TCGA.AB.2990.03 TCGA.AB.2937.03 TCGA.AB.3006.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2829.03 TCGA.AB.2848.03 TCGA.AB.2914.03 TCGA.AB.3002.03 TCGA.AB.2877.03 TCGA.AB.2969.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2839.03 TCGA.AB.2835.03 TCGA.AB.2974.03 TCGA.AB.2920.03 TCGA.AB.2980.03 TCGA.AB.2819.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2992.03 TCGA.AB.2919.03 TCGA.AB.2928.03 TCGA.AB.2927.03 TCGA.AB.2806.03 TCGA.AB.2885.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2815.03 TCGA.AB.2996.03 TCGA.AB.2936.03 TCGA.AB.2939.03 TCGA.AB.2979.03 TCGA.AB.2986.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2931.03 TCGA.AB.2896.03 TCGA.AB.2966.03 TCGA.AB.2820.03 TCGA.AB.2808.03 TCGA.AB.2991.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2803.03 TCGA.AB.2900.03 TCGA.AB.2899.03 TCGA.AB.2812.03 TCGA.AB.3011.03 TCGA.AB.2946.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.3000.03 TCGA.AB.2997.03 TCGA.AB.3001.03 TCGA.AB.2926.03 TCGA.AB.2856.03 TCGA.AB.2977.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2879.03 TCGA.AB.2976.03 TCGA.AB.2989.03 TCGA.AB.2849.03 TCGA.AB.2981.03 TCGA.AB.2954.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2973.03 TCGA.AB.2828.03 TCGA.AB.2804.03 TCGA.AB.2818.03 TCGA.AB.2930.03 TCGA.AB.2821.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2816.03 TCGA.AB.2863.03 TCGA.AB.2950.03 TCGA.AB.2925.03 TCGA.AB.3007.03 TCGA.AB.2882.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2825.03 TCGA.AB.2947.03 TCGA.AB.2916.03 TCGA.AB.2855.03 TCGA.AB.2978.03 TCGA.AB.2952.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2868.03 TCGA.AB.2908.03 TCGA.AB.2938.03 TCGA.AB.2923.03 TCGA.AB.2890.03 TCGA.AB.2988.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2985.03 TCGA.AB.2880.03 TCGA.AB.2889.03 TCGA.AB.2887.03 TCGA.AB.2881.03 TCGA.AB.2834.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2943.03 TCGA.AB.2982.03 TCGA.AB.2844.03 TCGA.AB.2870.03 TCGA.AB.2813.03 TCGA.AB.2894.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2909.03 TCGA.AB.2858.03 TCGA.AB.2935.03 TCGA.AB.2929.03 TCGA.AB.2831.03 TCGA.AB.2826.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2993.03 TCGA.AB.2810.03 TCGA.AB.2924.03 TCGA.AB.2901.03 TCGA.AB.2975.03 TCGA.AB.2860.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2854.03 TCGA.AB.2846.03 
#&gt;              NA              NA
</code></pre>

<script>
$('#tab-get-classes-from-hierarchical-partition-11-a').parent().next().next().hide();
$('#tab-get-classes-from-hierarchical-partition-11-a').click(function(){
  $('#tab-get-classes-from-hierarchical-partition-11-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-get-classes-from-hierarchical-partition-12'>
<p><a id='tab-get-classes-from-hierarchical-partition-12-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">get_classes(res_rh, merge_node = merge_node_param(min_n_signatures = 25188))
</code></pre>

<pre><code>#&gt; TCGA.AB.2888.03 TCGA.AB.2995.03 TCGA.AB.2884.03 TCGA.AB.2878.03 TCGA.AB.2998.03 TCGA.AB.2913.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2883.03 TCGA.AB.2957.03 TCGA.AB.2984.03 TCGA.AB.2837.03 TCGA.AB.2874.03 TCGA.AB.2836.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2876.03 TCGA.AB.2830.03 TCGA.AB.2823.03 TCGA.AB.2999.03 TCGA.AB.2940.03 TCGA.AB.2941.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2987.03 TCGA.AB.2945.03 TCGA.AB.2963.03 TCGA.AB.2967.03 TCGA.AB.2843.03 TCGA.AB.2807.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.3012.03 TCGA.AB.2971.03 TCGA.AB.2809.03 TCGA.AB.2873.03 TCGA.AB.2802.03 TCGA.AB.2851.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2853.03 TCGA.AB.2847.03 TCGA.AB.2833.03 TCGA.AB.2814.03 TCGA.AB.2898.03 TCGA.AB.2866.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2875.03 TCGA.AB.2841.03 TCGA.AB.2922.03 TCGA.AB.3008.03 TCGA.AB.2968.03 TCGA.AB.2811.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2895.03 TCGA.AB.2933.03 TCGA.AB.2827.03 TCGA.AB.2942.03 TCGA.AB.2910.03 TCGA.AB.2934.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2959.03 TCGA.AB.2871.03 TCGA.AB.2907.03 TCGA.AB.2932.03 TCGA.AB.2824.03 TCGA.AB.2972.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2915.03 TCGA.AB.2970.03 TCGA.AB.2949.03 TCGA.AB.2912.03 TCGA.AB.2838.03 TCGA.AB.2872.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2897.03 TCGA.AB.2965.03 TCGA.AB.2891.03 TCGA.AB.2921.03 TCGA.AB.2867.03 TCGA.AB.2842.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2862.03 TCGA.AB.2840.03 TCGA.AB.2822.03 TCGA.AB.2832.03 TCGA.AB.2893.03 TCGA.AB.2956.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2903.03 TCGA.AB.2845.03 TCGA.AB.2948.03 TCGA.AB.2869.03 TCGA.AB.3009.03 TCGA.AB.2944.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2886.03 TCGA.AB.2904.03 TCGA.AB.3005.03 TCGA.AB.2861.03 TCGA.AB.2917.03 TCGA.AB.2964.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2955.03 TCGA.AB.2911.03 TCGA.AB.2892.03 TCGA.AB.2817.03 TCGA.AB.2906.03 TCGA.AB.2857.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2805.03 TCGA.AB.2983.03 TCGA.AB.2918.03 TCGA.AB.2990.03 TCGA.AB.2937.03 TCGA.AB.3006.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2829.03 TCGA.AB.2848.03 TCGA.AB.2914.03 TCGA.AB.3002.03 TCGA.AB.2877.03 TCGA.AB.2969.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2839.03 TCGA.AB.2835.03 TCGA.AB.2974.03 TCGA.AB.2920.03 TCGA.AB.2980.03 TCGA.AB.2819.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2992.03 TCGA.AB.2919.03 TCGA.AB.2928.03 TCGA.AB.2927.03 TCGA.AB.2806.03 TCGA.AB.2885.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2815.03 TCGA.AB.2996.03 TCGA.AB.2936.03 TCGA.AB.2939.03 TCGA.AB.2979.03 TCGA.AB.2986.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2931.03 TCGA.AB.2896.03 TCGA.AB.2966.03 TCGA.AB.2820.03 TCGA.AB.2808.03 TCGA.AB.2991.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2803.03 TCGA.AB.2900.03 TCGA.AB.2899.03 TCGA.AB.2812.03 TCGA.AB.3011.03 TCGA.AB.2946.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.3000.03 TCGA.AB.2997.03 TCGA.AB.3001.03 TCGA.AB.2926.03 TCGA.AB.2856.03 TCGA.AB.2977.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2879.03 TCGA.AB.2976.03 TCGA.AB.2989.03 TCGA.AB.2849.03 TCGA.AB.2981.03 TCGA.AB.2954.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2973.03 TCGA.AB.2828.03 TCGA.AB.2804.03 TCGA.AB.2818.03 TCGA.AB.2930.03 TCGA.AB.2821.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2816.03 TCGA.AB.2863.03 TCGA.AB.2950.03 TCGA.AB.2925.03 TCGA.AB.3007.03 TCGA.AB.2882.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2825.03 TCGA.AB.2947.03 TCGA.AB.2916.03 TCGA.AB.2855.03 TCGA.AB.2978.03 TCGA.AB.2952.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2868.03 TCGA.AB.2908.03 TCGA.AB.2938.03 TCGA.AB.2923.03 TCGA.AB.2890.03 TCGA.AB.2988.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2985.03 TCGA.AB.2880.03 TCGA.AB.2889.03 TCGA.AB.2887.03 TCGA.AB.2881.03 TCGA.AB.2834.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2943.03 TCGA.AB.2982.03 TCGA.AB.2844.03 TCGA.AB.2870.03 TCGA.AB.2813.03 TCGA.AB.2894.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2909.03 TCGA.AB.2858.03 TCGA.AB.2935.03 TCGA.AB.2929.03 TCGA.AB.2831.03 TCGA.AB.2826.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2993.03 TCGA.AB.2810.03 TCGA.AB.2924.03 TCGA.AB.2901.03 TCGA.AB.2975.03 TCGA.AB.2860.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2854.03 TCGA.AB.2846.03 
#&gt;              NA              NA
</code></pre>

<script>
$('#tab-get-classes-from-hierarchical-partition-12-a').parent().next().next().hide();
$('#tab-get-classes-from-hierarchical-partition-12-a').click(function(){
  $('#tab-get-classes-from-hierarchical-partition-12-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-get-classes-from-hierarchical-partition-13'>
<p><a id='tab-get-classes-from-hierarchical-partition-13-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">get_classes(res_rh, merge_node = merge_node_param(min_n_signatures = 32510))
</code></pre>

<pre><code>#&gt; TCGA.AB.2888.03 TCGA.AB.2995.03 TCGA.AB.2884.03 TCGA.AB.2878.03 TCGA.AB.2998.03 TCGA.AB.2913.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2883.03 TCGA.AB.2957.03 TCGA.AB.2984.03 TCGA.AB.2837.03 TCGA.AB.2874.03 TCGA.AB.2836.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2876.03 TCGA.AB.2830.03 TCGA.AB.2823.03 TCGA.AB.2999.03 TCGA.AB.2940.03 TCGA.AB.2941.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2987.03 TCGA.AB.2945.03 TCGA.AB.2963.03 TCGA.AB.2967.03 TCGA.AB.2843.03 TCGA.AB.2807.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.3012.03 TCGA.AB.2971.03 TCGA.AB.2809.03 TCGA.AB.2873.03 TCGA.AB.2802.03 TCGA.AB.2851.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2853.03 TCGA.AB.2847.03 TCGA.AB.2833.03 TCGA.AB.2814.03 TCGA.AB.2898.03 TCGA.AB.2866.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2875.03 TCGA.AB.2841.03 TCGA.AB.2922.03 TCGA.AB.3008.03 TCGA.AB.2968.03 TCGA.AB.2811.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2895.03 TCGA.AB.2933.03 TCGA.AB.2827.03 TCGA.AB.2942.03 TCGA.AB.2910.03 TCGA.AB.2934.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2959.03 TCGA.AB.2871.03 TCGA.AB.2907.03 TCGA.AB.2932.03 TCGA.AB.2824.03 TCGA.AB.2972.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2915.03 TCGA.AB.2970.03 TCGA.AB.2949.03 TCGA.AB.2912.03 TCGA.AB.2838.03 TCGA.AB.2872.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2897.03 TCGA.AB.2965.03 TCGA.AB.2891.03 TCGA.AB.2921.03 TCGA.AB.2867.03 TCGA.AB.2842.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2862.03 TCGA.AB.2840.03 TCGA.AB.2822.03 TCGA.AB.2832.03 TCGA.AB.2893.03 TCGA.AB.2956.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2903.03 TCGA.AB.2845.03 TCGA.AB.2948.03 TCGA.AB.2869.03 TCGA.AB.3009.03 TCGA.AB.2944.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2886.03 TCGA.AB.2904.03 TCGA.AB.3005.03 TCGA.AB.2861.03 TCGA.AB.2917.03 TCGA.AB.2964.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2955.03 TCGA.AB.2911.03 TCGA.AB.2892.03 TCGA.AB.2817.03 TCGA.AB.2906.03 TCGA.AB.2857.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2805.03 TCGA.AB.2983.03 TCGA.AB.2918.03 TCGA.AB.2990.03 TCGA.AB.2937.03 TCGA.AB.3006.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2829.03 TCGA.AB.2848.03 TCGA.AB.2914.03 TCGA.AB.3002.03 TCGA.AB.2877.03 TCGA.AB.2969.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2839.03 TCGA.AB.2835.03 TCGA.AB.2974.03 TCGA.AB.2920.03 TCGA.AB.2980.03 TCGA.AB.2819.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2992.03 TCGA.AB.2919.03 TCGA.AB.2928.03 TCGA.AB.2927.03 TCGA.AB.2806.03 TCGA.AB.2885.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2815.03 TCGA.AB.2996.03 TCGA.AB.2936.03 TCGA.AB.2939.03 TCGA.AB.2979.03 TCGA.AB.2986.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2931.03 TCGA.AB.2896.03 TCGA.AB.2966.03 TCGA.AB.2820.03 TCGA.AB.2808.03 TCGA.AB.2991.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2803.03 TCGA.AB.2900.03 TCGA.AB.2899.03 TCGA.AB.2812.03 TCGA.AB.3011.03 TCGA.AB.2946.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.3000.03 TCGA.AB.2997.03 TCGA.AB.3001.03 TCGA.AB.2926.03 TCGA.AB.2856.03 TCGA.AB.2977.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2879.03 TCGA.AB.2976.03 TCGA.AB.2989.03 TCGA.AB.2849.03 TCGA.AB.2981.03 TCGA.AB.2954.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2973.03 TCGA.AB.2828.03 TCGA.AB.2804.03 TCGA.AB.2818.03 TCGA.AB.2930.03 TCGA.AB.2821.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2816.03 TCGA.AB.2863.03 TCGA.AB.2950.03 TCGA.AB.2925.03 TCGA.AB.3007.03 TCGA.AB.2882.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2825.03 TCGA.AB.2947.03 TCGA.AB.2916.03 TCGA.AB.2855.03 TCGA.AB.2978.03 TCGA.AB.2952.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2868.03 TCGA.AB.2908.03 TCGA.AB.2938.03 TCGA.AB.2923.03 TCGA.AB.2890.03 TCGA.AB.2988.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2985.03 TCGA.AB.2880.03 TCGA.AB.2889.03 TCGA.AB.2887.03 TCGA.AB.2881.03 TCGA.AB.2834.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2943.03 TCGA.AB.2982.03 TCGA.AB.2844.03 TCGA.AB.2870.03 TCGA.AB.2813.03 TCGA.AB.2894.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2909.03 TCGA.AB.2858.03 TCGA.AB.2935.03 TCGA.AB.2929.03 TCGA.AB.2831.03 TCGA.AB.2826.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2993.03 TCGA.AB.2810.03 TCGA.AB.2924.03 TCGA.AB.2901.03 TCGA.AB.2975.03 TCGA.AB.2860.03 
#&gt;              NA              NA              NA              NA              NA              NA 
#&gt; TCGA.AB.2854.03 TCGA.AB.2846.03 
#&gt;              NA              NA
</code></pre>

<script>
$('#tab-get-classes-from-hierarchical-partition-13-a').parent().next().next().hide();
$('#tab-get-classes-from-hierarchical-partition-13-a').click(function(){
  $('#tab-get-classes-from-hierarchical-partition-13-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>
</div>



### Top rows heatmap

Heatmaps of the top rows:





```r
top_rows_heatmap(res_rh)
```

![plot of chunk top-rows-heatmap](figure_cola/top-rows-heatmap-1.png)

```
#> Error in h(simpleError(msg, call)) : 
#>   error in evaluating the argument 'object' in selecting a method for function 'draw': no applicable method for 'height' applied to an object of class "list"
```

Top rows on each node:


```r
top_rows_overlap(res_rh, method = "upset")
```

![plot of chunk top-rows-overlap](figure_cola/top-rows-overlap-1.png)


### UMAP plot

UMAP plot which shows how samples are separated.




<script>
$( function() {
	$( '#tabs-dimension-reduction-by-depth' ).tabs();
} );
</script>
<div id='tabs-dimension-reduction-by-depth'>
<ul>
<li><a href='#tab-dimension-reduction-by-depth-1'>n_signatures ≥ 2818</a></li>
<li><a href='#tab-dimension-reduction-by-depth-2'>n_signatures ≥ 2995</a></li>
<li><a href='#tab-dimension-reduction-by-depth-3'>n_signatures ≥ 3376</a></li>
<li><a href='#tab-dimension-reduction-by-depth-4'>n_signatures ≥ 3533</a></li>
<li><a href='#tab-dimension-reduction-by-depth-5'>n_signatures ≥ 3565</a></li>
<li><a href='#tab-dimension-reduction-by-depth-6'>n_signatures ≥ 4786</a></li>
<li><a href='#tab-dimension-reduction-by-depth-7'>n_signatures ≥ 5739</a></li>
<li><a href='#tab-dimension-reduction-by-depth-8'>n_signatures ≥ 8194</a></li>
<li><a href='#tab-dimension-reduction-by-depth-9'>n_signatures ≥ 10868</a></li>
<li><a href='#tab-dimension-reduction-by-depth-10'>n_signatures ≥ 19218</a></li>
<li><a href='#tab-dimension-reduction-by-depth-11'>n_signatures ≥ 22248</a></li>
<li><a href='#tab-dimension-reduction-by-depth-12'>n_signatures ≥ 25188</a></li>
<li><a href='#tab-dimension-reduction-by-depth-13'>n_signatures ≥ 32510</a></li>
</ul>
<div id='tab-dimension-reduction-by-depth-1'>
<pre><code class="r">par(mfrow = c(1, 2))
dimension_reduction(res_rh, merge_node = merge_node_param(min_n_signatures = 2818),
    method = &quot;UMAP&quot;, top_value_method = &quot;SD&quot;, top_n = 40000, scale_rows = FALSE)
dimension_reduction(res_rh, merge_node = merge_node_param(min_n_signatures = 2818),
    method = &quot;UMAP&quot;, top_value_method = &quot;ATC&quot;, top_n = 40000, scale_rows = TRUE)
</code></pre>

<p><img src="figure_cola/tab-dimension-reduction-by-depth-1-1.png" title="plot of chunk tab-dimension-reduction-by-depth-1" alt="plot of chunk tab-dimension-reduction-by-depth-1" width="100%" /></p>

</div>
<div id='tab-dimension-reduction-by-depth-2'>
<pre><code class="r">par(mfrow = c(1, 2))
dimension_reduction(res_rh, merge_node = merge_node_param(min_n_signatures = 2995),
    method = &quot;UMAP&quot;, top_value_method = &quot;SD&quot;, top_n = 40000, scale_rows = FALSE)
dimension_reduction(res_rh, merge_node = merge_node_param(min_n_signatures = 2995),
    method = &quot;UMAP&quot;, top_value_method = &quot;ATC&quot;, top_n = 40000, scale_rows = TRUE)
</code></pre>

<p><img src="figure_cola/tab-dimension-reduction-by-depth-2-1.png" title="plot of chunk tab-dimension-reduction-by-depth-2" alt="plot of chunk tab-dimension-reduction-by-depth-2" width="100%" /></p>

</div>
<div id='tab-dimension-reduction-by-depth-3'>
<pre><code class="r">par(mfrow = c(1, 2))
dimension_reduction(res_rh, merge_node = merge_node_param(min_n_signatures = 3376),
    method = &quot;UMAP&quot;, top_value_method = &quot;SD&quot;, top_n = 40000, scale_rows = FALSE)
dimension_reduction(res_rh, merge_node = merge_node_param(min_n_signatures = 3376),
    method = &quot;UMAP&quot;, top_value_method = &quot;ATC&quot;, top_n = 40000, scale_rows = TRUE)
</code></pre>

<p><img src="figure_cola/tab-dimension-reduction-by-depth-3-1.png" title="plot of chunk tab-dimension-reduction-by-depth-3" alt="plot of chunk tab-dimension-reduction-by-depth-3" width="100%" /></p>

</div>
<div id='tab-dimension-reduction-by-depth-4'>
<pre><code class="r">par(mfrow = c(1, 2))
dimension_reduction(res_rh, merge_node = merge_node_param(min_n_signatures = 3533),
    method = &quot;UMAP&quot;, top_value_method = &quot;SD&quot;, top_n = 40000, scale_rows = FALSE)
dimension_reduction(res_rh, merge_node = merge_node_param(min_n_signatures = 3533),
    method = &quot;UMAP&quot;, top_value_method = &quot;ATC&quot;, top_n = 40000, scale_rows = TRUE)
</code></pre>

<p><img src="figure_cola/tab-dimension-reduction-by-depth-4-1.png" title="plot of chunk tab-dimension-reduction-by-depth-4" alt="plot of chunk tab-dimension-reduction-by-depth-4" width="100%" /></p>

</div>
<div id='tab-dimension-reduction-by-depth-5'>
<pre><code class="r">par(mfrow = c(1, 2))
dimension_reduction(res_rh, merge_node = merge_node_param(min_n_signatures = 3565),
    method = &quot;UMAP&quot;, top_value_method = &quot;SD&quot;, top_n = 40000, scale_rows = FALSE)
dimension_reduction(res_rh, merge_node = merge_node_param(min_n_signatures = 3565),
    method = &quot;UMAP&quot;, top_value_method = &quot;ATC&quot;, top_n = 40000, scale_rows = TRUE)
</code></pre>

<p><img src="figure_cola/tab-dimension-reduction-by-depth-5-1.png" title="plot of chunk tab-dimension-reduction-by-depth-5" alt="plot of chunk tab-dimension-reduction-by-depth-5" width="100%" /></p>

</div>
<div id='tab-dimension-reduction-by-depth-6'>
<pre><code class="r">par(mfrow = c(1, 2))
dimension_reduction(res_rh, merge_node = merge_node_param(min_n_signatures = 4786),
    method = &quot;UMAP&quot;, top_value_method = &quot;SD&quot;, top_n = 40000, scale_rows = FALSE)
dimension_reduction(res_rh, merge_node = merge_node_param(min_n_signatures = 4786),
    method = &quot;UMAP&quot;, top_value_method = &quot;ATC&quot;, top_n = 40000, scale_rows = TRUE)
</code></pre>

<p><img src="figure_cola/tab-dimension-reduction-by-depth-6-1.png" title="plot of chunk tab-dimension-reduction-by-depth-6" alt="plot of chunk tab-dimension-reduction-by-depth-6" width="100%" /></p>

</div>
<div id='tab-dimension-reduction-by-depth-7'>
<pre><code class="r">par(mfrow = c(1, 2))
dimension_reduction(res_rh, merge_node = merge_node_param(min_n_signatures = 5739),
    method = &quot;UMAP&quot;, top_value_method = &quot;SD&quot;, top_n = 40000, scale_rows = FALSE)
dimension_reduction(res_rh, merge_node = merge_node_param(min_n_signatures = 5739),
    method = &quot;UMAP&quot;, top_value_method = &quot;ATC&quot;, top_n = 40000, scale_rows = TRUE)
</code></pre>

<p><img src="figure_cola/tab-dimension-reduction-by-depth-7-1.png" title="plot of chunk tab-dimension-reduction-by-depth-7" alt="plot of chunk tab-dimension-reduction-by-depth-7" width="100%" /></p>

</div>
<div id='tab-dimension-reduction-by-depth-8'>
<pre><code class="r">par(mfrow = c(1, 2))
dimension_reduction(res_rh, merge_node = merge_node_param(min_n_signatures = 8194),
    method = &quot;UMAP&quot;, top_value_method = &quot;SD&quot;, top_n = 40000, scale_rows = FALSE)
dimension_reduction(res_rh, merge_node = merge_node_param(min_n_signatures = 8194),
    method = &quot;UMAP&quot;, top_value_method = &quot;ATC&quot;, top_n = 40000, scale_rows = TRUE)
</code></pre>

<p><img src="figure_cola/tab-dimension-reduction-by-depth-8-1.png" title="plot of chunk tab-dimension-reduction-by-depth-8" alt="plot of chunk tab-dimension-reduction-by-depth-8" width="100%" /></p>

</div>
<div id='tab-dimension-reduction-by-depth-9'>
<pre><code class="r">par(mfrow = c(1, 2))
dimension_reduction(res_rh, merge_node = merge_node_param(min_n_signatures = 10868),
    method = &quot;UMAP&quot;, top_value_method = &quot;SD&quot;, top_n = 40000, scale_rows = FALSE)
dimension_reduction(res_rh, merge_node = merge_node_param(min_n_signatures = 10868),
    method = &quot;UMAP&quot;, top_value_method = &quot;ATC&quot;, top_n = 40000, scale_rows = TRUE)
</code></pre>

<p><img src="figure_cola/tab-dimension-reduction-by-depth-9-1.png" title="plot of chunk tab-dimension-reduction-by-depth-9" alt="plot of chunk tab-dimension-reduction-by-depth-9" width="100%" /></p>

</div>
<div id='tab-dimension-reduction-by-depth-10'>
<pre><code class="r">par(mfrow = c(1, 2))
dimension_reduction(res_rh, merge_node = merge_node_param(min_n_signatures = 19218),
    method = &quot;UMAP&quot;, top_value_method = &quot;SD&quot;, top_n = 40000, scale_rows = FALSE)
dimension_reduction(res_rh, merge_node = merge_node_param(min_n_signatures = 19218),
    method = &quot;UMAP&quot;, top_value_method = &quot;ATC&quot;, top_n = 40000, scale_rows = TRUE)
</code></pre>

<p><img src="figure_cola/tab-dimension-reduction-by-depth-10-1.png" title="plot of chunk tab-dimension-reduction-by-depth-10" alt="plot of chunk tab-dimension-reduction-by-depth-10" width="100%" /></p>

</div>
<div id='tab-dimension-reduction-by-depth-11'>
<pre><code class="r">par(mfrow = c(1, 2))
dimension_reduction(res_rh, merge_node = merge_node_param(min_n_signatures = 22248),
    method = &quot;UMAP&quot;, top_value_method = &quot;SD&quot;, top_n = 40000, scale_rows = FALSE)
dimension_reduction(res_rh, merge_node = merge_node_param(min_n_signatures = 22248),
    method = &quot;UMAP&quot;, top_value_method = &quot;ATC&quot;, top_n = 40000, scale_rows = TRUE)
</code></pre>

<p><img src="figure_cola/tab-dimension-reduction-by-depth-11-1.png" title="plot of chunk tab-dimension-reduction-by-depth-11" alt="plot of chunk tab-dimension-reduction-by-depth-11" width="100%" /></p>

</div>
<div id='tab-dimension-reduction-by-depth-12'>
<pre><code class="r">par(mfrow = c(1, 2))
dimension_reduction(res_rh, merge_node = merge_node_param(min_n_signatures = 25188),
    method = &quot;UMAP&quot;, top_value_method = &quot;SD&quot;, top_n = 40000, scale_rows = FALSE)
dimension_reduction(res_rh, merge_node = merge_node_param(min_n_signatures = 25188),
    method = &quot;UMAP&quot;, top_value_method = &quot;ATC&quot;, top_n = 40000, scale_rows = TRUE)
</code></pre>

<p><img src="figure_cola/tab-dimension-reduction-by-depth-12-1.png" title="plot of chunk tab-dimension-reduction-by-depth-12" alt="plot of chunk tab-dimension-reduction-by-depth-12" width="100%" /></p>

</div>
<div id='tab-dimension-reduction-by-depth-13'>
<pre><code class="r">par(mfrow = c(1, 2))
dimension_reduction(res_rh, merge_node = merge_node_param(min_n_signatures = 32510),
    method = &quot;UMAP&quot;, top_value_method = &quot;SD&quot;, top_n = 40000, scale_rows = FALSE)
dimension_reduction(res_rh, merge_node = merge_node_param(min_n_signatures = 32510),
    method = &quot;UMAP&quot;, top_value_method = &quot;ATC&quot;, top_n = 40000, scale_rows = TRUE)
</code></pre>

<p><img src="figure_cola/tab-dimension-reduction-by-depth-13-1.png" title="plot of chunk tab-dimension-reduction-by-depth-13" alt="plot of chunk tab-dimension-reduction-by-depth-13" width="100%" /></p>

</div>
</div>




### Signature heatmap

Signatures on the heatmap are the union of all signatures found on every node
on the hierarchy. The number of k-means on rows are automatically selected by the function.




<script>
$( function() {
	$( '#tabs-get-signatures-from-hierarchical-partition' ).tabs();
} );
</script>
<div id='tabs-get-signatures-from-hierarchical-partition'>
<ul>
<li><a href='#tab-get-signatures-from-hierarchical-partition-1'>n_signatures ≥ 2818</a></li>
<li><a href='#tab-get-signatures-from-hierarchical-partition-2'>n_signatures ≥ 2995</a></li>
<li><a href='#tab-get-signatures-from-hierarchical-partition-3'>n_signatures ≥ 3376</a></li>
<li><a href='#tab-get-signatures-from-hierarchical-partition-4'>n_signatures ≥ 3533</a></li>
<li><a href='#tab-get-signatures-from-hierarchical-partition-5'>n_signatures ≥ 3565</a></li>
<li><a href='#tab-get-signatures-from-hierarchical-partition-6'>n_signatures ≥ 4786</a></li>
<li><a href='#tab-get-signatures-from-hierarchical-partition-7'>n_signatures ≥ 5739</a></li>
<li><a href='#tab-get-signatures-from-hierarchical-partition-8'>n_signatures ≥ 8194</a></li>
<li><a href='#tab-get-signatures-from-hierarchical-partition-9'>n_signatures ≥ 10868</a></li>
<li><a href='#tab-get-signatures-from-hierarchical-partition-10'>n_signatures ≥ 19218</a></li>
<li><a href='#tab-get-signatures-from-hierarchical-partition-11'>n_signatures ≥ 22248</a></li>
<li><a href='#tab-get-signatures-from-hierarchical-partition-12'>n_signatures ≥ 25188</a></li>
<li><a href='#tab-get-signatures-from-hierarchical-partition-13'>n_signatures ≥ 32510</a></li>
</ul>
<div id='tab-get-signatures-from-hierarchical-partition-1'>
<pre><code class="r">get_signatures(res_rh, merge_node = merge_node_param(min_n_signatures = 2818))
</code></pre>

<p><img src="figure_cola/tab-get-signatures-from-hierarchical-partition-1-1.png" alt="plot of chunk tab-get-signatures-from-hierarchical-partition-1"/></p>

</div>
<div id='tab-get-signatures-from-hierarchical-partition-2'>
<pre><code class="r">get_signatures(res_rh, merge_node = merge_node_param(min_n_signatures = 2995))
</code></pre>

<p><img src="figure_cola/tab-get-signatures-from-hierarchical-partition-2-1.png" alt="plot of chunk tab-get-signatures-from-hierarchical-partition-2"/></p>

</div>
<div id='tab-get-signatures-from-hierarchical-partition-3'>
<pre><code class="r">get_signatures(res_rh, merge_node = merge_node_param(min_n_signatures = 3376))
</code></pre>

<p><img src="figure_cola/tab-get-signatures-from-hierarchical-partition-3-1.png" alt="plot of chunk tab-get-signatures-from-hierarchical-partition-3"/></p>

</div>
<div id='tab-get-signatures-from-hierarchical-partition-4'>
<pre><code class="r">get_signatures(res_rh, merge_node = merge_node_param(min_n_signatures = 3533))
</code></pre>

<p><img src="figure_cola/tab-get-signatures-from-hierarchical-partition-4-1.png" alt="plot of chunk tab-get-signatures-from-hierarchical-partition-4"/></p>

</div>
<div id='tab-get-signatures-from-hierarchical-partition-5'>
<pre><code class="r">get_signatures(res_rh, merge_node = merge_node_param(min_n_signatures = 3565))
</code></pre>

<p><img src="figure_cola/tab-get-signatures-from-hierarchical-partition-5-1.png" alt="plot of chunk tab-get-signatures-from-hierarchical-partition-5"/></p>

</div>
<div id='tab-get-signatures-from-hierarchical-partition-6'>
<pre><code class="r">get_signatures(res_rh, merge_node = merge_node_param(min_n_signatures = 4786))
</code></pre>

<p><img src="figure_cola/tab-get-signatures-from-hierarchical-partition-6-1.png" alt="plot of chunk tab-get-signatures-from-hierarchical-partition-6"/></p>

</div>
<div id='tab-get-signatures-from-hierarchical-partition-7'>
<pre><code class="r">get_signatures(res_rh, merge_node = merge_node_param(min_n_signatures = 5739))
</code></pre>

<p><img src="figure_cola/tab-get-signatures-from-hierarchical-partition-7-1.png" alt="plot of chunk tab-get-signatures-from-hierarchical-partition-7"/></p>

</div>
<div id='tab-get-signatures-from-hierarchical-partition-8'>
<pre><code class="r">get_signatures(res_rh, merge_node = merge_node_param(min_n_signatures = 8194))
</code></pre>

<p><img src="figure_cola/tab-get-signatures-from-hierarchical-partition-8-1.png" alt="plot of chunk tab-get-signatures-from-hierarchical-partition-8"/></p>

</div>
<div id='tab-get-signatures-from-hierarchical-partition-9'>
<pre><code class="r">get_signatures(res_rh, merge_node = merge_node_param(min_n_signatures = 10868))
</code></pre>

<pre><code>#&gt; Error in lt[[hierarchy[i, 1]]]$AddChildNode({: attempt to apply non-function
</code></pre>

</div>
<div id='tab-get-signatures-from-hierarchical-partition-10'>
<pre><code class="r">get_signatures(res_rh, merge_node = merge_node_param(min_n_signatures = 19218))
</code></pre>

<pre><code>#&gt; Error in lt[[hierarchy[i, 1]]]$AddChildNode({: attempt to apply non-function
</code></pre>

</div>
<div id='tab-get-signatures-from-hierarchical-partition-11'>
<pre><code class="r">get_signatures(res_rh, merge_node = merge_node_param(min_n_signatures = 22248))
</code></pre>

<pre><code>#&gt; Error in names(x) &lt;- value: &#39;names&#39; attribute [1] must be the same length as the vector [0]
</code></pre>

</div>
<div id='tab-get-signatures-from-hierarchical-partition-12'>
<pre><code class="r">get_signatures(res_rh, merge_node = merge_node_param(min_n_signatures = 25188))
</code></pre>

<pre><code>#&gt; Error in names(x) &lt;- value: &#39;names&#39; attribute [1] must be the same length as the vector [0]
</code></pre>

</div>
<div id='tab-get-signatures-from-hierarchical-partition-13'>
<pre><code class="r">get_signatures(res_rh, merge_node = merge_node_param(min_n_signatures = 32510))
</code></pre>

<pre><code>#&gt; Error in names(x) &lt;- value: &#39;names&#39; attribute [1] must be the same length as the vector [0]
</code></pre>

</div>
</div>




Compare signatures from different nodes:


```r
compare_signatures(res_rh, verbose = FALSE)
```

![plot of chunk unnamed-chunk-24](figure_cola/unnamed-chunk-24-1.png)

If there are too many signatures, `top_signatures = ...` can be set to only show the 
signatures with the highest FDRs. Note it only works on every node and the final signatures
are the union of all signatures of all nodes.


```r
# code only for demonstration
# e.g. to show the top 500 most significant rows on each node.
tb = get_signature(res_rh, top_signatures = 500)
```


## Results for each node


---------------------------------------------------




### Node0


Child nodes: 
                [Node01](#Node01)
        ,
                [Node02](#Node02)
        ,
                [Node03](#Node03)
        .







The object with results only for a single top-value method and a single partitioning method 
can be extracted as:

```r
res = res_rh["0"]
```

A summary of `res` and all the functions that can be applied to it:

```r
res
```

```
#> A 'ConsensusPartition' object with k = 2, 3, 4, 5, 6, 7, 8.
#>   On a matrix with 30000 rows and 194 columns.
#>   Top rows (1000) are extracted by 'SD' method.
#>   Subgroups are detected by 'skmeans' method.
#>   Performed in total 350 partitions by row resampling.
#>   Best k for subgroups seems to be 3.
#> 
#> Following methods can be applied to this 'ConsensusPartition' object:
#>  [1] "cola_report"             "collect_classes"         "collect_plots"          
#>  [4] "collect_stats"           "colnames"                "compare_partitions"     
#>  [7] "compare_signatures"      "consensus_heatmap"       "dimension_reduction"    
#> [10] "functional_enrichment"   "get_anno_col"            "get_anno"               
#> [13] "get_classes"             "get_consensus"           "get_matrix"             
#> [16] "get_membership"          "get_param"               "get_signatures"         
#> [19] "get_stats"               "is_best_k"               "is_stable_k"            
#> [22] "membership_heatmap"      "ncol"                    "nrow"                   
#> [25] "plot_ecdf"               "predict_classes"         "rownames"               
#> [28] "select_partition_number" "show"                    "suggest_best_k"         
#> [31] "test_to_known_factors"   "top_rows_heatmap"
```

`collect_plots()` function collects all the plots made from `res` for all `k` (number of subgroups)
into one single page to provide an easy and fast comparison between different `k`.

```r
collect_plots(res)
```

![plot of chunk node-0-collect-plots](figure_cola/node-0-collect-plots-1.png)

The plots are:

- The first row: a plot of the eCDF (empirical cumulative distribution
  function) curves of the consensus matrix for each `k` and the heatmap of
  predicted classes for each `k`.
- The second row: heatmaps of the consensus matrix for each `k`.
- The third row: heatmaps of the membership matrix for each `k`.
- The fouth row: heatmaps of the signatures for each `k`.

All the plots in panels can be made by individual functions and they are
plotted later in this section.

`select_partition_number()` produces several plots showing different
statistics for choosing "optimized" `k`. There are following statistics:

- eCDF curves of the consensus matrix for each `k`;
- 1-PAC. [The PAC score](https://en.wikipedia.org/wiki/Consensus_clustering#Over-interpretation_potential_of_consensus_clustering)
  measures the proportion of the ambiguous subgrouping.
- Mean silhouette score.
- Concordance. The mean probability of fiting the consensus subgroup labels in all
  partitions.
- Area increased. Denote $A_k$ as the area under the eCDF curve for current
  `k`, the area increased is defined as $A_k - A_{k-1}$.
- Rand index. The percent of pairs of samples that are both in a same cluster
  or both are not in a same cluster in the partition of k and k-1.
- Jaccard index. The ratio of pairs of samples are both in a same cluster in
  the partition of k and k-1 and the pairs of samples are both in a same
  cluster in the partition k or k-1.

The detailed explanations of these statistics can be found in [the _cola_
vignette](https://jokergoo.github.io/cola_vignettes/cola.html#toc_13).

Generally speaking, higher 1-PAC score, higher mean silhouette score or higher
concordance corresponds to better partition. Rand index and Jaccard index
measure how similar the current partition is compared to partition with `k-1`.
If they are too similar, we won't accept `k` is better than `k-1`.

```r
select_partition_number(res)
```

![plot of chunk node-0-select-partition-number](figure_cola/node-0-select-partition-number-1.png)

The numeric values for all these statistics can be obtained by `get_stats()`.

```r
get_stats(res)
```

```
#>   k 1-PAC mean_silhouette concordance area_increased  Rand Jaccard
#> 2 2 0.619           0.803       0.910         0.4391 0.601   0.601
#> 3 3 1.000           0.998       0.999         0.4531 0.742   0.577
#> 4 4 0.864           0.866       0.928         0.1689 0.838   0.581
#> 5 5 0.824           0.830       0.872         0.0395 0.970   0.881
#> 6 6 0.870           0.844       0.904         0.0373 0.964   0.843
#> 7 7 0.812           0.807       0.837         0.0311 0.953   0.787
#> 8 8 0.812           0.634       0.807         0.0297 0.946   0.742
```

`suggest_best_k()` suggests the best $k$ based on these statistics. The rules are as follows:

- All $k$ with Jaccard index larger than 0.95 are removed because increasing
  $k$ does not provide enough extra information. If all $k$ are removed, it is
  marked as no subgroup is detected.
- For all $k$ with 1-PAC score larger than 0.9, the maximal $k$ is taken as
  the best $k$, and other $k$ are marked as optional $k$.
- If it does not fit the second rule. The $k$ with the maximal vote of the
  highest 1-PAC score, highest mean silhouette, and highest concordance is
  taken as the best $k$.

```r
suggest_best_k(res)
```

```
#> [1] 3
```


Following is the table of the partitions (You need to click the **show/hide
code output** link to see it). The membership matrix (columns with name `p*`)
is inferred by
[`clue::cl_consensus()`](https://www.rdocumentation.org/link/cl_consensus?package=clue)
function with the `SE` method. Basically the value in the membership matrix
represents the probability to belong to a certain group. The finall subgroup
label for an item is determined with the group with highest probability it
belongs to.

In `get_classes()` function, the entropy is calculated from the membership
matrix and the silhouette score is calculated from the consensus matrix.



<script>
$( function() {
	$( '#tabs-node-0-get-classes' ).tabs();
} );
</script>
<div id='tabs-node-0-get-classes'>
<ul>
<li><a href='#tab-node-0-get-classes-1'>k = 2</a></li>
<li><a href='#tab-node-0-get-classes-2'>k = 3</a></li>
<li><a href='#tab-node-0-get-classes-3'>k = 4</a></li>
<li><a href='#tab-node-0-get-classes-4'>k = 5</a></li>
<li><a href='#tab-node-0-get-classes-5'>k = 6</a></li>
<li><a href='#tab-node-0-get-classes-6'>k = 7</a></li>
<li><a href='#tab-node-0-get-classes-7'>k = 8</a></li>
</ul>

<div id='tab-node-0-get-classes-1'>
<p><a id='tab-node-0-get-classes-1-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 2), get_membership(res, k = 2))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2
#&gt; TCGA.AB.2888.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2995.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2884.03     1   0.000      0.977 1.00 0.00
#&gt; TCGA.AB.2878.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2998.03     2   0.990      0.417 0.44 0.56
#&gt; TCGA.AB.2913.03     1   0.000      0.977 1.00 0.00
#&gt; TCGA.AB.2883.03     2   0.327      0.839 0.06 0.94
#&gt; TCGA.AB.2957.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2984.03     2   0.469      0.814 0.10 0.90
#&gt; TCGA.AB.2837.03     1   0.000      0.977 1.00 0.00
#&gt; TCGA.AB.2874.03     2   0.634      0.767 0.16 0.84
#&gt; TCGA.AB.2836.03     1   0.000      0.977 1.00 0.00
#&gt; TCGA.AB.2876.03     2   0.990      0.417 0.44 0.56
#&gt; TCGA.AB.2830.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2823.03     2   0.990      0.417 0.44 0.56
#&gt; TCGA.AB.2999.03     2   0.981      0.451 0.42 0.58
#&gt; TCGA.AB.2940.03     2   0.990      0.417 0.44 0.56
#&gt; TCGA.AB.2941.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2987.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2945.03     1   0.000      0.977 1.00 0.00
#&gt; TCGA.AB.2963.03     1   0.000      0.977 1.00 0.00
#&gt; TCGA.AB.2967.03     1   0.000      0.977 1.00 0.00
#&gt; TCGA.AB.2843.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2807.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.3012.03     2   0.990      0.417 0.44 0.56
#&gt; TCGA.AB.2971.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2809.03     1   0.000      0.977 1.00 0.00
#&gt; TCGA.AB.2873.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2802.03     1   0.000      0.977 1.00 0.00
#&gt; TCGA.AB.2851.03     1   0.000      0.977 1.00 0.00
#&gt; TCGA.AB.2853.03     1   0.000      0.977 1.00 0.00
#&gt; TCGA.AB.2847.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2833.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2814.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2898.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2866.03     2   0.981      0.451 0.42 0.58
#&gt; TCGA.AB.2875.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2841.03     2   0.141      0.860 0.02 0.98
#&gt; TCGA.AB.2922.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.3008.03     2   0.990      0.417 0.44 0.56
#&gt; TCGA.AB.2968.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2811.03     1   0.000      0.977 1.00 0.00
#&gt; TCGA.AB.2895.03     1   0.000      0.977 1.00 0.00
#&gt; TCGA.AB.2933.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2827.03     1   0.000      0.977 1.00 0.00
#&gt; TCGA.AB.2942.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2910.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2934.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2959.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2871.03     2   0.469      0.814 0.10 0.90
#&gt; TCGA.AB.2907.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2932.03     1   0.000      0.977 1.00 0.00
#&gt; TCGA.AB.2824.03     1   0.000      0.977 1.00 0.00
#&gt; TCGA.AB.2972.03     1   0.000      0.977 1.00 0.00
#&gt; TCGA.AB.2915.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2970.03     2   0.722      0.730 0.20 0.80
#&gt; TCGA.AB.2949.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2912.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2838.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2872.03     2   0.990      0.417 0.44 0.56
#&gt; TCGA.AB.2897.03     2   0.990      0.417 0.44 0.56
#&gt; TCGA.AB.2965.03     1   0.000      0.977 1.00 0.00
#&gt; TCGA.AB.2891.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2921.03     2   0.990      0.417 0.44 0.56
#&gt; TCGA.AB.2867.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2842.03     1   0.000      0.977 1.00 0.00
#&gt; TCGA.AB.2862.03     2   0.990      0.417 0.44 0.56
#&gt; TCGA.AB.2840.03     2   0.990      0.417 0.44 0.56
#&gt; TCGA.AB.2822.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2832.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2893.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2956.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2903.03     1   0.999     -0.166 0.52 0.48
#&gt; TCGA.AB.2845.03     2   0.855      0.645 0.28 0.72
#&gt; TCGA.AB.2948.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2869.03     1   0.000      0.977 1.00 0.00
#&gt; TCGA.AB.3009.03     2   0.990      0.417 0.44 0.56
#&gt; TCGA.AB.2944.03     2   0.327      0.838 0.06 0.94
#&gt; TCGA.AB.2886.03     2   0.990      0.417 0.44 0.56
#&gt; TCGA.AB.2904.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.3005.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2861.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2917.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2964.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2955.03     2   0.529      0.798 0.12 0.88
#&gt; TCGA.AB.2911.03     1   0.000      0.977 1.00 0.00
#&gt; TCGA.AB.2892.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2817.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2906.03     2   0.990      0.417 0.44 0.56
#&gt; TCGA.AB.2857.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2805.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2983.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2918.03     1   0.000      0.977 1.00 0.00
#&gt; TCGA.AB.2990.03     2   0.469      0.814 0.10 0.90
#&gt; TCGA.AB.2937.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.3006.03     1   0.000      0.977 1.00 0.00
#&gt; TCGA.AB.2829.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2848.03     1   0.000      0.977 1.00 0.00
#&gt; TCGA.AB.2914.03     2   0.990      0.417 0.44 0.56
#&gt; TCGA.AB.3002.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2877.03     2   0.990      0.417 0.44 0.56
#&gt; TCGA.AB.2969.03     1   0.000      0.977 1.00 0.00
#&gt; TCGA.AB.2839.03     1   0.000      0.977 1.00 0.00
#&gt; TCGA.AB.2835.03     1   0.000      0.977 1.00 0.00
#&gt; TCGA.AB.2974.03     1   0.000      0.977 1.00 0.00
#&gt; TCGA.AB.2920.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2980.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2819.03     2   0.990      0.417 0.44 0.56
#&gt; TCGA.AB.2992.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2919.03     2   0.469      0.814 0.10 0.90
#&gt; TCGA.AB.2928.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2927.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2806.03     2   0.990      0.417 0.44 0.56
#&gt; TCGA.AB.2885.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2815.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2996.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2936.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2939.03     2   0.990      0.417 0.44 0.56
#&gt; TCGA.AB.2979.03     2   0.990      0.417 0.44 0.56
#&gt; TCGA.AB.2986.03     1   0.000      0.977 1.00 0.00
#&gt; TCGA.AB.2931.03     1   0.000      0.977 1.00 0.00
#&gt; TCGA.AB.2896.03     1   0.000      0.977 1.00 0.00
#&gt; TCGA.AB.2966.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2820.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2808.03     2   0.990      0.417 0.44 0.56
#&gt; TCGA.AB.2991.03     2   0.990      0.417 0.44 0.56
#&gt; TCGA.AB.2803.03     2   0.981      0.451 0.42 0.58
#&gt; TCGA.AB.2900.03     2   0.469      0.814 0.10 0.90
#&gt; TCGA.AB.2899.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2812.03     1   0.000      0.977 1.00 0.00
#&gt; TCGA.AB.3011.03     1   0.000      0.977 1.00 0.00
#&gt; TCGA.AB.2946.03     1   0.000      0.977 1.00 0.00
#&gt; TCGA.AB.3000.03     2   0.990      0.417 0.44 0.56
#&gt; TCGA.AB.2997.03     2   0.990      0.417 0.44 0.56
#&gt; TCGA.AB.3001.03     2   0.990      0.417 0.44 0.56
#&gt; TCGA.AB.2926.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2856.03     1   0.000      0.977 1.00 0.00
#&gt; TCGA.AB.2977.03     2   0.469      0.814 0.10 0.90
#&gt; TCGA.AB.2879.03     1   0.000      0.977 1.00 0.00
#&gt; TCGA.AB.2976.03     1   0.000      0.977 1.00 0.00
#&gt; TCGA.AB.2989.03     1   0.000      0.977 1.00 0.00
#&gt; TCGA.AB.2849.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2981.03     1   0.000      0.977 1.00 0.00
#&gt; TCGA.AB.2954.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2973.03     1   0.000      0.977 1.00 0.00
#&gt; TCGA.AB.2828.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2804.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2818.03     1   0.000      0.977 1.00 0.00
#&gt; TCGA.AB.2930.03     1   0.000      0.977 1.00 0.00
#&gt; TCGA.AB.2821.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2816.03     1   0.000      0.977 1.00 0.00
#&gt; TCGA.AB.2863.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2950.03     2   0.990      0.417 0.44 0.56
#&gt; TCGA.AB.2925.03     1   0.000      0.977 1.00 0.00
#&gt; TCGA.AB.3007.03     2   0.990      0.417 0.44 0.56
#&gt; TCGA.AB.2882.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2825.03     1   0.000      0.977 1.00 0.00
#&gt; TCGA.AB.2947.03     1   0.000      0.977 1.00 0.00
#&gt; TCGA.AB.2916.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2855.03     2   0.943      0.542 0.36 0.64
#&gt; TCGA.AB.2978.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2952.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2868.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2908.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2938.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2923.03     2   0.469      0.814 0.10 0.90
#&gt; TCGA.AB.2890.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2988.03     1   0.000      0.977 1.00 0.00
#&gt; TCGA.AB.2985.03     1   0.000      0.977 1.00 0.00
#&gt; TCGA.AB.2880.03     2   0.990      0.417 0.44 0.56
#&gt; TCGA.AB.2889.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2887.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2881.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2834.03     2   0.990      0.417 0.44 0.56
#&gt; TCGA.AB.2943.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2982.03     2   0.141      0.860 0.02 0.98
#&gt; TCGA.AB.2844.03     1   0.000      0.977 1.00 0.00
#&gt; TCGA.AB.2870.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2813.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2894.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2909.03     2   0.958      0.513 0.38 0.62
#&gt; TCGA.AB.2858.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2935.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2929.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2831.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2826.03     1   1.000     -0.271 0.50 0.50
#&gt; TCGA.AB.2993.03     1   0.000      0.977 1.00 0.00
#&gt; TCGA.AB.2810.03     2   0.402      0.826 0.08 0.92
#&gt; TCGA.AB.2924.03     1   0.000      0.977 1.00 0.00
#&gt; TCGA.AB.2901.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2975.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2860.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2854.03     2   0.000      0.869 0.00 1.00
#&gt; TCGA.AB.2846.03     2   0.000      0.869 0.00 1.00
</code></pre>

<script>
$('#tab-node-0-get-classes-1-a').parent().next().next().hide();
$('#tab-node-0-get-classes-1-a').click(function(){
  $('#tab-node-0-get-classes-1-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-0-get-classes-2'>
<p><a id='tab-node-0-get-classes-2-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 3), get_membership(res, k = 3))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3
#&gt; TCGA.AB.2888.03     3  0.0000      0.997 0.00 0.00 1.00
#&gt; TCGA.AB.2995.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2884.03     1  0.0000      1.000 1.00 0.00 0.00
#&gt; TCGA.AB.2878.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2998.03     3  0.0000      0.997 0.00 0.00 1.00
#&gt; TCGA.AB.2913.03     1  0.0000      1.000 1.00 0.00 0.00
#&gt; TCGA.AB.2883.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2957.03     3  0.0000      0.997 0.00 0.00 1.00
#&gt; TCGA.AB.2984.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2837.03     1  0.0000      1.000 1.00 0.00 0.00
#&gt; TCGA.AB.2874.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2836.03     1  0.0000      1.000 1.00 0.00 0.00
#&gt; TCGA.AB.2876.03     3  0.0000      0.997 0.00 0.00 1.00
#&gt; TCGA.AB.2830.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2823.03     3  0.0000      0.997 0.00 0.00 1.00
#&gt; TCGA.AB.2999.03     3  0.0000      0.997 0.00 0.00 1.00
#&gt; TCGA.AB.2940.03     3  0.0000      0.997 0.00 0.00 1.00
#&gt; TCGA.AB.2941.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2987.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2945.03     1  0.0000      1.000 1.00 0.00 0.00
#&gt; TCGA.AB.2963.03     1  0.0000      1.000 1.00 0.00 0.00
#&gt; TCGA.AB.2967.03     1  0.0000      1.000 1.00 0.00 0.00
#&gt; TCGA.AB.2843.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2807.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.3012.03     3  0.0000      0.997 0.00 0.00 1.00
#&gt; TCGA.AB.2971.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2809.03     1  0.0000      1.000 1.00 0.00 0.00
#&gt; TCGA.AB.2873.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2802.03     1  0.0000      1.000 1.00 0.00 0.00
#&gt; TCGA.AB.2851.03     1  0.0000      1.000 1.00 0.00 0.00
#&gt; TCGA.AB.2853.03     1  0.0000      1.000 1.00 0.00 0.00
#&gt; TCGA.AB.2847.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2833.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2814.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2898.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2866.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2875.03     3  0.0000      0.997 0.00 0.00 1.00
#&gt; TCGA.AB.2841.03     3  0.0000      0.997 0.00 0.00 1.00
#&gt; TCGA.AB.2922.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.3008.03     3  0.0000      0.997 0.00 0.00 1.00
#&gt; TCGA.AB.2968.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2811.03     1  0.0000      1.000 1.00 0.00 0.00
#&gt; TCGA.AB.2895.03     1  0.0000      1.000 1.00 0.00 0.00
#&gt; TCGA.AB.2933.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2827.03     1  0.0000      1.000 1.00 0.00 0.00
#&gt; TCGA.AB.2942.03     3  0.0000      0.997 0.00 0.00 1.00
#&gt; TCGA.AB.2910.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2934.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2959.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2871.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2907.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2932.03     1  0.0000      1.000 1.00 0.00 0.00
#&gt; TCGA.AB.2824.03     1  0.0000      1.000 1.00 0.00 0.00
#&gt; TCGA.AB.2972.03     1  0.0000      1.000 1.00 0.00 0.00
#&gt; TCGA.AB.2915.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2970.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2949.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2912.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2838.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2872.03     3  0.0000      0.997 0.00 0.00 1.00
#&gt; TCGA.AB.2897.03     3  0.0000      0.997 0.00 0.00 1.00
#&gt; TCGA.AB.2965.03     1  0.0000      1.000 1.00 0.00 0.00
#&gt; TCGA.AB.2891.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2921.03     3  0.0000      0.997 0.00 0.00 1.00
#&gt; TCGA.AB.2867.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2842.03     1  0.0000      1.000 1.00 0.00 0.00
#&gt; TCGA.AB.2862.03     3  0.0000      0.997 0.00 0.00 1.00
#&gt; TCGA.AB.2840.03     3  0.0000      0.997 0.00 0.00 1.00
#&gt; TCGA.AB.2822.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2832.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2893.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2956.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2903.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2845.03     3  0.0000      0.997 0.00 0.00 1.00
#&gt; TCGA.AB.2948.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2869.03     1  0.0000      1.000 1.00 0.00 0.00
#&gt; TCGA.AB.3009.03     3  0.3340      0.850 0.00 0.12 0.88
#&gt; TCGA.AB.2944.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2886.03     3  0.0000      0.997 0.00 0.00 1.00
#&gt; TCGA.AB.2904.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.3005.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2861.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2917.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2964.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2955.03     3  0.0000      0.997 0.00 0.00 1.00
#&gt; TCGA.AB.2911.03     1  0.0000      1.000 1.00 0.00 0.00
#&gt; TCGA.AB.2892.03     3  0.0000      0.997 0.00 0.00 1.00
#&gt; TCGA.AB.2817.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2906.03     3  0.0000      0.997 0.00 0.00 1.00
#&gt; TCGA.AB.2857.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2805.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2983.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2918.03     1  0.0000      1.000 1.00 0.00 0.00
#&gt; TCGA.AB.2990.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2937.03     3  0.0000      0.997 0.00 0.00 1.00
#&gt; TCGA.AB.3006.03     1  0.0000      1.000 1.00 0.00 0.00
#&gt; TCGA.AB.2829.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2848.03     1  0.0000      1.000 1.00 0.00 0.00
#&gt; TCGA.AB.2914.03     3  0.0000      0.997 0.00 0.00 1.00
#&gt; TCGA.AB.3002.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2877.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2969.03     1  0.0000      1.000 1.00 0.00 0.00
#&gt; TCGA.AB.2839.03     1  0.0000      1.000 1.00 0.00 0.00
#&gt; TCGA.AB.2835.03     1  0.0000      1.000 1.00 0.00 0.00
#&gt; TCGA.AB.2974.03     1  0.0000      1.000 1.00 0.00 0.00
#&gt; TCGA.AB.2920.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2980.03     3  0.0000      0.997 0.00 0.00 1.00
#&gt; TCGA.AB.2819.03     3  0.0000      0.997 0.00 0.00 1.00
#&gt; TCGA.AB.2992.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2919.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2928.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2927.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2806.03     3  0.0000      0.997 0.00 0.00 1.00
#&gt; TCGA.AB.2885.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2815.03     3  0.0000      0.997 0.00 0.00 1.00
#&gt; TCGA.AB.2996.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2936.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2939.03     3  0.0000      0.997 0.00 0.00 1.00
#&gt; TCGA.AB.2979.03     3  0.0000      0.997 0.00 0.00 1.00
#&gt; TCGA.AB.2986.03     1  0.0000      1.000 1.00 0.00 0.00
#&gt; TCGA.AB.2931.03     1  0.0000      1.000 1.00 0.00 0.00
#&gt; TCGA.AB.2896.03     1  0.0000      1.000 1.00 0.00 0.00
#&gt; TCGA.AB.2966.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2820.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2808.03     3  0.0000      0.997 0.00 0.00 1.00
#&gt; TCGA.AB.2991.03     3  0.0000      0.997 0.00 0.00 1.00
#&gt; TCGA.AB.2803.03     3  0.0000      0.997 0.00 0.00 1.00
#&gt; TCGA.AB.2900.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2899.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2812.03     1  0.0000      1.000 1.00 0.00 0.00
#&gt; TCGA.AB.3011.03     1  0.0000      1.000 1.00 0.00 0.00
#&gt; TCGA.AB.2946.03     1  0.0000      1.000 1.00 0.00 0.00
#&gt; TCGA.AB.3000.03     3  0.0000      0.997 0.00 0.00 1.00
#&gt; TCGA.AB.2997.03     3  0.0000      0.997 0.00 0.00 1.00
#&gt; TCGA.AB.3001.03     3  0.0000      0.997 0.00 0.00 1.00
#&gt; TCGA.AB.2926.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2856.03     1  0.0000      1.000 1.00 0.00 0.00
#&gt; TCGA.AB.2977.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2879.03     1  0.0000      1.000 1.00 0.00 0.00
#&gt; TCGA.AB.2976.03     1  0.0000      1.000 1.00 0.00 0.00
#&gt; TCGA.AB.2989.03     1  0.0000      1.000 1.00 0.00 0.00
#&gt; TCGA.AB.2849.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2981.03     1  0.0000      1.000 1.00 0.00 0.00
#&gt; TCGA.AB.2954.03     3  0.0000      0.997 0.00 0.00 1.00
#&gt; TCGA.AB.2973.03     1  0.0000      1.000 1.00 0.00 0.00
#&gt; TCGA.AB.2828.03     3  0.0000      0.997 0.00 0.00 1.00
#&gt; TCGA.AB.2804.03     3  0.0000      0.997 0.00 0.00 1.00
#&gt; TCGA.AB.2818.03     1  0.0000      1.000 1.00 0.00 0.00
#&gt; TCGA.AB.2930.03     1  0.0892      0.980 0.98 0.00 0.02
#&gt; TCGA.AB.2821.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2816.03     1  0.0000      1.000 1.00 0.00 0.00
#&gt; TCGA.AB.2863.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2950.03     3  0.0000      0.997 0.00 0.00 1.00
#&gt; TCGA.AB.2925.03     1  0.0000      1.000 1.00 0.00 0.00
#&gt; TCGA.AB.3007.03     3  0.0000      0.997 0.00 0.00 1.00
#&gt; TCGA.AB.2882.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2825.03     1  0.0000      1.000 1.00 0.00 0.00
#&gt; TCGA.AB.2947.03     1  0.0000      1.000 1.00 0.00 0.00
#&gt; TCGA.AB.2916.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2855.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2978.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2952.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2868.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2908.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2938.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2923.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2890.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2988.03     1  0.0000      1.000 1.00 0.00 0.00
#&gt; TCGA.AB.2985.03     1  0.0000      1.000 1.00 0.00 0.00
#&gt; TCGA.AB.2880.03     3  0.0000      0.997 0.00 0.00 1.00
#&gt; TCGA.AB.2889.03     3  0.0000      0.997 0.00 0.00 1.00
#&gt; TCGA.AB.2887.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2881.03     3  0.0000      0.997 0.00 0.00 1.00
#&gt; TCGA.AB.2834.03     2  0.0892      0.980 0.00 0.98 0.02
#&gt; TCGA.AB.2943.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2982.03     3  0.0000      0.997 0.00 0.00 1.00
#&gt; TCGA.AB.2844.03     1  0.0000      1.000 1.00 0.00 0.00
#&gt; TCGA.AB.2870.03     3  0.0000      0.997 0.00 0.00 1.00
#&gt; TCGA.AB.2813.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2894.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2909.03     3  0.0000      0.997 0.00 0.00 1.00
#&gt; TCGA.AB.2858.03     3  0.0000      0.997 0.00 0.00 1.00
#&gt; TCGA.AB.2935.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2929.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2831.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2826.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2993.03     1  0.0000      1.000 1.00 0.00 0.00
#&gt; TCGA.AB.2810.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2924.03     1  0.0000      1.000 1.00 0.00 0.00
#&gt; TCGA.AB.2901.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2975.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2860.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2854.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2846.03     3  0.0000      0.997 0.00 0.00 1.00
</code></pre>

<script>
$('#tab-node-0-get-classes-2-a').parent().next().next().hide();
$('#tab-node-0-get-classes-2-a').click(function(){
  $('#tab-node-0-get-classes-2-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-0-get-classes-3'>
<p><a id='tab-node-0-get-classes-3-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 4), get_membership(res, k = 4))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4
#&gt; TCGA.AB.2888.03     3  0.0000     0.9866 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2995.03     4  0.0000     0.9687 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2884.03     1  0.1211     0.9248 0.96 0.04 0.00 0.00
#&gt; TCGA.AB.2878.03     2  0.1637     0.8605 0.00 0.94 0.00 0.06
#&gt; TCGA.AB.2998.03     3  0.0000     0.9866 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2913.03     1  0.0707     0.9348 0.98 0.02 0.00 0.00
#&gt; TCGA.AB.2883.03     4  0.2647     0.8311 0.00 0.12 0.00 0.88
#&gt; TCGA.AB.2957.03     3  0.0000     0.9866 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2984.03     2  0.1211     0.8591 0.00 0.96 0.00 0.04
#&gt; TCGA.AB.2837.03     1  0.0707     0.9348 0.98 0.02 0.00 0.00
#&gt; TCGA.AB.2874.03     2  0.1211     0.8591 0.00 0.96 0.00 0.04
#&gt; TCGA.AB.2836.03     1  0.0707     0.9348 0.98 0.02 0.00 0.00
#&gt; TCGA.AB.2876.03     2  0.4907     0.3152 0.00 0.58 0.42 0.00
#&gt; TCGA.AB.2830.03     4  0.0000     0.9687 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2823.03     3  0.0000     0.9866 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2999.03     3  0.0000     0.9866 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2940.03     2  0.4907     0.3152 0.00 0.58 0.42 0.00
#&gt; TCGA.AB.2941.03     4  0.0000     0.9687 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2987.03     4  0.0000     0.9687 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2945.03     1  0.0000     0.9309 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2963.03     1  0.0707     0.9348 0.98 0.02 0.00 0.00
#&gt; TCGA.AB.2967.03     1  0.0707     0.9348 0.98 0.02 0.00 0.00
#&gt; TCGA.AB.2843.03     2  0.4713     0.4944 0.00 0.64 0.00 0.36
#&gt; TCGA.AB.2807.03     4  0.4522     0.4797 0.00 0.32 0.00 0.68
#&gt; TCGA.AB.3012.03     3  0.0000     0.9866 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2971.03     4  0.0000     0.9687 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2809.03     1  0.1211     0.9248 0.96 0.04 0.00 0.00
#&gt; TCGA.AB.2873.03     4  0.0000     0.9687 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2802.03     1  0.1211     0.9248 0.96 0.04 0.00 0.00
#&gt; TCGA.AB.2851.03     1  0.0707     0.9348 0.98 0.02 0.00 0.00
#&gt; TCGA.AB.2853.03     1  0.1211     0.9248 0.96 0.04 0.00 0.00
#&gt; TCGA.AB.2847.03     2  0.3172     0.7968 0.00 0.84 0.00 0.16
#&gt; TCGA.AB.2833.03     4  0.0000     0.9687 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2814.03     2  0.1637     0.8605 0.00 0.94 0.00 0.06
#&gt; TCGA.AB.2898.03     4  0.0000     0.9687 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2866.03     2  0.1211     0.8591 0.00 0.96 0.00 0.04
#&gt; TCGA.AB.2875.03     3  0.0000     0.9866 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2841.03     3  0.0000     0.9866 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2922.03     4  0.0000     0.9687 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.3008.03     2  0.4855     0.3622 0.00 0.60 0.40 0.00
#&gt; TCGA.AB.2968.03     4  0.0000     0.9687 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2811.03     1  0.1211     0.9248 0.96 0.04 0.00 0.00
#&gt; TCGA.AB.2895.03     1  0.1211     0.9248 0.96 0.04 0.00 0.00
#&gt; TCGA.AB.2933.03     4  0.0000     0.9687 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2827.03     1  0.4134     0.7066 0.74 0.26 0.00 0.00
#&gt; TCGA.AB.2942.03     3  0.0000     0.9866 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2910.03     4  0.0000     0.9687 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2934.03     4  0.0000     0.9687 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2959.03     2  0.3172     0.7968 0.00 0.84 0.00 0.16
#&gt; TCGA.AB.2871.03     2  0.1211     0.8591 0.00 0.96 0.00 0.04
#&gt; TCGA.AB.2907.03     2  0.4624     0.5353 0.00 0.66 0.00 0.34
#&gt; TCGA.AB.2932.03     1  0.0707     0.9348 0.98 0.02 0.00 0.00
#&gt; TCGA.AB.2824.03     1  0.0707     0.9348 0.98 0.02 0.00 0.00
#&gt; TCGA.AB.2972.03     1  0.0707     0.9348 0.98 0.02 0.00 0.00
#&gt; TCGA.AB.2915.03     2  0.4406     0.6118 0.00 0.70 0.00 0.30
#&gt; TCGA.AB.2970.03     2  0.1411     0.8476 0.02 0.96 0.00 0.02
#&gt; TCGA.AB.2949.03     4  0.0000     0.9687 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2912.03     2  0.1637     0.8605 0.00 0.94 0.00 0.06
#&gt; TCGA.AB.2838.03     2  0.1637     0.8605 0.00 0.94 0.00 0.06
#&gt; TCGA.AB.2872.03     3  0.0000     0.9866 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2897.03     3  0.0000     0.9866 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2965.03     1  0.1211     0.9248 0.96 0.04 0.00 0.00
#&gt; TCGA.AB.2891.03     2  0.3400     0.7767 0.00 0.82 0.00 0.18
#&gt; TCGA.AB.2921.03     2  0.4907     0.3152 0.00 0.58 0.42 0.00
#&gt; TCGA.AB.2867.03     4  0.0000     0.9687 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2842.03     1  0.0707     0.9348 0.98 0.02 0.00 0.00
#&gt; TCGA.AB.2862.03     3  0.0000     0.9866 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2840.03     3  0.0000     0.9866 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2822.03     2  0.4790     0.4475 0.00 0.62 0.00 0.38
#&gt; TCGA.AB.2832.03     4  0.0000     0.9687 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2893.03     4  0.0000     0.9687 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2956.03     4  0.0000     0.9687 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2903.03     2  0.1211     0.8591 0.00 0.96 0.00 0.04
#&gt; TCGA.AB.2845.03     2  0.4907     0.3305 0.00 0.58 0.42 0.00
#&gt; TCGA.AB.2948.03     4  0.0000     0.9687 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2869.03     1  0.0000     0.9309 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.3009.03     2  0.1211     0.8363 0.00 0.96 0.04 0.00
#&gt; TCGA.AB.2944.03     2  0.1211     0.8591 0.00 0.96 0.00 0.04
#&gt; TCGA.AB.2886.03     3  0.0000     0.9866 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2904.03     4  0.0000     0.9687 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.3005.03     4  0.0000     0.9687 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2861.03     4  0.0000     0.9687 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2917.03     4  0.0000     0.9687 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2964.03     2  0.1637     0.8605 0.00 0.94 0.00 0.06
#&gt; TCGA.AB.2955.03     3  0.0000     0.9866 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2911.03     1  0.4522     0.6147 0.68 0.32 0.00 0.00
#&gt; TCGA.AB.2892.03     3  0.0000     0.9866 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2817.03     4  0.0000     0.9687 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2906.03     3  0.0000     0.9866 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2857.03     4  0.0000     0.9687 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2805.03     2  0.3610     0.7544 0.00 0.80 0.00 0.20
#&gt; TCGA.AB.2983.03     2  0.1637     0.8605 0.00 0.94 0.00 0.06
#&gt; TCGA.AB.2918.03     1  0.3610     0.7820 0.80 0.20 0.00 0.00
#&gt; TCGA.AB.2990.03     2  0.1211     0.8591 0.00 0.96 0.00 0.04
#&gt; TCGA.AB.2937.03     3  0.0000     0.9866 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.3006.03     1  0.2345     0.8802 0.90 0.10 0.00 0.00
#&gt; TCGA.AB.2829.03     4  0.0000     0.9687 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2848.03     1  0.1211     0.9248 0.96 0.04 0.00 0.00
#&gt; TCGA.AB.2914.03     3  0.0000     0.9866 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.3002.03     2  0.1637     0.8605 0.00 0.94 0.00 0.06
#&gt; TCGA.AB.2877.03     2  0.1411     0.8476 0.02 0.96 0.00 0.02
#&gt; TCGA.AB.2969.03     1  0.1211     0.9248 0.96 0.04 0.00 0.00
#&gt; TCGA.AB.2839.03     1  0.0707     0.9348 0.98 0.02 0.00 0.00
#&gt; TCGA.AB.2835.03     1  0.0707     0.9348 0.98 0.02 0.00 0.00
#&gt; TCGA.AB.2974.03     1  0.1211     0.9248 0.96 0.04 0.00 0.00
#&gt; TCGA.AB.2920.03     2  0.1637     0.8605 0.00 0.94 0.00 0.06
#&gt; TCGA.AB.2980.03     3  0.0000     0.9866 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2819.03     3  0.0000     0.9866 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2992.03     4  0.0000     0.9687 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2919.03     2  0.1211     0.8591 0.00 0.96 0.00 0.04
#&gt; TCGA.AB.2928.03     4  0.0000     0.9687 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2927.03     4  0.0000     0.9687 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2806.03     3  0.0000     0.9866 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2885.03     2  0.3172     0.7968 0.00 0.84 0.00 0.16
#&gt; TCGA.AB.2815.03     3  0.0000     0.9866 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2996.03     4  0.0000     0.9687 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2936.03     4  0.4790     0.3286 0.00 0.38 0.00 0.62
#&gt; TCGA.AB.2939.03     2  0.4855     0.3622 0.00 0.60 0.40 0.00
#&gt; TCGA.AB.2979.03     2  0.4948     0.2790 0.00 0.56 0.44 0.00
#&gt; TCGA.AB.2986.03     1  0.0707     0.9348 0.98 0.02 0.00 0.00
#&gt; TCGA.AB.2931.03     1  0.1211     0.9248 0.96 0.04 0.00 0.00
#&gt; TCGA.AB.2896.03     1  0.1211     0.9248 0.96 0.04 0.00 0.00
#&gt; TCGA.AB.2966.03     2  0.1637     0.8605 0.00 0.94 0.00 0.06
#&gt; TCGA.AB.2820.03     4  0.0000     0.9687 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2808.03     2  0.4948     0.2790 0.00 0.56 0.44 0.00
#&gt; TCGA.AB.2991.03     3  0.0000     0.9866 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2803.03     3  0.0000     0.9866 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2900.03     2  0.1211     0.8591 0.00 0.96 0.00 0.04
#&gt; TCGA.AB.2899.03     2  0.1637     0.8605 0.00 0.94 0.00 0.06
#&gt; TCGA.AB.2812.03     1  0.0707     0.9348 0.98 0.02 0.00 0.00
#&gt; TCGA.AB.3011.03     1  0.0707     0.9348 0.98 0.02 0.00 0.00
#&gt; TCGA.AB.2946.03     1  0.4522     0.6147 0.68 0.32 0.00 0.00
#&gt; TCGA.AB.3000.03     2  0.4855     0.3622 0.00 0.60 0.40 0.00
#&gt; TCGA.AB.2997.03     3  0.0000     0.9866 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.3001.03     3  0.0000     0.9866 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2926.03     2  0.1637     0.8605 0.00 0.94 0.00 0.06
#&gt; TCGA.AB.2856.03     1  0.4522     0.6147 0.68 0.32 0.00 0.00
#&gt; TCGA.AB.2977.03     2  0.1211     0.8591 0.00 0.96 0.00 0.04
#&gt; TCGA.AB.2879.03     1  0.0707     0.9348 0.98 0.02 0.00 0.00
#&gt; TCGA.AB.2976.03     1  0.0707     0.9348 0.98 0.02 0.00 0.00
#&gt; TCGA.AB.2989.03     1  0.0707     0.9348 0.98 0.02 0.00 0.00
#&gt; TCGA.AB.2849.03     2  0.1637     0.8605 0.00 0.94 0.00 0.06
#&gt; TCGA.AB.2981.03     1  0.1211     0.9248 0.96 0.04 0.00 0.00
#&gt; TCGA.AB.2954.03     3  0.0000     0.9866 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2973.03     1  0.4277     0.6782 0.72 0.28 0.00 0.00
#&gt; TCGA.AB.2828.03     3  0.0000     0.9866 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2804.03     3  0.0000     0.9866 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2818.03     1  0.0707     0.9348 0.98 0.02 0.00 0.00
#&gt; TCGA.AB.2930.03     1  0.4522     0.6147 0.68 0.32 0.00 0.00
#&gt; TCGA.AB.2821.03     2  0.1637     0.8605 0.00 0.94 0.00 0.06
#&gt; TCGA.AB.2816.03     1  0.0707     0.9348 0.98 0.02 0.00 0.00
#&gt; TCGA.AB.2863.03     2  0.2345     0.8415 0.00 0.90 0.00 0.10
#&gt; TCGA.AB.2950.03     3  0.0000     0.9866 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2925.03     1  0.1211     0.9248 0.96 0.04 0.00 0.00
#&gt; TCGA.AB.3007.03     3  0.0000     0.9866 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2882.03     2  0.2921     0.8136 0.00 0.86 0.00 0.14
#&gt; TCGA.AB.2825.03     1  0.1211     0.9248 0.96 0.04 0.00 0.00
#&gt; TCGA.AB.2947.03     1  0.1211     0.9248 0.96 0.04 0.00 0.00
#&gt; TCGA.AB.2916.03     4  0.0000     0.9687 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2855.03     2  0.1211     0.8591 0.00 0.96 0.00 0.04
#&gt; TCGA.AB.2978.03     4  0.0000     0.9687 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2952.03     2  0.1637     0.8605 0.00 0.94 0.00 0.06
#&gt; TCGA.AB.2868.03     2  0.3610     0.7544 0.00 0.80 0.00 0.20
#&gt; TCGA.AB.2908.03     4  0.0000     0.9687 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2938.03     4  0.0000     0.9687 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2923.03     2  0.1211     0.8591 0.00 0.96 0.00 0.04
#&gt; TCGA.AB.2890.03     4  0.4790     0.3268 0.00 0.38 0.00 0.62
#&gt; TCGA.AB.2988.03     1  0.1211     0.9248 0.96 0.04 0.00 0.00
#&gt; TCGA.AB.2985.03     1  0.0707     0.9348 0.98 0.02 0.00 0.00
#&gt; TCGA.AB.2880.03     3  0.4977     0.0272 0.00 0.46 0.54 0.00
#&gt; TCGA.AB.2889.03     3  0.0000     0.9866 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2887.03     4  0.0000     0.9687 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2881.03     3  0.0000     0.9866 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2834.03     2  0.1211     0.8329 0.04 0.96 0.00 0.00
#&gt; TCGA.AB.2943.03     4  0.0000     0.9687 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2982.03     3  0.0000     0.9866 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2844.03     1  0.4522     0.6147 0.68 0.32 0.00 0.00
#&gt; TCGA.AB.2870.03     3  0.0000     0.9866 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2813.03     4  0.0000     0.9687 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2894.03     4  0.0000     0.9687 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2909.03     3  0.0000     0.9866 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2858.03     3  0.0000     0.9866 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2935.03     2  0.2345     0.8413 0.00 0.90 0.00 0.10
#&gt; TCGA.AB.2929.03     2  0.2647     0.8288 0.00 0.88 0.00 0.12
#&gt; TCGA.AB.2831.03     4  0.0000     0.9687 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2826.03     2  0.1211     0.8329 0.04 0.96 0.00 0.00
#&gt; TCGA.AB.2993.03     1  0.0707     0.9348 0.98 0.02 0.00 0.00
#&gt; TCGA.AB.2810.03     2  0.1211     0.8591 0.00 0.96 0.00 0.04
#&gt; TCGA.AB.2924.03     1  0.0707     0.9348 0.98 0.02 0.00 0.00
#&gt; TCGA.AB.2901.03     2  0.1637     0.8605 0.00 0.94 0.00 0.06
#&gt; TCGA.AB.2975.03     4  0.0000     0.9687 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2860.03     2  0.2647     0.8287 0.00 0.88 0.00 0.12
#&gt; TCGA.AB.2854.03     2  0.4624     0.5353 0.00 0.66 0.00 0.34
#&gt; TCGA.AB.2846.03     3  0.0000     0.9866 0.00 0.00 1.00 0.00
</code></pre>

<script>
$('#tab-node-0-get-classes-3-a').parent().next().next().hide();
$('#tab-node-0-get-classes-3-a').click(function(){
  $('#tab-node-0-get-classes-3-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-0-get-classes-4'>
<p><a id='tab-node-0-get-classes-4-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 5), get_membership(res, k = 5))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5
#&gt; TCGA.AB.2888.03     3  0.4767     0.8012 0.00 0.02 0.56 0.00 0.42
#&gt; TCGA.AB.2995.03     4  0.0000     0.9578 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2884.03     5  0.4767     0.9544 0.42 0.02 0.00 0.00 0.56
#&gt; TCGA.AB.2878.03     2  0.0609     0.8842 0.00 0.98 0.00 0.02 0.00
#&gt; TCGA.AB.2998.03     3  0.0000     0.7824 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2913.03     1  0.0000     0.8973 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2883.03     4  0.2516     0.8036 0.00 0.14 0.00 0.86 0.00
#&gt; TCGA.AB.2957.03     3  0.4767     0.8012 0.00 0.02 0.56 0.00 0.42
#&gt; TCGA.AB.2984.03     2  0.0609     0.8842 0.00 0.98 0.00 0.02 0.00
#&gt; TCGA.AB.2837.03     1  0.0000     0.8973 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2874.03     2  0.0609     0.8719 0.02 0.98 0.00 0.00 0.00
#&gt; TCGA.AB.2836.03     1  0.0000     0.8973 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2876.03     2  0.5631     0.2392 0.02 0.54 0.40 0.00 0.04
#&gt; TCGA.AB.2830.03     4  0.0000     0.9578 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2823.03     3  0.0000     0.7824 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2999.03     3  0.0000     0.7824 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2940.03     2  0.5631     0.2392 0.02 0.54 0.40 0.00 0.04
#&gt; TCGA.AB.2941.03     4  0.0000     0.9578 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2987.03     4  0.0000     0.9578 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2945.03     1  0.0609     0.8636 0.98 0.00 0.00 0.00 0.02
#&gt; TCGA.AB.2963.03     1  0.0000     0.8973 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2967.03     1  0.0000     0.8973 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2843.03     2  0.2929     0.7510 0.00 0.82 0.00 0.18 0.00
#&gt; TCGA.AB.2807.03     4  0.4182     0.3278 0.00 0.40 0.00 0.60 0.00
#&gt; TCGA.AB.3012.03     3  0.0000     0.7824 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2971.03     4  0.0000     0.9578 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2809.03     5  0.4227     0.9881 0.42 0.00 0.00 0.00 0.58
#&gt; TCGA.AB.2873.03     4  0.0000     0.9578 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2802.03     5  0.4227     0.9881 0.42 0.00 0.00 0.00 0.58
#&gt; TCGA.AB.2851.03     1  0.0000     0.8973 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2853.03     5  0.4227     0.9881 0.42 0.00 0.00 0.00 0.58
#&gt; TCGA.AB.2847.03     2  0.1732     0.8509 0.00 0.92 0.00 0.08 0.00
#&gt; TCGA.AB.2833.03     4  0.0000     0.9578 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2814.03     2  0.0609     0.8842 0.00 0.98 0.00 0.02 0.00
#&gt; TCGA.AB.2898.03     4  0.0000     0.9578 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2866.03     2  0.0609     0.8719 0.02 0.98 0.00 0.00 0.00
#&gt; TCGA.AB.2875.03     3  0.4726     0.8051 0.00 0.02 0.58 0.00 0.40
#&gt; TCGA.AB.2841.03     3  0.0000     0.7824 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2922.03     4  0.0609     0.9401 0.00 0.02 0.00 0.98 0.00
#&gt; TCGA.AB.3008.03     2  0.5631     0.2392 0.02 0.54 0.40 0.00 0.04
#&gt; TCGA.AB.2968.03     4  0.0000     0.9578 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2811.03     5  0.4287     0.9291 0.46 0.00 0.00 0.00 0.54
#&gt; TCGA.AB.2895.03     5  0.4227     0.9881 0.42 0.00 0.00 0.00 0.58
#&gt; TCGA.AB.2933.03     4  0.0000     0.9578 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2827.03     1  0.2020     0.7742 0.90 0.10 0.00 0.00 0.00
#&gt; TCGA.AB.2942.03     3  0.4767     0.8012 0.00 0.02 0.56 0.00 0.42
#&gt; TCGA.AB.2910.03     4  0.0000     0.9578 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2934.03     4  0.0000     0.9578 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2959.03     2  0.1410     0.8651 0.00 0.94 0.00 0.06 0.00
#&gt; TCGA.AB.2871.03     2  0.0609     0.8842 0.00 0.98 0.00 0.02 0.00
#&gt; TCGA.AB.2907.03     2  0.3109     0.7234 0.00 0.80 0.00 0.20 0.00
#&gt; TCGA.AB.2932.03     1  0.0000     0.8973 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2824.03     1  0.0000     0.8973 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2972.03     1  0.0000     0.8973 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2915.03     2  0.2929     0.7510 0.00 0.82 0.00 0.18 0.00
#&gt; TCGA.AB.2970.03     2  0.0609     0.8719 0.02 0.98 0.00 0.00 0.00
#&gt; TCGA.AB.2949.03     4  0.0000     0.9578 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2912.03     2  0.0609     0.8842 0.00 0.98 0.00 0.02 0.00
#&gt; TCGA.AB.2838.03     2  0.0609     0.8842 0.00 0.98 0.00 0.02 0.00
#&gt; TCGA.AB.2872.03     3  0.0000     0.7824 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2897.03     3  0.0000     0.7824 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2965.03     5  0.4227     0.9881 0.42 0.00 0.00 0.00 0.58
#&gt; TCGA.AB.2891.03     2  0.2280     0.8180 0.00 0.88 0.00 0.12 0.00
#&gt; TCGA.AB.2921.03     2  0.5631     0.2392 0.02 0.54 0.40 0.00 0.04
#&gt; TCGA.AB.2867.03     4  0.0000     0.9578 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2842.03     1  0.0000     0.8973 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2862.03     3  0.0000     0.7824 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2840.03     3  0.0000     0.7824 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2822.03     2  0.3424     0.6627 0.00 0.76 0.00 0.24 0.00
#&gt; TCGA.AB.2832.03     4  0.0000     0.9578 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2893.03     4  0.0000     0.9578 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2956.03     4  0.0000     0.9578 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2903.03     2  0.0609     0.8842 0.00 0.98 0.00 0.02 0.00
#&gt; TCGA.AB.2845.03     2  0.5631     0.2392 0.02 0.54 0.40 0.00 0.04
#&gt; TCGA.AB.2948.03     4  0.0000     0.9578 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2869.03     1  0.0609     0.8636 0.98 0.00 0.00 0.00 0.02
#&gt; TCGA.AB.3009.03     2  0.0609     0.8719 0.02 0.98 0.00 0.00 0.00
#&gt; TCGA.AB.2944.03     2  0.0609     0.8842 0.00 0.98 0.00 0.02 0.00
#&gt; TCGA.AB.2886.03     3  0.4726     0.8051 0.00 0.02 0.58 0.00 0.40
#&gt; TCGA.AB.2904.03     4  0.0000     0.9578 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.3005.03     4  0.0000     0.9578 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2861.03     4  0.0000     0.9578 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2917.03     4  0.0609     0.9401 0.00 0.02 0.00 0.98 0.00
#&gt; TCGA.AB.2964.03     2  0.0609     0.8842 0.00 0.98 0.00 0.02 0.00
#&gt; TCGA.AB.2955.03     3  0.5484     0.7569 0.00 0.12 0.64 0.00 0.24
#&gt; TCGA.AB.2911.03     1  0.3109     0.6274 0.80 0.20 0.00 0.00 0.00
#&gt; TCGA.AB.2892.03     3  0.4767     0.8012 0.00 0.02 0.56 0.00 0.42
#&gt; TCGA.AB.2817.03     4  0.0000     0.9578 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2906.03     3  0.0000     0.7824 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2857.03     4  0.0000     0.9578 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2805.03     2  0.1732     0.8509 0.00 0.92 0.00 0.08 0.00
#&gt; TCGA.AB.2983.03     2  0.0609     0.8842 0.00 0.98 0.00 0.02 0.00
#&gt; TCGA.AB.2918.03     1  0.2020     0.7742 0.90 0.10 0.00 0.00 0.00
#&gt; TCGA.AB.2990.03     2  0.0609     0.8842 0.00 0.98 0.00 0.02 0.00
#&gt; TCGA.AB.2937.03     3  0.4726     0.8051 0.00 0.02 0.58 0.00 0.40
#&gt; TCGA.AB.3006.03     1  0.1410     0.8254 0.94 0.06 0.00 0.00 0.00
#&gt; TCGA.AB.2829.03     4  0.0000     0.9578 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2848.03     1  0.0000     0.8973 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2914.03     3  0.4767     0.8012 0.00 0.02 0.56 0.00 0.42
#&gt; TCGA.AB.3002.03     2  0.0609     0.8842 0.00 0.98 0.00 0.02 0.00
#&gt; TCGA.AB.2877.03     2  0.0609     0.8719 0.02 0.98 0.00 0.00 0.00
#&gt; TCGA.AB.2969.03     5  0.4227     0.9881 0.42 0.00 0.00 0.00 0.58
#&gt; TCGA.AB.2839.03     1  0.0000     0.8973 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2835.03     1  0.0000     0.8973 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2974.03     5  0.4227     0.9881 0.42 0.00 0.00 0.00 0.58
#&gt; TCGA.AB.2920.03     2  0.0609     0.8842 0.00 0.98 0.00 0.02 0.00
#&gt; TCGA.AB.2980.03     3  0.0609     0.7714 0.00 0.00 0.98 0.02 0.00
#&gt; TCGA.AB.2819.03     3  0.4726     0.8051 0.00 0.02 0.58 0.00 0.40
#&gt; TCGA.AB.2992.03     4  0.0000     0.9578 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2919.03     2  0.0609     0.8842 0.00 0.98 0.00 0.02 0.00
#&gt; TCGA.AB.2928.03     4  0.0000     0.9578 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2927.03     4  0.0000     0.9578 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2806.03     3  0.4726     0.8051 0.00 0.02 0.58 0.00 0.40
#&gt; TCGA.AB.2885.03     2  0.1410     0.8651 0.00 0.94 0.00 0.06 0.00
#&gt; TCGA.AB.2815.03     3  0.4767     0.8012 0.00 0.02 0.56 0.00 0.42
#&gt; TCGA.AB.2996.03     4  0.0000     0.9578 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2936.03     4  0.4262     0.2163 0.00 0.44 0.00 0.56 0.00
#&gt; TCGA.AB.2939.03     2  0.5631     0.2392 0.02 0.54 0.40 0.00 0.04
#&gt; TCGA.AB.2979.03     2  0.5631     0.2392 0.02 0.54 0.40 0.00 0.04
#&gt; TCGA.AB.2986.03     1  0.0000     0.8973 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2931.03     5  0.4227     0.9881 0.42 0.00 0.00 0.00 0.58
#&gt; TCGA.AB.2896.03     5  0.4227     0.9881 0.42 0.00 0.00 0.00 0.58
#&gt; TCGA.AB.2966.03     2  0.0609     0.8842 0.00 0.98 0.00 0.02 0.00
#&gt; TCGA.AB.2820.03     4  0.0609     0.9401 0.00 0.02 0.00 0.98 0.00
#&gt; TCGA.AB.2808.03     2  0.5684     0.1074 0.02 0.50 0.44 0.00 0.04
#&gt; TCGA.AB.2991.03     3  0.0000     0.7824 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2803.03     3  0.0000     0.7824 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2900.03     2  0.0609     0.8842 0.00 0.98 0.00 0.02 0.00
#&gt; TCGA.AB.2899.03     2  0.0609     0.8842 0.00 0.98 0.00 0.02 0.00
#&gt; TCGA.AB.2812.03     1  0.0000     0.8973 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.3011.03     1  0.0000     0.8973 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2946.03     1  0.3109     0.6274 0.80 0.20 0.00 0.00 0.00
#&gt; TCGA.AB.3000.03     2  0.5631     0.2392 0.02 0.54 0.40 0.00 0.04
#&gt; TCGA.AB.2997.03     3  0.0000     0.7824 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.3001.03     3  0.0000     0.7824 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2926.03     2  0.0609     0.8842 0.00 0.98 0.00 0.02 0.00
#&gt; TCGA.AB.2856.03     1  0.3109     0.6274 0.80 0.20 0.00 0.00 0.00
#&gt; TCGA.AB.2977.03     2  0.0609     0.8842 0.00 0.98 0.00 0.02 0.00
#&gt; TCGA.AB.2879.03     1  0.0000     0.8973 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2976.03     1  0.0000     0.8973 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2989.03     1  0.0000     0.8973 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2849.03     2  0.0609     0.8842 0.00 0.98 0.00 0.02 0.00
#&gt; TCGA.AB.2981.03     5  0.4227     0.9881 0.42 0.00 0.00 0.00 0.58
#&gt; TCGA.AB.2954.03     3  0.4767     0.8012 0.00 0.02 0.56 0.00 0.42
#&gt; TCGA.AB.2973.03     1  0.2516     0.7156 0.86 0.14 0.00 0.00 0.00
#&gt; TCGA.AB.2828.03     3  0.4767     0.8012 0.00 0.02 0.56 0.00 0.42
#&gt; TCGA.AB.2804.03     3  0.0000     0.7824 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2818.03     1  0.0000     0.8973 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2930.03     1  0.3690     0.6026 0.78 0.20 0.02 0.00 0.00
#&gt; TCGA.AB.2821.03     2  0.0609     0.8842 0.00 0.98 0.00 0.02 0.00
#&gt; TCGA.AB.2816.03     1  0.0000     0.8973 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2863.03     2  0.1043     0.8763 0.00 0.96 0.00 0.04 0.00
#&gt; TCGA.AB.2950.03     3  0.4726     0.8051 0.00 0.02 0.58 0.00 0.40
#&gt; TCGA.AB.2925.03     5  0.4227     0.9881 0.42 0.00 0.00 0.00 0.58
#&gt; TCGA.AB.3007.03     3  0.0000     0.7824 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2882.03     2  0.1043     0.8763 0.00 0.96 0.00 0.04 0.00
#&gt; TCGA.AB.2825.03     5  0.4227     0.9881 0.42 0.00 0.00 0.00 0.58
#&gt; TCGA.AB.2947.03     5  0.4227     0.9881 0.42 0.00 0.00 0.00 0.58
#&gt; TCGA.AB.2916.03     4  0.0609     0.9347 0.00 0.02 0.00 0.98 0.00
#&gt; TCGA.AB.2855.03     2  0.0609     0.8719 0.02 0.98 0.00 0.00 0.00
#&gt; TCGA.AB.2978.03     4  0.0000     0.9578 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2952.03     2  0.0609     0.8842 0.00 0.98 0.00 0.02 0.00
#&gt; TCGA.AB.2868.03     2  0.2280     0.8183 0.00 0.88 0.00 0.12 0.00
#&gt; TCGA.AB.2908.03     4  0.0000     0.9578 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2938.03     4  0.0000     0.9578 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2923.03     2  0.0609     0.8842 0.00 0.98 0.00 0.02 0.00
#&gt; TCGA.AB.2890.03     4  0.4302     0.0751 0.00 0.48 0.00 0.52 0.00
#&gt; TCGA.AB.2988.03     5  0.4287     0.9297 0.46 0.00 0.00 0.00 0.54
#&gt; TCGA.AB.2985.03     1  0.0000     0.8973 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2880.03     3  0.5588     0.2899 0.02 0.38 0.56 0.00 0.04
#&gt; TCGA.AB.2889.03     3  0.4767     0.8012 0.00 0.02 0.56 0.00 0.42
#&gt; TCGA.AB.2887.03     4  0.0000     0.9578 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2881.03     3  0.4767     0.8012 0.00 0.02 0.56 0.00 0.42
#&gt; TCGA.AB.2834.03     2  0.0609     0.8719 0.02 0.98 0.00 0.00 0.00
#&gt; TCGA.AB.2943.03     4  0.0000     0.9578 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2982.03     3  0.0000     0.7824 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2844.03     1  0.3109     0.6274 0.80 0.20 0.00 0.00 0.00
#&gt; TCGA.AB.2870.03     3  0.4767     0.8012 0.00 0.02 0.56 0.00 0.42
#&gt; TCGA.AB.2813.03     4  0.0000     0.9578 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2894.03     4  0.0000     0.9578 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2909.03     3  0.4726     0.8051 0.00 0.02 0.58 0.00 0.40
#&gt; TCGA.AB.2858.03     3  0.4726     0.8051 0.00 0.02 0.58 0.00 0.40
#&gt; TCGA.AB.2935.03     2  0.1043     0.8763 0.00 0.96 0.00 0.04 0.00
#&gt; TCGA.AB.2929.03     2  0.1043     0.8763 0.00 0.96 0.00 0.04 0.00
#&gt; TCGA.AB.2831.03     4  0.0000     0.9578 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2826.03     2  0.0609     0.8719 0.02 0.98 0.00 0.00 0.00
#&gt; TCGA.AB.2993.03     1  0.0000     0.8973 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2810.03     2  0.0609     0.8842 0.00 0.98 0.00 0.02 0.00
#&gt; TCGA.AB.2924.03     1  0.0000     0.8973 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2901.03     2  0.0609     0.8842 0.00 0.98 0.00 0.02 0.00
#&gt; TCGA.AB.2975.03     4  0.0000     0.9578 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2860.03     2  0.1410     0.8651 0.00 0.94 0.00 0.06 0.00
#&gt; TCGA.AB.2854.03     2  0.2929     0.7510 0.00 0.82 0.00 0.18 0.00
#&gt; TCGA.AB.2846.03     3  0.4767     0.8012 0.00 0.02 0.56 0.00 0.42
</code></pre>

<script>
$('#tab-node-0-get-classes-4-a').parent().next().next().hide();
$('#tab-node-0-get-classes-4-a').click(function(){
  $('#tab-node-0-get-classes-4-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-0-get-classes-5'>
<p><a id='tab-node-0-get-classes-5-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 6), get_membership(res, k = 6))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5   p6
#&gt; TCGA.AB.2888.03     3  0.2454     0.8840 0.00 0.00 0.84 0.00 0.00 0.16
#&gt; TCGA.AB.2995.03     4  0.0000     0.9331 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2884.03     5  0.2790     0.9545 0.14 0.02 0.00 0.00 0.84 0.00
#&gt; TCGA.AB.2878.03     2  0.0547     0.8571 0.00 0.98 0.00 0.02 0.00 0.00
#&gt; TCGA.AB.2998.03     6  0.0000     0.9807 0.00 0.00 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2913.03     1  0.0000     0.9457 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2883.03     4  0.5185     0.7049 0.00 0.14 0.08 0.70 0.08 0.00
#&gt; TCGA.AB.2957.03     3  0.2454     0.8840 0.00 0.00 0.84 0.00 0.00 0.16
#&gt; TCGA.AB.2984.03     2  0.0547     0.8535 0.00 0.98 0.00 0.00 0.02 0.00
#&gt; TCGA.AB.2837.03     1  0.0000     0.9457 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2874.03     2  0.0547     0.8535 0.00 0.98 0.00 0.00 0.02 0.00
#&gt; TCGA.AB.2836.03     1  0.0000     0.9457 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2876.03     2  0.6990     0.1185 0.00 0.42 0.16 0.00 0.10 0.32
#&gt; TCGA.AB.2830.03     4  0.0000     0.9331 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2823.03     6  0.0000     0.9807 0.00 0.00 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2999.03     6  0.0000     0.9807 0.00 0.00 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2940.03     2  0.6990     0.1185 0.00 0.42 0.16 0.00 0.10 0.32
#&gt; TCGA.AB.2941.03     4  0.0000     0.9331 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2987.03     4  0.0937     0.9116 0.00 0.00 0.00 0.96 0.04 0.00
#&gt; TCGA.AB.2945.03     1  0.0000     0.9457 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2963.03     1  0.0000     0.9457 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2967.03     1  0.0000     0.9457 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2843.03     2  0.1267     0.8296 0.00 0.94 0.00 0.06 0.00 0.00
#&gt; TCGA.AB.2807.03     4  0.3851     0.1663 0.00 0.46 0.00 0.54 0.00 0.00
#&gt; TCGA.AB.3012.03     6  0.0937     0.9545 0.00 0.00 0.04 0.00 0.00 0.96
#&gt; TCGA.AB.2971.03     4  0.0547     0.9209 0.00 0.00 0.00 0.98 0.02 0.00
#&gt; TCGA.AB.2809.03     5  0.2260     0.9741 0.14 0.00 0.00 0.00 0.86 0.00
#&gt; TCGA.AB.2873.03     4  0.0000     0.9331 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2802.03     5  0.2260     0.9741 0.14 0.00 0.00 0.00 0.86 0.00
#&gt; TCGA.AB.2851.03     1  0.0000     0.9457 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2853.03     5  0.2260     0.9741 0.14 0.00 0.00 0.00 0.86 0.00
#&gt; TCGA.AB.2847.03     2  0.0547     0.8571 0.00 0.98 0.00 0.02 0.00 0.00
#&gt; TCGA.AB.2833.03     4  0.0000     0.9331 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2814.03     2  0.0000     0.8556 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2898.03     4  0.0000     0.9331 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2866.03     2  0.0547     0.8535 0.00 0.98 0.00 0.00 0.02 0.00
#&gt; TCGA.AB.2875.03     3  0.3163     0.8470 0.00 0.00 0.82 0.00 0.04 0.14
#&gt; TCGA.AB.2841.03     6  0.0000     0.9807 0.00 0.00 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2922.03     4  0.2454     0.7920 0.00 0.16 0.00 0.84 0.00 0.00
#&gt; TCGA.AB.3008.03     2  0.6990     0.1185 0.00 0.42 0.16 0.00 0.10 0.32
#&gt; TCGA.AB.2968.03     4  0.0000     0.9331 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2811.03     5  0.2941     0.9157 0.22 0.00 0.00 0.00 0.78 0.00
#&gt; TCGA.AB.2895.03     5  0.2260     0.9741 0.14 0.00 0.00 0.00 0.86 0.00
#&gt; TCGA.AB.2933.03     4  0.0547     0.9335 0.00 0.02 0.00 0.98 0.00 0.00
#&gt; TCGA.AB.2827.03     1  0.2728     0.8431 0.86 0.04 0.00 0.00 0.10 0.00
#&gt; TCGA.AB.2942.03     3  0.2454     0.8840 0.00 0.00 0.84 0.00 0.00 0.16
#&gt; TCGA.AB.2910.03     4  0.3073     0.8449 0.00 0.00 0.08 0.84 0.08 0.00
#&gt; TCGA.AB.2934.03     4  0.0000     0.9331 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2959.03     2  0.0547     0.8571 0.00 0.98 0.00 0.02 0.00 0.00
#&gt; TCGA.AB.2871.03     2  0.0547     0.8535 0.00 0.98 0.00 0.00 0.02 0.00
#&gt; TCGA.AB.2907.03     2  0.1267     0.8296 0.00 0.94 0.00 0.06 0.00 0.00
#&gt; TCGA.AB.2932.03     1  0.0000     0.9457 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2824.03     1  0.0000     0.9457 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2972.03     1  0.0000     0.9457 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2915.03     2  0.1556     0.8130 0.00 0.92 0.00 0.08 0.00 0.00
#&gt; TCGA.AB.2970.03     2  0.0547     0.8535 0.00 0.98 0.00 0.00 0.02 0.00
#&gt; TCGA.AB.2949.03     4  0.0547     0.9335 0.00 0.02 0.00 0.98 0.00 0.00
#&gt; TCGA.AB.2912.03     2  0.0547     0.8571 0.00 0.98 0.00 0.02 0.00 0.00
#&gt; TCGA.AB.2838.03     2  0.0547     0.8571 0.00 0.98 0.00 0.02 0.00 0.00
#&gt; TCGA.AB.2872.03     6  0.0937     0.9545 0.00 0.00 0.04 0.00 0.00 0.96
#&gt; TCGA.AB.2897.03     6  0.0000     0.9807 0.00 0.00 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2965.03     5  0.2260     0.9741 0.14 0.00 0.00 0.00 0.86 0.00
#&gt; TCGA.AB.2891.03     2  0.0547     0.8571 0.00 0.98 0.00 0.02 0.00 0.00
#&gt; TCGA.AB.2921.03     2  0.6990     0.1185 0.00 0.42 0.16 0.00 0.10 0.32
#&gt; TCGA.AB.2867.03     4  0.0547     0.9335 0.00 0.02 0.00 0.98 0.00 0.00
#&gt; TCGA.AB.2842.03     1  0.1480     0.9062 0.94 0.00 0.02 0.00 0.04 0.00
#&gt; TCGA.AB.2862.03     6  0.0000     0.9807 0.00 0.00 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2840.03     6  0.0000     0.9807 0.00 0.00 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2822.03     2  0.1814     0.7950 0.00 0.90 0.00 0.10 0.00 0.00
#&gt; TCGA.AB.2832.03     4  0.3073     0.8449 0.00 0.00 0.08 0.84 0.08 0.00
#&gt; TCGA.AB.2893.03     4  0.3073     0.8449 0.00 0.00 0.08 0.84 0.08 0.00
#&gt; TCGA.AB.2956.03     4  0.3073     0.8449 0.00 0.00 0.08 0.84 0.08 0.00
#&gt; TCGA.AB.2903.03     2  0.0547     0.8535 0.00 0.98 0.00 0.00 0.02 0.00
#&gt; TCGA.AB.2845.03     2  0.6990     0.1185 0.00 0.42 0.16 0.00 0.10 0.32
#&gt; TCGA.AB.2948.03     4  0.0547     0.9335 0.00 0.02 0.00 0.98 0.00 0.00
#&gt; TCGA.AB.2869.03     1  0.0000     0.9457 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.3009.03     2  0.3321     0.7346 0.00 0.82 0.08 0.00 0.10 0.00
#&gt; TCGA.AB.2944.03     2  0.0547     0.8535 0.00 0.98 0.00 0.00 0.02 0.00
#&gt; TCGA.AB.2886.03     3  0.3163     0.8470 0.00 0.00 0.82 0.00 0.04 0.14
#&gt; TCGA.AB.2904.03     4  0.0547     0.9335 0.00 0.02 0.00 0.98 0.00 0.00
#&gt; TCGA.AB.3005.03     4  0.3073     0.8449 0.00 0.00 0.08 0.84 0.08 0.00
#&gt; TCGA.AB.2861.03     4  0.3073     0.8449 0.00 0.00 0.08 0.84 0.08 0.00
#&gt; TCGA.AB.2917.03     4  0.2631     0.7696 0.00 0.18 0.00 0.82 0.00 0.00
#&gt; TCGA.AB.2964.03     2  0.0547     0.8571 0.00 0.98 0.00 0.02 0.00 0.00
#&gt; TCGA.AB.2955.03     3  0.6943     0.1475 0.00 0.18 0.40 0.00 0.08 0.34
#&gt; TCGA.AB.2911.03     1  0.3045     0.8232 0.84 0.06 0.00 0.00 0.10 0.00
#&gt; TCGA.AB.2892.03     3  0.2454     0.8840 0.00 0.00 0.84 0.00 0.00 0.16
#&gt; TCGA.AB.2817.03     4  0.1267     0.9031 0.00 0.06 0.00 0.94 0.00 0.00
#&gt; TCGA.AB.2906.03     6  0.0000     0.9807 0.00 0.00 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2857.03     4  0.0937     0.9201 0.00 0.04 0.00 0.96 0.00 0.00
#&gt; TCGA.AB.2805.03     2  0.0547     0.8571 0.00 0.98 0.00 0.02 0.00 0.00
#&gt; TCGA.AB.2983.03     2  0.0547     0.8571 0.00 0.98 0.00 0.02 0.00 0.00
#&gt; TCGA.AB.2918.03     1  0.2350     0.8598 0.88 0.02 0.00 0.00 0.10 0.00
#&gt; TCGA.AB.2990.03     2  0.0547     0.8535 0.00 0.98 0.00 0.00 0.02 0.00
#&gt; TCGA.AB.2937.03     3  0.3163     0.8470 0.00 0.00 0.82 0.00 0.04 0.14
#&gt; TCGA.AB.3006.03     1  0.0937     0.9169 0.96 0.04 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2829.03     4  0.0547     0.9335 0.00 0.02 0.00 0.98 0.00 0.00
#&gt; TCGA.AB.2848.03     1  0.0000     0.9457 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2914.03     3  0.2474     0.8542 0.00 0.00 0.88 0.00 0.04 0.08
#&gt; TCGA.AB.3002.03     2  0.0000     0.8556 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2877.03     2  0.0547     0.8535 0.00 0.98 0.00 0.00 0.02 0.00
#&gt; TCGA.AB.2969.03     5  0.2260     0.9741 0.14 0.00 0.00 0.00 0.86 0.00
#&gt; TCGA.AB.2839.03     1  0.0000     0.9457 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2835.03     1  0.0000     0.9457 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2974.03     5  0.2631     0.9544 0.18 0.00 0.00 0.00 0.82 0.00
#&gt; TCGA.AB.2920.03     2  0.0547     0.8571 0.00 0.98 0.00 0.02 0.00 0.00
#&gt; TCGA.AB.2980.03     6  0.0547     0.9533 0.00 0.00 0.00 0.02 0.00 0.98
#&gt; TCGA.AB.2819.03     3  0.3163     0.8470 0.00 0.00 0.82 0.00 0.04 0.14
#&gt; TCGA.AB.2992.03     4  0.0547     0.9335 0.00 0.02 0.00 0.98 0.00 0.00
#&gt; TCGA.AB.2919.03     2  0.0547     0.8535 0.00 0.98 0.00 0.00 0.02 0.00
#&gt; TCGA.AB.2928.03     4  0.0000     0.9331 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2927.03     4  0.0547     0.9335 0.00 0.02 0.00 0.98 0.00 0.00
#&gt; TCGA.AB.2806.03     3  0.3163     0.8470 0.00 0.00 0.82 0.00 0.04 0.14
#&gt; TCGA.AB.2885.03     2  0.0547     0.8571 0.00 0.98 0.00 0.02 0.00 0.00
#&gt; TCGA.AB.2815.03     3  0.2454     0.8840 0.00 0.00 0.84 0.00 0.00 0.16
#&gt; TCGA.AB.2996.03     4  0.0547     0.9335 0.00 0.02 0.00 0.98 0.00 0.00
#&gt; TCGA.AB.2936.03     2  0.3797     0.1948 0.00 0.58 0.00 0.42 0.00 0.00
#&gt; TCGA.AB.2939.03     2  0.6990     0.1185 0.00 0.42 0.16 0.00 0.10 0.32
#&gt; TCGA.AB.2979.03     2  0.6990     0.1185 0.00 0.42 0.16 0.00 0.10 0.32
#&gt; TCGA.AB.2986.03     1  0.0000     0.9457 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2931.03     5  0.2631     0.9544 0.18 0.00 0.00 0.00 0.82 0.00
#&gt; TCGA.AB.2896.03     5  0.2260     0.9741 0.14 0.00 0.00 0.00 0.86 0.00
#&gt; TCGA.AB.2966.03     2  0.0547     0.8571 0.00 0.98 0.00 0.02 0.00 0.00
#&gt; TCGA.AB.2820.03     4  0.0547     0.9335 0.00 0.02 0.00 0.98 0.00 0.00
#&gt; TCGA.AB.2808.03     2  0.6990     0.1185 0.00 0.42 0.16 0.00 0.10 0.32
#&gt; TCGA.AB.2991.03     6  0.0937     0.9545 0.00 0.00 0.04 0.00 0.00 0.96
#&gt; TCGA.AB.2803.03     6  0.0000     0.9807 0.00 0.00 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2900.03     2  0.0547     0.8535 0.00 0.98 0.00 0.00 0.02 0.00
#&gt; TCGA.AB.2899.03     2  0.0547     0.8571 0.00 0.98 0.00 0.02 0.00 0.00
#&gt; TCGA.AB.2812.03     1  0.0000     0.9457 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.3011.03     1  0.0000     0.9457 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2946.03     1  0.3045     0.8232 0.84 0.06 0.00 0.00 0.10 0.00
#&gt; TCGA.AB.3000.03     2  0.6990     0.1185 0.00 0.42 0.16 0.00 0.10 0.32
#&gt; TCGA.AB.2997.03     6  0.0000     0.9807 0.00 0.00 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.3001.03     6  0.0937     0.9545 0.00 0.00 0.04 0.00 0.00 0.96
#&gt; TCGA.AB.2926.03     2  0.0547     0.8535 0.00 0.98 0.00 0.00 0.02 0.00
#&gt; TCGA.AB.2856.03     1  0.3045     0.8232 0.84 0.06 0.00 0.00 0.10 0.00
#&gt; TCGA.AB.2977.03     2  0.0547     0.8535 0.00 0.98 0.00 0.00 0.02 0.00
#&gt; TCGA.AB.2879.03     1  0.0000     0.9457 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2976.03     1  0.0000     0.9457 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2989.03     1  0.0000     0.9457 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2849.03     2  0.0547     0.8535 0.00 0.98 0.00 0.00 0.02 0.00
#&gt; TCGA.AB.2981.03     5  0.2260     0.9741 0.14 0.00 0.00 0.00 0.86 0.00
#&gt; TCGA.AB.2954.03     3  0.2454     0.8840 0.00 0.00 0.84 0.00 0.00 0.16
#&gt; TCGA.AB.2973.03     1  0.2350     0.8393 0.88 0.10 0.00 0.00 0.02 0.00
#&gt; TCGA.AB.2828.03     3  0.2454     0.8840 0.00 0.00 0.84 0.00 0.00 0.16
#&gt; TCGA.AB.2804.03     6  0.0000     0.9807 0.00 0.00 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2818.03     1  0.0000     0.9457 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2930.03     1  0.4251     0.7616 0.78 0.06 0.06 0.00 0.10 0.00
#&gt; TCGA.AB.2821.03     2  0.0547     0.8571 0.00 0.98 0.00 0.02 0.00 0.00
#&gt; TCGA.AB.2816.03     1  0.0000     0.9457 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2863.03     2  0.0547     0.8571 0.00 0.98 0.00 0.02 0.00 0.00
#&gt; TCGA.AB.2950.03     3  0.3163     0.8470 0.00 0.00 0.82 0.00 0.04 0.14
#&gt; TCGA.AB.2925.03     5  0.2260     0.9741 0.14 0.00 0.00 0.00 0.86 0.00
#&gt; TCGA.AB.3007.03     6  0.0937     0.9545 0.00 0.00 0.04 0.00 0.00 0.96
#&gt; TCGA.AB.2882.03     2  0.0547     0.8571 0.00 0.98 0.00 0.02 0.00 0.00
#&gt; TCGA.AB.2825.03     5  0.2260     0.9741 0.14 0.00 0.00 0.00 0.86 0.00
#&gt; TCGA.AB.2947.03     5  0.2631     0.9544 0.18 0.00 0.00 0.00 0.82 0.00
#&gt; TCGA.AB.2916.03     4  0.0000     0.9331 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2855.03     2  0.0547     0.8535 0.00 0.98 0.00 0.00 0.02 0.00
#&gt; TCGA.AB.2978.03     4  0.0000     0.9331 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2952.03     2  0.0547     0.8571 0.00 0.98 0.00 0.02 0.00 0.00
#&gt; TCGA.AB.2868.03     2  0.0937     0.8445 0.00 0.96 0.00 0.04 0.00 0.00
#&gt; TCGA.AB.2908.03     4  0.0547     0.9335 0.00 0.02 0.00 0.98 0.00 0.00
#&gt; TCGA.AB.2938.03     4  0.0547     0.9335 0.00 0.02 0.00 0.98 0.00 0.00
#&gt; TCGA.AB.2923.03     2  0.0547     0.8535 0.00 0.98 0.00 0.00 0.02 0.00
#&gt; TCGA.AB.2890.03     2  0.3756     0.2565 0.00 0.60 0.00 0.40 0.00 0.00
#&gt; TCGA.AB.2988.03     5  0.3076     0.8915 0.24 0.00 0.00 0.00 0.76 0.00
#&gt; TCGA.AB.2985.03     1  0.1480     0.9062 0.94 0.00 0.02 0.00 0.04 0.00
#&gt; TCGA.AB.2880.03     2  0.7014     0.0568 0.00 0.40 0.16 0.00 0.10 0.34
#&gt; TCGA.AB.2889.03     3  0.2454     0.8840 0.00 0.00 0.84 0.00 0.00 0.16
#&gt; TCGA.AB.2887.03     4  0.0000     0.9331 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2881.03     3  0.2454     0.8840 0.00 0.00 0.84 0.00 0.00 0.16
#&gt; TCGA.AB.2834.03     2  0.1267     0.8317 0.00 0.94 0.00 0.00 0.06 0.00
#&gt; TCGA.AB.2943.03     4  0.0547     0.9335 0.00 0.02 0.00 0.98 0.00 0.00
#&gt; TCGA.AB.2982.03     6  0.0000     0.9807 0.00 0.00 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2844.03     1  0.3045     0.8232 0.84 0.06 0.00 0.00 0.10 0.00
#&gt; TCGA.AB.2870.03     3  0.2454     0.8840 0.00 0.00 0.84 0.00 0.00 0.16
#&gt; TCGA.AB.2813.03     4  0.0547     0.9335 0.00 0.02 0.00 0.98 0.00 0.00
#&gt; TCGA.AB.2894.03     4  0.3073     0.8449 0.00 0.00 0.08 0.84 0.08 0.00
#&gt; TCGA.AB.2909.03     3  0.3163     0.8470 0.00 0.00 0.82 0.00 0.04 0.14
#&gt; TCGA.AB.2858.03     3  0.3821     0.8397 0.00 0.00 0.74 0.04 0.00 0.22
#&gt; TCGA.AB.2935.03     2  0.0547     0.8571 0.00 0.98 0.00 0.02 0.00 0.00
#&gt; TCGA.AB.2929.03     2  0.0547     0.8571 0.00 0.98 0.00 0.02 0.00 0.00
#&gt; TCGA.AB.2831.03     4  0.0547     0.9335 0.00 0.02 0.00 0.98 0.00 0.00
#&gt; TCGA.AB.2826.03     2  0.0547     0.8535 0.00 0.98 0.00 0.00 0.02 0.00
#&gt; TCGA.AB.2993.03     1  0.0000     0.9457 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2810.03     2  0.0547     0.8535 0.00 0.98 0.00 0.00 0.02 0.00
#&gt; TCGA.AB.2924.03     1  0.0000     0.9457 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2901.03     2  0.0547     0.8571 0.00 0.98 0.00 0.02 0.00 0.00
#&gt; TCGA.AB.2975.03     4  0.0000     0.9331 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2860.03     2  0.0547     0.8571 0.00 0.98 0.00 0.02 0.00 0.00
#&gt; TCGA.AB.2854.03     2  0.1267     0.8296 0.00 0.94 0.00 0.06 0.00 0.00
#&gt; TCGA.AB.2846.03     3  0.2454     0.8840 0.00 0.00 0.84 0.00 0.00 0.16
</code></pre>

<script>
$('#tab-node-0-get-classes-5-a').parent().next().next().hide();
$('#tab-node-0-get-classes-5-a').click(function(){
  $('#tab-node-0-get-classes-5-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-0-get-classes-6'>
<p><a id='tab-node-0-get-classes-6-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 7), get_membership(res, k = 7))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5   p6   p7
#&gt; TCGA.AB.2888.03     3  0.3968      0.507 0.44 0.00 0.54 0.00 0.00 0.02 0.00
#&gt; TCGA.AB.2995.03     4  0.0000      0.874 0.00 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2884.03     5  0.3208      0.800 0.12 0.02 0.00 0.00 0.82 0.00 0.04
#&gt; TCGA.AB.2878.03     2  0.0504      0.854 0.02 0.98 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2998.03     6  0.0000      0.992 0.00 0.00 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2913.03     7  0.0504      0.918 0.00 0.00 0.00 0.00 0.02 0.00 0.98
#&gt; TCGA.AB.2883.03     4  0.4939      0.644 0.26 0.06 0.00 0.64 0.02 0.00 0.02
#&gt; TCGA.AB.2957.03     3  0.3968      0.507 0.44 0.00 0.54 0.00 0.00 0.02 0.00
#&gt; TCGA.AB.2984.03     2  0.3307      0.802 0.24 0.74 0.00 0.00 0.00 0.00 0.02
#&gt; TCGA.AB.2837.03     7  0.0504      0.918 0.00 0.00 0.00 0.00 0.02 0.00 0.98
#&gt; TCGA.AB.2874.03     2  0.3417      0.799 0.26 0.72 0.00 0.00 0.00 0.00 0.02
#&gt; TCGA.AB.2836.03     7  0.0504      0.918 0.00 0.00 0.00 0.00 0.02 0.00 0.98
#&gt; TCGA.AB.2876.03     3  0.6000      0.520 0.26 0.14 0.52 0.00 0.00 0.08 0.00
#&gt; TCGA.AB.2830.03     4  0.0000      0.874 0.00 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2823.03     6  0.0000      0.992 0.00 0.00 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2999.03     6  0.0000      0.992 0.00 0.00 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2940.03     3  0.6000      0.520 0.26 0.14 0.52 0.00 0.00 0.08 0.00
#&gt; TCGA.AB.2941.03     4  0.0000      0.874 0.00 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2987.03     4  0.0504      0.870 0.02 0.00 0.00 0.98 0.00 0.00 0.00
#&gt; TCGA.AB.2945.03     7  0.0863      0.905 0.00 0.00 0.00 0.00 0.04 0.00 0.96
#&gt; TCGA.AB.2963.03     7  0.0504      0.918 0.00 0.00 0.00 0.00 0.02 0.00 0.98
#&gt; TCGA.AB.2967.03     7  0.0504      0.918 0.00 0.00 0.00 0.00 0.02 0.00 0.98
#&gt; TCGA.AB.2843.03     2  0.0863      0.842 0.00 0.96 0.00 0.04 0.00 0.00 0.00
#&gt; TCGA.AB.2807.03     2  0.3139      0.455 0.00 0.70 0.00 0.30 0.00 0.00 0.00
#&gt; TCGA.AB.3012.03     6  0.0504      0.980 0.00 0.00 0.02 0.00 0.00 0.98 0.00
#&gt; TCGA.AB.2971.03     4  0.0000      0.874 0.00 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2809.03     5  0.0504      0.955 0.00 0.00 0.00 0.00 0.98 0.00 0.02
#&gt; TCGA.AB.2873.03     4  0.0000      0.874 0.00 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2802.03     5  0.0504      0.955 0.00 0.00 0.00 0.00 0.98 0.00 0.02
#&gt; TCGA.AB.2851.03     7  0.0504      0.918 0.00 0.00 0.00 0.00 0.02 0.00 0.98
#&gt; TCGA.AB.2853.03     5  0.0504      0.955 0.00 0.00 0.00 0.00 0.98 0.00 0.02
#&gt; TCGA.AB.2847.03     2  0.0504      0.854 0.00 0.98 0.00 0.02 0.00 0.00 0.00
#&gt; TCGA.AB.2833.03     4  0.0504      0.875 0.00 0.02 0.00 0.98 0.00 0.00 0.00
#&gt; TCGA.AB.2814.03     2  0.0504      0.854 0.02 0.98 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2898.03     4  0.0000      0.874 0.00 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2866.03     2  0.3307      0.802 0.24 0.74 0.00 0.00 0.00 0.00 0.02
#&gt; TCGA.AB.2875.03     3  0.0863      0.607 0.00 0.00 0.96 0.00 0.00 0.04 0.00
#&gt; TCGA.AB.2841.03     6  0.0000      0.992 0.00 0.00 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2922.03     4  0.3294      0.639 0.00 0.34 0.00 0.66 0.00 0.00 0.00
#&gt; TCGA.AB.3008.03     3  0.6000      0.520 0.26 0.14 0.52 0.00 0.00 0.08 0.00
#&gt; TCGA.AB.2968.03     4  0.1166      0.869 0.00 0.06 0.00 0.94 0.00 0.00 0.00
#&gt; TCGA.AB.2811.03     5  0.2259      0.849 0.00 0.00 0.00 0.00 0.84 0.00 0.16
#&gt; TCGA.AB.2895.03     5  0.0504      0.955 0.00 0.00 0.00 0.00 0.98 0.00 0.02
#&gt; TCGA.AB.2933.03     4  0.2708      0.781 0.00 0.22 0.00 0.78 0.00 0.00 0.00
#&gt; TCGA.AB.2827.03     7  0.2745      0.833 0.16 0.00 0.02 0.00 0.00 0.00 0.82
#&gt; TCGA.AB.2942.03     3  0.3968      0.507 0.44 0.00 0.54 0.00 0.00 0.02 0.00
#&gt; TCGA.AB.2910.03     4  0.3052      0.769 0.20 0.00 0.00 0.78 0.02 0.00 0.00
#&gt; TCGA.AB.2934.03     4  0.0000      0.874 0.00 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2959.03     2  0.2163      0.857 0.10 0.88 0.00 0.02 0.00 0.00 0.00
#&gt; TCGA.AB.2871.03     2  0.3307      0.802 0.24 0.74 0.00 0.00 0.00 0.00 0.02
#&gt; TCGA.AB.2907.03     2  0.2163      0.857 0.10 0.88 0.00 0.02 0.00 0.00 0.00
#&gt; TCGA.AB.2932.03     7  0.0504      0.918 0.00 0.00 0.00 0.00 0.02 0.00 0.98
#&gt; TCGA.AB.2824.03     7  0.0504      0.918 0.00 0.00 0.00 0.00 0.02 0.00 0.98
#&gt; TCGA.AB.2972.03     7  0.0000      0.911 0.00 0.00 0.00 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2915.03     2  0.0863      0.842 0.00 0.96 0.00 0.04 0.00 0.00 0.00
#&gt; TCGA.AB.2970.03     2  0.1886      0.840 0.12 0.88 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2949.03     4  0.1671      0.856 0.00 0.10 0.00 0.90 0.00 0.00 0.00
#&gt; TCGA.AB.2912.03     2  0.1006      0.847 0.02 0.96 0.02 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2838.03     2  0.0504      0.854 0.00 0.98 0.00 0.02 0.00 0.00 0.00
#&gt; TCGA.AB.2872.03     6  0.0504      0.980 0.00 0.00 0.02 0.00 0.00 0.98 0.00
#&gt; TCGA.AB.2897.03     6  0.0000      0.992 0.00 0.00 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2965.03     5  0.0504      0.955 0.00 0.00 0.00 0.00 0.98 0.00 0.02
#&gt; TCGA.AB.2891.03     2  0.0504      0.854 0.00 0.98 0.00 0.02 0.00 0.00 0.00
#&gt; TCGA.AB.2921.03     3  0.6000      0.520 0.26 0.14 0.52 0.00 0.00 0.08 0.00
#&gt; TCGA.AB.2867.03     4  0.1363      0.866 0.04 0.02 0.00 0.94 0.00 0.00 0.00
#&gt; TCGA.AB.2842.03     7  0.1928      0.877 0.08 0.02 0.00 0.00 0.00 0.00 0.90
#&gt; TCGA.AB.2862.03     6  0.0000      0.992 0.00 0.00 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2840.03     6  0.0000      0.992 0.00 0.00 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2822.03     2  0.3670      0.759 0.10 0.76 0.00 0.14 0.00 0.00 0.00
#&gt; TCGA.AB.2832.03     4  0.3052      0.769 0.20 0.00 0.00 0.78 0.02 0.00 0.00
#&gt; TCGA.AB.2893.03     4  0.3052      0.769 0.20 0.00 0.00 0.78 0.02 0.00 0.00
#&gt; TCGA.AB.2956.03     4  0.3052      0.769 0.20 0.00 0.00 0.78 0.02 0.00 0.00
#&gt; TCGA.AB.2903.03     2  0.3307      0.802 0.24 0.74 0.00 0.00 0.00 0.00 0.02
#&gt; TCGA.AB.2845.03     3  0.6000      0.520 0.26 0.14 0.52 0.00 0.00 0.08 0.00
#&gt; TCGA.AB.2948.03     4  0.0504      0.875 0.00 0.02 0.00 0.98 0.00 0.00 0.00
#&gt; TCGA.AB.2869.03     7  0.0504      0.918 0.00 0.00 0.00 0.00 0.02 0.00 0.98
#&gt; TCGA.AB.3009.03     3  0.5512      0.333 0.30 0.26 0.44 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2944.03     2  0.1433      0.852 0.08 0.92 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2886.03     3  0.0863      0.607 0.00 0.00 0.96 0.00 0.00 0.04 0.00
#&gt; TCGA.AB.2904.03     4  0.1886      0.847 0.00 0.12 0.00 0.88 0.00 0.00 0.00
#&gt; TCGA.AB.3005.03     4  0.3052      0.769 0.20 0.00 0.00 0.78 0.02 0.00 0.00
#&gt; TCGA.AB.2861.03     4  0.3052      0.769 0.20 0.00 0.00 0.78 0.02 0.00 0.00
#&gt; TCGA.AB.2917.03     4  0.3413      0.559 0.00 0.38 0.00 0.62 0.00 0.00 0.00
#&gt; TCGA.AB.2964.03     2  0.2376      0.850 0.12 0.86 0.00 0.00 0.00 0.00 0.02
#&gt; TCGA.AB.2955.03     3  0.5199      0.538 0.20 0.08 0.64 0.00 0.00 0.08 0.00
#&gt; TCGA.AB.2911.03     7  0.2259      0.838 0.16 0.00 0.00 0.00 0.00 0.00 0.84
#&gt; TCGA.AB.2892.03     3  0.3968      0.507 0.44 0.00 0.54 0.00 0.00 0.02 0.00
#&gt; TCGA.AB.2817.03     4  0.2832      0.765 0.00 0.24 0.00 0.76 0.00 0.00 0.00
#&gt; TCGA.AB.2906.03     6  0.0000      0.992 0.00 0.00 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2857.03     4  0.2832      0.765 0.00 0.24 0.00 0.76 0.00 0.00 0.00
#&gt; TCGA.AB.2805.03     2  0.2163      0.857 0.10 0.88 0.00 0.02 0.00 0.00 0.00
#&gt; TCGA.AB.2983.03     2  0.0504      0.854 0.00 0.98 0.00 0.02 0.00 0.00 0.00
#&gt; TCGA.AB.2918.03     7  0.2081      0.851 0.14 0.00 0.00 0.00 0.00 0.00 0.86
#&gt; TCGA.AB.2990.03     2  0.3307      0.802 0.24 0.74 0.00 0.00 0.00 0.00 0.02
#&gt; TCGA.AB.2937.03     3  0.0863      0.607 0.00 0.00 0.96 0.00 0.00 0.04 0.00
#&gt; TCGA.AB.3006.03     7  0.2278      0.862 0.08 0.04 0.00 0.00 0.00 0.00 0.88
#&gt; TCGA.AB.2829.03     4  0.0504      0.875 0.00 0.02 0.00 0.98 0.00 0.00 0.00
#&gt; TCGA.AB.2848.03     7  0.2163      0.863 0.10 0.02 0.00 0.00 0.00 0.00 0.88
#&gt; TCGA.AB.2914.03     3  0.0000      0.603 0.00 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.3002.03     2  0.1886      0.855 0.12 0.88 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2877.03     2  0.3307      0.802 0.24 0.74 0.00 0.00 0.00 0.00 0.02
#&gt; TCGA.AB.2969.03     5  0.0504      0.955 0.00 0.00 0.00 0.00 0.98 0.00 0.02
#&gt; TCGA.AB.2839.03     7  0.0504      0.918 0.00 0.00 0.00 0.00 0.02 0.00 0.98
#&gt; TCGA.AB.2835.03     7  0.0504      0.918 0.00 0.00 0.00 0.00 0.02 0.00 0.98
#&gt; TCGA.AB.2974.03     5  0.0504      0.955 0.00 0.00 0.00 0.00 0.98 0.00 0.02
#&gt; TCGA.AB.2920.03     2  0.1166      0.860 0.06 0.94 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2980.03     6  0.0000      0.992 0.00 0.00 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2819.03     3  0.0863      0.607 0.00 0.00 0.96 0.00 0.00 0.04 0.00
#&gt; TCGA.AB.2992.03     4  0.1363      0.866 0.04 0.02 0.00 0.94 0.00 0.00 0.00
#&gt; TCGA.AB.2919.03     2  0.3307      0.802 0.24 0.74 0.00 0.00 0.00 0.00 0.02
#&gt; TCGA.AB.2928.03     4  0.0000      0.874 0.00 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2927.03     4  0.2832      0.765 0.00 0.24 0.00 0.76 0.00 0.00 0.00
#&gt; TCGA.AB.2806.03     3  0.0863      0.607 0.00 0.00 0.96 0.00 0.00 0.04 0.00
#&gt; TCGA.AB.2885.03     2  0.0504      0.854 0.00 0.98 0.00 0.02 0.00 0.00 0.00
#&gt; TCGA.AB.2815.03     3  0.3968      0.507 0.44 0.00 0.54 0.00 0.00 0.02 0.00
#&gt; TCGA.AB.2996.03     4  0.1166      0.870 0.00 0.06 0.00 0.94 0.00 0.00 0.00
#&gt; TCGA.AB.2936.03     2  0.3617      0.745 0.08 0.76 0.00 0.16 0.00 0.00 0.00
#&gt; TCGA.AB.2939.03     3  0.6000      0.520 0.26 0.14 0.52 0.00 0.00 0.08 0.00
#&gt; TCGA.AB.2979.03     3  0.6000      0.520 0.26 0.14 0.52 0.00 0.00 0.08 0.00
#&gt; TCGA.AB.2986.03     7  0.0504      0.918 0.00 0.00 0.00 0.00 0.02 0.00 0.98
#&gt; TCGA.AB.2931.03     5  0.1433      0.921 0.00 0.00 0.00 0.00 0.92 0.00 0.08
#&gt; TCGA.AB.2896.03     5  0.0504      0.955 0.00 0.00 0.00 0.00 0.98 0.00 0.02
#&gt; TCGA.AB.2966.03     2  0.1433      0.858 0.08 0.92 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2820.03     4  0.3047      0.724 0.00 0.28 0.00 0.72 0.00 0.00 0.00
#&gt; TCGA.AB.2808.03     3  0.6000      0.520 0.26 0.14 0.52 0.00 0.00 0.08 0.00
#&gt; TCGA.AB.2991.03     6  0.0504      0.980 0.00 0.00 0.02 0.00 0.00 0.98 0.00
#&gt; TCGA.AB.2803.03     6  0.0000      0.992 0.00 0.00 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2900.03     2  0.3307      0.802 0.24 0.74 0.00 0.00 0.00 0.00 0.02
#&gt; TCGA.AB.2899.03     2  0.0504      0.854 0.02 0.98 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2812.03     7  0.0504      0.918 0.00 0.00 0.00 0.00 0.02 0.00 0.98
#&gt; TCGA.AB.3011.03     7  0.0504      0.918 0.00 0.00 0.00 0.00 0.02 0.00 0.98
#&gt; TCGA.AB.2946.03     7  0.2259      0.838 0.16 0.00 0.00 0.00 0.00 0.00 0.84
#&gt; TCGA.AB.3000.03     3  0.6000      0.520 0.26 0.14 0.52 0.00 0.00 0.08 0.00
#&gt; TCGA.AB.2997.03     6  0.0000      0.992 0.00 0.00 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.3001.03     6  0.0504      0.980 0.00 0.00 0.02 0.00 0.00 0.98 0.00
#&gt; TCGA.AB.2926.03     2  0.3186      0.813 0.22 0.76 0.00 0.00 0.00 0.00 0.02
#&gt; TCGA.AB.2856.03     7  0.2259      0.838 0.16 0.00 0.00 0.00 0.00 0.00 0.84
#&gt; TCGA.AB.2977.03     2  0.3307      0.802 0.24 0.74 0.00 0.00 0.00 0.00 0.02
#&gt; TCGA.AB.2879.03     7  0.2163      0.863 0.10 0.02 0.00 0.00 0.00 0.00 0.88
#&gt; TCGA.AB.2976.03     7  0.0504      0.918 0.00 0.00 0.00 0.00 0.02 0.00 0.98
#&gt; TCGA.AB.2989.03     7  0.0504      0.918 0.00 0.00 0.00 0.00 0.02 0.00 0.98
#&gt; TCGA.AB.2849.03     2  0.1671      0.854 0.10 0.90 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2981.03     5  0.0504      0.955 0.00 0.00 0.00 0.00 0.98 0.00 0.02
#&gt; TCGA.AB.2954.03     3  0.3968      0.507 0.44 0.00 0.54 0.00 0.00 0.02 0.00
#&gt; TCGA.AB.2973.03     7  0.3186      0.743 0.22 0.02 0.00 0.00 0.00 0.00 0.76
#&gt; TCGA.AB.2828.03     3  0.3968      0.507 0.44 0.00 0.54 0.00 0.00 0.02 0.00
#&gt; TCGA.AB.2804.03     6  0.0000      0.992 0.00 0.00 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2818.03     7  0.0504      0.918 0.00 0.00 0.00 0.00 0.02 0.00 0.98
#&gt; TCGA.AB.2930.03     7  0.5378      0.251 0.22 0.00 0.30 0.00 0.00 0.00 0.48
#&gt; TCGA.AB.2821.03     2  0.1886      0.854 0.12 0.88 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2816.03     7  0.0504      0.918 0.00 0.00 0.00 0.00 0.02 0.00 0.98
#&gt; TCGA.AB.2863.03     2  0.1886      0.854 0.12 0.88 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2950.03     3  0.0863      0.607 0.00 0.00 0.96 0.00 0.00 0.04 0.00
#&gt; TCGA.AB.2925.03     5  0.0504      0.955 0.00 0.00 0.00 0.00 0.98 0.00 0.02
#&gt; TCGA.AB.3007.03     6  0.0504      0.980 0.00 0.00 0.02 0.00 0.00 0.98 0.00
#&gt; TCGA.AB.2882.03     2  0.0504      0.854 0.00 0.98 0.00 0.02 0.00 0.00 0.00
#&gt; TCGA.AB.2825.03     5  0.0504      0.955 0.00 0.00 0.00 0.00 0.98 0.00 0.02
#&gt; TCGA.AB.2947.03     5  0.1433      0.921 0.00 0.00 0.00 0.00 0.92 0.00 0.08
#&gt; TCGA.AB.2916.03     4  0.1664      0.866 0.00 0.06 0.02 0.92 0.00 0.00 0.00
#&gt; TCGA.AB.2855.03     2  0.3186      0.805 0.22 0.76 0.00 0.00 0.00 0.00 0.02
#&gt; TCGA.AB.2978.03     4  0.0000      0.874 0.00 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2952.03     2  0.0504      0.854 0.02 0.98 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2868.03     2  0.0504      0.854 0.00 0.98 0.00 0.02 0.00 0.00 0.00
#&gt; TCGA.AB.2908.03     4  0.1671      0.856 0.00 0.10 0.00 0.90 0.00 0.00 0.00
#&gt; TCGA.AB.2938.03     4  0.1166      0.870 0.00 0.06 0.00 0.94 0.00 0.00 0.00
#&gt; TCGA.AB.2923.03     2  0.3307      0.802 0.24 0.74 0.00 0.00 0.00 0.00 0.02
#&gt; TCGA.AB.2890.03     2  0.2259      0.716 0.00 0.84 0.00 0.16 0.00 0.00 0.00
#&gt; TCGA.AB.2988.03     5  0.2572      0.805 0.00 0.00 0.00 0.00 0.80 0.00 0.20
#&gt; TCGA.AB.2985.03     7  0.2163      0.868 0.10 0.02 0.00 0.00 0.00 0.00 0.88
#&gt; TCGA.AB.2880.03     3  0.6000      0.520 0.26 0.14 0.52 0.00 0.00 0.08 0.00
#&gt; TCGA.AB.2889.03     3  0.3968      0.507 0.44 0.00 0.54 0.00 0.00 0.02 0.00
#&gt; TCGA.AB.2887.03     4  0.0000      0.874 0.00 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2881.03     3  0.3968      0.507 0.44 0.00 0.54 0.00 0.00 0.02 0.00
#&gt; TCGA.AB.2834.03     2  0.3517      0.766 0.28 0.70 0.00 0.00 0.00 0.00 0.02
#&gt; TCGA.AB.2943.03     4  0.3047      0.724 0.00 0.28 0.00 0.72 0.00 0.00 0.00
#&gt; TCGA.AB.2982.03     6  0.0000      0.992 0.00 0.00 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2844.03     7  0.2259      0.838 0.16 0.00 0.00 0.00 0.00 0.00 0.84
#&gt; TCGA.AB.2870.03     3  0.3968      0.507 0.44 0.00 0.54 0.00 0.00 0.02 0.00
#&gt; TCGA.AB.2813.03     4  0.1886      0.849 0.00 0.12 0.00 0.88 0.00 0.00 0.00
#&gt; TCGA.AB.2894.03     4  0.3052      0.769 0.20 0.00 0.00 0.78 0.02 0.00 0.00
#&gt; TCGA.AB.2909.03     3  0.0863      0.604 0.04 0.00 0.96 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2858.03     3  0.2509      0.589 0.02 0.00 0.88 0.04 0.00 0.06 0.00
#&gt; TCGA.AB.2935.03     2  0.0504      0.854 0.00 0.98 0.00 0.02 0.00 0.00 0.00
#&gt; TCGA.AB.2929.03     2  0.0504      0.854 0.00 0.98 0.00 0.02 0.00 0.00 0.00
#&gt; TCGA.AB.2831.03     4  0.0504      0.875 0.00 0.02 0.00 0.98 0.00 0.00 0.00
#&gt; TCGA.AB.2826.03     2  0.3307      0.802 0.24 0.74 0.00 0.00 0.00 0.00 0.02
#&gt; TCGA.AB.2993.03     7  0.0504      0.918 0.00 0.00 0.00 0.00 0.02 0.00 0.98
#&gt; TCGA.AB.2810.03     2  0.3307      0.802 0.24 0.74 0.00 0.00 0.00 0.00 0.02
#&gt; TCGA.AB.2924.03     7  0.0504      0.918 0.00 0.00 0.00 0.00 0.02 0.00 0.98
#&gt; TCGA.AB.2901.03     2  0.1886      0.854 0.12 0.88 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2975.03     4  0.0000      0.874 0.00 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2860.03     2  0.0504      0.854 0.00 0.98 0.00 0.02 0.00 0.00 0.00
#&gt; TCGA.AB.2854.03     2  0.0504      0.854 0.00 0.98 0.00 0.02 0.00 0.00 0.00
#&gt; TCGA.AB.2846.03     3  0.3968      0.507 0.44 0.00 0.54 0.00 0.00 0.02 0.00
</code></pre>

<script>
$('#tab-node-0-get-classes-6-a').parent().next().next().hide();
$('#tab-node-0-get-classes-6-a').click(function(){
  $('#tab-node-0-get-classes-6-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-0-get-classes-7'>
<p><a id='tab-node-0-get-classes-7-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 8), get_membership(res, k = 8))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5   p6   p7   p8
#&gt; TCGA.AB.2888.03     8  0.0471     1.0000 0.00 0.00 0.02 0.00 0.00 0.00 0.00 0.98
#&gt; TCGA.AB.2995.03     4  0.0808     0.7958 0.00 0.04 0.00 0.96 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2884.03     1  0.5612     0.4738 0.38 0.32 0.02 0.00 0.28 0.00 0.00 0.00
#&gt; TCGA.AB.2878.03     2  0.2938     0.5855 0.30 0.70 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2998.03     6  0.0000     0.9983 0.00 0.00 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2913.03     7  0.0000     0.8878 0.00 0.00 0.00 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2883.03     4  0.5646     0.4565 0.38 0.04 0.06 0.48 0.02 0.00 0.00 0.02
#&gt; TCGA.AB.2957.03     8  0.0471     1.0000 0.00 0.00 0.02 0.00 0.00 0.00 0.00 0.98
#&gt; TCGA.AB.2984.03     2  0.4100    -0.2476 0.36 0.58 0.06 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2837.03     7  0.0000     0.8878 0.00 0.00 0.00 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2874.03     2  0.4412    -0.2157 0.28 0.60 0.12 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2836.03     7  0.0000     0.8878 0.00 0.00 0.00 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2876.03     3  0.1341     0.8139 0.00 0.00 0.92 0.00 0.00 0.08 0.00 0.00
#&gt; TCGA.AB.2830.03     4  0.0808     0.7958 0.00 0.04 0.00 0.96 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2823.03     6  0.0000     0.9983 0.00 0.00 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2999.03     6  0.0000     0.9983 0.00 0.00 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2940.03     3  0.1341     0.8139 0.00 0.00 0.92 0.00 0.00 0.08 0.00 0.00
#&gt; TCGA.AB.2941.03     4  0.0808     0.7958 0.00 0.04 0.00 0.96 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2987.03     4  0.1557     0.7761 0.06 0.02 0.00 0.92 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2945.03     7  0.1275     0.8487 0.02 0.00 0.00 0.00 0.04 0.00 0.94 0.00
#&gt; TCGA.AB.2963.03     7  0.0000     0.8878 0.00 0.00 0.00 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2967.03     7  0.0000     0.8878 0.00 0.00 0.00 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2843.03     2  0.3015     0.5817 0.32 0.68 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2807.03     2  0.4799     0.4240 0.32 0.52 0.00 0.16 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.3012.03     6  0.0000     0.9983 0.00 0.00 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2971.03     4  0.0471     0.7763 0.02 0.00 0.00 0.98 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2809.03     5  0.1408     0.8801 0.02 0.00 0.02 0.00 0.94 0.00 0.02 0.00
#&gt; TCGA.AB.2873.03     4  0.0471     0.7877 0.00 0.02 0.00 0.98 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2802.03     5  0.1275     0.8727 0.04 0.00 0.00 0.00 0.94 0.00 0.02 0.00
#&gt; TCGA.AB.2851.03     7  0.0000     0.8878 0.00 0.00 0.00 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2853.03     5  0.1408     0.8801 0.02 0.00 0.02 0.00 0.94 0.00 0.02 0.00
#&gt; TCGA.AB.2847.03     2  0.3015     0.5817 0.32 0.68 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2833.03     4  0.2071     0.7927 0.04 0.04 0.02 0.90 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2814.03     2  0.2938     0.5855 0.30 0.70 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2898.03     4  0.0808     0.7958 0.00 0.04 0.00 0.96 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2866.03     2  0.4100    -0.2476 0.36 0.58 0.06 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2875.03     3  0.3728     0.6907 0.02 0.00 0.68 0.00 0.00 0.02 0.00 0.28
#&gt; TCGA.AB.2841.03     6  0.0000     0.9983 0.00 0.00 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2922.03     2  0.5030     0.3358 0.34 0.46 0.00 0.20 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.3008.03     3  0.1341     0.8139 0.00 0.00 0.92 0.00 0.00 0.08 0.00 0.00
#&gt; TCGA.AB.2968.03     4  0.3227     0.7421 0.14 0.08 0.00 0.78 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2811.03     5  0.3404     0.7141 0.04 0.00 0.00 0.00 0.72 0.00 0.24 0.00
#&gt; TCGA.AB.2895.03     5  0.0941     0.8801 0.00 0.00 0.02 0.00 0.96 0.00 0.02 0.00
#&gt; TCGA.AB.2933.03     2  0.5281     0.0694 0.34 0.34 0.00 0.32 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2827.03     7  0.2114     0.7827 0.00 0.00 0.16 0.00 0.00 0.00 0.84 0.00
#&gt; TCGA.AB.2942.03     8  0.0471     1.0000 0.00 0.00 0.02 0.00 0.00 0.00 0.00 0.98
#&gt; TCGA.AB.2910.03     4  0.4530     0.6154 0.24 0.00 0.06 0.66 0.02 0.00 0.00 0.02
#&gt; TCGA.AB.2934.03     4  0.0808     0.7958 0.00 0.04 0.00 0.96 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2959.03     2  0.0471     0.4072 0.00 0.98 0.02 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2871.03     2  0.4050    -0.2147 0.34 0.60 0.06 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2907.03     2  0.0000     0.4224 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2932.03     7  0.0000     0.8878 0.00 0.00 0.00 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2824.03     7  0.0000     0.8878 0.00 0.00 0.00 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2972.03     7  0.2534     0.6752 0.22 0.00 0.00 0.00 0.00 0.00 0.78 0.00
#&gt; TCGA.AB.2915.03     2  0.3449     0.5740 0.32 0.66 0.00 0.02 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2970.03     2  0.3618     0.5454 0.38 0.60 0.02 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2949.03     4  0.4799     0.3968 0.32 0.16 0.00 0.52 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2912.03     2  0.3015     0.5817 0.32 0.68 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2838.03     2  0.2938     0.5855 0.30 0.70 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2872.03     6  0.0000     0.9983 0.00 0.00 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2897.03     6  0.0000     0.9983 0.00 0.00 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2965.03     5  0.0941     0.8764 0.02 0.00 0.00 0.00 0.96 0.00 0.02 0.00
#&gt; TCGA.AB.2891.03     2  0.3095     0.5734 0.24 0.74 0.02 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2921.03     3  0.1341     0.8139 0.00 0.00 0.92 0.00 0.00 0.08 0.00 0.00
#&gt; TCGA.AB.2867.03     4  0.2852     0.6285 0.00 0.28 0.00 0.72 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2842.03     7  0.3169     0.7263 0.18 0.00 0.00 0.02 0.02 0.00 0.78 0.00
#&gt; TCGA.AB.2862.03     6  0.0000     0.9983 0.00 0.00 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2840.03     6  0.0000     0.9983 0.00 0.00 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2822.03     2  0.2623     0.2424 0.10 0.84 0.00 0.06 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2832.03     4  0.4530     0.6154 0.24 0.00 0.06 0.66 0.02 0.00 0.00 0.02
#&gt; TCGA.AB.2893.03     4  0.4530     0.6154 0.24 0.00 0.06 0.66 0.02 0.00 0.00 0.02
#&gt; TCGA.AB.2956.03     4  0.4530     0.6154 0.24 0.00 0.06 0.66 0.02 0.00 0.00 0.02
#&gt; TCGA.AB.2903.03     2  0.4100    -0.2476 0.36 0.58 0.06 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2845.03     3  0.1341     0.8139 0.00 0.00 0.92 0.00 0.00 0.08 0.00 0.00
#&gt; TCGA.AB.2948.03     4  0.2350     0.7736 0.04 0.10 0.00 0.86 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2869.03     7  0.1275     0.8487 0.02 0.00 0.00 0.00 0.04 0.00 0.94 0.00
#&gt; TCGA.AB.3009.03     3  0.2862     0.6264 0.08 0.10 0.82 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2944.03     2  0.4538     0.5195 0.32 0.56 0.12 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2886.03     3  0.3728     0.6907 0.02 0.00 0.68 0.00 0.00 0.02 0.00 0.28
#&gt; TCGA.AB.2904.03     4  0.4686     0.4197 0.28 0.16 0.00 0.56 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.3005.03     4  0.4530     0.6154 0.24 0.00 0.06 0.66 0.02 0.00 0.00 0.02
#&gt; TCGA.AB.2861.03     4  0.4530     0.6154 0.24 0.00 0.06 0.66 0.02 0.00 0.00 0.02
#&gt; TCGA.AB.2917.03     2  0.4996     0.3600 0.32 0.48 0.00 0.20 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2964.03     2  0.3862    -0.2210 0.36 0.60 0.04 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2955.03     3  0.1341     0.8139 0.00 0.00 0.92 0.00 0.00 0.08 0.00 0.00
#&gt; TCGA.AB.2911.03     7  0.3154     0.7391 0.06 0.00 0.16 0.00 0.00 0.00 0.78 0.00
#&gt; TCGA.AB.2892.03     8  0.0471     1.0000 0.00 0.00 0.02 0.00 0.00 0.00 0.00 0.98
#&gt; TCGA.AB.2817.03     2  0.5211     0.2097 0.34 0.40 0.00 0.26 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2906.03     6  0.0000     0.9983 0.00 0.00 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2857.03     2  0.5190     0.2447 0.32 0.42 0.00 0.26 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2805.03     2  0.0000     0.4224 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2983.03     2  0.3083     0.5804 0.34 0.66 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2918.03     7  0.2404     0.7884 0.02 0.00 0.14 0.00 0.00 0.00 0.84 0.00
#&gt; TCGA.AB.2990.03     2  0.4100    -0.2476 0.36 0.58 0.06 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2937.03     3  0.3728     0.6907 0.02 0.00 0.68 0.00 0.00 0.02 0.00 0.28
#&gt; TCGA.AB.3006.03     7  0.3675     0.4138 0.30 0.04 0.00 0.00 0.00 0.00 0.66 0.00
#&gt; TCGA.AB.2829.03     4  0.2407     0.7738 0.06 0.08 0.00 0.86 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2848.03     7  0.3514     0.3463 0.34 0.02 0.00 0.00 0.00 0.00 0.64 0.00
#&gt; TCGA.AB.2914.03     3  0.3015     0.6531 0.00 0.00 0.68 0.00 0.00 0.00 0.00 0.32
#&gt; TCGA.AB.3002.03     2  0.1887     0.3256 0.06 0.90 0.04 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2877.03     2  0.4100    -0.2476 0.36 0.58 0.06 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2969.03     5  0.1275     0.8727 0.04 0.00 0.00 0.00 0.94 0.00 0.02 0.00
#&gt; TCGA.AB.2839.03     7  0.0000     0.8878 0.00 0.00 0.00 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2835.03     7  0.0000     0.8878 0.00 0.00 0.00 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2974.03     5  0.1275     0.8727 0.04 0.00 0.00 0.00 0.94 0.00 0.02 0.00
#&gt; TCGA.AB.2920.03     2  0.3015     0.5801 0.32 0.68 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2980.03     6  0.0471     0.9704 0.00 0.00 0.00 0.02 0.00 0.98 0.00 0.00
#&gt; TCGA.AB.2819.03     3  0.3728     0.6907 0.02 0.00 0.68 0.00 0.00 0.02 0.00 0.28
#&gt; TCGA.AB.2992.03     4  0.2756     0.6553 0.00 0.26 0.00 0.74 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2919.03     2  0.4100    -0.2476 0.36 0.58 0.06 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2928.03     4  0.0808     0.7958 0.00 0.04 0.00 0.96 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2927.03     2  0.5211     0.2097 0.34 0.40 0.00 0.26 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2806.03     3  0.3637     0.7053 0.02 0.00 0.70 0.00 0.00 0.02 0.00 0.26
#&gt; TCGA.AB.2885.03     2  0.3015     0.5817 0.32 0.68 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2815.03     8  0.0471     1.0000 0.00 0.00 0.02 0.00 0.00 0.00 0.00 0.98
#&gt; TCGA.AB.2996.03     4  0.3263     0.7229 0.10 0.12 0.00 0.78 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2936.03     2  0.1091     0.3916 0.00 0.94 0.00 0.06 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2939.03     3  0.1341     0.8139 0.00 0.00 0.92 0.00 0.00 0.08 0.00 0.00
#&gt; TCGA.AB.2979.03     3  0.1341     0.8139 0.00 0.00 0.92 0.00 0.00 0.08 0.00 0.00
#&gt; TCGA.AB.2986.03     7  0.0000     0.8878 0.00 0.00 0.00 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2931.03     5  0.3293     0.7342 0.04 0.00 0.00 0.00 0.74 0.00 0.22 0.00
#&gt; TCGA.AB.2896.03     5  0.1408     0.8801 0.02 0.00 0.02 0.00 0.94 0.00 0.02 0.00
#&gt; TCGA.AB.2966.03     2  0.3757     0.5526 0.26 0.68 0.06 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2820.03     2  0.5073     0.3249 0.32 0.46 0.00 0.22 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2808.03     3  0.1341     0.8139 0.00 0.00 0.92 0.00 0.00 0.08 0.00 0.00
#&gt; TCGA.AB.2991.03     6  0.0000     0.9983 0.00 0.00 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2803.03     6  0.0000     0.9983 0.00 0.00 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2900.03     2  0.4100    -0.2476 0.36 0.58 0.06 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2899.03     2  0.2938     0.5855 0.30 0.70 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2812.03     7  0.0000     0.8878 0.00 0.00 0.00 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.3011.03     7  0.0000     0.8878 0.00 0.00 0.00 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2946.03     7  0.2888     0.7557 0.04 0.00 0.16 0.00 0.00 0.00 0.80 0.00
#&gt; TCGA.AB.3000.03     3  0.1341     0.8139 0.00 0.00 0.92 0.00 0.00 0.08 0.00 0.00
#&gt; TCGA.AB.2997.03     6  0.0000     0.9983 0.00 0.00 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.3001.03     6  0.0000     0.9983 0.00 0.00 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2926.03     2  0.3991    -0.1808 0.32 0.62 0.06 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2856.03     7  0.3154     0.7391 0.06 0.00 0.16 0.00 0.00 0.00 0.78 0.00
#&gt; TCGA.AB.2977.03     2  0.4100    -0.2476 0.36 0.58 0.06 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2879.03     7  0.3083     0.4109 0.34 0.00 0.00 0.00 0.00 0.00 0.66 0.00
#&gt; TCGA.AB.2976.03     7  0.0000     0.8878 0.00 0.00 0.00 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2989.03     7  0.0000     0.8878 0.00 0.00 0.00 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2849.03     2  0.4165     0.5062 0.26 0.64 0.10 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2981.03     5  0.1408     0.8801 0.02 0.00 0.02 0.00 0.94 0.00 0.02 0.00
#&gt; TCGA.AB.2954.03     8  0.0471     1.0000 0.00 0.00 0.02 0.00 0.00 0.00 0.00 0.98
#&gt; TCGA.AB.2973.03     1  0.5623     0.4690 0.36 0.28 0.02 0.00 0.00 0.00 0.34 0.00
#&gt; TCGA.AB.2828.03     8  0.0471     1.0000 0.00 0.00 0.02 0.00 0.00 0.00 0.00 0.98
#&gt; TCGA.AB.2804.03     6  0.0000     0.9983 0.00 0.00 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2818.03     7  0.0000     0.8878 0.00 0.00 0.00 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2930.03     3  0.3514     0.3609 0.02 0.00 0.64 0.00 0.00 0.00 0.34 0.00
#&gt; TCGA.AB.2821.03     2  0.2569     0.2048 0.16 0.82 0.02 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2816.03     7  0.0471     0.8768 0.02 0.00 0.00 0.00 0.00 0.00 0.98 0.00
#&gt; TCGA.AB.2863.03     2  0.2719     0.1705 0.18 0.80 0.02 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2950.03     3  0.3728     0.6907 0.02 0.00 0.68 0.00 0.00 0.02 0.00 0.28
#&gt; TCGA.AB.2925.03     5  0.1408     0.8801 0.02 0.00 0.02 0.00 0.94 0.00 0.02 0.00
#&gt; TCGA.AB.3007.03     6  0.0000     0.9983 0.00 0.00 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2882.03     2  0.2981     0.5601 0.22 0.76 0.02 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2825.03     5  0.1408     0.8801 0.02 0.00 0.02 0.00 0.94 0.00 0.02 0.00
#&gt; TCGA.AB.2947.03     5  0.3293     0.7342 0.04 0.00 0.00 0.00 0.74 0.00 0.22 0.00
#&gt; TCGA.AB.2916.03     4  0.4504     0.6189 0.24 0.10 0.00 0.64 0.00 0.00 0.00 0.02
#&gt; TCGA.AB.2855.03     2  0.4213    -0.0610 0.18 0.66 0.16 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2978.03     4  0.0808     0.7958 0.00 0.04 0.00 0.96 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2952.03     2  0.2938     0.5855 0.30 0.70 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2868.03     2  0.2938     0.5855 0.30 0.70 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2908.03     4  0.3619     0.6844 0.14 0.12 0.00 0.74 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2938.03     4  0.2862     0.7549 0.08 0.10 0.00 0.82 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2923.03     2  0.4100    -0.2476 0.36 0.58 0.06 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2890.03     2  0.3746     0.5642 0.32 0.64 0.00 0.04 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2988.03     5  0.3618     0.5028 0.02 0.00 0.00 0.00 0.60 0.00 0.38 0.00
#&gt; TCGA.AB.2985.03     7  0.3169     0.7263 0.18 0.00 0.00 0.02 0.02 0.00 0.78 0.00
#&gt; TCGA.AB.2880.03     3  0.1341     0.8139 0.00 0.00 0.92 0.00 0.00 0.08 0.00 0.00
#&gt; TCGA.AB.2889.03     8  0.0471     1.0000 0.00 0.00 0.02 0.00 0.00 0.00 0.00 0.98
#&gt; TCGA.AB.2887.03     4  0.0808     0.7958 0.00 0.04 0.00 0.96 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2881.03     8  0.0471     1.0000 0.00 0.00 0.02 0.00 0.00 0.00 0.00 0.98
#&gt; TCGA.AB.2834.03     2  0.4832    -0.3013 0.26 0.54 0.20 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2943.03     2  0.5237     0.1764 0.30 0.40 0.00 0.30 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2982.03     6  0.0000     0.9983 0.00 0.00 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2844.03     7  0.2114     0.7827 0.00 0.00 0.16 0.00 0.00 0.00 0.84 0.00
#&gt; TCGA.AB.2870.03     8  0.0471     1.0000 0.00 0.00 0.02 0.00 0.00 0.00 0.00 0.98
#&gt; TCGA.AB.2813.03     4  0.4747     0.4349 0.30 0.16 0.00 0.54 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2894.03     4  0.4530     0.6154 0.24 0.00 0.06 0.66 0.02 0.00 0.00 0.02
#&gt; TCGA.AB.2909.03     3  0.3095     0.7233 0.00 0.00 0.74 0.00 0.00 0.02 0.00 0.24
#&gt; TCGA.AB.2858.03     3  0.4040     0.5331 0.02 0.00 0.58 0.00 0.00 0.02 0.00 0.38
#&gt; TCGA.AB.2935.03     2  0.2938     0.5855 0.30 0.70 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2929.03     2  0.3015     0.5817 0.32 0.68 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2831.03     4  0.1804     0.7859 0.02 0.08 0.00 0.90 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2826.03     2  0.4100    -0.2476 0.36 0.58 0.06 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2993.03     7  0.0000     0.8878 0.00 0.00 0.00 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2810.03     2  0.4100    -0.2476 0.36 0.58 0.06 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2924.03     7  0.0000     0.8878 0.00 0.00 0.00 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2901.03     2  0.2981     0.0911 0.22 0.76 0.02 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2975.03     4  0.0808     0.7958 0.00 0.04 0.00 0.96 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2860.03     2  0.2938     0.5855 0.30 0.70 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2854.03     2  0.2938     0.5855 0.30 0.70 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2846.03     8  0.0471     1.0000 0.00 0.00 0.02 0.00 0.00 0.00 0.00 0.98
</code></pre>

<script>
$('#tab-node-0-get-classes-7-a').parent().next().next().hide();
$('#tab-node-0-get-classes-7-a').click(function(){
  $('#tab-node-0-get-classes-7-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>
</div>

Heatmaps for the consensus matrix. It visualizes the probability of two
samples to be in a same group.




<script>
$( function() {
	$( '#tabs-node-0-consensus-heatmap' ).tabs();
} );
</script>
<div id='tabs-node-0-consensus-heatmap'>
<ul>
<li><a href='#tab-node-0-consensus-heatmap-1'>k = 2</a></li>
<li><a href='#tab-node-0-consensus-heatmap-2'>k = 3</a></li>
<li><a href='#tab-node-0-consensus-heatmap-3'>k = 4</a></li>
<li><a href='#tab-node-0-consensus-heatmap-4'>k = 5</a></li>
<li><a href='#tab-node-0-consensus-heatmap-5'>k = 6</a></li>
<li><a href='#tab-node-0-consensus-heatmap-6'>k = 7</a></li>
<li><a href='#tab-node-0-consensus-heatmap-7'>k = 8</a></li>
</ul>
<div id='tab-node-0-consensus-heatmap-1'>
<pre><code class="r">consensus_heatmap(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-0-consensus-heatmap-1-1.png" alt="plot of chunk tab-node-0-consensus-heatmap-1"/></p>

</div>
<div id='tab-node-0-consensus-heatmap-2'>
<pre><code class="r">consensus_heatmap(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-0-consensus-heatmap-2-1.png" alt="plot of chunk tab-node-0-consensus-heatmap-2"/></p>

</div>
<div id='tab-node-0-consensus-heatmap-3'>
<pre><code class="r">consensus_heatmap(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-0-consensus-heatmap-3-1.png" alt="plot of chunk tab-node-0-consensus-heatmap-3"/></p>

</div>
<div id='tab-node-0-consensus-heatmap-4'>
<pre><code class="r">consensus_heatmap(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-0-consensus-heatmap-4-1.png" alt="plot of chunk tab-node-0-consensus-heatmap-4"/></p>

</div>
<div id='tab-node-0-consensus-heatmap-5'>
<pre><code class="r">consensus_heatmap(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-0-consensus-heatmap-5-1.png" alt="plot of chunk tab-node-0-consensus-heatmap-5"/></p>

</div>
<div id='tab-node-0-consensus-heatmap-6'>
<pre><code class="r">consensus_heatmap(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-0-consensus-heatmap-6-1.png" alt="plot of chunk tab-node-0-consensus-heatmap-6"/></p>

</div>
<div id='tab-node-0-consensus-heatmap-7'>
<pre><code class="r">consensus_heatmap(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-0-consensus-heatmap-7-1.png" alt="plot of chunk tab-node-0-consensus-heatmap-7"/></p>

</div>
</div>

Heatmaps for the membership of samples in all partitions to see how consistent they are:





<script>
$( function() {
	$( '#tabs-node-0-membership-heatmap' ).tabs();
} );
</script>
<div id='tabs-node-0-membership-heatmap'>
<ul>
<li><a href='#tab-node-0-membership-heatmap-1'>k = 2</a></li>
<li><a href='#tab-node-0-membership-heatmap-2'>k = 3</a></li>
<li><a href='#tab-node-0-membership-heatmap-3'>k = 4</a></li>
<li><a href='#tab-node-0-membership-heatmap-4'>k = 5</a></li>
<li><a href='#tab-node-0-membership-heatmap-5'>k = 6</a></li>
<li><a href='#tab-node-0-membership-heatmap-6'>k = 7</a></li>
<li><a href='#tab-node-0-membership-heatmap-7'>k = 8</a></li>
</ul>
<div id='tab-node-0-membership-heatmap-1'>
<pre><code class="r">membership_heatmap(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-0-membership-heatmap-1-1.png" alt="plot of chunk tab-node-0-membership-heatmap-1"/></p>

</div>
<div id='tab-node-0-membership-heatmap-2'>
<pre><code class="r">membership_heatmap(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-0-membership-heatmap-2-1.png" alt="plot of chunk tab-node-0-membership-heatmap-2"/></p>

</div>
<div id='tab-node-0-membership-heatmap-3'>
<pre><code class="r">membership_heatmap(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-0-membership-heatmap-3-1.png" alt="plot of chunk tab-node-0-membership-heatmap-3"/></p>

</div>
<div id='tab-node-0-membership-heatmap-4'>
<pre><code class="r">membership_heatmap(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-0-membership-heatmap-4-1.png" alt="plot of chunk tab-node-0-membership-heatmap-4"/></p>

</div>
<div id='tab-node-0-membership-heatmap-5'>
<pre><code class="r">membership_heatmap(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-0-membership-heatmap-5-1.png" alt="plot of chunk tab-node-0-membership-heatmap-5"/></p>

</div>
<div id='tab-node-0-membership-heatmap-6'>
<pre><code class="r">membership_heatmap(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-0-membership-heatmap-6-1.png" alt="plot of chunk tab-node-0-membership-heatmap-6"/></p>

</div>
<div id='tab-node-0-membership-heatmap-7'>
<pre><code class="r">membership_heatmap(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-0-membership-heatmap-7-1.png" alt="plot of chunk tab-node-0-membership-heatmap-7"/></p>

</div>
</div>

As soon as the classes for columns are determined, the signatures
that are significantly different between subgroups can be looked for. 
Following are the heatmaps for signatures.






<script>
$( function() {
	$( '#tabs-node-0-get-signatures' ).tabs();
} );
</script>
<div id='tabs-node-0-get-signatures'>
<ul>
<li><a href='#tab-node-0-get-signatures-1'>k = 2</a></li>
<li><a href='#tab-node-0-get-signatures-2'>k = 3</a></li>
<li><a href='#tab-node-0-get-signatures-3'>k = 4</a></li>
<li><a href='#tab-node-0-get-signatures-4'>k = 5</a></li>
<li><a href='#tab-node-0-get-signatures-5'>k = 6</a></li>
<li><a href='#tab-node-0-get-signatures-6'>k = 7</a></li>
<li><a href='#tab-node-0-get-signatures-7'>k = 8</a></li>
</ul>
<div id='tab-node-0-get-signatures-1'>
<pre><code class="r">get_signatures(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-0-get-signatures-1-1.png" alt="plot of chunk tab-node-0-get-signatures-1"/></p>

</div>
<div id='tab-node-0-get-signatures-2'>
<pre><code class="r">get_signatures(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-0-get-signatures-2-1.png" alt="plot of chunk tab-node-0-get-signatures-2"/></p>

</div>
<div id='tab-node-0-get-signatures-3'>
<pre><code class="r">get_signatures(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-0-get-signatures-3-1.png" alt="plot of chunk tab-node-0-get-signatures-3"/></p>

</div>
<div id='tab-node-0-get-signatures-4'>
<pre><code class="r">get_signatures(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-0-get-signatures-4-1.png" alt="plot of chunk tab-node-0-get-signatures-4"/></p>

</div>
<div id='tab-node-0-get-signatures-5'>
<pre><code class="r">get_signatures(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-0-get-signatures-5-1.png" alt="plot of chunk tab-node-0-get-signatures-5"/></p>

</div>
<div id='tab-node-0-get-signatures-6'>
<pre><code class="r">get_signatures(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-0-get-signatures-6-1.png" alt="plot of chunk tab-node-0-get-signatures-6"/></p>

</div>
<div id='tab-node-0-get-signatures-7'>
<pre><code class="r">get_signatures(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-0-get-signatures-7-1.png" alt="plot of chunk tab-node-0-get-signatures-7"/></p>

</div>
</div>



Compare the overlap of signatures from different k:

```r
compare_signatures(res)
```

![plot of chunk node-0-signature_compare](figure_cola/node-0-signature_compare-1.png)

`get_signature()` returns a data frame invisibly. To get the list of signatures, the function
call should be assigned to a variable explicitly. In following code, if `plot` argument is set
to `FALSE`, no heatmap is plotted while only the differential analysis is performed.

```r
# code only for demonstration
tb = get_signature(res, k = ..., plot = FALSE)
```

An example of the output of `tb` is:

```
#>   which_row         fdr    mean_1    mean_2 scaled_mean_1 scaled_mean_2 km
#> 1        38 0.042760348  8.373488  9.131774    -0.5533452     0.5164555  1
#> 2        40 0.018707592  7.106213  8.469186    -0.6173731     0.5762149  1
#> 3        55 0.019134737 10.221463 11.207825    -0.6159697     0.5749050  1
#> 4        59 0.006059896  5.921854  7.869574    -0.6899429     0.6439467  1
#> 5        60 0.018055526  8.928898 10.211722    -0.6204761     0.5791110  1
#> 6        98 0.009384629 15.714769 14.887706     0.6635654    -0.6193277  2
...
```

The columns in `tb` are:

1. `which_row`: row indices corresponding to the input matrix.
2. `fdr`: FDR for the differential test. 
3. `mean_x`: The mean value in group x.
4. `scaled_mean_x`: The mean value in group x after rows are scaled.
5. `km`: Row groups if k-means clustering is applied to rows (which is done by automatically selecting number of clusters).

If there are too many signatures, `top_signatures = ...` can be set to only show the 
signatures with the highest FDRs:

```r
# code only for demonstration
# e.g. to show the top 500 most significant rows
tb = get_signature(res, k = ..., top_signatures = 500)
```

If the signatures are defined as these which are uniquely high in current group, `diff_method` argument
can be set to `"uniquely_high_in_one_group"`:

```r
# code only for demonstration
tb = get_signature(res, k = ..., diff_method = "uniquely_high_in_one_group")
```




UMAP plot which shows how samples are separated.


<script>
$( function() {
	$( '#tabs-node-0-dimension-reduction' ).tabs();
} );
</script>
<div id='tabs-node-0-dimension-reduction'>
<ul>
<li><a href='#tab-node-0-dimension-reduction-1'>k = 2</a></li>
<li><a href='#tab-node-0-dimension-reduction-2'>k = 3</a></li>
<li><a href='#tab-node-0-dimension-reduction-3'>k = 4</a></li>
<li><a href='#tab-node-0-dimension-reduction-4'>k = 5</a></li>
<li><a href='#tab-node-0-dimension-reduction-5'>k = 6</a></li>
<li><a href='#tab-node-0-dimension-reduction-6'>k = 7</a></li>
<li><a href='#tab-node-0-dimension-reduction-7'>k = 8</a></li>
</ul>
<div id='tab-node-0-dimension-reduction-1'>
<pre><code class="r">dimension_reduction(res, k = 2, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-0-dimension-reduction-1-1.png" alt="plot of chunk tab-node-0-dimension-reduction-1"/></p>

</div>
<div id='tab-node-0-dimension-reduction-2'>
<pre><code class="r">dimension_reduction(res, k = 3, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-0-dimension-reduction-2-1.png" alt="plot of chunk tab-node-0-dimension-reduction-2"/></p>

</div>
<div id='tab-node-0-dimension-reduction-3'>
<pre><code class="r">dimension_reduction(res, k = 4, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-0-dimension-reduction-3-1.png" alt="plot of chunk tab-node-0-dimension-reduction-3"/></p>

</div>
<div id='tab-node-0-dimension-reduction-4'>
<pre><code class="r">dimension_reduction(res, k = 5, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-0-dimension-reduction-4-1.png" alt="plot of chunk tab-node-0-dimension-reduction-4"/></p>

</div>
<div id='tab-node-0-dimension-reduction-5'>
<pre><code class="r">dimension_reduction(res, k = 6, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-0-dimension-reduction-5-1.png" alt="plot of chunk tab-node-0-dimension-reduction-5"/></p>

</div>
<div id='tab-node-0-dimension-reduction-6'>
<pre><code class="r">dimension_reduction(res, k = 7, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-0-dimension-reduction-6-1.png" alt="plot of chunk tab-node-0-dimension-reduction-6"/></p>

</div>
<div id='tab-node-0-dimension-reduction-7'>
<pre><code class="r">dimension_reduction(res, k = 8, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-0-dimension-reduction-7-1.png" alt="plot of chunk tab-node-0-dimension-reduction-7"/></p>

</div>
</div>



Following heatmap shows how subgroups are split when increasing `k`:

```r
collect_classes(res)
```

![plot of chunk node-0-collect-classes](figure_cola/node-0-collect-classes-1.png)



If matrix rows can be associated to genes, consider to use `functional_enrichment(res,
...)` to perform function enrichment for the signature genes. See [this vignette](https://jokergoo.github.io/cola_vignettes/functional_enrichment.html) for more detailed explanations.


 

---------------------------------------------------




### Node01


Parent node: [Node0](#Node0).
Child nodes: 
                [Node011](#Node011)
        ,
                Node012-leaf
        ,
                [Node013](#Node013)
        ,
                [Node014](#Node014)
        ,
                [Node021](#Node021)
        ,
                [Node022](#Node022)
        ,
                [Node023](#Node023)
        ,
                Node031-leaf
        ,
                [Node032](#Node032)
        ,
                [Node033](#Node033)
        ,
                Node034-leaf
        .







The object with results only for a single top-value method and a single partitioning method 
can be extracted as:

```r
res = res_rh["01"]
```

A summary of `res` and all the functions that can be applied to it:

```r
res
```

```
#> A 'ConsensusPartition' object with k = 2, 3, 4, 5, 6, 7, 8.
#>   On a matrix with 30000 rows and 51 columns.
#>   Top rows (1000) are extracted by 'ATC' method.
#>   Subgroups are detected by 'kmeans' method.
#>   Performed in total 350 partitions by row resampling.
#>   Best k for subgroups seems to be 4.
#> 
#> Following methods can be applied to this 'ConsensusPartition' object:
#>  [1] "cola_report"             "collect_classes"         "collect_plots"          
#>  [4] "collect_stats"           "colnames"                "compare_partitions"     
#>  [7] "compare_signatures"      "consensus_heatmap"       "dimension_reduction"    
#> [10] "functional_enrichment"   "get_anno_col"            "get_anno"               
#> [13] "get_classes"             "get_consensus"           "get_matrix"             
#> [16] "get_membership"          "get_param"               "get_signatures"         
#> [19] "get_stats"               "is_best_k"               "is_stable_k"            
#> [22] "membership_heatmap"      "ncol"                    "nrow"                   
#> [25] "plot_ecdf"               "predict_classes"         "rownames"               
#> [28] "select_partition_number" "show"                    "suggest_best_k"         
#> [31] "test_to_known_factors"   "top_rows_heatmap"
```

`collect_plots()` function collects all the plots made from `res` for all `k` (number of subgroups)
into one single page to provide an easy and fast comparison between different `k`.

```r
collect_plots(res)
```

![plot of chunk node-01-collect-plots](figure_cola/node-01-collect-plots-1.png)

The plots are:

- The first row: a plot of the eCDF (empirical cumulative distribution
  function) curves of the consensus matrix for each `k` and the heatmap of
  predicted classes for each `k`.
- The second row: heatmaps of the consensus matrix for each `k`.
- The third row: heatmaps of the membership matrix for each `k`.
- The fouth row: heatmaps of the signatures for each `k`.

All the plots in panels can be made by individual functions and they are
plotted later in this section.

`select_partition_number()` produces several plots showing different
statistics for choosing "optimized" `k`. There are following statistics:

- eCDF curves of the consensus matrix for each `k`;
- 1-PAC. [The PAC score](https://en.wikipedia.org/wiki/Consensus_clustering#Over-interpretation_potential_of_consensus_clustering)
  measures the proportion of the ambiguous subgrouping.
- Mean silhouette score.
- Concordance. The mean probability of fiting the consensus subgroup labels in all
  partitions.
- Area increased. Denote $A_k$ as the area under the eCDF curve for current
  `k`, the area increased is defined as $A_k - A_{k-1}$.
- Rand index. The percent of pairs of samples that are both in a same cluster
  or both are not in a same cluster in the partition of k and k-1.
- Jaccard index. The ratio of pairs of samples are both in a same cluster in
  the partition of k and k-1 and the pairs of samples are both in a same
  cluster in the partition k or k-1.

The detailed explanations of these statistics can be found in [the _cola_
vignette](https://jokergoo.github.io/cola_vignettes/cola.html#toc_13).

Generally speaking, higher 1-PAC score, higher mean silhouette score or higher
concordance corresponds to better partition. Rand index and Jaccard index
measure how similar the current partition is compared to partition with `k-1`.
If they are too similar, we won't accept `k` is better than `k-1`.

```r
select_partition_number(res)
```

![plot of chunk node-01-select-partition-number](figure_cola/node-01-select-partition-number-1.png)

The numeric values for all these statistics can be obtained by `get_stats()`.

```r
get_stats(res)
```

```
#>   k 1-PAC mean_silhouette concordance area_increased  Rand Jaccard
#> 2 2 0.958           0.904       0.967         0.5020 0.495   0.495
#> 3 3 0.946           0.961       0.982         0.3334 0.664   0.424
#> 4 4 1.000           0.991       0.993         0.1271 0.807   0.501
#> 5 5 0.880           0.831       0.871         0.0543 1.000   1.000
#> 6 6 0.815           0.677       0.826         0.0385 0.929   0.721
#> 7 7 0.830           0.777       0.805         0.0296 0.936   0.672
#> 8 8 0.832           0.810       0.770         0.0122 0.968   0.768
```

`suggest_best_k()` suggests the best $k$ based on these statistics. The rules are as follows:

- All $k$ with Jaccard index larger than 0.95 are removed because increasing
  $k$ does not provide enough extra information. If all $k$ are removed, it is
  marked as no subgroup is detected.
- For all $k$ with 1-PAC score larger than 0.9, the maximal $k$ is taken as
  the best $k$, and other $k$ are marked as optional $k$.
- If it does not fit the second rule. The $k$ with the maximal vote of the
  highest 1-PAC score, highest mean silhouette, and highest concordance is
  taken as the best $k$.

```r
suggest_best_k(res)
```

```
#> [1] 4
#> attr(,"optional")
#> [1] 2 3
```

There is also optional best $k$ = 2 3 that is worth to check.

Following is the table of the partitions (You need to click the **show/hide
code output** link to see it). The membership matrix (columns with name `p*`)
is inferred by
[`clue::cl_consensus()`](https://www.rdocumentation.org/link/cl_consensus?package=clue)
function with the `SE` method. Basically the value in the membership matrix
represents the probability to belong to a certain group. The finall subgroup
label for an item is determined with the group with highest probability it
belongs to.

In `get_classes()` function, the entropy is calculated from the membership
matrix and the silhouette score is calculated from the consensus matrix.



<script>
$( function() {
	$( '#tabs-node-01-get-classes' ).tabs();
} );
</script>
<div id='tabs-node-01-get-classes'>
<ul>
<li><a href='#tab-node-01-get-classes-1'>k = 2</a></li>
<li><a href='#tab-node-01-get-classes-2'>k = 3</a></li>
<li><a href='#tab-node-01-get-classes-3'>k = 4</a></li>
<li><a href='#tab-node-01-get-classes-4'>k = 5</a></li>
<li><a href='#tab-node-01-get-classes-5'>k = 6</a></li>
<li><a href='#tab-node-01-get-classes-6'>k = 7</a></li>
<li><a href='#tab-node-01-get-classes-7'>k = 8</a></li>
</ul>

<div id='tab-node-01-get-classes-1'>
<p><a id='tab-node-01-get-classes-1-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 2), get_membership(res, k = 2))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2
#&gt; TCGA.AB.2884.03     1   0.000    0.95284 1.00 0.00
#&gt; TCGA.AB.2913.03     2   0.000    0.97124 0.00 1.00
#&gt; TCGA.AB.2837.03     2   0.000    0.97124 0.00 1.00
#&gt; TCGA.AB.2836.03     2   0.000    0.97124 0.00 1.00
#&gt; TCGA.AB.2945.03     1   0.000    0.95284 1.00 0.00
#&gt; TCGA.AB.2963.03     2   0.000    0.97124 0.00 1.00
#&gt; TCGA.AB.2967.03     2   0.000    0.97124 0.00 1.00
#&gt; TCGA.AB.2809.03     1   0.000    0.95284 1.00 0.00
#&gt; TCGA.AB.2802.03     1   0.000    0.95284 1.00 0.00
#&gt; TCGA.AB.2851.03     1   0.971    0.32405 0.60 0.40
#&gt; TCGA.AB.2853.03     1   0.000    0.95284 1.00 0.00
#&gt; TCGA.AB.2811.03     1   0.000    0.95284 1.00 0.00
#&gt; TCGA.AB.2895.03     1   0.000    0.95284 1.00 0.00
#&gt; TCGA.AB.2827.03     2   0.000    0.97124 0.00 1.00
#&gt; TCGA.AB.2932.03     2   0.000    0.97124 0.00 1.00
#&gt; TCGA.AB.2824.03     2   0.760    0.68901 0.22 0.78
#&gt; TCGA.AB.2972.03     2   0.000    0.97124 0.00 1.00
#&gt; TCGA.AB.2965.03     1   0.000    0.95284 1.00 0.00
#&gt; TCGA.AB.2842.03     1   0.402    0.87685 0.92 0.08
#&gt; TCGA.AB.2869.03     1   0.000    0.95284 1.00 0.00
#&gt; TCGA.AB.2911.03     2   0.000    0.97124 0.00 1.00
#&gt; TCGA.AB.2918.03     2   0.000    0.97124 0.00 1.00
#&gt; TCGA.AB.3006.03     2   1.000   -0.07177 0.50 0.50
#&gt; TCGA.AB.2848.03     2   0.000    0.97124 0.00 1.00
#&gt; TCGA.AB.2969.03     1   0.000    0.95284 1.00 0.00
#&gt; TCGA.AB.2839.03     2   0.000    0.97124 0.00 1.00
#&gt; TCGA.AB.2835.03     2   0.000    0.97124 0.00 1.00
#&gt; TCGA.AB.2974.03     1   0.000    0.95284 1.00 0.00
#&gt; TCGA.AB.2986.03     2   0.000    0.97124 0.00 1.00
#&gt; TCGA.AB.2931.03     1   0.000    0.95284 1.00 0.00
#&gt; TCGA.AB.2896.03     1   0.000    0.95284 1.00 0.00
#&gt; TCGA.AB.2812.03     2   0.000    0.97124 0.00 1.00
#&gt; TCGA.AB.3011.03     1   1.000   -0.00632 0.50 0.50
#&gt; TCGA.AB.2946.03     2   0.000    0.97124 0.00 1.00
#&gt; TCGA.AB.2856.03     2   0.000    0.97124 0.00 1.00
#&gt; TCGA.AB.2879.03     2   0.000    0.97124 0.00 1.00
#&gt; TCGA.AB.2976.03     2   0.000    0.97124 0.00 1.00
#&gt; TCGA.AB.2989.03     2   0.000    0.97124 0.00 1.00
#&gt; TCGA.AB.2981.03     1   0.000    0.95284 1.00 0.00
#&gt; TCGA.AB.2973.03     2   0.000    0.97124 0.00 1.00
#&gt; TCGA.AB.2818.03     2   0.000    0.97124 0.00 1.00
#&gt; TCGA.AB.2930.03     2   0.000    0.97124 0.00 1.00
#&gt; TCGA.AB.2816.03     1   0.000    0.95284 1.00 0.00
#&gt; TCGA.AB.2925.03     1   0.000    0.95284 1.00 0.00
#&gt; TCGA.AB.2825.03     1   0.000    0.95284 1.00 0.00
#&gt; TCGA.AB.2947.03     1   0.000    0.95284 1.00 0.00
#&gt; TCGA.AB.2988.03     1   0.000    0.95284 1.00 0.00
#&gt; TCGA.AB.2985.03     1   0.000    0.95284 1.00 0.00
#&gt; TCGA.AB.2844.03     2   0.000    0.97124 0.00 1.00
#&gt; TCGA.AB.2993.03     2   0.000    0.97124 0.00 1.00
#&gt; TCGA.AB.2924.03     2   0.000    0.97124 0.00 1.00
</code></pre>

<script>
$('#tab-node-01-get-classes-1-a').parent().next().next().hide();
$('#tab-node-01-get-classes-1-a').click(function(){
  $('#tab-node-01-get-classes-1-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-01-get-classes-2'>
<p><a id='tab-node-01-get-classes-2-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 3), get_membership(res, k = 3))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette  p1   p2   p3
#&gt; TCGA.AB.2884.03     1   0.000      1.000 1.0 0.00 0.00
#&gt; TCGA.AB.2913.03     2   0.000      1.000 0.0 1.00 0.00
#&gt; TCGA.AB.2837.03     3   0.000      0.955 0.0 0.00 1.00
#&gt; TCGA.AB.2836.03     2   0.000      1.000 0.0 1.00 0.00
#&gt; TCGA.AB.2945.03     3   0.000      0.955 0.0 0.00 1.00
#&gt; TCGA.AB.2963.03     3   0.000      0.955 0.0 0.00 1.00
#&gt; TCGA.AB.2967.03     2   0.000      1.000 0.0 1.00 0.00
#&gt; TCGA.AB.2809.03     1   0.000      1.000 1.0 0.00 0.00
#&gt; TCGA.AB.2802.03     1   0.000      1.000 1.0 0.00 0.00
#&gt; TCGA.AB.2851.03     3   0.000      0.955 0.0 0.00 1.00
#&gt; TCGA.AB.2853.03     1   0.000      1.000 1.0 0.00 0.00
#&gt; TCGA.AB.2811.03     1   0.000      1.000 1.0 0.00 0.00
#&gt; TCGA.AB.2895.03     1   0.000      1.000 1.0 0.00 0.00
#&gt; TCGA.AB.2827.03     2   0.000      1.000 0.0 1.00 0.00
#&gt; TCGA.AB.2932.03     3   0.000      0.955 0.0 0.00 1.00
#&gt; TCGA.AB.2824.03     3   0.000      0.955 0.0 0.00 1.00
#&gt; TCGA.AB.2972.03     3   0.000      0.955 0.0 0.00 1.00
#&gt; TCGA.AB.2965.03     1   0.000      1.000 1.0 0.00 0.00
#&gt; TCGA.AB.2842.03     3   0.000      0.955 0.0 0.00 1.00
#&gt; TCGA.AB.2869.03     3   0.000      0.955 0.0 0.00 1.00
#&gt; TCGA.AB.2911.03     2   0.000      1.000 0.0 1.00 0.00
#&gt; TCGA.AB.2918.03     2   0.000      1.000 0.0 1.00 0.00
#&gt; TCGA.AB.3006.03     3   0.000      0.955 0.0 0.00 1.00
#&gt; TCGA.AB.2848.03     3   0.000      0.955 0.0 0.00 1.00
#&gt; TCGA.AB.2969.03     1   0.000      1.000 1.0 0.00 0.00
#&gt; TCGA.AB.2839.03     2   0.000      1.000 0.0 1.00 0.00
#&gt; TCGA.AB.2835.03     3   0.455      0.762 0.0 0.20 0.80
#&gt; TCGA.AB.2974.03     1   0.000      1.000 1.0 0.00 0.00
#&gt; TCGA.AB.2986.03     2   0.000      1.000 0.0 1.00 0.00
#&gt; TCGA.AB.2931.03     1   0.000      1.000 1.0 0.00 0.00
#&gt; TCGA.AB.2896.03     1   0.000      1.000 1.0 0.00 0.00
#&gt; TCGA.AB.2812.03     2   0.000      1.000 0.0 1.00 0.00
#&gt; TCGA.AB.3011.03     3   0.000      0.955 0.0 0.00 1.00
#&gt; TCGA.AB.2946.03     2   0.000      1.000 0.0 1.00 0.00
#&gt; TCGA.AB.2856.03     2   0.000      1.000 0.0 1.00 0.00
#&gt; TCGA.AB.2879.03     3   0.571      0.567 0.0 0.32 0.68
#&gt; TCGA.AB.2976.03     3   0.000      0.955 0.0 0.00 1.00
#&gt; TCGA.AB.2989.03     2   0.000      1.000 0.0 1.00 0.00
#&gt; TCGA.AB.2981.03     1   0.000      1.000 1.0 0.00 0.00
#&gt; TCGA.AB.2973.03     3   0.000      0.955 0.0 0.00 1.00
#&gt; TCGA.AB.2818.03     3   0.000      0.955 0.0 0.00 1.00
#&gt; TCGA.AB.2930.03     2   0.000      1.000 0.0 1.00 0.00
#&gt; TCGA.AB.2816.03     3   0.000      0.955 0.0 0.00 1.00
#&gt; TCGA.AB.2925.03     1   0.000      1.000 1.0 0.00 0.00
#&gt; TCGA.AB.2825.03     1   0.000      1.000 1.0 0.00 0.00
#&gt; TCGA.AB.2947.03     1   0.000      1.000 1.0 0.00 0.00
#&gt; TCGA.AB.2988.03     3   0.455      0.737 0.2 0.00 0.80
#&gt; TCGA.AB.2985.03     3   0.000      0.955 0.0 0.00 1.00
#&gt; TCGA.AB.2844.03     2   0.000      1.000 0.0 1.00 0.00
#&gt; TCGA.AB.2993.03     3   0.000      0.955 0.0 0.00 1.00
#&gt; TCGA.AB.2924.03     3   0.455      0.762 0.0 0.20 0.80
</code></pre>

<script>
$('#tab-node-01-get-classes-2-a').parent().next().next().hide();
$('#tab-node-01-get-classes-2-a').click(function(){
  $('#tab-node-01-get-classes-2-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-01-get-classes-3'>
<p><a id='tab-node-01-get-classes-3-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 4), get_membership(res, k = 4))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4
#&gt; TCGA.AB.2884.03     3  0.0000      0.983 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2913.03     2  0.0000      1.000 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2837.03     4  0.0000      0.992 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2836.03     4  0.0707      0.983 0.00 0.02 0.00 0.98
#&gt; TCGA.AB.2945.03     3  0.0000      0.983 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2963.03     4  0.0000      0.992 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2967.03     4  0.0707      0.983 0.00 0.02 0.00 0.98
#&gt; TCGA.AB.2809.03     1  0.0000      0.992 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2802.03     1  0.0707      0.989 0.98 0.00 0.02 0.00
#&gt; TCGA.AB.2851.03     3  0.0707      0.991 0.00 0.00 0.98 0.02
#&gt; TCGA.AB.2853.03     1  0.0000      0.992 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2811.03     1  0.0707      0.989 0.98 0.00 0.02 0.00
#&gt; TCGA.AB.2895.03     1  0.0000      0.992 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2827.03     4  0.0707      0.983 0.00 0.02 0.00 0.98
#&gt; TCGA.AB.2932.03     4  0.0000      0.992 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2824.03     3  0.0707      0.991 0.00 0.00 0.98 0.02
#&gt; TCGA.AB.2972.03     3  0.0707      0.991 0.00 0.00 0.98 0.02
#&gt; TCGA.AB.2965.03     1  0.0000      0.992 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2842.03     3  0.0707      0.991 0.00 0.00 0.98 0.02
#&gt; TCGA.AB.2869.03     3  0.0000      0.983 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2911.03     4  0.0707      0.983 0.00 0.02 0.00 0.98
#&gt; TCGA.AB.2918.03     2  0.0000      1.000 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.3006.03     3  0.0707      0.991 0.00 0.00 0.98 0.02
#&gt; TCGA.AB.2848.03     4  0.0000      0.992 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2969.03     1  0.0707      0.989 0.98 0.00 0.02 0.00
#&gt; TCGA.AB.2839.03     2  0.0000      1.000 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2835.03     4  0.0000      0.992 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2974.03     1  0.0707      0.989 0.98 0.00 0.02 0.00
#&gt; TCGA.AB.2986.03     2  0.0000      1.000 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2931.03     1  0.0707      0.989 0.98 0.00 0.02 0.00
#&gt; TCGA.AB.2896.03     1  0.0000      0.992 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2812.03     2  0.0000      1.000 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.3011.03     3  0.0707      0.991 0.00 0.00 0.98 0.02
#&gt; TCGA.AB.2946.03     2  0.0000      1.000 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2856.03     2  0.0000      1.000 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2879.03     4  0.0000      0.992 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2976.03     4  0.0000      0.992 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2989.03     2  0.0000      1.000 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2981.03     1  0.0000      0.992 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2973.03     4  0.0000      0.992 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2818.03     4  0.0000      0.992 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2930.03     4  0.0707      0.983 0.00 0.02 0.00 0.98
#&gt; TCGA.AB.2816.03     3  0.0707      0.991 0.00 0.00 0.98 0.02
#&gt; TCGA.AB.2925.03     1  0.0000      0.992 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2825.03     1  0.0000      0.992 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2947.03     1  0.0707      0.989 0.98 0.00 0.02 0.00
#&gt; TCGA.AB.2988.03     3  0.0000      0.983 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2985.03     3  0.0707      0.991 0.00 0.00 0.98 0.02
#&gt; TCGA.AB.2844.03     2  0.0000      1.000 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2993.03     4  0.0000      0.992 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2924.03     4  0.0000      0.992 0.00 0.00 0.00 1.00
</code></pre>

<script>
$('#tab-node-01-get-classes-3-a').parent().next().next().hide();
$('#tab-node-01-get-classes-3-a').click(function(){
  $('#tab-node-01-get-classes-3-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-01-get-classes-4'>
<p><a id='tab-node-01-get-classes-4-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 5), get_membership(res, k = 5))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5
#&gt; TCGA.AB.2884.03     3  0.4307      0.524 0.50 0.00 0.50 0.00 0.00
#&gt; TCGA.AB.2913.03     2  0.0000      0.917 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2837.03     4  0.1410      0.841 0.06 0.00 0.00 0.94 0.00
#&gt; TCGA.AB.2836.03     4  0.4675      0.676 0.38 0.02 0.00 0.60 0.00
#&gt; TCGA.AB.2945.03     3  0.2732      0.863 0.16 0.00 0.84 0.00 0.00
#&gt; TCGA.AB.2963.03     4  0.1043      0.846 0.04 0.00 0.00 0.96 0.00
#&gt; TCGA.AB.2967.03     4  0.4126      0.688 0.38 0.00 0.00 0.62 0.00
#&gt; TCGA.AB.2809.03     5  0.0000      0.856 0.00 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2802.03     5  0.3983      0.803 0.34 0.00 0.00 0.00 0.66
#&gt; TCGA.AB.2851.03     3  0.1043      0.889 0.04 0.00 0.96 0.00 0.00
#&gt; TCGA.AB.2853.03     5  0.0000      0.856 0.00 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2811.03     5  0.3983      0.803 0.34 0.00 0.00 0.00 0.66
#&gt; TCGA.AB.2895.03     5  0.0000      0.856 0.00 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2827.03     4  0.4675      0.676 0.38 0.02 0.00 0.60 0.00
#&gt; TCGA.AB.2932.03     4  0.1043      0.846 0.04 0.00 0.00 0.96 0.00
#&gt; TCGA.AB.2824.03     3  0.1410      0.886 0.06 0.00 0.94 0.00 0.00
#&gt; TCGA.AB.2972.03     3  0.1410      0.886 0.06 0.00 0.94 0.00 0.00
#&gt; TCGA.AB.2965.03     5  0.0000      0.856 0.00 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2842.03     3  0.0609      0.887 0.02 0.00 0.98 0.00 0.00
#&gt; TCGA.AB.2869.03     3  0.2732      0.863 0.16 0.00 0.84 0.00 0.00
#&gt; TCGA.AB.2911.03     4  0.4182      0.685 0.40 0.00 0.00 0.60 0.00
#&gt; TCGA.AB.2918.03     2  0.4060      0.674 0.36 0.64 0.00 0.00 0.00
#&gt; TCGA.AB.3006.03     3  0.1410      0.886 0.06 0.00 0.94 0.00 0.00
#&gt; TCGA.AB.2848.03     4  0.1043      0.850 0.04 0.00 0.00 0.96 0.00
#&gt; TCGA.AB.2969.03     5  0.3983      0.803 0.34 0.00 0.00 0.00 0.66
#&gt; TCGA.AB.2839.03     2  0.0000      0.917 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2835.03     4  0.0609      0.853 0.02 0.00 0.00 0.98 0.00
#&gt; TCGA.AB.2974.03     5  0.3983      0.803 0.34 0.00 0.00 0.00 0.66
#&gt; TCGA.AB.2986.03     2  0.4060      0.674 0.36 0.64 0.00 0.00 0.00
#&gt; TCGA.AB.2931.03     5  0.3983      0.803 0.34 0.00 0.00 0.00 0.66
#&gt; TCGA.AB.2896.03     5  0.0000      0.856 0.00 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2812.03     2  0.0000      0.917 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.3011.03     3  0.1410      0.886 0.06 0.00 0.94 0.00 0.00
#&gt; TCGA.AB.2946.03     2  0.0000      0.917 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2856.03     2  0.0000      0.917 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2879.03     4  0.1043      0.850 0.04 0.00 0.00 0.96 0.00
#&gt; TCGA.AB.2976.03     4  0.1410      0.847 0.06 0.00 0.00 0.94 0.00
#&gt; TCGA.AB.2989.03     2  0.0000      0.917 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2981.03     5  0.0000      0.856 0.00 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2973.03     4  0.1043      0.850 0.04 0.00 0.00 0.96 0.00
#&gt; TCGA.AB.2818.03     4  0.1043      0.852 0.04 0.00 0.00 0.96 0.00
#&gt; TCGA.AB.2930.03     4  0.4675      0.676 0.38 0.02 0.00 0.60 0.00
#&gt; TCGA.AB.2816.03     3  0.2732      0.863 0.16 0.00 0.84 0.00 0.00
#&gt; TCGA.AB.2925.03     5  0.0000      0.856 0.00 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2825.03     5  0.0000      0.856 0.00 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2947.03     5  0.3983      0.803 0.34 0.00 0.00 0.00 0.66
#&gt; TCGA.AB.2988.03     3  0.2732      0.863 0.16 0.00 0.84 0.00 0.00
#&gt; TCGA.AB.2985.03     3  0.0609      0.887 0.02 0.00 0.98 0.00 0.00
#&gt; TCGA.AB.2844.03     2  0.0000      0.917 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2993.03     4  0.1043      0.850 0.04 0.00 0.00 0.96 0.00
#&gt; TCGA.AB.2924.03     4  0.0609      0.853 0.02 0.00 0.00 0.98 0.00
</code></pre>

<script>
$('#tab-node-01-get-classes-4-a').parent().next().next().hide();
$('#tab-node-01-get-classes-4-a').click(function(){
  $('#tab-node-01-get-classes-4-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-01-get-classes-5'>
<p><a id='tab-node-01-get-classes-5-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 6), get_membership(res, k = 6))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5   p6
#&gt; TCGA.AB.2884.03     6  0.7113      0.000 0.12 0.00 0.26 0.00 0.18 0.44
#&gt; TCGA.AB.2913.03     2  0.0000      0.997 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2837.03     4  0.1556      0.797 0.00 0.00 0.00 0.92 0.00 0.08
#&gt; TCGA.AB.2836.03     1  0.2631      0.761 0.82 0.00 0.00 0.18 0.00 0.00
#&gt; TCGA.AB.2945.03     3  0.5447     -0.243 0.12 0.00 0.46 0.00 0.00 0.42
#&gt; TCGA.AB.2963.03     4  0.1480      0.802 0.04 0.00 0.02 0.94 0.00 0.00
#&gt; TCGA.AB.2967.03     1  0.3797      0.456 0.58 0.00 0.00 0.42 0.00 0.00
#&gt; TCGA.AB.2809.03     5  0.3409      0.855 0.00 0.00 0.00 0.00 0.70 0.30
#&gt; TCGA.AB.2802.03     5  0.0547      0.806 0.02 0.00 0.00 0.00 0.98 0.00
#&gt; TCGA.AB.2851.03     3  0.0547      0.587 0.00 0.00 0.98 0.00 0.00 0.02
#&gt; TCGA.AB.2853.03     5  0.3409      0.855 0.00 0.00 0.00 0.00 0.70 0.30
#&gt; TCGA.AB.2811.03     5  0.0000      0.809 0.00 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2895.03     5  0.3409      0.855 0.00 0.00 0.00 0.00 0.70 0.30
#&gt; TCGA.AB.2827.03     1  0.2631      0.761 0.82 0.00 0.00 0.18 0.00 0.00
#&gt; TCGA.AB.2932.03     4  0.1480      0.802 0.04 0.00 0.02 0.94 0.00 0.00
#&gt; TCGA.AB.2824.03     3  0.0547      0.581 0.00 0.00 0.98 0.02 0.00 0.00
#&gt; TCGA.AB.2972.03     3  0.0547      0.581 0.00 0.00 0.98 0.02 0.00 0.00
#&gt; TCGA.AB.2965.03     5  0.2793      0.847 0.00 0.00 0.00 0.00 0.80 0.20
#&gt; TCGA.AB.2842.03     3  0.3985      0.495 0.10 0.00 0.76 0.00 0.00 0.14
#&gt; TCGA.AB.2869.03     3  0.5447     -0.243 0.12 0.00 0.46 0.00 0.00 0.42
#&gt; TCGA.AB.2911.03     1  0.2631      0.761 0.82 0.00 0.00 0.18 0.00 0.00
#&gt; TCGA.AB.2918.03     1  0.4002      0.480 0.66 0.32 0.00 0.00 0.00 0.02
#&gt; TCGA.AB.3006.03     3  0.0000      0.591 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2848.03     4  0.3982      0.753 0.06 0.00 0.00 0.74 0.00 0.20
#&gt; TCGA.AB.2969.03     5  0.0547      0.806 0.02 0.00 0.00 0.00 0.98 0.00
#&gt; TCGA.AB.2839.03     2  0.0000      0.997 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2835.03     4  0.2631      0.763 0.18 0.00 0.00 0.82 0.00 0.00
#&gt; TCGA.AB.2974.03     5  0.0000      0.809 0.00 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2986.03     1  0.4002      0.480 0.66 0.32 0.00 0.00 0.00 0.02
#&gt; TCGA.AB.2931.03     5  0.0000      0.809 0.00 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2896.03     5  0.3409      0.855 0.00 0.00 0.00 0.00 0.70 0.30
#&gt; TCGA.AB.2812.03     2  0.0000      0.997 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.3011.03     3  0.0000      0.591 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2946.03     2  0.0000      0.997 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2856.03     2  0.0000      0.997 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2879.03     4  0.4244      0.746 0.08 0.00 0.00 0.72 0.00 0.20
#&gt; TCGA.AB.2976.03     4  0.2094      0.787 0.08 0.00 0.02 0.90 0.00 0.00
#&gt; TCGA.AB.2989.03     2  0.0000      0.997 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2981.03     5  0.3409      0.855 0.00 0.00 0.00 0.00 0.70 0.30
#&gt; TCGA.AB.2973.03     4  0.4244      0.746 0.08 0.00 0.00 0.72 0.00 0.20
#&gt; TCGA.AB.2818.03     4  0.2094      0.787 0.08 0.00 0.02 0.90 0.00 0.00
#&gt; TCGA.AB.2930.03     1  0.2631      0.761 0.82 0.00 0.00 0.18 0.00 0.00
#&gt; TCGA.AB.2816.03     3  0.5295     -0.264 0.10 0.00 0.46 0.00 0.00 0.44
#&gt; TCGA.AB.2925.03     5  0.3409      0.855 0.00 0.00 0.00 0.00 0.70 0.30
#&gt; TCGA.AB.2825.03     5  0.3409      0.855 0.00 0.00 0.00 0.00 0.70 0.30
#&gt; TCGA.AB.2947.03     5  0.0000      0.809 0.00 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2988.03     3  0.5295     -0.264 0.10 0.00 0.46 0.00 0.00 0.44
#&gt; TCGA.AB.2985.03     3  0.3985      0.495 0.10 0.00 0.76 0.00 0.00 0.14
#&gt; TCGA.AB.2844.03     2  0.0547      0.981 0.00 0.98 0.00 0.00 0.00 0.02
#&gt; TCGA.AB.2993.03     4  0.3982      0.753 0.06 0.00 0.00 0.74 0.00 0.20
#&gt; TCGA.AB.2924.03     4  0.2048      0.775 0.12 0.00 0.00 0.88 0.00 0.00
</code></pre>

<script>
$('#tab-node-01-get-classes-5-a').parent().next().next().hide();
$('#tab-node-01-get-classes-5-a').click(function(){
  $('#tab-node-01-get-classes-5-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-01-get-classes-6'>
<p><a id='tab-node-01-get-classes-6-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 7), get_membership(res, k = 7))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5   p6   p7
#&gt; TCGA.AB.2884.03     6  0.5052     0.5650 0.02 0.00 0.14 0.00 0.00 0.62 0.22
#&gt; TCGA.AB.2913.03     2  0.0000     1.0000 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2837.03     4  0.2016     0.6547 0.00 0.00 0.00 0.90 0.06 0.04 0.00
#&gt; TCGA.AB.2836.03     1  0.2376     0.7735 0.86 0.02 0.00 0.12 0.00 0.00 0.00
#&gt; TCGA.AB.2945.03     6  0.3358     0.8570 0.00 0.00 0.36 0.00 0.00 0.64 0.00
#&gt; TCGA.AB.2963.03     4  0.5740     0.6973 0.06 0.00 0.02 0.60 0.22 0.10 0.00
#&gt; TCGA.AB.2967.03     1  0.6406     0.0519 0.44 0.00 0.00 0.22 0.26 0.08 0.00
#&gt; TCGA.AB.2809.03     5  0.3413     1.0000 0.00 0.00 0.00 0.00 0.62 0.00 0.38
#&gt; TCGA.AB.2802.03     7  0.0504     0.8792 0.00 0.00 0.00 0.00 0.00 0.02 0.98
#&gt; TCGA.AB.2851.03     3  0.0000     0.8307 0.00 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2853.03     5  0.3413     1.0000 0.00 0.00 0.00 0.00 0.62 0.00 0.38
#&gt; TCGA.AB.2811.03     7  0.0863     0.8610 0.04 0.00 0.00 0.00 0.00 0.00 0.96
#&gt; TCGA.AB.2895.03     5  0.3413     1.0000 0.00 0.00 0.00 0.00 0.62 0.00 0.38
#&gt; TCGA.AB.2827.03     1  0.3208     0.7747 0.82 0.02 0.00 0.12 0.00 0.04 0.00
#&gt; TCGA.AB.2932.03     4  0.5740     0.6973 0.06 0.00 0.02 0.60 0.22 0.10 0.00
#&gt; TCGA.AB.2824.03     3  0.0504     0.8228 0.00 0.00 0.98 0.00 0.00 0.02 0.00
#&gt; TCGA.AB.2972.03     3  0.0504     0.8228 0.00 0.00 0.98 0.00 0.00 0.02 0.00
#&gt; TCGA.AB.2965.03     7  0.3358    -0.2717 0.00 0.00 0.00 0.00 0.36 0.00 0.64
#&gt; TCGA.AB.2842.03     3  0.5086     0.4900 0.06 0.00 0.64 0.00 0.08 0.22 0.00
#&gt; TCGA.AB.2869.03     6  0.3358     0.8570 0.00 0.00 0.36 0.00 0.00 0.64 0.00
#&gt; TCGA.AB.2911.03     1  0.1886     0.7620 0.88 0.00 0.00 0.12 0.00 0.00 0.00
#&gt; TCGA.AB.2918.03     1  0.3519     0.6485 0.74 0.22 0.00 0.00 0.00 0.04 0.00
#&gt; TCGA.AB.3006.03     3  0.0000     0.8307 0.00 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2848.03     4  0.3257     0.5711 0.04 0.00 0.02 0.84 0.02 0.08 0.00
#&gt; TCGA.AB.2969.03     7  0.0504     0.8792 0.00 0.00 0.00 0.00 0.00 0.02 0.98
#&gt; TCGA.AB.2839.03     2  0.0000     1.0000 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2835.03     4  0.5605     0.6932 0.10 0.00 0.00 0.58 0.24 0.08 0.00
#&gt; TCGA.AB.2974.03     7  0.0000     0.8841 0.00 0.00 0.00 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2986.03     1  0.2708     0.6534 0.78 0.22 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2931.03     7  0.0000     0.8841 0.00 0.00 0.00 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2896.03     5  0.3413     1.0000 0.00 0.00 0.00 0.00 0.62 0.00 0.38
#&gt; TCGA.AB.2812.03     2  0.0000     1.0000 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.3011.03     3  0.0000     0.8307 0.00 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2946.03     2  0.0000     1.0000 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2856.03     2  0.0000     1.0000 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2879.03     4  0.3765     0.5240 0.10 0.00 0.00 0.78 0.02 0.10 0.00
#&gt; TCGA.AB.2976.03     4  0.5412     0.6966 0.08 0.00 0.00 0.60 0.24 0.08 0.00
#&gt; TCGA.AB.2989.03     2  0.0000     1.0000 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2981.03     5  0.3413     1.0000 0.00 0.00 0.00 0.00 0.62 0.00 0.38
#&gt; TCGA.AB.2973.03     4  0.2509     0.6020 0.04 0.00 0.02 0.88 0.00 0.06 0.00
#&gt; TCGA.AB.2818.03     4  0.5412     0.6966 0.08 0.00 0.00 0.60 0.24 0.08 0.00
#&gt; TCGA.AB.2930.03     1  0.3975     0.7662 0.78 0.02 0.00 0.12 0.02 0.06 0.00
#&gt; TCGA.AB.2816.03     6  0.3867     0.8287 0.02 0.00 0.38 0.00 0.00 0.60 0.00
#&gt; TCGA.AB.2925.03     5  0.3413     1.0000 0.00 0.00 0.00 0.00 0.62 0.00 0.38
#&gt; TCGA.AB.2825.03     5  0.3413     1.0000 0.00 0.00 0.00 0.00 0.62 0.00 0.38
#&gt; TCGA.AB.2947.03     7  0.0000     0.8841 0.00 0.00 0.00 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2988.03     6  0.3358     0.8570 0.00 0.00 0.36 0.00 0.00 0.64 0.00
#&gt; TCGA.AB.2985.03     3  0.5086     0.4900 0.06 0.00 0.64 0.00 0.08 0.22 0.00
#&gt; TCGA.AB.2844.03     2  0.0000     1.0000 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2993.03     4  0.2769     0.5839 0.04 0.00 0.00 0.86 0.02 0.08 0.00
#&gt; TCGA.AB.2924.03     4  0.5412     0.6966 0.08 0.00 0.00 0.60 0.24 0.08 0.00
</code></pre>

<script>
$('#tab-node-01-get-classes-6-a').parent().next().next().hide();
$('#tab-node-01-get-classes-6-a').click(function(){
  $('#tab-node-01-get-classes-6-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-01-get-classes-7'>
<p><a id='tab-node-01-get-classes-7-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 8), get_membership(res, k = 8))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1  p2   p3   p4   p5   p6   p7   p8
#&gt; TCGA.AB.2884.03     6  0.3871     0.8517 0.00 0.0 0.08 0.00 0.02 0.78 0.08 0.04
#&gt; TCGA.AB.2913.03     2  0.0000     1.0000 0.00 1.0 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2837.03     4  0.3757     0.0673 0.00 0.0 0.00 0.68 0.00 0.06 0.00 0.26
#&gt; TCGA.AB.2836.03     1  0.2406     0.7138 0.80 0.0 0.00 0.20 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2945.03     6  0.2569     0.9371 0.00 0.0 0.16 0.00 0.00 0.82 0.00 0.02
#&gt; TCGA.AB.2963.03     4  0.1557     0.7955 0.00 0.0 0.00 0.92 0.02 0.06 0.00 0.00
#&gt; TCGA.AB.2967.03     4  0.3615     0.5211 0.20 0.0 0.00 0.74 0.02 0.04 0.00 0.00
#&gt; TCGA.AB.2809.03     5  0.3083     1.0000 0.00 0.0 0.00 0.00 0.66 0.00 0.34 0.00
#&gt; TCGA.AB.2802.03     7  0.0000     0.8312 0.00 0.0 0.00 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2851.03     3  0.0000     0.8475 0.00 0.0 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2853.03     5  0.3083     1.0000 0.00 0.0 0.00 0.00 0.66 0.00 0.34 0.00
#&gt; TCGA.AB.2811.03     7  0.4033     0.6476 0.20 0.0 0.00 0.00 0.00 0.00 0.68 0.12
#&gt; TCGA.AB.2895.03     5  0.3083     1.0000 0.00 0.0 0.00 0.00 0.66 0.00 0.34 0.00
#&gt; TCGA.AB.2827.03     1  0.2856     0.7096 0.78 0.0 0.00 0.20 0.00 0.02 0.00 0.00
#&gt; TCGA.AB.2932.03     4  0.1887     0.7878 0.00 0.0 0.00 0.90 0.04 0.06 0.00 0.00
#&gt; TCGA.AB.2824.03     3  0.0000     0.8475 0.00 0.0 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2972.03     3  0.0000     0.8475 0.00 0.0 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2965.03     7  0.3083    -0.0157 0.00 0.0 0.00 0.00 0.34 0.00 0.66 0.00
#&gt; TCGA.AB.2842.03     3  0.5145     0.5502 0.00 0.0 0.54 0.00 0.18 0.02 0.00 0.26
#&gt; TCGA.AB.2869.03     6  0.2569     0.9371 0.00 0.0 0.16 0.00 0.00 0.82 0.00 0.02
#&gt; TCGA.AB.2911.03     1  0.2406     0.7138 0.80 0.0 0.00 0.20 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2918.03     1  0.3374     0.5462 0.68 0.3 0.00 0.00 0.02 0.00 0.00 0.00
#&gt; TCGA.AB.3006.03     3  0.0000     0.8475 0.00 0.0 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2848.03     8  0.4798     0.9094 0.10 0.0 0.02 0.32 0.00 0.00 0.00 0.56
#&gt; TCGA.AB.2969.03     7  0.0000     0.8312 0.00 0.0 0.00 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2839.03     2  0.0000     1.0000 0.00 1.0 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2835.03     4  0.1563     0.6896 0.10 0.0 0.00 0.90 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2974.03     7  0.0000     0.8312 0.00 0.0 0.00 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2986.03     1  0.3374     0.5462 0.68 0.3 0.00 0.00 0.02 0.00 0.00 0.00
#&gt; TCGA.AB.2931.03     7  0.2407     0.7792 0.08 0.0 0.00 0.00 0.00 0.00 0.86 0.06
#&gt; TCGA.AB.2896.03     5  0.3083     1.0000 0.00 0.0 0.00 0.00 0.66 0.00 0.34 0.00
#&gt; TCGA.AB.2812.03     2  0.0000     1.0000 0.00 1.0 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.3011.03     3  0.0000     0.8475 0.00 0.0 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2946.03     2  0.0000     1.0000 0.00 1.0 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2856.03     2  0.0000     1.0000 0.00 1.0 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2879.03     8  0.5037     0.8855 0.14 0.0 0.00 0.30 0.02 0.00 0.00 0.54
#&gt; TCGA.AB.2976.03     4  0.1557     0.7955 0.00 0.0 0.00 0.92 0.02 0.06 0.00 0.00
#&gt; TCGA.AB.2989.03     2  0.0000     1.0000 0.00 1.0 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2981.03     5  0.3083     1.0000 0.00 0.0 0.00 0.00 0.66 0.00 0.34 0.00
#&gt; TCGA.AB.2973.03     8  0.5801     0.8282 0.10 0.0 0.02 0.38 0.00 0.06 0.00 0.44
#&gt; TCGA.AB.2818.03     4  0.0000     0.7901 0.00 0.0 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2930.03     1  0.4057     0.6745 0.72 0.0 0.00 0.20 0.04 0.02 0.00 0.02
#&gt; TCGA.AB.2816.03     6  0.3337     0.9212 0.00 0.0 0.16 0.00 0.02 0.78 0.00 0.04
#&gt; TCGA.AB.2925.03     5  0.3083     1.0000 0.00 0.0 0.00 0.00 0.66 0.00 0.34 0.00
#&gt; TCGA.AB.2825.03     5  0.3083     1.0000 0.00 0.0 0.00 0.00 0.66 0.00 0.34 0.00
#&gt; TCGA.AB.2947.03     7  0.0471     0.8281 0.00 0.0 0.00 0.00 0.00 0.00 0.98 0.02
#&gt; TCGA.AB.2988.03     6  0.2114     0.9379 0.00 0.0 0.16 0.00 0.00 0.84 0.00 0.00
#&gt; TCGA.AB.2985.03     3  0.5145     0.5502 0.00 0.0 0.54 0.00 0.18 0.02 0.00 0.26
#&gt; TCGA.AB.2844.03     2  0.0000     1.0000 0.00 1.0 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2993.03     8  0.4433     0.9050 0.10 0.0 0.00 0.34 0.00 0.00 0.00 0.56
#&gt; TCGA.AB.2924.03     4  0.0000     0.7901 0.00 0.0 0.00 1.00 0.00 0.00 0.00 0.00
</code></pre>

<script>
$('#tab-node-01-get-classes-7-a').parent().next().next().hide();
$('#tab-node-01-get-classes-7-a').click(function(){
  $('#tab-node-01-get-classes-7-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>
</div>

Heatmaps for the consensus matrix. It visualizes the probability of two
samples to be in a same group.




<script>
$( function() {
	$( '#tabs-node-01-consensus-heatmap' ).tabs();
} );
</script>
<div id='tabs-node-01-consensus-heatmap'>
<ul>
<li><a href='#tab-node-01-consensus-heatmap-1'>k = 2</a></li>
<li><a href='#tab-node-01-consensus-heatmap-2'>k = 3</a></li>
<li><a href='#tab-node-01-consensus-heatmap-3'>k = 4</a></li>
<li><a href='#tab-node-01-consensus-heatmap-4'>k = 5</a></li>
<li><a href='#tab-node-01-consensus-heatmap-5'>k = 6</a></li>
<li><a href='#tab-node-01-consensus-heatmap-6'>k = 7</a></li>
<li><a href='#tab-node-01-consensus-heatmap-7'>k = 8</a></li>
</ul>
<div id='tab-node-01-consensus-heatmap-1'>
<pre><code class="r">consensus_heatmap(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-01-consensus-heatmap-1-1.png" alt="plot of chunk tab-node-01-consensus-heatmap-1"/></p>

</div>
<div id='tab-node-01-consensus-heatmap-2'>
<pre><code class="r">consensus_heatmap(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-01-consensus-heatmap-2-1.png" alt="plot of chunk tab-node-01-consensus-heatmap-2"/></p>

</div>
<div id='tab-node-01-consensus-heatmap-3'>
<pre><code class="r">consensus_heatmap(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-01-consensus-heatmap-3-1.png" alt="plot of chunk tab-node-01-consensus-heatmap-3"/></p>

</div>
<div id='tab-node-01-consensus-heatmap-4'>
<pre><code class="r">consensus_heatmap(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-01-consensus-heatmap-4-1.png" alt="plot of chunk tab-node-01-consensus-heatmap-4"/></p>

</div>
<div id='tab-node-01-consensus-heatmap-5'>
<pre><code class="r">consensus_heatmap(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-01-consensus-heatmap-5-1.png" alt="plot of chunk tab-node-01-consensus-heatmap-5"/></p>

</div>
<div id='tab-node-01-consensus-heatmap-6'>
<pre><code class="r">consensus_heatmap(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-01-consensus-heatmap-6-1.png" alt="plot of chunk tab-node-01-consensus-heatmap-6"/></p>

</div>
<div id='tab-node-01-consensus-heatmap-7'>
<pre><code class="r">consensus_heatmap(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-01-consensus-heatmap-7-1.png" alt="plot of chunk tab-node-01-consensus-heatmap-7"/></p>

</div>
</div>

Heatmaps for the membership of samples in all partitions to see how consistent they are:





<script>
$( function() {
	$( '#tabs-node-01-membership-heatmap' ).tabs();
} );
</script>
<div id='tabs-node-01-membership-heatmap'>
<ul>
<li><a href='#tab-node-01-membership-heatmap-1'>k = 2</a></li>
<li><a href='#tab-node-01-membership-heatmap-2'>k = 3</a></li>
<li><a href='#tab-node-01-membership-heatmap-3'>k = 4</a></li>
<li><a href='#tab-node-01-membership-heatmap-4'>k = 5</a></li>
<li><a href='#tab-node-01-membership-heatmap-5'>k = 6</a></li>
<li><a href='#tab-node-01-membership-heatmap-6'>k = 7</a></li>
<li><a href='#tab-node-01-membership-heatmap-7'>k = 8</a></li>
</ul>
<div id='tab-node-01-membership-heatmap-1'>
<pre><code class="r">membership_heatmap(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-01-membership-heatmap-1-1.png" alt="plot of chunk tab-node-01-membership-heatmap-1"/></p>

</div>
<div id='tab-node-01-membership-heatmap-2'>
<pre><code class="r">membership_heatmap(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-01-membership-heatmap-2-1.png" alt="plot of chunk tab-node-01-membership-heatmap-2"/></p>

</div>
<div id='tab-node-01-membership-heatmap-3'>
<pre><code class="r">membership_heatmap(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-01-membership-heatmap-3-1.png" alt="plot of chunk tab-node-01-membership-heatmap-3"/></p>

</div>
<div id='tab-node-01-membership-heatmap-4'>
<pre><code class="r">membership_heatmap(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-01-membership-heatmap-4-1.png" alt="plot of chunk tab-node-01-membership-heatmap-4"/></p>

</div>
<div id='tab-node-01-membership-heatmap-5'>
<pre><code class="r">membership_heatmap(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-01-membership-heatmap-5-1.png" alt="plot of chunk tab-node-01-membership-heatmap-5"/></p>

</div>
<div id='tab-node-01-membership-heatmap-6'>
<pre><code class="r">membership_heatmap(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-01-membership-heatmap-6-1.png" alt="plot of chunk tab-node-01-membership-heatmap-6"/></p>

</div>
<div id='tab-node-01-membership-heatmap-7'>
<pre><code class="r">membership_heatmap(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-01-membership-heatmap-7-1.png" alt="plot of chunk tab-node-01-membership-heatmap-7"/></p>

</div>
</div>

As soon as the classes for columns are determined, the signatures
that are significantly different between subgroups can be looked for. 
Following are the heatmaps for signatures.






<script>
$( function() {
	$( '#tabs-node-01-get-signatures' ).tabs();
} );
</script>
<div id='tabs-node-01-get-signatures'>
<ul>
<li><a href='#tab-node-01-get-signatures-1'>k = 2</a></li>
<li><a href='#tab-node-01-get-signatures-2'>k = 3</a></li>
<li><a href='#tab-node-01-get-signatures-3'>k = 4</a></li>
<li><a href='#tab-node-01-get-signatures-4'>k = 5</a></li>
<li><a href='#tab-node-01-get-signatures-5'>k = 6</a></li>
<li><a href='#tab-node-01-get-signatures-6'>k = 7</a></li>
<li><a href='#tab-node-01-get-signatures-7'>k = 8</a></li>
</ul>
<div id='tab-node-01-get-signatures-1'>
<pre><code class="r">get_signatures(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-01-get-signatures-1-1.png" alt="plot of chunk tab-node-01-get-signatures-1"/></p>

</div>
<div id='tab-node-01-get-signatures-2'>
<pre><code class="r">get_signatures(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-01-get-signatures-2-1.png" alt="plot of chunk tab-node-01-get-signatures-2"/></p>

</div>
<div id='tab-node-01-get-signatures-3'>
<pre><code class="r">get_signatures(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-01-get-signatures-3-1.png" alt="plot of chunk tab-node-01-get-signatures-3"/></p>

</div>
<div id='tab-node-01-get-signatures-4'>
<pre><code class="r">get_signatures(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-01-get-signatures-4-1.png" alt="plot of chunk tab-node-01-get-signatures-4"/></p>

</div>
<div id='tab-node-01-get-signatures-5'>
<pre><code class="r">get_signatures(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-01-get-signatures-5-1.png" alt="plot of chunk tab-node-01-get-signatures-5"/></p>

</div>
<div id='tab-node-01-get-signatures-6'>
<pre><code class="r">get_signatures(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-01-get-signatures-6-1.png" alt="plot of chunk tab-node-01-get-signatures-6"/></p>

</div>
<div id='tab-node-01-get-signatures-7'>
<pre><code class="r">get_signatures(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-01-get-signatures-7-1.png" alt="plot of chunk tab-node-01-get-signatures-7"/></p>

</div>
</div>



Compare the overlap of signatures from different k:

```r
compare_signatures(res)
```

![plot of chunk node-01-signature_compare](figure_cola/node-01-signature_compare-1.png)

`get_signature()` returns a data frame invisibly. To get the list of signatures, the function
call should be assigned to a variable explicitly. In following code, if `plot` argument is set
to `FALSE`, no heatmap is plotted while only the differential analysis is performed.

```r
# code only for demonstration
tb = get_signature(res, k = ..., plot = FALSE)
```

An example of the output of `tb` is:

```
#>   which_row         fdr    mean_1    mean_2 scaled_mean_1 scaled_mean_2 km
#> 1        38 0.042760348  8.373488  9.131774    -0.5533452     0.5164555  1
#> 2        40 0.018707592  7.106213  8.469186    -0.6173731     0.5762149  1
#> 3        55 0.019134737 10.221463 11.207825    -0.6159697     0.5749050  1
#> 4        59 0.006059896  5.921854  7.869574    -0.6899429     0.6439467  1
#> 5        60 0.018055526  8.928898 10.211722    -0.6204761     0.5791110  1
#> 6        98 0.009384629 15.714769 14.887706     0.6635654    -0.6193277  2
...
```

The columns in `tb` are:

1. `which_row`: row indices corresponding to the input matrix.
2. `fdr`: FDR for the differential test. 
3. `mean_x`: The mean value in group x.
4. `scaled_mean_x`: The mean value in group x after rows are scaled.
5. `km`: Row groups if k-means clustering is applied to rows (which is done by automatically selecting number of clusters).

If there are too many signatures, `top_signatures = ...` can be set to only show the 
signatures with the highest FDRs:

```r
# code only for demonstration
# e.g. to show the top 500 most significant rows
tb = get_signature(res, k = ..., top_signatures = 500)
```

If the signatures are defined as these which are uniquely high in current group, `diff_method` argument
can be set to `"uniquely_high_in_one_group"`:

```r
# code only for demonstration
tb = get_signature(res, k = ..., diff_method = "uniquely_high_in_one_group")
```




UMAP plot which shows how samples are separated.


<script>
$( function() {
	$( '#tabs-node-01-dimension-reduction' ).tabs();
} );
</script>
<div id='tabs-node-01-dimension-reduction'>
<ul>
<li><a href='#tab-node-01-dimension-reduction-1'>k = 2</a></li>
<li><a href='#tab-node-01-dimension-reduction-2'>k = 3</a></li>
<li><a href='#tab-node-01-dimension-reduction-3'>k = 4</a></li>
<li><a href='#tab-node-01-dimension-reduction-4'>k = 5</a></li>
<li><a href='#tab-node-01-dimension-reduction-5'>k = 6</a></li>
<li><a href='#tab-node-01-dimension-reduction-6'>k = 7</a></li>
<li><a href='#tab-node-01-dimension-reduction-7'>k = 8</a></li>
</ul>
<div id='tab-node-01-dimension-reduction-1'>
<pre><code class="r">dimension_reduction(res, k = 2, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-01-dimension-reduction-1-1.png" alt="plot of chunk tab-node-01-dimension-reduction-1"/></p>

</div>
<div id='tab-node-01-dimension-reduction-2'>
<pre><code class="r">dimension_reduction(res, k = 3, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-01-dimension-reduction-2-1.png" alt="plot of chunk tab-node-01-dimension-reduction-2"/></p>

</div>
<div id='tab-node-01-dimension-reduction-3'>
<pre><code class="r">dimension_reduction(res, k = 4, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-01-dimension-reduction-3-1.png" alt="plot of chunk tab-node-01-dimension-reduction-3"/></p>

</div>
<div id='tab-node-01-dimension-reduction-4'>
<pre><code class="r">dimension_reduction(res, k = 5, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-01-dimension-reduction-4-1.png" alt="plot of chunk tab-node-01-dimension-reduction-4"/></p>

</div>
<div id='tab-node-01-dimension-reduction-5'>
<pre><code class="r">dimension_reduction(res, k = 6, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-01-dimension-reduction-5-1.png" alt="plot of chunk tab-node-01-dimension-reduction-5"/></p>

</div>
<div id='tab-node-01-dimension-reduction-6'>
<pre><code class="r">dimension_reduction(res, k = 7, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-01-dimension-reduction-6-1.png" alt="plot of chunk tab-node-01-dimension-reduction-6"/></p>

</div>
<div id='tab-node-01-dimension-reduction-7'>
<pre><code class="r">dimension_reduction(res, k = 8, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-01-dimension-reduction-7-1.png" alt="plot of chunk tab-node-01-dimension-reduction-7"/></p>

</div>
</div>



Following heatmap shows how subgroups are split when increasing `k`:

```r
collect_classes(res)
```

![plot of chunk node-01-collect-classes](figure_cola/node-01-collect-classes-1.png)



If matrix rows can be associated to genes, consider to use `functional_enrichment(res,
...)` to perform function enrichment for the signature genes. See [this vignette](https://jokergoo.github.io/cola_vignettes/functional_enrichment.html) for more detailed explanations.


 

---------------------------------------------------




### Node011


Parent node: [Node01](#Node01).
Child nodes: 
                Node0111-leaf
        ,
                Node0112-leaf
        ,
                Node0131-leaf
        ,
                Node0132-leaf
        ,
                Node0141-leaf
        ,
                Node0142-leaf
        ,
                Node0211-leaf
        ,
                Node0212-leaf
        ,
                Node0213-leaf
        ,
                Node0221-leaf
        ,
                [Node0222](#Node0222)
        ,
                Node0231-leaf
        ,
                Node0232-leaf
        ,
                Node0233-leaf
        ,
                Node0321-leaf
        ,
                Node0322-leaf
        ,
                Node0323-leaf
        ,
                Node0324-leaf
        ,
                Node0325-leaf
        ,
                Node0331-leaf
        ,
                Node0332-leaf
        .







The object with results only for a single top-value method and a single partitioning method 
can be extracted as:

```r
res = res_rh["011"]
```

A summary of `res` and all the functions that can be applied to it:

```r
res
```

```
#> A 'ConsensusPartition' object with k = 2, 3, 4, 5, 6, 7, 8.
#>   On a matrix with 30000 rows and 14 columns.
#>   Top rows (1000) are extracted by 'ATC' method.
#>   Subgroups are detected by 'kmeans' method.
#>   Performed in total 350 partitions by row resampling.
#>   Best k for subgroups seems to be 2.
#> 
#> Following methods can be applied to this 'ConsensusPartition' object:
#>  [1] "cola_report"             "collect_classes"         "collect_plots"          
#>  [4] "collect_stats"           "colnames"                "compare_partitions"     
#>  [7] "compare_signatures"      "consensus_heatmap"       "dimension_reduction"    
#> [10] "functional_enrichment"   "get_anno_col"            "get_anno"               
#> [13] "get_classes"             "get_consensus"           "get_matrix"             
#> [16] "get_membership"          "get_param"               "get_signatures"         
#> [19] "get_stats"               "is_best_k"               "is_stable_k"            
#> [22] "membership_heatmap"      "ncol"                    "nrow"                   
#> [25] "plot_ecdf"               "predict_classes"         "rownames"               
#> [28] "select_partition_number" "show"                    "suggest_best_k"         
#> [31] "test_to_known_factors"   "top_rows_heatmap"
```

`collect_plots()` function collects all the plots made from `res` for all `k` (number of subgroups)
into one single page to provide an easy and fast comparison between different `k`.

```r
collect_plots(res)
```

![plot of chunk node-011-collect-plots](figure_cola/node-011-collect-plots-1.png)

The plots are:

- The first row: a plot of the eCDF (empirical cumulative distribution
  function) curves of the consensus matrix for each `k` and the heatmap of
  predicted classes for each `k`.
- The second row: heatmaps of the consensus matrix for each `k`.
- The third row: heatmaps of the membership matrix for each `k`.
- The fouth row: heatmaps of the signatures for each `k`.

All the plots in panels can be made by individual functions and they are
plotted later in this section.

`select_partition_number()` produces several plots showing different
statistics for choosing "optimized" `k`. There are following statistics:

- eCDF curves of the consensus matrix for each `k`;
- 1-PAC. [The PAC score](https://en.wikipedia.org/wiki/Consensus_clustering#Over-interpretation_potential_of_consensus_clustering)
  measures the proportion of the ambiguous subgrouping.
- Mean silhouette score.
- Concordance. The mean probability of fiting the consensus subgroup labels in all
  partitions.
- Area increased. Denote $A_k$ as the area under the eCDF curve for current
  `k`, the area increased is defined as $A_k - A_{k-1}$.
- Rand index. The percent of pairs of samples that are both in a same cluster
  or both are not in a same cluster in the partition of k and k-1.
- Jaccard index. The ratio of pairs of samples are both in a same cluster in
  the partition of k and k-1 and the pairs of samples are both in a same
  cluster in the partition k or k-1.

The detailed explanations of these statistics can be found in [the _cola_
vignette](https://jokergoo.github.io/cola_vignettes/cola.html#toc_13).

Generally speaking, higher 1-PAC score, higher mean silhouette score or higher
concordance corresponds to better partition. Rand index and Jaccard index
measure how similar the current partition is compared to partition with `k-1`.
If they are too similar, we won't accept `k` is better than `k-1`.

```r
select_partition_number(res)
```

![plot of chunk node-011-select-partition-number](figure_cola/node-011-select-partition-number-1.png)

The numeric values for all these statistics can be obtained by `get_stats()`.

```r
get_stats(res)
```

```
#>   k 1-PAC mean_silhouette concordance area_increased  Rand Jaccard
#> 2 2 1.000           1.000       1.000         0.5279 0.473   0.473
#> 3 3 0.736           0.883       0.863         0.2286 0.835   0.651
#> 4 4 0.659           0.772       0.853         0.1104 0.945   0.821
#> 5 5 0.582           0.665       0.840         0.0855 0.956   0.826
#> 6 6 0.714           0.434       0.723         0.0696 0.956   0.789
#> 7 7 0.813           0.406       0.673         0.0389 0.934   0.667
#> 8 8 0.835           0.463       0.843         0.0391 0.923   0.533
```

`suggest_best_k()` suggests the best $k$ based on these statistics. The rules are as follows:

- All $k$ with Jaccard index larger than 0.95 are removed because increasing
  $k$ does not provide enough extra information. If all $k$ are removed, it is
  marked as no subgroup is detected.
- For all $k$ with 1-PAC score larger than 0.9, the maximal $k$ is taken as
  the best $k$, and other $k$ are marked as optional $k$.
- If it does not fit the second rule. The $k$ with the maximal vote of the
  highest 1-PAC score, highest mean silhouette, and highest concordance is
  taken as the best $k$.

```r
suggest_best_k(res)
```

```
#> [1] 2
```


Following is the table of the partitions (You need to click the **show/hide
code output** link to see it). The membership matrix (columns with name `p*`)
is inferred by
[`clue::cl_consensus()`](https://www.rdocumentation.org/link/cl_consensus?package=clue)
function with the `SE` method. Basically the value in the membership matrix
represents the probability to belong to a certain group. The finall subgroup
label for an item is determined with the group with highest probability it
belongs to.

In `get_classes()` function, the entropy is calculated from the membership
matrix and the silhouette score is calculated from the consensus matrix.



<script>
$( function() {
	$( '#tabs-node-011-get-classes' ).tabs();
} );
</script>
<div id='tabs-node-011-get-classes'>
<ul>
<li><a href='#tab-node-011-get-classes-1'>k = 2</a></li>
<li><a href='#tab-node-011-get-classes-2'>k = 3</a></li>
<li><a href='#tab-node-011-get-classes-3'>k = 4</a></li>
<li><a href='#tab-node-011-get-classes-4'>k = 5</a></li>
<li><a href='#tab-node-011-get-classes-5'>k = 6</a></li>
<li><a href='#tab-node-011-get-classes-6'>k = 7</a></li>
<li><a href='#tab-node-011-get-classes-7'>k = 8</a></li>
</ul>

<div id='tab-node-011-get-classes-1'>
<p><a id='tab-node-011-get-classes-1-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 2), get_membership(res, k = 2))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette p1 p2
#&gt; TCGA.AB.2809.03     2       0          1  0  1
#&gt; TCGA.AB.2802.03     1       0          1  1  0
#&gt; TCGA.AB.2853.03     1       0          1  1  0
#&gt; TCGA.AB.2811.03     1       0          1  1  0
#&gt; TCGA.AB.2895.03     2       0          1  0  1
#&gt; TCGA.AB.2965.03     1       0          1  1  0
#&gt; TCGA.AB.2969.03     1       0          1  1  0
#&gt; TCGA.AB.2974.03     2       0          1  0  1
#&gt; TCGA.AB.2931.03     1       0          1  1  0
#&gt; TCGA.AB.2896.03     2       0          1  0  1
#&gt; TCGA.AB.2981.03     2       0          1  0  1
#&gt; TCGA.AB.2925.03     1       0          1  1  0
#&gt; TCGA.AB.2825.03     2       0          1  0  1
#&gt; TCGA.AB.2947.03     1       0          1  1  0
</code></pre>

<script>
$('#tab-node-011-get-classes-1-a').parent().next().next().hide();
$('#tab-node-011-get-classes-1-a').click(function(){
  $('#tab-node-011-get-classes-1-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-011-get-classes-2'>
<p><a id='tab-node-011-get-classes-2-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 3), get_membership(res, k = 3))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3
#&gt; TCGA.AB.2809.03     2   0.000      0.940 0.00 1.00 0.00
#&gt; TCGA.AB.2802.03     1   0.254      0.833 0.92 0.00 0.08
#&gt; TCGA.AB.2853.03     1   0.000      0.866 1.00 0.00 0.00
#&gt; TCGA.AB.2811.03     3   0.628      1.000 0.46 0.00 0.54
#&gt; TCGA.AB.2895.03     2   0.000      0.940 0.00 1.00 0.00
#&gt; TCGA.AB.2965.03     1   0.000      0.866 1.00 0.00 0.00
#&gt; TCGA.AB.2969.03     1   0.369      0.597 0.86 0.00 0.14
#&gt; TCGA.AB.2974.03     2   0.604      0.648 0.00 0.62 0.38
#&gt; TCGA.AB.2931.03     3   0.628      1.000 0.46 0.00 0.54
#&gt; TCGA.AB.2896.03     2   0.000      0.940 0.00 1.00 0.00
#&gt; TCGA.AB.2981.03     2   0.000      0.940 0.00 1.00 0.00
#&gt; TCGA.AB.2925.03     1   0.207      0.852 0.94 0.00 0.06
#&gt; TCGA.AB.2825.03     2   0.000      0.940 0.00 1.00 0.00
#&gt; TCGA.AB.2947.03     3   0.628      1.000 0.46 0.00 0.54
</code></pre>

<script>
$('#tab-node-011-get-classes-2-a').parent().next().next().hide();
$('#tab-node-011-get-classes-2-a').click(function(){
  $('#tab-node-011-get-classes-2-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-011-get-classes-3'>
<p><a id='tab-node-011-get-classes-3-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 4), get_membership(res, k = 4))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4
#&gt; TCGA.AB.2809.03     2   0.000      0.789 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2802.03     1   0.777      0.531 0.40 0.00 0.24 0.36
#&gt; TCGA.AB.2853.03     1   0.413      0.861 0.74 0.00 0.26 0.00
#&gt; TCGA.AB.2811.03     3   0.000      1.000 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2895.03     2   0.398      0.751 0.24 0.76 0.00 0.00
#&gt; TCGA.AB.2965.03     1   0.480      0.861 0.72 0.00 0.26 0.02
#&gt; TCGA.AB.2969.03     1   0.517      0.813 0.66 0.00 0.32 0.02
#&gt; TCGA.AB.2974.03     4   0.471      0.000 0.00 0.36 0.00 0.64
#&gt; TCGA.AB.2931.03     3   0.000      1.000 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2896.03     2   0.000      0.789 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2981.03     2   0.398      0.751 0.24 0.76 0.00 0.00
#&gt; TCGA.AB.2925.03     1   0.398      0.857 0.76 0.00 0.24 0.00
#&gt; TCGA.AB.2825.03     2   0.201      0.806 0.08 0.92 0.00 0.00
#&gt; TCGA.AB.2947.03     3   0.000      1.000 0.00 0.00 1.00 0.00
</code></pre>

<script>
$('#tab-node-011-get-classes-3-a').parent().next().next().hide();
$('#tab-node-011-get-classes-3-a').click(function(){
  $('#tab-node-011-get-classes-3-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-011-get-classes-4'>
<p><a id='tab-node-011-get-classes-4-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 5), get_membership(res, k = 5))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5
#&gt; TCGA.AB.2809.03     2   0.406      0.720 0.36 0.64 0.00 0.00 0.00
#&gt; TCGA.AB.2802.03     5   0.202      0.000 0.00 0.00 0.10 0.00 0.90
#&gt; TCGA.AB.2853.03     1   0.763      0.772 0.46 0.00 0.12 0.12 0.30
#&gt; TCGA.AB.2811.03     3   0.000      1.000 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2895.03     2   0.244      0.621 0.04 0.90 0.00 0.00 0.06
#&gt; TCGA.AB.2965.03     1   0.570      0.748 0.60 0.00 0.12 0.00 0.28
#&gt; TCGA.AB.2969.03     1   0.748      0.586 0.50 0.00 0.20 0.08 0.22
#&gt; TCGA.AB.2974.03     4   0.311      0.000 0.00 0.20 0.00 0.80 0.00
#&gt; TCGA.AB.2931.03     3   0.000      1.000 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2896.03     2   0.406      0.720 0.36 0.64 0.00 0.00 0.00
#&gt; TCGA.AB.2981.03     2   0.104      0.636 0.00 0.96 0.00 0.00 0.04
#&gt; TCGA.AB.2925.03     1   0.763      0.772 0.46 0.00 0.12 0.12 0.30
#&gt; TCGA.AB.2825.03     2   0.327      0.732 0.22 0.78 0.00 0.00 0.00
#&gt; TCGA.AB.2947.03     3   0.000      1.000 0.00 0.00 1.00 0.00 0.00
</code></pre>

<script>
$('#tab-node-011-get-classes-4-a').parent().next().next().hide();
$('#tab-node-011-get-classes-4-a').click(function(){
  $('#tab-node-011-get-classes-4-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-011-get-classes-5'>
<p><a id='tab-node-011-get-classes-5-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 6), get_membership(res, k = 6))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2  p3   p4   p5   p6
#&gt; TCGA.AB.2809.03     2   0.245      0.525 0.00 0.84 0.0 0.00 0.16 0.00
#&gt; TCGA.AB.2802.03     5   0.331      0.000 0.28 0.00 0.0 0.00 0.72 0.00
#&gt; TCGA.AB.2853.03     1   0.000      0.623 1.00 0.00 0.0 0.00 0.00 0.00
#&gt; TCGA.AB.2811.03     3   0.000      1.000 0.00 0.00 1.0 0.00 0.00 0.00
#&gt; TCGA.AB.2895.03     6   0.380      0.000 0.00 0.42 0.0 0.00 0.00 0.58
#&gt; TCGA.AB.2965.03     1   0.412      0.581 0.72 0.00 0.0 0.06 0.00 0.22
#&gt; TCGA.AB.2969.03     1   0.528      0.400 0.48 0.00 0.1 0.00 0.00 0.42
#&gt; TCGA.AB.2974.03     4   0.181      0.000 0.00 0.10 0.0 0.90 0.00 0.00
#&gt; TCGA.AB.2931.03     3   0.000      1.000 0.00 0.00 1.0 0.00 0.00 0.00
#&gt; TCGA.AB.2896.03     2   0.245      0.525 0.00 0.84 0.0 0.00 0.16 0.00
#&gt; TCGA.AB.2981.03     2   0.520     -0.546 0.00 0.58 0.0 0.00 0.12 0.30
#&gt; TCGA.AB.2925.03     1   0.148      0.619 0.94 0.00 0.0 0.04 0.00 0.02
#&gt; TCGA.AB.2825.03     2   0.156      0.344 0.00 0.92 0.0 0.00 0.00 0.08
#&gt; TCGA.AB.2947.03     3   0.000      1.000 0.00 0.00 1.0 0.00 0.00 0.00
</code></pre>

<script>
$('#tab-node-011-get-classes-5-a').parent().next().next().hide();
$('#tab-node-011-get-classes-5-a').click(function(){
  $('#tab-node-011-get-classes-5-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-011-get-classes-6'>
<p><a id='tab-node-011-get-classes-6-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 7), get_membership(res, k = 7))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5   p6   p7
#&gt; TCGA.AB.2809.03     2  0.0000      0.536 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2802.03     5  0.0863      0.000 0.04 0.00 0.00 0.00 0.96 0.00 0.00
#&gt; TCGA.AB.2853.03     1  0.4146      0.617 0.64 0.00 0.00 0.32 0.00 0.02 0.02
#&gt; TCGA.AB.2811.03     3  0.2259      0.856 0.00 0.00 0.84 0.00 0.00 0.00 0.16
#&gt; TCGA.AB.2895.03     2  0.5631     -0.566 0.00 0.36 0.00 0.34 0.00 0.00 0.30
#&gt; TCGA.AB.2965.03     1  0.0000      0.580 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2969.03     1  0.5324      0.368 0.58 0.00 0.02 0.22 0.00 0.00 0.18
#&gt; TCGA.AB.2974.03     6  0.0863      0.000 0.00 0.04 0.00 0.00 0.00 0.96 0.00
#&gt; TCGA.AB.2931.03     3  0.0504      0.923 0.00 0.00 0.98 0.00 0.00 0.02 0.00
#&gt; TCGA.AB.2896.03     2  0.0000      0.536 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2981.03     7  0.3358      0.000 0.00 0.36 0.00 0.00 0.00 0.00 0.64
#&gt; TCGA.AB.2925.03     1  0.3546      0.600 0.54 0.00 0.00 0.46 0.00 0.00 0.00
#&gt; TCGA.AB.2825.03     2  0.3244      0.314 0.00 0.78 0.00 0.00 0.04 0.00 0.18
#&gt; TCGA.AB.2947.03     3  0.0000      0.923 0.00 0.00 1.00 0.00 0.00 0.00 0.00
</code></pre>

<script>
$('#tab-node-011-get-classes-6-a').parent().next().next().hide();
$('#tab-node-011-get-classes-6-a').click(function(){
  $('#tab-node-011-get-classes-6-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-011-get-classes-7'>
<p><a id='tab-node-011-get-classes-7-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 8), get_membership(res, k = 8))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4 p5 p6   p7   p8
#&gt; TCGA.AB.2809.03     2  0.2406      0.769 0.00 0.80 0.00 0.20  0  0 0.00 0.00
#&gt; TCGA.AB.2802.03     5  0.0000      0.000 0.00 0.00 0.00 0.00  1  0 0.00 0.00
#&gt; TCGA.AB.2853.03     1  0.4199      0.753 0.52 0.00 0.00 0.00  0  0 0.06 0.42
#&gt; TCGA.AB.2811.03     3  0.2852      0.734 0.00 0.00 0.72 0.00  0  0 0.28 0.00
#&gt; TCGA.AB.2895.03     4  0.0000      0.000 0.00 0.00 0.00 1.00  0  0 0.00 0.00
#&gt; TCGA.AB.2965.03     8  0.0000      0.212 0.00 0.00 0.00 0.00  0  0 0.00 1.00
#&gt; TCGA.AB.2969.03     8  0.6099      0.418 0.24 0.16 0.00 0.00  0  0 0.14 0.46
#&gt; TCGA.AB.2974.03     6  0.0000      0.000 0.00 0.00 0.00 0.00  0  1 0.00 0.00
#&gt; TCGA.AB.2931.03     3  0.0808      0.860 0.00 0.04 0.96 0.00  0  0 0.00 0.00
#&gt; TCGA.AB.2896.03     2  0.2406      0.769 0.00 0.80 0.00 0.20  0  0 0.00 0.00
#&gt; TCGA.AB.2981.03     7  0.3329      0.000 0.00 0.00 0.00 0.48  0  0 0.52 0.00
#&gt; TCGA.AB.2925.03     1  0.2852      0.762 0.72 0.00 0.00 0.00  0  0 0.00 0.28
#&gt; TCGA.AB.2825.03     2  0.5792      0.344 0.06 0.46 0.00 0.28  0  0 0.20 0.00
#&gt; TCGA.AB.2947.03     3  0.0000      0.860 0.00 0.00 1.00 0.00  0  0 0.00 0.00
</code></pre>

<script>
$('#tab-node-011-get-classes-7-a').parent().next().next().hide();
$('#tab-node-011-get-classes-7-a').click(function(){
  $('#tab-node-011-get-classes-7-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>
</div>

Heatmaps for the consensus matrix. It visualizes the probability of two
samples to be in a same group.




<script>
$( function() {
	$( '#tabs-node-011-consensus-heatmap' ).tabs();
} );
</script>
<div id='tabs-node-011-consensus-heatmap'>
<ul>
<li><a href='#tab-node-011-consensus-heatmap-1'>k = 2</a></li>
<li><a href='#tab-node-011-consensus-heatmap-2'>k = 3</a></li>
<li><a href='#tab-node-011-consensus-heatmap-3'>k = 4</a></li>
<li><a href='#tab-node-011-consensus-heatmap-4'>k = 5</a></li>
<li><a href='#tab-node-011-consensus-heatmap-5'>k = 6</a></li>
<li><a href='#tab-node-011-consensus-heatmap-6'>k = 7</a></li>
<li><a href='#tab-node-011-consensus-heatmap-7'>k = 8</a></li>
</ul>
<div id='tab-node-011-consensus-heatmap-1'>
<pre><code class="r">consensus_heatmap(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-011-consensus-heatmap-1-1.png" alt="plot of chunk tab-node-011-consensus-heatmap-1"/></p>

</div>
<div id='tab-node-011-consensus-heatmap-2'>
<pre><code class="r">consensus_heatmap(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-011-consensus-heatmap-2-1.png" alt="plot of chunk tab-node-011-consensus-heatmap-2"/></p>

</div>
<div id='tab-node-011-consensus-heatmap-3'>
<pre><code class="r">consensus_heatmap(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-011-consensus-heatmap-3-1.png" alt="plot of chunk tab-node-011-consensus-heatmap-3"/></p>

</div>
<div id='tab-node-011-consensus-heatmap-4'>
<pre><code class="r">consensus_heatmap(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-011-consensus-heatmap-4-1.png" alt="plot of chunk tab-node-011-consensus-heatmap-4"/></p>

</div>
<div id='tab-node-011-consensus-heatmap-5'>
<pre><code class="r">consensus_heatmap(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-011-consensus-heatmap-5-1.png" alt="plot of chunk tab-node-011-consensus-heatmap-5"/></p>

</div>
<div id='tab-node-011-consensus-heatmap-6'>
<pre><code class="r">consensus_heatmap(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-011-consensus-heatmap-6-1.png" alt="plot of chunk tab-node-011-consensus-heatmap-6"/></p>

</div>
<div id='tab-node-011-consensus-heatmap-7'>
<pre><code class="r">consensus_heatmap(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-011-consensus-heatmap-7-1.png" alt="plot of chunk tab-node-011-consensus-heatmap-7"/></p>

</div>
</div>

Heatmaps for the membership of samples in all partitions to see how consistent they are:





<script>
$( function() {
	$( '#tabs-node-011-membership-heatmap' ).tabs();
} );
</script>
<div id='tabs-node-011-membership-heatmap'>
<ul>
<li><a href='#tab-node-011-membership-heatmap-1'>k = 2</a></li>
<li><a href='#tab-node-011-membership-heatmap-2'>k = 3</a></li>
<li><a href='#tab-node-011-membership-heatmap-3'>k = 4</a></li>
<li><a href='#tab-node-011-membership-heatmap-4'>k = 5</a></li>
<li><a href='#tab-node-011-membership-heatmap-5'>k = 6</a></li>
<li><a href='#tab-node-011-membership-heatmap-6'>k = 7</a></li>
<li><a href='#tab-node-011-membership-heatmap-7'>k = 8</a></li>
</ul>
<div id='tab-node-011-membership-heatmap-1'>
<pre><code class="r">membership_heatmap(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-011-membership-heatmap-1-1.png" alt="plot of chunk tab-node-011-membership-heatmap-1"/></p>

</div>
<div id='tab-node-011-membership-heatmap-2'>
<pre><code class="r">membership_heatmap(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-011-membership-heatmap-2-1.png" alt="plot of chunk tab-node-011-membership-heatmap-2"/></p>

</div>
<div id='tab-node-011-membership-heatmap-3'>
<pre><code class="r">membership_heatmap(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-011-membership-heatmap-3-1.png" alt="plot of chunk tab-node-011-membership-heatmap-3"/></p>

</div>
<div id='tab-node-011-membership-heatmap-4'>
<pre><code class="r">membership_heatmap(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-011-membership-heatmap-4-1.png" alt="plot of chunk tab-node-011-membership-heatmap-4"/></p>

</div>
<div id='tab-node-011-membership-heatmap-5'>
<pre><code class="r">membership_heatmap(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-011-membership-heatmap-5-1.png" alt="plot of chunk tab-node-011-membership-heatmap-5"/></p>

</div>
<div id='tab-node-011-membership-heatmap-6'>
<pre><code class="r">membership_heatmap(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-011-membership-heatmap-6-1.png" alt="plot of chunk tab-node-011-membership-heatmap-6"/></p>

</div>
<div id='tab-node-011-membership-heatmap-7'>
<pre><code class="r">membership_heatmap(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-011-membership-heatmap-7-1.png" alt="plot of chunk tab-node-011-membership-heatmap-7"/></p>

</div>
</div>

As soon as the classes for columns are determined, the signatures
that are significantly different between subgroups can be looked for. 
Following are the heatmaps for signatures.






<script>
$( function() {
	$( '#tabs-node-011-get-signatures' ).tabs();
} );
</script>
<div id='tabs-node-011-get-signatures'>
<ul>
<li><a href='#tab-node-011-get-signatures-1'>k = 2</a></li>
<li><a href='#tab-node-011-get-signatures-2'>k = 3</a></li>
<li><a href='#tab-node-011-get-signatures-3'>k = 4</a></li>
<li><a href='#tab-node-011-get-signatures-4'>k = 5</a></li>
<li><a href='#tab-node-011-get-signatures-5'>k = 6</a></li>
<li><a href='#tab-node-011-get-signatures-6'>k = 7</a></li>
<li><a href='#tab-node-011-get-signatures-7'>k = 8</a></li>
</ul>
<div id='tab-node-011-get-signatures-1'>
<pre><code class="r">get_signatures(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-011-get-signatures-1-1.png" alt="plot of chunk tab-node-011-get-signatures-1"/></p>

</div>
<div id='tab-node-011-get-signatures-2'>
<pre><code class="r">get_signatures(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-011-get-signatures-2-1.png" alt="plot of chunk tab-node-011-get-signatures-2"/></p>

</div>
<div id='tab-node-011-get-signatures-3'>
<pre><code class="r">get_signatures(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-011-get-signatures-3-1.png" alt="plot of chunk tab-node-011-get-signatures-3"/></p>

</div>
<div id='tab-node-011-get-signatures-4'>
<pre><code class="r">get_signatures(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-011-get-signatures-4-1.png" alt="plot of chunk tab-node-011-get-signatures-4"/></p>

</div>
<div id='tab-node-011-get-signatures-5'>
<pre><code class="r">get_signatures(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-011-get-signatures-5-1.png" alt="plot of chunk tab-node-011-get-signatures-5"/></p>

</div>
<div id='tab-node-011-get-signatures-6'>
<pre><code class="r">get_signatures(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-011-get-signatures-6-1.png" alt="plot of chunk tab-node-011-get-signatures-6"/></p>

</div>
<div id='tab-node-011-get-signatures-7'>
<pre><code class="r">get_signatures(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-011-get-signatures-7-1.png" alt="plot of chunk tab-node-011-get-signatures-7"/></p>

</div>
</div>



Compare the overlap of signatures from different k:

```r
compare_signatures(res)
```

![plot of chunk node-011-signature_compare](figure_cola/node-011-signature_compare-1.png)

`get_signature()` returns a data frame invisibly. To get the list of signatures, the function
call should be assigned to a variable explicitly. In following code, if `plot` argument is set
to `FALSE`, no heatmap is plotted while only the differential analysis is performed.

```r
# code only for demonstration
tb = get_signature(res, k = ..., plot = FALSE)
```

An example of the output of `tb` is:

```
#>   which_row         fdr    mean_1    mean_2 scaled_mean_1 scaled_mean_2 km
#> 1        38 0.042760348  8.373488  9.131774    -0.5533452     0.5164555  1
#> 2        40 0.018707592  7.106213  8.469186    -0.6173731     0.5762149  1
#> 3        55 0.019134737 10.221463 11.207825    -0.6159697     0.5749050  1
#> 4        59 0.006059896  5.921854  7.869574    -0.6899429     0.6439467  1
#> 5        60 0.018055526  8.928898 10.211722    -0.6204761     0.5791110  1
#> 6        98 0.009384629 15.714769 14.887706     0.6635654    -0.6193277  2
...
```

The columns in `tb` are:

1. `which_row`: row indices corresponding to the input matrix.
2. `fdr`: FDR for the differential test. 
3. `mean_x`: The mean value in group x.
4. `scaled_mean_x`: The mean value in group x after rows are scaled.
5. `km`: Row groups if k-means clustering is applied to rows (which is done by automatically selecting number of clusters).

If there are too many signatures, `top_signatures = ...` can be set to only show the 
signatures with the highest FDRs:

```r
# code only for demonstration
# e.g. to show the top 500 most significant rows
tb = get_signature(res, k = ..., top_signatures = 500)
```

If the signatures are defined as these which are uniquely high in current group, `diff_method` argument
can be set to `"uniquely_high_in_one_group"`:

```r
# code only for demonstration
tb = get_signature(res, k = ..., diff_method = "uniquely_high_in_one_group")
```




UMAP plot which shows how samples are separated.


<script>
$( function() {
	$( '#tabs-node-011-dimension-reduction' ).tabs();
} );
</script>
<div id='tabs-node-011-dimension-reduction'>
<ul>
<li><a href='#tab-node-011-dimension-reduction-1'>k = 2</a></li>
<li><a href='#tab-node-011-dimension-reduction-2'>k = 3</a></li>
<li><a href='#tab-node-011-dimension-reduction-3'>k = 4</a></li>
<li><a href='#tab-node-011-dimension-reduction-4'>k = 5</a></li>
<li><a href='#tab-node-011-dimension-reduction-5'>k = 6</a></li>
<li><a href='#tab-node-011-dimension-reduction-6'>k = 7</a></li>
<li><a href='#tab-node-011-dimension-reduction-7'>k = 8</a></li>
</ul>
<div id='tab-node-011-dimension-reduction-1'>
<pre><code class="r">dimension_reduction(res, k = 2, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-011-dimension-reduction-1-1.png" alt="plot of chunk tab-node-011-dimension-reduction-1"/></p>

</div>
<div id='tab-node-011-dimension-reduction-2'>
<pre><code class="r">dimension_reduction(res, k = 3, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-011-dimension-reduction-2-1.png" alt="plot of chunk tab-node-011-dimension-reduction-2"/></p>

</div>
<div id='tab-node-011-dimension-reduction-3'>
<pre><code class="r">dimension_reduction(res, k = 4, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-011-dimension-reduction-3-1.png" alt="plot of chunk tab-node-011-dimension-reduction-3"/></p>

</div>
<div id='tab-node-011-dimension-reduction-4'>
<pre><code class="r">dimension_reduction(res, k = 5, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-011-dimension-reduction-4-1.png" alt="plot of chunk tab-node-011-dimension-reduction-4"/></p>

</div>
<div id='tab-node-011-dimension-reduction-5'>
<pre><code class="r">dimension_reduction(res, k = 6, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-011-dimension-reduction-5-1.png" alt="plot of chunk tab-node-011-dimension-reduction-5"/></p>

</div>
<div id='tab-node-011-dimension-reduction-6'>
<pre><code class="r">dimension_reduction(res, k = 7, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-011-dimension-reduction-6-1.png" alt="plot of chunk tab-node-011-dimension-reduction-6"/></p>

</div>
<div id='tab-node-011-dimension-reduction-7'>
<pre><code class="r">dimension_reduction(res, k = 8, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-011-dimension-reduction-7-1.png" alt="plot of chunk tab-node-011-dimension-reduction-7"/></p>

</div>
</div>



Following heatmap shows how subgroups are split when increasing `k`:

```r
collect_classes(res)
```

![plot of chunk node-011-collect-classes](figure_cola/node-011-collect-classes-1.png)



If matrix rows can be associated to genes, consider to use `functional_enrichment(res,
...)` to perform function enrichment for the signature genes. See [this vignette](https://jokergoo.github.io/cola_vignettes/functional_enrichment.html) for more detailed explanations.


 

---------------------------------------------------




### Node013


Parent node: [Node01](#Node01).
Child nodes: 
                Node0111-leaf
        ,
                Node0112-leaf
        ,
                Node0131-leaf
        ,
                Node0132-leaf
        ,
                Node0141-leaf
        ,
                Node0142-leaf
        ,
                Node0211-leaf
        ,
                Node0212-leaf
        ,
                Node0213-leaf
        ,
                Node0221-leaf
        ,
                [Node0222](#Node0222)
        ,
                Node0231-leaf
        ,
                Node0232-leaf
        ,
                Node0233-leaf
        ,
                Node0321-leaf
        ,
                Node0322-leaf
        ,
                Node0323-leaf
        ,
                Node0324-leaf
        ,
                Node0325-leaf
        ,
                Node0331-leaf
        ,
                Node0332-leaf
        .







The object with results only for a single top-value method and a single partitioning method 
can be extracted as:

```r
res = res_rh["013"]
```

A summary of `res` and all the functions that can be applied to it:

```r
res
```

```
#> A 'ConsensusPartition' object with k = 2, 3, 4, 5, 6, 7, 8.
#>   On a matrix with 30000 rows and 12 columns.
#>   Top rows (1000) are extracted by 'ATC' method.
#>   Subgroups are detected by 'skmeans' method.
#>   Performed in total 350 partitions by row resampling.
#>   Best k for subgroups seems to be 3.
#> 
#> Following methods can be applied to this 'ConsensusPartition' object:
#>  [1] "cola_report"             "collect_classes"         "collect_plots"          
#>  [4] "collect_stats"           "colnames"                "compare_partitions"     
#>  [7] "compare_signatures"      "consensus_heatmap"       "dimension_reduction"    
#> [10] "functional_enrichment"   "get_anno_col"            "get_anno"               
#> [13] "get_classes"             "get_consensus"           "get_matrix"             
#> [16] "get_membership"          "get_param"               "get_signatures"         
#> [19] "get_stats"               "is_best_k"               "is_stable_k"            
#> [22] "membership_heatmap"      "ncol"                    "nrow"                   
#> [25] "plot_ecdf"               "predict_classes"         "rownames"               
#> [28] "select_partition_number" "show"                    "suggest_best_k"         
#> [31] "test_to_known_factors"   "top_rows_heatmap"
```

`collect_plots()` function collects all the plots made from `res` for all `k` (number of subgroups)
into one single page to provide an easy and fast comparison between different `k`.

```r
collect_plots(res)
```

![plot of chunk node-013-collect-plots](figure_cola/node-013-collect-plots-1.png)

The plots are:

- The first row: a plot of the eCDF (empirical cumulative distribution
  function) curves of the consensus matrix for each `k` and the heatmap of
  predicted classes for each `k`.
- The second row: heatmaps of the consensus matrix for each `k`.
- The third row: heatmaps of the membership matrix for each `k`.
- The fouth row: heatmaps of the signatures for each `k`.

All the plots in panels can be made by individual functions and they are
plotted later in this section.

`select_partition_number()` produces several plots showing different
statistics for choosing "optimized" `k`. There are following statistics:

- eCDF curves of the consensus matrix for each `k`;
- 1-PAC. [The PAC score](https://en.wikipedia.org/wiki/Consensus_clustering#Over-interpretation_potential_of_consensus_clustering)
  measures the proportion of the ambiguous subgrouping.
- Mean silhouette score.
- Concordance. The mean probability of fiting the consensus subgroup labels in all
  partitions.
- Area increased. Denote $A_k$ as the area under the eCDF curve for current
  `k`, the area increased is defined as $A_k - A_{k-1}$.
- Rand index. The percent of pairs of samples that are both in a same cluster
  or both are not in a same cluster in the partition of k and k-1.
- Jaccard index. The ratio of pairs of samples are both in a same cluster in
  the partition of k and k-1 and the pairs of samples are both in a same
  cluster in the partition k or k-1.

The detailed explanations of these statistics can be found in [the _cola_
vignette](https://jokergoo.github.io/cola_vignettes/cola.html#toc_13).

Generally speaking, higher 1-PAC score, higher mean silhouette score or higher
concordance corresponds to better partition. Rand index and Jaccard index
measure how similar the current partition is compared to partition with `k-1`.
If they are too similar, we won't accept `k` is better than `k-1`.

```r
select_partition_number(res)
```

![plot of chunk node-013-select-partition-number](figure_cola/node-013-select-partition-number-1.png)

The numeric values for all these statistics can be obtained by `get_stats()`.

```r
get_stats(res)
```

```
#>   k 1-PAC mean_silhouette concordance area_increased  Rand Jaccard
#> 2 2 1.000           1.000       1.000         0.4854 0.515   0.515
#> 3 3 1.000           0.913       0.998         0.2195 0.894   0.794
#> 4 4 1.000           0.807       0.977         0.0918 0.955   0.889
#> 5 5 0.848           0.712       0.935         0.2307 0.818   0.500
#> 6 6 0.909           0.644       0.963         0.0525 0.970   0.833
#> 7 7 0.879           0.609       0.972         0.0571 0.879   0.385
#> 8 8 0.879           0.436       0.947         0.0229 0.985   0.875
```

`suggest_best_k()` suggests the best $k$ based on these statistics. The rules are as follows:

- All $k$ with Jaccard index larger than 0.95 are removed because increasing
  $k$ does not provide enough extra information. If all $k$ are removed, it is
  marked as no subgroup is detected.
- For all $k$ with 1-PAC score larger than 0.9, the maximal $k$ is taken as
  the best $k$, and other $k$ are marked as optional $k$.
- If it does not fit the second rule. The $k$ with the maximal vote of the
  highest 1-PAC score, highest mean silhouette, and highest concordance is
  taken as the best $k$.

```r
suggest_best_k(res)
```

```
#> [1] 3
#> attr(,"optional")
#> [1] 2
```

There is also optional best $k$ = 2 that is worth to check.

Following is the table of the partitions (You need to click the **show/hide
code output** link to see it). The membership matrix (columns with name `p*`)
is inferred by
[`clue::cl_consensus()`](https://www.rdocumentation.org/link/cl_consensus?package=clue)
function with the `SE` method. Basically the value in the membership matrix
represents the probability to belong to a certain group. The finall subgroup
label for an item is determined with the group with highest probability it
belongs to.

In `get_classes()` function, the entropy is calculated from the membership
matrix and the silhouette score is calculated from the consensus matrix.



<script>
$( function() {
	$( '#tabs-node-013-get-classes' ).tabs();
} );
</script>
<div id='tabs-node-013-get-classes'>
<ul>
<li><a href='#tab-node-013-get-classes-1'>k = 2</a></li>
<li><a href='#tab-node-013-get-classes-2'>k = 3</a></li>
<li><a href='#tab-node-013-get-classes-3'>k = 4</a></li>
<li><a href='#tab-node-013-get-classes-4'>k = 5</a></li>
<li><a href='#tab-node-013-get-classes-5'>k = 6</a></li>
<li><a href='#tab-node-013-get-classes-6'>k = 7</a></li>
<li><a href='#tab-node-013-get-classes-7'>k = 8</a></li>
</ul>

<div id='tab-node-013-get-classes-1'>
<p><a id='tab-node-013-get-classes-1-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 2), get_membership(res, k = 2))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette p1 p2
#&gt; TCGA.AB.2884.03     2       0          1  0  1
#&gt; TCGA.AB.2945.03     2       0          1  0  1
#&gt; TCGA.AB.2851.03     2       0          1  0  1
#&gt; TCGA.AB.2824.03     1       0          1  1  0
#&gt; TCGA.AB.2972.03     2       0          1  0  1
#&gt; TCGA.AB.2842.03     1       0          1  1  0
#&gt; TCGA.AB.2869.03     2       0          1  0  1
#&gt; TCGA.AB.3006.03     1       0          1  1  0
#&gt; TCGA.AB.3011.03     1       0          1  1  0
#&gt; TCGA.AB.2816.03     2       0          1  0  1
#&gt; TCGA.AB.2988.03     2       0          1  0  1
#&gt; TCGA.AB.2985.03     2       0          1  0  1
</code></pre>

<script>
$('#tab-node-013-get-classes-1-a').parent().next().next().hide();
$('#tab-node-013-get-classes-1-a').click(function(){
  $('#tab-node-013-get-classes-1-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-013-get-classes-2'>
<p><a id='tab-node-013-get-classes-2-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 3), get_membership(res, k = 3))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1 p2   p3
#&gt; TCGA.AB.2884.03     2  0.0000      1.000 0.00  1 0.00
#&gt; TCGA.AB.2945.03     2  0.0000      1.000 0.00  1 0.00
#&gt; TCGA.AB.2851.03     2  0.0000      1.000 0.00  1 0.00
#&gt; TCGA.AB.2824.03     1  0.0000      0.993 1.00  0 0.00
#&gt; TCGA.AB.2972.03     2  0.0000      1.000 0.00  1 0.00
#&gt; TCGA.AB.2842.03     1  0.0892      0.980 0.98  0 0.02
#&gt; TCGA.AB.2869.03     2  0.0000      1.000 0.00  1 0.00
#&gt; TCGA.AB.3006.03     1  0.0000      0.993 1.00  0 0.00
#&gt; TCGA.AB.3011.03     1  0.0000      0.993 1.00  0 0.00
#&gt; TCGA.AB.2816.03     2  0.0000      1.000 0.00  1 0.00
#&gt; TCGA.AB.2988.03     2  0.0000      1.000 0.00  1 0.00
#&gt; TCGA.AB.2985.03     3  0.0000      0.000 0.00  0 1.00
</code></pre>

<script>
$('#tab-node-013-get-classes-2-a').parent().next().next().hide();
$('#tab-node-013-get-classes-2-a').click(function(){
  $('#tab-node-013-get-classes-2-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-013-get-classes-3'>
<p><a id='tab-node-013-get-classes-3-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 4), get_membership(res, k = 4))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette p1   p2   p3 p4
#&gt; TCGA.AB.2884.03     2   0.000      0.953  0 1.00 0.00  0
#&gt; TCGA.AB.2945.03     2   0.164      0.961  0 0.94 0.06  0
#&gt; TCGA.AB.2851.03     2   0.201      0.954  0 0.92 0.08  0
#&gt; TCGA.AB.2824.03     1   0.000      1.000  1 0.00 0.00  0
#&gt; TCGA.AB.2972.03     2   0.201      0.954  0 0.92 0.08  0
#&gt; TCGA.AB.2842.03     4   0.000      0.000  0 0.00 0.00  1
#&gt; TCGA.AB.2869.03     2   0.164      0.961  0 0.94 0.06  0
#&gt; TCGA.AB.3006.03     1   0.000      1.000  1 0.00 0.00  0
#&gt; TCGA.AB.3011.03     1   0.000      1.000  1 0.00 0.00  0
#&gt; TCGA.AB.2816.03     2   0.000      0.953  0 1.00 0.00  0
#&gt; TCGA.AB.2988.03     2   0.000      0.953  0 1.00 0.00  0
#&gt; TCGA.AB.2985.03     3   0.000      0.000  0 0.00 1.00  0
</code></pre>

<script>
$('#tab-node-013-get-classes-3-a').parent().next().next().hide();
$('#tab-node-013-get-classes-3-a').click(function(){
  $('#tab-node-013-get-classes-3-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-013-get-classes-4'>
<p><a id='tab-node-013-get-classes-4-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 5), get_membership(res, k = 5))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2 p3 p4   p5
#&gt; TCGA.AB.2884.03     5   0.173      0.774 0.00 0.08  0  0 0.92
#&gt; TCGA.AB.2945.03     2   0.173      0.911 0.00 0.92  0  0 0.08
#&gt; TCGA.AB.2851.03     2   0.000      0.941 0.00 1.00  0  0 0.00
#&gt; TCGA.AB.2824.03     1   0.000      0.965 1.00 0.00  0  0 0.00
#&gt; TCGA.AB.2972.03     2   0.000      0.941 0.00 1.00  0  0 0.00
#&gt; TCGA.AB.2842.03     4   0.000      0.000 0.00 0.00  0  1 0.00
#&gt; TCGA.AB.2869.03     2   0.141      0.930 0.00 0.94  0  0 0.06
#&gt; TCGA.AB.3006.03     1   0.173      0.928 0.92 0.00  0  0 0.08
#&gt; TCGA.AB.3011.03     1   0.000      0.965 1.00 0.00  0  0 0.00
#&gt; TCGA.AB.2816.03     5   0.173      0.774 0.00 0.08  0  0 0.92
#&gt; TCGA.AB.2988.03     5   0.418      0.410 0.00 0.40  0  0 0.60
#&gt; TCGA.AB.2985.03     3   0.000      0.000 0.00 0.00  1  0 0.00
</code></pre>

<script>
$('#tab-node-013-get-classes-4-a').parent().next().next().hide();
$('#tab-node-013-get-classes-4-a').click(function(){
  $('#tab-node-013-get-classes-4-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-013-get-classes-5'>
<p><a id='tab-node-013-get-classes-5-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 6), get_membership(res, k = 6))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2 p3 p4  p5   p6
#&gt; TCGA.AB.2884.03     5  0.0000      0.713 0.00 0.00  0  0 1.0 0.00
#&gt; TCGA.AB.2945.03     2  0.0000      0.993 0.00 1.00  0  0 0.0 0.00
#&gt; TCGA.AB.2851.03     2  0.0547      0.979 0.00 0.98  0  0 0.0 0.02
#&gt; TCGA.AB.2824.03     1  0.0000      1.000 1.00 0.00  0  0 0.0 0.00
#&gt; TCGA.AB.2972.03     2  0.0000      0.993 0.00 1.00  0  0 0.0 0.00
#&gt; TCGA.AB.2842.03     4  0.0000      0.000 0.00 0.00  0  1 0.0 0.00
#&gt; TCGA.AB.2869.03     2  0.0000      0.993 0.00 1.00  0  0 0.0 0.00
#&gt; TCGA.AB.3006.03     6  0.0547      0.000 0.02 0.00  0  0 0.0 0.98
#&gt; TCGA.AB.3011.03     1  0.0000      1.000 1.00 0.00  0  0 0.0 0.00
#&gt; TCGA.AB.2816.03     5  0.0000      0.713 0.00 0.00  0  0 1.0 0.00
#&gt; TCGA.AB.2988.03     5  0.3756      0.337 0.00 0.40  0  0 0.6 0.00
#&gt; TCGA.AB.2985.03     3  0.0000      0.000 0.00 0.00  1  0 0.0 0.00
</code></pre>

<script>
$('#tab-node-013-get-classes-5-a').parent().next().next().hide();
$('#tab-node-013-get-classes-5-a').click(function(){
  $('#tab-node-013-get-classes-5-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-013-get-classes-6'>
<p><a id='tab-node-013-get-classes-6-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 7), get_membership(res, k = 7))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2 p3 p4   p5 p6   p7
#&gt; TCGA.AB.2884.03     5  0.0000      1.000 0.00 0.00  0  0 1.00  0 0.00
#&gt; TCGA.AB.2945.03     2  0.0000      0.884 0.00 1.00  0  0 0.00  0 0.00
#&gt; TCGA.AB.2851.03     7  0.0504      0.000 0.00 0.02  0  0 0.00  0 0.98
#&gt; TCGA.AB.2824.03     1  0.0504      0.984 0.98 0.00  0  0 0.00  0 0.02
#&gt; TCGA.AB.2972.03     2  0.2081      0.792 0.00 0.86  0  0 0.00  0 0.14
#&gt; TCGA.AB.2842.03     4  0.0000      0.000 0.00 0.00  0  1 0.00  0 0.00
#&gt; TCGA.AB.2869.03     2  0.0000      0.884 0.00 1.00  0  0 0.00  0 0.00
#&gt; TCGA.AB.3006.03     6  0.0000      0.000 0.00 0.00  0  0 0.00  1 0.00
#&gt; TCGA.AB.3011.03     1  0.0000      0.984 1.00 0.00  0  0 0.00  0 0.00
#&gt; TCGA.AB.2816.03     5  0.0000      1.000 0.00 0.00  0  0 1.00  0 0.00
#&gt; TCGA.AB.2988.03     2  0.2259      0.776 0.00 0.84  0  0 0.16  0 0.00
#&gt; TCGA.AB.2985.03     3  0.0000      0.000 0.00 0.00  1  0 0.00  0 0.00
</code></pre>

<script>
$('#tab-node-013-get-classes-6-a').parent().next().next().hide();
$('#tab-node-013-get-classes-6-a').click(function(){
  $('#tab-node-013-get-classes-6-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-013-get-classes-7'>
<p><a id='tab-node-013-get-classes-7-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 8), get_membership(res, k = 8))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2 p3 p4   p5 p6   p7   p8
#&gt; TCGA.AB.2884.03     5  0.0000      1.000 0.00 0.00  0  0 1.00  0 0.00 0.00
#&gt; TCGA.AB.2945.03     2  0.0471      0.842 0.00 0.98  0  0 0.00  0 0.02 0.00
#&gt; TCGA.AB.2851.03     7  0.0000      0.000 0.00 0.00  0  0 0.00  0 1.00 0.00
#&gt; TCGA.AB.2824.03     1  0.0000      0.000 1.00 0.00  0  0 0.00  0 0.00 0.00
#&gt; TCGA.AB.2972.03     2  0.2224      0.769 0.00 0.86  0  0 0.00  0 0.12 0.02
#&gt; TCGA.AB.2842.03     4  0.0000      0.000 0.00 0.00  0  1 0.00  0 0.00 0.00
#&gt; TCGA.AB.2869.03     2  0.1563      0.842 0.00 0.90  0  0 0.00  0 0.00 0.10
#&gt; TCGA.AB.3006.03     6  0.0000      0.000 0.00 0.00  0  0 0.00  1 0.00 0.00
#&gt; TCGA.AB.3011.03     8  0.2114      0.000 0.16 0.00  0  0 0.00  0 0.00 0.84
#&gt; TCGA.AB.2816.03     5  0.0000      1.000 0.00 0.00  0  0 1.00  0 0.00 0.00
#&gt; TCGA.AB.2988.03     2  0.3227      0.779 0.00 0.78  0  0 0.08  0 0.00 0.14
#&gt; TCGA.AB.2985.03     3  0.0000      0.000 0.00 0.00  1  0 0.00  0 0.00 0.00
</code></pre>

<script>
$('#tab-node-013-get-classes-7-a').parent().next().next().hide();
$('#tab-node-013-get-classes-7-a').click(function(){
  $('#tab-node-013-get-classes-7-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>
</div>

Heatmaps for the consensus matrix. It visualizes the probability of two
samples to be in a same group.




<script>
$( function() {
	$( '#tabs-node-013-consensus-heatmap' ).tabs();
} );
</script>
<div id='tabs-node-013-consensus-heatmap'>
<ul>
<li><a href='#tab-node-013-consensus-heatmap-1'>k = 2</a></li>
<li><a href='#tab-node-013-consensus-heatmap-2'>k = 3</a></li>
<li><a href='#tab-node-013-consensus-heatmap-3'>k = 4</a></li>
<li><a href='#tab-node-013-consensus-heatmap-4'>k = 5</a></li>
<li><a href='#tab-node-013-consensus-heatmap-5'>k = 6</a></li>
<li><a href='#tab-node-013-consensus-heatmap-6'>k = 7</a></li>
<li><a href='#tab-node-013-consensus-heatmap-7'>k = 8</a></li>
</ul>
<div id='tab-node-013-consensus-heatmap-1'>
<pre><code class="r">consensus_heatmap(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-013-consensus-heatmap-1-1.png" alt="plot of chunk tab-node-013-consensus-heatmap-1"/></p>

</div>
<div id='tab-node-013-consensus-heatmap-2'>
<pre><code class="r">consensus_heatmap(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-013-consensus-heatmap-2-1.png" alt="plot of chunk tab-node-013-consensus-heatmap-2"/></p>

</div>
<div id='tab-node-013-consensus-heatmap-3'>
<pre><code class="r">consensus_heatmap(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-013-consensus-heatmap-3-1.png" alt="plot of chunk tab-node-013-consensus-heatmap-3"/></p>

</div>
<div id='tab-node-013-consensus-heatmap-4'>
<pre><code class="r">consensus_heatmap(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-013-consensus-heatmap-4-1.png" alt="plot of chunk tab-node-013-consensus-heatmap-4"/></p>

</div>
<div id='tab-node-013-consensus-heatmap-5'>
<pre><code class="r">consensus_heatmap(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-013-consensus-heatmap-5-1.png" alt="plot of chunk tab-node-013-consensus-heatmap-5"/></p>

</div>
<div id='tab-node-013-consensus-heatmap-6'>
<pre><code class="r">consensus_heatmap(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-013-consensus-heatmap-6-1.png" alt="plot of chunk tab-node-013-consensus-heatmap-6"/></p>

</div>
<div id='tab-node-013-consensus-heatmap-7'>
<pre><code class="r">consensus_heatmap(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-013-consensus-heatmap-7-1.png" alt="plot of chunk tab-node-013-consensus-heatmap-7"/></p>

</div>
</div>

Heatmaps for the membership of samples in all partitions to see how consistent they are:





<script>
$( function() {
	$( '#tabs-node-013-membership-heatmap' ).tabs();
} );
</script>
<div id='tabs-node-013-membership-heatmap'>
<ul>
<li><a href='#tab-node-013-membership-heatmap-1'>k = 2</a></li>
<li><a href='#tab-node-013-membership-heatmap-2'>k = 3</a></li>
<li><a href='#tab-node-013-membership-heatmap-3'>k = 4</a></li>
<li><a href='#tab-node-013-membership-heatmap-4'>k = 5</a></li>
<li><a href='#tab-node-013-membership-heatmap-5'>k = 6</a></li>
<li><a href='#tab-node-013-membership-heatmap-6'>k = 7</a></li>
<li><a href='#tab-node-013-membership-heatmap-7'>k = 8</a></li>
</ul>
<div id='tab-node-013-membership-heatmap-1'>
<pre><code class="r">membership_heatmap(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-013-membership-heatmap-1-1.png" alt="plot of chunk tab-node-013-membership-heatmap-1"/></p>

</div>
<div id='tab-node-013-membership-heatmap-2'>
<pre><code class="r">membership_heatmap(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-013-membership-heatmap-2-1.png" alt="plot of chunk tab-node-013-membership-heatmap-2"/></p>

</div>
<div id='tab-node-013-membership-heatmap-3'>
<pre><code class="r">membership_heatmap(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-013-membership-heatmap-3-1.png" alt="plot of chunk tab-node-013-membership-heatmap-3"/></p>

</div>
<div id='tab-node-013-membership-heatmap-4'>
<pre><code class="r">membership_heatmap(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-013-membership-heatmap-4-1.png" alt="plot of chunk tab-node-013-membership-heatmap-4"/></p>

</div>
<div id='tab-node-013-membership-heatmap-5'>
<pre><code class="r">membership_heatmap(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-013-membership-heatmap-5-1.png" alt="plot of chunk tab-node-013-membership-heatmap-5"/></p>

</div>
<div id='tab-node-013-membership-heatmap-6'>
<pre><code class="r">membership_heatmap(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-013-membership-heatmap-6-1.png" alt="plot of chunk tab-node-013-membership-heatmap-6"/></p>

</div>
<div id='tab-node-013-membership-heatmap-7'>
<pre><code class="r">membership_heatmap(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-013-membership-heatmap-7-1.png" alt="plot of chunk tab-node-013-membership-heatmap-7"/></p>

</div>
</div>

As soon as the classes for columns are determined, the signatures
that are significantly different between subgroups can be looked for. 
Following are the heatmaps for signatures.






<script>
$( function() {
	$( '#tabs-node-013-get-signatures' ).tabs();
} );
</script>
<div id='tabs-node-013-get-signatures'>
<ul>
<li><a href='#tab-node-013-get-signatures-1'>k = 2</a></li>
<li><a href='#tab-node-013-get-signatures-2'>k = 3</a></li>
<li><a href='#tab-node-013-get-signatures-3'>k = 4</a></li>
<li><a href='#tab-node-013-get-signatures-4'>k = 5</a></li>
<li><a href='#tab-node-013-get-signatures-5'>k = 6</a></li>
<li><a href='#tab-node-013-get-signatures-6'>k = 7</a></li>
<li><a href='#tab-node-013-get-signatures-7'>k = 8</a></li>
</ul>
<div id='tab-node-013-get-signatures-1'>
<pre><code class="r">get_signatures(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-013-get-signatures-1-1.png" alt="plot of chunk tab-node-013-get-signatures-1"/></p>

</div>
<div id='tab-node-013-get-signatures-2'>
<pre><code class="r">get_signatures(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-013-get-signatures-2-1.png" alt="plot of chunk tab-node-013-get-signatures-2"/></p>

</div>
<div id='tab-node-013-get-signatures-3'>
<pre><code class="r">get_signatures(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-013-get-signatures-3-1.png" alt="plot of chunk tab-node-013-get-signatures-3"/></p>

</div>
<div id='tab-node-013-get-signatures-4'>
<pre><code class="r">get_signatures(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-013-get-signatures-4-1.png" alt="plot of chunk tab-node-013-get-signatures-4"/></p>

</div>
<div id='tab-node-013-get-signatures-5'>
<pre><code class="r">get_signatures(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-013-get-signatures-5-1.png" alt="plot of chunk tab-node-013-get-signatures-5"/></p>

</div>
<div id='tab-node-013-get-signatures-6'>
<pre><code class="r">get_signatures(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-013-get-signatures-6-1.png" alt="plot of chunk tab-node-013-get-signatures-6"/></p>

</div>
<div id='tab-node-013-get-signatures-7'>
<pre><code class="r">get_signatures(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-013-get-signatures-7-1.png" alt="plot of chunk tab-node-013-get-signatures-7"/></p>

</div>
</div>



Compare the overlap of signatures from different k:

```r
compare_signatures(res)
```

![plot of chunk node-013-signature_compare](figure_cola/node-013-signature_compare-1.png)

`get_signature()` returns a data frame invisibly. To get the list of signatures, the function
call should be assigned to a variable explicitly. In following code, if `plot` argument is set
to `FALSE`, no heatmap is plotted while only the differential analysis is performed.

```r
# code only for demonstration
tb = get_signature(res, k = ..., plot = FALSE)
```

An example of the output of `tb` is:

```
#>   which_row         fdr    mean_1    mean_2 scaled_mean_1 scaled_mean_2 km
#> 1        38 0.042760348  8.373488  9.131774    -0.5533452     0.5164555  1
#> 2        40 0.018707592  7.106213  8.469186    -0.6173731     0.5762149  1
#> 3        55 0.019134737 10.221463 11.207825    -0.6159697     0.5749050  1
#> 4        59 0.006059896  5.921854  7.869574    -0.6899429     0.6439467  1
#> 5        60 0.018055526  8.928898 10.211722    -0.6204761     0.5791110  1
#> 6        98 0.009384629 15.714769 14.887706     0.6635654    -0.6193277  2
...
```

The columns in `tb` are:

1. `which_row`: row indices corresponding to the input matrix.
2. `fdr`: FDR for the differential test. 
3. `mean_x`: The mean value in group x.
4. `scaled_mean_x`: The mean value in group x after rows are scaled.
5. `km`: Row groups if k-means clustering is applied to rows (which is done by automatically selecting number of clusters).

If there are too many signatures, `top_signatures = ...` can be set to only show the 
signatures with the highest FDRs:

```r
# code only for demonstration
# e.g. to show the top 500 most significant rows
tb = get_signature(res, k = ..., top_signatures = 500)
```

If the signatures are defined as these which are uniquely high in current group, `diff_method` argument
can be set to `"uniquely_high_in_one_group"`:

```r
# code only for demonstration
tb = get_signature(res, k = ..., diff_method = "uniquely_high_in_one_group")
```




UMAP plot which shows how samples are separated.


<script>
$( function() {
	$( '#tabs-node-013-dimension-reduction' ).tabs();
} );
</script>
<div id='tabs-node-013-dimension-reduction'>
<ul>
<li><a href='#tab-node-013-dimension-reduction-1'>k = 2</a></li>
<li><a href='#tab-node-013-dimension-reduction-2'>k = 3</a></li>
<li><a href='#tab-node-013-dimension-reduction-3'>k = 4</a></li>
<li><a href='#tab-node-013-dimension-reduction-4'>k = 5</a></li>
<li><a href='#tab-node-013-dimension-reduction-5'>k = 6</a></li>
<li><a href='#tab-node-013-dimension-reduction-6'>k = 7</a></li>
<li><a href='#tab-node-013-dimension-reduction-7'>k = 8</a></li>
</ul>
<div id='tab-node-013-dimension-reduction-1'>
<pre><code class="r">dimension_reduction(res, k = 2, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-013-dimension-reduction-1-1.png" alt="plot of chunk tab-node-013-dimension-reduction-1"/></p>

</div>
<div id='tab-node-013-dimension-reduction-2'>
<pre><code class="r">dimension_reduction(res, k = 3, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-013-dimension-reduction-2-1.png" alt="plot of chunk tab-node-013-dimension-reduction-2"/></p>

</div>
<div id='tab-node-013-dimension-reduction-3'>
<pre><code class="r">dimension_reduction(res, k = 4, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-013-dimension-reduction-3-1.png" alt="plot of chunk tab-node-013-dimension-reduction-3"/></p>

</div>
<div id='tab-node-013-dimension-reduction-4'>
<pre><code class="r">dimension_reduction(res, k = 5, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-013-dimension-reduction-4-1.png" alt="plot of chunk tab-node-013-dimension-reduction-4"/></p>

</div>
<div id='tab-node-013-dimension-reduction-5'>
<pre><code class="r">dimension_reduction(res, k = 6, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-013-dimension-reduction-5-1.png" alt="plot of chunk tab-node-013-dimension-reduction-5"/></p>

</div>
<div id='tab-node-013-dimension-reduction-6'>
<pre><code class="r">dimension_reduction(res, k = 7, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-013-dimension-reduction-6-1.png" alt="plot of chunk tab-node-013-dimension-reduction-6"/></p>

</div>
<div id='tab-node-013-dimension-reduction-7'>
<pre><code class="r">dimension_reduction(res, k = 8, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-013-dimension-reduction-7-1.png" alt="plot of chunk tab-node-013-dimension-reduction-7"/></p>

</div>
</div>



Following heatmap shows how subgroups are split when increasing `k`:

```r
collect_classes(res)
```

![plot of chunk node-013-collect-classes](figure_cola/node-013-collect-classes-1.png)



If matrix rows can be associated to genes, consider to use `functional_enrichment(res,
...)` to perform function enrichment for the signature genes. See [this vignette](https://jokergoo.github.io/cola_vignettes/functional_enrichment.html) for more detailed explanations.


 

---------------------------------------------------




### Node014


Parent node: [Node01](#Node01).
Child nodes: 
                Node0111-leaf
        ,
                Node0112-leaf
        ,
                Node0131-leaf
        ,
                Node0132-leaf
        ,
                Node0141-leaf
        ,
                Node0142-leaf
        ,
                Node0211-leaf
        ,
                Node0212-leaf
        ,
                Node0213-leaf
        ,
                Node0221-leaf
        ,
                [Node0222](#Node0222)
        ,
                Node0231-leaf
        ,
                Node0232-leaf
        ,
                Node0233-leaf
        ,
                Node0321-leaf
        ,
                Node0322-leaf
        ,
                Node0323-leaf
        ,
                Node0324-leaf
        ,
                Node0325-leaf
        ,
                Node0331-leaf
        ,
                Node0332-leaf
        .







The object with results only for a single top-value method and a single partitioning method 
can be extracted as:

```r
res = res_rh["014"]
```

A summary of `res` and all the functions that can be applied to it:

```r
res
```

```
#> A 'ConsensusPartition' object with k = 2, 3, 4, 5, 6, 7, 8.
#>   On a matrix with 30000 rows and 16 columns.
#>   Top rows (1000) are extracted by 'ATC' method.
#>   Subgroups are detected by 'kmeans' method.
#>   Performed in total 350 partitions by row resampling.
#>   Best k for subgroups seems to be 2.
#> 
#> Following methods can be applied to this 'ConsensusPartition' object:
#>  [1] "cola_report"             "collect_classes"         "collect_plots"          
#>  [4] "collect_stats"           "colnames"                "compare_partitions"     
#>  [7] "compare_signatures"      "consensus_heatmap"       "dimension_reduction"    
#> [10] "functional_enrichment"   "get_anno_col"            "get_anno"               
#> [13] "get_classes"             "get_consensus"           "get_matrix"             
#> [16] "get_membership"          "get_param"               "get_signatures"         
#> [19] "get_stats"               "is_best_k"               "is_stable_k"            
#> [22] "membership_heatmap"      "ncol"                    "nrow"                   
#> [25] "plot_ecdf"               "predict_classes"         "rownames"               
#> [28] "select_partition_number" "show"                    "suggest_best_k"         
#> [31] "test_to_known_factors"   "top_rows_heatmap"
```

`collect_plots()` function collects all the plots made from `res` for all `k` (number of subgroups)
into one single page to provide an easy and fast comparison between different `k`.

```r
collect_plots(res)
```

![plot of chunk node-014-collect-plots](figure_cola/node-014-collect-plots-1.png)

The plots are:

- The first row: a plot of the eCDF (empirical cumulative distribution
  function) curves of the consensus matrix for each `k` and the heatmap of
  predicted classes for each `k`.
- The second row: heatmaps of the consensus matrix for each `k`.
- The third row: heatmaps of the membership matrix for each `k`.
- The fouth row: heatmaps of the signatures for each `k`.

All the plots in panels can be made by individual functions and they are
plotted later in this section.

`select_partition_number()` produces several plots showing different
statistics for choosing "optimized" `k`. There are following statistics:

- eCDF curves of the consensus matrix for each `k`;
- 1-PAC. [The PAC score](https://en.wikipedia.org/wiki/Consensus_clustering#Over-interpretation_potential_of_consensus_clustering)
  measures the proportion of the ambiguous subgrouping.
- Mean silhouette score.
- Concordance. The mean probability of fiting the consensus subgroup labels in all
  partitions.
- Area increased. Denote $A_k$ as the area under the eCDF curve for current
  `k`, the area increased is defined as $A_k - A_{k-1}$.
- Rand index. The percent of pairs of samples that are both in a same cluster
  or both are not in a same cluster in the partition of k and k-1.
- Jaccard index. The ratio of pairs of samples are both in a same cluster in
  the partition of k and k-1 and the pairs of samples are both in a same
  cluster in the partition k or k-1.

The detailed explanations of these statistics can be found in [the _cola_
vignette](https://jokergoo.github.io/cola_vignettes/cola.html#toc_13).

Generally speaking, higher 1-PAC score, higher mean silhouette score or higher
concordance corresponds to better partition. Rand index and Jaccard index
measure how similar the current partition is compared to partition with `k-1`.
If they are too similar, we won't accept `k` is better than `k-1`.

```r
select_partition_number(res)
```

![plot of chunk node-014-select-partition-number](figure_cola/node-014-select-partition-number-1.png)

The numeric values for all these statistics can be obtained by `get_stats()`.

```r
get_stats(res)
```

```
#>   k 1-PAC mean_silhouette concordance area_increased  Rand Jaccard
#> 2 2 1.000           1.000       1.000         0.5255 0.475   0.475
#> 3 3 0.800           0.839       0.895         0.1507 0.933   0.860
#> 4 4 0.658           0.584       0.812         0.1446 0.917   0.796
#> 5 5 0.808           0.793       0.855         0.1307 0.825   0.488
#> 6 6 0.783           0.777       0.848         0.0474 0.933   0.667
#> 7 7 0.833           0.717       0.840         0.0476 1.000   1.000
#> 8 8 0.867           0.570       0.784         0.0289 0.950   0.667
```

`suggest_best_k()` suggests the best $k$ based on these statistics. The rules are as follows:

- All $k$ with Jaccard index larger than 0.95 are removed because increasing
  $k$ does not provide enough extra information. If all $k$ are removed, it is
  marked as no subgroup is detected.
- For all $k$ with 1-PAC score larger than 0.9, the maximal $k$ is taken as
  the best $k$, and other $k$ are marked as optional $k$.
- If it does not fit the second rule. The $k$ with the maximal vote of the
  highest 1-PAC score, highest mean silhouette, and highest concordance is
  taken as the best $k$.

```r
suggest_best_k(res)
```

```
#> [1] 2
```


Following is the table of the partitions (You need to click the **show/hide
code output** link to see it). The membership matrix (columns with name `p*`)
is inferred by
[`clue::cl_consensus()`](https://www.rdocumentation.org/link/cl_consensus?package=clue)
function with the `SE` method. Basically the value in the membership matrix
represents the probability to belong to a certain group. The finall subgroup
label for an item is determined with the group with highest probability it
belongs to.

In `get_classes()` function, the entropy is calculated from the membership
matrix and the silhouette score is calculated from the consensus matrix.



<script>
$( function() {
	$( '#tabs-node-014-get-classes' ).tabs();
} );
</script>
<div id='tabs-node-014-get-classes'>
<ul>
<li><a href='#tab-node-014-get-classes-1'>k = 2</a></li>
<li><a href='#tab-node-014-get-classes-2'>k = 3</a></li>
<li><a href='#tab-node-014-get-classes-3'>k = 4</a></li>
<li><a href='#tab-node-014-get-classes-4'>k = 5</a></li>
<li><a href='#tab-node-014-get-classes-5'>k = 6</a></li>
<li><a href='#tab-node-014-get-classes-6'>k = 7</a></li>
<li><a href='#tab-node-014-get-classes-7'>k = 8</a></li>
</ul>

<div id='tab-node-014-get-classes-1'>
<p><a id='tab-node-014-get-classes-1-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 2), get_membership(res, k = 2))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette p1 p2
#&gt; TCGA.AB.2837.03     2       0          1  0  1
#&gt; TCGA.AB.2836.03     1       0          1  1  0
#&gt; TCGA.AB.2963.03     1       0          1  1  0
#&gt; TCGA.AB.2967.03     1       0          1  1  0
#&gt; TCGA.AB.2827.03     1       0          1  1  0
#&gt; TCGA.AB.2932.03     1       0          1  1  0
#&gt; TCGA.AB.2911.03     2       0          1  0  1
#&gt; TCGA.AB.2848.03     1       0          1  1  0
#&gt; TCGA.AB.2835.03     1       0          1  1  0
#&gt; TCGA.AB.2879.03     2       0          1  0  1
#&gt; TCGA.AB.2976.03     1       0          1  1  0
#&gt; TCGA.AB.2973.03     2       0          1  0  1
#&gt; TCGA.AB.2818.03     2       0          1  0  1
#&gt; TCGA.AB.2930.03     2       0          1  0  1
#&gt; TCGA.AB.2993.03     2       0          1  0  1
#&gt; TCGA.AB.2924.03     1       0          1  1  0
</code></pre>

<script>
$('#tab-node-014-get-classes-1-a').parent().next().next().hide();
$('#tab-node-014-get-classes-1-a').click(function(){
  $('#tab-node-014-get-classes-1-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-014-get-classes-2'>
<p><a id='tab-node-014-get-classes-2-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 3), get_membership(res, k = 3))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3
#&gt; TCGA.AB.2837.03     2   0.000      0.772 0.00 1.00 0.00
#&gt; TCGA.AB.2836.03     1   0.628      1.000 0.54 0.00 0.46
#&gt; TCGA.AB.2963.03     1   0.628      1.000 0.54 0.00 0.46
#&gt; TCGA.AB.2967.03     1   0.628      1.000 0.54 0.00 0.46
#&gt; TCGA.AB.2827.03     1   0.628      1.000 0.54 0.00 0.46
#&gt; TCGA.AB.2932.03     1   0.628      1.000 0.54 0.00 0.46
#&gt; TCGA.AB.2911.03     2   0.556      0.805 0.30 0.70 0.00
#&gt; TCGA.AB.2848.03     3   0.000      0.000 0.00 0.00 1.00
#&gt; TCGA.AB.2835.03     1   0.628      1.000 0.54 0.00 0.46
#&gt; TCGA.AB.2879.03     2   0.628      0.748 0.46 0.54 0.00
#&gt; TCGA.AB.2976.03     1   0.628      1.000 0.54 0.00 0.46
#&gt; TCGA.AB.2973.03     2   0.628      0.748 0.46 0.54 0.00
#&gt; TCGA.AB.2818.03     2   0.000      0.772 0.00 1.00 0.00
#&gt; TCGA.AB.2930.03     2   0.556      0.805 0.30 0.70 0.00
#&gt; TCGA.AB.2993.03     2   0.000      0.772 0.00 1.00 0.00
#&gt; TCGA.AB.2924.03     1   0.628      1.000 0.54 0.00 0.46
</code></pre>

<script>
$('#tab-node-014-get-classes-2-a').parent().next().next().hide();
$('#tab-node-014-get-classes-2-a').click(function(){
  $('#tab-node-014-get-classes-2-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-014-get-classes-3'>
<p><a id='tab-node-014-get-classes-3-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 4), get_membership(res, k = 4))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4
#&gt; TCGA.AB.2837.03     4   0.499      1.000 0.00 0.48 0.00 0.52
#&gt; TCGA.AB.2836.03     1   0.000      0.650 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2963.03     1   0.462      0.810 0.66 0.00 0.00 0.34
#&gt; TCGA.AB.2967.03     1   0.462      0.810 0.66 0.00 0.00 0.34
#&gt; TCGA.AB.2827.03     1   0.000      0.650 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2932.03     1   0.462      0.810 0.66 0.00 0.00 0.34
#&gt; TCGA.AB.2911.03     2   0.000      0.485 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2848.03     3   0.340      0.000 0.18 0.00 0.82 0.00
#&gt; TCGA.AB.2835.03     1   0.000      0.650 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2879.03     2   0.610      0.509 0.00 0.68 0.18 0.14
#&gt; TCGA.AB.2976.03     1   0.462      0.810 0.66 0.00 0.00 0.34
#&gt; TCGA.AB.2973.03     2   0.610      0.509 0.00 0.68 0.18 0.14
#&gt; TCGA.AB.2818.03     4   0.499      1.000 0.00 0.48 0.00 0.52
#&gt; TCGA.AB.2930.03     2   0.000      0.485 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2993.03     2   0.462     -0.639 0.00 0.66 0.00 0.34
#&gt; TCGA.AB.2924.03     1   0.462      0.810 0.66 0.00 0.00 0.34
</code></pre>

<script>
$('#tab-node-014-get-classes-3-a').parent().next().next().hide();
$('#tab-node-014-get-classes-3-a').click(function(){
  $('#tab-node-014-get-classes-3-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-014-get-classes-4'>
<p><a id='tab-node-014-get-classes-4-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 5), get_membership(res, k = 5))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2 p3   p4   p5
#&gt; TCGA.AB.2837.03     4   0.000      0.782 0.00 0.00  0 1.00 0.00
#&gt; TCGA.AB.2836.03     5   0.406      1.000 0.36 0.00  0 0.00 0.64
#&gt; TCGA.AB.2963.03     1   0.000      1.000 1.00 0.00  0 0.00 0.00
#&gt; TCGA.AB.2967.03     1   0.000      1.000 1.00 0.00  0 0.00 0.00
#&gt; TCGA.AB.2827.03     5   0.406      1.000 0.36 0.00  0 0.00 0.64
#&gt; TCGA.AB.2932.03     1   0.000      1.000 1.00 0.00  0 0.00 0.00
#&gt; TCGA.AB.2911.03     2   0.556      0.640 0.00 0.56  0 0.08 0.36
#&gt; TCGA.AB.2848.03     3   0.000      0.000 0.00 0.00  1 0.00 0.00
#&gt; TCGA.AB.2835.03     5   0.406      1.000 0.36 0.00  0 0.00 0.64
#&gt; TCGA.AB.2879.03     2   0.000      0.653 0.00 1.00  0 0.00 0.00
#&gt; TCGA.AB.2976.03     1   0.000      1.000 1.00 0.00  0 0.00 0.00
#&gt; TCGA.AB.2973.03     2   0.000      0.653 0.00 1.00  0 0.00 0.00
#&gt; TCGA.AB.2818.03     4   0.000      0.782 0.00 0.00  0 1.00 0.00
#&gt; TCGA.AB.2930.03     2   0.556      0.640 0.00 0.56  0 0.08 0.36
#&gt; TCGA.AB.2993.03     4   0.406      0.532 0.00 0.00  0 0.64 0.36
#&gt; TCGA.AB.2924.03     1   0.000      1.000 1.00 0.00  0 0.00 0.00
</code></pre>

<script>
$('#tab-node-014-get-classes-4-a').parent().next().next().hide();
$('#tab-node-014-get-classes-4-a').click(function(){
  $('#tab-node-014-get-classes-4-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-014-get-classes-5'>
<p><a id='tab-node-014-get-classes-5-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 6), get_membership(res, k = 6))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2 p3   p4   p5   p6
#&gt; TCGA.AB.2837.03     4  0.0937      0.967 0.00 0.04  0 0.96 0.00 0.00
#&gt; TCGA.AB.2836.03     5  0.4690      0.846 0.22 0.00  0 0.04 0.70 0.04
#&gt; TCGA.AB.2963.03     1  0.0000      0.978 1.00 0.00  0 0.00 0.00 0.00
#&gt; TCGA.AB.2967.03     1  0.0000      0.978 1.00 0.00  0 0.00 0.00 0.00
#&gt; TCGA.AB.2827.03     5  0.4121      0.852 0.22 0.00  0 0.00 0.72 0.06
#&gt; TCGA.AB.2932.03     1  0.0000      0.978 1.00 0.00  0 0.00 0.00 0.00
#&gt; TCGA.AB.2911.03     2  0.0000      0.578 0.00 1.00  0 0.00 0.00 0.00
#&gt; TCGA.AB.2848.03     3  0.0000      0.000 0.00 0.00  1 0.00 0.00 0.00
#&gt; TCGA.AB.2835.03     5  0.5292      0.798 0.22 0.00  0 0.00 0.60 0.18
#&gt; TCGA.AB.2879.03     6  0.4482      0.962 0.00 0.36  0 0.00 0.04 0.60
#&gt; TCGA.AB.2976.03     1  0.1556      0.909 0.92 0.00  0 0.00 0.00 0.08
#&gt; TCGA.AB.2973.03     6  0.3647      0.962 0.00 0.36  0 0.00 0.00 0.64
#&gt; TCGA.AB.2818.03     4  0.1865      0.967 0.00 0.04  0 0.92 0.04 0.00
#&gt; TCGA.AB.2930.03     2  0.0937      0.566 0.00 0.96  0 0.00 0.04 0.00
#&gt; TCGA.AB.2993.03     2  0.5195      0.114 0.00 0.54  0 0.36 0.10 0.00
#&gt; TCGA.AB.2924.03     1  0.0000      0.978 1.00 0.00  0 0.00 0.00 0.00
</code></pre>

<script>
$('#tab-node-014-get-classes-5-a').parent().next().next().hide();
$('#tab-node-014-get-classes-5-a').click(function(){
  $('#tab-node-014-get-classes-5-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-014-get-classes-6'>
<p><a id='tab-node-014-get-classes-6-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 7), get_membership(res, k = 7))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5   p6 p7
#&gt; TCGA.AB.2837.03     4  0.4317      0.964 0.00 0.38 0.02 0.58 0.02 0.00  0
#&gt; TCGA.AB.2836.03     5  0.4278      0.595 0.04 0.00 0.46 0.00 0.50 0.00  0
#&gt; TCGA.AB.2963.03     1  0.0000      0.914 1.00 0.00 0.00 0.00 0.00 0.00  0
#&gt; TCGA.AB.2967.03     1  0.0000      0.914 1.00 0.00 0.00 0.00 0.00 0.00  0
#&gt; TCGA.AB.2827.03     5  0.0863      0.574 0.04 0.00 0.00 0.00 0.96 0.00  0
#&gt; TCGA.AB.2932.03     1  0.0000      0.914 1.00 0.00 0.00 0.00 0.00 0.00  0
#&gt; TCGA.AB.2911.03     2  0.4908      0.669 0.00 0.62 0.10 0.00 0.02 0.26  0
#&gt; TCGA.AB.2848.03     7  0.0000      0.000 0.00 0.00 0.00 0.00 0.00 0.00  1
#&gt; TCGA.AB.2835.03     5  0.5564      0.574 0.04 0.00 0.40 0.10 0.46 0.00  0
#&gt; TCGA.AB.2879.03     6  0.0000      0.983 0.00 0.00 0.00 0.00 0.00 1.00  0
#&gt; TCGA.AB.2976.03     1  0.4338      0.578 0.64 0.00 0.08 0.28 0.00 0.00  0
#&gt; TCGA.AB.2973.03     6  0.0504      0.983 0.00 0.00 0.02 0.00 0.00 0.98  0
#&gt; TCGA.AB.2818.03     4  0.3413      0.964 0.00 0.38 0.00 0.62 0.00 0.00  0
#&gt; TCGA.AB.2930.03     2  0.5259      0.640 0.00 0.52 0.22 0.00 0.00 0.26  0
#&gt; TCGA.AB.2993.03     2  0.0000      0.300 0.00 1.00 0.00 0.00 0.00 0.00  0
#&gt; TCGA.AB.2924.03     1  0.0000      0.914 1.00 0.00 0.00 0.00 0.00 0.00  0
</code></pre>

<script>
$('#tab-node-014-get-classes-6-a').parent().next().next().hide();
$('#tab-node-014-get-classes-6-a').click(function(){
  $('#tab-node-014-get-classes-6-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-014-get-classes-7'>
<p><a id='tab-node-014-get-classes-7-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 8), get_membership(res, k = 8))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5   p6 p7   p8
#&gt; TCGA.AB.2837.03     4   0.109      0.967 0.00 0.06 0.00 0.94 0.00 0.00  0 0.00
#&gt; TCGA.AB.2836.03     5   0.672     -0.285 0.02 0.10 0.32 0.04 0.42 0.00  0 0.10
#&gt; TCGA.AB.2963.03     1   0.000      0.966 1.00 0.00 0.00 0.00 0.00 0.00  0 0.00
#&gt; TCGA.AB.2967.03     1   0.000      0.966 1.00 0.00 0.00 0.00 0.00 0.00  0 0.00
#&gt; TCGA.AB.2827.03     3   0.240      0.000 0.02 0.00 0.84 0.00 0.14 0.00  0 0.00
#&gt; TCGA.AB.2932.03     1   0.000      0.966 1.00 0.00 0.00 0.00 0.00 0.00  0 0.00
#&gt; TCGA.AB.2911.03     2   0.195      0.697 0.00 0.86 0.00 0.00 0.00 0.14  0 0.00
#&gt; TCGA.AB.2848.03     7   0.000      0.000 0.00 0.00 0.00 0.00 0.00 0.00  1 0.00
#&gt; TCGA.AB.2835.03     5   0.257     -0.047 0.02 0.00 0.16 0.00 0.82 0.00  0 0.00
#&gt; TCGA.AB.2879.03     6   0.000      0.950 0.00 0.00 0.00 0.00 0.00 1.00  0 0.00
#&gt; TCGA.AB.2976.03     8   0.332      0.000 0.46 0.00 0.00 0.00 0.00 0.00  0 0.54
#&gt; TCGA.AB.2973.03     6   0.109      0.950 0.00 0.00 0.06 0.00 0.00 0.94  0 0.00
#&gt; TCGA.AB.2818.03     4   0.189      0.967 0.00 0.06 0.04 0.90 0.00 0.00  0 0.00
#&gt; TCGA.AB.2930.03     2   0.450      0.640 0.00 0.66 0.00 0.00 0.02 0.14  0 0.18
#&gt; TCGA.AB.2993.03     2   0.505      0.486 0.00 0.62 0.06 0.14 0.00 0.00  0 0.18
#&gt; TCGA.AB.2924.03     1   0.128      0.894 0.94 0.04 0.00 0.02 0.00 0.00  0 0.00
</code></pre>

<script>
$('#tab-node-014-get-classes-7-a').parent().next().next().hide();
$('#tab-node-014-get-classes-7-a').click(function(){
  $('#tab-node-014-get-classes-7-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>
</div>

Heatmaps for the consensus matrix. It visualizes the probability of two
samples to be in a same group.




<script>
$( function() {
	$( '#tabs-node-014-consensus-heatmap' ).tabs();
} );
</script>
<div id='tabs-node-014-consensus-heatmap'>
<ul>
<li><a href='#tab-node-014-consensus-heatmap-1'>k = 2</a></li>
<li><a href='#tab-node-014-consensus-heatmap-2'>k = 3</a></li>
<li><a href='#tab-node-014-consensus-heatmap-3'>k = 4</a></li>
<li><a href='#tab-node-014-consensus-heatmap-4'>k = 5</a></li>
<li><a href='#tab-node-014-consensus-heatmap-5'>k = 6</a></li>
<li><a href='#tab-node-014-consensus-heatmap-6'>k = 7</a></li>
<li><a href='#tab-node-014-consensus-heatmap-7'>k = 8</a></li>
</ul>
<div id='tab-node-014-consensus-heatmap-1'>
<pre><code class="r">consensus_heatmap(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-014-consensus-heatmap-1-1.png" alt="plot of chunk tab-node-014-consensus-heatmap-1"/></p>

</div>
<div id='tab-node-014-consensus-heatmap-2'>
<pre><code class="r">consensus_heatmap(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-014-consensus-heatmap-2-1.png" alt="plot of chunk tab-node-014-consensus-heatmap-2"/></p>

</div>
<div id='tab-node-014-consensus-heatmap-3'>
<pre><code class="r">consensus_heatmap(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-014-consensus-heatmap-3-1.png" alt="plot of chunk tab-node-014-consensus-heatmap-3"/></p>

</div>
<div id='tab-node-014-consensus-heatmap-4'>
<pre><code class="r">consensus_heatmap(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-014-consensus-heatmap-4-1.png" alt="plot of chunk tab-node-014-consensus-heatmap-4"/></p>

</div>
<div id='tab-node-014-consensus-heatmap-5'>
<pre><code class="r">consensus_heatmap(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-014-consensus-heatmap-5-1.png" alt="plot of chunk tab-node-014-consensus-heatmap-5"/></p>

</div>
<div id='tab-node-014-consensus-heatmap-6'>
<pre><code class="r">consensus_heatmap(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-014-consensus-heatmap-6-1.png" alt="plot of chunk tab-node-014-consensus-heatmap-6"/></p>

</div>
<div id='tab-node-014-consensus-heatmap-7'>
<pre><code class="r">consensus_heatmap(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-014-consensus-heatmap-7-1.png" alt="plot of chunk tab-node-014-consensus-heatmap-7"/></p>

</div>
</div>

Heatmaps for the membership of samples in all partitions to see how consistent they are:





<script>
$( function() {
	$( '#tabs-node-014-membership-heatmap' ).tabs();
} );
</script>
<div id='tabs-node-014-membership-heatmap'>
<ul>
<li><a href='#tab-node-014-membership-heatmap-1'>k = 2</a></li>
<li><a href='#tab-node-014-membership-heatmap-2'>k = 3</a></li>
<li><a href='#tab-node-014-membership-heatmap-3'>k = 4</a></li>
<li><a href='#tab-node-014-membership-heatmap-4'>k = 5</a></li>
<li><a href='#tab-node-014-membership-heatmap-5'>k = 6</a></li>
<li><a href='#tab-node-014-membership-heatmap-6'>k = 7</a></li>
<li><a href='#tab-node-014-membership-heatmap-7'>k = 8</a></li>
</ul>
<div id='tab-node-014-membership-heatmap-1'>
<pre><code class="r">membership_heatmap(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-014-membership-heatmap-1-1.png" alt="plot of chunk tab-node-014-membership-heatmap-1"/></p>

</div>
<div id='tab-node-014-membership-heatmap-2'>
<pre><code class="r">membership_heatmap(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-014-membership-heatmap-2-1.png" alt="plot of chunk tab-node-014-membership-heatmap-2"/></p>

</div>
<div id='tab-node-014-membership-heatmap-3'>
<pre><code class="r">membership_heatmap(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-014-membership-heatmap-3-1.png" alt="plot of chunk tab-node-014-membership-heatmap-3"/></p>

</div>
<div id='tab-node-014-membership-heatmap-4'>
<pre><code class="r">membership_heatmap(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-014-membership-heatmap-4-1.png" alt="plot of chunk tab-node-014-membership-heatmap-4"/></p>

</div>
<div id='tab-node-014-membership-heatmap-5'>
<pre><code class="r">membership_heatmap(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-014-membership-heatmap-5-1.png" alt="plot of chunk tab-node-014-membership-heatmap-5"/></p>

</div>
<div id='tab-node-014-membership-heatmap-6'>
<pre><code class="r">membership_heatmap(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-014-membership-heatmap-6-1.png" alt="plot of chunk tab-node-014-membership-heatmap-6"/></p>

</div>
<div id='tab-node-014-membership-heatmap-7'>
<pre><code class="r">membership_heatmap(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-014-membership-heatmap-7-1.png" alt="plot of chunk tab-node-014-membership-heatmap-7"/></p>

</div>
</div>

As soon as the classes for columns are determined, the signatures
that are significantly different between subgroups can be looked for. 
Following are the heatmaps for signatures.






<script>
$( function() {
	$( '#tabs-node-014-get-signatures' ).tabs();
} );
</script>
<div id='tabs-node-014-get-signatures'>
<ul>
<li><a href='#tab-node-014-get-signatures-1'>k = 2</a></li>
<li><a href='#tab-node-014-get-signatures-2'>k = 3</a></li>
<li><a href='#tab-node-014-get-signatures-3'>k = 4</a></li>
<li><a href='#tab-node-014-get-signatures-4'>k = 5</a></li>
<li><a href='#tab-node-014-get-signatures-5'>k = 6</a></li>
<li><a href='#tab-node-014-get-signatures-6'>k = 7</a></li>
<li><a href='#tab-node-014-get-signatures-7'>k = 8</a></li>
</ul>
<div id='tab-node-014-get-signatures-1'>
<pre><code class="r">get_signatures(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-014-get-signatures-1-1.png" alt="plot of chunk tab-node-014-get-signatures-1"/></p>

</div>
<div id='tab-node-014-get-signatures-2'>
<pre><code class="r">get_signatures(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-014-get-signatures-2-1.png" alt="plot of chunk tab-node-014-get-signatures-2"/></p>

</div>
<div id='tab-node-014-get-signatures-3'>
<pre><code class="r">get_signatures(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-014-get-signatures-3-1.png" alt="plot of chunk tab-node-014-get-signatures-3"/></p>

</div>
<div id='tab-node-014-get-signatures-4'>
<pre><code class="r">get_signatures(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-014-get-signatures-4-1.png" alt="plot of chunk tab-node-014-get-signatures-4"/></p>

</div>
<div id='tab-node-014-get-signatures-5'>
<pre><code class="r">get_signatures(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-014-get-signatures-5-1.png" alt="plot of chunk tab-node-014-get-signatures-5"/></p>

</div>
<div id='tab-node-014-get-signatures-6'>
<pre><code class="r">get_signatures(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-014-get-signatures-6-1.png" alt="plot of chunk tab-node-014-get-signatures-6"/></p>

</div>
<div id='tab-node-014-get-signatures-7'>
<pre><code class="r">get_signatures(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-014-get-signatures-7-1.png" alt="plot of chunk tab-node-014-get-signatures-7"/></p>

</div>
</div>



Compare the overlap of signatures from different k:

```r
compare_signatures(res)
```

![plot of chunk node-014-signature_compare](figure_cola/node-014-signature_compare-1.png)

`get_signature()` returns a data frame invisibly. To get the list of signatures, the function
call should be assigned to a variable explicitly. In following code, if `plot` argument is set
to `FALSE`, no heatmap is plotted while only the differential analysis is performed.

```r
# code only for demonstration
tb = get_signature(res, k = ..., plot = FALSE)
```

An example of the output of `tb` is:

```
#>   which_row         fdr    mean_1    mean_2 scaled_mean_1 scaled_mean_2 km
#> 1        38 0.042760348  8.373488  9.131774    -0.5533452     0.5164555  1
#> 2        40 0.018707592  7.106213  8.469186    -0.6173731     0.5762149  1
#> 3        55 0.019134737 10.221463 11.207825    -0.6159697     0.5749050  1
#> 4        59 0.006059896  5.921854  7.869574    -0.6899429     0.6439467  1
#> 5        60 0.018055526  8.928898 10.211722    -0.6204761     0.5791110  1
#> 6        98 0.009384629 15.714769 14.887706     0.6635654    -0.6193277  2
...
```

The columns in `tb` are:

1. `which_row`: row indices corresponding to the input matrix.
2. `fdr`: FDR for the differential test. 
3. `mean_x`: The mean value in group x.
4. `scaled_mean_x`: The mean value in group x after rows are scaled.
5. `km`: Row groups if k-means clustering is applied to rows (which is done by automatically selecting number of clusters).

If there are too many signatures, `top_signatures = ...` can be set to only show the 
signatures with the highest FDRs:

```r
# code only for demonstration
# e.g. to show the top 500 most significant rows
tb = get_signature(res, k = ..., top_signatures = 500)
```

If the signatures are defined as these which are uniquely high in current group, `diff_method` argument
can be set to `"uniquely_high_in_one_group"`:

```r
# code only for demonstration
tb = get_signature(res, k = ..., diff_method = "uniquely_high_in_one_group")
```




UMAP plot which shows how samples are separated.


<script>
$( function() {
	$( '#tabs-node-014-dimension-reduction' ).tabs();
} );
</script>
<div id='tabs-node-014-dimension-reduction'>
<ul>
<li><a href='#tab-node-014-dimension-reduction-1'>k = 2</a></li>
<li><a href='#tab-node-014-dimension-reduction-2'>k = 3</a></li>
<li><a href='#tab-node-014-dimension-reduction-3'>k = 4</a></li>
<li><a href='#tab-node-014-dimension-reduction-4'>k = 5</a></li>
<li><a href='#tab-node-014-dimension-reduction-5'>k = 6</a></li>
<li><a href='#tab-node-014-dimension-reduction-6'>k = 7</a></li>
<li><a href='#tab-node-014-dimension-reduction-7'>k = 8</a></li>
</ul>
<div id='tab-node-014-dimension-reduction-1'>
<pre><code class="r">dimension_reduction(res, k = 2, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-014-dimension-reduction-1-1.png" alt="plot of chunk tab-node-014-dimension-reduction-1"/></p>

</div>
<div id='tab-node-014-dimension-reduction-2'>
<pre><code class="r">dimension_reduction(res, k = 3, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-014-dimension-reduction-2-1.png" alt="plot of chunk tab-node-014-dimension-reduction-2"/></p>

</div>
<div id='tab-node-014-dimension-reduction-3'>
<pre><code class="r">dimension_reduction(res, k = 4, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-014-dimension-reduction-3-1.png" alt="plot of chunk tab-node-014-dimension-reduction-3"/></p>

</div>
<div id='tab-node-014-dimension-reduction-4'>
<pre><code class="r">dimension_reduction(res, k = 5, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-014-dimension-reduction-4-1.png" alt="plot of chunk tab-node-014-dimension-reduction-4"/></p>

</div>
<div id='tab-node-014-dimension-reduction-5'>
<pre><code class="r">dimension_reduction(res, k = 6, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-014-dimension-reduction-5-1.png" alt="plot of chunk tab-node-014-dimension-reduction-5"/></p>

</div>
<div id='tab-node-014-dimension-reduction-6'>
<pre><code class="r">dimension_reduction(res, k = 7, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-014-dimension-reduction-6-1.png" alt="plot of chunk tab-node-014-dimension-reduction-6"/></p>

</div>
<div id='tab-node-014-dimension-reduction-7'>
<pre><code class="r">dimension_reduction(res, k = 8, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-014-dimension-reduction-7-1.png" alt="plot of chunk tab-node-014-dimension-reduction-7"/></p>

</div>
</div>



Following heatmap shows how subgroups are split when increasing `k`:

```r
collect_classes(res)
```

![plot of chunk node-014-collect-classes](figure_cola/node-014-collect-classes-1.png)



If matrix rows can be associated to genes, consider to use `functional_enrichment(res,
...)` to perform function enrichment for the signature genes. See [this vignette](https://jokergoo.github.io/cola_vignettes/functional_enrichment.html) for more detailed explanations.


 

---------------------------------------------------




### Node02


Parent node: [Node0](#Node0).
Child nodes: 
                [Node011](#Node011)
        ,
                Node012-leaf
        ,
                [Node013](#Node013)
        ,
                [Node014](#Node014)
        ,
                [Node021](#Node021)
        ,
                [Node022](#Node022)
        ,
                [Node023](#Node023)
        ,
                Node031-leaf
        ,
                [Node032](#Node032)
        ,
                [Node033](#Node033)
        ,
                Node034-leaf
        .







The object with results only for a single top-value method and a single partitioning method 
can be extracted as:

```r
res = res_rh["02"]
```

A summary of `res` and all the functions that can be applied to it:

```r
res
```

```
#> A 'ConsensusPartition' object with k = 2, 3, 4, 5, 6, 7, 8.
#>   On a matrix with 30000 rows and 93 columns.
#>   Top rows (1000) are extracted by 'SD' method.
#>   Subgroups are detected by 'skmeans' method.
#>   Performed in total 350 partitions by row resampling.
#>   Best k for subgroups seems to be 4.
#> 
#> Following methods can be applied to this 'ConsensusPartition' object:
#>  [1] "cola_report"             "collect_classes"         "collect_plots"          
#>  [4] "collect_stats"           "colnames"                "compare_partitions"     
#>  [7] "compare_signatures"      "consensus_heatmap"       "dimension_reduction"    
#> [10] "functional_enrichment"   "get_anno_col"            "get_anno"               
#> [13] "get_classes"             "get_consensus"           "get_matrix"             
#> [16] "get_membership"          "get_param"               "get_signatures"         
#> [19] "get_stats"               "is_best_k"               "is_stable_k"            
#> [22] "membership_heatmap"      "ncol"                    "nrow"                   
#> [25] "plot_ecdf"               "predict_classes"         "rownames"               
#> [28] "select_partition_number" "show"                    "suggest_best_k"         
#> [31] "test_to_known_factors"   "top_rows_heatmap"
```

`collect_plots()` function collects all the plots made from `res` for all `k` (number of subgroups)
into one single page to provide an easy and fast comparison between different `k`.

```r
collect_plots(res)
```

![plot of chunk node-02-collect-plots](figure_cola/node-02-collect-plots-1.png)

The plots are:

- The first row: a plot of the eCDF (empirical cumulative distribution
  function) curves of the consensus matrix for each `k` and the heatmap of
  predicted classes for each `k`.
- The second row: heatmaps of the consensus matrix for each `k`.
- The third row: heatmaps of the membership matrix for each `k`.
- The fouth row: heatmaps of the signatures for each `k`.

All the plots in panels can be made by individual functions and they are
plotted later in this section.

`select_partition_number()` produces several plots showing different
statistics for choosing "optimized" `k`. There are following statistics:

- eCDF curves of the consensus matrix for each `k`;
- 1-PAC. [The PAC score](https://en.wikipedia.org/wiki/Consensus_clustering#Over-interpretation_potential_of_consensus_clustering)
  measures the proportion of the ambiguous subgrouping.
- Mean silhouette score.
- Concordance. The mean probability of fiting the consensus subgroup labels in all
  partitions.
- Area increased. Denote $A_k$ as the area under the eCDF curve for current
  `k`, the area increased is defined as $A_k - A_{k-1}$.
- Rand index. The percent of pairs of samples that are both in a same cluster
  or both are not in a same cluster in the partition of k and k-1.
- Jaccard index. The ratio of pairs of samples are both in a same cluster in
  the partition of k and k-1 and the pairs of samples are both in a same
  cluster in the partition k or k-1.

The detailed explanations of these statistics can be found in [the _cola_
vignette](https://jokergoo.github.io/cola_vignettes/cola.html#toc_13).

Generally speaking, higher 1-PAC score, higher mean silhouette score or higher
concordance corresponds to better partition. Rand index and Jaccard index
measure how similar the current partition is compared to partition with `k-1`.
If they are too similar, we won't accept `k` is better than `k-1`.

```r
select_partition_number(res)
```

![plot of chunk node-02-select-partition-number](figure_cola/node-02-select-partition-number-1.png)

The numeric values for all these statistics can be obtained by `get_stats()`.

```r
get_stats(res)
```

```
#>   k 1-PAC mean_silhouette concordance area_increased  Rand Jaccard
#> 2 2 1.000           0.964       0.986         0.4739 0.531   0.531
#> 3 3 1.000           0.955       0.983         0.4085 0.696   0.479
#> 4 4 0.998           0.948       0.977         0.0718 0.918   0.766
#> 5 5 0.853           0.792       0.907         0.0717 0.927   0.753
#> 6 6 0.783           0.693       0.833         0.0377 0.948   0.790
#> 7 7 0.744           0.640       0.815         0.0221 0.970   0.863
#> 8 8 0.732           0.596       0.795         0.0147 0.969   0.849
```

`suggest_best_k()` suggests the best $k$ based on these statistics. The rules are as follows:

- All $k$ with Jaccard index larger than 0.95 are removed because increasing
  $k$ does not provide enough extra information. If all $k$ are removed, it is
  marked as no subgroup is detected.
- For all $k$ with 1-PAC score larger than 0.9, the maximal $k$ is taken as
  the best $k$, and other $k$ are marked as optional $k$.
- If it does not fit the second rule. The $k$ with the maximal vote of the
  highest 1-PAC score, highest mean silhouette, and highest concordance is
  taken as the best $k$.

```r
suggest_best_k(res)
```

```
#> [1] 4
#> attr(,"optional")
#> [1] 2 3
```

There is also optional best $k$ = 2 3 that is worth to check.

Following is the table of the partitions (You need to click the **show/hide
code output** link to see it). The membership matrix (columns with name `p*`)
is inferred by
[`clue::cl_consensus()`](https://www.rdocumentation.org/link/cl_consensus?package=clue)
function with the `SE` method. Basically the value in the membership matrix
represents the probability to belong to a certain group. The finall subgroup
label for an item is determined with the group with highest probability it
belongs to.

In `get_classes()` function, the entropy is calculated from the membership
matrix and the silhouette score is calculated from the consensus matrix.



<script>
$( function() {
	$( '#tabs-node-02-get-classes' ).tabs();
} );
</script>
<div id='tabs-node-02-get-classes'>
<ul>
<li><a href='#tab-node-02-get-classes-1'>k = 2</a></li>
<li><a href='#tab-node-02-get-classes-2'>k = 3</a></li>
<li><a href='#tab-node-02-get-classes-3'>k = 4</a></li>
<li><a href='#tab-node-02-get-classes-4'>k = 5</a></li>
<li><a href='#tab-node-02-get-classes-5'>k = 6</a></li>
<li><a href='#tab-node-02-get-classes-6'>k = 7</a></li>
<li><a href='#tab-node-02-get-classes-7'>k = 8</a></li>
</ul>

<div id='tab-node-02-get-classes-1'>
<p><a id='tab-node-02-get-classes-1-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 2), get_membership(res, k = 2))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2
#&gt; TCGA.AB.2995.03     1   0.000     0.9932 1.00 0.00
#&gt; TCGA.AB.2878.03     2   0.000     0.9808 0.00 1.00
#&gt; TCGA.AB.2883.03     1   0.000     0.9932 1.00 0.00
#&gt; TCGA.AB.2984.03     2   0.000     0.9808 0.00 1.00
#&gt; TCGA.AB.2874.03     2   0.000     0.9808 0.00 1.00
#&gt; TCGA.AB.2830.03     1   0.000     0.9932 1.00 0.00
#&gt; TCGA.AB.2941.03     1   0.000     0.9932 1.00 0.00
#&gt; TCGA.AB.2987.03     1   0.000     0.9932 1.00 0.00
#&gt; TCGA.AB.2843.03     2   0.000     0.9808 0.00 1.00
#&gt; TCGA.AB.2807.03     2   0.000     0.9808 0.00 1.00
#&gt; TCGA.AB.2971.03     1   0.000     0.9932 1.00 0.00
#&gt; TCGA.AB.2873.03     1   0.000     0.9932 1.00 0.00
#&gt; TCGA.AB.2847.03     2   0.000     0.9808 0.00 1.00
#&gt; TCGA.AB.2833.03     1   0.000     0.9932 1.00 0.00
#&gt; TCGA.AB.2814.03     2   0.000     0.9808 0.00 1.00
#&gt; TCGA.AB.2898.03     1   0.000     0.9932 1.00 0.00
#&gt; TCGA.AB.2866.03     2   0.000     0.9808 0.00 1.00
#&gt; TCGA.AB.2922.03     2   0.242     0.9440 0.04 0.96
#&gt; TCGA.AB.2968.03     1   0.000     0.9932 1.00 0.00
#&gt; TCGA.AB.2933.03     1   0.000     0.9932 1.00 0.00
#&gt; TCGA.AB.2910.03     1   0.000     0.9932 1.00 0.00
#&gt; TCGA.AB.2934.03     1   0.000     0.9932 1.00 0.00
#&gt; TCGA.AB.2959.03     2   0.000     0.9808 0.00 1.00
#&gt; TCGA.AB.2871.03     2   0.000     0.9808 0.00 1.00
#&gt; TCGA.AB.2907.03     2   0.000     0.9808 0.00 1.00
#&gt; TCGA.AB.2915.03     2   0.000     0.9808 0.00 1.00
#&gt; TCGA.AB.2970.03     2   0.000     0.9808 0.00 1.00
#&gt; TCGA.AB.2949.03     1   0.000     0.9932 1.00 0.00
#&gt; TCGA.AB.2912.03     2   0.000     0.9808 0.00 1.00
#&gt; TCGA.AB.2838.03     2   0.000     0.9808 0.00 1.00
#&gt; TCGA.AB.2891.03     2   0.000     0.9808 0.00 1.00
#&gt; TCGA.AB.2867.03     2   0.000     0.9808 0.00 1.00
#&gt; TCGA.AB.2822.03     2   0.000     0.9808 0.00 1.00
#&gt; TCGA.AB.2832.03     1   0.000     0.9932 1.00 0.00
#&gt; TCGA.AB.2893.03     1   0.000     0.9932 1.00 0.00
#&gt; TCGA.AB.2956.03     1   0.000     0.9932 1.00 0.00
#&gt; TCGA.AB.2903.03     2   0.000     0.9808 0.00 1.00
#&gt; TCGA.AB.2948.03     2   0.402     0.9019 0.08 0.92
#&gt; TCGA.AB.2944.03     2   0.000     0.9808 0.00 1.00
#&gt; TCGA.AB.2904.03     1   0.141     0.9763 0.98 0.02
#&gt; TCGA.AB.3005.03     1   0.000     0.9932 1.00 0.00
#&gt; TCGA.AB.2861.03     1   0.000     0.9932 1.00 0.00
#&gt; TCGA.AB.2917.03     2   0.402     0.9026 0.08 0.92
#&gt; TCGA.AB.2964.03     2   0.000     0.9808 0.00 1.00
#&gt; TCGA.AB.2817.03     2   0.000     0.9808 0.00 1.00
#&gt; TCGA.AB.2857.03     1   0.242     0.9577 0.96 0.04
#&gt; TCGA.AB.2805.03     2   0.000     0.9808 0.00 1.00
#&gt; TCGA.AB.2983.03     2   0.000     0.9808 0.00 1.00
#&gt; TCGA.AB.2990.03     2   0.000     0.9808 0.00 1.00
#&gt; TCGA.AB.2829.03     1   0.000     0.9932 1.00 0.00
#&gt; TCGA.AB.3002.03     2   0.000     0.9808 0.00 1.00
#&gt; TCGA.AB.2877.03     2   0.000     0.9808 0.00 1.00
#&gt; TCGA.AB.2920.03     2   0.000     0.9808 0.00 1.00
#&gt; TCGA.AB.2992.03     2   0.000     0.9808 0.00 1.00
#&gt; TCGA.AB.2919.03     2   0.000     0.9808 0.00 1.00
#&gt; TCGA.AB.2928.03     1   0.000     0.9932 1.00 0.00
#&gt; TCGA.AB.2927.03     1   0.242     0.9579 0.96 0.04
#&gt; TCGA.AB.2885.03     2   0.000     0.9808 0.00 1.00
#&gt; TCGA.AB.2996.03     2   0.981     0.2850 0.42 0.58
#&gt; TCGA.AB.2936.03     2   0.000     0.9808 0.00 1.00
#&gt; TCGA.AB.2966.03     2   0.000     0.9808 0.00 1.00
#&gt; TCGA.AB.2820.03     1   0.529     0.8645 0.88 0.12
#&gt; TCGA.AB.2900.03     2   0.000     0.9808 0.00 1.00
#&gt; TCGA.AB.2899.03     2   0.000     0.9808 0.00 1.00
#&gt; TCGA.AB.2926.03     2   0.000     0.9808 0.00 1.00
#&gt; TCGA.AB.2977.03     2   0.000     0.9808 0.00 1.00
#&gt; TCGA.AB.2849.03     2   0.000     0.9808 0.00 1.00
#&gt; TCGA.AB.2821.03     2   0.000     0.9808 0.00 1.00
#&gt; TCGA.AB.2863.03     2   0.000     0.9808 0.00 1.00
#&gt; TCGA.AB.2882.03     2   0.000     0.9808 0.00 1.00
#&gt; TCGA.AB.2916.03     1   0.000     0.9932 1.00 0.00
#&gt; TCGA.AB.2855.03     2   0.000     0.9808 0.00 1.00
#&gt; TCGA.AB.2978.03     1   0.000     0.9932 1.00 0.00
#&gt; TCGA.AB.2952.03     2   0.000     0.9808 0.00 1.00
#&gt; TCGA.AB.2868.03     2   0.000     0.9808 0.00 1.00
#&gt; TCGA.AB.2908.03     1   0.000     0.9932 1.00 0.00
#&gt; TCGA.AB.2938.03     1   0.000     0.9932 1.00 0.00
#&gt; TCGA.AB.2923.03     2   0.000     0.9808 0.00 1.00
#&gt; TCGA.AB.2890.03     2   0.000     0.9808 0.00 1.00
#&gt; TCGA.AB.2887.03     1   0.000     0.9932 1.00 0.00
#&gt; TCGA.AB.2834.03     2   0.000     0.9808 0.00 1.00
#&gt; TCGA.AB.2943.03     2   0.999     0.0845 0.48 0.52
#&gt; TCGA.AB.2813.03     1   0.000     0.9932 1.00 0.00
#&gt; TCGA.AB.2894.03     1   0.000     0.9932 1.00 0.00
#&gt; TCGA.AB.2935.03     2   0.000     0.9808 0.00 1.00
#&gt; TCGA.AB.2929.03     2   0.000     0.9808 0.00 1.00
#&gt; TCGA.AB.2831.03     1   0.000     0.9932 1.00 0.00
#&gt; TCGA.AB.2826.03     2   0.000     0.9808 0.00 1.00
#&gt; TCGA.AB.2810.03     2   0.000     0.9808 0.00 1.00
#&gt; TCGA.AB.2901.03     2   0.000     0.9808 0.00 1.00
#&gt; TCGA.AB.2975.03     1   0.000     0.9932 1.00 0.00
#&gt; TCGA.AB.2860.03     2   0.000     0.9808 0.00 1.00
#&gt; TCGA.AB.2854.03     2   0.000     0.9808 0.00 1.00
</code></pre>

<script>
$('#tab-node-02-get-classes-1-a').parent().next().next().hide();
$('#tab-node-02-get-classes-1-a').click(function(){
  $('#tab-node-02-get-classes-1-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-02-get-classes-2'>
<p><a id='tab-node-02-get-classes-2-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 3), get_membership(res, k = 3))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3
#&gt; TCGA.AB.2995.03     1  0.0000   0.984885 1.00 0.00 0.00
#&gt; TCGA.AB.2878.03     3  0.0000   0.978196 0.00 0.00 1.00
#&gt; TCGA.AB.2883.03     1  0.0000   0.984885 1.00 0.00 0.00
#&gt; TCGA.AB.2984.03     2  0.0000   0.982109 0.00 1.00 0.00
#&gt; TCGA.AB.2874.03     2  0.0000   0.982109 0.00 1.00 0.00
#&gt; TCGA.AB.2830.03     1  0.0000   0.984885 1.00 0.00 0.00
#&gt; TCGA.AB.2941.03     1  0.0000   0.984885 1.00 0.00 0.00
#&gt; TCGA.AB.2987.03     1  0.0000   0.984885 1.00 0.00 0.00
#&gt; TCGA.AB.2843.03     3  0.0000   0.978196 0.00 0.00 1.00
#&gt; TCGA.AB.2807.03     3  0.5948   0.439261 0.00 0.36 0.64
#&gt; TCGA.AB.2971.03     1  0.0000   0.984885 1.00 0.00 0.00
#&gt; TCGA.AB.2873.03     1  0.0000   0.984885 1.00 0.00 0.00
#&gt; TCGA.AB.2847.03     3  0.0000   0.978196 0.00 0.00 1.00
#&gt; TCGA.AB.2833.03     1  0.0000   0.984885 1.00 0.00 0.00
#&gt; TCGA.AB.2814.03     3  0.0000   0.978196 0.00 0.00 1.00
#&gt; TCGA.AB.2898.03     1  0.0000   0.984885 1.00 0.00 0.00
#&gt; TCGA.AB.2866.03     2  0.0000   0.982109 0.00 1.00 0.00
#&gt; TCGA.AB.2922.03     3  0.0000   0.978196 0.00 0.00 1.00
#&gt; TCGA.AB.2968.03     1  0.5560   0.571272 0.70 0.00 0.30
#&gt; TCGA.AB.2933.03     3  0.0000   0.978196 0.00 0.00 1.00
#&gt; TCGA.AB.2910.03     1  0.0000   0.984885 1.00 0.00 0.00
#&gt; TCGA.AB.2934.03     1  0.0000   0.984885 1.00 0.00 0.00
#&gt; TCGA.AB.2959.03     2  0.0000   0.982109 0.00 1.00 0.00
#&gt; TCGA.AB.2871.03     2  0.0000   0.982109 0.00 1.00 0.00
#&gt; TCGA.AB.2907.03     2  0.0000   0.982109 0.00 1.00 0.00
#&gt; TCGA.AB.2915.03     3  0.0000   0.978196 0.00 0.00 1.00
#&gt; TCGA.AB.2970.03     3  0.0000   0.978196 0.00 0.00 1.00
#&gt; TCGA.AB.2949.03     3  0.0000   0.978196 0.00 0.00 1.00
#&gt; TCGA.AB.2912.03     3  0.0000   0.978196 0.00 0.00 1.00
#&gt; TCGA.AB.2838.03     3  0.0000   0.978196 0.00 0.00 1.00
#&gt; TCGA.AB.2891.03     3  0.0000   0.978196 0.00 0.00 1.00
#&gt; TCGA.AB.2867.03     2  0.0000   0.982109 0.00 1.00 0.00
#&gt; TCGA.AB.2822.03     2  0.0000   0.982109 0.00 1.00 0.00
#&gt; TCGA.AB.2832.03     1  0.0000   0.984885 1.00 0.00 0.00
#&gt; TCGA.AB.2893.03     1  0.0000   0.984885 1.00 0.00 0.00
#&gt; TCGA.AB.2956.03     1  0.0000   0.984885 1.00 0.00 0.00
#&gt; TCGA.AB.2903.03     2  0.0000   0.982109 0.00 1.00 0.00
#&gt; TCGA.AB.2948.03     2  0.0000   0.982109 0.00 1.00 0.00
#&gt; TCGA.AB.2944.03     3  0.0000   0.978196 0.00 0.00 1.00
#&gt; TCGA.AB.2904.03     3  0.0000   0.978196 0.00 0.00 1.00
#&gt; TCGA.AB.3005.03     1  0.0000   0.984885 1.00 0.00 0.00
#&gt; TCGA.AB.2861.03     1  0.0000   0.984885 1.00 0.00 0.00
#&gt; TCGA.AB.2917.03     3  0.0000   0.978196 0.00 0.00 1.00
#&gt; TCGA.AB.2964.03     2  0.0000   0.982109 0.00 1.00 0.00
#&gt; TCGA.AB.2817.03     3  0.0000   0.978196 0.00 0.00 1.00
#&gt; TCGA.AB.2857.03     3  0.0000   0.978196 0.00 0.00 1.00
#&gt; TCGA.AB.2805.03     2  0.0000   0.982109 0.00 1.00 0.00
#&gt; TCGA.AB.2983.03     3  0.0000   0.978196 0.00 0.00 1.00
#&gt; TCGA.AB.2990.03     2  0.0000   0.982109 0.00 1.00 0.00
#&gt; TCGA.AB.2829.03     1  0.2066   0.926939 0.94 0.00 0.06
#&gt; TCGA.AB.3002.03     2  0.0000   0.982109 0.00 1.00 0.00
#&gt; TCGA.AB.2877.03     2  0.0000   0.982109 0.00 1.00 0.00
#&gt; TCGA.AB.2920.03     3  0.0000   0.978196 0.00 0.00 1.00
#&gt; TCGA.AB.2992.03     2  0.0000   0.982109 0.00 1.00 0.00
#&gt; TCGA.AB.2919.03     2  0.0000   0.982109 0.00 1.00 0.00
#&gt; TCGA.AB.2928.03     1  0.0000   0.984885 1.00 0.00 0.00
#&gt; TCGA.AB.2927.03     3  0.0000   0.978196 0.00 0.00 1.00
#&gt; TCGA.AB.2885.03     3  0.0000   0.978196 0.00 0.00 1.00
#&gt; TCGA.AB.2996.03     2  0.7995   0.000107 0.06 0.48 0.46
#&gt; TCGA.AB.2936.03     2  0.0000   0.982109 0.00 1.00 0.00
#&gt; TCGA.AB.2966.03     3  0.0000   0.978196 0.00 0.00 1.00
#&gt; TCGA.AB.2820.03     3  0.0000   0.978196 0.00 0.00 1.00
#&gt; TCGA.AB.2900.03     2  0.0000   0.982109 0.00 1.00 0.00
#&gt; TCGA.AB.2899.03     3  0.0000   0.978196 0.00 0.00 1.00
#&gt; TCGA.AB.2926.03     2  0.0000   0.982109 0.00 1.00 0.00
#&gt; TCGA.AB.2977.03     2  0.0000   0.982109 0.00 1.00 0.00
#&gt; TCGA.AB.2849.03     3  0.0892   0.959916 0.00 0.02 0.98
#&gt; TCGA.AB.2821.03     2  0.0000   0.982109 0.00 1.00 0.00
#&gt; TCGA.AB.2863.03     2  0.0000   0.982109 0.00 1.00 0.00
#&gt; TCGA.AB.2882.03     3  0.5706   0.531200 0.00 0.32 0.68
#&gt; TCGA.AB.2916.03     1  0.0000   0.984885 1.00 0.00 0.00
#&gt; TCGA.AB.2855.03     2  0.0000   0.982109 0.00 1.00 0.00
#&gt; TCGA.AB.2978.03     1  0.0000   0.984885 1.00 0.00 0.00
#&gt; TCGA.AB.2952.03     3  0.0000   0.978196 0.00 0.00 1.00
#&gt; TCGA.AB.2868.03     3  0.0000   0.978196 0.00 0.00 1.00
#&gt; TCGA.AB.2908.03     3  0.0892   0.959439 0.02 0.00 0.98
#&gt; TCGA.AB.2938.03     1  0.0000   0.984885 1.00 0.00 0.00
#&gt; TCGA.AB.2923.03     2  0.0000   0.982109 0.00 1.00 0.00
#&gt; TCGA.AB.2890.03     3  0.0000   0.978196 0.00 0.00 1.00
#&gt; TCGA.AB.2887.03     1  0.0000   0.984885 1.00 0.00 0.00
#&gt; TCGA.AB.2834.03     2  0.0000   0.982109 0.00 1.00 0.00
#&gt; TCGA.AB.2943.03     3  0.0000   0.978196 0.00 0.00 1.00
#&gt; TCGA.AB.2813.03     3  0.0000   0.978196 0.00 0.00 1.00
#&gt; TCGA.AB.2894.03     1  0.0000   0.984885 1.00 0.00 0.00
#&gt; TCGA.AB.2935.03     3  0.0000   0.978196 0.00 0.00 1.00
#&gt; TCGA.AB.2929.03     3  0.0000   0.978196 0.00 0.00 1.00
#&gt; TCGA.AB.2831.03     1  0.0000   0.984885 1.00 0.00 0.00
#&gt; TCGA.AB.2826.03     2  0.0000   0.982109 0.00 1.00 0.00
#&gt; TCGA.AB.2810.03     2  0.0000   0.982109 0.00 1.00 0.00
#&gt; TCGA.AB.2901.03     2  0.0000   0.982109 0.00 1.00 0.00
#&gt; TCGA.AB.2975.03     1  0.0000   0.984885 1.00 0.00 0.00
#&gt; TCGA.AB.2860.03     3  0.0000   0.978196 0.00 0.00 1.00
#&gt; TCGA.AB.2854.03     2  0.0000   0.982109 0.00 1.00 0.00
</code></pre>

<script>
$('#tab-node-02-get-classes-2-a').parent().next().next().hide();
$('#tab-node-02-get-classes-2-a').click(function(){
  $('#tab-node-02-get-classes-2-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-02-get-classes-3'>
<p><a id='tab-node-02-get-classes-3-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 4), get_membership(res, k = 4))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4
#&gt; TCGA.AB.2995.03     1  0.0000      0.958 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2878.03     3  0.0000      0.957 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2883.03     4  0.0000      0.979 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2984.03     2  0.0000      1.000 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2874.03     2  0.0000      1.000 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2830.03     1  0.0000      0.958 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2941.03     1  0.0000      0.958 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2987.03     4  0.2011      0.930 0.08 0.00 0.00 0.92
#&gt; TCGA.AB.2843.03     3  0.0000      0.957 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2807.03     3  0.4277      0.616 0.00 0.28 0.72 0.00
#&gt; TCGA.AB.2971.03     1  0.0000      0.958 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2873.03     1  0.0000      0.958 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2847.03     3  0.0000      0.957 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2833.03     4  0.0707      0.971 0.02 0.00 0.00 0.98
#&gt; TCGA.AB.2814.03     3  0.0000      0.957 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2898.03     1  0.0000      0.958 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2866.03     2  0.0000      1.000 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2922.03     3  0.0707      0.948 0.00 0.00 0.98 0.02
#&gt; TCGA.AB.2968.03     3  0.7095      0.381 0.26 0.00 0.56 0.18
#&gt; TCGA.AB.2933.03     3  0.0707      0.948 0.00 0.00 0.98 0.02
#&gt; TCGA.AB.2910.03     4  0.0707      0.982 0.02 0.00 0.00 0.98
#&gt; TCGA.AB.2934.03     1  0.0000      0.958 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2959.03     2  0.0000      1.000 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2871.03     2  0.0000      1.000 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2907.03     2  0.0000      1.000 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2915.03     3  0.0000      0.957 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2970.03     3  0.0000      0.957 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2949.03     3  0.1411      0.936 0.02 0.00 0.96 0.02
#&gt; TCGA.AB.2912.03     3  0.0707      0.948 0.00 0.00 0.98 0.02
#&gt; TCGA.AB.2838.03     3  0.0000      0.957 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2891.03     3  0.0000      0.957 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2867.03     2  0.0000      1.000 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2822.03     2  0.0000      1.000 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2832.03     4  0.0707      0.982 0.02 0.00 0.00 0.98
#&gt; TCGA.AB.2893.03     4  0.0707      0.982 0.02 0.00 0.00 0.98
#&gt; TCGA.AB.2956.03     4  0.0000      0.979 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2903.03     2  0.0000      1.000 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2948.03     1  0.4790      0.391 0.62 0.38 0.00 0.00
#&gt; TCGA.AB.2944.03     3  0.0000      0.957 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2904.03     3  0.2011      0.888 0.08 0.00 0.92 0.00
#&gt; TCGA.AB.3005.03     4  0.0707      0.982 0.02 0.00 0.00 0.98
#&gt; TCGA.AB.2861.03     4  0.0000      0.979 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2917.03     3  0.0707      0.948 0.00 0.00 0.98 0.02
#&gt; TCGA.AB.2964.03     2  0.0000      1.000 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2817.03     3  0.0000      0.957 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2857.03     3  0.0707      0.944 0.02 0.00 0.98 0.00
#&gt; TCGA.AB.2805.03     2  0.0000      1.000 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2983.03     3  0.0000      0.957 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2990.03     2  0.0000      1.000 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2829.03     1  0.0000      0.958 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.3002.03     2  0.0000      1.000 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2877.03     2  0.0000      1.000 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2920.03     3  0.0000      0.957 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2992.03     2  0.0000      1.000 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2919.03     2  0.0000      1.000 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2928.03     1  0.0000      0.958 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2927.03     3  0.0707      0.948 0.00 0.00 0.98 0.02
#&gt; TCGA.AB.2885.03     3  0.0000      0.957 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2996.03     1  0.0707      0.937 0.98 0.02 0.00 0.00
#&gt; TCGA.AB.2936.03     2  0.0000      1.000 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2966.03     3  0.0000      0.957 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2820.03     3  0.0000      0.957 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2900.03     2  0.0000      1.000 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2899.03     3  0.0000      0.957 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2926.03     2  0.0000      1.000 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2977.03     2  0.0000      1.000 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2849.03     3  0.1211      0.923 0.00 0.04 0.96 0.00
#&gt; TCGA.AB.2821.03     2  0.0000      1.000 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2863.03     2  0.0000      1.000 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2882.03     3  0.4713      0.455 0.00 0.36 0.64 0.00
#&gt; TCGA.AB.2916.03     4  0.0000      0.979 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2855.03     2  0.0000      1.000 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2978.03     1  0.0000      0.958 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2952.03     3  0.0000      0.957 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2868.03     3  0.0000      0.957 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2908.03     1  0.2345      0.837 0.90 0.00 0.10 0.00
#&gt; TCGA.AB.2938.03     1  0.0000      0.958 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2923.03     2  0.0000      1.000 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2890.03     3  0.0000      0.957 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2887.03     1  0.0000      0.958 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2834.03     2  0.0000      1.000 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2943.03     3  0.0000      0.957 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2813.03     3  0.1411      0.936 0.02 0.00 0.96 0.02
#&gt; TCGA.AB.2894.03     4  0.0707      0.982 0.02 0.00 0.00 0.98
#&gt; TCGA.AB.2935.03     3  0.0000      0.957 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2929.03     3  0.0000      0.957 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2831.03     1  0.0000      0.958 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2826.03     2  0.0000      1.000 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2810.03     2  0.0000      1.000 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2901.03     2  0.0000      1.000 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2975.03     1  0.0000      0.958 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2860.03     3  0.0000      0.957 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2854.03     2  0.0000      1.000 0.00 1.00 0.00 0.00
</code></pre>

<script>
$('#tab-node-02-get-classes-3-a').parent().next().next().hide();
$('#tab-node-02-get-classes-3-a').click(function(){
  $('#tab-node-02-get-classes-3-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-02-get-classes-4'>
<p><a id='tab-node-02-get-classes-4-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 5), get_membership(res, k = 5))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5
#&gt; TCGA.AB.2995.03     1  0.0609      0.861 0.98 0.00 0.00 0.00 0.02
#&gt; TCGA.AB.2878.03     3  0.0000      0.844 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2883.03     4  0.0000      0.929 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2984.03     2  0.0000      0.976 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2874.03     2  0.0000      0.976 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2830.03     1  0.0000      0.864 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2941.03     1  0.1410      0.852 0.94 0.00 0.00 0.00 0.06
#&gt; TCGA.AB.2987.03     4  0.5095      0.331 0.40 0.00 0.00 0.56 0.04
#&gt; TCGA.AB.2843.03     3  0.4126      0.333 0.00 0.00 0.62 0.00 0.38
#&gt; TCGA.AB.2807.03     2  0.4921      0.395 0.00 0.62 0.34 0.00 0.04
#&gt; TCGA.AB.2971.03     1  0.0000      0.864 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2873.03     1  0.0000      0.864 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2847.03     3  0.0609      0.835 0.00 0.00 0.98 0.00 0.02
#&gt; TCGA.AB.2833.03     5  0.3274      0.541 0.00 0.00 0.00 0.22 0.78
#&gt; TCGA.AB.2814.03     3  0.0000      0.844 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2898.03     1  0.0000      0.864 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2866.03     2  0.0000      0.976 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2922.03     5  0.3983      0.494 0.00 0.00 0.34 0.00 0.66
#&gt; TCGA.AB.2968.03     5  0.1820      0.711 0.02 0.00 0.02 0.02 0.94
#&gt; TCGA.AB.2933.03     5  0.2516      0.747 0.00 0.00 0.14 0.00 0.86
#&gt; TCGA.AB.2910.03     4  0.0609      0.929 0.00 0.00 0.00 0.98 0.02
#&gt; TCGA.AB.2934.03     1  0.0000      0.864 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2959.03     2  0.0000      0.976 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2871.03     2  0.0000      0.976 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2907.03     2  0.0000      0.976 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2915.03     3  0.1410      0.811 0.00 0.00 0.94 0.00 0.06
#&gt; TCGA.AB.2970.03     3  0.0000      0.844 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2949.03     5  0.1410      0.742 0.00 0.00 0.06 0.00 0.94
#&gt; TCGA.AB.2912.03     3  0.4262      0.153 0.00 0.00 0.56 0.00 0.44
#&gt; TCGA.AB.2838.03     3  0.0000      0.844 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2891.03     3  0.1410      0.817 0.00 0.00 0.94 0.00 0.06
#&gt; TCGA.AB.2867.03     2  0.0000      0.976 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2822.03     2  0.0000      0.976 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2832.03     4  0.0000      0.929 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2893.03     4  0.0609      0.929 0.00 0.00 0.00 0.98 0.02
#&gt; TCGA.AB.2956.03     4  0.0609      0.929 0.00 0.00 0.00 0.98 0.02
#&gt; TCGA.AB.2903.03     2  0.0000      0.976 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2948.03     1  0.5884      0.248 0.48 0.42 0.00 0.00 0.10
#&gt; TCGA.AB.2944.03     3  0.0000      0.844 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2904.03     5  0.6043      0.441 0.14 0.00 0.32 0.00 0.54
#&gt; TCGA.AB.3005.03     4  0.0000      0.929 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2861.03     4  0.0000      0.929 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2917.03     3  0.4182      0.255 0.00 0.00 0.60 0.00 0.40
#&gt; TCGA.AB.2964.03     2  0.0000      0.976 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2817.03     3  0.4227      0.219 0.00 0.00 0.58 0.00 0.42
#&gt; TCGA.AB.2857.03     3  0.4829     -0.105 0.02 0.00 0.50 0.00 0.48
#&gt; TCGA.AB.2805.03     2  0.0000      0.976 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2983.03     3  0.1043      0.825 0.00 0.00 0.96 0.00 0.04
#&gt; TCGA.AB.2990.03     2  0.0000      0.976 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2829.03     1  0.3109      0.773 0.80 0.00 0.00 0.00 0.20
#&gt; TCGA.AB.3002.03     2  0.0000      0.976 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2877.03     2  0.0000      0.976 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2920.03     3  0.0000      0.844 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2992.03     2  0.0000      0.976 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2919.03     2  0.0000      0.976 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2928.03     1  0.0000      0.864 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2927.03     5  0.3274      0.682 0.00 0.00 0.22 0.00 0.78
#&gt; TCGA.AB.2885.03     3  0.0000      0.844 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2996.03     1  0.5013      0.677 0.68 0.08 0.00 0.00 0.24
#&gt; TCGA.AB.2936.03     2  0.0000      0.976 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2966.03     3  0.0609      0.831 0.00 0.00 0.98 0.00 0.02
#&gt; TCGA.AB.2820.03     5  0.3983      0.534 0.00 0.00 0.34 0.00 0.66
#&gt; TCGA.AB.2900.03     2  0.0000      0.976 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2899.03     3  0.0000      0.844 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2926.03     2  0.0000      0.976 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2977.03     2  0.0000      0.976 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2849.03     3  0.1648      0.794 0.00 0.04 0.94 0.00 0.02
#&gt; TCGA.AB.2821.03     2  0.0000      0.976 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2863.03     2  0.0000      0.976 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2882.03     3  0.3999      0.510 0.00 0.24 0.74 0.00 0.02
#&gt; TCGA.AB.2916.03     5  0.4456      0.349 0.02 0.00 0.00 0.32 0.66
#&gt; TCGA.AB.2855.03     2  0.2020      0.873 0.00 0.90 0.10 0.00 0.00
#&gt; TCGA.AB.2978.03     1  0.0000      0.864 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2952.03     3  0.0000      0.844 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2868.03     3  0.0000      0.844 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2908.03     1  0.5131      0.404 0.54 0.00 0.04 0.00 0.42
#&gt; TCGA.AB.2938.03     1  0.3561      0.721 0.74 0.00 0.00 0.00 0.26
#&gt; TCGA.AB.2923.03     2  0.0000      0.976 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2890.03     3  0.4126      0.331 0.00 0.00 0.62 0.00 0.38
#&gt; TCGA.AB.2887.03     1  0.0000      0.864 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2834.03     2  0.1043      0.939 0.00 0.96 0.04 0.00 0.00
#&gt; TCGA.AB.2943.03     3  0.2280      0.749 0.00 0.00 0.88 0.00 0.12
#&gt; TCGA.AB.2813.03     5  0.1732      0.748 0.00 0.00 0.08 0.00 0.92
#&gt; TCGA.AB.2894.03     4  0.0609      0.929 0.00 0.00 0.00 0.98 0.02
#&gt; TCGA.AB.2935.03     3  0.0000      0.844 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2929.03     3  0.0000      0.844 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2831.03     1  0.2020      0.838 0.90 0.00 0.00 0.00 0.10
#&gt; TCGA.AB.2826.03     2  0.0000      0.976 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2810.03     2  0.0000      0.976 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2901.03     2  0.0000      0.976 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2975.03     1  0.2732      0.795 0.84 0.00 0.00 0.00 0.16
#&gt; TCGA.AB.2860.03     3  0.0000      0.844 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2854.03     2  0.1732      0.897 0.00 0.92 0.08 0.00 0.00
</code></pre>

<script>
$('#tab-node-02-get-classes-4-a').parent().next().next().hide();
$('#tab-node-02-get-classes-4-a').click(function(){
  $('#tab-node-02-get-classes-4-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-02-get-classes-5'>
<p><a id='tab-node-02-get-classes-5-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 6), get_membership(res, k = 6))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5   p6
#&gt; TCGA.AB.2995.03     1  0.2048     0.7041 0.88 0.00 0.00 0.00 0.00 0.12
#&gt; TCGA.AB.2878.03     3  0.0000     0.8343 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2883.03     4  0.0547     0.9707 0.00 0.00 0.00 0.98 0.02 0.00
#&gt; TCGA.AB.2984.03     2  0.0000     0.9304 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2874.03     2  0.0000     0.9304 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2830.03     1  0.1556     0.7286 0.92 0.00 0.00 0.00 0.00 0.08
#&gt; TCGA.AB.2941.03     1  0.3828     0.0889 0.56 0.00 0.00 0.00 0.00 0.44
#&gt; TCGA.AB.2987.03     1  0.5428     0.2822 0.54 0.00 0.00 0.32 0.00 0.14
#&gt; TCGA.AB.2843.03     3  0.5802    -0.2454 0.00 0.00 0.42 0.00 0.40 0.18
#&gt; TCGA.AB.2807.03     2  0.7336     0.0802 0.02 0.42 0.18 0.00 0.08 0.30
#&gt; TCGA.AB.2971.03     1  0.3076     0.5816 0.76 0.00 0.00 0.00 0.00 0.24
#&gt; TCGA.AB.2873.03     1  0.0000     0.7524 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2847.03     3  0.2581     0.7811 0.00 0.00 0.86 0.00 0.02 0.12
#&gt; TCGA.AB.2833.03     5  0.5390     0.3942 0.02 0.00 0.00 0.18 0.64 0.16
#&gt; TCGA.AB.2814.03     3  0.1267     0.8233 0.00 0.00 0.94 0.00 0.00 0.06
#&gt; TCGA.AB.2898.03     1  0.0000     0.7524 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2866.03     2  0.0000     0.9304 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2922.03     5  0.4004     0.5929 0.00 0.00 0.12 0.00 0.76 0.12
#&gt; TCGA.AB.2968.03     5  0.2260     0.4980 0.00 0.00 0.00 0.00 0.86 0.14
#&gt; TCGA.AB.2933.03     5  0.2190     0.5788 0.00 0.00 0.06 0.00 0.90 0.04
#&gt; TCGA.AB.2910.03     4  0.0547     0.9819 0.00 0.00 0.00 0.98 0.00 0.02
#&gt; TCGA.AB.2934.03     1  0.1092     0.7398 0.96 0.00 0.00 0.00 0.02 0.02
#&gt; TCGA.AB.2959.03     2  0.1267     0.9127 0.00 0.94 0.00 0.00 0.00 0.06
#&gt; TCGA.AB.2871.03     2  0.0547     0.9204 0.00 0.98 0.02 0.00 0.00 0.00
#&gt; TCGA.AB.2907.03     2  0.1267     0.9127 0.00 0.94 0.00 0.00 0.00 0.06
#&gt; TCGA.AB.2915.03     3  0.3928     0.6578 0.00 0.00 0.76 0.00 0.16 0.08
#&gt; TCGA.AB.2970.03     3  0.2094     0.8042 0.00 0.00 0.90 0.00 0.02 0.08
#&gt; TCGA.AB.2949.03     5  0.1556     0.5259 0.00 0.00 0.00 0.00 0.92 0.08
#&gt; TCGA.AB.2912.03     5  0.5267     0.4411 0.00 0.00 0.32 0.00 0.56 0.12
#&gt; TCGA.AB.2838.03     3  0.0000     0.8343 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2891.03     3  0.3829     0.6587 0.00 0.00 0.76 0.00 0.06 0.18
#&gt; TCGA.AB.2867.03     2  0.2454     0.8459 0.00 0.84 0.00 0.00 0.00 0.16
#&gt; TCGA.AB.2822.03     2  0.1556     0.9025 0.00 0.92 0.00 0.00 0.00 0.08
#&gt; TCGA.AB.2832.03     4  0.0000     0.9831 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2893.03     4  0.0547     0.9777 0.00 0.00 0.00 0.98 0.00 0.02
#&gt; TCGA.AB.2956.03     4  0.0000     0.9831 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2903.03     2  0.2048     0.8641 0.00 0.88 0.00 0.00 0.00 0.12
#&gt; TCGA.AB.2948.03     6  0.5748     0.2574 0.16 0.24 0.00 0.00 0.02 0.58
#&gt; TCGA.AB.2944.03     3  0.1267     0.8227 0.00 0.00 0.94 0.00 0.00 0.06
#&gt; TCGA.AB.2904.03     6  0.6985     0.0891 0.06 0.00 0.32 0.00 0.26 0.36
#&gt; TCGA.AB.3005.03     4  0.0547     0.9803 0.00 0.00 0.00 0.98 0.00 0.02
#&gt; TCGA.AB.2861.03     4  0.0937     0.9766 0.00 0.00 0.00 0.96 0.00 0.04
#&gt; TCGA.AB.2917.03     5  0.4609     0.3762 0.00 0.00 0.42 0.00 0.54 0.04
#&gt; TCGA.AB.2964.03     2  0.1556     0.8938 0.00 0.92 0.00 0.00 0.00 0.08
#&gt; TCGA.AB.2817.03     5  0.6070     0.3274 0.00 0.00 0.32 0.00 0.40 0.28
#&gt; TCGA.AB.2857.03     3  0.5882    -0.2304 0.00 0.00 0.42 0.00 0.20 0.38
#&gt; TCGA.AB.2805.03     2  0.1267     0.9127 0.00 0.94 0.00 0.00 0.00 0.06
#&gt; TCGA.AB.2983.03     3  0.3567     0.7149 0.00 0.00 0.80 0.00 0.10 0.10
#&gt; TCGA.AB.2990.03     2  0.0000     0.9304 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2829.03     6  0.4646     0.0898 0.46 0.00 0.00 0.00 0.04 0.50
#&gt; TCGA.AB.3002.03     2  0.0000     0.9304 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2877.03     2  0.0000     0.9304 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2920.03     3  0.0000     0.8343 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2992.03     2  0.2454     0.8459 0.00 0.84 0.00 0.00 0.00 0.16
#&gt; TCGA.AB.2919.03     2  0.0000     0.9304 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2928.03     1  0.0000     0.7524 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2927.03     5  0.3787     0.5965 0.00 0.00 0.12 0.00 0.78 0.10
#&gt; TCGA.AB.2885.03     3  0.0000     0.8343 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2996.03     6  0.4574     0.3656 0.26 0.00 0.02 0.00 0.04 0.68
#&gt; TCGA.AB.2936.03     2  0.2048     0.8807 0.00 0.88 0.00 0.00 0.00 0.12
#&gt; TCGA.AB.2966.03     3  0.0937     0.8287 0.00 0.00 0.96 0.00 0.00 0.04
#&gt; TCGA.AB.2820.03     5  0.4265     0.4718 0.00 0.00 0.30 0.00 0.66 0.04
#&gt; TCGA.AB.2900.03     2  0.0000     0.9304 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2899.03     3  0.2350     0.7916 0.00 0.00 0.88 0.00 0.02 0.10
#&gt; TCGA.AB.2926.03     2  0.0000     0.9304 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2977.03     2  0.0000     0.9304 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2849.03     3  0.1556     0.7683 0.00 0.08 0.92 0.00 0.00 0.00
#&gt; TCGA.AB.2821.03     2  0.0000     0.9304 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2863.03     2  0.0937     0.9203 0.00 0.96 0.00 0.00 0.00 0.04
#&gt; TCGA.AB.2882.03     3  0.4723     0.4885 0.00 0.18 0.68 0.00 0.00 0.14
#&gt; TCGA.AB.2916.03     5  0.6480     0.2711 0.08 0.00 0.00 0.22 0.54 0.16
#&gt; TCGA.AB.2855.03     2  0.2048     0.8304 0.00 0.88 0.12 0.00 0.00 0.00
#&gt; TCGA.AB.2978.03     1  0.0937     0.7359 0.96 0.00 0.00 0.00 0.00 0.04
#&gt; TCGA.AB.2952.03     3  0.0000     0.8343 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2868.03     3  0.0000     0.8343 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2908.03     6  0.7273     0.2881 0.16 0.00 0.14 0.00 0.34 0.36
#&gt; TCGA.AB.2938.03     6  0.4902     0.0972 0.46 0.00 0.00 0.00 0.06 0.48
#&gt; TCGA.AB.2923.03     2  0.1556     0.8938 0.00 0.92 0.00 0.00 0.00 0.08
#&gt; TCGA.AB.2890.03     5  0.5888     0.1827 0.00 0.00 0.40 0.00 0.40 0.20
#&gt; TCGA.AB.2887.03     1  0.0000     0.7524 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2834.03     2  0.1267     0.8917 0.00 0.94 0.06 0.00 0.00 0.00
#&gt; TCGA.AB.2943.03     3  0.3600     0.6788 0.02 0.00 0.82 0.00 0.08 0.08
#&gt; TCGA.AB.2813.03     5  0.4004     0.5055 0.00 0.00 0.12 0.00 0.76 0.12
#&gt; TCGA.AB.2894.03     4  0.0547     0.9819 0.00 0.00 0.00 0.98 0.00 0.02
#&gt; TCGA.AB.2935.03     3  0.0000     0.8343 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2929.03     3  0.0547     0.8320 0.00 0.00 0.98 0.00 0.00 0.02
#&gt; TCGA.AB.2831.03     1  0.4482     0.2313 0.60 0.00 0.00 0.00 0.04 0.36
#&gt; TCGA.AB.2826.03     2  0.0000     0.9304 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2810.03     2  0.0000     0.9304 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2901.03     2  0.0000     0.9304 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2975.03     1  0.4810     0.4396 0.66 0.00 0.00 0.00 0.12 0.22
#&gt; TCGA.AB.2860.03     3  0.0000     0.8343 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2854.03     2  0.3544     0.7807 0.00 0.80 0.12 0.00 0.00 0.08
</code></pre>

<script>
$('#tab-node-02-get-classes-5-a').parent().next().next().hide();
$('#tab-node-02-get-classes-5-a').click(function(){
  $('#tab-node-02-get-classes-5-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-02-get-classes-6'>
<p><a id='tab-node-02-get-classes-6-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 7), get_membership(res, k = 7))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5   p6   p7
#&gt; TCGA.AB.2995.03     1  0.2572     0.7056 0.80 0.00 0.00 0.00 0.00 0.20 0.00
#&gt; TCGA.AB.2878.03     3  0.0863     0.8258 0.00 0.00 0.96 0.00 0.00 0.00 0.04
#&gt; TCGA.AB.2883.03     4  0.0863     0.8720 0.00 0.00 0.00 0.96 0.00 0.04 0.00
#&gt; TCGA.AB.2984.03     2  0.0000     0.9029 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2874.03     2  0.0000     0.9029 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2830.03     1  0.2376     0.7655 0.86 0.00 0.00 0.00 0.00 0.12 0.02
#&gt; TCGA.AB.2941.03     1  0.3985     0.2619 0.52 0.00 0.00 0.00 0.00 0.46 0.02
#&gt; TCGA.AB.2987.03     4  0.6964    -0.3008 0.32 0.00 0.00 0.40 0.04 0.08 0.16
#&gt; TCGA.AB.2843.03     5  0.2945     0.5157 0.00 0.00 0.26 0.00 0.74 0.00 0.00
#&gt; TCGA.AB.2807.03     2  0.8200    -0.1735 0.02 0.34 0.12 0.00 0.12 0.18 0.22
#&gt; TCGA.AB.2971.03     1  0.5678     0.3925 0.54 0.04 0.00 0.00 0.00 0.26 0.16
#&gt; TCGA.AB.2873.03     1  0.1166     0.8038 0.94 0.00 0.00 0.00 0.00 0.06 0.00
#&gt; TCGA.AB.2847.03     3  0.3052     0.6796 0.00 0.00 0.78 0.00 0.20 0.00 0.02
#&gt; TCGA.AB.2833.03     5  0.7475    -0.7714 0.08 0.00 0.00 0.16 0.36 0.10 0.30
#&gt; TCGA.AB.2814.03     3  0.1664     0.8214 0.00 0.00 0.92 0.00 0.02 0.00 0.06
#&gt; TCGA.AB.2898.03     1  0.0000     0.8011 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2866.03     2  0.0000     0.9029 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2922.03     5  0.2278     0.4641 0.00 0.00 0.08 0.00 0.88 0.00 0.04
#&gt; TCGA.AB.2968.03     5  0.5694    -0.2902 0.04 0.00 0.00 0.00 0.46 0.12 0.38
#&gt; TCGA.AB.2933.03     5  0.3000     0.3356 0.00 0.00 0.02 0.00 0.84 0.04 0.10
#&gt; TCGA.AB.2910.03     4  0.0000     0.8833 0.00 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2934.03     1  0.0863     0.7975 0.96 0.00 0.00 0.00 0.00 0.04 0.00
#&gt; TCGA.AB.2959.03     2  0.0863     0.8968 0.00 0.96 0.00 0.00 0.00 0.00 0.04
#&gt; TCGA.AB.2871.03     2  0.1363     0.8766 0.00 0.94 0.04 0.00 0.00 0.00 0.02
#&gt; TCGA.AB.2907.03     2  0.1166     0.8910 0.00 0.94 0.00 0.00 0.00 0.00 0.06
#&gt; TCGA.AB.2915.03     3  0.3052     0.6873 0.00 0.00 0.78 0.00 0.20 0.00 0.02
#&gt; TCGA.AB.2970.03     3  0.1928     0.7968 0.00 0.00 0.90 0.00 0.08 0.00 0.02
#&gt; TCGA.AB.2949.03     5  0.4353     0.1465 0.00 0.00 0.00 0.00 0.66 0.10 0.24
#&gt; TCGA.AB.2912.03     5  0.3606     0.4981 0.00 0.00 0.30 0.00 0.68 0.00 0.02
#&gt; TCGA.AB.2838.03     3  0.0504     0.8314 0.00 0.00 0.98 0.00 0.00 0.00 0.02
#&gt; TCGA.AB.2891.03     3  0.5052     0.5327 0.02 0.00 0.66 0.00 0.04 0.22 0.06
#&gt; TCGA.AB.2867.03     2  0.2722     0.8329 0.00 0.84 0.00 0.00 0.00 0.04 0.12
#&gt; TCGA.AB.2822.03     2  0.1928     0.8721 0.00 0.90 0.00 0.00 0.00 0.02 0.08
#&gt; TCGA.AB.2832.03     4  0.0504     0.8801 0.00 0.00 0.00 0.98 0.00 0.00 0.02
#&gt; TCGA.AB.2893.03     4  0.0000     0.8833 0.00 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2956.03     4  0.0000     0.8833 0.00 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2903.03     2  0.2422     0.7859 0.00 0.82 0.00 0.00 0.00 0.00 0.18
#&gt; TCGA.AB.2948.03     6  0.6523     0.2169 0.06 0.28 0.00 0.00 0.02 0.46 0.18
#&gt; TCGA.AB.2944.03     3  0.0504     0.8280 0.00 0.00 0.98 0.00 0.00 0.00 0.02
#&gt; TCGA.AB.2904.03     6  0.6308     0.2821 0.02 0.00 0.32 0.00 0.10 0.48 0.08
#&gt; TCGA.AB.3005.03     4  0.1006     0.8727 0.00 0.00 0.00 0.96 0.00 0.02 0.02
#&gt; TCGA.AB.2861.03     4  0.0504     0.8805 0.00 0.00 0.00 0.98 0.00 0.02 0.00
#&gt; TCGA.AB.2917.03     5  0.4828     0.4139 0.00 0.00 0.36 0.00 0.56 0.06 0.02
#&gt; TCGA.AB.2964.03     2  0.2906     0.7715 0.00 0.80 0.02 0.00 0.00 0.00 0.18
#&gt; TCGA.AB.2817.03     5  0.4377     0.5014 0.00 0.00 0.24 0.00 0.68 0.02 0.06
#&gt; TCGA.AB.2857.03     6  0.6497     0.2641 0.02 0.00 0.28 0.00 0.14 0.48 0.08
#&gt; TCGA.AB.2805.03     2  0.0863     0.8968 0.00 0.96 0.00 0.00 0.00 0.00 0.04
#&gt; TCGA.AB.2983.03     3  0.4870     0.3967 0.00 0.00 0.58 0.00 0.28 0.00 0.14
#&gt; TCGA.AB.2990.03     2  0.0000     0.9029 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2829.03     6  0.4377     0.3953 0.24 0.00 0.02 0.00 0.06 0.68 0.00
#&gt; TCGA.AB.3002.03     2  0.0863     0.8968 0.00 0.96 0.00 0.00 0.00 0.00 0.04
#&gt; TCGA.AB.2877.03     2  0.0000     0.9029 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2920.03     3  0.0504     0.8314 0.00 0.00 0.98 0.00 0.00 0.00 0.02
#&gt; TCGA.AB.2992.03     2  0.3263     0.7969 0.00 0.80 0.00 0.00 0.00 0.08 0.12
#&gt; TCGA.AB.2919.03     2  0.0000     0.9029 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2928.03     1  0.0000     0.8011 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2927.03     5  0.1363     0.3855 0.00 0.00 0.02 0.00 0.94 0.00 0.04
#&gt; TCGA.AB.2885.03     3  0.0863     0.8258 0.00 0.00 0.96 0.00 0.00 0.00 0.04
#&gt; TCGA.AB.2996.03     6  0.6130     0.4069 0.10 0.02 0.00 0.00 0.16 0.58 0.14
#&gt; TCGA.AB.2936.03     2  0.2512     0.8480 0.00 0.86 0.00 0.00 0.00 0.04 0.10
#&gt; TCGA.AB.2966.03     3  0.2016     0.8109 0.00 0.00 0.90 0.00 0.00 0.06 0.04
#&gt; TCGA.AB.2820.03     5  0.6685     0.3096 0.00 0.00 0.32 0.00 0.38 0.16 0.14
#&gt; TCGA.AB.2900.03     2  0.0000     0.9029 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2899.03     3  0.2906     0.7068 0.00 0.00 0.80 0.00 0.18 0.00 0.02
#&gt; TCGA.AB.2926.03     2  0.0000     0.9029 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2977.03     2  0.0000     0.9029 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2849.03     3  0.1664     0.8195 0.00 0.00 0.92 0.00 0.00 0.02 0.06
#&gt; TCGA.AB.2821.03     2  0.0504     0.9004 0.00 0.98 0.00 0.00 0.00 0.00 0.02
#&gt; TCGA.AB.2863.03     2  0.1664     0.8816 0.00 0.92 0.00 0.00 0.00 0.02 0.06
#&gt; TCGA.AB.2882.03     3  0.6158     0.3041 0.00 0.18 0.52 0.00 0.02 0.04 0.24
#&gt; TCGA.AB.2916.03     7  0.7549     0.0000 0.10 0.00 0.00 0.18 0.30 0.08 0.34
#&gt; TCGA.AB.2855.03     2  0.3244     0.7125 0.00 0.78 0.18 0.00 0.00 0.00 0.04
#&gt; TCGA.AB.2978.03     1  0.2803     0.6886 0.84 0.00 0.00 0.00 0.00 0.10 0.06
#&gt; TCGA.AB.2952.03     3  0.0504     0.8314 0.00 0.00 0.98 0.00 0.00 0.00 0.02
#&gt; TCGA.AB.2868.03     3  0.1166     0.8257 0.00 0.00 0.94 0.00 0.00 0.00 0.06
#&gt; TCGA.AB.2908.03     6  0.6612     0.4094 0.08 0.00 0.14 0.00 0.10 0.56 0.12
#&gt; TCGA.AB.2938.03     6  0.4377     0.4065 0.24 0.00 0.00 0.00 0.06 0.68 0.02
#&gt; TCGA.AB.2923.03     2  0.3388     0.7324 0.00 0.76 0.04 0.00 0.00 0.00 0.20
#&gt; TCGA.AB.2890.03     5  0.3186     0.5221 0.00 0.00 0.22 0.00 0.76 0.00 0.02
#&gt; TCGA.AB.2887.03     1  0.0863     0.7980 0.96 0.00 0.00 0.00 0.00 0.04 0.00
#&gt; TCGA.AB.2834.03     2  0.3086     0.7396 0.00 0.80 0.16 0.00 0.00 0.00 0.04
#&gt; TCGA.AB.2943.03     3  0.4779     0.5424 0.00 0.00 0.68 0.00 0.04 0.18 0.10
#&gt; TCGA.AB.2813.03     5  0.6930     0.1962 0.00 0.00 0.18 0.00 0.36 0.20 0.26
#&gt; TCGA.AB.2894.03     4  0.0504     0.8701 0.00 0.00 0.00 0.98 0.02 0.00 0.00
#&gt; TCGA.AB.2935.03     3  0.0504     0.8314 0.00 0.00 0.98 0.00 0.00 0.00 0.02
#&gt; TCGA.AB.2929.03     3  0.1671     0.7892 0.00 0.00 0.90 0.00 0.10 0.00 0.00
#&gt; TCGA.AB.2831.03     6  0.3909     0.0745 0.40 0.00 0.00 0.00 0.00 0.58 0.02
#&gt; TCGA.AB.2826.03     2  0.0000     0.9029 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2810.03     2  0.0000     0.9029 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2901.03     2  0.0504     0.8999 0.00 0.98 0.00 0.00 0.00 0.00 0.02
#&gt; TCGA.AB.2975.03     6  0.5822     0.0780 0.30 0.00 0.00 0.02 0.02 0.52 0.14
#&gt; TCGA.AB.2860.03     3  0.0863     0.8294 0.00 0.00 0.96 0.00 0.00 0.00 0.04
#&gt; TCGA.AB.2854.03     2  0.2163     0.8406 0.00 0.88 0.10 0.00 0.00 0.00 0.02
</code></pre>

<script>
$('#tab-node-02-get-classes-6-a').parent().next().next().hide();
$('#tab-node-02-get-classes-6-a').click(function(){
  $('#tab-node-02-get-classes-6-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-02-get-classes-7'>
<p><a id='tab-node-02-get-classes-7-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 8), get_membership(res, k = 8))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5   p6   p7   p8
#&gt; TCGA.AB.2995.03     1  0.2981     0.4397 0.76 0.00 0.00 0.00 0.00 0.22 0.00 0.02
#&gt; TCGA.AB.2878.03     3  0.0471     0.8045 0.00 0.00 0.98 0.00 0.02 0.00 0.00 0.00
#&gt; TCGA.AB.2883.03     4  0.2348     0.8093 0.00 0.00 0.00 0.88 0.00 0.02 0.04 0.06
#&gt; TCGA.AB.2984.03     2  0.0000     0.8871 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2874.03     2  0.0000     0.8871 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2830.03     1  0.4512     0.2496 0.66 0.00 0.00 0.00 0.00 0.22 0.04 0.08
#&gt; TCGA.AB.2941.03     6  0.4821    -0.0437 0.24 0.00 0.00 0.00 0.02 0.60 0.00 0.14
#&gt; TCGA.AB.2987.03     4  0.6109    -0.1192 0.28 0.00 0.00 0.42 0.00 0.02 0.24 0.04
#&gt; TCGA.AB.2843.03     5  0.4672     0.5280 0.00 0.00 0.26 0.00 0.64 0.02 0.04 0.04
#&gt; TCGA.AB.2807.03     6  0.7521     0.0243 0.02 0.30 0.10 0.00 0.12 0.32 0.00 0.14
#&gt; TCGA.AB.2971.03     8  0.6547     0.0000 0.34 0.02 0.00 0.02 0.00 0.24 0.04 0.34
#&gt; TCGA.AB.2873.03     1  0.2674     0.6231 0.86 0.00 0.00 0.00 0.00 0.04 0.06 0.04
#&gt; TCGA.AB.2847.03     3  0.2569     0.6845 0.00 0.00 0.82 0.00 0.16 0.00 0.00 0.02
#&gt; TCGA.AB.2833.03     7  0.5623     0.5258 0.06 0.00 0.00 0.16 0.12 0.02 0.62 0.02
#&gt; TCGA.AB.2814.03     3  0.0000     0.8103 0.00 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2898.03     1  0.0471     0.6732 0.98 0.00 0.00 0.00 0.00 0.02 0.00 0.00
#&gt; TCGA.AB.2866.03     2  0.0000     0.8871 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2922.03     5  0.3421     0.4853 0.00 0.00 0.08 0.00 0.80 0.00 0.08 0.04
#&gt; TCGA.AB.2968.03     7  0.5183     0.2512 0.00 0.00 0.00 0.00 0.34 0.06 0.52 0.08
#&gt; TCGA.AB.2933.03     5  0.4492     0.2598 0.00 0.00 0.04 0.00 0.70 0.06 0.18 0.02
#&gt; TCGA.AB.2910.03     4  0.0808     0.8511 0.00 0.00 0.00 0.96 0.00 0.00 0.04 0.00
#&gt; TCGA.AB.2934.03     1  0.0941     0.6637 0.96 0.00 0.00 0.00 0.00 0.00 0.02 0.02
#&gt; TCGA.AB.2959.03     2  0.1275     0.8730 0.00 0.94 0.00 0.00 0.00 0.02 0.00 0.04
#&gt; TCGA.AB.2871.03     2  0.2591     0.8062 0.00 0.86 0.04 0.00 0.00 0.02 0.00 0.08
#&gt; TCGA.AB.2907.03     2  0.1275     0.8730 0.00 0.94 0.00 0.00 0.00 0.02 0.00 0.04
#&gt; TCGA.AB.2915.03     3  0.3660     0.5382 0.00 0.00 0.70 0.00 0.24 0.00 0.06 0.00
#&gt; TCGA.AB.2970.03     3  0.1091     0.7903 0.00 0.00 0.94 0.00 0.06 0.00 0.00 0.00
#&gt; TCGA.AB.2949.03     5  0.6177    -0.2406 0.02 0.00 0.02 0.00 0.44 0.06 0.36 0.10
#&gt; TCGA.AB.2912.03     5  0.4397     0.5256 0.00 0.00 0.24 0.00 0.66 0.00 0.06 0.04
#&gt; TCGA.AB.2838.03     3  0.0000     0.8103 0.00 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2891.03     3  0.5355     0.2806 0.02 0.00 0.54 0.00 0.02 0.34 0.04 0.04
#&gt; TCGA.AB.2867.03     2  0.2864     0.8069 0.00 0.84 0.00 0.00 0.00 0.08 0.02 0.06
#&gt; TCGA.AB.2822.03     2  0.2071     0.8524 0.00 0.90 0.00 0.00 0.00 0.04 0.02 0.04
#&gt; TCGA.AB.2832.03     4  0.0471     0.8577 0.00 0.00 0.00 0.98 0.02 0.00 0.00 0.00
#&gt; TCGA.AB.2893.03     4  0.0000     0.8596 0.00 0.00 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2956.03     4  0.0941     0.8551 0.00 0.00 0.00 0.96 0.00 0.02 0.00 0.02
#&gt; TCGA.AB.2903.03     2  0.3808     0.4983 0.00 0.62 0.00 0.00 0.00 0.04 0.00 0.34
#&gt; TCGA.AB.2948.03     6  0.4528     0.2094 0.04 0.14 0.00 0.00 0.00 0.68 0.00 0.14
#&gt; TCGA.AB.2944.03     3  0.0000     0.8103 0.00 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2904.03     6  0.7292     0.2228 0.08 0.00 0.18 0.00 0.18 0.42 0.02 0.12
#&gt; TCGA.AB.3005.03     4  0.1741     0.8351 0.00 0.00 0.00 0.92 0.02 0.00 0.04 0.02
#&gt; TCGA.AB.2861.03     4  0.2165     0.8220 0.00 0.00 0.00 0.88 0.00 0.00 0.06 0.06
#&gt; TCGA.AB.2917.03     3  0.5189    -0.1599 0.00 0.00 0.48 0.00 0.38 0.00 0.10 0.04
#&gt; TCGA.AB.2964.03     2  0.3991     0.4990 0.00 0.62 0.00 0.00 0.00 0.06 0.00 0.32
#&gt; TCGA.AB.2817.03     5  0.5269     0.4505 0.00 0.00 0.14 0.00 0.64 0.12 0.08 0.02
#&gt; TCGA.AB.2857.03     6  0.6335     0.1233 0.00 0.00 0.24 0.00 0.22 0.40 0.00 0.14
#&gt; TCGA.AB.2805.03     2  0.1275     0.8730 0.00 0.94 0.00 0.00 0.00 0.02 0.00 0.04
#&gt; TCGA.AB.2983.03     3  0.5698     0.4201 0.00 0.00 0.60 0.00 0.16 0.08 0.04 0.12
#&gt; TCGA.AB.2990.03     2  0.0000     0.8871 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2829.03     6  0.4622     0.2504 0.26 0.00 0.00 0.00 0.02 0.64 0.02 0.06
#&gt; TCGA.AB.3002.03     2  0.0471     0.8838 0.00 0.98 0.00 0.00 0.00 0.00 0.00 0.02
#&gt; TCGA.AB.2877.03     2  0.0000     0.8871 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2920.03     3  0.0000     0.8103 0.00 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2992.03     2  0.3102     0.7959 0.00 0.82 0.00 0.00 0.00 0.08 0.02 0.08
#&gt; TCGA.AB.2919.03     2  0.0000     0.8871 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2928.03     1  0.0000     0.6723 1.00 0.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2927.03     5  0.3879     0.4649 0.00 0.00 0.10 0.00 0.74 0.00 0.14 0.02
#&gt; TCGA.AB.2885.03     3  0.0808     0.8010 0.00 0.00 0.96 0.00 0.00 0.00 0.00 0.04
#&gt; TCGA.AB.2996.03     6  0.3903     0.3562 0.06 0.02 0.00 0.00 0.08 0.78 0.00 0.06
#&gt; TCGA.AB.2936.03     2  0.2348     0.8402 0.00 0.88 0.00 0.00 0.00 0.04 0.02 0.06
#&gt; TCGA.AB.2966.03     3  0.2025     0.7586 0.00 0.00 0.88 0.00 0.00 0.10 0.00 0.02
#&gt; TCGA.AB.2820.03     5  0.7133     0.3354 0.00 0.00 0.26 0.00 0.36 0.08 0.12 0.18
#&gt; TCGA.AB.2900.03     2  0.0000     0.8871 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2899.03     3  0.1563     0.7615 0.00 0.00 0.90 0.00 0.10 0.00 0.00 0.00
#&gt; TCGA.AB.2926.03     2  0.0000     0.8871 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2977.03     2  0.0000     0.8871 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2849.03     3  0.2071     0.7629 0.00 0.04 0.90 0.00 0.00 0.02 0.00 0.04
#&gt; TCGA.AB.2821.03     2  0.0000     0.8871 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2863.03     2  0.0808     0.8788 0.00 0.96 0.00 0.00 0.00 0.00 0.00 0.04
#&gt; TCGA.AB.2882.03     3  0.6723    -0.0080 0.00 0.18 0.38 0.00 0.02 0.16 0.00 0.26
#&gt; TCGA.AB.2916.03     7  0.6457     0.4556 0.10 0.00 0.00 0.20 0.14 0.00 0.50 0.06
#&gt; TCGA.AB.2855.03     2  0.3808     0.4455 0.00 0.62 0.34 0.00 0.00 0.00 0.00 0.04
#&gt; TCGA.AB.2978.03     1  0.3178     0.5553 0.80 0.00 0.00 0.00 0.00 0.02 0.04 0.14
#&gt; TCGA.AB.2952.03     3  0.0000     0.8103 0.00 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2868.03     3  0.1275     0.7920 0.00 0.00 0.94 0.00 0.00 0.04 0.00 0.02
#&gt; TCGA.AB.2908.03     6  0.6221     0.3814 0.16 0.00 0.08 0.00 0.02 0.58 0.08 0.08
#&gt; TCGA.AB.2938.03     6  0.3627     0.3835 0.14 0.00 0.00 0.00 0.02 0.78 0.04 0.02
#&gt; TCGA.AB.2923.03     2  0.4570     0.5095 0.00 0.62 0.04 0.00 0.00 0.06 0.00 0.28
#&gt; TCGA.AB.2890.03     5  0.5293     0.5245 0.00 0.00 0.20 0.00 0.62 0.08 0.08 0.02
#&gt; TCGA.AB.2887.03     1  0.1275     0.6632 0.94 0.00 0.00 0.00 0.00 0.04 0.02 0.00
#&gt; TCGA.AB.2834.03     2  0.3170     0.6766 0.00 0.76 0.20 0.00 0.00 0.00 0.00 0.04
#&gt; TCGA.AB.2943.03     3  0.4896     0.4929 0.00 0.00 0.68 0.00 0.06 0.12 0.02 0.12
#&gt; TCGA.AB.2813.03     5  0.7441     0.1788 0.02 0.00 0.10 0.00 0.40 0.14 0.20 0.14
#&gt; TCGA.AB.2894.03     4  0.0471     0.8582 0.00 0.00 0.00 0.98 0.00 0.00 0.02 0.00
#&gt; TCGA.AB.2935.03     3  0.0000     0.8103 0.00 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2929.03     3  0.0941     0.8027 0.00 0.00 0.96 0.00 0.02 0.00 0.00 0.02
#&gt; TCGA.AB.2831.03     6  0.3291     0.2667 0.28 0.00 0.00 0.00 0.02 0.70 0.00 0.00
#&gt; TCGA.AB.2826.03     2  0.0000     0.8871 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2810.03     2  0.0000     0.8871 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2901.03     2  0.0471     0.8833 0.00 0.98 0.00 0.00 0.00 0.00 0.00 0.02
#&gt; TCGA.AB.2975.03     1  0.6804    -0.1847 0.36 0.00 0.00 0.00 0.02 0.22 0.24 0.16
#&gt; TCGA.AB.2860.03     3  0.0000     0.8103 0.00 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2854.03     2  0.3794     0.6668 0.00 0.74 0.18 0.00 0.04 0.00 0.00 0.04
</code></pre>

<script>
$('#tab-node-02-get-classes-7-a').parent().next().next().hide();
$('#tab-node-02-get-classes-7-a').click(function(){
  $('#tab-node-02-get-classes-7-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>
</div>

Heatmaps for the consensus matrix. It visualizes the probability of two
samples to be in a same group.




<script>
$( function() {
	$( '#tabs-node-02-consensus-heatmap' ).tabs();
} );
</script>
<div id='tabs-node-02-consensus-heatmap'>
<ul>
<li><a href='#tab-node-02-consensus-heatmap-1'>k = 2</a></li>
<li><a href='#tab-node-02-consensus-heatmap-2'>k = 3</a></li>
<li><a href='#tab-node-02-consensus-heatmap-3'>k = 4</a></li>
<li><a href='#tab-node-02-consensus-heatmap-4'>k = 5</a></li>
<li><a href='#tab-node-02-consensus-heatmap-5'>k = 6</a></li>
<li><a href='#tab-node-02-consensus-heatmap-6'>k = 7</a></li>
<li><a href='#tab-node-02-consensus-heatmap-7'>k = 8</a></li>
</ul>
<div id='tab-node-02-consensus-heatmap-1'>
<pre><code class="r">consensus_heatmap(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-02-consensus-heatmap-1-1.png" alt="plot of chunk tab-node-02-consensus-heatmap-1"/></p>

</div>
<div id='tab-node-02-consensus-heatmap-2'>
<pre><code class="r">consensus_heatmap(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-02-consensus-heatmap-2-1.png" alt="plot of chunk tab-node-02-consensus-heatmap-2"/></p>

</div>
<div id='tab-node-02-consensus-heatmap-3'>
<pre><code class="r">consensus_heatmap(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-02-consensus-heatmap-3-1.png" alt="plot of chunk tab-node-02-consensus-heatmap-3"/></p>

</div>
<div id='tab-node-02-consensus-heatmap-4'>
<pre><code class="r">consensus_heatmap(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-02-consensus-heatmap-4-1.png" alt="plot of chunk tab-node-02-consensus-heatmap-4"/></p>

</div>
<div id='tab-node-02-consensus-heatmap-5'>
<pre><code class="r">consensus_heatmap(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-02-consensus-heatmap-5-1.png" alt="plot of chunk tab-node-02-consensus-heatmap-5"/></p>

</div>
<div id='tab-node-02-consensus-heatmap-6'>
<pre><code class="r">consensus_heatmap(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-02-consensus-heatmap-6-1.png" alt="plot of chunk tab-node-02-consensus-heatmap-6"/></p>

</div>
<div id='tab-node-02-consensus-heatmap-7'>
<pre><code class="r">consensus_heatmap(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-02-consensus-heatmap-7-1.png" alt="plot of chunk tab-node-02-consensus-heatmap-7"/></p>

</div>
</div>

Heatmaps for the membership of samples in all partitions to see how consistent they are:





<script>
$( function() {
	$( '#tabs-node-02-membership-heatmap' ).tabs();
} );
</script>
<div id='tabs-node-02-membership-heatmap'>
<ul>
<li><a href='#tab-node-02-membership-heatmap-1'>k = 2</a></li>
<li><a href='#tab-node-02-membership-heatmap-2'>k = 3</a></li>
<li><a href='#tab-node-02-membership-heatmap-3'>k = 4</a></li>
<li><a href='#tab-node-02-membership-heatmap-4'>k = 5</a></li>
<li><a href='#tab-node-02-membership-heatmap-5'>k = 6</a></li>
<li><a href='#tab-node-02-membership-heatmap-6'>k = 7</a></li>
<li><a href='#tab-node-02-membership-heatmap-7'>k = 8</a></li>
</ul>
<div id='tab-node-02-membership-heatmap-1'>
<pre><code class="r">membership_heatmap(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-02-membership-heatmap-1-1.png" alt="plot of chunk tab-node-02-membership-heatmap-1"/></p>

</div>
<div id='tab-node-02-membership-heatmap-2'>
<pre><code class="r">membership_heatmap(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-02-membership-heatmap-2-1.png" alt="plot of chunk tab-node-02-membership-heatmap-2"/></p>

</div>
<div id='tab-node-02-membership-heatmap-3'>
<pre><code class="r">membership_heatmap(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-02-membership-heatmap-3-1.png" alt="plot of chunk tab-node-02-membership-heatmap-3"/></p>

</div>
<div id='tab-node-02-membership-heatmap-4'>
<pre><code class="r">membership_heatmap(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-02-membership-heatmap-4-1.png" alt="plot of chunk tab-node-02-membership-heatmap-4"/></p>

</div>
<div id='tab-node-02-membership-heatmap-5'>
<pre><code class="r">membership_heatmap(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-02-membership-heatmap-5-1.png" alt="plot of chunk tab-node-02-membership-heatmap-5"/></p>

</div>
<div id='tab-node-02-membership-heatmap-6'>
<pre><code class="r">membership_heatmap(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-02-membership-heatmap-6-1.png" alt="plot of chunk tab-node-02-membership-heatmap-6"/></p>

</div>
<div id='tab-node-02-membership-heatmap-7'>
<pre><code class="r">membership_heatmap(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-02-membership-heatmap-7-1.png" alt="plot of chunk tab-node-02-membership-heatmap-7"/></p>

</div>
</div>

As soon as the classes for columns are determined, the signatures
that are significantly different between subgroups can be looked for. 
Following are the heatmaps for signatures.






<script>
$( function() {
	$( '#tabs-node-02-get-signatures' ).tabs();
} );
</script>
<div id='tabs-node-02-get-signatures'>
<ul>
<li><a href='#tab-node-02-get-signatures-1'>k = 2</a></li>
<li><a href='#tab-node-02-get-signatures-2'>k = 3</a></li>
<li><a href='#tab-node-02-get-signatures-3'>k = 4</a></li>
<li><a href='#tab-node-02-get-signatures-4'>k = 5</a></li>
<li><a href='#tab-node-02-get-signatures-5'>k = 6</a></li>
<li><a href='#tab-node-02-get-signatures-6'>k = 7</a></li>
<li><a href='#tab-node-02-get-signatures-7'>k = 8</a></li>
</ul>
<div id='tab-node-02-get-signatures-1'>
<pre><code class="r">get_signatures(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-02-get-signatures-1-1.png" alt="plot of chunk tab-node-02-get-signatures-1"/></p>

</div>
<div id='tab-node-02-get-signatures-2'>
<pre><code class="r">get_signatures(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-02-get-signatures-2-1.png" alt="plot of chunk tab-node-02-get-signatures-2"/></p>

</div>
<div id='tab-node-02-get-signatures-3'>
<pre><code class="r">get_signatures(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-02-get-signatures-3-1.png" alt="plot of chunk tab-node-02-get-signatures-3"/></p>

</div>
<div id='tab-node-02-get-signatures-4'>
<pre><code class="r">get_signatures(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-02-get-signatures-4-1.png" alt="plot of chunk tab-node-02-get-signatures-4"/></p>

</div>
<div id='tab-node-02-get-signatures-5'>
<pre><code class="r">get_signatures(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-02-get-signatures-5-1.png" alt="plot of chunk tab-node-02-get-signatures-5"/></p>

</div>
<div id='tab-node-02-get-signatures-6'>
<pre><code class="r">get_signatures(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-02-get-signatures-6-1.png" alt="plot of chunk tab-node-02-get-signatures-6"/></p>

</div>
<div id='tab-node-02-get-signatures-7'>
<pre><code class="r">get_signatures(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-02-get-signatures-7-1.png" alt="plot of chunk tab-node-02-get-signatures-7"/></p>

</div>
</div>



Compare the overlap of signatures from different k:

```r
compare_signatures(res)
```

![plot of chunk node-02-signature_compare](figure_cola/node-02-signature_compare-1.png)

`get_signature()` returns a data frame invisibly. To get the list of signatures, the function
call should be assigned to a variable explicitly. In following code, if `plot` argument is set
to `FALSE`, no heatmap is plotted while only the differential analysis is performed.

```r
# code only for demonstration
tb = get_signature(res, k = ..., plot = FALSE)
```

An example of the output of `tb` is:

```
#>   which_row         fdr    mean_1    mean_2 scaled_mean_1 scaled_mean_2 km
#> 1        38 0.042760348  8.373488  9.131774    -0.5533452     0.5164555  1
#> 2        40 0.018707592  7.106213  8.469186    -0.6173731     0.5762149  1
#> 3        55 0.019134737 10.221463 11.207825    -0.6159697     0.5749050  1
#> 4        59 0.006059896  5.921854  7.869574    -0.6899429     0.6439467  1
#> 5        60 0.018055526  8.928898 10.211722    -0.6204761     0.5791110  1
#> 6        98 0.009384629 15.714769 14.887706     0.6635654    -0.6193277  2
...
```

The columns in `tb` are:

1. `which_row`: row indices corresponding to the input matrix.
2. `fdr`: FDR for the differential test. 
3. `mean_x`: The mean value in group x.
4. `scaled_mean_x`: The mean value in group x after rows are scaled.
5. `km`: Row groups if k-means clustering is applied to rows (which is done by automatically selecting number of clusters).

If there are too many signatures, `top_signatures = ...` can be set to only show the 
signatures with the highest FDRs:

```r
# code only for demonstration
# e.g. to show the top 500 most significant rows
tb = get_signature(res, k = ..., top_signatures = 500)
```

If the signatures are defined as these which are uniquely high in current group, `diff_method` argument
can be set to `"uniquely_high_in_one_group"`:

```r
# code only for demonstration
tb = get_signature(res, k = ..., diff_method = "uniquely_high_in_one_group")
```




UMAP plot which shows how samples are separated.


<script>
$( function() {
	$( '#tabs-node-02-dimension-reduction' ).tabs();
} );
</script>
<div id='tabs-node-02-dimension-reduction'>
<ul>
<li><a href='#tab-node-02-dimension-reduction-1'>k = 2</a></li>
<li><a href='#tab-node-02-dimension-reduction-2'>k = 3</a></li>
<li><a href='#tab-node-02-dimension-reduction-3'>k = 4</a></li>
<li><a href='#tab-node-02-dimension-reduction-4'>k = 5</a></li>
<li><a href='#tab-node-02-dimension-reduction-5'>k = 6</a></li>
<li><a href='#tab-node-02-dimension-reduction-6'>k = 7</a></li>
<li><a href='#tab-node-02-dimension-reduction-7'>k = 8</a></li>
</ul>
<div id='tab-node-02-dimension-reduction-1'>
<pre><code class="r">dimension_reduction(res, k = 2, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-02-dimension-reduction-1-1.png" alt="plot of chunk tab-node-02-dimension-reduction-1"/></p>

</div>
<div id='tab-node-02-dimension-reduction-2'>
<pre><code class="r">dimension_reduction(res, k = 3, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-02-dimension-reduction-2-1.png" alt="plot of chunk tab-node-02-dimension-reduction-2"/></p>

</div>
<div id='tab-node-02-dimension-reduction-3'>
<pre><code class="r">dimension_reduction(res, k = 4, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-02-dimension-reduction-3-1.png" alt="plot of chunk tab-node-02-dimension-reduction-3"/></p>

</div>
<div id='tab-node-02-dimension-reduction-4'>
<pre><code class="r">dimension_reduction(res, k = 5, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-02-dimension-reduction-4-1.png" alt="plot of chunk tab-node-02-dimension-reduction-4"/></p>

</div>
<div id='tab-node-02-dimension-reduction-5'>
<pre><code class="r">dimension_reduction(res, k = 6, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-02-dimension-reduction-5-1.png" alt="plot of chunk tab-node-02-dimension-reduction-5"/></p>

</div>
<div id='tab-node-02-dimension-reduction-6'>
<pre><code class="r">dimension_reduction(res, k = 7, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-02-dimension-reduction-6-1.png" alt="plot of chunk tab-node-02-dimension-reduction-6"/></p>

</div>
<div id='tab-node-02-dimension-reduction-7'>
<pre><code class="r">dimension_reduction(res, k = 8, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-02-dimension-reduction-7-1.png" alt="plot of chunk tab-node-02-dimension-reduction-7"/></p>

</div>
</div>



Following heatmap shows how subgroups are split when increasing `k`:

```r
collect_classes(res)
```

![plot of chunk node-02-collect-classes](figure_cola/node-02-collect-classes-1.png)



If matrix rows can be associated to genes, consider to use `functional_enrichment(res,
...)` to perform function enrichment for the signature genes. See [this vignette](https://jokergoo.github.io/cola_vignettes/functional_enrichment.html) for more detailed explanations.


 

---------------------------------------------------




### Node021


Parent node: [Node02](#Node02).
Child nodes: 
                Node0111-leaf
        ,
                Node0112-leaf
        ,
                Node0131-leaf
        ,
                Node0132-leaf
        ,
                Node0141-leaf
        ,
                Node0142-leaf
        ,
                Node0211-leaf
        ,
                Node0212-leaf
        ,
                Node0213-leaf
        ,
                Node0221-leaf
        ,
                [Node0222](#Node0222)
        ,
                Node0231-leaf
        ,
                Node0232-leaf
        ,
                Node0233-leaf
        ,
                Node0321-leaf
        ,
                Node0322-leaf
        ,
                Node0323-leaf
        ,
                Node0324-leaf
        ,
                Node0325-leaf
        ,
                Node0331-leaf
        ,
                Node0332-leaf
        .







The object with results only for a single top-value method and a single partitioning method 
can be extracted as:

```r
res = res_rh["021"]
```

A summary of `res` and all the functions that can be applied to it:

```r
res
```

```
#> A 'ConsensusPartition' object with k = 2, 3, 4, 5, 6, 7, 8.
#>   On a matrix with 30000 rows and 26 columns.
#>   Top rows (1000) are extracted by 'ATC' method.
#>   Subgroups are detected by 'kmeans' method.
#>   Performed in total 350 partitions by row resampling.
#>   Best k for subgroups seems to be 3.
#> 
#> Following methods can be applied to this 'ConsensusPartition' object:
#>  [1] "cola_report"             "collect_classes"         "collect_plots"          
#>  [4] "collect_stats"           "colnames"                "compare_partitions"     
#>  [7] "compare_signatures"      "consensus_heatmap"       "dimension_reduction"    
#> [10] "functional_enrichment"   "get_anno_col"            "get_anno"               
#> [13] "get_classes"             "get_consensus"           "get_matrix"             
#> [16] "get_membership"          "get_param"               "get_signatures"         
#> [19] "get_stats"               "is_best_k"               "is_stable_k"            
#> [22] "membership_heatmap"      "ncol"                    "nrow"                   
#> [25] "plot_ecdf"               "predict_classes"         "rownames"               
#> [28] "select_partition_number" "show"                    "suggest_best_k"         
#> [31] "test_to_known_factors"   "top_rows_heatmap"
```

`collect_plots()` function collects all the plots made from `res` for all `k` (number of subgroups)
into one single page to provide an easy and fast comparison between different `k`.

```r
collect_plots(res)
```

![plot of chunk node-021-collect-plots](figure_cola/node-021-collect-plots-1.png)

The plots are:

- The first row: a plot of the eCDF (empirical cumulative distribution
  function) curves of the consensus matrix for each `k` and the heatmap of
  predicted classes for each `k`.
- The second row: heatmaps of the consensus matrix for each `k`.
- The third row: heatmaps of the membership matrix for each `k`.
- The fouth row: heatmaps of the signatures for each `k`.

All the plots in panels can be made by individual functions and they are
plotted later in this section.

`select_partition_number()` produces several plots showing different
statistics for choosing "optimized" `k`. There are following statistics:

- eCDF curves of the consensus matrix for each `k`;
- 1-PAC. [The PAC score](https://en.wikipedia.org/wiki/Consensus_clustering#Over-interpretation_potential_of_consensus_clustering)
  measures the proportion of the ambiguous subgrouping.
- Mean silhouette score.
- Concordance. The mean probability of fiting the consensus subgroup labels in all
  partitions.
- Area increased. Denote $A_k$ as the area under the eCDF curve for current
  `k`, the area increased is defined as $A_k - A_{k-1}$.
- Rand index. The percent of pairs of samples that are both in a same cluster
  or both are not in a same cluster in the partition of k and k-1.
- Jaccard index. The ratio of pairs of samples are both in a same cluster in
  the partition of k and k-1 and the pairs of samples are both in a same
  cluster in the partition k or k-1.

The detailed explanations of these statistics can be found in [the _cola_
vignette](https://jokergoo.github.io/cola_vignettes/cola.html#toc_13).

Generally speaking, higher 1-PAC score, higher mean silhouette score or higher
concordance corresponds to better partition. Rand index and Jaccard index
measure how similar the current partition is compared to partition with `k-1`.
If they are too similar, we won't accept `k` is better than `k-1`.

```r
select_partition_number(res)
```

![plot of chunk node-021-select-partition-number](figure_cola/node-021-select-partition-number-1.png)

The numeric values for all these statistics can be obtained by `get_stats()`.

```r
get_stats(res)
```

```
#>   k 1-PAC mean_silhouette concordance area_increased  Rand Jaccard
#> 2 2 1.000           1.000       1.000         0.5205 0.480   0.480
#> 3 3 1.000           0.983       0.985         0.3254 0.729   0.488
#> 4 4 0.783           0.792       0.870         0.0932 0.914   0.731
#> 5 5 0.815           0.556       0.842         0.0609 0.978   0.912
#> 6 6 0.841           0.911       0.851         0.0334 0.898   0.566
#> 7 7 0.826           0.845       0.878         0.0329 0.991   0.935
#> 8 8 0.851           0.800       0.881         0.0251 1.000   1.000
```

`suggest_best_k()` suggests the best $k$ based on these statistics. The rules are as follows:

- All $k$ with Jaccard index larger than 0.95 are removed because increasing
  $k$ does not provide enough extra information. If all $k$ are removed, it is
  marked as no subgroup is detected.
- For all $k$ with 1-PAC score larger than 0.9, the maximal $k$ is taken as
  the best $k$, and other $k$ are marked as optional $k$.
- If it does not fit the second rule. The $k$ with the maximal vote of the
  highest 1-PAC score, highest mean silhouette, and highest concordance is
  taken as the best $k$.

```r
suggest_best_k(res)
```

```
#> [1] 3
#> attr(,"optional")
#> [1] 2
```

There is also optional best $k$ = 2 that is worth to check.

Following is the table of the partitions (You need to click the **show/hide
code output** link to see it). The membership matrix (columns with name `p*`)
is inferred by
[`clue::cl_consensus()`](https://www.rdocumentation.org/link/cl_consensus?package=clue)
function with the `SE` method. Basically the value in the membership matrix
represents the probability to belong to a certain group. The finall subgroup
label for an item is determined with the group with highest probability it
belongs to.

In `get_classes()` function, the entropy is calculated from the membership
matrix and the silhouette score is calculated from the consensus matrix.



<script>
$( function() {
	$( '#tabs-node-021-get-classes' ).tabs();
} );
</script>
<div id='tabs-node-021-get-classes'>
<ul>
<li><a href='#tab-node-021-get-classes-1'>k = 2</a></li>
<li><a href='#tab-node-021-get-classes-2'>k = 3</a></li>
<li><a href='#tab-node-021-get-classes-3'>k = 4</a></li>
<li><a href='#tab-node-021-get-classes-4'>k = 5</a></li>
<li><a href='#tab-node-021-get-classes-5'>k = 6</a></li>
<li><a href='#tab-node-021-get-classes-6'>k = 7</a></li>
<li><a href='#tab-node-021-get-classes-7'>k = 8</a></li>
</ul>

<div id='tab-node-021-get-classes-1'>
<p><a id='tab-node-021-get-classes-1-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 2), get_membership(res, k = 2))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette p1 p2
#&gt; TCGA.AB.2995.03     1       0          1  1  0
#&gt; TCGA.AB.2883.03     2       0          1  0  1
#&gt; TCGA.AB.2830.03     1       0          1  1  0
#&gt; TCGA.AB.2941.03     2       0          1  0  1
#&gt; TCGA.AB.2987.03     2       0          1  0  1
#&gt; TCGA.AB.2971.03     1       0          1  1  0
#&gt; TCGA.AB.2873.03     1       0          1  1  0
#&gt; TCGA.AB.2833.03     2       0          1  0  1
#&gt; TCGA.AB.2898.03     1       0          1  1  0
#&gt; TCGA.AB.2968.03     2       0          1  0  1
#&gt; TCGA.AB.2910.03     2       0          1  0  1
#&gt; TCGA.AB.2934.03     1       0          1  1  0
#&gt; TCGA.AB.2832.03     2       0          1  0  1
#&gt; TCGA.AB.2893.03     2       0          1  0  1
#&gt; TCGA.AB.2956.03     2       0          1  0  1
#&gt; TCGA.AB.3005.03     2       0          1  0  1
#&gt; TCGA.AB.2861.03     2       0          1  0  1
#&gt; TCGA.AB.2829.03     1       0          1  1  0
#&gt; TCGA.AB.2928.03     1       0          1  1  0
#&gt; TCGA.AB.2916.03     2       0          1  0  1
#&gt; TCGA.AB.2978.03     1       0          1  1  0
#&gt; TCGA.AB.2938.03     1       0          1  1  0
#&gt; TCGA.AB.2887.03     1       0          1  1  0
#&gt; TCGA.AB.2894.03     2       0          1  0  1
#&gt; TCGA.AB.2831.03     1       0          1  1  0
#&gt; TCGA.AB.2975.03     1       0          1  1  0
</code></pre>

<script>
$('#tab-node-021-get-classes-1-a').parent().next().next().hide();
$('#tab-node-021-get-classes-1-a').click(function(){
  $('#tab-node-021-get-classes-1-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-021-get-classes-2'>
<p><a id='tab-node-021-get-classes-2-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 3), get_membership(res, k = 3))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3
#&gt; TCGA.AB.2995.03     3  0.0892      0.959 0.02 0.00 0.98
#&gt; TCGA.AB.2883.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2830.03     1  0.1529      0.982 0.96 0.00 0.04
#&gt; TCGA.AB.2941.03     3  0.1529      0.969 0.00 0.04 0.96
#&gt; TCGA.AB.2987.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2971.03     1  0.1529      0.982 0.96 0.00 0.04
#&gt; TCGA.AB.2873.03     3  0.0892      0.959 0.02 0.00 0.98
#&gt; TCGA.AB.2833.03     3  0.1529      0.969 0.00 0.04 0.96
#&gt; TCGA.AB.2898.03     1  0.0000      0.977 1.00 0.00 0.00
#&gt; TCGA.AB.2968.03     3  0.1529      0.969 0.00 0.04 0.96
#&gt; TCGA.AB.2910.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2934.03     1  0.0000      0.977 1.00 0.00 0.00
#&gt; TCGA.AB.2832.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2893.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2956.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.3005.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2861.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2829.03     3  0.0000      0.967 0.00 0.00 1.00
#&gt; TCGA.AB.2928.03     1  0.0000      0.977 1.00 0.00 0.00
#&gt; TCGA.AB.2916.03     3  0.1529      0.969 0.00 0.04 0.96
#&gt; TCGA.AB.2978.03     1  0.1529      0.982 0.96 0.00 0.04
#&gt; TCGA.AB.2938.03     3  0.0000      0.967 0.00 0.00 1.00
#&gt; TCGA.AB.2887.03     1  0.0000      0.977 1.00 0.00 0.00
#&gt; TCGA.AB.2894.03     2  0.0000      1.000 0.00 1.00 0.00
#&gt; TCGA.AB.2831.03     1  0.1529      0.982 0.96 0.00 0.04
#&gt; TCGA.AB.2975.03     1  0.1529      0.982 0.96 0.00 0.04
</code></pre>

<script>
$('#tab-node-021-get-classes-2-a').parent().next().next().hide();
$('#tab-node-021-get-classes-2-a').click(function(){
  $('#tab-node-021-get-classes-2-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-021-get-classes-3'>
<p><a id='tab-node-021-get-classes-3-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 4), get_membership(res, k = 4))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4
#&gt; TCGA.AB.2995.03     3   0.517      0.691 0.02 0.00 0.66 0.32
#&gt; TCGA.AB.2883.03     2   0.000      0.954 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2830.03     1   0.630      0.661 0.60 0.00 0.08 0.32
#&gt; TCGA.AB.2941.03     4   0.498      1.000 0.00 0.00 0.46 0.54
#&gt; TCGA.AB.2987.03     2   0.317      0.893 0.00 0.84 0.00 0.16
#&gt; TCGA.AB.2971.03     1   0.630      0.661 0.60 0.00 0.08 0.32
#&gt; TCGA.AB.2873.03     3   0.517      0.691 0.02 0.00 0.66 0.32
#&gt; TCGA.AB.2833.03     4   0.498      1.000 0.00 0.00 0.46 0.54
#&gt; TCGA.AB.2898.03     1   0.000      0.724 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2968.03     4   0.498      1.000 0.00 0.00 0.46 0.54
#&gt; TCGA.AB.2910.03     2   0.292      0.905 0.00 0.86 0.00 0.14
#&gt; TCGA.AB.2934.03     1   0.000      0.724 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2832.03     2   0.000      0.954 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2893.03     2   0.000      0.954 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2956.03     2   0.000      0.954 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.3005.03     2   0.000      0.954 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2861.03     2   0.000      0.954 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2829.03     3   0.000      0.380 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2928.03     1   0.000      0.724 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2916.03     4   0.498      1.000 0.00 0.00 0.46 0.54
#&gt; TCGA.AB.2978.03     1   0.630      0.661 0.60 0.00 0.08 0.32
#&gt; TCGA.AB.2938.03     3   0.000      0.380 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2887.03     1   0.000      0.724 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2894.03     2   0.292      0.905 0.00 0.86 0.00 0.14
#&gt; TCGA.AB.2831.03     3   0.702      0.489 0.14 0.00 0.54 0.32
#&gt; TCGA.AB.2975.03     1   0.630      0.661 0.60 0.00 0.08 0.32
</code></pre>

<script>
$('#tab-node-021-get-classes-3-a').parent().next().next().hide();
$('#tab-node-021-get-classes-3-a').click(function(){
  $('#tab-node-021-get-classes-3-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-021-get-classes-4'>
<p><a id='tab-node-021-get-classes-4-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 5), get_membership(res, k = 5))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5
#&gt; TCGA.AB.2995.03     3   0.598      0.916 0.12 0.00 0.52 0.00 0.36
#&gt; TCGA.AB.2883.03     2   0.418      0.858 0.00 0.60 0.40 0.00 0.00
#&gt; TCGA.AB.2830.03     1   0.000      0.510 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2941.03     4   0.275      0.879 0.00 0.00 0.08 0.88 0.04
#&gt; TCGA.AB.2987.03     2   0.104      0.644 0.00 0.96 0.00 0.04 0.00
#&gt; TCGA.AB.2971.03     1   0.000      0.510 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2873.03     3   0.598      0.916 0.12 0.00 0.52 0.00 0.36
#&gt; TCGA.AB.2833.03     4   0.202      0.906 0.00 0.00 0.00 0.90 0.10
#&gt; TCGA.AB.2898.03     1   0.431     -1.000 0.50 0.00 0.00 0.00 0.50
#&gt; TCGA.AB.2968.03     4   0.000      0.940 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2910.03     2   0.000      0.683 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2934.03     1   0.429     -0.877 0.54 0.00 0.00 0.00 0.46
#&gt; TCGA.AB.2832.03     2   0.418      0.858 0.00 0.60 0.40 0.00 0.00
#&gt; TCGA.AB.2893.03     2   0.418      0.858 0.00 0.60 0.40 0.00 0.00
#&gt; TCGA.AB.2956.03     2   0.418      0.858 0.00 0.60 0.40 0.00 0.00
#&gt; TCGA.AB.3005.03     2   0.418      0.858 0.00 0.60 0.40 0.00 0.00
#&gt; TCGA.AB.2861.03     2   0.418      0.858 0.00 0.60 0.40 0.00 0.00
#&gt; TCGA.AB.2829.03     3   0.509      0.866 0.00 0.00 0.56 0.04 0.40
#&gt; TCGA.AB.2928.03     1   0.431     -1.000 0.50 0.00 0.00 0.00 0.50
#&gt; TCGA.AB.2916.03     4   0.000      0.940 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2978.03     1   0.000      0.510 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2938.03     3   0.509      0.866 0.00 0.00 0.56 0.04 0.40
#&gt; TCGA.AB.2887.03     5   0.431      0.000 0.50 0.00 0.00 0.00 0.50
#&gt; TCGA.AB.2894.03     2   0.000      0.683 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2831.03     3   0.598      0.916 0.12 0.00 0.52 0.00 0.36
#&gt; TCGA.AB.2975.03     1   0.000      0.510 1.00 0.00 0.00 0.00 0.00
</code></pre>

<script>
$('#tab-node-021-get-classes-4-a').parent().next().next().hide();
$('#tab-node-021-get-classes-4-a').click(function(){
  $('#tab-node-021-get-classes-4-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-021-get-classes-5'>
<p><a id='tab-node-021-get-classes-5-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 6), get_membership(res, k = 6))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5   p6
#&gt; TCGA.AB.2995.03     3  0.0547      0.941 0.02 0.00 0.98 0.00 0.00 0.00
#&gt; TCGA.AB.2883.03     2  0.3797      0.975 0.00 0.58 0.00 0.00 0.00 0.42
#&gt; TCGA.AB.2830.03     1  0.4348      0.975 0.64 0.00 0.04 0.00 0.32 0.00
#&gt; TCGA.AB.2941.03     4  0.2345      0.798 0.02 0.06 0.02 0.90 0.00 0.00
#&gt; TCGA.AB.2987.03     6  0.1267      0.871 0.00 0.00 0.00 0.06 0.00 0.94
#&gt; TCGA.AB.2971.03     1  0.4348      0.975 0.64 0.00 0.04 0.00 0.32 0.00
#&gt; TCGA.AB.2873.03     3  0.1807      0.916 0.02 0.06 0.92 0.00 0.00 0.00
#&gt; TCGA.AB.2833.03     4  0.5747      0.562 0.30 0.20 0.00 0.50 0.00 0.00
#&gt; TCGA.AB.2898.03     5  0.0000      0.950 0.00 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2968.03     4  0.0000      0.838 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2910.03     6  0.0937      0.895 0.04 0.00 0.00 0.00 0.00 0.96
#&gt; TCGA.AB.2934.03     5  0.2474      0.832 0.08 0.04 0.00 0.00 0.88 0.00
#&gt; TCGA.AB.2832.03     2  0.3797      0.975 0.00 0.58 0.00 0.00 0.00 0.42
#&gt; TCGA.AB.2893.03     2  0.4609      0.950 0.04 0.54 0.00 0.00 0.00 0.42
#&gt; TCGA.AB.2956.03     2  0.4609      0.950 0.04 0.54 0.00 0.00 0.00 0.42
#&gt; TCGA.AB.3005.03     2  0.3797      0.975 0.00 0.58 0.00 0.00 0.00 0.42
#&gt; TCGA.AB.2861.03     2  0.3797      0.975 0.00 0.58 0.00 0.00 0.00 0.42
#&gt; TCGA.AB.2829.03     3  0.1807      0.923 0.02 0.06 0.92 0.00 0.00 0.00
#&gt; TCGA.AB.2928.03     5  0.0000      0.950 0.00 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2916.03     4  0.0000      0.838 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2978.03     1  0.4348      0.975 0.64 0.00 0.04 0.00 0.32 0.00
#&gt; TCGA.AB.2938.03     3  0.1807      0.923 0.02 0.06 0.92 0.00 0.00 0.00
#&gt; TCGA.AB.2887.03     5  0.0000      0.950 0.00 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2894.03     6  0.0000      0.912 0.00 0.00 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2831.03     3  0.0547      0.941 0.02 0.00 0.98 0.00 0.00 0.00
#&gt; TCGA.AB.2975.03     1  0.5459      0.924 0.58 0.06 0.04 0.00 0.32 0.00
</code></pre>

<script>
$('#tab-node-021-get-classes-5-a').parent().next().next().hide();
$('#tab-node-021-get-classes-5-a').click(function(){
  $('#tab-node-021-get-classes-5-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-021-get-classes-6'>
<p><a id='tab-node-021-get-classes-6-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 7), get_membership(res, k = 7))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5   p6   p7
#&gt; TCGA.AB.2995.03     3  0.0000      0.854 0.00 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2883.03     2  0.0000      0.981 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2830.03     1  0.0000      0.927 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2941.03     4  0.3991      0.626 0.00 0.00 0.00 0.72 0.04 0.02 0.22
#&gt; TCGA.AB.2987.03     6  0.3186      0.952 0.00 0.22 0.00 0.02 0.00 0.76 0.00
#&gt; TCGA.AB.2971.03     1  0.0504      0.920 0.98 0.00 0.00 0.00 0.00 0.02 0.00
#&gt; TCGA.AB.2873.03     3  0.2213      0.803 0.00 0.00 0.90 0.04 0.02 0.04 0.00
#&gt; TCGA.AB.2833.03     7  0.0000      0.000 0.00 0.00 0.00 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2898.03     5  0.2259      0.903 0.16 0.00 0.00 0.00 0.84 0.00 0.00
#&gt; TCGA.AB.2968.03     4  0.3413      0.806 0.00 0.00 0.00 0.62 0.00 0.00 0.38
#&gt; TCGA.AB.2910.03     6  0.3637      0.948 0.00 0.24 0.00 0.00 0.04 0.72 0.00
#&gt; TCGA.AB.2934.03     5  0.5277      0.640 0.32 0.00 0.00 0.06 0.56 0.06 0.00
#&gt; TCGA.AB.2832.03     2  0.0000      0.981 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2893.03     2  0.0863      0.962 0.00 0.96 0.00 0.00 0.04 0.00 0.00
#&gt; TCGA.AB.2956.03     2  0.0863      0.962 0.00 0.96 0.00 0.00 0.04 0.00 0.00
#&gt; TCGA.AB.3005.03     2  0.0000      0.981 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2861.03     2  0.0000      0.981 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2829.03     3  0.3848      0.801 0.00 0.00 0.76 0.16 0.06 0.02 0.00
#&gt; TCGA.AB.2928.03     5  0.2259      0.903 0.16 0.00 0.00 0.00 0.84 0.00 0.00
#&gt; TCGA.AB.2916.03     4  0.3413      0.806 0.00 0.00 0.00 0.62 0.00 0.00 0.38
#&gt; TCGA.AB.2978.03     1  0.0000      0.927 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2938.03     3  0.3848      0.801 0.00 0.00 0.76 0.16 0.06 0.02 0.00
#&gt; TCGA.AB.2887.03     5  0.2259      0.903 0.16 0.00 0.00 0.00 0.84 0.00 0.00
#&gt; TCGA.AB.2894.03     6  0.2832      0.963 0.00 0.24 0.00 0.00 0.00 0.76 0.00
#&gt; TCGA.AB.2831.03     3  0.0000      0.854 0.00 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2975.03     1  0.3263      0.793 0.80 0.00 0.00 0.12 0.00 0.08 0.00
</code></pre>

<script>
$('#tab-node-021-get-classes-6-a').parent().next().next().hide();
$('#tab-node-021-get-classes-6-a').click(function(){
  $('#tab-node-021-get-classes-6-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-021-get-classes-7'>
<p><a id='tab-node-021-get-classes-7-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 8), get_membership(res, k = 8))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5   p6   p7   p8
#&gt; TCGA.AB.2995.03     3   0.000      0.786 0.00 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2883.03     2   0.000      0.935 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2830.03     8   0.000      0.976 0.00 0.00 0.00 0.00 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2941.03     4   0.301      0.566 0.32 0.00 0.00 0.68 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2987.03     6   0.449      0.742 0.18 0.06 0.00 0.00 0.04 0.70 0.02 0.00
#&gt; TCGA.AB.2971.03     8   0.000      0.976 0.00 0.00 0.00 0.00 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2873.03     3   0.332      0.704 0.02 0.00 0.82 0.00 0.02 0.06 0.08 0.00
#&gt; TCGA.AB.2833.03     7   0.276      0.000 0.00 0.00 0.00 0.26 0.00 0.00 0.74 0.00
#&gt; TCGA.AB.2898.03     5   0.235      0.875 0.00 0.00 0.00 0.00 0.86 0.00 0.04 0.10
#&gt; TCGA.AB.2968.03     4   0.000      0.784 0.00 0.00 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2910.03     6   0.202      0.849 0.02 0.06 0.00 0.00 0.00 0.90 0.02 0.00
#&gt; TCGA.AB.2934.03     5   0.527      0.646 0.22 0.00 0.00 0.00 0.56 0.00 0.04 0.18
#&gt; TCGA.AB.2832.03     2   0.000      0.935 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2893.03     2   0.207      0.888 0.02 0.90 0.00 0.00 0.04 0.00 0.04 0.00
#&gt; TCGA.AB.2956.03     2   0.378      0.738 0.02 0.76 0.00 0.00 0.04 0.16 0.02 0.00
#&gt; TCGA.AB.3005.03     2   0.000      0.935 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2861.03     2   0.000      0.935 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2829.03     3   0.308      0.718 0.34 0.00 0.66 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2928.03     5   0.156      0.883 0.00 0.00 0.00 0.00 0.90 0.00 0.00 0.10
#&gt; TCGA.AB.2916.03     4   0.000      0.784 0.00 0.00 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2978.03     8   0.000      0.976 0.00 0.00 0.00 0.00 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2938.03     3   0.308      0.718 0.34 0.00 0.66 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2887.03     5   0.156      0.883 0.00 0.00 0.00 0.00 0.90 0.00 0.00 0.10
#&gt; TCGA.AB.2894.03     6   0.109      0.861 0.00 0.06 0.00 0.00 0.00 0.94 0.00 0.00
#&gt; TCGA.AB.2831.03     3   0.000      0.786 0.00 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2975.03     8   0.161      0.924 0.04 0.00 0.00 0.00 0.00 0.00 0.04 0.92
</code></pre>

<script>
$('#tab-node-021-get-classes-7-a').parent().next().next().hide();
$('#tab-node-021-get-classes-7-a').click(function(){
  $('#tab-node-021-get-classes-7-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>
</div>

Heatmaps for the consensus matrix. It visualizes the probability of two
samples to be in a same group.




<script>
$( function() {
	$( '#tabs-node-021-consensus-heatmap' ).tabs();
} );
</script>
<div id='tabs-node-021-consensus-heatmap'>
<ul>
<li><a href='#tab-node-021-consensus-heatmap-1'>k = 2</a></li>
<li><a href='#tab-node-021-consensus-heatmap-2'>k = 3</a></li>
<li><a href='#tab-node-021-consensus-heatmap-3'>k = 4</a></li>
<li><a href='#tab-node-021-consensus-heatmap-4'>k = 5</a></li>
<li><a href='#tab-node-021-consensus-heatmap-5'>k = 6</a></li>
<li><a href='#tab-node-021-consensus-heatmap-6'>k = 7</a></li>
<li><a href='#tab-node-021-consensus-heatmap-7'>k = 8</a></li>
</ul>
<div id='tab-node-021-consensus-heatmap-1'>
<pre><code class="r">consensus_heatmap(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-021-consensus-heatmap-1-1.png" alt="plot of chunk tab-node-021-consensus-heatmap-1"/></p>

</div>
<div id='tab-node-021-consensus-heatmap-2'>
<pre><code class="r">consensus_heatmap(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-021-consensus-heatmap-2-1.png" alt="plot of chunk tab-node-021-consensus-heatmap-2"/></p>

</div>
<div id='tab-node-021-consensus-heatmap-3'>
<pre><code class="r">consensus_heatmap(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-021-consensus-heatmap-3-1.png" alt="plot of chunk tab-node-021-consensus-heatmap-3"/></p>

</div>
<div id='tab-node-021-consensus-heatmap-4'>
<pre><code class="r">consensus_heatmap(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-021-consensus-heatmap-4-1.png" alt="plot of chunk tab-node-021-consensus-heatmap-4"/></p>

</div>
<div id='tab-node-021-consensus-heatmap-5'>
<pre><code class="r">consensus_heatmap(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-021-consensus-heatmap-5-1.png" alt="plot of chunk tab-node-021-consensus-heatmap-5"/></p>

</div>
<div id='tab-node-021-consensus-heatmap-6'>
<pre><code class="r">consensus_heatmap(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-021-consensus-heatmap-6-1.png" alt="plot of chunk tab-node-021-consensus-heatmap-6"/></p>

</div>
<div id='tab-node-021-consensus-heatmap-7'>
<pre><code class="r">consensus_heatmap(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-021-consensus-heatmap-7-1.png" alt="plot of chunk tab-node-021-consensus-heatmap-7"/></p>

</div>
</div>

Heatmaps for the membership of samples in all partitions to see how consistent they are:





<script>
$( function() {
	$( '#tabs-node-021-membership-heatmap' ).tabs();
} );
</script>
<div id='tabs-node-021-membership-heatmap'>
<ul>
<li><a href='#tab-node-021-membership-heatmap-1'>k = 2</a></li>
<li><a href='#tab-node-021-membership-heatmap-2'>k = 3</a></li>
<li><a href='#tab-node-021-membership-heatmap-3'>k = 4</a></li>
<li><a href='#tab-node-021-membership-heatmap-4'>k = 5</a></li>
<li><a href='#tab-node-021-membership-heatmap-5'>k = 6</a></li>
<li><a href='#tab-node-021-membership-heatmap-6'>k = 7</a></li>
<li><a href='#tab-node-021-membership-heatmap-7'>k = 8</a></li>
</ul>
<div id='tab-node-021-membership-heatmap-1'>
<pre><code class="r">membership_heatmap(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-021-membership-heatmap-1-1.png" alt="plot of chunk tab-node-021-membership-heatmap-1"/></p>

</div>
<div id='tab-node-021-membership-heatmap-2'>
<pre><code class="r">membership_heatmap(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-021-membership-heatmap-2-1.png" alt="plot of chunk tab-node-021-membership-heatmap-2"/></p>

</div>
<div id='tab-node-021-membership-heatmap-3'>
<pre><code class="r">membership_heatmap(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-021-membership-heatmap-3-1.png" alt="plot of chunk tab-node-021-membership-heatmap-3"/></p>

</div>
<div id='tab-node-021-membership-heatmap-4'>
<pre><code class="r">membership_heatmap(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-021-membership-heatmap-4-1.png" alt="plot of chunk tab-node-021-membership-heatmap-4"/></p>

</div>
<div id='tab-node-021-membership-heatmap-5'>
<pre><code class="r">membership_heatmap(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-021-membership-heatmap-5-1.png" alt="plot of chunk tab-node-021-membership-heatmap-5"/></p>

</div>
<div id='tab-node-021-membership-heatmap-6'>
<pre><code class="r">membership_heatmap(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-021-membership-heatmap-6-1.png" alt="plot of chunk tab-node-021-membership-heatmap-6"/></p>

</div>
<div id='tab-node-021-membership-heatmap-7'>
<pre><code class="r">membership_heatmap(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-021-membership-heatmap-7-1.png" alt="plot of chunk tab-node-021-membership-heatmap-7"/></p>

</div>
</div>

As soon as the classes for columns are determined, the signatures
that are significantly different between subgroups can be looked for. 
Following are the heatmaps for signatures.






<script>
$( function() {
	$( '#tabs-node-021-get-signatures' ).tabs();
} );
</script>
<div id='tabs-node-021-get-signatures'>
<ul>
<li><a href='#tab-node-021-get-signatures-1'>k = 2</a></li>
<li><a href='#tab-node-021-get-signatures-2'>k = 3</a></li>
<li><a href='#tab-node-021-get-signatures-3'>k = 4</a></li>
<li><a href='#tab-node-021-get-signatures-4'>k = 5</a></li>
<li><a href='#tab-node-021-get-signatures-5'>k = 6</a></li>
<li><a href='#tab-node-021-get-signatures-6'>k = 7</a></li>
<li><a href='#tab-node-021-get-signatures-7'>k = 8</a></li>
</ul>
<div id='tab-node-021-get-signatures-1'>
<pre><code class="r">get_signatures(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-021-get-signatures-1-1.png" alt="plot of chunk tab-node-021-get-signatures-1"/></p>

</div>
<div id='tab-node-021-get-signatures-2'>
<pre><code class="r">get_signatures(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-021-get-signatures-2-1.png" alt="plot of chunk tab-node-021-get-signatures-2"/></p>

</div>
<div id='tab-node-021-get-signatures-3'>
<pre><code class="r">get_signatures(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-021-get-signatures-3-1.png" alt="plot of chunk tab-node-021-get-signatures-3"/></p>

</div>
<div id='tab-node-021-get-signatures-4'>
<pre><code class="r">get_signatures(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-021-get-signatures-4-1.png" alt="plot of chunk tab-node-021-get-signatures-4"/></p>

</div>
<div id='tab-node-021-get-signatures-5'>
<pre><code class="r">get_signatures(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-021-get-signatures-5-1.png" alt="plot of chunk tab-node-021-get-signatures-5"/></p>

</div>
<div id='tab-node-021-get-signatures-6'>
<pre><code class="r">get_signatures(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-021-get-signatures-6-1.png" alt="plot of chunk tab-node-021-get-signatures-6"/></p>

</div>
<div id='tab-node-021-get-signatures-7'>
<pre><code class="r">get_signatures(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-021-get-signatures-7-1.png" alt="plot of chunk tab-node-021-get-signatures-7"/></p>

</div>
</div>



Compare the overlap of signatures from different k:

```r
compare_signatures(res)
```

![plot of chunk node-021-signature_compare](figure_cola/node-021-signature_compare-1.png)

`get_signature()` returns a data frame invisibly. To get the list of signatures, the function
call should be assigned to a variable explicitly. In following code, if `plot` argument is set
to `FALSE`, no heatmap is plotted while only the differential analysis is performed.

```r
# code only for demonstration
tb = get_signature(res, k = ..., plot = FALSE)
```

An example of the output of `tb` is:

```
#>   which_row         fdr    mean_1    mean_2 scaled_mean_1 scaled_mean_2 km
#> 1        38 0.042760348  8.373488  9.131774    -0.5533452     0.5164555  1
#> 2        40 0.018707592  7.106213  8.469186    -0.6173731     0.5762149  1
#> 3        55 0.019134737 10.221463 11.207825    -0.6159697     0.5749050  1
#> 4        59 0.006059896  5.921854  7.869574    -0.6899429     0.6439467  1
#> 5        60 0.018055526  8.928898 10.211722    -0.6204761     0.5791110  1
#> 6        98 0.009384629 15.714769 14.887706     0.6635654    -0.6193277  2
...
```

The columns in `tb` are:

1. `which_row`: row indices corresponding to the input matrix.
2. `fdr`: FDR for the differential test. 
3. `mean_x`: The mean value in group x.
4. `scaled_mean_x`: The mean value in group x after rows are scaled.
5. `km`: Row groups if k-means clustering is applied to rows (which is done by automatically selecting number of clusters).

If there are too many signatures, `top_signatures = ...` can be set to only show the 
signatures with the highest FDRs:

```r
# code only for demonstration
# e.g. to show the top 500 most significant rows
tb = get_signature(res, k = ..., top_signatures = 500)
```

If the signatures are defined as these which are uniquely high in current group, `diff_method` argument
can be set to `"uniquely_high_in_one_group"`:

```r
# code only for demonstration
tb = get_signature(res, k = ..., diff_method = "uniquely_high_in_one_group")
```




UMAP plot which shows how samples are separated.


<script>
$( function() {
	$( '#tabs-node-021-dimension-reduction' ).tabs();
} );
</script>
<div id='tabs-node-021-dimension-reduction'>
<ul>
<li><a href='#tab-node-021-dimension-reduction-1'>k = 2</a></li>
<li><a href='#tab-node-021-dimension-reduction-2'>k = 3</a></li>
<li><a href='#tab-node-021-dimension-reduction-3'>k = 4</a></li>
<li><a href='#tab-node-021-dimension-reduction-4'>k = 5</a></li>
<li><a href='#tab-node-021-dimension-reduction-5'>k = 6</a></li>
<li><a href='#tab-node-021-dimension-reduction-6'>k = 7</a></li>
<li><a href='#tab-node-021-dimension-reduction-7'>k = 8</a></li>
</ul>
<div id='tab-node-021-dimension-reduction-1'>
<pre><code class="r">dimension_reduction(res, k = 2, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-021-dimension-reduction-1-1.png" alt="plot of chunk tab-node-021-dimension-reduction-1"/></p>

</div>
<div id='tab-node-021-dimension-reduction-2'>
<pre><code class="r">dimension_reduction(res, k = 3, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-021-dimension-reduction-2-1.png" alt="plot of chunk tab-node-021-dimension-reduction-2"/></p>

</div>
<div id='tab-node-021-dimension-reduction-3'>
<pre><code class="r">dimension_reduction(res, k = 4, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-021-dimension-reduction-3-1.png" alt="plot of chunk tab-node-021-dimension-reduction-3"/></p>

</div>
<div id='tab-node-021-dimension-reduction-4'>
<pre><code class="r">dimension_reduction(res, k = 5, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-021-dimension-reduction-4-1.png" alt="plot of chunk tab-node-021-dimension-reduction-4"/></p>

</div>
<div id='tab-node-021-dimension-reduction-5'>
<pre><code class="r">dimension_reduction(res, k = 6, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-021-dimension-reduction-5-1.png" alt="plot of chunk tab-node-021-dimension-reduction-5"/></p>

</div>
<div id='tab-node-021-dimension-reduction-6'>
<pre><code class="r">dimension_reduction(res, k = 7, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-021-dimension-reduction-6-1.png" alt="plot of chunk tab-node-021-dimension-reduction-6"/></p>

</div>
<div id='tab-node-021-dimension-reduction-7'>
<pre><code class="r">dimension_reduction(res, k = 8, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-021-dimension-reduction-7-1.png" alt="plot of chunk tab-node-021-dimension-reduction-7"/></p>

</div>
</div>



Following heatmap shows how subgroups are split when increasing `k`:

```r
collect_classes(res)
```

![plot of chunk node-021-collect-classes](figure_cola/node-021-collect-classes-1.png)



If matrix rows can be associated to genes, consider to use `functional_enrichment(res,
...)` to perform function enrichment for the signature genes. See [this vignette](https://jokergoo.github.io/cola_vignettes/functional_enrichment.html) for more detailed explanations.


 

---------------------------------------------------




### Node022


Parent node: [Node02](#Node02).
Child nodes: 
                Node0111-leaf
        ,
                Node0112-leaf
        ,
                Node0131-leaf
        ,
                Node0132-leaf
        ,
                Node0141-leaf
        ,
                Node0142-leaf
        ,
                Node0211-leaf
        ,
                Node0212-leaf
        ,
                Node0213-leaf
        ,
                Node0221-leaf
        ,
                [Node0222](#Node0222)
        ,
                Node0231-leaf
        ,
                Node0232-leaf
        ,
                Node0233-leaf
        ,
                Node0321-leaf
        ,
                Node0322-leaf
        ,
                Node0323-leaf
        ,
                Node0324-leaf
        ,
                Node0325-leaf
        ,
                Node0331-leaf
        ,
                Node0332-leaf
        .







The object with results only for a single top-value method and a single partitioning method 
can be extracted as:

```r
res = res_rh["022"]
```

A summary of `res` and all the functions that can be applied to it:

```r
res
```

```
#> A 'ConsensusPartition' object with k = 2, 3, 4, 5, 6, 7, 8.
#>   On a matrix with 30000 rows and 31 columns.
#>   Top rows (1000) are extracted by 'ATC' method.
#>   Subgroups are detected by 'kmeans' method.
#>   Performed in total 350 partitions by row resampling.
#>   Best k for subgroups seems to be 2.
#> 
#> Following methods can be applied to this 'ConsensusPartition' object:
#>  [1] "cola_report"             "collect_classes"         "collect_plots"          
#>  [4] "collect_stats"           "colnames"                "compare_partitions"     
#>  [7] "compare_signatures"      "consensus_heatmap"       "dimension_reduction"    
#> [10] "functional_enrichment"   "get_anno_col"            "get_anno"               
#> [13] "get_classes"             "get_consensus"           "get_matrix"             
#> [16] "get_membership"          "get_param"               "get_signatures"         
#> [19] "get_stats"               "is_best_k"               "is_stable_k"            
#> [22] "membership_heatmap"      "ncol"                    "nrow"                   
#> [25] "plot_ecdf"               "predict_classes"         "rownames"               
#> [28] "select_partition_number" "show"                    "suggest_best_k"         
#> [31] "test_to_known_factors"   "top_rows_heatmap"
```

`collect_plots()` function collects all the plots made from `res` for all `k` (number of subgroups)
into one single page to provide an easy and fast comparison between different `k`.

```r
collect_plots(res)
```

![plot of chunk node-022-collect-plots](figure_cola/node-022-collect-plots-1.png)

The plots are:

- The first row: a plot of the eCDF (empirical cumulative distribution
  function) curves of the consensus matrix for each `k` and the heatmap of
  predicted classes for each `k`.
- The second row: heatmaps of the consensus matrix for each `k`.
- The third row: heatmaps of the membership matrix for each `k`.
- The fouth row: heatmaps of the signatures for each `k`.

All the plots in panels can be made by individual functions and they are
plotted later in this section.

`select_partition_number()` produces several plots showing different
statistics for choosing "optimized" `k`. There are following statistics:

- eCDF curves of the consensus matrix for each `k`;
- 1-PAC. [The PAC score](https://en.wikipedia.org/wiki/Consensus_clustering#Over-interpretation_potential_of_consensus_clustering)
  measures the proportion of the ambiguous subgrouping.
- Mean silhouette score.
- Concordance. The mean probability of fiting the consensus subgroup labels in all
  partitions.
- Area increased. Denote $A_k$ as the area under the eCDF curve for current
  `k`, the area increased is defined as $A_k - A_{k-1}$.
- Rand index. The percent of pairs of samples that are both in a same cluster
  or both are not in a same cluster in the partition of k and k-1.
- Jaccard index. The ratio of pairs of samples are both in a same cluster in
  the partition of k and k-1 and the pairs of samples are both in a same
  cluster in the partition k or k-1.

The detailed explanations of these statistics can be found in [the _cola_
vignette](https://jokergoo.github.io/cola_vignettes/cola.html#toc_13).

Generally speaking, higher 1-PAC score, higher mean silhouette score or higher
concordance corresponds to better partition. Rand index and Jaccard index
measure how similar the current partition is compared to partition with `k-1`.
If they are too similar, we won't accept `k` is better than `k-1`.

```r
select_partition_number(res)
```

![plot of chunk node-022-select-partition-number](figure_cola/node-022-select-partition-number-1.png)

The numeric values for all these statistics can be obtained by `get_stats()`.

```r
get_stats(res)
```

```
#>   k 1-PAC mean_silhouette concordance area_increased  Rand Jaccard
#> 2 2 1.000           1.000       1.000         0.5123 0.488   0.488
#> 3 3 0.680           0.718       0.863         0.2881 0.798   0.607
#> 4 4 0.695           0.655       0.717         0.1126 0.862   0.626
#> 5 5 0.788           0.783       0.845         0.0697 0.882   0.583
#> 6 6 0.768           0.759       0.862         0.0515 0.948   0.747
#> 7 7 0.835           0.686       0.777         0.0276 0.953   0.747
#> 8 8 0.840           0.674       0.810         0.0242 0.946   0.709
```

`suggest_best_k()` suggests the best $k$ based on these statistics. The rules are as follows:

- All $k$ with Jaccard index larger than 0.95 are removed because increasing
  $k$ does not provide enough extra information. If all $k$ are removed, it is
  marked as no subgroup is detected.
- For all $k$ with 1-PAC score larger than 0.9, the maximal $k$ is taken as
  the best $k$, and other $k$ are marked as optional $k$.
- If it does not fit the second rule. The $k$ with the maximal vote of the
  highest 1-PAC score, highest mean silhouette, and highest concordance is
  taken as the best $k$.

```r
suggest_best_k(res)
```

```
#> [1] 2
```


Following is the table of the partitions (You need to click the **show/hide
code output** link to see it). The membership matrix (columns with name `p*`)
is inferred by
[`clue::cl_consensus()`](https://www.rdocumentation.org/link/cl_consensus?package=clue)
function with the `SE` method. Basically the value in the membership matrix
represents the probability to belong to a certain group. The finall subgroup
label for an item is determined with the group with highest probability it
belongs to.

In `get_classes()` function, the entropy is calculated from the membership
matrix and the silhouette score is calculated from the consensus matrix.



<script>
$( function() {
	$( '#tabs-node-022-get-classes' ).tabs();
} );
</script>
<div id='tabs-node-022-get-classes'>
<ul>
<li><a href='#tab-node-022-get-classes-1'>k = 2</a></li>
<li><a href='#tab-node-022-get-classes-2'>k = 3</a></li>
<li><a href='#tab-node-022-get-classes-3'>k = 4</a></li>
<li><a href='#tab-node-022-get-classes-4'>k = 5</a></li>
<li><a href='#tab-node-022-get-classes-5'>k = 6</a></li>
<li><a href='#tab-node-022-get-classes-6'>k = 7</a></li>
<li><a href='#tab-node-022-get-classes-7'>k = 8</a></li>
</ul>

<div id='tab-node-022-get-classes-1'>
<p><a id='tab-node-022-get-classes-1-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 2), get_membership(res, k = 2))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette p1 p2
#&gt; TCGA.AB.2984.03     1       0          1  1  0
#&gt; TCGA.AB.2874.03     1       0          1  1  0
#&gt; TCGA.AB.2866.03     1       0          1  1  0
#&gt; TCGA.AB.2959.03     2       0          1  0  1
#&gt; TCGA.AB.2871.03     2       0          1  0  1
#&gt; TCGA.AB.2907.03     2       0          1  0  1
#&gt; TCGA.AB.2867.03     2       0          1  0  1
#&gt; TCGA.AB.2822.03     2       0          1  0  1
#&gt; TCGA.AB.2903.03     2       0          1  0  1
#&gt; TCGA.AB.2948.03     2       0          1  0  1
#&gt; TCGA.AB.2964.03     2       0          1  0  1
#&gt; TCGA.AB.2805.03     2       0          1  0  1
#&gt; TCGA.AB.2990.03     1       0          1  1  0
#&gt; TCGA.AB.3002.03     1       0          1  1  0
#&gt; TCGA.AB.2877.03     1       0          1  1  0
#&gt; TCGA.AB.2992.03     2       0          1  0  1
#&gt; TCGA.AB.2919.03     1       0          1  1  0
#&gt; TCGA.AB.2996.03     2       0          1  0  1
#&gt; TCGA.AB.2936.03     2       0          1  0  1
#&gt; TCGA.AB.2900.03     1       0          1  1  0
#&gt; TCGA.AB.2926.03     1       0          1  1  0
#&gt; TCGA.AB.2977.03     1       0          1  1  0
#&gt; TCGA.AB.2821.03     2       0          1  0  1
#&gt; TCGA.AB.2863.03     2       0          1  0  1
#&gt; TCGA.AB.2855.03     1       0          1  1  0
#&gt; TCGA.AB.2923.03     2       0          1  0  1
#&gt; TCGA.AB.2834.03     1       0          1  1  0
#&gt; TCGA.AB.2826.03     1       0          1  1  0
#&gt; TCGA.AB.2810.03     1       0          1  1  0
#&gt; TCGA.AB.2901.03     2       0          1  0  1
#&gt; TCGA.AB.2854.03     2       0          1  0  1
</code></pre>

<script>
$('#tab-node-022-get-classes-1-a').parent().next().next().hide();
$('#tab-node-022-get-classes-1-a').click(function(){
  $('#tab-node-022-get-classes-1-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-022-get-classes-2'>
<p><a id='tab-node-022-get-classes-2-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 3), get_membership(res, k = 3))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3
#&gt; TCGA.AB.2984.03     1  0.0000      0.887 1.00 0.00 0.00
#&gt; TCGA.AB.2874.03     3  0.6309      0.249 0.50 0.00 0.50
#&gt; TCGA.AB.2866.03     1  0.0000      0.887 1.00 0.00 0.00
#&gt; TCGA.AB.2959.03     2  0.5706      0.420 0.00 0.68 0.32
#&gt; TCGA.AB.2871.03     2  0.0000      0.842 0.00 1.00 0.00
#&gt; TCGA.AB.2907.03     2  0.0000      0.842 0.00 1.00 0.00
#&gt; TCGA.AB.2867.03     2  0.4796      0.859 0.00 0.78 0.22
#&gt; TCGA.AB.2822.03     2  0.4796      0.859 0.00 0.78 0.22
#&gt; TCGA.AB.2903.03     3  0.4796      0.627 0.00 0.22 0.78
#&gt; TCGA.AB.2948.03     2  0.4796      0.859 0.00 0.78 0.22
#&gt; TCGA.AB.2964.03     2  0.0892      0.829 0.00 0.98 0.02
#&gt; TCGA.AB.2805.03     2  0.0000      0.842 0.00 1.00 0.00
#&gt; TCGA.AB.2990.03     1  0.0000      0.887 1.00 0.00 0.00
#&gt; TCGA.AB.3002.03     3  0.4796      0.561 0.22 0.00 0.78
#&gt; TCGA.AB.2877.03     1  0.0000      0.887 1.00 0.00 0.00
#&gt; TCGA.AB.2992.03     2  0.4796      0.859 0.00 0.78 0.22
#&gt; TCGA.AB.2919.03     1  0.5948      0.156 0.64 0.00 0.36
#&gt; TCGA.AB.2996.03     2  0.4796      0.859 0.00 0.78 0.22
#&gt; TCGA.AB.2936.03     2  0.4796      0.859 0.00 0.78 0.22
#&gt; TCGA.AB.2900.03     1  0.0000      0.887 1.00 0.00 0.00
#&gt; TCGA.AB.2926.03     1  0.0000      0.887 1.00 0.00 0.00
#&gt; TCGA.AB.2977.03     1  0.0000      0.887 1.00 0.00 0.00
#&gt; TCGA.AB.2821.03     3  0.4796      0.627 0.00 0.22 0.78
#&gt; TCGA.AB.2863.03     2  0.0000      0.842 0.00 1.00 0.00
#&gt; TCGA.AB.2855.03     1  0.0000      0.887 1.00 0.00 0.00
#&gt; TCGA.AB.2923.03     3  0.4796      0.627 0.00 0.22 0.78
#&gt; TCGA.AB.2834.03     3  0.6309      0.249 0.50 0.00 0.50
#&gt; TCGA.AB.2826.03     1  0.5706      0.295 0.68 0.00 0.32
#&gt; TCGA.AB.2810.03     3  0.6302      0.292 0.48 0.00 0.52
#&gt; TCGA.AB.2901.03     2  0.0000      0.842 0.00 1.00 0.00
#&gt; TCGA.AB.2854.03     2  0.4796      0.859 0.00 0.78 0.22
</code></pre>

<script>
$('#tab-node-022-get-classes-2-a').parent().next().next().hide();
$('#tab-node-022-get-classes-2-a').click(function(){
  $('#tab-node-022-get-classes-2-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-022-get-classes-3'>
<p><a id='tab-node-022-get-classes-3-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 4), get_membership(res, k = 4))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4
#&gt; TCGA.AB.2984.03     1   0.000      1.000 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2874.03     3   0.462      0.731 0.34 0.00 0.66 0.00
#&gt; TCGA.AB.2866.03     1   0.000      1.000 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2959.03     4   0.738     -0.121 0.00 0.26 0.22 0.52
#&gt; TCGA.AB.2871.03     2   0.638      0.474 0.00 0.58 0.08 0.34
#&gt; TCGA.AB.2907.03     2   0.748      0.375 0.00 0.44 0.18 0.38
#&gt; TCGA.AB.2867.03     2   0.000      0.677 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2822.03     2   0.000      0.677 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2903.03     4   0.340      0.664 0.00 0.00 0.18 0.82
#&gt; TCGA.AB.2948.03     2   0.000      0.677 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2964.03     4   0.121      0.637 0.00 0.04 0.00 0.96
#&gt; TCGA.AB.2805.03     2   0.748      0.375 0.00 0.44 0.18 0.38
#&gt; TCGA.AB.2990.03     1   0.000      1.000 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.3002.03     3   0.292      0.642 0.14 0.00 0.86 0.00
#&gt; TCGA.AB.2877.03     1   0.000      1.000 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2992.03     2   0.000      0.677 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2919.03     3   0.485      0.673 0.40 0.00 0.60 0.00
#&gt; TCGA.AB.2996.03     2   0.000      0.677 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2936.03     2   0.000      0.677 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2900.03     1   0.000      1.000 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2926.03     1   0.000      1.000 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2977.03     1   0.000      1.000 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2821.03     3   0.462     -0.359 0.00 0.00 0.66 0.34
#&gt; TCGA.AB.2863.03     2   0.748      0.375 0.00 0.44 0.18 0.38
#&gt; TCGA.AB.2855.03     1   0.000      1.000 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2923.03     4   0.340      0.664 0.00 0.00 0.18 0.82
#&gt; TCGA.AB.2834.03     3   0.462      0.731 0.34 0.00 0.66 0.00
#&gt; TCGA.AB.2826.03     3   0.485      0.673 0.40 0.00 0.60 0.00
#&gt; TCGA.AB.2810.03     3   0.398      0.719 0.24 0.00 0.76 0.00
#&gt; TCGA.AB.2901.03     2   0.748      0.375 0.00 0.44 0.18 0.38
#&gt; TCGA.AB.2854.03     2   0.484      0.614 0.00 0.78 0.08 0.14
</code></pre>

<script>
$('#tab-node-022-get-classes-3-a').parent().next().next().hide();
$('#tab-node-022-get-classes-3-a').click(function(){
  $('#tab-node-022-get-classes-3-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-022-get-classes-4'>
<p><a id='tab-node-022-get-classes-4-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 5), get_membership(res, k = 5))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5
#&gt; TCGA.AB.2984.03     1  0.2331      0.932 0.90 0.00 0.00 0.02 0.08
#&gt; TCGA.AB.2874.03     3  0.1410      0.807 0.06 0.00 0.94 0.00 0.00
#&gt; TCGA.AB.2866.03     1  0.0609      0.929 0.98 0.00 0.00 0.00 0.02
#&gt; TCGA.AB.2959.03     5  0.4653      0.626 0.00 0.16 0.06 0.02 0.76
#&gt; TCGA.AB.2871.03     5  0.5350      0.525 0.00 0.48 0.02 0.02 0.48
#&gt; TCGA.AB.2907.03     5  0.4613      0.760 0.00 0.36 0.00 0.02 0.62
#&gt; TCGA.AB.2867.03     2  0.0000      0.861 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2822.03     2  0.0000      0.861 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2903.03     4  0.1648      0.970 0.00 0.00 0.02 0.94 0.04
#&gt; TCGA.AB.2948.03     2  0.1216      0.843 0.00 0.96 0.02 0.02 0.00
#&gt; TCGA.AB.2964.03     4  0.2610      0.940 0.00 0.02 0.02 0.90 0.06
#&gt; TCGA.AB.2805.03     5  0.5162      0.753 0.00 0.36 0.02 0.02 0.60
#&gt; TCGA.AB.2990.03     1  0.2331      0.932 0.90 0.00 0.00 0.02 0.08
#&gt; TCGA.AB.3002.03     3  0.4312      0.672 0.04 0.00 0.78 0.02 0.16
#&gt; TCGA.AB.2877.03     1  0.0609      0.929 0.98 0.00 0.00 0.00 0.02
#&gt; TCGA.AB.2992.03     2  0.0000      0.861 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2919.03     3  0.5685      0.814 0.08 0.00 0.68 0.04 0.20
#&gt; TCGA.AB.2996.03     2  0.1216      0.843 0.00 0.96 0.02 0.02 0.00
#&gt; TCGA.AB.2936.03     2  0.0000      0.861 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2900.03     1  0.2331      0.932 0.90 0.00 0.00 0.02 0.08
#&gt; TCGA.AB.2926.03     1  0.0000      0.931 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2977.03     1  0.2331      0.932 0.90 0.00 0.00 0.02 0.08
#&gt; TCGA.AB.2821.03     5  0.4254      0.400 0.00 0.00 0.22 0.04 0.74
#&gt; TCGA.AB.2863.03     5  0.4613      0.760 0.00 0.36 0.00 0.02 0.62
#&gt; TCGA.AB.2855.03     1  0.0609      0.929 0.98 0.00 0.00 0.00 0.02
#&gt; TCGA.AB.2923.03     4  0.1648      0.970 0.00 0.00 0.02 0.94 0.04
#&gt; TCGA.AB.2834.03     3  0.1410      0.807 0.06 0.00 0.94 0.00 0.00
#&gt; TCGA.AB.2826.03     3  0.5685      0.814 0.08 0.00 0.68 0.04 0.20
#&gt; TCGA.AB.2810.03     3  0.5400      0.818 0.06 0.00 0.70 0.04 0.20
#&gt; TCGA.AB.2901.03     5  0.4613      0.760 0.00 0.36 0.00 0.02 0.62
#&gt; TCGA.AB.2854.03     2  0.4798     -0.500 0.00 0.54 0.02 0.00 0.44
</code></pre>

<script>
$('#tab-node-022-get-classes-4-a').parent().next().next().hide();
$('#tab-node-022-get-classes-4-a').click(function(){
  $('#tab-node-022-get-classes-4-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-022-get-classes-5'>
<p><a id='tab-node-022-get-classes-5-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 6), get_membership(res, k = 6))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5   p6
#&gt; TCGA.AB.2984.03     1  0.1814     0.9222 0.90 0.00 0.10 0.00 0.00 0.00
#&gt; TCGA.AB.2874.03     3  0.4993     0.3824 0.00 0.08 0.56 0.00 0.00 0.36
#&gt; TCGA.AB.2866.03     1  0.1480     0.9049 0.94 0.02 0.00 0.00 0.00 0.04
#&gt; TCGA.AB.2959.03     5  0.3076     0.5225 0.00 0.00 0.00 0.00 0.76 0.24
#&gt; TCGA.AB.2871.03     5  0.3475     0.7255 0.00 0.14 0.00 0.00 0.80 0.06
#&gt; TCGA.AB.2907.03     5  0.0547     0.8197 0.00 0.00 0.00 0.00 0.98 0.02
#&gt; TCGA.AB.2867.03     2  0.2260     0.9586 0.00 0.86 0.00 0.00 0.14 0.00
#&gt; TCGA.AB.2822.03     2  0.2260     0.9586 0.00 0.86 0.00 0.00 0.14 0.00
#&gt; TCGA.AB.2903.03     4  0.1807     0.9233 0.00 0.02 0.00 0.92 0.00 0.06
#&gt; TCGA.AB.2948.03     2  0.3985     0.9167 0.00 0.76 0.00 0.00 0.14 0.10
#&gt; TCGA.AB.2964.03     4  0.1267     0.9243 0.00 0.00 0.00 0.94 0.00 0.06
#&gt; TCGA.AB.2805.03     5  0.0937     0.8158 0.00 0.00 0.00 0.00 0.96 0.04
#&gt; TCGA.AB.2990.03     1  0.1814     0.9222 0.90 0.00 0.10 0.00 0.00 0.00
#&gt; TCGA.AB.3002.03     6  0.3706    -0.3183 0.00 0.00 0.38 0.00 0.00 0.62
#&gt; TCGA.AB.2877.03     1  0.1480     0.9049 0.94 0.02 0.00 0.00 0.00 0.04
#&gt; TCGA.AB.2992.03     2  0.2260     0.9586 0.00 0.86 0.00 0.00 0.14 0.00
#&gt; TCGA.AB.2919.03     3  0.0000     0.7089 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2996.03     2  0.3985     0.9167 0.00 0.76 0.00 0.00 0.14 0.10
#&gt; TCGA.AB.2936.03     2  0.2260     0.9586 0.00 0.86 0.00 0.00 0.14 0.00
#&gt; TCGA.AB.2900.03     1  0.1814     0.9222 0.90 0.00 0.10 0.00 0.00 0.00
#&gt; TCGA.AB.2926.03     1  0.0547     0.9135 0.98 0.02 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2977.03     1  0.1814     0.9222 0.90 0.00 0.10 0.00 0.00 0.00
#&gt; TCGA.AB.2821.03     6  0.3828    -0.0562 0.00 0.00 0.00 0.00 0.44 0.56
#&gt; TCGA.AB.2863.03     5  0.0937     0.8141 0.00 0.00 0.00 0.00 0.96 0.04
#&gt; TCGA.AB.2855.03     1  0.1480     0.9049 0.94 0.02 0.00 0.00 0.00 0.04
#&gt; TCGA.AB.2923.03     4  0.0000     0.9418 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2834.03     3  0.4993     0.3824 0.00 0.08 0.56 0.00 0.00 0.36
#&gt; TCGA.AB.2826.03     3  0.0000     0.7089 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2810.03     3  0.0000     0.7089 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2901.03     5  0.1267     0.8122 0.00 0.00 0.00 0.00 0.94 0.06
#&gt; TCGA.AB.2854.03     5  0.3475     0.7255 0.00 0.14 0.00 0.00 0.80 0.06
</code></pre>

<script>
$('#tab-node-022-get-classes-5-a').parent().next().next().hide();
$('#tab-node-022-get-classes-5-a').click(function(){
  $('#tab-node-022-get-classes-5-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-022-get-classes-6'>
<p><a id='tab-node-022-get-classes-6-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 7), get_membership(res, k = 7))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5   p6   p7
#&gt; TCGA.AB.2984.03     1  0.1166      0.893 0.94 0.00 0.06 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2874.03     3  0.4426      0.668 0.00 0.00 0.56 0.00 0.06 0.38 0.00
#&gt; TCGA.AB.2866.03     1  0.3058      0.842 0.82 0.00 0.00 0.00 0.00 0.08 0.10
#&gt; TCGA.AB.2959.03     5  0.2708      0.494 0.00 0.00 0.00 0.00 0.78 0.00 0.22
#&gt; TCGA.AB.2871.03     7  0.4264      0.565 0.00 0.22 0.00 0.02 0.06 0.00 0.70
#&gt; TCGA.AB.2907.03     5  0.4901      0.477 0.00 0.06 0.00 0.02 0.52 0.00 0.40
#&gt; TCGA.AB.2867.03     2  0.0000      0.896 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2822.03     2  0.0000      0.896 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2903.03     4  0.2163      0.788 0.00 0.00 0.00 0.88 0.00 0.10 0.02
#&gt; TCGA.AB.2948.03     2  0.3186      0.789 0.00 0.76 0.00 0.00 0.00 0.22 0.02
#&gt; TCGA.AB.2964.03     4  0.3606      0.630 0.00 0.00 0.00 0.68 0.00 0.02 0.30
#&gt; TCGA.AB.2805.03     5  0.4778      0.501 0.00 0.06 0.00 0.02 0.58 0.00 0.34
#&gt; TCGA.AB.2990.03     1  0.1166      0.893 0.94 0.00 0.06 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.3002.03     3  0.5539      0.468 0.00 0.00 0.38 0.00 0.38 0.24 0.00
#&gt; TCGA.AB.2877.03     1  0.3058      0.842 0.82 0.00 0.00 0.00 0.00 0.08 0.10
#&gt; TCGA.AB.2992.03     2  0.0000      0.896 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2919.03     3  0.0000      0.718 0.00 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2996.03     2  0.3186      0.789 0.00 0.76 0.00 0.00 0.00 0.22 0.02
#&gt; TCGA.AB.2936.03     2  0.0000      0.896 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2900.03     1  0.1166      0.893 0.94 0.00 0.06 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2926.03     1  0.1006      0.873 0.96 0.00 0.00 0.00 0.00 0.02 0.02
#&gt; TCGA.AB.2977.03     1  0.1166      0.893 0.94 0.00 0.06 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2821.03     5  0.2016      0.320 0.00 0.00 0.00 0.00 0.90 0.06 0.04
#&gt; TCGA.AB.2863.03     5  0.5309      0.387 0.00 0.06 0.00 0.02 0.52 0.02 0.38
#&gt; TCGA.AB.2855.03     1  0.3058      0.842 0.82 0.00 0.00 0.00 0.00 0.08 0.10
#&gt; TCGA.AB.2923.03     4  0.0000      0.805 0.00 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2834.03     3  0.4426      0.668 0.00 0.00 0.56 0.00 0.06 0.38 0.00
#&gt; TCGA.AB.2826.03     3  0.0000      0.718 0.00 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2810.03     3  0.0504      0.716 0.00 0.00 0.98 0.00 0.00 0.00 0.02
#&gt; TCGA.AB.2901.03     7  0.6298     -0.365 0.00 0.06 0.00 0.02 0.34 0.12 0.46
#&gt; TCGA.AB.2854.03     7  0.4015      0.561 0.00 0.26 0.00 0.00 0.06 0.00 0.68
</code></pre>

<script>
$('#tab-node-022-get-classes-6-a').parent().next().next().hide();
$('#tab-node-022-get-classes-6-a').click(function(){
  $('#tab-node-022-get-classes-6-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-022-get-classes-7'>
<p><a id='tab-node-022-get-classes-7-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 8), get_membership(res, k = 8))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5   p6   p7   p8
#&gt; TCGA.AB.2984.03     1  0.0000     0.7796 1.00 0.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2874.03     3  0.0471     0.6696 0.00 0.00 0.98 0.00 0.00 0.02 0.00 0.00
#&gt; TCGA.AB.2866.03     1  0.3318     0.6457 0.54 0.00 0.00 0.00 0.00 0.46 0.00 0.00
#&gt; TCGA.AB.2959.03     5  0.3537     0.1349 0.00 0.00 0.00 0.00 0.72 0.02 0.02 0.24
#&gt; TCGA.AB.2871.03     5  0.4480     0.5187 0.00 0.12 0.00 0.00 0.58 0.00 0.00 0.30
#&gt; TCGA.AB.2907.03     5  0.0471     0.6507 0.00 0.02 0.00 0.00 0.98 0.00 0.00 0.00
#&gt; TCGA.AB.2867.03     2  0.0000     0.9016 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2822.03     2  0.0000     0.9016 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2903.03     4  0.2807     0.7221 0.00 0.00 0.00 0.84 0.00 0.10 0.02 0.04
#&gt; TCGA.AB.2948.03     2  0.3293     0.7893 0.00 0.74 0.00 0.00 0.00 0.22 0.00 0.04
#&gt; TCGA.AB.2964.03     4  0.3991     0.5861 0.00 0.00 0.00 0.62 0.00 0.00 0.06 0.32
#&gt; TCGA.AB.2805.03     5  0.1741     0.6388 0.00 0.02 0.00 0.00 0.92 0.02 0.04 0.00
#&gt; TCGA.AB.2990.03     1  0.0000     0.7796 1.00 0.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.3002.03     3  0.4008    -0.0622 0.00 0.00 0.48 0.00 0.00 0.04 0.00 0.48
#&gt; TCGA.AB.2877.03     1  0.3318     0.6457 0.54 0.00 0.00 0.00 0.00 0.46 0.00 0.00
#&gt; TCGA.AB.2992.03     2  0.0000     0.9016 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2919.03     7  0.3551     0.9771 0.06 0.00 0.22 0.00 0.00 0.00 0.72 0.00
#&gt; TCGA.AB.2996.03     2  0.3293     0.7893 0.00 0.74 0.00 0.00 0.00 0.22 0.00 0.04
#&gt; TCGA.AB.2936.03     2  0.0000     0.9016 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2900.03     1  0.0000     0.7796 1.00 0.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2926.03     1  0.3402     0.7021 0.82 0.00 0.00 0.00 0.02 0.04 0.06 0.06
#&gt; TCGA.AB.2977.03     1  0.0000     0.7796 1.00 0.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2821.03     8  0.5451     0.0000 0.00 0.00 0.10 0.00 0.30 0.08 0.00 0.52
#&gt; TCGA.AB.2863.03     5  0.2724     0.6294 0.00 0.02 0.00 0.00 0.86 0.08 0.02 0.02
#&gt; TCGA.AB.2855.03     1  0.3318     0.6457 0.54 0.00 0.00 0.00 0.00 0.46 0.00 0.00
#&gt; TCGA.AB.2923.03     4  0.0000     0.7486 0.00 0.00 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2834.03     3  0.0471     0.6687 0.00 0.00 0.98 0.00 0.00 0.00 0.02 0.00
#&gt; TCGA.AB.2826.03     7  0.3551     0.9771 0.06 0.00 0.22 0.00 0.00 0.00 0.72 0.00
#&gt; TCGA.AB.2810.03     7  0.3735     0.9539 0.04 0.00 0.22 0.00 0.00 0.02 0.72 0.00
#&gt; TCGA.AB.2901.03     5  0.3847     0.6123 0.00 0.02 0.00 0.00 0.78 0.06 0.10 0.04
#&gt; TCGA.AB.2854.03     5  0.4480     0.5187 0.00 0.12 0.00 0.00 0.58 0.00 0.00 0.30
</code></pre>

<script>
$('#tab-node-022-get-classes-7-a').parent().next().next().hide();
$('#tab-node-022-get-classes-7-a').click(function(){
  $('#tab-node-022-get-classes-7-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>
</div>

Heatmaps for the consensus matrix. It visualizes the probability of two
samples to be in a same group.




<script>
$( function() {
	$( '#tabs-node-022-consensus-heatmap' ).tabs();
} );
</script>
<div id='tabs-node-022-consensus-heatmap'>
<ul>
<li><a href='#tab-node-022-consensus-heatmap-1'>k = 2</a></li>
<li><a href='#tab-node-022-consensus-heatmap-2'>k = 3</a></li>
<li><a href='#tab-node-022-consensus-heatmap-3'>k = 4</a></li>
<li><a href='#tab-node-022-consensus-heatmap-4'>k = 5</a></li>
<li><a href='#tab-node-022-consensus-heatmap-5'>k = 6</a></li>
<li><a href='#tab-node-022-consensus-heatmap-6'>k = 7</a></li>
<li><a href='#tab-node-022-consensus-heatmap-7'>k = 8</a></li>
</ul>
<div id='tab-node-022-consensus-heatmap-1'>
<pre><code class="r">consensus_heatmap(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-022-consensus-heatmap-1-1.png" alt="plot of chunk tab-node-022-consensus-heatmap-1"/></p>

</div>
<div id='tab-node-022-consensus-heatmap-2'>
<pre><code class="r">consensus_heatmap(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-022-consensus-heatmap-2-1.png" alt="plot of chunk tab-node-022-consensus-heatmap-2"/></p>

</div>
<div id='tab-node-022-consensus-heatmap-3'>
<pre><code class="r">consensus_heatmap(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-022-consensus-heatmap-3-1.png" alt="plot of chunk tab-node-022-consensus-heatmap-3"/></p>

</div>
<div id='tab-node-022-consensus-heatmap-4'>
<pre><code class="r">consensus_heatmap(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-022-consensus-heatmap-4-1.png" alt="plot of chunk tab-node-022-consensus-heatmap-4"/></p>

</div>
<div id='tab-node-022-consensus-heatmap-5'>
<pre><code class="r">consensus_heatmap(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-022-consensus-heatmap-5-1.png" alt="plot of chunk tab-node-022-consensus-heatmap-5"/></p>

</div>
<div id='tab-node-022-consensus-heatmap-6'>
<pre><code class="r">consensus_heatmap(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-022-consensus-heatmap-6-1.png" alt="plot of chunk tab-node-022-consensus-heatmap-6"/></p>

</div>
<div id='tab-node-022-consensus-heatmap-7'>
<pre><code class="r">consensus_heatmap(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-022-consensus-heatmap-7-1.png" alt="plot of chunk tab-node-022-consensus-heatmap-7"/></p>

</div>
</div>

Heatmaps for the membership of samples in all partitions to see how consistent they are:





<script>
$( function() {
	$( '#tabs-node-022-membership-heatmap' ).tabs();
} );
</script>
<div id='tabs-node-022-membership-heatmap'>
<ul>
<li><a href='#tab-node-022-membership-heatmap-1'>k = 2</a></li>
<li><a href='#tab-node-022-membership-heatmap-2'>k = 3</a></li>
<li><a href='#tab-node-022-membership-heatmap-3'>k = 4</a></li>
<li><a href='#tab-node-022-membership-heatmap-4'>k = 5</a></li>
<li><a href='#tab-node-022-membership-heatmap-5'>k = 6</a></li>
<li><a href='#tab-node-022-membership-heatmap-6'>k = 7</a></li>
<li><a href='#tab-node-022-membership-heatmap-7'>k = 8</a></li>
</ul>
<div id='tab-node-022-membership-heatmap-1'>
<pre><code class="r">membership_heatmap(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-022-membership-heatmap-1-1.png" alt="plot of chunk tab-node-022-membership-heatmap-1"/></p>

</div>
<div id='tab-node-022-membership-heatmap-2'>
<pre><code class="r">membership_heatmap(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-022-membership-heatmap-2-1.png" alt="plot of chunk tab-node-022-membership-heatmap-2"/></p>

</div>
<div id='tab-node-022-membership-heatmap-3'>
<pre><code class="r">membership_heatmap(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-022-membership-heatmap-3-1.png" alt="plot of chunk tab-node-022-membership-heatmap-3"/></p>

</div>
<div id='tab-node-022-membership-heatmap-4'>
<pre><code class="r">membership_heatmap(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-022-membership-heatmap-4-1.png" alt="plot of chunk tab-node-022-membership-heatmap-4"/></p>

</div>
<div id='tab-node-022-membership-heatmap-5'>
<pre><code class="r">membership_heatmap(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-022-membership-heatmap-5-1.png" alt="plot of chunk tab-node-022-membership-heatmap-5"/></p>

</div>
<div id='tab-node-022-membership-heatmap-6'>
<pre><code class="r">membership_heatmap(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-022-membership-heatmap-6-1.png" alt="plot of chunk tab-node-022-membership-heatmap-6"/></p>

</div>
<div id='tab-node-022-membership-heatmap-7'>
<pre><code class="r">membership_heatmap(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-022-membership-heatmap-7-1.png" alt="plot of chunk tab-node-022-membership-heatmap-7"/></p>

</div>
</div>

As soon as the classes for columns are determined, the signatures
that are significantly different between subgroups can be looked for. 
Following are the heatmaps for signatures.






<script>
$( function() {
	$( '#tabs-node-022-get-signatures' ).tabs();
} );
</script>
<div id='tabs-node-022-get-signatures'>
<ul>
<li><a href='#tab-node-022-get-signatures-1'>k = 2</a></li>
<li><a href='#tab-node-022-get-signatures-2'>k = 3</a></li>
<li><a href='#tab-node-022-get-signatures-3'>k = 4</a></li>
<li><a href='#tab-node-022-get-signatures-4'>k = 5</a></li>
<li><a href='#tab-node-022-get-signatures-5'>k = 6</a></li>
<li><a href='#tab-node-022-get-signatures-6'>k = 7</a></li>
<li><a href='#tab-node-022-get-signatures-7'>k = 8</a></li>
</ul>
<div id='tab-node-022-get-signatures-1'>
<pre><code class="r">get_signatures(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-022-get-signatures-1-1.png" alt="plot of chunk tab-node-022-get-signatures-1"/></p>

</div>
<div id='tab-node-022-get-signatures-2'>
<pre><code class="r">get_signatures(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-022-get-signatures-2-1.png" alt="plot of chunk tab-node-022-get-signatures-2"/></p>

</div>
<div id='tab-node-022-get-signatures-3'>
<pre><code class="r">get_signatures(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-022-get-signatures-3-1.png" alt="plot of chunk tab-node-022-get-signatures-3"/></p>

</div>
<div id='tab-node-022-get-signatures-4'>
<pre><code class="r">get_signatures(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-022-get-signatures-4-1.png" alt="plot of chunk tab-node-022-get-signatures-4"/></p>

</div>
<div id='tab-node-022-get-signatures-5'>
<pre><code class="r">get_signatures(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-022-get-signatures-5-1.png" alt="plot of chunk tab-node-022-get-signatures-5"/></p>

</div>
<div id='tab-node-022-get-signatures-6'>
<pre><code class="r">get_signatures(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-022-get-signatures-6-1.png" alt="plot of chunk tab-node-022-get-signatures-6"/></p>

</div>
<div id='tab-node-022-get-signatures-7'>
<pre><code class="r">get_signatures(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-022-get-signatures-7-1.png" alt="plot of chunk tab-node-022-get-signatures-7"/></p>

</div>
</div>



Compare the overlap of signatures from different k:

```r
compare_signatures(res)
```

![plot of chunk node-022-signature_compare](figure_cola/node-022-signature_compare-1.png)

`get_signature()` returns a data frame invisibly. To get the list of signatures, the function
call should be assigned to a variable explicitly. In following code, if `plot` argument is set
to `FALSE`, no heatmap is plotted while only the differential analysis is performed.

```r
# code only for demonstration
tb = get_signature(res, k = ..., plot = FALSE)
```

An example of the output of `tb` is:

```
#>   which_row         fdr    mean_1    mean_2 scaled_mean_1 scaled_mean_2 km
#> 1        38 0.042760348  8.373488  9.131774    -0.5533452     0.5164555  1
#> 2        40 0.018707592  7.106213  8.469186    -0.6173731     0.5762149  1
#> 3        55 0.019134737 10.221463 11.207825    -0.6159697     0.5749050  1
#> 4        59 0.006059896  5.921854  7.869574    -0.6899429     0.6439467  1
#> 5        60 0.018055526  8.928898 10.211722    -0.6204761     0.5791110  1
#> 6        98 0.009384629 15.714769 14.887706     0.6635654    -0.6193277  2
...
```

The columns in `tb` are:

1. `which_row`: row indices corresponding to the input matrix.
2. `fdr`: FDR for the differential test. 
3. `mean_x`: The mean value in group x.
4. `scaled_mean_x`: The mean value in group x after rows are scaled.
5. `km`: Row groups if k-means clustering is applied to rows (which is done by automatically selecting number of clusters).

If there are too many signatures, `top_signatures = ...` can be set to only show the 
signatures with the highest FDRs:

```r
# code only for demonstration
# e.g. to show the top 500 most significant rows
tb = get_signature(res, k = ..., top_signatures = 500)
```

If the signatures are defined as these which are uniquely high in current group, `diff_method` argument
can be set to `"uniquely_high_in_one_group"`:

```r
# code only for demonstration
tb = get_signature(res, k = ..., diff_method = "uniquely_high_in_one_group")
```




UMAP plot which shows how samples are separated.


<script>
$( function() {
	$( '#tabs-node-022-dimension-reduction' ).tabs();
} );
</script>
<div id='tabs-node-022-dimension-reduction'>
<ul>
<li><a href='#tab-node-022-dimension-reduction-1'>k = 2</a></li>
<li><a href='#tab-node-022-dimension-reduction-2'>k = 3</a></li>
<li><a href='#tab-node-022-dimension-reduction-3'>k = 4</a></li>
<li><a href='#tab-node-022-dimension-reduction-4'>k = 5</a></li>
<li><a href='#tab-node-022-dimension-reduction-5'>k = 6</a></li>
<li><a href='#tab-node-022-dimension-reduction-6'>k = 7</a></li>
<li><a href='#tab-node-022-dimension-reduction-7'>k = 8</a></li>
</ul>
<div id='tab-node-022-dimension-reduction-1'>
<pre><code class="r">dimension_reduction(res, k = 2, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-022-dimension-reduction-1-1.png" alt="plot of chunk tab-node-022-dimension-reduction-1"/></p>

</div>
<div id='tab-node-022-dimension-reduction-2'>
<pre><code class="r">dimension_reduction(res, k = 3, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-022-dimension-reduction-2-1.png" alt="plot of chunk tab-node-022-dimension-reduction-2"/></p>

</div>
<div id='tab-node-022-dimension-reduction-3'>
<pre><code class="r">dimension_reduction(res, k = 4, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-022-dimension-reduction-3-1.png" alt="plot of chunk tab-node-022-dimension-reduction-3"/></p>

</div>
<div id='tab-node-022-dimension-reduction-4'>
<pre><code class="r">dimension_reduction(res, k = 5, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-022-dimension-reduction-4-1.png" alt="plot of chunk tab-node-022-dimension-reduction-4"/></p>

</div>
<div id='tab-node-022-dimension-reduction-5'>
<pre><code class="r">dimension_reduction(res, k = 6, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-022-dimension-reduction-5-1.png" alt="plot of chunk tab-node-022-dimension-reduction-5"/></p>

</div>
<div id='tab-node-022-dimension-reduction-6'>
<pre><code class="r">dimension_reduction(res, k = 7, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-022-dimension-reduction-6-1.png" alt="plot of chunk tab-node-022-dimension-reduction-6"/></p>

</div>
<div id='tab-node-022-dimension-reduction-7'>
<pre><code class="r">dimension_reduction(res, k = 8, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-022-dimension-reduction-7-1.png" alt="plot of chunk tab-node-022-dimension-reduction-7"/></p>

</div>
</div>



Following heatmap shows how subgroups are split when increasing `k`:

```r
collect_classes(res)
```

![plot of chunk node-022-collect-classes](figure_cola/node-022-collect-classes-1.png)



If matrix rows can be associated to genes, consider to use `functional_enrichment(res,
...)` to perform function enrichment for the signature genes. See [this vignette](https://jokergoo.github.io/cola_vignettes/functional_enrichment.html) for more detailed explanations.


 

---------------------------------------------------




### Node0222


Parent node: [Node022](#Node022).
Child nodes: 
                Node02221-leaf
        ,
                Node02222-leaf
        ,
                Node02223-leaf
        .







The object with results only for a single top-value method and a single partitioning method 
can be extracted as:

```r
res = res_rh["0222"]
```

A summary of `res` and all the functions that can be applied to it:

```r
res
```

```
#> A 'ConsensusPartition' object with k = 2, 3, 4, 5, 6, 7, 8.
#>   On a matrix with 30000 rows and 17 columns.
#>   Top rows (1000) are extracted by 'ATC' method.
#>   Subgroups are detected by 'kmeans' method.
#>   Performed in total 350 partitions by row resampling.
#>   Best k for subgroups seems to be 3.
#> 
#> Following methods can be applied to this 'ConsensusPartition' object:
#>  [1] "cola_report"             "collect_classes"         "collect_plots"          
#>  [4] "collect_stats"           "colnames"                "compare_partitions"     
#>  [7] "compare_signatures"      "consensus_heatmap"       "dimension_reduction"    
#> [10] "functional_enrichment"   "get_anno_col"            "get_anno"               
#> [13] "get_classes"             "get_consensus"           "get_matrix"             
#> [16] "get_membership"          "get_param"               "get_signatures"         
#> [19] "get_stats"               "is_best_k"               "is_stable_k"            
#> [22] "membership_heatmap"      "ncol"                    "nrow"                   
#> [25] "plot_ecdf"               "predict_classes"         "rownames"               
#> [28] "select_partition_number" "show"                    "suggest_best_k"         
#> [31] "test_to_known_factors"   "top_rows_heatmap"
```

`collect_plots()` function collects all the plots made from `res` for all `k` (number of subgroups)
into one single page to provide an easy and fast comparison between different `k`.

```r
collect_plots(res)
```

![plot of chunk node-0222-collect-plots](figure_cola/node-0222-collect-plots-1.png)

The plots are:

- The first row: a plot of the eCDF (empirical cumulative distribution
  function) curves of the consensus matrix for each `k` and the heatmap of
  predicted classes for each `k`.
- The second row: heatmaps of the consensus matrix for each `k`.
- The third row: heatmaps of the membership matrix for each `k`.
- The fouth row: heatmaps of the signatures for each `k`.

All the plots in panels can be made by individual functions and they are
plotted later in this section.

`select_partition_number()` produces several plots showing different
statistics for choosing "optimized" `k`. There are following statistics:

- eCDF curves of the consensus matrix for each `k`;
- 1-PAC. [The PAC score](https://en.wikipedia.org/wiki/Consensus_clustering#Over-interpretation_potential_of_consensus_clustering)
  measures the proportion of the ambiguous subgrouping.
- Mean silhouette score.
- Concordance. The mean probability of fiting the consensus subgroup labels in all
  partitions.
- Area increased. Denote $A_k$ as the area under the eCDF curve for current
  `k`, the area increased is defined as $A_k - A_{k-1}$.
- Rand index. The percent of pairs of samples that are both in a same cluster
  or both are not in a same cluster in the partition of k and k-1.
- Jaccard index. The ratio of pairs of samples are both in a same cluster in
  the partition of k and k-1 and the pairs of samples are both in a same
  cluster in the partition k or k-1.

The detailed explanations of these statistics can be found in [the _cola_
vignette](https://jokergoo.github.io/cola_vignettes/cola.html#toc_13).

Generally speaking, higher 1-PAC score, higher mean silhouette score or higher
concordance corresponds to better partition. Rand index and Jaccard index
measure how similar the current partition is compared to partition with `k-1`.
If they are too similar, we won't accept `k` is better than `k-1`.

```r
select_partition_number(res)
```

![plot of chunk node-0222-select-partition-number](figure_cola/node-0222-select-partition-number-1.png)

The numeric values for all these statistics can be obtained by `get_stats()`.

```r
get_stats(res)
```

```
#>   k 1-PAC mean_silhouette concordance area_increased  Rand Jaccard
#> 2 2 0.618           0.942       0.952         0.4736 0.485   0.485
#> 3 3 1.000           1.000       1.000         0.2740 0.912   0.818
#> 4 4 0.772           0.902       0.929         0.2304 0.846   0.611
#> 5 5 0.706           0.855       0.884         0.0568 0.934   0.750
#> 6 6 0.801           0.754       0.860         0.0596 0.963   0.833
#> 7 7 0.846           0.633       0.800         0.0255 0.971   0.840
#> 8 8 0.794           0.520       0.811         0.0220 0.934   0.609
```

`suggest_best_k()` suggests the best $k$ based on these statistics. The rules are as follows:

- All $k$ with Jaccard index larger than 0.95 are removed because increasing
  $k$ does not provide enough extra information. If all $k$ are removed, it is
  marked as no subgroup is detected.
- For all $k$ with 1-PAC score larger than 0.9, the maximal $k$ is taken as
  the best $k$, and other $k$ are marked as optional $k$.
- If it does not fit the second rule. The $k$ with the maximal vote of the
  highest 1-PAC score, highest mean silhouette, and highest concordance is
  taken as the best $k$.

```r
suggest_best_k(res)
```

```
#> [1] 3
```


Following is the table of the partitions (You need to click the **show/hide
code output** link to see it). The membership matrix (columns with name `p*`)
is inferred by
[`clue::cl_consensus()`](https://www.rdocumentation.org/link/cl_consensus?package=clue)
function with the `SE` method. Basically the value in the membership matrix
represents the probability to belong to a certain group. The finall subgroup
label for an item is determined with the group with highest probability it
belongs to.

In `get_classes()` function, the entropy is calculated from the membership
matrix and the silhouette score is calculated from the consensus matrix.



<script>
$( function() {
	$( '#tabs-node-0222-get-classes' ).tabs();
} );
</script>
<div id='tabs-node-0222-get-classes'>
<ul>
<li><a href='#tab-node-0222-get-classes-1'>k = 2</a></li>
<li><a href='#tab-node-0222-get-classes-2'>k = 3</a></li>
<li><a href='#tab-node-0222-get-classes-3'>k = 4</a></li>
<li><a href='#tab-node-0222-get-classes-4'>k = 5</a></li>
<li><a href='#tab-node-0222-get-classes-5'>k = 6</a></li>
<li><a href='#tab-node-0222-get-classes-6'>k = 7</a></li>
<li><a href='#tab-node-0222-get-classes-7'>k = 8</a></li>
</ul>

<div id='tab-node-0222-get-classes-1'>
<p><a id='tab-node-0222-get-classes-1-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 2), get_membership(res, k = 2))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2
#&gt; TCGA.AB.2959.03     1   0.000      1.000 1.00 0.00
#&gt; TCGA.AB.2871.03     2   0.722      0.870 0.20 0.80
#&gt; TCGA.AB.2907.03     1   0.000      1.000 1.00 0.00
#&gt; TCGA.AB.2867.03     1   0.000      1.000 1.00 0.00
#&gt; TCGA.AB.2822.03     1   0.000      1.000 1.00 0.00
#&gt; TCGA.AB.2903.03     2   0.000      0.853 0.00 1.00
#&gt; TCGA.AB.2948.03     2   0.722      0.870 0.20 0.80
#&gt; TCGA.AB.2964.03     2   0.000      0.853 0.00 1.00
#&gt; TCGA.AB.2805.03     1   0.000      1.000 1.00 0.00
#&gt; TCGA.AB.2992.03     1   0.000      1.000 1.00 0.00
#&gt; TCGA.AB.2996.03     2   0.722      0.870 0.20 0.80
#&gt; TCGA.AB.2936.03     1   0.000      1.000 1.00 0.00
#&gt; TCGA.AB.2821.03     1   0.000      1.000 1.00 0.00
#&gt; TCGA.AB.2863.03     1   0.000      1.000 1.00 0.00
#&gt; TCGA.AB.2923.03     2   0.000      0.853 0.00 1.00
#&gt; TCGA.AB.2901.03     1   0.000      1.000 1.00 0.00
#&gt; TCGA.AB.2854.03     2   0.760      0.850 0.22 0.78
</code></pre>

<script>
$('#tab-node-0222-get-classes-1-a').parent().next().next().hide();
$('#tab-node-0222-get-classes-1-a').click(function(){
  $('#tab-node-0222-get-classes-1-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-0222-get-classes-2'>
<p><a id='tab-node-0222-get-classes-2-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 3), get_membership(res, k = 3))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette p1 p2 p3
#&gt; TCGA.AB.2959.03     1       0          1  1  0  0
#&gt; TCGA.AB.2871.03     2       0          1  0  1  0
#&gt; TCGA.AB.2907.03     1       0          1  1  0  0
#&gt; TCGA.AB.2867.03     1       0          1  1  0  0
#&gt; TCGA.AB.2822.03     1       0          1  1  0  0
#&gt; TCGA.AB.2903.03     3       0          1  0  0  1
#&gt; TCGA.AB.2948.03     2       0          1  0  1  0
#&gt; TCGA.AB.2964.03     3       0          1  0  0  1
#&gt; TCGA.AB.2805.03     1       0          1  1  0  0
#&gt; TCGA.AB.2992.03     1       0          1  1  0  0
#&gt; TCGA.AB.2996.03     2       0          1  0  1  0
#&gt; TCGA.AB.2936.03     1       0          1  1  0  0
#&gt; TCGA.AB.2821.03     1       0          1  1  0  0
#&gt; TCGA.AB.2863.03     1       0          1  1  0  0
#&gt; TCGA.AB.2923.03     3       0          1  0  0  1
#&gt; TCGA.AB.2901.03     1       0          1  1  0  0
#&gt; TCGA.AB.2854.03     2       0          1  0  1  0
</code></pre>

<script>
$('#tab-node-0222-get-classes-2-a').parent().next().next().hide();
$('#tab-node-0222-get-classes-2-a').click(function(){
  $('#tab-node-0222-get-classes-2-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-0222-get-classes-3'>
<p><a id='tab-node-0222-get-classes-3-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 4), get_membership(res, k = 4))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1  p2   p3   p4
#&gt; TCGA.AB.2959.03     1  0.0000      0.919 1.00 0.0 0.00 0.00
#&gt; TCGA.AB.2871.03     2  0.0000      0.947 0.00 1.0 0.00 0.00
#&gt; TCGA.AB.2907.03     1  0.4790      0.136 0.62 0.0 0.00 0.38
#&gt; TCGA.AB.2867.03     4  0.3400      1.000 0.18 0.0 0.00 0.82
#&gt; TCGA.AB.2822.03     1  0.0000      0.919 1.00 0.0 0.00 0.00
#&gt; TCGA.AB.2903.03     3  0.1637      0.955 0.00 0.0 0.94 0.06
#&gt; TCGA.AB.2948.03     2  0.2345      0.947 0.00 0.9 0.00 0.10
#&gt; TCGA.AB.2964.03     3  0.0000      0.973 0.00 0.0 1.00 0.00
#&gt; TCGA.AB.2805.03     1  0.0000      0.919 1.00 0.0 0.00 0.00
#&gt; TCGA.AB.2992.03     4  0.3400      1.000 0.18 0.0 0.00 0.82
#&gt; TCGA.AB.2996.03     2  0.2345      0.947 0.00 0.9 0.00 0.10
#&gt; TCGA.AB.2936.03     4  0.3400      1.000 0.18 0.0 0.00 0.82
#&gt; TCGA.AB.2821.03     1  0.0000      0.919 1.00 0.0 0.00 0.00
#&gt; TCGA.AB.2863.03     1  0.0000      0.919 1.00 0.0 0.00 0.00
#&gt; TCGA.AB.2923.03     3  0.0707      0.969 0.00 0.0 0.98 0.02
#&gt; TCGA.AB.2901.03     1  0.0000      0.919 1.00 0.0 0.00 0.00
#&gt; TCGA.AB.2854.03     2  0.0000      0.947 0.00 1.0 0.00 0.00
</code></pre>

<script>
$('#tab-node-0222-get-classes-3-a').parent().next().next().hide();
$('#tab-node-0222-get-classes-3-a').click(function(){
  $('#tab-node-0222-get-classes-3-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-0222-get-classes-4'>
<p><a id='tab-node-0222-get-classes-4-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 5), get_membership(res, k = 5))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5
#&gt; TCGA.AB.2959.03     1   0.000      0.963 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2871.03     5   0.398      0.817 0.00 0.34 0.00 0.00 0.66
#&gt; TCGA.AB.2907.03     4   0.679      0.611 0.32 0.30 0.00 0.38 0.00
#&gt; TCGA.AB.2867.03     4   0.202      0.678 0.10 0.00 0.00 0.90 0.00
#&gt; TCGA.AB.2822.03     1   0.000      0.963 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2903.03     3   0.202      0.918 0.00 0.10 0.90 0.00 0.00
#&gt; TCGA.AB.2948.03     5   0.173      0.798 0.00 0.00 0.00 0.08 0.92
#&gt; TCGA.AB.2964.03     3   0.000      0.948 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2805.03     1   0.293      0.796 0.82 0.18 0.00 0.00 0.00
#&gt; TCGA.AB.2992.03     4   0.578      0.797 0.10 0.36 0.00 0.54 0.00
#&gt; TCGA.AB.2996.03     5   0.000      0.798 0.00 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2936.03     4   0.558      0.803 0.10 0.30 0.00 0.60 0.00
#&gt; TCGA.AB.2821.03     1   0.000      0.963 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2863.03     1   0.000      0.963 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2923.03     3   0.122      0.941 0.00 0.02 0.96 0.02 0.00
#&gt; TCGA.AB.2901.03     1   0.000      0.963 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2854.03     5   0.398      0.817 0.00 0.34 0.00 0.00 0.66
</code></pre>

<script>
$('#tab-node-0222-get-classes-4-a').parent().next().next().hide();
$('#tab-node-0222-get-classes-4-a').click(function(){
  $('#tab-node-0222-get-classes-4-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-0222-get-classes-5'>
<p><a id='tab-node-0222-get-classes-5-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 6), get_membership(res, k = 6))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5   p6
#&gt; TCGA.AB.2959.03     1   0.380      0.929 0.58 0.00 0.00 0.00 0.00 0.42
#&gt; TCGA.AB.2871.03     5   0.383      0.732 0.00 0.44 0.00 0.00 0.56 0.00
#&gt; TCGA.AB.2907.03     4   0.296      0.643 0.04 0.00 0.00 0.84 0.00 0.12
#&gt; TCGA.AB.2867.03     4   0.473      0.625 0.10 0.24 0.00 0.66 0.00 0.00
#&gt; TCGA.AB.2822.03     1   0.376      0.933 0.60 0.00 0.00 0.00 0.00 0.40
#&gt; TCGA.AB.2903.03     3   0.156      0.900 0.08 0.00 0.92 0.00 0.00 0.00
#&gt; TCGA.AB.2948.03     5   0.000      0.714 0.00 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2964.03     3   0.000      0.915 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2805.03     6   0.000      0.000 0.00 0.00 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2992.03     4   0.375      0.707 0.08 0.14 0.00 0.78 0.00 0.00
#&gt; TCGA.AB.2996.03     5   0.127      0.714 0.06 0.00 0.00 0.00 0.94 0.00
#&gt; TCGA.AB.2936.03     4   0.000      0.758 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2821.03     1   0.380      0.929 0.58 0.00 0.00 0.00 0.00 0.42
#&gt; TCGA.AB.2863.03     1   0.376      0.933 0.60 0.00 0.00 0.00 0.00 0.40
#&gt; TCGA.AB.2923.03     3   0.279      0.873 0.08 0.06 0.86 0.00 0.00 0.00
#&gt; TCGA.AB.2901.03     1   0.543      0.779 0.48 0.12 0.00 0.00 0.00 0.40
#&gt; TCGA.AB.2854.03     5   0.383      0.732 0.00 0.44 0.00 0.00 0.56 0.00
</code></pre>

<script>
$('#tab-node-0222-get-classes-5-a').parent().next().next().hide();
$('#tab-node-0222-get-classes-5-a').click(function(){
  $('#tab-node-0222-get-classes-5-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-0222-get-classes-6'>
<p><a id='tab-node-0222-get-classes-6-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 7), get_membership(res, k = 7))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5   p6   p7
#&gt; TCGA.AB.2959.03     1  0.0504    0.92944 0.98 0.00 0.00 0.02 0.00 0.00 0.00
#&gt; TCGA.AB.2871.03     5  0.0000    0.68109 0.00 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2907.03     4  0.1166    0.83387 0.06 0.00 0.00 0.94 0.00 0.00 0.00
#&gt; TCGA.AB.2867.03     7  0.6595   -0.00524 0.00 0.00 0.12 0.36 0.00 0.16 0.36
#&gt; TCGA.AB.2822.03     1  0.0000    0.93250 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2903.03     2  0.4737    0.66485 0.00 0.68 0.20 0.00 0.00 0.06 0.06
#&gt; TCGA.AB.2948.03     5  0.3558    0.65928 0.00 0.00 0.48 0.00 0.52 0.00 0.00
#&gt; TCGA.AB.2964.03     2  0.0000    0.77505 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2805.03     6  0.3685    0.00000 0.32 0.00 0.00 0.02 0.00 0.66 0.00
#&gt; TCGA.AB.2992.03     7  0.3562   -0.23000 0.00 0.00 0.00 0.50 0.00 0.00 0.50
#&gt; TCGA.AB.2996.03     5  0.4701    0.64962 0.00 0.00 0.44 0.00 0.50 0.02 0.04
#&gt; TCGA.AB.2936.03     4  0.0000    0.82790 0.00 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2821.03     1  0.0504    0.92944 0.98 0.00 0.00 0.02 0.00 0.00 0.00
#&gt; TCGA.AB.2863.03     1  0.0000    0.93250 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2923.03     2  0.3630    0.73084 0.00 0.80 0.06 0.00 0.00 0.10 0.04
#&gt; TCGA.AB.2901.03     1  0.2376    0.77338 0.86 0.00 0.12 0.00 0.00 0.00 0.02
#&gt; TCGA.AB.2854.03     5  0.0000    0.68109 0.00 0.00 0.00 0.00 1.00 0.00 0.00
</code></pre>

<script>
$('#tab-node-0222-get-classes-6-a').parent().next().next().hide();
$('#tab-node-0222-get-classes-6-a').click(function(){
  $('#tab-node-0222-get-classes-6-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-0222-get-classes-7'>
<p><a id='tab-node-0222-get-classes-7-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 8), get_membership(res, k = 8))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5   p6   p7   p8
#&gt; TCGA.AB.2959.03     1  0.0000      0.912 1.00 0.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2871.03     5  0.3193      0.976 0.00 0.00 0.38 0.00 0.62 0.00 0.00 0.00
#&gt; TCGA.AB.2907.03     4  0.1765      0.495 0.12 0.00 0.00 0.88 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2867.03     7  0.2756      0.000 0.00 0.00 0.00 0.26 0.00 0.00 0.74 0.00
#&gt; TCGA.AB.2822.03     1  0.0000      0.912 1.00 0.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2903.03     2  0.0000      0.275 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2948.03     3  0.0000      0.672 0.00 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2964.03     2  0.4943     -0.122 0.00 0.64 0.00 0.00 0.02 0.08 0.04 0.22
#&gt; TCGA.AB.2805.03     6  0.2267      0.000 0.18 0.00 0.00 0.00 0.00 0.82 0.00 0.00
#&gt; TCGA.AB.2992.03     4  0.6162      0.161 0.00 0.00 0.00 0.44 0.32 0.02 0.08 0.14
#&gt; TCGA.AB.2996.03     3  0.4019      0.687 0.00 0.00 0.74 0.00 0.00 0.06 0.14 0.06
#&gt; TCGA.AB.2936.03     4  0.0471      0.502 0.02 0.00 0.00 0.98 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2821.03     1  0.0000      0.912 1.00 0.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2863.03     1  0.0000      0.912 1.00 0.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2923.03     8  0.3318      0.000 0.00 0.46 0.00 0.00 0.00 0.00 0.00 0.54
#&gt; TCGA.AB.2901.03     1  0.3504      0.570 0.70 0.00 0.00 0.00 0.04 0.00 0.00 0.26
#&gt; TCGA.AB.2854.03     5  0.3618      0.976 0.00 0.00 0.38 0.00 0.60 0.02 0.00 0.00
</code></pre>

<script>
$('#tab-node-0222-get-classes-7-a').parent().next().next().hide();
$('#tab-node-0222-get-classes-7-a').click(function(){
  $('#tab-node-0222-get-classes-7-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>
</div>

Heatmaps for the consensus matrix. It visualizes the probability of two
samples to be in a same group.




<script>
$( function() {
	$( '#tabs-node-0222-consensus-heatmap' ).tabs();
} );
</script>
<div id='tabs-node-0222-consensus-heatmap'>
<ul>
<li><a href='#tab-node-0222-consensus-heatmap-1'>k = 2</a></li>
<li><a href='#tab-node-0222-consensus-heatmap-2'>k = 3</a></li>
<li><a href='#tab-node-0222-consensus-heatmap-3'>k = 4</a></li>
<li><a href='#tab-node-0222-consensus-heatmap-4'>k = 5</a></li>
<li><a href='#tab-node-0222-consensus-heatmap-5'>k = 6</a></li>
<li><a href='#tab-node-0222-consensus-heatmap-6'>k = 7</a></li>
<li><a href='#tab-node-0222-consensus-heatmap-7'>k = 8</a></li>
</ul>
<div id='tab-node-0222-consensus-heatmap-1'>
<pre><code class="r">consensus_heatmap(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-0222-consensus-heatmap-1-1.png" alt="plot of chunk tab-node-0222-consensus-heatmap-1"/></p>

</div>
<div id='tab-node-0222-consensus-heatmap-2'>
<pre><code class="r">consensus_heatmap(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-0222-consensus-heatmap-2-1.png" alt="plot of chunk tab-node-0222-consensus-heatmap-2"/></p>

</div>
<div id='tab-node-0222-consensus-heatmap-3'>
<pre><code class="r">consensus_heatmap(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-0222-consensus-heatmap-3-1.png" alt="plot of chunk tab-node-0222-consensus-heatmap-3"/></p>

</div>
<div id='tab-node-0222-consensus-heatmap-4'>
<pre><code class="r">consensus_heatmap(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-0222-consensus-heatmap-4-1.png" alt="plot of chunk tab-node-0222-consensus-heatmap-4"/></p>

</div>
<div id='tab-node-0222-consensus-heatmap-5'>
<pre><code class="r">consensus_heatmap(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-0222-consensus-heatmap-5-1.png" alt="plot of chunk tab-node-0222-consensus-heatmap-5"/></p>

</div>
<div id='tab-node-0222-consensus-heatmap-6'>
<pre><code class="r">consensus_heatmap(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-0222-consensus-heatmap-6-1.png" alt="plot of chunk tab-node-0222-consensus-heatmap-6"/></p>

</div>
<div id='tab-node-0222-consensus-heatmap-7'>
<pre><code class="r">consensus_heatmap(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-0222-consensus-heatmap-7-1.png" alt="plot of chunk tab-node-0222-consensus-heatmap-7"/></p>

</div>
</div>

Heatmaps for the membership of samples in all partitions to see how consistent they are:





<script>
$( function() {
	$( '#tabs-node-0222-membership-heatmap' ).tabs();
} );
</script>
<div id='tabs-node-0222-membership-heatmap'>
<ul>
<li><a href='#tab-node-0222-membership-heatmap-1'>k = 2</a></li>
<li><a href='#tab-node-0222-membership-heatmap-2'>k = 3</a></li>
<li><a href='#tab-node-0222-membership-heatmap-3'>k = 4</a></li>
<li><a href='#tab-node-0222-membership-heatmap-4'>k = 5</a></li>
<li><a href='#tab-node-0222-membership-heatmap-5'>k = 6</a></li>
<li><a href='#tab-node-0222-membership-heatmap-6'>k = 7</a></li>
<li><a href='#tab-node-0222-membership-heatmap-7'>k = 8</a></li>
</ul>
<div id='tab-node-0222-membership-heatmap-1'>
<pre><code class="r">membership_heatmap(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-0222-membership-heatmap-1-1.png" alt="plot of chunk tab-node-0222-membership-heatmap-1"/></p>

</div>
<div id='tab-node-0222-membership-heatmap-2'>
<pre><code class="r">membership_heatmap(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-0222-membership-heatmap-2-1.png" alt="plot of chunk tab-node-0222-membership-heatmap-2"/></p>

</div>
<div id='tab-node-0222-membership-heatmap-3'>
<pre><code class="r">membership_heatmap(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-0222-membership-heatmap-3-1.png" alt="plot of chunk tab-node-0222-membership-heatmap-3"/></p>

</div>
<div id='tab-node-0222-membership-heatmap-4'>
<pre><code class="r">membership_heatmap(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-0222-membership-heatmap-4-1.png" alt="plot of chunk tab-node-0222-membership-heatmap-4"/></p>

</div>
<div id='tab-node-0222-membership-heatmap-5'>
<pre><code class="r">membership_heatmap(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-0222-membership-heatmap-5-1.png" alt="plot of chunk tab-node-0222-membership-heatmap-5"/></p>

</div>
<div id='tab-node-0222-membership-heatmap-6'>
<pre><code class="r">membership_heatmap(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-0222-membership-heatmap-6-1.png" alt="plot of chunk tab-node-0222-membership-heatmap-6"/></p>

</div>
<div id='tab-node-0222-membership-heatmap-7'>
<pre><code class="r">membership_heatmap(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-0222-membership-heatmap-7-1.png" alt="plot of chunk tab-node-0222-membership-heatmap-7"/></p>

</div>
</div>

As soon as the classes for columns are determined, the signatures
that are significantly different between subgroups can be looked for. 
Following are the heatmaps for signatures.






<script>
$( function() {
	$( '#tabs-node-0222-get-signatures' ).tabs();
} );
</script>
<div id='tabs-node-0222-get-signatures'>
<ul>
<li><a href='#tab-node-0222-get-signatures-1'>k = 2</a></li>
<li><a href='#tab-node-0222-get-signatures-2'>k = 3</a></li>
<li><a href='#tab-node-0222-get-signatures-3'>k = 4</a></li>
<li><a href='#tab-node-0222-get-signatures-4'>k = 5</a></li>
<li><a href='#tab-node-0222-get-signatures-5'>k = 6</a></li>
<li><a href='#tab-node-0222-get-signatures-6'>k = 7</a></li>
<li><a href='#tab-node-0222-get-signatures-7'>k = 8</a></li>
</ul>
<div id='tab-node-0222-get-signatures-1'>
<pre><code class="r">get_signatures(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-0222-get-signatures-1-1.png" alt="plot of chunk tab-node-0222-get-signatures-1"/></p>

</div>
<div id='tab-node-0222-get-signatures-2'>
<pre><code class="r">get_signatures(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-0222-get-signatures-2-1.png" alt="plot of chunk tab-node-0222-get-signatures-2"/></p>

</div>
<div id='tab-node-0222-get-signatures-3'>
<pre><code class="r">get_signatures(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-0222-get-signatures-3-1.png" alt="plot of chunk tab-node-0222-get-signatures-3"/></p>

</div>
<div id='tab-node-0222-get-signatures-4'>
<pre><code class="r">get_signatures(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-0222-get-signatures-4-1.png" alt="plot of chunk tab-node-0222-get-signatures-4"/></p>

</div>
<div id='tab-node-0222-get-signatures-5'>
<pre><code class="r">get_signatures(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-0222-get-signatures-5-1.png" alt="plot of chunk tab-node-0222-get-signatures-5"/></p>

</div>
<div id='tab-node-0222-get-signatures-6'>
<pre><code class="r">get_signatures(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-0222-get-signatures-6-1.png" alt="plot of chunk tab-node-0222-get-signatures-6"/></p>

</div>
<div id='tab-node-0222-get-signatures-7'>
<pre><code class="r">get_signatures(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-0222-get-signatures-7-1.png" alt="plot of chunk tab-node-0222-get-signatures-7"/></p>

</div>
</div>



Compare the overlap of signatures from different k:

```r
compare_signatures(res)
```

![plot of chunk node-0222-signature_compare](figure_cola/node-0222-signature_compare-1.png)

`get_signature()` returns a data frame invisibly. To get the list of signatures, the function
call should be assigned to a variable explicitly. In following code, if `plot` argument is set
to `FALSE`, no heatmap is plotted while only the differential analysis is performed.

```r
# code only for demonstration
tb = get_signature(res, k = ..., plot = FALSE)
```

An example of the output of `tb` is:

```
#>   which_row         fdr    mean_1    mean_2 scaled_mean_1 scaled_mean_2 km
#> 1        38 0.042760348  8.373488  9.131774    -0.5533452     0.5164555  1
#> 2        40 0.018707592  7.106213  8.469186    -0.6173731     0.5762149  1
#> 3        55 0.019134737 10.221463 11.207825    -0.6159697     0.5749050  1
#> 4        59 0.006059896  5.921854  7.869574    -0.6899429     0.6439467  1
#> 5        60 0.018055526  8.928898 10.211722    -0.6204761     0.5791110  1
#> 6        98 0.009384629 15.714769 14.887706     0.6635654    -0.6193277  2
...
```

The columns in `tb` are:

1. `which_row`: row indices corresponding to the input matrix.
2. `fdr`: FDR for the differential test. 
3. `mean_x`: The mean value in group x.
4. `scaled_mean_x`: The mean value in group x after rows are scaled.
5. `km`: Row groups if k-means clustering is applied to rows (which is done by automatically selecting number of clusters).

If there are too many signatures, `top_signatures = ...` can be set to only show the 
signatures with the highest FDRs:

```r
# code only for demonstration
# e.g. to show the top 500 most significant rows
tb = get_signature(res, k = ..., top_signatures = 500)
```

If the signatures are defined as these which are uniquely high in current group, `diff_method` argument
can be set to `"uniquely_high_in_one_group"`:

```r
# code only for demonstration
tb = get_signature(res, k = ..., diff_method = "uniquely_high_in_one_group")
```




UMAP plot which shows how samples are separated.


<script>
$( function() {
	$( '#tabs-node-0222-dimension-reduction' ).tabs();
} );
</script>
<div id='tabs-node-0222-dimension-reduction'>
<ul>
<li><a href='#tab-node-0222-dimension-reduction-1'>k = 2</a></li>
<li><a href='#tab-node-0222-dimension-reduction-2'>k = 3</a></li>
<li><a href='#tab-node-0222-dimension-reduction-3'>k = 4</a></li>
<li><a href='#tab-node-0222-dimension-reduction-4'>k = 5</a></li>
<li><a href='#tab-node-0222-dimension-reduction-5'>k = 6</a></li>
<li><a href='#tab-node-0222-dimension-reduction-6'>k = 7</a></li>
<li><a href='#tab-node-0222-dimension-reduction-7'>k = 8</a></li>
</ul>
<div id='tab-node-0222-dimension-reduction-1'>
<pre><code class="r">dimension_reduction(res, k = 2, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-0222-dimension-reduction-1-1.png" alt="plot of chunk tab-node-0222-dimension-reduction-1"/></p>

</div>
<div id='tab-node-0222-dimension-reduction-2'>
<pre><code class="r">dimension_reduction(res, k = 3, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-0222-dimension-reduction-2-1.png" alt="plot of chunk tab-node-0222-dimension-reduction-2"/></p>

</div>
<div id='tab-node-0222-dimension-reduction-3'>
<pre><code class="r">dimension_reduction(res, k = 4, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-0222-dimension-reduction-3-1.png" alt="plot of chunk tab-node-0222-dimension-reduction-3"/></p>

</div>
<div id='tab-node-0222-dimension-reduction-4'>
<pre><code class="r">dimension_reduction(res, k = 5, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-0222-dimension-reduction-4-1.png" alt="plot of chunk tab-node-0222-dimension-reduction-4"/></p>

</div>
<div id='tab-node-0222-dimension-reduction-5'>
<pre><code class="r">dimension_reduction(res, k = 6, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-0222-dimension-reduction-5-1.png" alt="plot of chunk tab-node-0222-dimension-reduction-5"/></p>

</div>
<div id='tab-node-0222-dimension-reduction-6'>
<pre><code class="r">dimension_reduction(res, k = 7, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-0222-dimension-reduction-6-1.png" alt="plot of chunk tab-node-0222-dimension-reduction-6"/></p>

</div>
<div id='tab-node-0222-dimension-reduction-7'>
<pre><code class="r">dimension_reduction(res, k = 8, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-0222-dimension-reduction-7-1.png" alt="plot of chunk tab-node-0222-dimension-reduction-7"/></p>

</div>
</div>



Following heatmap shows how subgroups are split when increasing `k`:

```r
collect_classes(res)
```

![plot of chunk node-0222-collect-classes](figure_cola/node-0222-collect-classes-1.png)



If matrix rows can be associated to genes, consider to use `functional_enrichment(res,
...)` to perform function enrichment for the signature genes. See [this vignette](https://jokergoo.github.io/cola_vignettes/functional_enrichment.html) for more detailed explanations.


 

---------------------------------------------------




### Node023


Parent node: [Node02](#Node02).
Child nodes: 
                Node0111-leaf
        ,
                Node0112-leaf
        ,
                Node0131-leaf
        ,
                Node0132-leaf
        ,
                Node0141-leaf
        ,
                Node0142-leaf
        ,
                Node0211-leaf
        ,
                Node0212-leaf
        ,
                Node0213-leaf
        ,
                Node0221-leaf
        ,
                [Node0222](#Node0222)
        ,
                Node0231-leaf
        ,
                Node0232-leaf
        ,
                Node0233-leaf
        ,
                Node0321-leaf
        ,
                Node0322-leaf
        ,
                Node0323-leaf
        ,
                Node0324-leaf
        ,
                Node0325-leaf
        ,
                Node0331-leaf
        ,
                Node0332-leaf
        .







The object with results only for a single top-value method and a single partitioning method 
can be extracted as:

```r
res = res_rh["023"]
```

A summary of `res` and all the functions that can be applied to it:

```r
res
```

```
#> A 'ConsensusPartition' object with k = 2, 3, 4, 5, 6, 7, 8.
#>   On a matrix with 30000 rows and 36 columns.
#>   Top rows (1000) are extracted by 'ATC' method.
#>   Subgroups are detected by 'kmeans' method.
#>   Performed in total 350 partitions by row resampling.
#>   Best k for subgroups seems to be 3.
#> 
#> Following methods can be applied to this 'ConsensusPartition' object:
#>  [1] "cola_report"             "collect_classes"         "collect_plots"          
#>  [4] "collect_stats"           "colnames"                "compare_partitions"     
#>  [7] "compare_signatures"      "consensus_heatmap"       "dimension_reduction"    
#> [10] "functional_enrichment"   "get_anno_col"            "get_anno"               
#> [13] "get_classes"             "get_consensus"           "get_matrix"             
#> [16] "get_membership"          "get_param"               "get_signatures"         
#> [19] "get_stats"               "is_best_k"               "is_stable_k"            
#> [22] "membership_heatmap"      "ncol"                    "nrow"                   
#> [25] "plot_ecdf"               "predict_classes"         "rownames"               
#> [28] "select_partition_number" "show"                    "suggest_best_k"         
#> [31] "test_to_known_factors"   "top_rows_heatmap"
```

`collect_plots()` function collects all the plots made from `res` for all `k` (number of subgroups)
into one single page to provide an easy and fast comparison between different `k`.

```r
collect_plots(res)
```

![plot of chunk node-023-collect-plots](figure_cola/node-023-collect-plots-1.png)

The plots are:

- The first row: a plot of the eCDF (empirical cumulative distribution
  function) curves of the consensus matrix for each `k` and the heatmap of
  predicted classes for each `k`.
- The second row: heatmaps of the consensus matrix for each `k`.
- The third row: heatmaps of the membership matrix for each `k`.
- The fouth row: heatmaps of the signatures for each `k`.

All the plots in panels can be made by individual functions and they are
plotted later in this section.

`select_partition_number()` produces several plots showing different
statistics for choosing "optimized" `k`. There are following statistics:

- eCDF curves of the consensus matrix for each `k`;
- 1-PAC. [The PAC score](https://en.wikipedia.org/wiki/Consensus_clustering#Over-interpretation_potential_of_consensus_clustering)
  measures the proportion of the ambiguous subgrouping.
- Mean silhouette score.
- Concordance. The mean probability of fiting the consensus subgroup labels in all
  partitions.
- Area increased. Denote $A_k$ as the area under the eCDF curve for current
  `k`, the area increased is defined as $A_k - A_{k-1}$.
- Rand index. The percent of pairs of samples that are both in a same cluster
  or both are not in a same cluster in the partition of k and k-1.
- Jaccard index. The ratio of pairs of samples are both in a same cluster in
  the partition of k and k-1 and the pairs of samples are both in a same
  cluster in the partition k or k-1.

The detailed explanations of these statistics can be found in [the _cola_
vignette](https://jokergoo.github.io/cola_vignettes/cola.html#toc_13).

Generally speaking, higher 1-PAC score, higher mean silhouette score or higher
concordance corresponds to better partition. Rand index and Jaccard index
measure how similar the current partition is compared to partition with `k-1`.
If they are too similar, we won't accept `k` is better than `k-1`.

```r
select_partition_number(res)
```

![plot of chunk node-023-select-partition-number](figure_cola/node-023-select-partition-number-1.png)

The numeric values for all these statistics can be obtained by `get_stats()`.

```r
get_stats(res)
```

```
#>   k 1-PAC mean_silhouette concordance area_increased  Rand Jaccard
#> 2 2 1.000           0.929       0.974         0.2419 0.797   0.797
#> 3 3 1.000           0.974       0.989         1.4867 0.600   0.498
#> 4 4 0.671           0.520       0.767         0.1285 0.894   0.742
#> 5 5 0.825           0.903       0.928         0.0864 0.848   0.584
#> 6 6 0.827           0.884       0.917         0.0710 0.892   0.611
#> 7 7 0.975           0.896       0.935         0.0372 1.000   1.000
#> 8 8 0.868           0.785       0.897         0.0195 0.992   0.958
```

`suggest_best_k()` suggests the best $k$ based on these statistics. The rules are as follows:

- All $k$ with Jaccard index larger than 0.95 are removed because increasing
  $k$ does not provide enough extra information. If all $k$ are removed, it is
  marked as no subgroup is detected.
- For all $k$ with 1-PAC score larger than 0.9, the maximal $k$ is taken as
  the best $k$, and other $k$ are marked as optional $k$.
- If it does not fit the second rule. The $k$ with the maximal vote of the
  highest 1-PAC score, highest mean silhouette, and highest concordance is
  taken as the best $k$.

```r
suggest_best_k(res)
```

```
#> [1] 3
#> attr(,"optional")
#> [1] 2
```

There is also optional best $k$ = 2 that is worth to check.

Following is the table of the partitions (You need to click the **show/hide
code output** link to see it). The membership matrix (columns with name `p*`)
is inferred by
[`clue::cl_consensus()`](https://www.rdocumentation.org/link/cl_consensus?package=clue)
function with the `SE` method. Basically the value in the membership matrix
represents the probability to belong to a certain group. The finall subgroup
label for an item is determined with the group with highest probability it
belongs to.

In `get_classes()` function, the entropy is calculated from the membership
matrix and the silhouette score is calculated from the consensus matrix.



<script>
$( function() {
	$( '#tabs-node-023-get-classes' ).tabs();
} );
</script>
<div id='tabs-node-023-get-classes'>
<ul>
<li><a href='#tab-node-023-get-classes-1'>k = 2</a></li>
<li><a href='#tab-node-023-get-classes-2'>k = 3</a></li>
<li><a href='#tab-node-023-get-classes-3'>k = 4</a></li>
<li><a href='#tab-node-023-get-classes-4'>k = 5</a></li>
<li><a href='#tab-node-023-get-classes-5'>k = 6</a></li>
<li><a href='#tab-node-023-get-classes-6'>k = 7</a></li>
<li><a href='#tab-node-023-get-classes-7'>k = 8</a></li>
</ul>

<div id='tab-node-023-get-classes-1'>
<p><a id='tab-node-023-get-classes-1-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 2), get_membership(res, k = 2))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2
#&gt; TCGA.AB.2878.03     1   0.000      0.969 1.00 0.00
#&gt; TCGA.AB.2843.03     1   0.000      0.969 1.00 0.00
#&gt; TCGA.AB.2807.03     1   0.995      0.176 0.54 0.46
#&gt; TCGA.AB.2847.03     1   0.000      0.969 1.00 0.00
#&gt; TCGA.AB.2814.03     1   0.000      0.969 1.00 0.00
#&gt; TCGA.AB.2922.03     1   0.000      0.969 1.00 0.00
#&gt; TCGA.AB.2933.03     1   0.000      0.969 1.00 0.00
#&gt; TCGA.AB.2915.03     1   0.000      0.969 1.00 0.00
#&gt; TCGA.AB.2970.03     1   0.000      0.969 1.00 0.00
#&gt; TCGA.AB.2949.03     1   0.000      0.969 1.00 0.00
#&gt; TCGA.AB.2912.03     1   0.995      0.176 0.54 0.46
#&gt; TCGA.AB.2838.03     1   0.000      0.969 1.00 0.00
#&gt; TCGA.AB.2891.03     2   0.000      1.000 0.00 1.00
#&gt; TCGA.AB.2944.03     2   0.000      1.000 0.00 1.00
#&gt; TCGA.AB.2904.03     1   0.000      0.969 1.00 0.00
#&gt; TCGA.AB.2917.03     1   0.000      0.969 1.00 0.00
#&gt; TCGA.AB.2817.03     1   0.000      0.969 1.00 0.00
#&gt; TCGA.AB.2857.03     1   0.000      0.969 1.00 0.00
#&gt; TCGA.AB.2983.03     1   0.000      0.969 1.00 0.00
#&gt; TCGA.AB.2920.03     1   0.000      0.969 1.00 0.00
#&gt; TCGA.AB.2927.03     1   0.000      0.969 1.00 0.00
#&gt; TCGA.AB.2885.03     1   0.000      0.969 1.00 0.00
#&gt; TCGA.AB.2966.03     2   0.000      1.000 0.00 1.00
#&gt; TCGA.AB.2820.03     1   0.000      0.969 1.00 0.00
#&gt; TCGA.AB.2899.03     1   0.000      0.969 1.00 0.00
#&gt; TCGA.AB.2849.03     2   0.000      1.000 0.00 1.00
#&gt; TCGA.AB.2882.03     1   0.000      0.969 1.00 0.00
#&gt; TCGA.AB.2952.03     1   0.000      0.969 1.00 0.00
#&gt; TCGA.AB.2868.03     1   0.000      0.969 1.00 0.00
#&gt; TCGA.AB.2908.03     1   0.000      0.969 1.00 0.00
#&gt; TCGA.AB.2890.03     1   0.000      0.969 1.00 0.00
#&gt; TCGA.AB.2943.03     1   0.000      0.969 1.00 0.00
#&gt; TCGA.AB.2813.03     1   0.000      0.969 1.00 0.00
#&gt; TCGA.AB.2935.03     1   0.000      0.969 1.00 0.00
#&gt; TCGA.AB.2929.03     1   0.000      0.969 1.00 0.00
#&gt; TCGA.AB.2860.03     1   0.000      0.969 1.00 0.00
</code></pre>

<script>
$('#tab-node-023-get-classes-1-a').parent().next().next().hide();
$('#tab-node-023-get-classes-1-a').click(function(){
  $('#tab-node-023-get-classes-1-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-023-get-classes-2'>
<p><a id='tab-node-023-get-classes-2-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 3), get_membership(res, k = 3))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1 p2   p3
#&gt; TCGA.AB.2878.03     3   0.254      0.900 0.08  0 0.92
#&gt; TCGA.AB.2843.03     1   0.000      0.991 1.00  0 0.00
#&gt; TCGA.AB.2807.03     3   0.000      0.974 0.00  0 1.00
#&gt; TCGA.AB.2847.03     3   0.334      0.848 0.12  0 0.88
#&gt; TCGA.AB.2814.03     3   0.000      0.974 0.00  0 1.00
#&gt; TCGA.AB.2922.03     1   0.000      0.991 1.00  0 0.00
#&gt; TCGA.AB.2933.03     1   0.000      0.991 1.00  0 0.00
#&gt; TCGA.AB.2915.03     1   0.000      0.991 1.00  0 0.00
#&gt; TCGA.AB.2970.03     3   0.000      0.974 0.00  0 1.00
#&gt; TCGA.AB.2949.03     1   0.000      0.991 1.00  0 0.00
#&gt; TCGA.AB.2912.03     3   0.000      0.974 0.00  0 1.00
#&gt; TCGA.AB.2838.03     3   0.000      0.974 0.00  0 1.00
#&gt; TCGA.AB.2891.03     2   0.000      1.000 0.00  1 0.00
#&gt; TCGA.AB.2944.03     2   0.000      1.000 0.00  1 0.00
#&gt; TCGA.AB.2904.03     1   0.000      0.991 1.00  0 0.00
#&gt; TCGA.AB.2917.03     3   0.000      0.974 0.00  0 1.00
#&gt; TCGA.AB.2817.03     1   0.000      0.991 1.00  0 0.00
#&gt; TCGA.AB.2857.03     1   0.000      0.991 1.00  0 0.00
#&gt; TCGA.AB.2983.03     1   0.000      0.991 1.00  0 0.00
#&gt; TCGA.AB.2920.03     3   0.000      0.974 0.00  0 1.00
#&gt; TCGA.AB.2927.03     1   0.000      0.991 1.00  0 0.00
#&gt; TCGA.AB.2885.03     1   0.000      0.991 1.00  0 0.00
#&gt; TCGA.AB.2966.03     2   0.000      1.000 0.00  1 0.00
#&gt; TCGA.AB.2820.03     1   0.000      0.991 1.00  0 0.00
#&gt; TCGA.AB.2899.03     3   0.000      0.974 0.00  0 1.00
#&gt; TCGA.AB.2849.03     2   0.000      1.000 0.00  1 0.00
#&gt; TCGA.AB.2882.03     3   0.207      0.921 0.06  0 0.94
#&gt; TCGA.AB.2952.03     3   0.000      0.974 0.00  0 1.00
#&gt; TCGA.AB.2868.03     1   0.000      0.991 1.00  0 0.00
#&gt; TCGA.AB.2908.03     1   0.000      0.991 1.00  0 0.00
#&gt; TCGA.AB.2890.03     1   0.000      0.991 1.00  0 0.00
#&gt; TCGA.AB.2943.03     1   0.000      0.991 1.00  0 0.00
#&gt; TCGA.AB.2813.03     1   0.000      0.991 1.00  0 0.00
#&gt; TCGA.AB.2935.03     1   0.334      0.842 0.88  0 0.12
#&gt; TCGA.AB.2929.03     3   0.000      0.974 0.00  0 1.00
#&gt; TCGA.AB.2860.03     3   0.000      0.974 0.00  0 1.00
</code></pre>

<script>
$('#tab-node-023-get-classes-2-a').parent().next().next().hide();
$('#tab-node-023-get-classes-2-a').click(function(){
  $('#tab-node-023-get-classes-2-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-023-get-classes-3'>
<p><a id='tab-node-023-get-classes-3-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 4), get_membership(res, k = 4))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1 p2   p3   p4
#&gt; TCGA.AB.2878.03     4  0.4994     1.0000 0.00  0 0.48 0.52
#&gt; TCGA.AB.2843.03     1  0.0000     0.9033 1.00  0 0.00 0.00
#&gt; TCGA.AB.2807.03     3  0.4994     0.0661 0.00  0 0.52 0.48
#&gt; TCGA.AB.2847.03     3  0.7021    -0.6011 0.12  0 0.48 0.40
#&gt; TCGA.AB.2814.03     3  0.0000     0.2361 0.00  0 1.00 0.00
#&gt; TCGA.AB.2922.03     1  0.0000     0.9033 1.00  0 0.00 0.00
#&gt; TCGA.AB.2933.03     1  0.0000     0.9033 1.00  0 0.00 0.00
#&gt; TCGA.AB.2915.03     1  0.2647     0.8190 0.88  0 0.00 0.12
#&gt; TCGA.AB.2970.03     3  0.0707     0.2223 0.00  0 0.98 0.02
#&gt; TCGA.AB.2949.03     1  0.0000     0.9033 1.00  0 0.00 0.00
#&gt; TCGA.AB.2912.03     3  0.4994     0.0661 0.00  0 0.52 0.48
#&gt; TCGA.AB.2838.03     3  0.4855    -0.6289 0.00  0 0.60 0.40
#&gt; TCGA.AB.2891.03     2  0.0000     1.0000 0.00  1 0.00 0.00
#&gt; TCGA.AB.2944.03     2  0.0000     1.0000 0.00  1 0.00 0.00
#&gt; TCGA.AB.2904.03     1  0.0000     0.9033 1.00  0 0.00 0.00
#&gt; TCGA.AB.2917.03     4  0.4994     1.0000 0.00  0 0.48 0.52
#&gt; TCGA.AB.2817.03     1  0.0000     0.9033 1.00  0 0.00 0.00
#&gt; TCGA.AB.2857.03     1  0.0000     0.9033 1.00  0 0.00 0.00
#&gt; TCGA.AB.2983.03     1  0.0000     0.9033 1.00  0 0.00 0.00
#&gt; TCGA.AB.2920.03     3  0.4855    -0.6289 0.00  0 0.60 0.40
#&gt; TCGA.AB.2927.03     1  0.2647     0.8190 0.88  0 0.00 0.12
#&gt; TCGA.AB.2885.03     1  0.7021    -0.0477 0.48  0 0.12 0.40
#&gt; TCGA.AB.2966.03     2  0.0000     1.0000 0.00  1 0.00 0.00
#&gt; TCGA.AB.2820.03     1  0.0000     0.9033 1.00  0 0.00 0.00
#&gt; TCGA.AB.2899.03     3  0.0000     0.2361 0.00  0 1.00 0.00
#&gt; TCGA.AB.2849.03     2  0.0000     1.0000 0.00  1 0.00 0.00
#&gt; TCGA.AB.2882.03     4  0.4994     1.0000 0.00  0 0.48 0.52
#&gt; TCGA.AB.2952.03     3  0.4855    -0.6289 0.00  0 0.60 0.40
#&gt; TCGA.AB.2868.03     1  0.4522     0.5380 0.68  0 0.00 0.32
#&gt; TCGA.AB.2908.03     1  0.0000     0.9033 1.00  0 0.00 0.00
#&gt; TCGA.AB.2890.03     1  0.0000     0.9033 1.00  0 0.00 0.00
#&gt; TCGA.AB.2943.03     1  0.4406     0.6560 0.70  0 0.00 0.30
#&gt; TCGA.AB.2813.03     1  0.0000     0.9033 1.00  0 0.00 0.00
#&gt; TCGA.AB.2935.03     3  0.7206    -0.5635 0.14  0 0.46 0.40
#&gt; TCGA.AB.2929.03     4  0.4994     1.0000 0.00  0 0.48 0.52
#&gt; TCGA.AB.2860.03     3  0.4907    -0.6859 0.00  0 0.58 0.42
</code></pre>

<script>
$('#tab-node-023-get-classes-3-a').parent().next().next().hide();
$('#tab-node-023-get-classes-3-a').click(function(){
  $('#tab-node-023-get-classes-3-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-023-get-classes-4'>
<p><a id='tab-node-023-get-classes-4-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 5), get_membership(res, k = 5))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5
#&gt; TCGA.AB.2878.03     4  0.2929      0.816 0.00 0.00 0.18 0.82 0.00
#&gt; TCGA.AB.2843.03     1  0.0000      0.964 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2807.03     5  0.0000      1.000 0.00 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2847.03     3  0.1410      0.916 0.00 0.00 0.94 0.06 0.00
#&gt; TCGA.AB.2814.03     4  0.2797      0.795 0.00 0.00 0.06 0.88 0.06
#&gt; TCGA.AB.2922.03     1  0.0000      0.964 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2933.03     1  0.0000      0.964 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2915.03     1  0.2280      0.870 0.88 0.00 0.00 0.12 0.00
#&gt; TCGA.AB.2970.03     4  0.2438      0.797 0.00 0.00 0.04 0.90 0.06
#&gt; TCGA.AB.2949.03     1  0.0000      0.964 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2912.03     5  0.0000      1.000 0.00 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2838.03     3  0.1410      0.916 0.00 0.00 0.94 0.06 0.00
#&gt; TCGA.AB.2891.03     2  0.0609      0.977 0.00 0.98 0.02 0.00 0.00
#&gt; TCGA.AB.2944.03     2  0.1043      0.965 0.00 0.96 0.04 0.00 0.00
#&gt; TCGA.AB.2904.03     1  0.0000      0.964 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2917.03     4  0.2929      0.816 0.00 0.00 0.18 0.82 0.00
#&gt; TCGA.AB.2817.03     1  0.0000      0.964 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2857.03     1  0.0000      0.964 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2983.03     1  0.0000      0.964 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2920.03     3  0.1410      0.916 0.00 0.00 0.94 0.06 0.00
#&gt; TCGA.AB.2927.03     1  0.2280      0.870 0.88 0.00 0.00 0.12 0.00
#&gt; TCGA.AB.2885.03     3  0.2331      0.855 0.08 0.00 0.90 0.02 0.00
#&gt; TCGA.AB.2966.03     2  0.0000      0.984 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2820.03     1  0.0000      0.964 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2899.03     4  0.2754      0.786 0.00 0.00 0.04 0.88 0.08
#&gt; TCGA.AB.2849.03     2  0.0000      0.984 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2882.03     4  0.2929      0.816 0.00 0.00 0.18 0.82 0.00
#&gt; TCGA.AB.2952.03     4  0.3690      0.829 0.00 0.00 0.20 0.78 0.02
#&gt; TCGA.AB.2868.03     3  0.2732      0.744 0.16 0.00 0.84 0.00 0.00
#&gt; TCGA.AB.2908.03     1  0.0000      0.964 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2890.03     1  0.0000      0.964 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2943.03     1  0.4458      0.723 0.76 0.00 0.12 0.12 0.00
#&gt; TCGA.AB.2813.03     1  0.0000      0.964 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2935.03     3  0.1410      0.916 0.00 0.00 0.94 0.06 0.00
#&gt; TCGA.AB.2929.03     4  0.3424      0.814 0.00 0.00 0.24 0.76 0.00
#&gt; TCGA.AB.2860.03     4  0.3690      0.829 0.00 0.00 0.20 0.78 0.02
</code></pre>

<script>
$('#tab-node-023-get-classes-4-a').parent().next().next().hide();
$('#tab-node-023-get-classes-4-a').click(function(){
  $('#tab-node-023-get-classes-4-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-023-get-classes-5'>
<p><a id='tab-node-023-get-classes-5-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 6), get_membership(res, k = 6))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5   p6
#&gt; TCGA.AB.2878.03     6  0.3544      0.702 0.00 0.00 0.08 0.12 0.00 0.80
#&gt; TCGA.AB.2843.03     1  0.0000      1.000 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2807.03     5  0.0000      0.976 0.00 0.00 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2847.03     3  0.2094      0.918 0.00 0.00 0.90 0.02 0.00 0.08
#&gt; TCGA.AB.2814.03     4  0.0000      0.888 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2922.03     1  0.0000      1.000 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2933.03     1  0.0000      1.000 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2915.03     6  0.3647      0.542 0.36 0.00 0.00 0.00 0.00 0.64
#&gt; TCGA.AB.2970.03     4  0.0547      0.891 0.00 0.00 0.00 0.98 0.00 0.02
#&gt; TCGA.AB.2949.03     1  0.0000      1.000 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2912.03     5  0.0937      0.976 0.00 0.00 0.00 0.00 0.96 0.04
#&gt; TCGA.AB.2838.03     3  0.1480      0.882 0.00 0.00 0.94 0.02 0.00 0.04
#&gt; TCGA.AB.2891.03     2  0.1092      0.952 0.00 0.96 0.02 0.00 0.00 0.02
#&gt; TCGA.AB.2944.03     2  0.1556      0.928 0.00 0.92 0.00 0.00 0.00 0.08
#&gt; TCGA.AB.2904.03     1  0.0000      1.000 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2917.03     6  0.3544      0.702 0.00 0.00 0.08 0.12 0.00 0.80
#&gt; TCGA.AB.2817.03     1  0.0000      1.000 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2857.03     1  0.0000      1.000 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2983.03     1  0.0000      1.000 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2920.03     3  0.1807      0.872 0.00 0.00 0.92 0.02 0.00 0.06
#&gt; TCGA.AB.2927.03     6  0.3647      0.542 0.36 0.00 0.00 0.00 0.00 0.64
#&gt; TCGA.AB.2885.03     3  0.2094      0.913 0.02 0.00 0.90 0.00 0.00 0.08
#&gt; TCGA.AB.2966.03     2  0.0000      0.966 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2820.03     1  0.0000      1.000 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2899.03     4  0.0000      0.888 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2849.03     2  0.0000      0.966 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2882.03     6  0.3544      0.702 0.00 0.00 0.08 0.12 0.00 0.80
#&gt; TCGA.AB.2952.03     4  0.3270      0.840 0.00 0.00 0.12 0.82 0.00 0.06
#&gt; TCGA.AB.2868.03     3  0.2794      0.873 0.06 0.00 0.86 0.00 0.00 0.08
#&gt; TCGA.AB.2908.03     1  0.0000      1.000 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2890.03     1  0.0000      1.000 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2943.03     6  0.3351      0.675 0.16 0.00 0.04 0.00 0.00 0.80
#&gt; TCGA.AB.2813.03     1  0.0000      1.000 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2935.03     3  0.2094      0.918 0.00 0.00 0.90 0.02 0.00 0.08
#&gt; TCGA.AB.2929.03     6  0.4711      0.495 0.00 0.00 0.08 0.28 0.00 0.64
#&gt; TCGA.AB.2860.03     4  0.3321      0.821 0.00 0.00 0.08 0.82 0.00 0.10
</code></pre>

<script>
$('#tab-node-023-get-classes-5-a').parent().next().next().hide();
$('#tab-node-023-get-classes-5-a').click(function(){
  $('#tab-node-023-get-classes-5-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-023-get-classes-6'>
<p><a id='tab-node-023-get-classes-6-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 7), get_membership(res, k = 7))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2  p3   p4  p5   p6   p7
#&gt; TCGA.AB.2878.03     6  0.0863      0.876 0.00 0.00 0.0 0.00 0.0 0.96 0.04
#&gt; TCGA.AB.2843.03     1  0.1166      0.961 0.94 0.00 0.0 0.06 0.0 0.00 0.00
#&gt; TCGA.AB.2807.03     5  0.0000      0.876 0.00 0.00 0.0 0.00 1.0 0.00 0.00
#&gt; TCGA.AB.2847.03     3  0.0000      0.870 0.00 0.00 1.0 0.00 0.0 0.00 0.00
#&gt; TCGA.AB.2814.03     7  0.2081      0.882 0.00 0.00 0.0 0.14 0.0 0.00 0.86
#&gt; TCGA.AB.2922.03     1  0.0000      0.981 1.00 0.00 0.0 0.00 0.0 0.00 0.00
#&gt; TCGA.AB.2933.03     1  0.0000      0.981 1.00 0.00 0.0 0.00 0.0 0.00 0.00
#&gt; TCGA.AB.2915.03     6  0.1166      0.862 0.06 0.00 0.0 0.00 0.0 0.94 0.00
#&gt; TCGA.AB.2970.03     7  0.0504      0.933 0.00 0.00 0.0 0.02 0.0 0.00 0.98
#&gt; TCGA.AB.2949.03     1  0.0000      0.981 1.00 0.00 0.0 0.00 0.0 0.00 0.00
#&gt; TCGA.AB.2912.03     5  0.2906      0.876 0.00 0.00 0.0 0.18 0.8 0.02 0.00
#&gt; TCGA.AB.2838.03     3  0.3139      0.726 0.00 0.00 0.7 0.30 0.0 0.00 0.00
#&gt; TCGA.AB.2891.03     2  0.1433      0.919 0.00 0.92 0.0 0.08 0.0 0.00 0.00
#&gt; TCGA.AB.2944.03     2  0.1664      0.919 0.00 0.92 0.0 0.06 0.0 0.02 0.00
#&gt; TCGA.AB.2904.03     1  0.1166      0.961 0.94 0.00 0.0 0.06 0.0 0.00 0.00
#&gt; TCGA.AB.2917.03     6  0.1718      0.864 0.00 0.00 0.0 0.04 0.0 0.92 0.04
#&gt; TCGA.AB.2817.03     1  0.0000      0.981 1.00 0.00 0.0 0.00 0.0 0.00 0.00
#&gt; TCGA.AB.2857.03     1  0.0504      0.979 0.98 0.00 0.0 0.02 0.0 0.00 0.00
#&gt; TCGA.AB.2983.03     1  0.0504      0.979 0.98 0.00 0.0 0.02 0.0 0.00 0.00
#&gt; TCGA.AB.2920.03     3  0.3459      0.646 0.00 0.00 0.6 0.40 0.0 0.00 0.00
#&gt; TCGA.AB.2927.03     6  0.1166      0.862 0.06 0.00 0.0 0.00 0.0 0.94 0.00
#&gt; TCGA.AB.2885.03     3  0.0000      0.870 0.00 0.00 1.0 0.00 0.0 0.00 0.00
#&gt; TCGA.AB.2966.03     2  0.0000      0.954 0.00 1.00 0.0 0.00 0.0 0.00 0.00
#&gt; TCGA.AB.2820.03     1  0.1166      0.961 0.94 0.00 0.0 0.06 0.0 0.00 0.00
#&gt; TCGA.AB.2899.03     7  0.1166      0.923 0.00 0.00 0.0 0.06 0.0 0.00 0.94
#&gt; TCGA.AB.2849.03     2  0.0000      0.954 0.00 1.00 0.0 0.00 0.0 0.00 0.00
#&gt; TCGA.AB.2882.03     6  0.0863      0.876 0.00 0.00 0.0 0.00 0.0 0.96 0.04
#&gt; TCGA.AB.2952.03     7  0.1006      0.937 0.00 0.00 0.0 0.02 0.0 0.02 0.96
#&gt; TCGA.AB.2868.03     3  0.0000      0.870 0.00 0.00 1.0 0.00 0.0 0.00 0.00
#&gt; TCGA.AB.2908.03     1  0.0000      0.981 1.00 0.00 0.0 0.00 0.0 0.00 0.00
#&gt; TCGA.AB.2890.03     1  0.0504      0.979 0.98 0.00 0.0 0.02 0.0 0.00 0.00
#&gt; TCGA.AB.2943.03     6  0.0863      0.873 0.04 0.00 0.0 0.00 0.0 0.96 0.00
#&gt; TCGA.AB.2813.03     1  0.0000      0.981 1.00 0.00 0.0 0.00 0.0 0.00 0.00
#&gt; TCGA.AB.2935.03     3  0.0000      0.870 0.00 0.00 1.0 0.00 0.0 0.00 0.00
#&gt; TCGA.AB.2929.03     6  0.4175      0.378 0.00 0.00 0.0 0.04 0.0 0.58 0.38
#&gt; TCGA.AB.2860.03     7  0.1006      0.937 0.00 0.00 0.0 0.02 0.0 0.02 0.96
</code></pre>

<script>
$('#tab-node-023-get-classes-6-a').parent().next().next().hide();
$('#tab-node-023-get-classes-6-a').click(function(){
  $('#tab-node-023-get-classes-6-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-023-get-classes-7'>
<p><a id='tab-node-023-get-classes-7-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 8), get_membership(res, k = 8))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5   p6   p7   p8
#&gt; TCGA.AB.2878.03     6  0.0000      0.890 0.00 0.00 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2843.03     1  0.2534      0.853 0.78 0.00 0.00 0.00 0.00 0.00 0.22 0.00
#&gt; TCGA.AB.2807.03     5  0.4100      0.670 0.00 0.00 0.00 0.00 0.58 0.00 0.36 0.06
#&gt; TCGA.AB.2847.03     3  0.0471      0.802 0.00 0.00 0.98 0.00 0.00 0.02 0.00 0.00
#&gt; TCGA.AB.2814.03     4  0.2623      0.811 0.00 0.00 0.00 0.84 0.00 0.00 0.10 0.06
#&gt; TCGA.AB.2922.03     1  0.0000      0.922 1.00 0.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2933.03     1  0.0000      0.922 1.00 0.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2915.03     6  0.0941      0.882 0.02 0.00 0.00 0.00 0.00 0.96 0.00 0.02
#&gt; TCGA.AB.2970.03     4  0.0808      0.864 0.00 0.00 0.00 0.96 0.00 0.00 0.04 0.00
#&gt; TCGA.AB.2949.03     1  0.0000      0.922 1.00 0.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2912.03     5  0.0000      0.670 0.00 0.00 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2838.03     3  0.4391     -0.528 0.00 0.00 0.50 0.00 0.00 0.00 0.08 0.42
#&gt; TCGA.AB.2891.03     2  0.2224      0.871 0.00 0.86 0.00 0.00 0.00 0.00 0.12 0.02
#&gt; TCGA.AB.2944.03     2  0.2680      0.858 0.00 0.84 0.02 0.00 0.00 0.00 0.02 0.12
#&gt; TCGA.AB.2904.03     1  0.2406      0.866 0.80 0.00 0.00 0.00 0.00 0.00 0.20 0.00
#&gt; TCGA.AB.2917.03     6  0.1341      0.851 0.00 0.00 0.00 0.00 0.00 0.92 0.08 0.00
#&gt; TCGA.AB.2817.03     1  0.0000      0.922 1.00 0.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2857.03     1  0.1563      0.913 0.90 0.00 0.00 0.00 0.00 0.00 0.10 0.00
#&gt; TCGA.AB.2983.03     1  0.1563      0.913 0.90 0.00 0.00 0.00 0.00 0.00 0.10 0.00
#&gt; TCGA.AB.2920.03     8  0.2938      0.000 0.00 0.00 0.30 0.00 0.00 0.00 0.00 0.70
#&gt; TCGA.AB.2927.03     6  0.0941      0.882 0.02 0.00 0.00 0.00 0.00 0.96 0.00 0.02
#&gt; TCGA.AB.2885.03     3  0.0471      0.802 0.00 0.00 0.98 0.00 0.00 0.02 0.00 0.00
#&gt; TCGA.AB.2966.03     2  0.0000      0.918 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2820.03     1  0.2534      0.853 0.78 0.00 0.00 0.00 0.00 0.00 0.22 0.00
#&gt; TCGA.AB.2899.03     4  0.1887      0.853 0.00 0.00 0.00 0.90 0.00 0.00 0.06 0.04
#&gt; TCGA.AB.2849.03     2  0.0000      0.918 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2882.03     6  0.0000      0.890 0.00 0.00 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2952.03     4  0.1765      0.841 0.00 0.00 0.00 0.88 0.00 0.00 0.00 0.12
#&gt; TCGA.AB.2868.03     3  0.0941      0.784 0.00 0.00 0.96 0.00 0.00 0.02 0.02 0.00
#&gt; TCGA.AB.2908.03     1  0.0000      0.922 1.00 0.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2890.03     1  0.1563      0.913 0.90 0.00 0.00 0.00 0.00 0.00 0.10 0.00
#&gt; TCGA.AB.2943.03     6  0.0471      0.888 0.00 0.00 0.00 0.00 0.00 0.98 0.00 0.02
#&gt; TCGA.AB.2813.03     1  0.0000      0.922 1.00 0.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2935.03     3  0.0471      0.802 0.00 0.00 0.98 0.00 0.00 0.02 0.00 0.00
#&gt; TCGA.AB.2929.03     6  0.4255      0.370 0.00 0.00 0.00 0.34 0.00 0.58 0.08 0.00
#&gt; TCGA.AB.2860.03     4  0.2132      0.829 0.00 0.00 0.00 0.88 0.00 0.08 0.00 0.04
</code></pre>

<script>
$('#tab-node-023-get-classes-7-a').parent().next().next().hide();
$('#tab-node-023-get-classes-7-a').click(function(){
  $('#tab-node-023-get-classes-7-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>
</div>

Heatmaps for the consensus matrix. It visualizes the probability of two
samples to be in a same group.




<script>
$( function() {
	$( '#tabs-node-023-consensus-heatmap' ).tabs();
} );
</script>
<div id='tabs-node-023-consensus-heatmap'>
<ul>
<li><a href='#tab-node-023-consensus-heatmap-1'>k = 2</a></li>
<li><a href='#tab-node-023-consensus-heatmap-2'>k = 3</a></li>
<li><a href='#tab-node-023-consensus-heatmap-3'>k = 4</a></li>
<li><a href='#tab-node-023-consensus-heatmap-4'>k = 5</a></li>
<li><a href='#tab-node-023-consensus-heatmap-5'>k = 6</a></li>
<li><a href='#tab-node-023-consensus-heatmap-6'>k = 7</a></li>
<li><a href='#tab-node-023-consensus-heatmap-7'>k = 8</a></li>
</ul>
<div id='tab-node-023-consensus-heatmap-1'>
<pre><code class="r">consensus_heatmap(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-023-consensus-heatmap-1-1.png" alt="plot of chunk tab-node-023-consensus-heatmap-1"/></p>

</div>
<div id='tab-node-023-consensus-heatmap-2'>
<pre><code class="r">consensus_heatmap(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-023-consensus-heatmap-2-1.png" alt="plot of chunk tab-node-023-consensus-heatmap-2"/></p>

</div>
<div id='tab-node-023-consensus-heatmap-3'>
<pre><code class="r">consensus_heatmap(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-023-consensus-heatmap-3-1.png" alt="plot of chunk tab-node-023-consensus-heatmap-3"/></p>

</div>
<div id='tab-node-023-consensus-heatmap-4'>
<pre><code class="r">consensus_heatmap(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-023-consensus-heatmap-4-1.png" alt="plot of chunk tab-node-023-consensus-heatmap-4"/></p>

</div>
<div id='tab-node-023-consensus-heatmap-5'>
<pre><code class="r">consensus_heatmap(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-023-consensus-heatmap-5-1.png" alt="plot of chunk tab-node-023-consensus-heatmap-5"/></p>

</div>
<div id='tab-node-023-consensus-heatmap-6'>
<pre><code class="r">consensus_heatmap(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-023-consensus-heatmap-6-1.png" alt="plot of chunk tab-node-023-consensus-heatmap-6"/></p>

</div>
<div id='tab-node-023-consensus-heatmap-7'>
<pre><code class="r">consensus_heatmap(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-023-consensus-heatmap-7-1.png" alt="plot of chunk tab-node-023-consensus-heatmap-7"/></p>

</div>
</div>

Heatmaps for the membership of samples in all partitions to see how consistent they are:





<script>
$( function() {
	$( '#tabs-node-023-membership-heatmap' ).tabs();
} );
</script>
<div id='tabs-node-023-membership-heatmap'>
<ul>
<li><a href='#tab-node-023-membership-heatmap-1'>k = 2</a></li>
<li><a href='#tab-node-023-membership-heatmap-2'>k = 3</a></li>
<li><a href='#tab-node-023-membership-heatmap-3'>k = 4</a></li>
<li><a href='#tab-node-023-membership-heatmap-4'>k = 5</a></li>
<li><a href='#tab-node-023-membership-heatmap-5'>k = 6</a></li>
<li><a href='#tab-node-023-membership-heatmap-6'>k = 7</a></li>
<li><a href='#tab-node-023-membership-heatmap-7'>k = 8</a></li>
</ul>
<div id='tab-node-023-membership-heatmap-1'>
<pre><code class="r">membership_heatmap(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-023-membership-heatmap-1-1.png" alt="plot of chunk tab-node-023-membership-heatmap-1"/></p>

</div>
<div id='tab-node-023-membership-heatmap-2'>
<pre><code class="r">membership_heatmap(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-023-membership-heatmap-2-1.png" alt="plot of chunk tab-node-023-membership-heatmap-2"/></p>

</div>
<div id='tab-node-023-membership-heatmap-3'>
<pre><code class="r">membership_heatmap(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-023-membership-heatmap-3-1.png" alt="plot of chunk tab-node-023-membership-heatmap-3"/></p>

</div>
<div id='tab-node-023-membership-heatmap-4'>
<pre><code class="r">membership_heatmap(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-023-membership-heatmap-4-1.png" alt="plot of chunk tab-node-023-membership-heatmap-4"/></p>

</div>
<div id='tab-node-023-membership-heatmap-5'>
<pre><code class="r">membership_heatmap(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-023-membership-heatmap-5-1.png" alt="plot of chunk tab-node-023-membership-heatmap-5"/></p>

</div>
<div id='tab-node-023-membership-heatmap-6'>
<pre><code class="r">membership_heatmap(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-023-membership-heatmap-6-1.png" alt="plot of chunk tab-node-023-membership-heatmap-6"/></p>

</div>
<div id='tab-node-023-membership-heatmap-7'>
<pre><code class="r">membership_heatmap(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-023-membership-heatmap-7-1.png" alt="plot of chunk tab-node-023-membership-heatmap-7"/></p>

</div>
</div>

As soon as the classes for columns are determined, the signatures
that are significantly different between subgroups can be looked for. 
Following are the heatmaps for signatures.






<script>
$( function() {
	$( '#tabs-node-023-get-signatures' ).tabs();
} );
</script>
<div id='tabs-node-023-get-signatures'>
<ul>
<li><a href='#tab-node-023-get-signatures-1'>k = 2</a></li>
<li><a href='#tab-node-023-get-signatures-2'>k = 3</a></li>
<li><a href='#tab-node-023-get-signatures-3'>k = 4</a></li>
<li><a href='#tab-node-023-get-signatures-4'>k = 5</a></li>
<li><a href='#tab-node-023-get-signatures-5'>k = 6</a></li>
<li><a href='#tab-node-023-get-signatures-6'>k = 7</a></li>
<li><a href='#tab-node-023-get-signatures-7'>k = 8</a></li>
</ul>
<div id='tab-node-023-get-signatures-1'>
<pre><code class="r">get_signatures(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-023-get-signatures-1-1.png" alt="plot of chunk tab-node-023-get-signatures-1"/></p>

</div>
<div id='tab-node-023-get-signatures-2'>
<pre><code class="r">get_signatures(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-023-get-signatures-2-1.png" alt="plot of chunk tab-node-023-get-signatures-2"/></p>

</div>
<div id='tab-node-023-get-signatures-3'>
<pre><code class="r">get_signatures(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-023-get-signatures-3-1.png" alt="plot of chunk tab-node-023-get-signatures-3"/></p>

</div>
<div id='tab-node-023-get-signatures-4'>
<pre><code class="r">get_signatures(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-023-get-signatures-4-1.png" alt="plot of chunk tab-node-023-get-signatures-4"/></p>

</div>
<div id='tab-node-023-get-signatures-5'>
<pre><code class="r">get_signatures(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-023-get-signatures-5-1.png" alt="plot of chunk tab-node-023-get-signatures-5"/></p>

</div>
<div id='tab-node-023-get-signatures-6'>
<pre><code class="r">get_signatures(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-023-get-signatures-6-1.png" alt="plot of chunk tab-node-023-get-signatures-6"/></p>

</div>
<div id='tab-node-023-get-signatures-7'>
<pre><code class="r">get_signatures(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-023-get-signatures-7-1.png" alt="plot of chunk tab-node-023-get-signatures-7"/></p>

</div>
</div>



Compare the overlap of signatures from different k:

```r
compare_signatures(res)
```

![plot of chunk node-023-signature_compare](figure_cola/node-023-signature_compare-1.png)

`get_signature()` returns a data frame invisibly. To get the list of signatures, the function
call should be assigned to a variable explicitly. In following code, if `plot` argument is set
to `FALSE`, no heatmap is plotted while only the differential analysis is performed.

```r
# code only for demonstration
tb = get_signature(res, k = ..., plot = FALSE)
```

An example of the output of `tb` is:

```
#>   which_row         fdr    mean_1    mean_2 scaled_mean_1 scaled_mean_2 km
#> 1        38 0.042760348  8.373488  9.131774    -0.5533452     0.5164555  1
#> 2        40 0.018707592  7.106213  8.469186    -0.6173731     0.5762149  1
#> 3        55 0.019134737 10.221463 11.207825    -0.6159697     0.5749050  1
#> 4        59 0.006059896  5.921854  7.869574    -0.6899429     0.6439467  1
#> 5        60 0.018055526  8.928898 10.211722    -0.6204761     0.5791110  1
#> 6        98 0.009384629 15.714769 14.887706     0.6635654    -0.6193277  2
...
```

The columns in `tb` are:

1. `which_row`: row indices corresponding to the input matrix.
2. `fdr`: FDR for the differential test. 
3. `mean_x`: The mean value in group x.
4. `scaled_mean_x`: The mean value in group x after rows are scaled.
5. `km`: Row groups if k-means clustering is applied to rows (which is done by automatically selecting number of clusters).

If there are too many signatures, `top_signatures = ...` can be set to only show the 
signatures with the highest FDRs:

```r
# code only for demonstration
# e.g. to show the top 500 most significant rows
tb = get_signature(res, k = ..., top_signatures = 500)
```

If the signatures are defined as these which are uniquely high in current group, `diff_method` argument
can be set to `"uniquely_high_in_one_group"`:

```r
# code only for demonstration
tb = get_signature(res, k = ..., diff_method = "uniquely_high_in_one_group")
```




UMAP plot which shows how samples are separated.


<script>
$( function() {
	$( '#tabs-node-023-dimension-reduction' ).tabs();
} );
</script>
<div id='tabs-node-023-dimension-reduction'>
<ul>
<li><a href='#tab-node-023-dimension-reduction-1'>k = 2</a></li>
<li><a href='#tab-node-023-dimension-reduction-2'>k = 3</a></li>
<li><a href='#tab-node-023-dimension-reduction-3'>k = 4</a></li>
<li><a href='#tab-node-023-dimension-reduction-4'>k = 5</a></li>
<li><a href='#tab-node-023-dimension-reduction-5'>k = 6</a></li>
<li><a href='#tab-node-023-dimension-reduction-6'>k = 7</a></li>
<li><a href='#tab-node-023-dimension-reduction-7'>k = 8</a></li>
</ul>
<div id='tab-node-023-dimension-reduction-1'>
<pre><code class="r">dimension_reduction(res, k = 2, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-023-dimension-reduction-1-1.png" alt="plot of chunk tab-node-023-dimension-reduction-1"/></p>

</div>
<div id='tab-node-023-dimension-reduction-2'>
<pre><code class="r">dimension_reduction(res, k = 3, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-023-dimension-reduction-2-1.png" alt="plot of chunk tab-node-023-dimension-reduction-2"/></p>

</div>
<div id='tab-node-023-dimension-reduction-3'>
<pre><code class="r">dimension_reduction(res, k = 4, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-023-dimension-reduction-3-1.png" alt="plot of chunk tab-node-023-dimension-reduction-3"/></p>

</div>
<div id='tab-node-023-dimension-reduction-4'>
<pre><code class="r">dimension_reduction(res, k = 5, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-023-dimension-reduction-4-1.png" alt="plot of chunk tab-node-023-dimension-reduction-4"/></p>

</div>
<div id='tab-node-023-dimension-reduction-5'>
<pre><code class="r">dimension_reduction(res, k = 6, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-023-dimension-reduction-5-1.png" alt="plot of chunk tab-node-023-dimension-reduction-5"/></p>

</div>
<div id='tab-node-023-dimension-reduction-6'>
<pre><code class="r">dimension_reduction(res, k = 7, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-023-dimension-reduction-6-1.png" alt="plot of chunk tab-node-023-dimension-reduction-6"/></p>

</div>
<div id='tab-node-023-dimension-reduction-7'>
<pre><code class="r">dimension_reduction(res, k = 8, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-023-dimension-reduction-7-1.png" alt="plot of chunk tab-node-023-dimension-reduction-7"/></p>

</div>
</div>



Following heatmap shows how subgroups are split when increasing `k`:

```r
collect_classes(res)
```

![plot of chunk node-023-collect-classes](figure_cola/node-023-collect-classes-1.png)



If matrix rows can be associated to genes, consider to use `functional_enrichment(res,
...)` to perform function enrichment for the signature genes. See [this vignette](https://jokergoo.github.io/cola_vignettes/functional_enrichment.html) for more detailed explanations.


 

---------------------------------------------------




### Node03


Parent node: [Node0](#Node0).
Child nodes: 
                [Node011](#Node011)
        ,
                Node012-leaf
        ,
                [Node013](#Node013)
        ,
                [Node014](#Node014)
        ,
                [Node021](#Node021)
        ,
                [Node022](#Node022)
        ,
                [Node023](#Node023)
        ,
                Node031-leaf
        ,
                [Node032](#Node032)
        ,
                [Node033](#Node033)
        ,
                Node034-leaf
        .







The object with results only for a single top-value method and a single partitioning method 
can be extracted as:

```r
res = res_rh["03"]
```

A summary of `res` and all the functions that can be applied to it:

```r
res
```

```
#> A 'ConsensusPartition' object with k = 2, 3, 4, 5, 6, 7, 8.
#>   On a matrix with 30000 rows and 50 columns.
#>   Top rows (1000) are extracted by 'SD' method.
#>   Subgroups are detected by 'kmeans' method.
#>   Performed in total 350 partitions by row resampling.
#>   Best k for subgroups seems to be 3.
#> 
#> Following methods can be applied to this 'ConsensusPartition' object:
#>  [1] "cola_report"             "collect_classes"         "collect_plots"          
#>  [4] "collect_stats"           "colnames"                "compare_partitions"     
#>  [7] "compare_signatures"      "consensus_heatmap"       "dimension_reduction"    
#> [10] "functional_enrichment"   "get_anno_col"            "get_anno"               
#> [13] "get_classes"             "get_consensus"           "get_matrix"             
#> [16] "get_membership"          "get_param"               "get_signatures"         
#> [19] "get_stats"               "is_best_k"               "is_stable_k"            
#> [22] "membership_heatmap"      "ncol"                    "nrow"                   
#> [25] "plot_ecdf"               "predict_classes"         "rownames"               
#> [28] "select_partition_number" "show"                    "suggest_best_k"         
#> [31] "test_to_known_factors"   "top_rows_heatmap"
```

`collect_plots()` function collects all the plots made from `res` for all `k` (number of subgroups)
into one single page to provide an easy and fast comparison between different `k`.

```r
collect_plots(res)
```

![plot of chunk node-03-collect-plots](figure_cola/node-03-collect-plots-1.png)

The plots are:

- The first row: a plot of the eCDF (empirical cumulative distribution
  function) curves of the consensus matrix for each `k` and the heatmap of
  predicted classes for each `k`.
- The second row: heatmaps of the consensus matrix for each `k`.
- The third row: heatmaps of the membership matrix for each `k`.
- The fouth row: heatmaps of the signatures for each `k`.

All the plots in panels can be made by individual functions and they are
plotted later in this section.

`select_partition_number()` produces several plots showing different
statistics for choosing "optimized" `k`. There are following statistics:

- eCDF curves of the consensus matrix for each `k`;
- 1-PAC. [The PAC score](https://en.wikipedia.org/wiki/Consensus_clustering#Over-interpretation_potential_of_consensus_clustering)
  measures the proportion of the ambiguous subgrouping.
- Mean silhouette score.
- Concordance. The mean probability of fiting the consensus subgroup labels in all
  partitions.
- Area increased. Denote $A_k$ as the area under the eCDF curve for current
  `k`, the area increased is defined as $A_k - A_{k-1}$.
- Rand index. The percent of pairs of samples that are both in a same cluster
  or both are not in a same cluster in the partition of k and k-1.
- Jaccard index. The ratio of pairs of samples are both in a same cluster in
  the partition of k and k-1 and the pairs of samples are both in a same
  cluster in the partition k or k-1.

The detailed explanations of these statistics can be found in [the _cola_
vignette](https://jokergoo.github.io/cola_vignettes/cola.html#toc_13).

Generally speaking, higher 1-PAC score, higher mean silhouette score or higher
concordance corresponds to better partition. Rand index and Jaccard index
measure how similar the current partition is compared to partition with `k-1`.
If they are too similar, we won't accept `k` is better than `k-1`.

```r
select_partition_number(res)
```

![plot of chunk node-03-select-partition-number](figure_cola/node-03-select-partition-number-1.png)

The numeric values for all these statistics can be obtained by `get_stats()`.

```r
get_stats(res)
```

```
#>   k 1-PAC mean_silhouette concordance area_increased  Rand Jaccard
#> 2 2 0.367           0.807       0.864         0.4818 0.519   0.519
#> 3 3 1.000           0.993       0.991         0.3790 0.666   0.437
#> 4 4 0.859           0.953       0.912         0.1058 0.922   0.765
#> 5 5 0.810           0.881       0.879         0.0604 0.947   0.792
#> 6 6 0.846           0.884       0.901         0.0435 0.966   0.835
#> 7 7 0.835           0.849       0.879         0.0190 1.000   1.000
#> 8 8 0.821           0.773       0.837         0.0249 0.967   0.818
```

`suggest_best_k()` suggests the best $k$ based on these statistics. The rules are as follows:

- All $k$ with Jaccard index larger than 0.95 are removed because increasing
  $k$ does not provide enough extra information. If all $k$ are removed, it is
  marked as no subgroup is detected.
- For all $k$ with 1-PAC score larger than 0.9, the maximal $k$ is taken as
  the best $k$, and other $k$ are marked as optional $k$.
- If it does not fit the second rule. The $k$ with the maximal vote of the
  highest 1-PAC score, highest mean silhouette, and highest concordance is
  taken as the best $k$.

```r
suggest_best_k(res)
```

```
#> [1] 3
```


Following is the table of the partitions (You need to click the **show/hide
code output** link to see it). The membership matrix (columns with name `p*`)
is inferred by
[`clue::cl_consensus()`](https://www.rdocumentation.org/link/cl_consensus?package=clue)
function with the `SE` method. Basically the value in the membership matrix
represents the probability to belong to a certain group. The finall subgroup
label for an item is determined with the group with highest probability it
belongs to.

In `get_classes()` function, the entropy is calculated from the membership
matrix and the silhouette score is calculated from the consensus matrix.



<script>
$( function() {
	$( '#tabs-node-03-get-classes' ).tabs();
} );
</script>
<div id='tabs-node-03-get-classes'>
<ul>
<li><a href='#tab-node-03-get-classes-1'>k = 2</a></li>
<li><a href='#tab-node-03-get-classes-2'>k = 3</a></li>
<li><a href='#tab-node-03-get-classes-3'>k = 4</a></li>
<li><a href='#tab-node-03-get-classes-4'>k = 5</a></li>
<li><a href='#tab-node-03-get-classes-5'>k = 6</a></li>
<li><a href='#tab-node-03-get-classes-6'>k = 7</a></li>
<li><a href='#tab-node-03-get-classes-7'>k = 8</a></li>
</ul>

<div id='tab-node-03-get-classes-1'>
<p><a id='tab-node-03-get-classes-1-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 2), get_membership(res, k = 2))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2
#&gt; TCGA.AB.2888.03     2   0.722      0.699 0.20 0.80
#&gt; TCGA.AB.2998.03     2   0.634      0.818 0.16 0.84
#&gt; TCGA.AB.2957.03     2   0.722      0.699 0.20 0.80
#&gt; TCGA.AB.2876.03     1   0.000      0.911 1.00 0.00
#&gt; TCGA.AB.2823.03     2   0.634      0.818 0.16 0.84
#&gt; TCGA.AB.2999.03     2   0.634      0.818 0.16 0.84
#&gt; TCGA.AB.2940.03     1   0.000      0.911 1.00 0.00
#&gt; TCGA.AB.3012.03     2   0.634      0.818 0.16 0.84
#&gt; TCGA.AB.2875.03     1   0.680      0.838 0.82 0.18
#&gt; TCGA.AB.2841.03     2   0.634      0.818 0.16 0.84
#&gt; TCGA.AB.3008.03     1   0.000      0.911 1.00 0.00
#&gt; TCGA.AB.2942.03     2   0.722      0.699 0.20 0.80
#&gt; TCGA.AB.2872.03     2   0.634      0.818 0.16 0.84
#&gt; TCGA.AB.2897.03     2   0.634      0.818 0.16 0.84
#&gt; TCGA.AB.2921.03     1   0.000      0.911 1.00 0.00
#&gt; TCGA.AB.2862.03     2   0.634      0.818 0.16 0.84
#&gt; TCGA.AB.2840.03     2   0.634      0.818 0.16 0.84
#&gt; TCGA.AB.2845.03     1   0.000      0.911 1.00 0.00
#&gt; TCGA.AB.3009.03     1   0.000      0.911 1.00 0.00
#&gt; TCGA.AB.2886.03     1   0.634      0.849 0.84 0.16
#&gt; TCGA.AB.2955.03     1   0.000      0.911 1.00 0.00
#&gt; TCGA.AB.2892.03     2   0.722      0.699 0.20 0.80
#&gt; TCGA.AB.2906.03     2   0.634      0.818 0.16 0.84
#&gt; TCGA.AB.2937.03     2   0.943      0.384 0.36 0.64
#&gt; TCGA.AB.2914.03     1   0.634      0.849 0.84 0.16
#&gt; TCGA.AB.2980.03     2   0.634      0.818 0.16 0.84
#&gt; TCGA.AB.2819.03     1   0.634      0.849 0.84 0.16
#&gt; TCGA.AB.2806.03     1   0.634      0.849 0.84 0.16
#&gt; TCGA.AB.2815.03     2   0.722      0.699 0.20 0.80
#&gt; TCGA.AB.2939.03     1   0.000      0.911 1.00 0.00
#&gt; TCGA.AB.2979.03     1   0.000      0.911 1.00 0.00
#&gt; TCGA.AB.2808.03     1   0.000      0.911 1.00 0.00
#&gt; TCGA.AB.2991.03     2   0.634      0.818 0.16 0.84
#&gt; TCGA.AB.2803.03     2   0.634      0.818 0.16 0.84
#&gt; TCGA.AB.3000.03     1   0.000      0.911 1.00 0.00
#&gt; TCGA.AB.2997.03     2   0.634      0.818 0.16 0.84
#&gt; TCGA.AB.3001.03     2   0.634      0.818 0.16 0.84
#&gt; TCGA.AB.2954.03     2   0.722      0.699 0.20 0.80
#&gt; TCGA.AB.2828.03     2   0.722      0.699 0.20 0.80
#&gt; TCGA.AB.2804.03     2   0.634      0.818 0.16 0.84
#&gt; TCGA.AB.2950.03     1   0.680      0.838 0.82 0.18
#&gt; TCGA.AB.3007.03     2   0.634      0.818 0.16 0.84
#&gt; TCGA.AB.2880.03     1   0.000      0.911 1.00 0.00
#&gt; TCGA.AB.2889.03     2   0.722      0.699 0.20 0.80
#&gt; TCGA.AB.2881.03     2   0.722      0.699 0.20 0.80
#&gt; TCGA.AB.2982.03     2   0.634      0.818 0.16 0.84
#&gt; TCGA.AB.2870.03     2   0.722      0.699 0.20 0.80
#&gt; TCGA.AB.2909.03     1   0.634      0.849 0.84 0.16
#&gt; TCGA.AB.2858.03     2   0.722      0.699 0.20 0.80
#&gt; TCGA.AB.2846.03     2   0.722      0.699 0.20 0.80
</code></pre>

<script>
$('#tab-node-03-get-classes-1-a').parent().next().next().hide();
$('#tab-node-03-get-classes-1-a').click(function(){
  $('#tab-node-03-get-classes-1-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-03-get-classes-2'>
<p><a id='tab-node-03-get-classes-2-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 3), get_membership(res, k = 3))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3
#&gt; TCGA.AB.2888.03     3  0.0000      0.995 0.00 0.00 1.00
#&gt; TCGA.AB.2998.03     2  0.0000      0.995 0.00 1.00 0.00
#&gt; TCGA.AB.2957.03     3  0.0000      0.995 0.00 0.00 1.00
#&gt; TCGA.AB.2876.03     1  0.0892      1.000 0.98 0.00 0.02
#&gt; TCGA.AB.2823.03     2  0.0000      0.995 0.00 1.00 0.00
#&gt; TCGA.AB.2999.03     2  0.0000      0.995 0.00 1.00 0.00
#&gt; TCGA.AB.2940.03     1  0.0892      1.000 0.98 0.00 0.02
#&gt; TCGA.AB.3012.03     2  0.0892      0.989 0.02 0.98 0.00
#&gt; TCGA.AB.2875.03     3  0.0000      0.995 0.00 0.00 1.00
#&gt; TCGA.AB.2841.03     2  0.0000      0.995 0.00 1.00 0.00
#&gt; TCGA.AB.3008.03     1  0.0892      1.000 0.98 0.00 0.02
#&gt; TCGA.AB.2942.03     3  0.0000      0.995 0.00 0.00 1.00
#&gt; TCGA.AB.2872.03     2  0.0892      0.989 0.02 0.98 0.00
#&gt; TCGA.AB.2897.03     2  0.0000      0.995 0.00 1.00 0.00
#&gt; TCGA.AB.2921.03     1  0.0892      1.000 0.98 0.00 0.02
#&gt; TCGA.AB.2862.03     2  0.0000      0.995 0.00 1.00 0.00
#&gt; TCGA.AB.2840.03     2  0.0000      0.995 0.00 1.00 0.00
#&gt; TCGA.AB.2845.03     1  0.0892      1.000 0.98 0.00 0.02
#&gt; TCGA.AB.3009.03     1  0.0892      1.000 0.98 0.00 0.02
#&gt; TCGA.AB.2886.03     3  0.0000      0.995 0.00 0.00 1.00
#&gt; TCGA.AB.2955.03     1  0.0892      1.000 0.98 0.00 0.02
#&gt; TCGA.AB.2892.03     3  0.0000      0.995 0.00 0.00 1.00
#&gt; TCGA.AB.2906.03     2  0.0000      0.995 0.00 1.00 0.00
#&gt; TCGA.AB.2937.03     3  0.0000      0.995 0.00 0.00 1.00
#&gt; TCGA.AB.2914.03     3  0.0000      0.995 0.00 0.00 1.00
#&gt; TCGA.AB.2980.03     2  0.0000      0.995 0.00 1.00 0.00
#&gt; TCGA.AB.2819.03     3  0.0000      0.995 0.00 0.00 1.00
#&gt; TCGA.AB.2806.03     3  0.1529      0.959 0.04 0.00 0.96
#&gt; TCGA.AB.2815.03     3  0.0000      0.995 0.00 0.00 1.00
#&gt; TCGA.AB.2939.03     1  0.0892      1.000 0.98 0.00 0.02
#&gt; TCGA.AB.2979.03     1  0.0892      1.000 0.98 0.00 0.02
#&gt; TCGA.AB.2808.03     1  0.0892      1.000 0.98 0.00 0.02
#&gt; TCGA.AB.2991.03     2  0.0892      0.989 0.02 0.98 0.00
#&gt; TCGA.AB.2803.03     2  0.0000      0.995 0.00 1.00 0.00
#&gt; TCGA.AB.3000.03     1  0.0892      1.000 0.98 0.00 0.02
#&gt; TCGA.AB.2997.03     2  0.0892      0.989 0.02 0.98 0.00
#&gt; TCGA.AB.3001.03     2  0.0892      0.989 0.02 0.98 0.00
#&gt; TCGA.AB.2954.03     3  0.0000      0.995 0.00 0.00 1.00
#&gt; TCGA.AB.2828.03     3  0.0000      0.995 0.00 0.00 1.00
#&gt; TCGA.AB.2804.03     2  0.0000      0.995 0.00 1.00 0.00
#&gt; TCGA.AB.2950.03     3  0.0000      0.995 0.00 0.00 1.00
#&gt; TCGA.AB.3007.03     2  0.0892      0.989 0.02 0.98 0.00
#&gt; TCGA.AB.2880.03     1  0.0892      1.000 0.98 0.00 0.02
#&gt; TCGA.AB.2889.03     3  0.0000      0.995 0.00 0.00 1.00
#&gt; TCGA.AB.2881.03     3  0.0000      0.995 0.00 0.00 1.00
#&gt; TCGA.AB.2982.03     2  0.0000      0.995 0.00 1.00 0.00
#&gt; TCGA.AB.2870.03     3  0.0000      0.995 0.00 0.00 1.00
#&gt; TCGA.AB.2909.03     3  0.2066      0.938 0.06 0.00 0.94
#&gt; TCGA.AB.2858.03     3  0.0000      0.995 0.00 0.00 1.00
#&gt; TCGA.AB.2846.03     3  0.0000      0.995 0.00 0.00 1.00
</code></pre>

<script>
$('#tab-node-03-get-classes-2-a').parent().next().next().hide();
$('#tab-node-03-get-classes-2-a').click(function(){
  $('#tab-node-03-get-classes-2-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-03-get-classes-3'>
<p><a id='tab-node-03-get-classes-3-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 4), get_membership(res, k = 4))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4
#&gt; TCGA.AB.2888.03     3  0.0000      0.990 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2998.03     2  0.0000      0.917 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2957.03     3  0.0000      0.990 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2876.03     1  0.0707      1.000 0.98 0.00 0.02 0.00
#&gt; TCGA.AB.2823.03     2  0.0000      0.917 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2999.03     2  0.0000      0.917 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2940.03     1  0.0707      1.000 0.98 0.00 0.02 0.00
#&gt; TCGA.AB.3012.03     2  0.4277      0.824 0.00 0.72 0.00 0.28
#&gt; TCGA.AB.2875.03     4  0.4406      0.995 0.00 0.00 0.30 0.70
#&gt; TCGA.AB.2841.03     2  0.0000      0.917 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.3008.03     1  0.0707      1.000 0.98 0.00 0.02 0.00
#&gt; TCGA.AB.2942.03     3  0.0000      0.990 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2872.03     2  0.4277      0.824 0.00 0.72 0.00 0.28
#&gt; TCGA.AB.2897.03     2  0.0000      0.917 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2921.03     1  0.0707      1.000 0.98 0.00 0.02 0.00
#&gt; TCGA.AB.2862.03     2  0.1637      0.902 0.00 0.94 0.00 0.06
#&gt; TCGA.AB.2840.03     2  0.0000      0.917 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2845.03     1  0.0707      1.000 0.98 0.00 0.02 0.00
#&gt; TCGA.AB.3009.03     1  0.0707      1.000 0.98 0.00 0.02 0.00
#&gt; TCGA.AB.2886.03     4  0.4406      0.995 0.00 0.00 0.30 0.70
#&gt; TCGA.AB.2955.03     1  0.0707      1.000 0.98 0.00 0.02 0.00
#&gt; TCGA.AB.2892.03     3  0.0000      0.990 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2906.03     2  0.0000      0.917 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2937.03     4  0.4406      0.995 0.00 0.00 0.30 0.70
#&gt; TCGA.AB.2914.03     4  0.4406      0.995 0.00 0.00 0.30 0.70
#&gt; TCGA.AB.2980.03     2  0.0000      0.917 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2819.03     4  0.4406      0.995 0.00 0.00 0.30 0.70
#&gt; TCGA.AB.2806.03     4  0.4406      0.995 0.00 0.00 0.30 0.70
#&gt; TCGA.AB.2815.03     3  0.0000      0.990 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2939.03     1  0.0707      1.000 0.98 0.00 0.02 0.00
#&gt; TCGA.AB.2979.03     1  0.0707      1.000 0.98 0.00 0.02 0.00
#&gt; TCGA.AB.2808.03     1  0.0707      1.000 0.98 0.00 0.02 0.00
#&gt; TCGA.AB.2991.03     2  0.4277      0.824 0.00 0.72 0.00 0.28
#&gt; TCGA.AB.2803.03     2  0.0000      0.917 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.3000.03     1  0.0707      1.000 0.98 0.00 0.02 0.00
#&gt; TCGA.AB.2997.03     2  0.4472      0.839 0.02 0.76 0.00 0.22
#&gt; TCGA.AB.3001.03     2  0.4277      0.824 0.00 0.72 0.00 0.28
#&gt; TCGA.AB.2954.03     3  0.0000      0.990 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2828.03     3  0.0000      0.990 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2804.03     2  0.0000      0.917 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2950.03     4  0.4406      0.995 0.00 0.00 0.30 0.70
#&gt; TCGA.AB.3007.03     2  0.4277      0.824 0.00 0.72 0.00 0.28
#&gt; TCGA.AB.2880.03     1  0.0707      1.000 0.98 0.00 0.02 0.00
#&gt; TCGA.AB.2889.03     3  0.0000      0.990 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2881.03     3  0.0000      0.990 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2982.03     2  0.0000      0.917 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2870.03     3  0.0000      0.990 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2909.03     4  0.4936      0.963 0.02 0.00 0.28 0.70
#&gt; TCGA.AB.2858.03     3  0.2011      0.871 0.00 0.00 0.92 0.08
#&gt; TCGA.AB.2846.03     3  0.0000      0.990 0.00 0.00 1.00 0.00
</code></pre>

<script>
$('#tab-node-03-get-classes-3-a').parent().next().next().hide();
$('#tab-node-03-get-classes-3-a').click(function(){
  $('#tab-node-03-get-classes-3-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-03-get-classes-4'>
<p><a id='tab-node-03-get-classes-4-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 5), get_membership(res, k = 5))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5
#&gt; TCGA.AB.2888.03     3  0.0000      0.976 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2998.03     2  0.1732      0.832 0.00 0.92 0.00 0.08 0.00
#&gt; TCGA.AB.2957.03     3  0.0000      0.976 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2876.03     1  0.0000      0.929 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2823.03     2  0.2331      0.811 0.00 0.90 0.00 0.08 0.02
#&gt; TCGA.AB.2999.03     2  0.0000      0.876 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2940.03     1  0.3291      0.898 0.84 0.00 0.00 0.04 0.12
#&gt; TCGA.AB.3012.03     5  0.4126      1.000 0.00 0.38 0.00 0.00 0.62
#&gt; TCGA.AB.2875.03     4  0.5597      0.862 0.00 0.00 0.20 0.64 0.16
#&gt; TCGA.AB.2841.03     2  0.0000      0.876 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.3008.03     1  0.3291      0.898 0.84 0.00 0.00 0.04 0.12
#&gt; TCGA.AB.2942.03     3  0.0000      0.976 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2872.03     5  0.4126      1.000 0.00 0.38 0.00 0.00 0.62
#&gt; TCGA.AB.2897.03     2  0.1043      0.859 0.00 0.96 0.00 0.04 0.00
#&gt; TCGA.AB.2921.03     1  0.0000      0.929 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2862.03     2  0.2929      0.599 0.00 0.82 0.00 0.00 0.18
#&gt; TCGA.AB.2840.03     2  0.0609      0.870 0.00 0.98 0.00 0.02 0.00
#&gt; TCGA.AB.2845.03     1  0.0000      0.929 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.3009.03     1  0.4254      0.847 0.74 0.00 0.00 0.04 0.22
#&gt; TCGA.AB.2886.03     4  0.3513      0.941 0.00 0.00 0.18 0.80 0.02
#&gt; TCGA.AB.2955.03     1  0.0000      0.929 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2892.03     3  0.0000      0.976 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2906.03     2  0.0000      0.876 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2937.03     4  0.5597      0.862 0.00 0.00 0.20 0.64 0.16
#&gt; TCGA.AB.2914.03     4  0.3922      0.928 0.00 0.00 0.18 0.78 0.04
#&gt; TCGA.AB.2980.03     2  0.0609      0.867 0.00 0.98 0.00 0.02 0.00
#&gt; TCGA.AB.2819.03     4  0.2929      0.941 0.00 0.00 0.18 0.82 0.00
#&gt; TCGA.AB.2806.03     4  0.2929      0.941 0.00 0.00 0.18 0.82 0.00
#&gt; TCGA.AB.2815.03     3  0.0000      0.976 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2939.03     1  0.4254      0.847 0.74 0.00 0.00 0.04 0.22
#&gt; TCGA.AB.2979.03     1  0.0000      0.929 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2808.03     1  0.0000      0.929 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2991.03     5  0.4126      1.000 0.00 0.38 0.00 0.00 0.62
#&gt; TCGA.AB.2803.03     2  0.0000      0.876 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.3000.03     1  0.3291      0.898 0.84 0.00 0.00 0.04 0.12
#&gt; TCGA.AB.2997.03     2  0.6064     -0.687 0.00 0.46 0.00 0.12 0.42
#&gt; TCGA.AB.3001.03     5  0.4126      1.000 0.00 0.38 0.00 0.00 0.62
#&gt; TCGA.AB.2954.03     3  0.0000      0.976 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2828.03     3  0.0000      0.976 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2804.03     2  0.0609      0.867 0.00 0.98 0.00 0.02 0.00
#&gt; TCGA.AB.2950.03     4  0.3513      0.941 0.00 0.00 0.18 0.80 0.02
#&gt; TCGA.AB.3007.03     5  0.4126      1.000 0.00 0.38 0.00 0.00 0.62
#&gt; TCGA.AB.2880.03     1  0.0000      0.929 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2889.03     3  0.0000      0.976 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2881.03     3  0.0000      0.976 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2982.03     2  0.0000      0.876 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2870.03     3  0.0000      0.976 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2909.03     4  0.3922      0.928 0.00 0.00 0.18 0.78 0.04
#&gt; TCGA.AB.2858.03     3  0.4373      0.660 0.00 0.00 0.76 0.08 0.16
#&gt; TCGA.AB.2846.03     3  0.0000      0.976 0.00 0.00 1.00 0.00 0.00
</code></pre>

<script>
$('#tab-node-03-get-classes-4-a').parent().next().next().hide();
$('#tab-node-03-get-classes-4-a').click(function(){
  $('#tab-node-03-get-classes-4-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-03-get-classes-5'>
<p><a id='tab-node-03-get-classes-5-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 6), get_membership(res, k = 6))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5   p6
#&gt; TCGA.AB.2888.03     3  0.0000      1.000 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2998.03     2  0.1814      0.873 0.00 0.90 0.00 0.00 0.00 0.10
#&gt; TCGA.AB.2957.03     3  0.0000      1.000 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2876.03     1  0.0547      0.919 0.98 0.00 0.00 0.00 0.00 0.02
#&gt; TCGA.AB.2823.03     2  0.1814      0.873 0.00 0.90 0.00 0.00 0.00 0.10
#&gt; TCGA.AB.2999.03     2  0.0547      0.928 0.00 0.98 0.00 0.00 0.00 0.02
#&gt; TCGA.AB.2940.03     1  0.2512      0.894 0.88 0.00 0.00 0.00 0.06 0.06
#&gt; TCGA.AB.3012.03     5  0.2941      0.951 0.00 0.22 0.00 0.00 0.78 0.00
#&gt; TCGA.AB.2875.03     6  0.4199      0.490 0.00 0.00 0.02 0.38 0.00 0.60
#&gt; TCGA.AB.2841.03     2  0.0547      0.928 0.00 0.98 0.00 0.00 0.00 0.02
#&gt; TCGA.AB.3008.03     1  0.2512      0.894 0.88 0.00 0.00 0.00 0.06 0.06
#&gt; TCGA.AB.2942.03     3  0.0000      1.000 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2872.03     5  0.2941      0.951 0.00 0.22 0.00 0.00 0.78 0.00
#&gt; TCGA.AB.2897.03     2  0.0547      0.921 0.00 0.98 0.00 0.00 0.00 0.02
#&gt; TCGA.AB.2921.03     1  0.0000      0.920 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2862.03     2  0.2260      0.783 0.00 0.86 0.00 0.00 0.14 0.00
#&gt; TCGA.AB.2840.03     2  0.0937      0.921 0.00 0.96 0.00 0.00 0.00 0.04
#&gt; TCGA.AB.2845.03     1  0.0547      0.919 0.98 0.00 0.00 0.00 0.00 0.02
#&gt; TCGA.AB.3009.03     1  0.4566      0.780 0.70 0.00 0.00 0.00 0.16 0.14
#&gt; TCGA.AB.2886.03     4  0.2260      0.787 0.00 0.00 0.00 0.86 0.00 0.14
#&gt; TCGA.AB.2955.03     1  0.0547      0.919 0.98 0.00 0.00 0.00 0.00 0.02
#&gt; TCGA.AB.2892.03     3  0.0000      1.000 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2906.03     2  0.0547      0.925 0.00 0.98 0.00 0.00 0.00 0.02
#&gt; TCGA.AB.2937.03     6  0.4199      0.490 0.00 0.00 0.02 0.38 0.00 0.60
#&gt; TCGA.AB.2914.03     4  0.1807      0.854 0.00 0.00 0.00 0.92 0.06 0.02
#&gt; TCGA.AB.2980.03     2  0.2048      0.877 0.00 0.88 0.00 0.00 0.00 0.12
#&gt; TCGA.AB.2819.03     4  0.0000      0.877 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2806.03     4  0.0000      0.877 0.00 0.00 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2815.03     3  0.0000      1.000 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2939.03     1  0.4566      0.780 0.70 0.00 0.00 0.00 0.16 0.14
#&gt; TCGA.AB.2979.03     1  0.0547      0.919 0.98 0.00 0.00 0.00 0.00 0.02
#&gt; TCGA.AB.2808.03     1  0.0000      0.920 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2991.03     5  0.2941      0.951 0.00 0.22 0.00 0.00 0.78 0.00
#&gt; TCGA.AB.2803.03     2  0.0547      0.928 0.00 0.98 0.00 0.00 0.00 0.02
#&gt; TCGA.AB.3000.03     1  0.2512      0.894 0.88 0.00 0.00 0.00 0.06 0.06
#&gt; TCGA.AB.2997.03     5  0.5324      0.699 0.00 0.34 0.00 0.00 0.54 0.12
#&gt; TCGA.AB.3001.03     5  0.2941      0.951 0.00 0.22 0.00 0.00 0.78 0.00
#&gt; TCGA.AB.2954.03     3  0.0000      1.000 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2828.03     3  0.0000      1.000 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2804.03     2  0.2048      0.877 0.00 0.88 0.00 0.00 0.00 0.12
#&gt; TCGA.AB.2950.03     4  0.2260      0.787 0.00 0.00 0.00 0.86 0.00 0.14
#&gt; TCGA.AB.3007.03     5  0.2941      0.951 0.00 0.22 0.00 0.00 0.78 0.00
#&gt; TCGA.AB.2880.03     1  0.0000      0.920 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2889.03     3  0.0000      1.000 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2881.03     3  0.0000      1.000 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2982.03     2  0.0547      0.928 0.00 0.98 0.00 0.00 0.00 0.02
#&gt; TCGA.AB.2870.03     3  0.0000      1.000 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2909.03     4  0.1807      0.854 0.00 0.00 0.00 0.92 0.06 0.02
#&gt; TCGA.AB.2858.03     6  0.4199      0.309 0.00 0.00 0.38 0.02 0.00 0.60
#&gt; TCGA.AB.2846.03     3  0.0000      1.000 0.00 0.00 1.00 0.00 0.00 0.00
</code></pre>

<script>
$('#tab-node-03-get-classes-5-a').parent().next().next().hide();
$('#tab-node-03-get-classes-5-a').click(function(){
  $('#tab-node-03-get-classes-5-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-03-get-classes-6'>
<p><a id='tab-node-03-get-classes-6-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 7), get_membership(res, k = 7))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5   p6   p7
#&gt; TCGA.AB.2888.03     3  0.1664      0.929 0.02 0.00 0.92 0.00 0.06 0.00 0.00
#&gt; TCGA.AB.2998.03     2  0.2163      0.837 0.10 0.88 0.00 0.00 0.00 0.02 0.00
#&gt; TCGA.AB.2957.03     3  0.0504      0.967 0.02 0.00 0.98 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2876.03     7  0.0000      0.874 0.00 0.00 0.00 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2823.03     2  0.3208      0.799 0.12 0.82 0.00 0.00 0.02 0.04 0.00
#&gt; TCGA.AB.2999.03     2  0.0504      0.881 0.02 0.98 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2940.03     7  0.3086      0.830 0.16 0.00 0.00 0.00 0.04 0.00 0.80
#&gt; TCGA.AB.3012.03     5  0.2422      0.909 0.00 0.18 0.00 0.00 0.82 0.00 0.00
#&gt; TCGA.AB.2875.03     6  0.2945      0.723 0.00 0.00 0.00 0.26 0.00 0.74 0.00
#&gt; TCGA.AB.2841.03     2  0.1166      0.877 0.00 0.94 0.00 0.00 0.00 0.06 0.00
#&gt; TCGA.AB.3008.03     7  0.3086      0.830 0.16 0.00 0.00 0.00 0.04 0.00 0.80
#&gt; TCGA.AB.2942.03     3  0.0000      0.966 0.00 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2872.03     5  0.2422      0.909 0.00 0.18 0.00 0.00 0.82 0.00 0.00
#&gt; TCGA.AB.2897.03     2  0.0504      0.879 0.02 0.98 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2921.03     7  0.0863      0.869 0.00 0.00 0.00 0.00 0.04 0.00 0.96
#&gt; TCGA.AB.2862.03     2  0.2422      0.716 0.00 0.82 0.00 0.00 0.18 0.00 0.00
#&gt; TCGA.AB.2840.03     2  0.2163      0.857 0.10 0.88 0.00 0.00 0.00 0.02 0.00
#&gt; TCGA.AB.2845.03     7  0.0000      0.874 0.00 0.00 0.00 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.3009.03     7  0.3546      0.612 0.46 0.00 0.00 0.00 0.00 0.00 0.54
#&gt; TCGA.AB.2886.03     4  0.1433      0.846 0.00 0.00 0.00 0.92 0.00 0.08 0.00
#&gt; TCGA.AB.2955.03     7  0.0504      0.872 0.00 0.00 0.00 0.00 0.02 0.00 0.98
#&gt; TCGA.AB.2892.03     3  0.0000      0.966 0.00 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2906.03     2  0.1166      0.878 0.06 0.94 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2937.03     6  0.2945      0.723 0.00 0.00 0.00 0.26 0.00 0.74 0.00
#&gt; TCGA.AB.2914.03     4  0.2912      0.810 0.14 0.00 0.00 0.82 0.04 0.00 0.00
#&gt; TCGA.AB.2980.03     2  0.3086      0.806 0.04 0.80 0.00 0.00 0.00 0.16 0.00
#&gt; TCGA.AB.2819.03     4  0.0000      0.876 0.00 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2806.03     4  0.0000      0.876 0.00 0.00 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2815.03     3  0.0504      0.967 0.02 0.00 0.98 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2939.03     7  0.3546      0.612 0.46 0.00 0.00 0.00 0.00 0.00 0.54
#&gt; TCGA.AB.2979.03     7  0.0000      0.874 0.00 0.00 0.00 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2808.03     7  0.0000      0.874 0.00 0.00 0.00 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2991.03     5  0.2422      0.909 0.00 0.18 0.00 0.00 0.82 0.00 0.00
#&gt; TCGA.AB.2803.03     2  0.1166      0.877 0.00 0.94 0.00 0.00 0.00 0.06 0.00
#&gt; TCGA.AB.3000.03     7  0.3086      0.830 0.16 0.00 0.00 0.00 0.04 0.00 0.80
#&gt; TCGA.AB.2997.03     5  0.6732      0.394 0.28 0.28 0.00 0.00 0.34 0.10 0.00
#&gt; TCGA.AB.3001.03     5  0.2422      0.909 0.00 0.18 0.00 0.00 0.82 0.00 0.00
#&gt; TCGA.AB.2954.03     3  0.1664      0.929 0.02 0.00 0.92 0.00 0.06 0.00 0.00
#&gt; TCGA.AB.2828.03     3  0.0504      0.967 0.02 0.00 0.98 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2804.03     2  0.3086      0.806 0.04 0.80 0.00 0.00 0.00 0.16 0.00
#&gt; TCGA.AB.2950.03     4  0.1433      0.846 0.00 0.00 0.00 0.92 0.00 0.08 0.00
#&gt; TCGA.AB.3007.03     5  0.2422      0.909 0.00 0.18 0.00 0.00 0.82 0.00 0.00
#&gt; TCGA.AB.2880.03     7  0.0000      0.874 0.00 0.00 0.00 0.00 0.00 0.00 1.00
#&gt; TCGA.AB.2889.03     3  0.0504      0.967 0.02 0.00 0.98 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2881.03     3  0.0000      0.966 0.00 0.00 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2982.03     2  0.1166      0.877 0.00 0.94 0.00 0.00 0.00 0.06 0.00
#&gt; TCGA.AB.2870.03     3  0.0504      0.967 0.02 0.00 0.98 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2909.03     4  0.2912      0.810 0.14 0.00 0.00 0.82 0.04 0.00 0.00
#&gt; TCGA.AB.2858.03     6  0.3307      0.571 0.00 0.00 0.24 0.02 0.00 0.74 0.00
#&gt; TCGA.AB.2846.03     3  0.1664      0.929 0.02 0.00 0.92 0.00 0.06 0.00 0.00
</code></pre>

<script>
$('#tab-node-03-get-classes-6-a').parent().next().next().hide();
$('#tab-node-03-get-classes-6-a').click(function(){
  $('#tab-node-03-get-classes-6-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-03-get-classes-7'>
<p><a id='tab-node-03-get-classes-7-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 8), get_membership(res, k = 8))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5   p6   p7   p8
#&gt; TCGA.AB.2888.03     3  0.2350      0.879 0.10 0.00 0.86 0.00 0.04 0.00 0.00 0.00
#&gt; TCGA.AB.2998.03     2  0.3193      0.416 0.38 0.62 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2957.03     3  0.0471      0.950 0.00 0.00 0.98 0.00 0.00 0.00 0.02 0.00
#&gt; TCGA.AB.2876.03     7  0.3083      0.962 0.00 0.00 0.00 0.00 0.00 0.00 0.66 0.34
#&gt; TCGA.AB.2823.03     2  0.3658      0.316 0.40 0.58 0.00 0.00 0.02 0.00 0.00 0.00
#&gt; TCGA.AB.2999.03     2  0.1341      0.708 0.08 0.92 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2940.03     8  0.2852      0.550 0.00 0.00 0.00 0.00 0.00 0.00 0.28 0.72
#&gt; TCGA.AB.3012.03     5  0.1563      1.000 0.00 0.10 0.00 0.00 0.90 0.00 0.00 0.00
#&gt; TCGA.AB.2875.03     6  0.2404      0.894 0.00 0.00 0.02 0.14 0.00 0.84 0.00 0.00
#&gt; TCGA.AB.2841.03     2  0.0471      0.704 0.00 0.98 0.00 0.00 0.00 0.00 0.02 0.00
#&gt; TCGA.AB.3008.03     8  0.2852      0.550 0.00 0.00 0.00 0.00 0.00 0.00 0.28 0.72
#&gt; TCGA.AB.2942.03     3  0.0000      0.949 0.00 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2872.03     5  0.1563      1.000 0.00 0.10 0.00 0.00 0.90 0.00 0.00 0.00
#&gt; TCGA.AB.2897.03     2  0.2547      0.675 0.12 0.84 0.00 0.00 0.00 0.04 0.00 0.00
#&gt; TCGA.AB.2921.03     7  0.3193      0.899 0.00 0.00 0.00 0.00 0.00 0.00 0.62 0.38
#&gt; TCGA.AB.2862.03     2  0.4779      0.252 0.08 0.60 0.00 0.00 0.28 0.04 0.00 0.00
#&gt; TCGA.AB.2840.03     2  0.3291      0.651 0.28 0.70 0.00 0.00 0.00 0.00 0.02 0.00
#&gt; TCGA.AB.2845.03     7  0.3083      0.962 0.00 0.00 0.00 0.00 0.00 0.00 0.66 0.34
#&gt; TCGA.AB.3009.03     8  0.1741      0.571 0.04 0.00 0.00 0.00 0.02 0.02 0.00 0.92
#&gt; TCGA.AB.2886.03     4  0.2224      0.754 0.00 0.00 0.02 0.86 0.00 0.12 0.00 0.00
#&gt; TCGA.AB.2955.03     7  0.4522      0.843 0.04 0.00 0.00 0.00 0.04 0.00 0.58 0.34
#&gt; TCGA.AB.2892.03     3  0.0000      0.949 0.00 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2906.03     2  0.2981      0.681 0.22 0.76 0.00 0.00 0.00 0.00 0.02 0.00
#&gt; TCGA.AB.2937.03     6  0.2404      0.894 0.00 0.00 0.02 0.14 0.00 0.84 0.00 0.00
#&gt; TCGA.AB.2914.03     4  0.4647      0.696 0.12 0.00 0.02 0.68 0.00 0.00 0.16 0.02
#&gt; TCGA.AB.2980.03     2  0.4019      0.562 0.14 0.74 0.00 0.00 0.00 0.06 0.06 0.00
#&gt; TCGA.AB.2819.03     4  0.0471      0.807 0.00 0.00 0.02 0.98 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2806.03     4  0.0471      0.807 0.00 0.00 0.02 0.98 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2815.03     3  0.0471      0.950 0.00 0.00 0.98 0.00 0.00 0.00 0.02 0.00
#&gt; TCGA.AB.2939.03     8  0.1741      0.571 0.04 0.00 0.00 0.00 0.02 0.02 0.00 0.92
#&gt; TCGA.AB.2979.03     7  0.3083      0.962 0.00 0.00 0.00 0.00 0.00 0.00 0.66 0.34
#&gt; TCGA.AB.2808.03     7  0.3083      0.962 0.00 0.00 0.00 0.00 0.00 0.00 0.66 0.34
#&gt; TCGA.AB.2991.03     5  0.1563      1.000 0.00 0.10 0.00 0.00 0.90 0.00 0.00 0.00
#&gt; TCGA.AB.2803.03     2  0.0000      0.710 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.3000.03     8  0.2852      0.550 0.00 0.00 0.00 0.00 0.00 0.00 0.28 0.72
#&gt; TCGA.AB.2997.03     1  0.6926      0.000 0.44 0.22 0.00 0.02 0.18 0.04 0.10 0.00
#&gt; TCGA.AB.3001.03     5  0.1563      1.000 0.00 0.10 0.00 0.00 0.90 0.00 0.00 0.00
#&gt; TCGA.AB.2954.03     3  0.2350      0.879 0.10 0.00 0.86 0.00 0.04 0.00 0.00 0.00
#&gt; TCGA.AB.2828.03     3  0.0471      0.950 0.00 0.00 0.98 0.00 0.00 0.00 0.02 0.00
#&gt; TCGA.AB.2804.03     2  0.4019      0.562 0.14 0.74 0.00 0.00 0.00 0.06 0.06 0.00
#&gt; TCGA.AB.2950.03     4  0.2224      0.754 0.00 0.00 0.02 0.86 0.00 0.12 0.00 0.00
#&gt; TCGA.AB.3007.03     5  0.1563      1.000 0.00 0.10 0.00 0.00 0.90 0.00 0.00 0.00
#&gt; TCGA.AB.2880.03     7  0.3083      0.962 0.00 0.00 0.00 0.00 0.00 0.00 0.66 0.34
#&gt; TCGA.AB.2889.03     3  0.0471      0.950 0.00 0.00 0.98 0.00 0.00 0.00 0.02 0.00
#&gt; TCGA.AB.2881.03     3  0.0000      0.949 0.00 0.00 1.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2982.03     2  0.0000      0.710 0.00 1.00 0.00 0.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2870.03     3  0.0471      0.950 0.00 0.00 0.98 0.00 0.00 0.00 0.02 0.00
#&gt; TCGA.AB.2909.03     4  0.4647      0.696 0.12 0.00 0.02 0.68 0.00 0.00 0.16 0.02
#&gt; TCGA.AB.2858.03     6  0.2547      0.803 0.00 0.00 0.12 0.04 0.00 0.84 0.00 0.00
#&gt; TCGA.AB.2846.03     3  0.2350      0.879 0.10 0.00 0.86 0.00 0.04 0.00 0.00 0.00
</code></pre>

<script>
$('#tab-node-03-get-classes-7-a').parent().next().next().hide();
$('#tab-node-03-get-classes-7-a').click(function(){
  $('#tab-node-03-get-classes-7-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>
</div>

Heatmaps for the consensus matrix. It visualizes the probability of two
samples to be in a same group.




<script>
$( function() {
	$( '#tabs-node-03-consensus-heatmap' ).tabs();
} );
</script>
<div id='tabs-node-03-consensus-heatmap'>
<ul>
<li><a href='#tab-node-03-consensus-heatmap-1'>k = 2</a></li>
<li><a href='#tab-node-03-consensus-heatmap-2'>k = 3</a></li>
<li><a href='#tab-node-03-consensus-heatmap-3'>k = 4</a></li>
<li><a href='#tab-node-03-consensus-heatmap-4'>k = 5</a></li>
<li><a href='#tab-node-03-consensus-heatmap-5'>k = 6</a></li>
<li><a href='#tab-node-03-consensus-heatmap-6'>k = 7</a></li>
<li><a href='#tab-node-03-consensus-heatmap-7'>k = 8</a></li>
</ul>
<div id='tab-node-03-consensus-heatmap-1'>
<pre><code class="r">consensus_heatmap(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-03-consensus-heatmap-1-1.png" alt="plot of chunk tab-node-03-consensus-heatmap-1"/></p>

</div>
<div id='tab-node-03-consensus-heatmap-2'>
<pre><code class="r">consensus_heatmap(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-03-consensus-heatmap-2-1.png" alt="plot of chunk tab-node-03-consensus-heatmap-2"/></p>

</div>
<div id='tab-node-03-consensus-heatmap-3'>
<pre><code class="r">consensus_heatmap(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-03-consensus-heatmap-3-1.png" alt="plot of chunk tab-node-03-consensus-heatmap-3"/></p>

</div>
<div id='tab-node-03-consensus-heatmap-4'>
<pre><code class="r">consensus_heatmap(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-03-consensus-heatmap-4-1.png" alt="plot of chunk tab-node-03-consensus-heatmap-4"/></p>

</div>
<div id='tab-node-03-consensus-heatmap-5'>
<pre><code class="r">consensus_heatmap(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-03-consensus-heatmap-5-1.png" alt="plot of chunk tab-node-03-consensus-heatmap-5"/></p>

</div>
<div id='tab-node-03-consensus-heatmap-6'>
<pre><code class="r">consensus_heatmap(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-03-consensus-heatmap-6-1.png" alt="plot of chunk tab-node-03-consensus-heatmap-6"/></p>

</div>
<div id='tab-node-03-consensus-heatmap-7'>
<pre><code class="r">consensus_heatmap(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-03-consensus-heatmap-7-1.png" alt="plot of chunk tab-node-03-consensus-heatmap-7"/></p>

</div>
</div>

Heatmaps for the membership of samples in all partitions to see how consistent they are:





<script>
$( function() {
	$( '#tabs-node-03-membership-heatmap' ).tabs();
} );
</script>
<div id='tabs-node-03-membership-heatmap'>
<ul>
<li><a href='#tab-node-03-membership-heatmap-1'>k = 2</a></li>
<li><a href='#tab-node-03-membership-heatmap-2'>k = 3</a></li>
<li><a href='#tab-node-03-membership-heatmap-3'>k = 4</a></li>
<li><a href='#tab-node-03-membership-heatmap-4'>k = 5</a></li>
<li><a href='#tab-node-03-membership-heatmap-5'>k = 6</a></li>
<li><a href='#tab-node-03-membership-heatmap-6'>k = 7</a></li>
<li><a href='#tab-node-03-membership-heatmap-7'>k = 8</a></li>
</ul>
<div id='tab-node-03-membership-heatmap-1'>
<pre><code class="r">membership_heatmap(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-03-membership-heatmap-1-1.png" alt="plot of chunk tab-node-03-membership-heatmap-1"/></p>

</div>
<div id='tab-node-03-membership-heatmap-2'>
<pre><code class="r">membership_heatmap(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-03-membership-heatmap-2-1.png" alt="plot of chunk tab-node-03-membership-heatmap-2"/></p>

</div>
<div id='tab-node-03-membership-heatmap-3'>
<pre><code class="r">membership_heatmap(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-03-membership-heatmap-3-1.png" alt="plot of chunk tab-node-03-membership-heatmap-3"/></p>

</div>
<div id='tab-node-03-membership-heatmap-4'>
<pre><code class="r">membership_heatmap(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-03-membership-heatmap-4-1.png" alt="plot of chunk tab-node-03-membership-heatmap-4"/></p>

</div>
<div id='tab-node-03-membership-heatmap-5'>
<pre><code class="r">membership_heatmap(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-03-membership-heatmap-5-1.png" alt="plot of chunk tab-node-03-membership-heatmap-5"/></p>

</div>
<div id='tab-node-03-membership-heatmap-6'>
<pre><code class="r">membership_heatmap(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-03-membership-heatmap-6-1.png" alt="plot of chunk tab-node-03-membership-heatmap-6"/></p>

</div>
<div id='tab-node-03-membership-heatmap-7'>
<pre><code class="r">membership_heatmap(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-03-membership-heatmap-7-1.png" alt="plot of chunk tab-node-03-membership-heatmap-7"/></p>

</div>
</div>

As soon as the classes for columns are determined, the signatures
that are significantly different between subgroups can be looked for. 
Following are the heatmaps for signatures.






<script>
$( function() {
	$( '#tabs-node-03-get-signatures' ).tabs();
} );
</script>
<div id='tabs-node-03-get-signatures'>
<ul>
<li><a href='#tab-node-03-get-signatures-1'>k = 2</a></li>
<li><a href='#tab-node-03-get-signatures-2'>k = 3</a></li>
<li><a href='#tab-node-03-get-signatures-3'>k = 4</a></li>
<li><a href='#tab-node-03-get-signatures-4'>k = 5</a></li>
<li><a href='#tab-node-03-get-signatures-5'>k = 6</a></li>
<li><a href='#tab-node-03-get-signatures-6'>k = 7</a></li>
<li><a href='#tab-node-03-get-signatures-7'>k = 8</a></li>
</ul>
<div id='tab-node-03-get-signatures-1'>
<pre><code class="r">get_signatures(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-03-get-signatures-1-1.png" alt="plot of chunk tab-node-03-get-signatures-1"/></p>

</div>
<div id='tab-node-03-get-signatures-2'>
<pre><code class="r">get_signatures(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-03-get-signatures-2-1.png" alt="plot of chunk tab-node-03-get-signatures-2"/></p>

</div>
<div id='tab-node-03-get-signatures-3'>
<pre><code class="r">get_signatures(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-03-get-signatures-3-1.png" alt="plot of chunk tab-node-03-get-signatures-3"/></p>

</div>
<div id='tab-node-03-get-signatures-4'>
<pre><code class="r">get_signatures(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-03-get-signatures-4-1.png" alt="plot of chunk tab-node-03-get-signatures-4"/></p>

</div>
<div id='tab-node-03-get-signatures-5'>
<pre><code class="r">get_signatures(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-03-get-signatures-5-1.png" alt="plot of chunk tab-node-03-get-signatures-5"/></p>

</div>
<div id='tab-node-03-get-signatures-6'>
<pre><code class="r">get_signatures(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-03-get-signatures-6-1.png" alt="plot of chunk tab-node-03-get-signatures-6"/></p>

</div>
<div id='tab-node-03-get-signatures-7'>
<pre><code class="r">get_signatures(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-03-get-signatures-7-1.png" alt="plot of chunk tab-node-03-get-signatures-7"/></p>

</div>
</div>



Compare the overlap of signatures from different k:

```r
compare_signatures(res)
```

![plot of chunk node-03-signature_compare](figure_cola/node-03-signature_compare-1.png)

`get_signature()` returns a data frame invisibly. To get the list of signatures, the function
call should be assigned to a variable explicitly. In following code, if `plot` argument is set
to `FALSE`, no heatmap is plotted while only the differential analysis is performed.

```r
# code only for demonstration
tb = get_signature(res, k = ..., plot = FALSE)
```

An example of the output of `tb` is:

```
#>   which_row         fdr    mean_1    mean_2 scaled_mean_1 scaled_mean_2 km
#> 1        38 0.042760348  8.373488  9.131774    -0.5533452     0.5164555  1
#> 2        40 0.018707592  7.106213  8.469186    -0.6173731     0.5762149  1
#> 3        55 0.019134737 10.221463 11.207825    -0.6159697     0.5749050  1
#> 4        59 0.006059896  5.921854  7.869574    -0.6899429     0.6439467  1
#> 5        60 0.018055526  8.928898 10.211722    -0.6204761     0.5791110  1
#> 6        98 0.009384629 15.714769 14.887706     0.6635654    -0.6193277  2
...
```

The columns in `tb` are:

1. `which_row`: row indices corresponding to the input matrix.
2. `fdr`: FDR for the differential test. 
3. `mean_x`: The mean value in group x.
4. `scaled_mean_x`: The mean value in group x after rows are scaled.
5. `km`: Row groups if k-means clustering is applied to rows (which is done by automatically selecting number of clusters).

If there are too many signatures, `top_signatures = ...` can be set to only show the 
signatures with the highest FDRs:

```r
# code only for demonstration
# e.g. to show the top 500 most significant rows
tb = get_signature(res, k = ..., top_signatures = 500)
```

If the signatures are defined as these which are uniquely high in current group, `diff_method` argument
can be set to `"uniquely_high_in_one_group"`:

```r
# code only for demonstration
tb = get_signature(res, k = ..., diff_method = "uniquely_high_in_one_group")
```




UMAP plot which shows how samples are separated.


<script>
$( function() {
	$( '#tabs-node-03-dimension-reduction' ).tabs();
} );
</script>
<div id='tabs-node-03-dimension-reduction'>
<ul>
<li><a href='#tab-node-03-dimension-reduction-1'>k = 2</a></li>
<li><a href='#tab-node-03-dimension-reduction-2'>k = 3</a></li>
<li><a href='#tab-node-03-dimension-reduction-3'>k = 4</a></li>
<li><a href='#tab-node-03-dimension-reduction-4'>k = 5</a></li>
<li><a href='#tab-node-03-dimension-reduction-5'>k = 6</a></li>
<li><a href='#tab-node-03-dimension-reduction-6'>k = 7</a></li>
<li><a href='#tab-node-03-dimension-reduction-7'>k = 8</a></li>
</ul>
<div id='tab-node-03-dimension-reduction-1'>
<pre><code class="r">dimension_reduction(res, k = 2, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-03-dimension-reduction-1-1.png" alt="plot of chunk tab-node-03-dimension-reduction-1"/></p>

</div>
<div id='tab-node-03-dimension-reduction-2'>
<pre><code class="r">dimension_reduction(res, k = 3, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-03-dimension-reduction-2-1.png" alt="plot of chunk tab-node-03-dimension-reduction-2"/></p>

</div>
<div id='tab-node-03-dimension-reduction-3'>
<pre><code class="r">dimension_reduction(res, k = 4, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-03-dimension-reduction-3-1.png" alt="plot of chunk tab-node-03-dimension-reduction-3"/></p>

</div>
<div id='tab-node-03-dimension-reduction-4'>
<pre><code class="r">dimension_reduction(res, k = 5, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-03-dimension-reduction-4-1.png" alt="plot of chunk tab-node-03-dimension-reduction-4"/></p>

</div>
<div id='tab-node-03-dimension-reduction-5'>
<pre><code class="r">dimension_reduction(res, k = 6, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-03-dimension-reduction-5-1.png" alt="plot of chunk tab-node-03-dimension-reduction-5"/></p>

</div>
<div id='tab-node-03-dimension-reduction-6'>
<pre><code class="r">dimension_reduction(res, k = 7, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-03-dimension-reduction-6-1.png" alt="plot of chunk tab-node-03-dimension-reduction-6"/></p>

</div>
<div id='tab-node-03-dimension-reduction-7'>
<pre><code class="r">dimension_reduction(res, k = 8, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-03-dimension-reduction-7-1.png" alt="plot of chunk tab-node-03-dimension-reduction-7"/></p>

</div>
</div>



Following heatmap shows how subgroups are split when increasing `k`:

```r
collect_classes(res)
```

![plot of chunk node-03-collect-classes](figure_cola/node-03-collect-classes-1.png)



If matrix rows can be associated to genes, consider to use `functional_enrichment(res,
...)` to perform function enrichment for the signature genes. See [this vignette](https://jokergoo.github.io/cola_vignettes/functional_enrichment.html) for more detailed explanations.


 

---------------------------------------------------




### Node032


Parent node: [Node03](#Node03).
Child nodes: 
                Node0111-leaf
        ,
                Node0112-leaf
        ,
                Node0131-leaf
        ,
                Node0132-leaf
        ,
                Node0141-leaf
        ,
                Node0142-leaf
        ,
                Node0211-leaf
        ,
                Node0212-leaf
        ,
                Node0213-leaf
        ,
                Node0221-leaf
        ,
                [Node0222](#Node0222)
        ,
                Node0231-leaf
        ,
                Node0232-leaf
        ,
                Node0233-leaf
        ,
                Node0321-leaf
        ,
                Node0322-leaf
        ,
                Node0323-leaf
        ,
                Node0324-leaf
        ,
                Node0325-leaf
        ,
                Node0331-leaf
        ,
                Node0332-leaf
        .







The object with results only for a single top-value method and a single partitioning method 
can be extracted as:

```r
res = res_rh["032"]
```

A summary of `res` and all the functions that can be applied to it:

```r
res
```

```
#> A 'ConsensusPartition' object with k = 2, 3, 4, 5, 6, 7, 8.
#>   On a matrix with 30000 rows and 18 columns.
#>   Top rows (1000) are extracted by 'ATC' method.
#>   Subgroups are detected by 'skmeans' method.
#>   Performed in total 350 partitions by row resampling.
#>   Best k for subgroups seems to be 5.
#> 
#> Following methods can be applied to this 'ConsensusPartition' object:
#>  [1] "cola_report"             "collect_classes"         "collect_plots"          
#>  [4] "collect_stats"           "colnames"                "compare_partitions"     
#>  [7] "compare_signatures"      "consensus_heatmap"       "dimension_reduction"    
#> [10] "functional_enrichment"   "get_anno_col"            "get_anno"               
#> [13] "get_classes"             "get_consensus"           "get_matrix"             
#> [16] "get_membership"          "get_param"               "get_signatures"         
#> [19] "get_stats"               "is_best_k"               "is_stable_k"            
#> [22] "membership_heatmap"      "ncol"                    "nrow"                   
#> [25] "plot_ecdf"               "predict_classes"         "rownames"               
#> [28] "select_partition_number" "show"                    "suggest_best_k"         
#> [31] "test_to_known_factors"   "top_rows_heatmap"
```

`collect_plots()` function collects all the plots made from `res` for all `k` (number of subgroups)
into one single page to provide an easy and fast comparison between different `k`.

```r
collect_plots(res)
```

![plot of chunk node-032-collect-plots](figure_cola/node-032-collect-plots-1.png)

The plots are:

- The first row: a plot of the eCDF (empirical cumulative distribution
  function) curves of the consensus matrix for each `k` and the heatmap of
  predicted classes for each `k`.
- The second row: heatmaps of the consensus matrix for each `k`.
- The third row: heatmaps of the membership matrix for each `k`.
- The fouth row: heatmaps of the signatures for each `k`.

All the plots in panels can be made by individual functions and they are
plotted later in this section.

`select_partition_number()` produces several plots showing different
statistics for choosing "optimized" `k`. There are following statistics:

- eCDF curves of the consensus matrix for each `k`;
- 1-PAC. [The PAC score](https://en.wikipedia.org/wiki/Consensus_clustering#Over-interpretation_potential_of_consensus_clustering)
  measures the proportion of the ambiguous subgrouping.
- Mean silhouette score.
- Concordance. The mean probability of fiting the consensus subgroup labels in all
  partitions.
- Area increased. Denote $A_k$ as the area under the eCDF curve for current
  `k`, the area increased is defined as $A_k - A_{k-1}$.
- Rand index. The percent of pairs of samples that are both in a same cluster
  or both are not in a same cluster in the partition of k and k-1.
- Jaccard index. The ratio of pairs of samples are both in a same cluster in
  the partition of k and k-1 and the pairs of samples are both in a same
  cluster in the partition k or k-1.

The detailed explanations of these statistics can be found in [the _cola_
vignette](https://jokergoo.github.io/cola_vignettes/cola.html#toc_13).

Generally speaking, higher 1-PAC score, higher mean silhouette score or higher
concordance corresponds to better partition. Rand index and Jaccard index
measure how similar the current partition is compared to partition with `k-1`.
If they are too similar, we won't accept `k` is better than `k-1`.

```r
select_partition_number(res)
```

![plot of chunk node-032-select-partition-number](figure_cola/node-032-select-partition-number-1.png)

The numeric values for all these statistics can be obtained by `get_stats()`.

```r
get_stats(res)
```

```
#>   k 1-PAC mean_silhouette concordance area_increased  Rand Jaccard
#> 2 2 1.000           1.000       1.000         0.5234 0.477   0.477
#> 3 3 0.922           0.982       0.989         0.1871 0.902   0.795
#> 4 4 0.935           0.977       0.970         0.2387 0.843   0.586
#> 5 5 0.987           0.976       0.988         0.0588 0.961   0.824
#> 6 6 0.980           0.821       0.939         0.0135 0.993   0.964
#> 7 7 0.928           0.776       0.968         0.0123 0.987   0.926
#> 8 8 0.856           0.647       0.947         0.0139 0.993   0.960
```

`suggest_best_k()` suggests the best $k$ based on these statistics. The rules are as follows:

- All $k$ with Jaccard index larger than 0.95 are removed because increasing
  $k$ does not provide enough extra information. If all $k$ are removed, it is
  marked as no subgroup is detected.
- For all $k$ with 1-PAC score larger than 0.9, the maximal $k$ is taken as
  the best $k$, and other $k$ are marked as optional $k$.
- If it does not fit the second rule. The $k$ with the maximal vote of the
  highest 1-PAC score, highest mean silhouette, and highest concordance is
  taken as the best $k$.

```r
suggest_best_k(res)
```

```
#> [1] 5
#> attr(,"optional")
#> [1] 2 3 4
```

There is also optional best $k$ = 2 3 4 that is worth to check.

Following is the table of the partitions (You need to click the **show/hide
code output** link to see it). The membership matrix (columns with name `p*`)
is inferred by
[`clue::cl_consensus()`](https://www.rdocumentation.org/link/cl_consensus?package=clue)
function with the `SE` method. Basically the value in the membership matrix
represents the probability to belong to a certain group. The finall subgroup
label for an item is determined with the group with highest probability it
belongs to.

In `get_classes()` function, the entropy is calculated from the membership
matrix and the silhouette score is calculated from the consensus matrix.



<script>
$( function() {
	$( '#tabs-node-032-get-classes' ).tabs();
} );
</script>
<div id='tabs-node-032-get-classes'>
<ul>
<li><a href='#tab-node-032-get-classes-1'>k = 2</a></li>
<li><a href='#tab-node-032-get-classes-2'>k = 3</a></li>
<li><a href='#tab-node-032-get-classes-3'>k = 4</a></li>
<li><a href='#tab-node-032-get-classes-4'>k = 5</a></li>
<li><a href='#tab-node-032-get-classes-5'>k = 6</a></li>
<li><a href='#tab-node-032-get-classes-6'>k = 7</a></li>
<li><a href='#tab-node-032-get-classes-7'>k = 8</a></li>
</ul>

<div id='tab-node-032-get-classes-1'>
<p><a id='tab-node-032-get-classes-1-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 2), get_membership(res, k = 2))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette p1 p2
#&gt; TCGA.AB.2998.03     1       0          1  1  0
#&gt; TCGA.AB.2823.03     1       0          1  1  0
#&gt; TCGA.AB.2999.03     2       0          1  0  1
#&gt; TCGA.AB.3012.03     2       0          1  0  1
#&gt; TCGA.AB.2841.03     1       0          1  1  0
#&gt; TCGA.AB.2872.03     2       0          1  0  1
#&gt; TCGA.AB.2897.03     1       0          1  1  0
#&gt; TCGA.AB.2862.03     1       0          1  1  0
#&gt; TCGA.AB.2840.03     2       0          1  0  1
#&gt; TCGA.AB.2906.03     2       0          1  0  1
#&gt; TCGA.AB.2980.03     2       0          1  0  1
#&gt; TCGA.AB.2991.03     1       0          1  1  0
#&gt; TCGA.AB.2803.03     1       0          1  1  0
#&gt; TCGA.AB.2997.03     1       0          1  1  0
#&gt; TCGA.AB.3001.03     1       0          1  1  0
#&gt; TCGA.AB.2804.03     2       0          1  0  1
#&gt; TCGA.AB.3007.03     2       0          1  0  1
#&gt; TCGA.AB.2982.03     1       0          1  1  0
</code></pre>

<script>
$('#tab-node-032-get-classes-1-a').parent().next().next().hide();
$('#tab-node-032-get-classes-1-a').click(function(){
  $('#tab-node-032-get-classes-1-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-032-get-classes-2'>
<p><a id='tab-node-032-get-classes-2-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 3), get_membership(res, k = 3))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette p1  p2  p3
#&gt; TCGA.AB.2998.03     1   0.000      1.000  1 0.0 0.0
#&gt; TCGA.AB.2823.03     1   0.000      1.000  1 0.0 0.0
#&gt; TCGA.AB.2999.03     2   0.000      0.948  0 1.0 0.0
#&gt; TCGA.AB.3012.03     3   0.000      1.000  0 0.0 1.0
#&gt; TCGA.AB.2841.03     1   0.000      1.000  1 0.0 0.0
#&gt; TCGA.AB.2872.03     3   0.000      1.000  0 0.0 1.0
#&gt; TCGA.AB.2897.03     1   0.000      1.000  1 0.0 0.0
#&gt; TCGA.AB.2862.03     1   0.000      1.000  1 0.0 0.0
#&gt; TCGA.AB.2840.03     2   0.296      0.917  0 0.9 0.1
#&gt; TCGA.AB.2906.03     2   0.296      0.917  0 0.9 0.1
#&gt; TCGA.AB.2980.03     2   0.000      0.948  0 1.0 0.0
#&gt; TCGA.AB.2991.03     1   0.000      1.000  1 0.0 0.0
#&gt; TCGA.AB.2803.03     1   0.000      1.000  1 0.0 0.0
#&gt; TCGA.AB.2997.03     1   0.000      1.000  1 0.0 0.0
#&gt; TCGA.AB.3001.03     1   0.000      1.000  1 0.0 0.0
#&gt; TCGA.AB.2804.03     2   0.000      0.948  0 1.0 0.0
#&gt; TCGA.AB.3007.03     3   0.000      1.000  0 0.0 1.0
#&gt; TCGA.AB.2982.03     1   0.000      1.000  1 0.0 0.0
</code></pre>

<script>
$('#tab-node-032-get-classes-2-a').parent().next().next().hide();
$('#tab-node-032-get-classes-2-a').click(function(){
  $('#tab-node-032-get-classes-2-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-032-get-classes-3'>
<p><a id='tab-node-032-get-classes-3-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 4), get_membership(res, k = 4))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4
#&gt; TCGA.AB.2998.03     1   0.000      1.000 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2823.03     4   0.234      0.961 0.10 0.00 0.00 0.90
#&gt; TCGA.AB.2999.03     2   0.000      0.944 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.3012.03     3   0.000      1.000 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2841.03     1   0.000      1.000 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2872.03     3   0.000      1.000 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2897.03     1   0.000      1.000 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2862.03     1   0.000      1.000 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2840.03     2   0.164      0.934 0.00 0.94 0.06 0.00
#&gt; TCGA.AB.2906.03     2   0.164      0.934 0.00 0.94 0.06 0.00
#&gt; TCGA.AB.2980.03     2   0.164      0.939 0.00 0.94 0.00 0.06
#&gt; TCGA.AB.2991.03     4   0.164      0.977 0.06 0.00 0.00 0.94
#&gt; TCGA.AB.2803.03     1   0.000      1.000 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2997.03     4   0.201      0.976 0.08 0.00 0.00 0.92
#&gt; TCGA.AB.3001.03     4   0.164      0.977 0.06 0.00 0.00 0.94
#&gt; TCGA.AB.2804.03     2   0.164      0.939 0.00 0.94 0.00 0.06
#&gt; TCGA.AB.3007.03     3   0.000      1.000 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.2982.03     1   0.000      1.000 1.00 0.00 0.00 0.00
</code></pre>

<script>
$('#tab-node-032-get-classes-3-a').parent().next().next().hide();
$('#tab-node-032-get-classes-3-a').click(function(){
  $('#tab-node-032-get-classes-3-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-032-get-classes-4'>
<p><a id='tab-node-032-get-classes-4-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 5), get_membership(res, k = 5))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2 p3   p4   p5
#&gt; TCGA.AB.2998.03     1  0.0000      1.000 1.00 0.00  0 0.00 0.00
#&gt; TCGA.AB.2823.03     4  0.1732      0.892 0.08 0.00  0 0.92 0.00
#&gt; TCGA.AB.2999.03     2  0.1732      0.925 0.00 0.92  0 0.00 0.08
#&gt; TCGA.AB.3012.03     3  0.0000      1.000 0.00 0.00  1 0.00 0.00
#&gt; TCGA.AB.2841.03     1  0.0000      1.000 1.00 0.00  0 0.00 0.00
#&gt; TCGA.AB.2872.03     3  0.0000      1.000 0.00 0.00  1 0.00 0.00
#&gt; TCGA.AB.2897.03     1  0.0000      1.000 1.00 0.00  0 0.00 0.00
#&gt; TCGA.AB.2862.03     1  0.0000      1.000 1.00 0.00  0 0.00 0.00
#&gt; TCGA.AB.2840.03     2  0.0000      0.950 0.00 1.00  0 0.00 0.00
#&gt; TCGA.AB.2906.03     2  0.0609      0.957 0.00 0.98  0 0.00 0.02
#&gt; TCGA.AB.2980.03     5  0.0609      0.972 0.00 0.02  0 0.00 0.98
#&gt; TCGA.AB.2991.03     4  0.0000      0.965 0.00 0.00  0 1.00 0.00
#&gt; TCGA.AB.2803.03     1  0.0000      1.000 1.00 0.00  0 0.00 0.00
#&gt; TCGA.AB.2997.03     4  0.0000      0.965 0.00 0.00  0 1.00 0.00
#&gt; TCGA.AB.3001.03     4  0.0000      0.965 0.00 0.00  0 1.00 0.00
#&gt; TCGA.AB.2804.03     5  0.0609      0.972 0.00 0.02  0 0.00 0.98
#&gt; TCGA.AB.3007.03     3  0.0000      1.000 0.00 0.00  1 0.00 0.00
#&gt; TCGA.AB.2982.03     1  0.0000      1.000 1.00 0.00  0 0.00 0.00
</code></pre>

<script>
$('#tab-node-032-get-classes-4-a').parent().next().next().hide();
$('#tab-node-032-get-classes-4-a').click(function(){
  $('#tab-node-032-get-classes-4-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-032-get-classes-5'>
<p><a id='tab-node-032-get-classes-5-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 6), get_membership(res, k = 6))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2 p3   p4   p5   p6
#&gt; TCGA.AB.2998.03     1  0.0000      1.000 1.00 0.00  0 0.00 0.00 0.00
#&gt; TCGA.AB.2823.03     4  0.0937      0.955 0.04 0.00  0 0.96 0.00 0.00
#&gt; TCGA.AB.2999.03     2  0.5095      0.426 0.00 0.50  0 0.00 0.08 0.42
#&gt; TCGA.AB.3012.03     3  0.0000      1.000 0.00 0.00  1 0.00 0.00 0.00
#&gt; TCGA.AB.2841.03     1  0.0000      1.000 1.00 0.00  0 0.00 0.00 0.00
#&gt; TCGA.AB.2872.03     3  0.0000      1.000 0.00 0.00  1 0.00 0.00 0.00
#&gt; TCGA.AB.2897.03     1  0.0000      1.000 1.00 0.00  0 0.00 0.00 0.00
#&gt; TCGA.AB.2862.03     1  0.0000      1.000 1.00 0.00  0 0.00 0.00 0.00
#&gt; TCGA.AB.2840.03     2  0.0937      0.734 0.00 0.96  0 0.00 0.00 0.04
#&gt; TCGA.AB.2906.03     2  0.0000      0.742 0.00 1.00  0 0.00 0.00 0.00
#&gt; TCGA.AB.2980.03     5  0.0000      0.000 0.00 0.00  0 0.00 1.00 0.00
#&gt; TCGA.AB.2991.03     4  0.0000      0.973 0.00 0.00  0 1.00 0.00 0.00
#&gt; TCGA.AB.2803.03     1  0.0000      1.000 1.00 0.00  0 0.00 0.00 0.00
#&gt; TCGA.AB.2997.03     4  0.0547      0.972 0.02 0.00  0 0.98 0.00 0.00
#&gt; TCGA.AB.3001.03     4  0.0000      0.973 0.00 0.00  0 1.00 0.00 0.00
#&gt; TCGA.AB.2804.03     6  0.3851      0.000 0.00 0.00  0 0.00 0.46 0.54
#&gt; TCGA.AB.3007.03     3  0.0000      1.000 0.00 0.00  1 0.00 0.00 0.00
#&gt; TCGA.AB.2982.03     1  0.0000      1.000 1.00 0.00  0 0.00 0.00 0.00
</code></pre>

<script>
$('#tab-node-032-get-classes-5-a').parent().next().next().hide();
$('#tab-node-032-get-classes-5-a').click(function(){
  $('#tab-node-032-get-classes-5-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-032-get-classes-6'>
<p><a id='tab-node-032-get-classes-6-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 7), get_membership(res, k = 7))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2 p3   p4   p5   p6   p7
#&gt; TCGA.AB.2998.03     1  0.0863      0.965 0.96 0.00  0 0.00 0.00 0.00 0.04
#&gt; TCGA.AB.2823.03     4  0.2722      0.798 0.12 0.00  0 0.84 0.00 0.00 0.04
#&gt; TCGA.AB.2999.03     7  0.0863      0.000 0.00 0.04  0 0.00 0.00 0.00 0.96
#&gt; TCGA.AB.3012.03     3  0.0000      1.000 0.00 0.00  1 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2841.03     1  0.0000      0.983 1.00 0.00  0 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2872.03     3  0.0000      1.000 0.00 0.00  1 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2897.03     1  0.0000      0.983 1.00 0.00  0 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2862.03     1  0.0863      0.965 0.96 0.00  0 0.00 0.00 0.00 0.04
#&gt; TCGA.AB.2840.03     2  0.0000      0.789 0.00 1.00  0 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2906.03     2  0.3199      0.772 0.00 0.80  0 0.00 0.06 0.00 0.14
#&gt; TCGA.AB.2980.03     5  0.1166      0.000 0.00 0.00  0 0.00 0.94 0.06 0.00
#&gt; TCGA.AB.2991.03     4  0.0000      0.917 0.00 0.00  0 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2803.03     1  0.0000      0.983 1.00 0.00  0 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2997.03     4  0.0863      0.911 0.00 0.00  0 0.96 0.00 0.00 0.04
#&gt; TCGA.AB.3001.03     4  0.0000      0.917 0.00 0.00  0 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2804.03     6  0.0000      0.000 0.00 0.00  0 0.00 0.00 1.00 0.00
#&gt; TCGA.AB.3007.03     3  0.0000      1.000 0.00 0.00  1 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2982.03     1  0.0000      0.983 1.00 0.00  0 0.00 0.00 0.00 0.00
</code></pre>

<script>
$('#tab-node-032-get-classes-6-a').parent().next().next().hide();
$('#tab-node-032-get-classes-6-a').click(function(){
  $('#tab-node-032-get-classes-6-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-032-get-classes-7'>
<p><a id='tab-node-032-get-classes-7-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 8), get_membership(res, k = 8))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2 p3   p4 p5 p6   p7   p8
#&gt; TCGA.AB.2998.03     1  0.1563      0.900 0.90 0.00  0 0.10  0  0 0.00 0.00
#&gt; TCGA.AB.2823.03     4  0.1947      0.682 0.14 0.00  0 0.86  0  0 0.00 0.00
#&gt; TCGA.AB.2999.03     7  0.0471      0.000 0.00 0.00  0 0.00  0  0 0.98 0.02
#&gt; TCGA.AB.3012.03     3  0.0000      1.000 0.00 0.00  1 0.00  0  0 0.00 0.00
#&gt; TCGA.AB.2841.03     1  0.0000      0.949 1.00 0.00  0 0.00  0  0 0.00 0.00
#&gt; TCGA.AB.2872.03     3  0.0000      1.000 0.00 0.00  1 0.00  0  0 0.00 0.00
#&gt; TCGA.AB.2897.03     1  0.0000      0.949 1.00 0.00  0 0.00  0  0 0.00 0.00
#&gt; TCGA.AB.2862.03     1  0.1947      0.868 0.86 0.00  0 0.14  0  0 0.00 0.00
#&gt; TCGA.AB.2840.03     2  0.2267      0.000 0.00 0.82  0 0.00  0  0 0.00 0.18
#&gt; TCGA.AB.2906.03     8  0.0000      0.000 0.00 0.00  0 0.00  0  0 0.00 1.00
#&gt; TCGA.AB.2980.03     5  0.0000      0.000 0.00 0.00  0 0.00  1  0 0.00 0.00
#&gt; TCGA.AB.2991.03     4  0.2569      0.811 0.00 0.16  0 0.82  0  0 0.02 0.00
#&gt; TCGA.AB.2803.03     1  0.0000      0.949 1.00 0.00  0 0.00  0  0 0.00 0.00
#&gt; TCGA.AB.2997.03     4  0.0471      0.787 0.00 0.02  0 0.98  0  0 0.00 0.00
#&gt; TCGA.AB.3001.03     4  0.2569      0.811 0.00 0.16  0 0.82  0  0 0.02 0.00
#&gt; TCGA.AB.2804.03     6  0.0000      0.000 0.00 0.00  0 0.00  0  1 0.00 0.00
#&gt; TCGA.AB.3007.03     3  0.0000      1.000 0.00 0.00  1 0.00  0  0 0.00 0.00
#&gt; TCGA.AB.2982.03     1  0.0000      0.949 1.00 0.00  0 0.00  0  0 0.00 0.00
</code></pre>

<script>
$('#tab-node-032-get-classes-7-a').parent().next().next().hide();
$('#tab-node-032-get-classes-7-a').click(function(){
  $('#tab-node-032-get-classes-7-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>
</div>

Heatmaps for the consensus matrix. It visualizes the probability of two
samples to be in a same group.




<script>
$( function() {
	$( '#tabs-node-032-consensus-heatmap' ).tabs();
} );
</script>
<div id='tabs-node-032-consensus-heatmap'>
<ul>
<li><a href='#tab-node-032-consensus-heatmap-1'>k = 2</a></li>
<li><a href='#tab-node-032-consensus-heatmap-2'>k = 3</a></li>
<li><a href='#tab-node-032-consensus-heatmap-3'>k = 4</a></li>
<li><a href='#tab-node-032-consensus-heatmap-4'>k = 5</a></li>
<li><a href='#tab-node-032-consensus-heatmap-5'>k = 6</a></li>
<li><a href='#tab-node-032-consensus-heatmap-6'>k = 7</a></li>
<li><a href='#tab-node-032-consensus-heatmap-7'>k = 8</a></li>
</ul>
<div id='tab-node-032-consensus-heatmap-1'>
<pre><code class="r">consensus_heatmap(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-032-consensus-heatmap-1-1.png" alt="plot of chunk tab-node-032-consensus-heatmap-1"/></p>

</div>
<div id='tab-node-032-consensus-heatmap-2'>
<pre><code class="r">consensus_heatmap(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-032-consensus-heatmap-2-1.png" alt="plot of chunk tab-node-032-consensus-heatmap-2"/></p>

</div>
<div id='tab-node-032-consensus-heatmap-3'>
<pre><code class="r">consensus_heatmap(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-032-consensus-heatmap-3-1.png" alt="plot of chunk tab-node-032-consensus-heatmap-3"/></p>

</div>
<div id='tab-node-032-consensus-heatmap-4'>
<pre><code class="r">consensus_heatmap(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-032-consensus-heatmap-4-1.png" alt="plot of chunk tab-node-032-consensus-heatmap-4"/></p>

</div>
<div id='tab-node-032-consensus-heatmap-5'>
<pre><code class="r">consensus_heatmap(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-032-consensus-heatmap-5-1.png" alt="plot of chunk tab-node-032-consensus-heatmap-5"/></p>

</div>
<div id='tab-node-032-consensus-heatmap-6'>
<pre><code class="r">consensus_heatmap(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-032-consensus-heatmap-6-1.png" alt="plot of chunk tab-node-032-consensus-heatmap-6"/></p>

</div>
<div id='tab-node-032-consensus-heatmap-7'>
<pre><code class="r">consensus_heatmap(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-032-consensus-heatmap-7-1.png" alt="plot of chunk tab-node-032-consensus-heatmap-7"/></p>

</div>
</div>

Heatmaps for the membership of samples in all partitions to see how consistent they are:





<script>
$( function() {
	$( '#tabs-node-032-membership-heatmap' ).tabs();
} );
</script>
<div id='tabs-node-032-membership-heatmap'>
<ul>
<li><a href='#tab-node-032-membership-heatmap-1'>k = 2</a></li>
<li><a href='#tab-node-032-membership-heatmap-2'>k = 3</a></li>
<li><a href='#tab-node-032-membership-heatmap-3'>k = 4</a></li>
<li><a href='#tab-node-032-membership-heatmap-4'>k = 5</a></li>
<li><a href='#tab-node-032-membership-heatmap-5'>k = 6</a></li>
<li><a href='#tab-node-032-membership-heatmap-6'>k = 7</a></li>
<li><a href='#tab-node-032-membership-heatmap-7'>k = 8</a></li>
</ul>
<div id='tab-node-032-membership-heatmap-1'>
<pre><code class="r">membership_heatmap(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-032-membership-heatmap-1-1.png" alt="plot of chunk tab-node-032-membership-heatmap-1"/></p>

</div>
<div id='tab-node-032-membership-heatmap-2'>
<pre><code class="r">membership_heatmap(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-032-membership-heatmap-2-1.png" alt="plot of chunk tab-node-032-membership-heatmap-2"/></p>

</div>
<div id='tab-node-032-membership-heatmap-3'>
<pre><code class="r">membership_heatmap(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-032-membership-heatmap-3-1.png" alt="plot of chunk tab-node-032-membership-heatmap-3"/></p>

</div>
<div id='tab-node-032-membership-heatmap-4'>
<pre><code class="r">membership_heatmap(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-032-membership-heatmap-4-1.png" alt="plot of chunk tab-node-032-membership-heatmap-4"/></p>

</div>
<div id='tab-node-032-membership-heatmap-5'>
<pre><code class="r">membership_heatmap(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-032-membership-heatmap-5-1.png" alt="plot of chunk tab-node-032-membership-heatmap-5"/></p>

</div>
<div id='tab-node-032-membership-heatmap-6'>
<pre><code class="r">membership_heatmap(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-032-membership-heatmap-6-1.png" alt="plot of chunk tab-node-032-membership-heatmap-6"/></p>

</div>
<div id='tab-node-032-membership-heatmap-7'>
<pre><code class="r">membership_heatmap(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-032-membership-heatmap-7-1.png" alt="plot of chunk tab-node-032-membership-heatmap-7"/></p>

</div>
</div>

As soon as the classes for columns are determined, the signatures
that are significantly different between subgroups can be looked for. 
Following are the heatmaps for signatures.






<script>
$( function() {
	$( '#tabs-node-032-get-signatures' ).tabs();
} );
</script>
<div id='tabs-node-032-get-signatures'>
<ul>
<li><a href='#tab-node-032-get-signatures-1'>k = 2</a></li>
<li><a href='#tab-node-032-get-signatures-2'>k = 3</a></li>
<li><a href='#tab-node-032-get-signatures-3'>k = 4</a></li>
<li><a href='#tab-node-032-get-signatures-4'>k = 5</a></li>
<li><a href='#tab-node-032-get-signatures-5'>k = 6</a></li>
<li><a href='#tab-node-032-get-signatures-6'>k = 7</a></li>
<li><a href='#tab-node-032-get-signatures-7'>k = 8</a></li>
</ul>
<div id='tab-node-032-get-signatures-1'>
<pre><code class="r">get_signatures(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-032-get-signatures-1-1.png" alt="plot of chunk tab-node-032-get-signatures-1"/></p>

</div>
<div id='tab-node-032-get-signatures-2'>
<pre><code class="r">get_signatures(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-032-get-signatures-2-1.png" alt="plot of chunk tab-node-032-get-signatures-2"/></p>

</div>
<div id='tab-node-032-get-signatures-3'>
<pre><code class="r">get_signatures(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-032-get-signatures-3-1.png" alt="plot of chunk tab-node-032-get-signatures-3"/></p>

</div>
<div id='tab-node-032-get-signatures-4'>
<pre><code class="r">get_signatures(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-032-get-signatures-4-1.png" alt="plot of chunk tab-node-032-get-signatures-4"/></p>

</div>
<div id='tab-node-032-get-signatures-5'>
<pre><code class="r">get_signatures(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-032-get-signatures-5-1.png" alt="plot of chunk tab-node-032-get-signatures-5"/></p>

</div>
<div id='tab-node-032-get-signatures-6'>
<pre><code class="r">get_signatures(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-032-get-signatures-6-1.png" alt="plot of chunk tab-node-032-get-signatures-6"/></p>

</div>
<div id='tab-node-032-get-signatures-7'>
<pre><code class="r">get_signatures(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-032-get-signatures-7-1.png" alt="plot of chunk tab-node-032-get-signatures-7"/></p>

</div>
</div>



Compare the overlap of signatures from different k:

```r
compare_signatures(res)
```

![plot of chunk node-032-signature_compare](figure_cola/node-032-signature_compare-1.png)

`get_signature()` returns a data frame invisibly. To get the list of signatures, the function
call should be assigned to a variable explicitly. In following code, if `plot` argument is set
to `FALSE`, no heatmap is plotted while only the differential analysis is performed.

```r
# code only for demonstration
tb = get_signature(res, k = ..., plot = FALSE)
```

An example of the output of `tb` is:

```
#>   which_row         fdr    mean_1    mean_2 scaled_mean_1 scaled_mean_2 km
#> 1        38 0.042760348  8.373488  9.131774    -0.5533452     0.5164555  1
#> 2        40 0.018707592  7.106213  8.469186    -0.6173731     0.5762149  1
#> 3        55 0.019134737 10.221463 11.207825    -0.6159697     0.5749050  1
#> 4        59 0.006059896  5.921854  7.869574    -0.6899429     0.6439467  1
#> 5        60 0.018055526  8.928898 10.211722    -0.6204761     0.5791110  1
#> 6        98 0.009384629 15.714769 14.887706     0.6635654    -0.6193277  2
...
```

The columns in `tb` are:

1. `which_row`: row indices corresponding to the input matrix.
2. `fdr`: FDR for the differential test. 
3. `mean_x`: The mean value in group x.
4. `scaled_mean_x`: The mean value in group x after rows are scaled.
5. `km`: Row groups if k-means clustering is applied to rows (which is done by automatically selecting number of clusters).

If there are too many signatures, `top_signatures = ...` can be set to only show the 
signatures with the highest FDRs:

```r
# code only for demonstration
# e.g. to show the top 500 most significant rows
tb = get_signature(res, k = ..., top_signatures = 500)
```

If the signatures are defined as these which are uniquely high in current group, `diff_method` argument
can be set to `"uniquely_high_in_one_group"`:

```r
# code only for demonstration
tb = get_signature(res, k = ..., diff_method = "uniquely_high_in_one_group")
```




UMAP plot which shows how samples are separated.


<script>
$( function() {
	$( '#tabs-node-032-dimension-reduction' ).tabs();
} );
</script>
<div id='tabs-node-032-dimension-reduction'>
<ul>
<li><a href='#tab-node-032-dimension-reduction-1'>k = 2</a></li>
<li><a href='#tab-node-032-dimension-reduction-2'>k = 3</a></li>
<li><a href='#tab-node-032-dimension-reduction-3'>k = 4</a></li>
<li><a href='#tab-node-032-dimension-reduction-4'>k = 5</a></li>
<li><a href='#tab-node-032-dimension-reduction-5'>k = 6</a></li>
<li><a href='#tab-node-032-dimension-reduction-6'>k = 7</a></li>
<li><a href='#tab-node-032-dimension-reduction-7'>k = 8</a></li>
</ul>
<div id='tab-node-032-dimension-reduction-1'>
<pre><code class="r">dimension_reduction(res, k = 2, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-032-dimension-reduction-1-1.png" alt="plot of chunk tab-node-032-dimension-reduction-1"/></p>

</div>
<div id='tab-node-032-dimension-reduction-2'>
<pre><code class="r">dimension_reduction(res, k = 3, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-032-dimension-reduction-2-1.png" alt="plot of chunk tab-node-032-dimension-reduction-2"/></p>

</div>
<div id='tab-node-032-dimension-reduction-3'>
<pre><code class="r">dimension_reduction(res, k = 4, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-032-dimension-reduction-3-1.png" alt="plot of chunk tab-node-032-dimension-reduction-3"/></p>

</div>
<div id='tab-node-032-dimension-reduction-4'>
<pre><code class="r">dimension_reduction(res, k = 5, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-032-dimension-reduction-4-1.png" alt="plot of chunk tab-node-032-dimension-reduction-4"/></p>

</div>
<div id='tab-node-032-dimension-reduction-5'>
<pre><code class="r">dimension_reduction(res, k = 6, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-032-dimension-reduction-5-1.png" alt="plot of chunk tab-node-032-dimension-reduction-5"/></p>

</div>
<div id='tab-node-032-dimension-reduction-6'>
<pre><code class="r">dimension_reduction(res, k = 7, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-032-dimension-reduction-6-1.png" alt="plot of chunk tab-node-032-dimension-reduction-6"/></p>

</div>
<div id='tab-node-032-dimension-reduction-7'>
<pre><code class="r">dimension_reduction(res, k = 8, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-032-dimension-reduction-7-1.png" alt="plot of chunk tab-node-032-dimension-reduction-7"/></p>

</div>
</div>



Following heatmap shows how subgroups are split when increasing `k`:

```r
collect_classes(res)
```

![plot of chunk node-032-collect-classes](figure_cola/node-032-collect-classes-1.png)



If matrix rows can be associated to genes, consider to use `functional_enrichment(res,
...)` to perform function enrichment for the signature genes. See [this vignette](https://jokergoo.github.io/cola_vignettes/functional_enrichment.html) for more detailed explanations.


 

---------------------------------------------------




### Node033


Parent node: [Node03](#Node03).
Child nodes: 
                Node0111-leaf
        ,
                Node0112-leaf
        ,
                Node0131-leaf
        ,
                Node0132-leaf
        ,
                Node0141-leaf
        ,
                Node0142-leaf
        ,
                Node0211-leaf
        ,
                Node0212-leaf
        ,
                Node0213-leaf
        ,
                Node0221-leaf
        ,
                [Node0222](#Node0222)
        ,
                Node0231-leaf
        ,
                Node0232-leaf
        ,
                Node0233-leaf
        ,
                Node0321-leaf
        ,
                Node0322-leaf
        ,
                Node0323-leaf
        ,
                Node0324-leaf
        ,
                Node0325-leaf
        ,
                Node0331-leaf
        ,
                Node0332-leaf
        .







The object with results only for a single top-value method and a single partitioning method 
can be extracted as:

```r
res = res_rh["033"]
```

A summary of `res` and all the functions that can be applied to it:

```r
res
```

```
#> A 'ConsensusPartition' object with k = 2, 3, 4, 5, 6, 7, 8.
#>   On a matrix with 30000 rows and 12 columns.
#>   Top rows (1000) are extracted by 'ATC' method.
#>   Subgroups are detected by 'kmeans' method.
#>   Performed in total 350 partitions by row resampling.
#>   Best k for subgroups seems to be 2.
#> 
#> Following methods can be applied to this 'ConsensusPartition' object:
#>  [1] "cola_report"             "collect_classes"         "collect_plots"          
#>  [4] "collect_stats"           "colnames"                "compare_partitions"     
#>  [7] "compare_signatures"      "consensus_heatmap"       "dimension_reduction"    
#> [10] "functional_enrichment"   "get_anno_col"            "get_anno"               
#> [13] "get_classes"             "get_consensus"           "get_matrix"             
#> [16] "get_membership"          "get_param"               "get_signatures"         
#> [19] "get_stats"               "is_best_k"               "is_stable_k"            
#> [22] "membership_heatmap"      "ncol"                    "nrow"                   
#> [25] "plot_ecdf"               "predict_classes"         "rownames"               
#> [28] "select_partition_number" "show"                    "suggest_best_k"         
#> [31] "test_to_known_factors"   "top_rows_heatmap"
```

`collect_plots()` function collects all the plots made from `res` for all `k` (number of subgroups)
into one single page to provide an easy and fast comparison between different `k`.

```r
collect_plots(res)
```

![plot of chunk node-033-collect-plots](figure_cola/node-033-collect-plots-1.png)

The plots are:

- The first row: a plot of the eCDF (empirical cumulative distribution
  function) curves of the consensus matrix for each `k` and the heatmap of
  predicted classes for each `k`.
- The second row: heatmaps of the consensus matrix for each `k`.
- The third row: heatmaps of the membership matrix for each `k`.
- The fouth row: heatmaps of the signatures for each `k`.

All the plots in panels can be made by individual functions and they are
plotted later in this section.

`select_partition_number()` produces several plots showing different
statistics for choosing "optimized" `k`. There are following statistics:

- eCDF curves of the consensus matrix for each `k`;
- 1-PAC. [The PAC score](https://en.wikipedia.org/wiki/Consensus_clustering#Over-interpretation_potential_of_consensus_clustering)
  measures the proportion of the ambiguous subgrouping.
- Mean silhouette score.
- Concordance. The mean probability of fiting the consensus subgroup labels in all
  partitions.
- Area increased. Denote $A_k$ as the area under the eCDF curve for current
  `k`, the area increased is defined as $A_k - A_{k-1}$.
- Rand index. The percent of pairs of samples that are both in a same cluster
  or both are not in a same cluster in the partition of k and k-1.
- Jaccard index. The ratio of pairs of samples are both in a same cluster in
  the partition of k and k-1 and the pairs of samples are both in a same
  cluster in the partition k or k-1.

The detailed explanations of these statistics can be found in [the _cola_
vignette](https://jokergoo.github.io/cola_vignettes/cola.html#toc_13).

Generally speaking, higher 1-PAC score, higher mean silhouette score or higher
concordance corresponds to better partition. Rand index and Jaccard index
measure how similar the current partition is compared to partition with `k-1`.
If they are too similar, we won't accept `k` is better than `k-1`.

```r
select_partition_number(res)
```

![plot of chunk node-033-select-partition-number](figure_cola/node-033-select-partition-number-1.png)

The numeric values for all these statistics can be obtained by `get_stats()`.

```r
get_stats(res)
```

```
#>   k 1-PAC mean_silhouette concordance area_increased  Rand Jaccard
#> 2 2 1.000           1.000       1.000         0.5459 0.455   0.455
#> 3 3 0.742           0.822       0.830         0.1818 1.000   1.000
#> 4 4 0.667           0.477       0.793         0.1079 0.803   0.567
#> 5 5 0.606           0.559       0.738         0.0878 0.894   0.632
#> 6 6 0.712           0.531       0.840         0.0733 0.939   0.714
#> 7 7 0.742           0.492       0.840         0.0522 0.970   0.800
#> 8 8 0.818           0.486       0.840         0.0407 0.939   0.500
```

`suggest_best_k()` suggests the best $k$ based on these statistics. The rules are as follows:

- All $k$ with Jaccard index larger than 0.95 are removed because increasing
  $k$ does not provide enough extra information. If all $k$ are removed, it is
  marked as no subgroup is detected.
- For all $k$ with 1-PAC score larger than 0.9, the maximal $k$ is taken as
  the best $k$, and other $k$ are marked as optional $k$.
- If it does not fit the second rule. The $k$ with the maximal vote of the
  highest 1-PAC score, highest mean silhouette, and highest concordance is
  taken as the best $k$.

```r
suggest_best_k(res)
```

```
#> [1] 2
```


Following is the table of the partitions (You need to click the **show/hide
code output** link to see it). The membership matrix (columns with name `p*`)
is inferred by
[`clue::cl_consensus()`](https://www.rdocumentation.org/link/cl_consensus?package=clue)
function with the `SE` method. Basically the value in the membership matrix
represents the probability to belong to a certain group. The finall subgroup
label for an item is determined with the group with highest probability it
belongs to.

In `get_classes()` function, the entropy is calculated from the membership
matrix and the silhouette score is calculated from the consensus matrix.



<script>
$( function() {
	$( '#tabs-node-033-get-classes' ).tabs();
} );
</script>
<div id='tabs-node-033-get-classes'>
<ul>
<li><a href='#tab-node-033-get-classes-1'>k = 2</a></li>
<li><a href='#tab-node-033-get-classes-2'>k = 3</a></li>
<li><a href='#tab-node-033-get-classes-3'>k = 4</a></li>
<li><a href='#tab-node-033-get-classes-4'>k = 5</a></li>
<li><a href='#tab-node-033-get-classes-5'>k = 6</a></li>
<li><a href='#tab-node-033-get-classes-6'>k = 7</a></li>
<li><a href='#tab-node-033-get-classes-7'>k = 8</a></li>
</ul>

<div id='tab-node-033-get-classes-1'>
<p><a id='tab-node-033-get-classes-1-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 2), get_membership(res, k = 2))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette p1 p2
#&gt; TCGA.AB.2888.03     1       0          1  1  0
#&gt; TCGA.AB.2957.03     1       0          1  1  0
#&gt; TCGA.AB.2942.03     2       0          1  0  1
#&gt; TCGA.AB.2892.03     2       0          1  0  1
#&gt; TCGA.AB.2815.03     1       0          1  1  0
#&gt; TCGA.AB.2954.03     2       0          1  0  1
#&gt; TCGA.AB.2828.03     1       0          1  1  0
#&gt; TCGA.AB.2889.03     1       0          1  1  0
#&gt; TCGA.AB.2881.03     2       0          1  0  1
#&gt; TCGA.AB.2870.03     1       0          1  1  0
#&gt; TCGA.AB.2858.03     2       0          1  0  1
#&gt; TCGA.AB.2846.03     2       0          1  0  1
</code></pre>

<script>
$('#tab-node-033-get-classes-1-a').parent().next().next().hide();
$('#tab-node-033-get-classes-1-a').click(function(){
  $('#tab-node-033-get-classes-1-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-033-get-classes-2'>
<p><a id='tab-node-033-get-classes-2-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 3), get_membership(res, k = 3))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3
#&gt; TCGA.AB.2888.03     1   0.630      0.525 0.52 0.00 0.48
#&gt; TCGA.AB.2957.03     1   0.000      0.922 1.00 0.00 0.00
#&gt; TCGA.AB.2942.03     2   0.000      0.830 0.00 1.00 0.00
#&gt; TCGA.AB.2892.03     2   0.000      0.830 0.00 1.00 0.00
#&gt; TCGA.AB.2815.03     1   0.000      0.922 1.00 0.00 0.00
#&gt; TCGA.AB.2954.03     2   0.522      0.767 0.00 0.74 0.26
#&gt; TCGA.AB.2828.03     1   0.000      0.922 1.00 0.00 0.00
#&gt; TCGA.AB.2889.03     1   0.000      0.922 1.00 0.00 0.00
#&gt; TCGA.AB.2881.03     2   0.522      0.767 0.00 0.74 0.26
#&gt; TCGA.AB.2870.03     1   0.000      0.922 1.00 0.00 0.00
#&gt; TCGA.AB.2858.03     2   0.522      0.767 0.00 0.74 0.26
#&gt; TCGA.AB.2846.03     2   0.522      0.767 0.00 0.74 0.26
</code></pre>

<script>
$('#tab-node-033-get-classes-2-a').parent().next().next().hide();
$('#tab-node-033-get-classes-2-a').click(function(){
  $('#tab-node-033-get-classes-2-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-033-get-classes-3'>
<p><a id='tab-node-033-get-classes-3-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 4), get_membership(res, k = 4))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4
#&gt; TCGA.AB.2888.03     4  0.3975     0.0000 0.24 0.00 0.00 0.76
#&gt; TCGA.AB.2957.03     1  0.0707     0.8722 0.98 0.00 0.02 0.00
#&gt; TCGA.AB.2942.03     2  0.4948    -0.0261 0.00 0.56 0.44 0.00
#&gt; TCGA.AB.2892.03     2  0.4948    -0.0261 0.00 0.56 0.44 0.00
#&gt; TCGA.AB.2815.03     1  0.0707     0.8657 0.98 0.00 0.02 0.00
#&gt; TCGA.AB.2954.03     2  0.0000     0.4434 0.00 1.00 0.00 0.00
#&gt; TCGA.AB.2828.03     1  0.4624     0.4537 0.66 0.00 0.34 0.00
#&gt; TCGA.AB.2889.03     1  0.0707     0.8722 0.98 0.00 0.02 0.00
#&gt; TCGA.AB.2881.03     3  0.4713     0.4406 0.00 0.36 0.64 0.00
#&gt; TCGA.AB.2870.03     1  0.0000     0.8728 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2858.03     3  0.7768     0.5182 0.00 0.36 0.40 0.24
#&gt; TCGA.AB.2846.03     2  0.0000     0.4434 0.00 1.00 0.00 0.00
</code></pre>

<script>
$('#tab-node-033-get-classes-3-a').parent().next().next().hide();
$('#tab-node-033-get-classes-3-a').click(function(){
  $('#tab-node-033-get-classes-3-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-033-get-classes-4'>
<p><a id='tab-node-033-get-classes-4-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 5), get_membership(res, k = 5))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5
#&gt; TCGA.AB.2888.03     4   0.228      0.000 0.12 0.00 0.00 0.88 0.00
#&gt; TCGA.AB.2957.03     1   0.000      0.781 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2942.03     2   0.000      0.673 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2892.03     2   0.000      0.673 0.00 1.00 0.00 0.00 0.00
#&gt; TCGA.AB.2815.03     1   0.327      0.750 0.78 0.00 0.22 0.00 0.00
#&gt; TCGA.AB.2954.03     5   0.423      0.938 0.00 0.42 0.00 0.00 0.58
#&gt; TCGA.AB.2828.03     1   0.615      0.371 0.50 0.00 0.14 0.00 0.36
#&gt; TCGA.AB.2889.03     1   0.000      0.781 1.00 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2881.03     2   0.647      0.025 0.00 0.62 0.20 0.12 0.06
#&gt; TCGA.AB.2870.03     1   0.252      0.777 0.86 0.00 0.14 0.00 0.00
#&gt; TCGA.AB.2858.03     3   0.389      0.000 0.00 0.32 0.68 0.00 0.00
#&gt; TCGA.AB.2846.03     5   0.429      0.937 0.00 0.46 0.00 0.00 0.54
</code></pre>

<script>
$('#tab-node-033-get-classes-4-a').parent().next().next().hide();
$('#tab-node-033-get-classes-4-a').click(function(){
  $('#tab-node-033-get-classes-4-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-033-get-classes-5'>
<p><a id='tab-node-033-get-classes-5-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 6), get_membership(res, k = 6))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3   p4   p5   p6
#&gt; TCGA.AB.2888.03     4  0.0937      0.000 0.04 0.00 0.00 0.96 0.00 0.00
#&gt; TCGA.AB.2957.03     1  0.2581      0.821 0.86 0.12 0.02 0.00 0.00 0.00
#&gt; TCGA.AB.2942.03     2  0.3198      0.660 0.00 0.74 0.00 0.00 0.26 0.00
#&gt; TCGA.AB.2892.03     2  0.3076      0.664 0.00 0.76 0.00 0.00 0.24 0.00
#&gt; TCGA.AB.2815.03     1  0.2350      0.734 0.88 0.02 0.10 0.00 0.00 0.00
#&gt; TCGA.AB.2954.03     5  0.0547      0.863 0.00 0.00 0.00 0.02 0.98 0.00
#&gt; TCGA.AB.2828.03     6  0.3198      0.000 0.26 0.00 0.00 0.00 0.00 0.74
#&gt; TCGA.AB.2889.03     1  0.2581      0.821 0.86 0.12 0.02 0.00 0.00 0.00
#&gt; TCGA.AB.2881.03     2  0.6294      0.164 0.00 0.52 0.18 0.00 0.04 0.26
#&gt; TCGA.AB.2870.03     1  0.0937      0.796 0.96 0.04 0.00 0.00 0.00 0.00
#&gt; TCGA.AB.2858.03     3  0.2474      0.000 0.00 0.08 0.88 0.00 0.04 0.00
#&gt; TCGA.AB.2846.03     5  0.2094      0.856 0.00 0.08 0.00 0.02 0.90 0.00
</code></pre>

<script>
$('#tab-node-033-get-classes-5-a').parent().next().next().hide();
$('#tab-node-033-get-classes-5-a').click(function(){
  $('#tab-node-033-get-classes-5-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-033-get-classes-6'>
<p><a id='tab-node-033-get-classes-6-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 7), get_membership(res, k = 7))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3 p4   p5   p6   p7
#&gt; TCGA.AB.2888.03     4  0.0000      0.000 0.00 0.00 0.00  1 0.00 0.00 0.00
#&gt; TCGA.AB.2957.03     1  0.2906      0.685 0.80 0.18 0.00  0 0.00 0.02 0.00
#&gt; TCGA.AB.2942.03     2  0.5240      0.978 0.00 0.58 0.00  0 0.14 0.02 0.26
#&gt; TCGA.AB.2892.03     2  0.4789      0.978 0.00 0.60 0.00  0 0.14 0.00 0.26
#&gt; TCGA.AB.2815.03     1  0.4318      0.421 0.70 0.22 0.00  0 0.00 0.04 0.04
#&gt; TCGA.AB.2954.03     5  0.2259      0.776 0.00 0.00 0.00  0 0.84 0.16 0.00
#&gt; TCGA.AB.2828.03     6  0.2422      0.000 0.18 0.00 0.00  0 0.00 0.82 0.00
#&gt; TCGA.AB.2889.03     1  0.2906      0.685 0.80 0.18 0.00  0 0.00 0.02 0.00
#&gt; TCGA.AB.2881.03     7  0.1886      0.000 0.00 0.00 0.12  0 0.00 0.00 0.88
#&gt; TCGA.AB.2870.03     1  0.1928      0.624 0.90 0.00 0.02  0 0.00 0.00 0.08
#&gt; TCGA.AB.2858.03     3  0.0504      0.000 0.00 0.00 0.98  0 0.00 0.00 0.02
#&gt; TCGA.AB.2846.03     5  0.1433      0.761 0.00 0.08 0.00  0 0.92 0.00 0.00
</code></pre>

<script>
$('#tab-node-033-get-classes-6-a').parent().next().next().hide();
$('#tab-node-033-get-classes-6-a').click(function(){
  $('#tab-node-033-get-classes-6-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>

<div id='tab-node-033-get-classes-7'>
<p><a id='tab-node-033-get-classes-7-a' style='color:#0366d6' href='#'>show/hide code output</a></p>
<pre><code class="r">cbind(get_classes(res, k = 8), get_membership(res, k = 8))
</code></pre>

<pre><code>#&gt;                 class entropy silhouette   p1   p2   p3 p4   p5  p6   p7   p8
#&gt; TCGA.AB.2888.03     4  0.0000      0.000 0.00 0.00 0.00  1 0.00 0.0 0.00 0.00
#&gt; TCGA.AB.2957.03     1  0.3083      0.973 0.66 0.00 0.00  0 0.00 0.0 0.00 0.34
#&gt; TCGA.AB.2942.03     2  0.0000      0.837 0.00 1.00 0.00  0 0.00 0.0 0.00 0.00
#&gt; TCGA.AB.2892.03     2  0.2623      0.837 0.06 0.84 0.00  0 0.00 0.1 0.00 0.00
#&gt; TCGA.AB.2815.03     8  0.1947      0.558 0.00 0.00 0.00  0 0.00 0.0 0.14 0.86
#&gt; TCGA.AB.2954.03     5  0.0471      0.600 0.00 0.02 0.00  0 0.98 0.0 0.00 0.00
#&gt; TCGA.AB.2828.03     6  0.1563      0.000 0.00 0.00 0.00  0 0.00 0.9 0.00 0.10
#&gt; TCGA.AB.2889.03     1  0.3514      0.973 0.64 0.00 0.00  0 0.00 0.0 0.02 0.34
#&gt; TCGA.AB.2881.03     7  0.5257      0.000 0.28 0.14 0.04  0 0.00 0.0 0.54 0.00
#&gt; TCGA.AB.2870.03     8  0.2569      0.449 0.16 0.00 0.00  0 0.02 0.0 0.00 0.82
#&gt; TCGA.AB.2858.03     3  0.0000      0.000 0.00 0.00 1.00  0 0.00 0.0 0.00 0.00
#&gt; TCGA.AB.2846.03     5  0.4622      0.600 0.00 0.14 0.00  0 0.56 0.0 0.30 0.00
</code></pre>

<script>
$('#tab-node-033-get-classes-7-a').parent().next().next().hide();
$('#tab-node-033-get-classes-7-a').click(function(){
  $('#tab-node-033-get-classes-7-a').parent().next().next().toggle();
  return(false);
});
</script>
</div>
</div>

Heatmaps for the consensus matrix. It visualizes the probability of two
samples to be in a same group.




<script>
$( function() {
	$( '#tabs-node-033-consensus-heatmap' ).tabs();
} );
</script>
<div id='tabs-node-033-consensus-heatmap'>
<ul>
<li><a href='#tab-node-033-consensus-heatmap-1'>k = 2</a></li>
<li><a href='#tab-node-033-consensus-heatmap-2'>k = 3</a></li>
<li><a href='#tab-node-033-consensus-heatmap-3'>k = 4</a></li>
<li><a href='#tab-node-033-consensus-heatmap-4'>k = 5</a></li>
<li><a href='#tab-node-033-consensus-heatmap-5'>k = 6</a></li>
<li><a href='#tab-node-033-consensus-heatmap-6'>k = 7</a></li>
<li><a href='#tab-node-033-consensus-heatmap-7'>k = 8</a></li>
</ul>
<div id='tab-node-033-consensus-heatmap-1'>
<pre><code class="r">consensus_heatmap(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-033-consensus-heatmap-1-1.png" alt="plot of chunk tab-node-033-consensus-heatmap-1"/></p>

</div>
<div id='tab-node-033-consensus-heatmap-2'>
<pre><code class="r">consensus_heatmap(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-033-consensus-heatmap-2-1.png" alt="plot of chunk tab-node-033-consensus-heatmap-2"/></p>

</div>
<div id='tab-node-033-consensus-heatmap-3'>
<pre><code class="r">consensus_heatmap(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-033-consensus-heatmap-3-1.png" alt="plot of chunk tab-node-033-consensus-heatmap-3"/></p>

</div>
<div id='tab-node-033-consensus-heatmap-4'>
<pre><code class="r">consensus_heatmap(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-033-consensus-heatmap-4-1.png" alt="plot of chunk tab-node-033-consensus-heatmap-4"/></p>

</div>
<div id='tab-node-033-consensus-heatmap-5'>
<pre><code class="r">consensus_heatmap(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-033-consensus-heatmap-5-1.png" alt="plot of chunk tab-node-033-consensus-heatmap-5"/></p>

</div>
<div id='tab-node-033-consensus-heatmap-6'>
<pre><code class="r">consensus_heatmap(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-033-consensus-heatmap-6-1.png" alt="plot of chunk tab-node-033-consensus-heatmap-6"/></p>

</div>
<div id='tab-node-033-consensus-heatmap-7'>
<pre><code class="r">consensus_heatmap(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-033-consensus-heatmap-7-1.png" alt="plot of chunk tab-node-033-consensus-heatmap-7"/></p>

</div>
</div>

Heatmaps for the membership of samples in all partitions to see how consistent they are:





<script>
$( function() {
	$( '#tabs-node-033-membership-heatmap' ).tabs();
} );
</script>
<div id='tabs-node-033-membership-heatmap'>
<ul>
<li><a href='#tab-node-033-membership-heatmap-1'>k = 2</a></li>
<li><a href='#tab-node-033-membership-heatmap-2'>k = 3</a></li>
<li><a href='#tab-node-033-membership-heatmap-3'>k = 4</a></li>
<li><a href='#tab-node-033-membership-heatmap-4'>k = 5</a></li>
<li><a href='#tab-node-033-membership-heatmap-5'>k = 6</a></li>
<li><a href='#tab-node-033-membership-heatmap-6'>k = 7</a></li>
<li><a href='#tab-node-033-membership-heatmap-7'>k = 8</a></li>
</ul>
<div id='tab-node-033-membership-heatmap-1'>
<pre><code class="r">membership_heatmap(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-033-membership-heatmap-1-1.png" alt="plot of chunk tab-node-033-membership-heatmap-1"/></p>

</div>
<div id='tab-node-033-membership-heatmap-2'>
<pre><code class="r">membership_heatmap(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-033-membership-heatmap-2-1.png" alt="plot of chunk tab-node-033-membership-heatmap-2"/></p>

</div>
<div id='tab-node-033-membership-heatmap-3'>
<pre><code class="r">membership_heatmap(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-033-membership-heatmap-3-1.png" alt="plot of chunk tab-node-033-membership-heatmap-3"/></p>

</div>
<div id='tab-node-033-membership-heatmap-4'>
<pre><code class="r">membership_heatmap(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-033-membership-heatmap-4-1.png" alt="plot of chunk tab-node-033-membership-heatmap-4"/></p>

</div>
<div id='tab-node-033-membership-heatmap-5'>
<pre><code class="r">membership_heatmap(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-033-membership-heatmap-5-1.png" alt="plot of chunk tab-node-033-membership-heatmap-5"/></p>

</div>
<div id='tab-node-033-membership-heatmap-6'>
<pre><code class="r">membership_heatmap(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-033-membership-heatmap-6-1.png" alt="plot of chunk tab-node-033-membership-heatmap-6"/></p>

</div>
<div id='tab-node-033-membership-heatmap-7'>
<pre><code class="r">membership_heatmap(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-033-membership-heatmap-7-1.png" alt="plot of chunk tab-node-033-membership-heatmap-7"/></p>

</div>
</div>

As soon as the classes for columns are determined, the signatures
that are significantly different between subgroups can be looked for. 
Following are the heatmaps for signatures.






<script>
$( function() {
	$( '#tabs-node-033-get-signatures' ).tabs();
} );
</script>
<div id='tabs-node-033-get-signatures'>
<ul>
<li><a href='#tab-node-033-get-signatures-1'>k = 2</a></li>
<li><a href='#tab-node-033-get-signatures-2'>k = 3</a></li>
<li><a href='#tab-node-033-get-signatures-3'>k = 4</a></li>
<li><a href='#tab-node-033-get-signatures-4'>k = 5</a></li>
<li><a href='#tab-node-033-get-signatures-5'>k = 6</a></li>
<li><a href='#tab-node-033-get-signatures-6'>k = 7</a></li>
<li><a href='#tab-node-033-get-signatures-7'>k = 8</a></li>
</ul>
<div id='tab-node-033-get-signatures-1'>
<pre><code class="r">get_signatures(res, k = 2)
</code></pre>

<p><img src="figure_cola/tab-node-033-get-signatures-1-1.png" alt="plot of chunk tab-node-033-get-signatures-1"/></p>

</div>
<div id='tab-node-033-get-signatures-2'>
<pre><code class="r">get_signatures(res, k = 3)
</code></pre>

<p><img src="figure_cola/tab-node-033-get-signatures-2-1.png" alt="plot of chunk tab-node-033-get-signatures-2"/></p>

</div>
<div id='tab-node-033-get-signatures-3'>
<pre><code class="r">get_signatures(res, k = 4)
</code></pre>

<p><img src="figure_cola/tab-node-033-get-signatures-3-1.png" alt="plot of chunk tab-node-033-get-signatures-3"/></p>

</div>
<div id='tab-node-033-get-signatures-4'>
<pre><code class="r">get_signatures(res, k = 5)
</code></pre>

<p><img src="figure_cola/tab-node-033-get-signatures-4-1.png" alt="plot of chunk tab-node-033-get-signatures-4"/></p>

</div>
<div id='tab-node-033-get-signatures-5'>
<pre><code class="r">get_signatures(res, k = 6)
</code></pre>

<p><img src="figure_cola/tab-node-033-get-signatures-5-1.png" alt="plot of chunk tab-node-033-get-signatures-5"/></p>

</div>
<div id='tab-node-033-get-signatures-6'>
<pre><code class="r">get_signatures(res, k = 7)
</code></pre>

<p><img src="figure_cola/tab-node-033-get-signatures-6-1.png" alt="plot of chunk tab-node-033-get-signatures-6"/></p>

</div>
<div id='tab-node-033-get-signatures-7'>
<pre><code class="r">get_signatures(res, k = 8)
</code></pre>

<p><img src="figure_cola/tab-node-033-get-signatures-7-1.png" alt="plot of chunk tab-node-033-get-signatures-7"/></p>

</div>
</div>



Compare the overlap of signatures from different k:

```r
compare_signatures(res)
```

![plot of chunk node-033-signature_compare](figure_cola/node-033-signature_compare-1.png)

`get_signature()` returns a data frame invisibly. To get the list of signatures, the function
call should be assigned to a variable explicitly. In following code, if `plot` argument is set
to `FALSE`, no heatmap is plotted while only the differential analysis is performed.

```r
# code only for demonstration
tb = get_signature(res, k = ..., plot = FALSE)
```

An example of the output of `tb` is:

```
#>   which_row         fdr    mean_1    mean_2 scaled_mean_1 scaled_mean_2 km
#> 1        38 0.042760348  8.373488  9.131774    -0.5533452     0.5164555  1
#> 2        40 0.018707592  7.106213  8.469186    -0.6173731     0.5762149  1
#> 3        55 0.019134737 10.221463 11.207825    -0.6159697     0.5749050  1
#> 4        59 0.006059896  5.921854  7.869574    -0.6899429     0.6439467  1
#> 5        60 0.018055526  8.928898 10.211722    -0.6204761     0.5791110  1
#> 6        98 0.009384629 15.714769 14.887706     0.6635654    -0.6193277  2
...
```

The columns in `tb` are:

1. `which_row`: row indices corresponding to the input matrix.
2. `fdr`: FDR for the differential test. 
3. `mean_x`: The mean value in group x.
4. `scaled_mean_x`: The mean value in group x after rows are scaled.
5. `km`: Row groups if k-means clustering is applied to rows (which is done by automatically selecting number of clusters).

If there are too many signatures, `top_signatures = ...` can be set to only show the 
signatures with the highest FDRs:

```r
# code only for demonstration
# e.g. to show the top 500 most significant rows
tb = get_signature(res, k = ..., top_signatures = 500)
```

If the signatures are defined as these which are uniquely high in current group, `diff_method` argument
can be set to `"uniquely_high_in_one_group"`:

```r
# code only for demonstration
tb = get_signature(res, k = ..., diff_method = "uniquely_high_in_one_group")
```




UMAP plot which shows how samples are separated.


<script>
$( function() {
	$( '#tabs-node-033-dimension-reduction' ).tabs();
} );
</script>
<div id='tabs-node-033-dimension-reduction'>
<ul>
<li><a href='#tab-node-033-dimension-reduction-1'>k = 2</a></li>
<li><a href='#tab-node-033-dimension-reduction-2'>k = 3</a></li>
<li><a href='#tab-node-033-dimension-reduction-3'>k = 4</a></li>
<li><a href='#tab-node-033-dimension-reduction-4'>k = 5</a></li>
<li><a href='#tab-node-033-dimension-reduction-5'>k = 6</a></li>
<li><a href='#tab-node-033-dimension-reduction-6'>k = 7</a></li>
<li><a href='#tab-node-033-dimension-reduction-7'>k = 8</a></li>
</ul>
<div id='tab-node-033-dimension-reduction-1'>
<pre><code class="r">dimension_reduction(res, k = 2, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-033-dimension-reduction-1-1.png" alt="plot of chunk tab-node-033-dimension-reduction-1"/></p>

</div>
<div id='tab-node-033-dimension-reduction-2'>
<pre><code class="r">dimension_reduction(res, k = 3, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-033-dimension-reduction-2-1.png" alt="plot of chunk tab-node-033-dimension-reduction-2"/></p>

</div>
<div id='tab-node-033-dimension-reduction-3'>
<pre><code class="r">dimension_reduction(res, k = 4, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-033-dimension-reduction-3-1.png" alt="plot of chunk tab-node-033-dimension-reduction-3"/></p>

</div>
<div id='tab-node-033-dimension-reduction-4'>
<pre><code class="r">dimension_reduction(res, k = 5, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-033-dimension-reduction-4-1.png" alt="plot of chunk tab-node-033-dimension-reduction-4"/></p>

</div>
<div id='tab-node-033-dimension-reduction-5'>
<pre><code class="r">dimension_reduction(res, k = 6, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-033-dimension-reduction-5-1.png" alt="plot of chunk tab-node-033-dimension-reduction-5"/></p>

</div>
<div id='tab-node-033-dimension-reduction-6'>
<pre><code class="r">dimension_reduction(res, k = 7, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-033-dimension-reduction-6-1.png" alt="plot of chunk tab-node-033-dimension-reduction-6"/></p>

</div>
<div id='tab-node-033-dimension-reduction-7'>
<pre><code class="r">dimension_reduction(res, k = 8, method = &quot;UMAP&quot;)
</code></pre>

<p><img src="figure_cola/tab-node-033-dimension-reduction-7-1.png" alt="plot of chunk tab-node-033-dimension-reduction-7"/></p>

</div>
</div>



Following heatmap shows how subgroups are split when increasing `k`:

```r
collect_classes(res)
```

![plot of chunk node-033-collect-classes](figure_cola/node-033-collect-classes-1.png)



If matrix rows can be associated to genes, consider to use `functional_enrichment(res,
...)` to perform function enrichment for the signature genes. See [this vignette](https://jokergoo.github.io/cola_vignettes/functional_enrichment.html) for more detailed explanations.


 

## Session info


```r
sessionInfo()
```

```
#> R version 4.1.0 (2021-05-18)
#> Platform: x86_64-pc-linux-gnu (64-bit)
#> Running under: CentOS Linux 7 (Core)
#> 
#> Matrix products: default
#> BLAS/LAPACK: /usr/lib64/libopenblas-r0.3.3.so
#> 
#> locale:
#>  [1] LC_CTYPE=en_US.UTF-8       LC_NUMERIC=C               LC_TIME=en_US.UTF-8       
#>  [4] LC_COLLATE=en_US.UTF-8     LC_MONETARY=en_US.UTF-8    LC_MESSAGES=en_US.UTF-8   
#>  [7] LC_PAPER=en_US.UTF-8       LC_NAME=C                  LC_ADDRESS=C              
#> [10] LC_TELEPHONE=C             LC_MEASUREMENT=en_US.UTF-8 LC_IDENTIFICATION=C       
#> 
#> attached base packages:
#> [1] grid      stats     graphics  grDevices utils     datasets  methods   base     
#> 
#> other attached packages:
#> [1] genefilter_1.74.0    ComplexHeatmap_2.8.0 markdown_1.1         knitr_1.33          
#> [5] matrixStats_0.59.0   cola_1.9.4          
#> 
#> loaded via a namespace (and not attached):
#>   [1] bitops_1.0-7           bit64_4.0.5            doParallel_1.0.16      RColorBrewer_1.1-2    
#>   [5] httr_1.4.2             GenomeInfoDb_1.28.1    data.tree_1.0.0        tools_4.1.0           
#>   [9] utf8_1.2.1             R6_2.5.0               irlba_2.3.3            DBI_1.1.1             
#>  [13] BiocGenerics_0.38.0    colorspace_2.0-2       GetoptLong_1.0.5       gridExtra_2.3         
#>  [17] tidyselect_1.1.1       bit_4.0.4              compiler_4.1.0         Biobase_2.52.0        
#>  [21] Cairo_1.5-12.2         xml2_1.3.2             microbenchmark_1.4-7   slam_0.1-48           
#>  [25] scales_1.1.1           askpass_1.1            stringr_1.4.0          digest_0.6.27         
#>  [29] XVector_0.32.0         pkgconfig_2.0.3        umap_0.2.7.0           fastmap_1.1.0         
#>  [33] highr_0.9              rlang_0.4.11           GlobalOptions_0.1.2    rstudioapi_0.13       
#>  [37] RSQLite_2.2.7          impute_1.66.0          generics_0.1.0         shape_1.4.6           
#>  [41] jsonlite_1.7.2         mclust_5.4.7           dplyr_1.0.7            dendextend_1.15.1     
#>  [45] RCurl_1.98-1.3         magrittr_2.0.1         GenomeInfoDbData_1.2.6 Matrix_1.3-4          
#>  [49] fansi_0.5.0            Rcpp_1.0.7             munsell_0.5.0          S4Vectors_0.30.0      
#>  [53] viridis_0.6.1          reticulate_1.20        lifecycle_1.0.0        scatterplot3d_0.3-41  
#>  [57] stringi_1.7.3          zlibbioc_1.38.0        blob_1.2.1             parallel_4.1.0        
#>  [61] crayon_1.4.1           lattice_0.20-44        Biostrings_2.60.1      splines_4.1.0         
#>  [65] annotate_1.70.0        circlize_0.4.13        KEGGREST_1.32.0        polylabelr_0.2.0      
#>  [69] pillar_1.6.1           rjson_0.2.20           codetools_0.2-18       stats4_4.1.0          
#>  [73] XML_3.99-0.6           glue_1.4.2             evaluate_0.14          png_0.1-7             
#>  [77] vctrs_0.3.8            foreach_1.5.1          polyclip_1.10-0        purrr_0.3.4           
#>  [81] gtable_0.3.0           openssl_1.4.4          assertthat_0.2.1       clue_0.3-59           
#>  [85] cachem_1.0.5           ggplot2_3.3.5          xfun_0.24              eulerr_6.1.0          
#>  [89] xtable_1.8-4           skmeans_0.2-13         RSpectra_0.16-0        viridisLite_0.4.0     
#>  [93] survival_3.2-11        tibble_3.1.2           Polychrome_1.3.1       iterators_1.0.13      
#>  [97] AnnotationDbi_1.54.1   memoise_2.0.0          IRanges_2.26.0         cluster_2.1.2         
#> [101] ellipsis_0.3.2         brew_1.0-6
```




