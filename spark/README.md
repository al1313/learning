
# Setting up spark on windows

#### 1. Install python on your machine. 

I find the Anaconda distribution is the most convenient because it also comes with notebook (ipython/jupyter) and virtual environment (conda)

I use the 3.5 64bit version
https://www.continuum.io/downloads
Note. keep jupyter up to date with
conda update jupyter
#### 2. Download and extract spark
Download the pre-built version for Hadoop 2.7 and later.

The latest version is 2.0.0 which has a lot of under-the-hood performance improvement over 1.6
http://spark.apache.org/downloads.html
After download, use 7-Zip to extract the folder into C:\

Rename the folder to spark. Now you should have a directory called C:\spark

#### 3. Change verbosity of Spark log messages

By default, spark returns very detailed messages into the log.

This can be adjusted, or supressed, by changing the log4j.properties.template in the conf directory inside the spark folder.

First rename the file log4j.properties.template to log4j.properties.

Then in the file, change the following line
log4j.rootCategory=INFO, console
to
log4j.rootCategory=WARN, console
This will only show warnings or errors in the log.

If you want to only show error messages, then set the line to be
log4j.rootCategory=ERROR, console

```python

```
