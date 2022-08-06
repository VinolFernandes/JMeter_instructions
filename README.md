# JMeter_instructions

### Run jmeter through command line

```
jmeter -Jjmeter.reportgenerator.overall_granularity=1000 -n -t "path_to_test_file" -l "_name_of_csv_file.csv" -e -o "directory"
```
- If you havent setup jmeter to run globally in your machine, then replace `jmeter` with `jmeter.bat` for windows and `jmeter.sh` for linux/ubuntu, but firstly you need to change your directory to where you have installed jmeter in your machine and then relocate to jmeter/bin. 
- The `-Jjmeter.reportgenerator.overall_granularity=1000` indicates the logging of each request per milisecond. This command is **optional** .You can overwrite to intended logging duration . Default is 60000 (1 min).
- `-n` specfies jmeter to run in non-GUI mode.
- `-t` path to the .jmx test file.
- `-l` name of csv file to log sample results to.
- `-e` specifies to generate report dashboard after load test
- `-o` output folder where to generate the report dashboard after load test. Folder must not exist or be empty

### Steps
<hr/>

- Now change the directory to the location where the report is generated.
- Open the index.html using a web browser.
