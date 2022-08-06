# JMeter_instructions

## Initialization
- Install Jmeter -> [Installation link](https://www.youtube.com/watch?v=A_PSfvnIlz8)
- note: You need to setup jmeter globally [Instructions](https://www.how2shout.com/linux/install-apache-jmeter-on-ubuntu-20-04-lts-focal-fossa/) 
- Run Jmeter in GUI mode `user@pc:~$ jmeter`

## Creating a new test plan
- Right click on test plan and create a new **thread group** ( this simulates a user)
- Right click the thread group and hover over sampler to create a new **Scenario/Request**. (for API testing choose HTTP Request)
- Right click on the HTTP Request and select a listener to monitor all the responses.
- Click on run or `ctrl+r` to simulate a HTTP Request to your selected API.
- You can increse the number of times the specific user does a particular activity by increasing the number of Threads.
- You can add an assertion to each Request to cross check the particular request for a response code or json format etc. Note that assertions execute once the response has been recieved after the request has been sent. Down below I have attached the flow of execution of components in JMeter.

### Flow of execution
    1. Configuration elements
    2. Pre-Processors
    3. Timers
    4. Sampler
    5. Post-Processors
    6. Assertions
    7. Listeners


### Running jmeter in non GUI mode
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

- Now change the directory to the location where the report is generated.
- Open the index.html using a web browser.
