# Route Optimization Model for Fleet Management

Efficient route optimization is critical for applications like fleet management and logistics, where reducing travel time and fuel consumption can significantly improve operational efficiency. However, leveraging real-time traffic data is challenging due to its complexity and lack of availability at the segment level. This project proposes solutions to bridge this gap.

---

## Technologies
- **Python**
- **Scikit-learn**: Machine learning library for clustering.
- **Prophet**: Time-series forecasting for traffic data patterns.
- **XGBoost**: Gradient boosting for travel time prediction.
- **OSMnx**: Graph-based geographic analysis.
- **NetworkX**: Graph manipulation and shortest-path algorithms.

---

## Problem Description

In route optimization, the challenge lies in using traffic data to calculate the optimal route between two nodes. For example, as shown below, given a pair of nodes **A** and **B**, three available routes exist (blue, yellow, and green), each consisting of several road segments (S1 to S9). If real-time traffic information (e.g., travel time) is available for each segment, the shortest route in terms of total travel time can be computed efficiently, which is the yellow route here.

![Route Optimization Problem Description](images/route_opt_des.png)

However, **traffic data is often available at the trip level**, containing information such as:
- Total trip distance
- Trip duration
- Start and end timestamps

This makes segment-level optimization challenging. To address this, I proposed a two-step solution:
1. **Convert trip-level traffic data to segment-level traffic information**: By mapping trip data to individual road segments, I enabled segment-level travel time prediction and route optimization.
2. **Cluster road segments with similar properties**: Using clustering techniques, road segments were grouped based on geographical proximity, traffic patterns and scales. This reduced the complexity of predicting travel time at the individual segment level and addressed issues with incomplete data.

---

## Methodology

![Approach](images/route_opt_metho.png)
---

## Contributions

The main contributions of this work are:
1. **Trip-to-Segment Conversion**:
   - Matched real trips from the original dataset with calculated shortest routes from OSMnx:
     - Matched the endpoints of each real trip with nodes in the OSMnx graph.
     - Calculated the shortest route using the identified nodes.
   - Filtered trips based on the matching results:
     - Retained trips with a strong match between their endpoints and the nearest OSMnx nodes.
     - Kept trips with a close match between their real trip distances and calculated shortest route lengths.
   - Distributed trip travel times to road segments using proportional weighting based on the free-flow travel time of each segment.
   - Extracted road segment details from the OSMnx graph.
   - Converted trip-level traffic data to segment-level traffic data.
   
2. **Cluster-Level Prediction**:
   - Clustered road segments with similar characteristics (location, travel patterns, and scales) using KMeans.
   - Performed cluster-level travel time predictions using Prophet and XGBoost.
   - Merged cluster-level prediction results into the segment-level traffic data for real-time route optimization.

---

## Results

### Comparing Route Optimization with Predicted and Actual Travel Times
To evaluate the performance of the model, the following experiment was conducted:
- **Timestamp Selected**: 2024-03-04 08:00:00.
- **Test Data**: 
  - 1000 pairs of nodes were randomly generated.
  - Each trip had a mean duration of approximately 15 minutes.
  - Each pair had multiple route options to select from.

#### Key Metrics for Comparison:
1. **Absolute percentage time difference between the predicted path and the actual fastest path**:
   abs(predicted fastest path travel time-actual fastest path travel time)/actual fastest path travel time
   
2. **Absolute percentage error between the predicted travel time and the actual inferred travel time**:
   abs(predicted travel time-actual travel time)/actual travel time
3. **Absolute time difference in second between the predicted path and the actual fastest path**:
   abs(predicted fastest path travel time-actual fastest path travel time)

4. **Absolute time difference in second between the predicted travel time and the actual inferred travel time**:
   abs(predicted travel time –actual travel time)

![Route Optimization Results Comparison](images/route_opt_res.png)

---

### Visualizing Route Optimization
The following map demonstrates the optimization process for a selected pair of nodes:
- **Nodes Displayed**: Start node and end node.
- **Routes Visualized**: Predicted fastest route and the actual fastest route.

![Route Optimization Results on Map](images/route_opt_demo.png)

---

## Conclusion

This project demonstrates how trip-level traffic data can be converted to segment-level data to enable real-time route optimization. By clustering road segments and performing cluster-level predictions, the approach balances scalability and accuracy. 

### Key Findings:
- The model achieved **100% accuracy** in recommending the fastest route for the 1000 test cases.
- The **average error** in predicting trip duration was approximately **10%**.

### Future Work:
1. Incorporate dynamic, real-time traffic data feeds for enhanced adaptability.
2. Explore alternative clustering and prediction methods to further optimize performance.
3. Extend the approach to larger, more diverse datasets to validate scalability.

---





