# Cryptocurrencies


### Purpose

The purpose of this analysis was to find other cryptocurrencies that may be of
interest for potential future investment. Utilizing unsupervised machine
learning models, we found out which factors led to the potential for excellent
performance.


### Methodology

We first had to clean the dataset to make it usable in unsupervised machine
learning. We filtered out the cryptocurrencies that were not trading from our
dataset. We had to find any algorithms that were undefined, to which there
were none. Then, we dropped the IsTrading column and all rows with N/As.
Finally, we removed the cryptocurrencies with no coins mined.

Next, before we remove the names of the cryptocurrencies from our data, saved
them in their own dataframe. Since ProofType and Algorithm are string type
data, we used the pandas get dummies method to generage numeric data for use
in our model.

The next step in the process was to scale the data so that no feature would
artificially skew our model. We utilized Scikit Learn's Standard Scaler for
this. The final step in the pre-processing was to reduce the dimensionality of
our data using Principal Component Analysis (PCA).

For our clustering model, we selected the K Means model. To find out the
appropriate number of clusters, we created an elbow curve using the k and
inertia values. Based on the elbow curve, four clusters appeared to be the
best k value to go with. We then ran the K Means model to first fit the data,
then to create the labels. We then created a dataframe combining the name
dataframe, along with our labels. We then visualized the principal components
in a 3d model using Plotly and a 2d scatterplot using HvPlot. For the 2D plot,
we used logs to get a better representation of the data.


### Analysis

While looking at the clusters, one cluster (class 2) had only one data point,
which was the Bit Torrent cryptocurrency. This particular cryptocurrency had a
high TotalCoinsMined and TotalCoinSupply. This would make this the next
cryptocurrency to consider for the future. There were a few others that were
almost as high in TotalCoinSupply but had a much smaller TotalCoinsMined
value. These belong to class 0, and may be other coins to consider.
