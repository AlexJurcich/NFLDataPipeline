# NFLDataPipeline
Built a full data pipeline combining BigQuery (structured) and MongoDB (unstructured) data.

---

## Introduction
We have seen a major shift in sports organizations utilizing data to uncover insights, optimize decision-making, and enhance performance. The National Football League (NFL) has become the industry leader in sports analytics. Many teams have full-time data scientists and data engineers who face the challenge of storing, processing, and managing structured and unstructured data. Some examples include play-by-play data, player-level statistics, and player tracking data.

This project aims to design and implement a big data pipeline that is tailored for NFL game analysis. Specifically, the pipeline turns structured data sources, including play-by-play logs and player statistics, as well as semi-structured data sources, including tracking coordinates, into a scalable architecture using Google BigQuery and MongoDB. By using distributed and NoSQL storage, the project demonstrates concepts from the LifeCycle and Pipeline course module while preparing the data for analytics and visualization. While the project will include some analytical outcomes, the primary focus is on the design, implementation, and management of the data processing workflow.

---

## Background
The reason I came up with this project design is due to the technical challenges it presents and its relevance to my aspiration to work in the field. I understand that data infrastructure is one of the foundations of meaningful analysis. During a football game, there are 22 players on the field, each one of them wearing a tracking chip in their shoulder pads. The tracking chip collects data every millisecond. Thus, by the end of the season, we have millions of rows of tracking data. Without a scalable and well-structured pipeline to manage this data, it becomes impossible to generate insights and perform effective analysis.

---

## Results
The objective of this project was to integrate diverse data sources and technologies to visualize and analyze NFL game and tracking data. A primary accomplishment was the successful use of Google BigQuery to manage structured data and MongoDB to handle unstructured tracking data. By querying and combining data, we created a detailed and dynamic animated visualization that captures player movement during a play, distinguishing between offensive and defensive units.

This project demonstrated the use of cloud-based big data analysis and visualization software. It showed the need for data integration between storage systems and demonstrated the merging of structured game metadata with high-frequency tracking data to produce valuable insights. In doing so, we employed skills from the course, including data querying, joining heterogeneous data sources into datasets, and generating interesting visual representations of actual sports scenarios.

---

## Technolgies & Skill Used:
**MongoDB**  
Used to store and retrieve high-frequency tracking data for each player on a per-play basis. We queried MongoDB to reconstruct the positions of all players over time.

**Google BigQuery**  
Queried for static and contextual game information (e.g., possession team, clock, down and distance, team abbreviations).

**Python (Pandas, Matplotlib, NumPy)**  
Served as the backbone of data manipulation and visualization.

**Jupyter Notebook / Google Colab**  
Provided an interactive environment to write, execute, and iterate on code. Enabled inline visualization of animated plots and seamless integration across MongoDB and BigQuery workflows.

---

## Data Volume and Memory Problems
One of the biggest challenges I had during the project was the volume of tracking data. There are hundreds of plays in every NFL game, and every play tracks between 22 players at 10 frames per second. While attempting to import all the available tracking data for Weeks 1 to 4 into MongoDB Atlas, we quickly exceeded the free-tier memory limit (512 MB).

As a result, we had to cut back and use only part of the data, specifically, half of the Week 1 tracking data. This reduction allowed us to continue with the analysis and visualization work within our MongoDB Atlas instance's limits.

A potential solution to this issue would be to either move to a paid MongoDB Atlas plan with more storage space or refactor the database to store only essential fields. Another option would be to stream data in batches at runtime or cache older data outside of the cluster. These solutions would enable us to analyze more of the season while not breaching storage constraints.

---

## Conclusion
In this project, we demonstrated how to build a data pipeline by integrating structured and unstructured data, employing Google BigQuery for static player and game metadata and MongoDB for high-frequency tracking data on players. Through effective querying, joining, and visualization, we built an animated NFL play that highlighted player movement, team alignment, down, distance, and game clock context. While we were limited by storage space, the pipeline itself provides a scalable basis for more in-depth analysis today. Having built the infrastructure, we can draw on this effort to explore issues like play success prediction, defensive coverage detection, motion tendencies, or route clustering, supporting a range of sophisticated football analytics from integrated, synchronized data.

