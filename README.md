# simpleDP
Simple binary and decimal implementations of a **Differential Privacy** algorithm.

Differential Privacy (DP) is a system for publicly sharing information about a dataset by describing the patterns of groups within the dataset while withholding information about individuals in the dataset.

The idea behind Differential privacy is that if the effect of making an arbitrary single substitution in the database is small enough, the query result cannot be used to infer much about any single individual, and therefore provides privacy.

With this approach, the edited dataset can be used for statistical/training purposes.

Furthermore, adding a new information to the dataset and applying the Differential Privacy algorithm allows not to reveal its value has shown in the following plots.

## Results:

- Binary implementation (*dp-binary.ipynb*):

    >**Stats of the original dataset:**\
    >![](plots/binary/noDP.png)

    >**After adding one bit with value 1:**\
    >![](plots/binary/noDP+1.png)\
    >**The new bit is identifiable**

    >**Stats after DP algorithm**\
    >![](plots/binary/DP.png)

    >**Stats after adding one bit and after DP algorithm**\
    >![](plots/binary/DP+1.png)\
    >**The new bit is not identifiable**

- Decimal implementation (*dp-decimal.ipynb*):

    >**Stats of the original dataset:**\
    >![](plots/decimal/noDP.png)

    >**After adding one bit with value 1:**\
    >![](plots/decimal/noDP+1.png)\
    >**The new bit is identifiable**

    >**Stats after DP algorithm**\
    >![](plots/decimal/DP.png)

    >**Stats after adding one bit and after DP algorithm**\
    >![](plots/decimal/DP+1.png)\
    >**The new bit is not identifiable**

## PRNG vs TRNG
> TRNG bits and implementation cannot be published, so it is not in the actual code

||0|1|2|3|4|5|&|7|8|9|
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
|NoDP|10000|10000|10000|10000|10000|10000|10000|10000|10000|10000|
|NoDP+1|10000|10001|10000|10000|10000|10000|10000|10000|10000|10000|
|DP_PRNG|10013|9986|9876|9969|10043|9961|10081|9936|10130|10006|
|DP+1_PRNG|10095|9917|9911|9934|10076|9991|10093|10109|9997|9879|
|DP_TRNG|10056|10059|10021|9992|9993|9898|9928|9988|10035|10030|
|DP+1_TRNG|9940|9954|9969|10019|10057|10100|10068|10097|9883|9913|


## DP Algorithm
![](DP-algorithm-scheme.png)
