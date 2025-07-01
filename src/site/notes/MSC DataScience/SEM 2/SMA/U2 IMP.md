---
{"dg-publish":true,"permalink":"/MSC DataScience/SEM 2/SMA/U2 IMP/","created":"2025-07-01T21:08:38.783+05:30"}
---


## **Unit 2: Social Network Structure & Analysis**

### **1. Basics of Social Network**

- **Social Network**: A structure showing how individuals (nodes) are connected (edges).
    
- **Example**: Class of 25 students → each student = node; friendships = edges.
    

#### **Key Components**:

- **Nodes (Vertices)**: People, organizations, websites, etc. Properties include age, gender, interests, etc.
    
- **Edges (Links/Ties)**:
    
    - **Undirected**: Mutual (e.g., Facebook friends).
        
    - **Directed**: One-way (e.g., Twitter follow).
        
    - **Weighted**: Shows intensity (e.g., frequency of messages).
        

#### **Ties**:

|Aspect|Strong Ties|Weak Ties|
|---|---|---|
|Examples|Close friends|Acquaintances|
|Contact|Frequent|Occasional|
|Support|High|Low|
|Info Shared|Similar|New/diverse|
|Jobs|Limited|Broader scope|

---

### **2. Network Measures**

#### **Degree**:

- Number of connections per person.
    
- **Average Degree** = Total connections / Total people.
    

#### **Density**:

- Measures how connected the group is.
    
- **Formula**: Density = Actual connections / Max possible connections.
    
- **Range**: 0 (none) to 1 (fully connected).
    

#### **Density Levels**:

|Level|Range|Characteristics|Examples|
|---|---|---|---|
|Very Low|0.0 - 0.2|Sparse|Twitter networks|
|Medium|0.4 - 0.6|Moderate|Friend circles|
|Very High|0.8 - 1.0|Almost all connected|Wedding parties|

#### **Centrality Measures**:

|Measure|What it shows|Example|
|---|---|---|
|Degree|Most connected|Popular student|
|Betweenness|Bridge between groups|Knows nerds and athletes|
|Closeness|Reach everyone fast|Gossip center|
|Eigenvector|Knows influential people|Assistant to CEO|

---

### **3. Network Visualization**

#### **Layouts**:

|Layout|Description|Best for|
|---|---|---|
|Spring|Nodes pull/push like springs|Revealing clusters|
|Circular|Arranged in a circle|Small groups|
|Hierarchical|Top-down|Company structure|
|Grid|Rows/columns|Easy comparison|

#### **Big Network Issues**:

- Visualizing thousands of connections → becomes messy ("hairball").
    
- **Solution**: Filter by community or interaction level.
    

---

### **4. Correlations in Networks**

#### **Triangles**:

- Three people all connected to each other.
    
- Shows **strong group cohesion**.
    

#### **Clustering Coefficient**:

- % of your friends who are also friends with each other.
    
- **Formula**: Actual triangles / Possible triangles.
    

#### **Assortativity**:

- Measures similarity in connections.
    
- Range: -1 (opposites) to +1 (similar).
    

|Type|Meaning|Examples|
|---|---|---|
|Positive|Similar people connect|Same profession|
|Negative|Different people connect|Mentor-mentee|

---

### **5. Social Media Network Analytics**

#### **Terms**:

- **Community**: Group with more internal links.
    
- **Bridge**: Connects different communities.
    
- **Hub**: Highly connected node (e.g., influencer).
    
- **Reciprocity**: Two-way connection (e.g., Facebook = 100%, Twitter = ~20%).
    

#### **Platform Comparison**:

|Platform|Type|Clustering|Purpose|Reciprocity|
|---|---|---|---|---|
|Facebook|Undirected|High|Social|100%|
|Twitter|Directed|Low|Info|20–30%|
|LinkedIn|Undirected|Medium|Professional|100%|
|Instagram|Directed|Medium|Content|30–50%|

#### **Tools for Analysis**:

|Tool|Type|Use|
|---|---|---|
|Gephi|Visual platform|Easy graphs|
|NetworkX|Python lib|Coding-based|
|Cytoscape|Desktop app|Complex networks|
|R igraph|R library|Stats modeling|
|NodeXL|Excel Add-on|Easy for beginners|
|D3.js|JS library|Interactive visualizations|

#### **Network Structures**:

|Type|Description|Examples|
|---|---|---|
|Random|Random links|Early internet|
|Small-World|High clustering + shortcuts|Social networks|
|Scale-Free|Popular nodes get more links|Web, social media|
|Hierarchical|Clear levels|Military, corporate|
