To run this program change the following variables in fault-proneness/src/main/Main.java file:
	cwd = "directory of the project to analyse"
	project = "name of the project"
	projectConfigFile = "name of the configuration file"
	repo = "cloned repository of the project"
	resDir = "name of the directory where results will be written"
	issueDir ="name of the directory where issues are downloaded"

Then, run the Main.java

Configuaration file:
It contains the list of tags/releases to analyse and bugpattern
Check the sample configuration file change-proneness/demo-project/activemq.conf

Downloading issues:
	For Bugzilla:
	    https://gist.github.com/toukir-ahammed/3dd6db6437f8e32e64acea232414aafb#file-fetch_bugzilla_issues-py
	For Jira:
	    https://gist.github.com/toukir-ahammed/3dd6db6437f8e32e64acea232414aafb#file-fetch_jira_issues-py


