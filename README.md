# Do Internal Software Metrics Have Relationship with Fault-proneness and Change-proneness? - Online Appendix
## SIMPAC-24-178

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
