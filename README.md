# DepLabData

Data from Noah Dephoure's lab at Weill Cornell Medical College

[![](https://travis-ci.org/julia-wrobel/depthTests.svg?branch=master)](https://travis-ci.org/julia-wrobel/DepLabData)

---------------

### Installation

To install the latest version directly from Github, please use:
<pre><code>install.packages("devtools")
devtools::install_github("julia-wrobel/DepLabData")
</code></pre>



### Help file

To see what datasets are available in the package, please use:
<pre><code>
library(help = "DepLabData")
</code></pre>

### Go from wide to long format

```
# load the data in wide format --> every row corresponds to one protein, but the columns contain
# values for at least 7 variables (x 30 fractions)
data(WT_trial1)

# extract protein IDs
ids <- extract_proteinID(WT_trial1$Protein.IDs, routine = "human")

# extract only values from "raw.intensity" columns
# and return a long data.frame
WT1_raw.intensity <- MQ_to_longFormat(WT_trial1, y= "raw.intensity", return.dt = TRUE, ids)
```
