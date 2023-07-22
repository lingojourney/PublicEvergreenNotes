# YouTube Tutorial
- https://www.youtube.com/watch?v=8loLHbhfyh0&t=615s

# How to use JMeter
- Step: 1: Create a new Test Plan
- Step: 2: Add a Thread Group
- Step: 3: Add a Sampler
- Step: 4: Add a Listener
- Step: 5: Add a Timer
- Step: 6: Run the Test Plan
- Step: 7: View the Results
- Step: 8: Save the Test Plan

# How to use JMeter - Step 1: Create a new Test Plan
- Right click on Test Plan
- Add > Threads (Users) > Thread Group

# How to use JMeter - Step 2: Add a Thread Group
- Thread Group
- Number of Threads: 10
- Ramp-Up Period (in seconds): 1
- Loop Count: 1

# How to use JMeter - Step 3: Add a Sampler
- Thread Group
- Sampler > HTTP Request
- Protocol: http
- Server Name or IP: localhost
- Port Number: 8080
- Method: GET
- Path: /api/trades

# How to use JMeter - Step 4: Add a Listener
- Thread Group
- Listener > View Results Tree

# How to use JMeter - Step 5: Add a Timer
- Thread Group
- Timer > Constant Timer
- Thread Delay (in milliseconds): 1000

# How to use JMeter - Step 6: Run the Test Plan
- Click the green play button to start the test

# How to use JMeter - Step 7: View the Results
- Click on the View Results Tree node
- Click on the Response Data tab to view the results

# How to use JMeter - Step 8: Save the Test Plan
- File > Save Test Plan As...
- Enter a name for the test plan
- Click Save

# Where to save the JMX file in a Maven project: src/test/jmeter

# Adapt the above for: curl --request POST -F "file=@trade.csv" --header "Accept: text/csv" http://localhost:8080/api/v1/enrich
