
# Setting up spark on windows

#### 1. Install python on your machine. 

The Anaconda distribution is quite convenient because it also comes with notebook (ipython/jupyter) and virtual environment (conda)

I use the 3.5 64bit version
```
https://www.continuum.io/downloads
```

#### 2. Download and extract spark
Download the pre-built version for Hadoop 2.7 and later.

The latest version is 2.0.0 which has a lot of under-the-hood performance improvement over 1.6
```
http://spark.apache.org/downloads.html
```
After download, use 7-Zip to extract the folder into C:\

Rename the folder to spark. Now you should have a directory called C:\spark

#### 3. Change verbosity of Spark log messages

By default, spark returns very detailed messages into the log.

This can be adjusted, or supressed, by changing the log4j.properties.template in the conf directory inside the spark folder.

First rename the file log4j.properties.template to log4j.properties.

Then in the file, change the following line
```
log4j.rootCategory=INFO, console
```
to
```
log4j.rootCategory=WARN, console
```
This will only show warnings or errors in the log.

If you want to only show error messages, then set the line to be
```
log4j.rootCategory=ERROR, console
```

#### 4. Install winutils
Even though spark can be run in a standalone mode (without Hadoop), it will try to locate the winutils binary in the hadoop path.

The fix to this is to download just the winutils file and set HADOOP\\_HOME path variable to the binary file
```
http://public-repo-1.hortonworks.com/hdp-win-alpha/winutils.exe
```
Copy this exe file to
```
C:\winutils\bin\winutils.exe
```
#### 5. Set up path variables
* JAVA//_HOME
```
C:\Program Files\Java\jdk1.8.0_102
```
Then add PATH environment variable as
```
%JAVA_HOME%\bin
```