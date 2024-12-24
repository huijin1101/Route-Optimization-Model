
[View Notebook on nbviewer](https://nbviewer.org/github/huijin1101/Route-Optimization-Model/blob/main/workbook/Chicago_Route_Optimization-completecode_clean.ipynb#1.1-Data-preparation-and-OSMnx-graph-creation)
# Table of Contents

Click on the links below to navigate to specific sections via **nbviewer**:

- [Chapter 1: Match Real Trip Routes with Calculated Shortest Routes from OSMnx](https://nbviewer.org/github/huijin1101/Route-Optimization-Model/blob/main/workbook/Chicago_Route_Optimization-completecode_clean.ipynb#Chapter-1-Match-Real-Trip-Routes-with-Calculated-Shortest-Routes-from-OSMnx)
  - [1.1 Data preparation and OSMnx graph creation](https://nbviewer.org/github/huijin1101/Route-Optimization-Model/blob/main/workbook/Chicago_Route_Optimization-completecode_clean.ipynb#1.1-Data-preparation-and-OSMnx-graph-creation)
  - [1.2 Match the end points of each trip with the nodes from the OSMnx graph and calculate the shortest route with the obtained nodes](https://nbviewer.org/github/huijin1101/Route-Optimization-Model/blob/main/workbook/Chicago_Route_Optimization-completecode_clean.ipynb#1.2-Match-the-end-points-of-each-trip-with-the-nodes-from-the-OSMnx-graph-and-calculate-the-shortest-route-with-the-obtained-nodes)
  - [1.3 Filter trips based on the match result](https://nbviewer.org/github/huijin1101/Route-Optimization-Model/blob/main/workbook/Chicago_Route_Optimization-completecode_clean.ipynb#1.3-Filter-trips-based-on-the-match-result)
    - [1.3.1 Filter trips by the point-to-nearest-node distance](https://nbviewer.org/github/huijin1101/Route-Optimization-Model/blob/main/workbook/Chicago_Route_Optimization-completecode_clean.ipynb#1.3.1-Filter-trips-by-the-point-to-nearest-node-distance)
    - [1.3.2 Filter trips by the absolute difference between the real trip miles and the calculated shortest route length](https://nbviewer.org/github/huijin1101/Route-Optimization-Model/blob/main/workbook/Chicago_Route_Optimization-completecode_clean.ipynb#1.3.2-Filter-trips-by-the-absolute-difference-between-the-real-trip-miles-and-the-calculated-shortest-route-length)
      - [1.3.2.1 Compare the trip features before and after filtering with different thresholds](https://nbviewer.org/github/huijin1101/Route-Optimization-Model/blob/main/workbook/Chicago_Route_Optimization-completecode_clean.ipynb#1.3.2.1-compare-the-trip-features-before-and-after-filter-with-different-thresholds)
      - [1.3.2.2 Compare the temporal traffic pattern before and after filtering with the 500m threshold](https://nbviewer.org/github/huijin1101/Route-Optimization-Model/blob/main/workbook/Chicago_Route_Optimization-completecode_clean.ipynb#1.3.2.2-compare-the-temporal-traffic-pattern-before-and-after-filter-with-the-500m-threshold)

- [Chapter 2: Create Segment-Level Dataset](https://nbviewer.org/github/huijin1101/Route-Optimization-Model/blob/main/workbook/Chicago_Route_Optimization-completecode_clean.ipynb#Chapter-2-Create-Segment-Level-Dataset)
  - [2.1 Cluster all road segments of Chicago into regions](https://nbviewer.org/github/huijin1101/Route-Optimization-Model/blob/main/workbook/Chicago_Route_Optimization-completecode_clean.ipynb#2.1-Cluster-all-road-segments-of-Chicago-into-regions)
  - [2.2 Extract the road segments details from G](https://nbviewer.org/github/huijin1101/Route-Optimization-Model/blob/main/workbook/Chicago_Route_Optimization-completecode_clean.ipynb#2.2-Extract-the-road-segments-details-from-G)
  - [2.3 Display the road segments in our dataset on OSMnx graph and check their coverage ratio in each region](https://nbviewer.org/github/huijin1101/Route-Optimization-Model/blob/main/workbook/Chicago_Route_Optimization-completecode_clean.ipynb#2.3-Display-the-road-segments-in-our-dataset-on-OSMnx-graph-and-check-their-coverage-ratio-in-each-region)
  - [2.4 Complete the segment-level traffic information](https://nbviewer.org/github/huijin1101/Route-Optimization-Model/blob/main/workbook/Chicago_Route_Optimization-completecode_clean.ipynb#2.4-Complete-the-segment-level-traffic-information)

- [Chapter 3: Check the Temporal Traffic Pattern Completeness for Each Region](https://nbviewer.org/github/huijin1101/Route-Optimization-Model/blob/main/workbook/Chicago_Route_Optimization-completecode_clean.ipynb#Chapter-3-Check-the-Temporal-Traffic-Pattern-Completeness-for-Each-Region)

- [Chapter 4: Road Segments Clustering within Each Region](https://nbviewer.org/github/huijin1101/Route-Optimization-Model/blob/main/workbook/Chicago_Route_Optimization-completecode_clean.ipynb#Chapter-4-Road-Segments-Clustering-within-Each-Region)
  - [4.1 Data preparation for KMeans clustering](https://nbviewer.org/github/huijin1101/Route-Optimization-Model/blob/main/workbook/Chicago_Route_Optimization-completecode_clean.ipynb#4.1-Data-preparation-for-KMeans-clustering)
  - [4.2 Use elbow method to determine K for each region](https://nbviewer.org/github/huijin1101/Route-Optimization-Model/blob/main/workbook/Chicago_Route_Optimization-completecode_clean.ipynb#4.2-Use-elbow-method-to-determine-K-for-each-region)

- [Chapter 5: Build ML Models for Predicting the Travel Time for Each Road Segment Cluster](https://nbviewer.org/github/huijin1101/Route-Optimization-Model/blob/main/workbook/Chicago_Route_Optimization-completecode_clean.ipynb#Chapter-5--Build-ML-models-for-predicting-the--travel-time-for-each-road-segment-cluster)
  - [5.1 Check the clustering accuracy by plotting the inferred travel time histogram for each cluster](https://nbviewer.org/github/huijin1101/Route-Optimization-Model/blob/main/workbook/Chicago_Route_Optimization-completecode_clean.ipynb#5.1-Check-the-clustering-accuracy-by-plotting-the-inferred-travel-time-histogram-for-each-cluster)
  - [5.2 EDA for feature engineering](https://nbviewer.org/github/huijin1101/Route-Optimization-Model/blob/main/workbook/Chicago_Route_Optimization-completecode_clean.ipynb#5.2-EDA-for-feature-engineering)
