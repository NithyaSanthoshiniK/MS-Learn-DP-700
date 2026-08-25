# Course: DP-700T00-A: Implement Data Engineering Solutions using Microsoft Fabric

## Module: Implement Dataflows Gen2 in Microsoft Fabric
### Submodule: Explore Dataflows Gen2 in Microsoft Fabric

This module explores the authoring environment of **Dataflows Gen2** in Microsoft Fabric, focusing on the Data Factory workload experience, interface components, and supported data destinations.

---

### 1. Where to Create Dataflows Gen2
In Microsoft Fabric, you can create a Dataflow Gen2 from multiple entry points:
* The **Data Factory** workload (primary experience for data ingestion).
* A **Power BI** workspace.
* Directly within a **Lakehouse**.

---

### 2. Interface Overview (Power Query Online)
Dataflows Gen2 leverage **Power Query Online** to provide a visual, low-to-no-code interface for data preparation. The workspace is divided into five key functional areas:

#### 1. Power Query Ribbon
This toolbar serves as the control hub for establishing connections and configuring transformations.
* **Supported Data Sources:** 
  * Cloud & on-premises relational databases.
  * Excel or flat files (CSV, TXT, etc.).
  * SharePoint, Salesforce, and Spark.
  * Microsoft Fabric Lakehouses.
* **Common Transformations Available:**
  * *Organising:* Filter and Sort rows, Choose Top N or Bottom N.
  * *Structuring:* Pivot & Unpivot, Split & Conditional split.
  * *Combining:* Merge queries (joins) & Append queries (unions).
  * *Cleaning:* Replace values, Remove duplicates, Rank and Percentage calculations.
  * *Schema Modification:* Add, Rename, Reorder, or Delete columns.
* **Management Tasks:** Create and manage connections, set parameters, and configure default data destinations.

#### 2. Queries Pane
* **Definition:** Displays all the different connected data sources, representing each as an individual "query".
* **Downstream Load:** These queries become physical **tables** when successfully loaded into your target data store.
* **Best Practices:**
  * **Duplicate/Reference:** You can duplicate or reference a query to create multiple copies of the same raw data (e.g., when designing a star schema and splitting a wide source table into separate, smaller tables).
  * **Disable Load:** If a query is only needed as an intermediate stage (e.g., a staging query for a merge operation), you can disable its load so it is not written to the destination.

#### 3. Diagram View
* **Function:** Provides an interactive, graphical visualization showing how your data sources are connected and the exact sequence of applied transformations.
* **Visual Representation:** Each query is represented as a distinct shape showing its transformations, connected by lines to represent references or duplicates.
* **Flexibility:** This view can be toggled on or off to suit your screen space preferences.

#### 4. Data Preview Pane
* **Purpose:** Displays a subset of your data in real-time, allowing you to instantly preview how transformation steps affect the data.
* **Interactive Design:** You can drag and drop columns to change their order, or right-click column headers to apply filters and quick changes directly.

#### 5. Query Settings Pane
This pane is essential for auditing and editing the transformation history.
* **Applied Steps:** Tracks every action taken on the query. Several steps are automatically applied upon connecting to a source, and subsequent transformations are added sequentially.
* **Modifying Transformations:** Most steps feature a **gear icon**, enabling you to edit the step's parameters directly without having to delete and recreate the step.
* **Context Menu:** Right-click any step to rename, reorder, or delete it.
* **Advanced Options:**
  * **Query Folding:** When connected to a source that supports query folding, you can right-click to view the native data source query being pushed back to the source.
  * **Advanced Editor:** For advanced users, the complete underlying **M code** of the query can be viewed and modified directly.

---

### 3. Configurable Data Destinations
Unlike traditional Power Query, Dataflows Gen2 allow you to land your transformed data into specific targets directly from the Query Settings pane.

#### Fabric Destinations:
* **Lakehouse**
* **Warehouse**
* **SQL Database**

#### External Destinations:
* **Azure SQL Database**
* **Azure Data Explorer**
* **Azure Synapse Analytics**

---

### Summary for GitHub Documentation
Dataflows Gen2 provide a visual, accessible bridge for team members of varying technical skill levels. Power BI developers who are already proficient with Power Query can quickly leverage this interface to perform robust data transformations upstream, ultimately optimizing report performance.
