# Do Internal Software Metrics Have Relationship with Fault-proneness and Change-proneness? - SIMPAC-24-178

## Repository Structure
- ```change-proneness``` folder contains the source code(```change-proneness-main```) and output(```results```) for the change-proneness analysis
- ```falult-proneness``` folder contains the source code(```fault-proneness-main```) and output(```results```) for the fault-proneness analysis
- ```SoftwareMetricsVsFPandCP - SoftwareImpacts.xlsx``` contains the dataset with all metrics and correlation analysis

## Change-proneness Analysis
1. Open the [change-proneness-main](https://github.com/toukir-ahammed/SIMPAC-24-178/tree/main/change-proneness/change-proneness-main) with Eclipse
2. Clone the project from GitHub which you want to analyze in the directory named ```demo-project```. (_Note: Make sure the project name ends with -repo, e.g., activemq-repo._). For example to analyze Apache ActiveMQ,
```
git clone https://github.com/apache/activemq.git activemq-repo
```
3. Create a configuration file in the ```demo-project``` folder (```projectname.conf```)  for the project you want to analyze. The format of the configuration file can be found [here](https://github.com/toukir-ahammed/SIMPAC-24-178/blob/main/project.conf). The sample configuration file for activemq project ```activemq.conf``` can be found [here](https://github.com/toukir-ahammed/SIMPAC-24-178/blob/main/activemq.conf). In the configuration file, you should give the project name and the list releases/revisions you want to analyze.
4. To Run Analysis, open ```Main.java``` and edit the following line with the project name you want to analyze.
```java
String project = "activemq";
```
5. Run ```Main.java``` and find the results in the ```demo-project/res``` folder. The file named ```projectname-cp.csv``` (e.g., ```activemq-cp.csv```) contains all results.

## Fault-proneness Analysis
1. Open the [fault-proneness-main](https://github.com/toukir-ahammed/SIMPAC-24-178/tree/main/fault-proneness/fault-proneness-main) with Eclipse
2. Clone the project from GitHub which you want to analyze in the directory named ```demo-project```. (_Note: Make sure the project name ends with -repo, e.g., activemq-repo._). For example to analyze Apache ActiveMQ,
```
git clone https://github.com/apache/activemq.git activemq-repo
```
3. Create a configuration file in the ```demo-project``` folder (```projectname.conf```)  for the project you want to analyze. The format of the configuration file can be found [here](https://github.com/toukir-ahammed/SIMPAC-24-178/blob/main/project.conf). The sample configuration file for activemq project ```activemq.conf``` can be found [here](https://github.com/toukir-ahammed/SIMPAC-24-178/blob/main/activemq.conf). In the configuration file, you should give the project name and the list releases/revisions you want to analyze and and bug pattern (the regex pattern for identifying bug fixing commits from commit message). For example, let consider the following commit message from ActiveMQ project that can be identified with the regular expression ```“AMQ-\\d+”```.:
    >“[AMQ-8309] Fix spring import range, change optional to be more flexible . . . ”

4. Download Issue Reports from Jira/Bugzilla
  - **Jira:**
      - Download [jira_batch.py](https://gist.github.com/toukir-ahammed/3dd6db6437f8e32e64acea232414aafb#file-jira_batch-py)
      - Change the following line with project keys.
    ```
      projects = ["AMQ", "CASSANDRA", "CAY", "CXF", "DRILL", "JCR", "JENA", "SOLR", "MAHOUT", "OPENNLP", "PIG", "POI", "XERCESJ"]
    ```
      - The project keys can be found in the Jira repository link. For example,  AMQ is the project key for ActiveMQ
         ht<span>tps://issues.apache.org/jira/projects/**AMQ**/issues/AMQ-7229?filter=allopenissues
      - Run ```jira_batch.py```
  - **Bugzilla**
      - Download [fetch_bugzilla_issues.py](https://gist.github.com/toukir-ahammed/3dd6db6437f8e32e64acea232414aafb#file-fetch_bugzilla_issues-py)
      - Change the following line with the project key.
        ```project = 'ant'```
      - The project keys can be found in the Bugzilla repository link.
      - Run ```fetch_bugzilla_issues.py```
  
  - Make a folder named ```projectname-issues``` (e.g., ```activemq-issues```) in the ```demo-project``` folder and put all downloaded issues (csv files) in this folder.

4. To Run Analysis, open ```Main.java``` and edit the following line with the project name you want to analyze.
```java
String project = "activemq";
```
5. Run ```Main.java``` and find the results in the ```demo-project/res``` folder. The file named ```projectname-fp.csv``` (e.g., ```activemq-fp.csv```) contains all results.

