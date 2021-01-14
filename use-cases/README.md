# What is the use case?
The use case is quite simple, based on the config files, this script automatically logs in to the targeted Secure Network Analytics SMC and looks for all the IP addresses that in the last hour (parameter that can be modified in the configs), either as source or as target, generated an abnourmally high total traffic. 
As continuing inbound or outbound traffic (or a mix of the two), is generally a sign of anomalous behavior, the script creates a TAG (host group) to which it adds the source IP addresses, of the inside hosts, that were part of such events.
Once the TAG is created, further analysis can be performed.
This is of extreme importance especially in a cloud environment, where the client has less control and visibility over what the devices are actually doing and how they are communicating.
The script, automating the procedure, saves time potentially detecting a threat before it spreads preventing a security incident.

Possible future improvements include:
- Integration with Umbrella, to analyze the destination IP addresses and gather more information about them so as to determine whether the High Total Traffic was a signal for an actual threat.
- Integration with Secure Endpoint, to provide context as per which process is responsible for this abnormal amount of traffic.
- Integration with Webex, to signal the discovery of a new host (or IP) that triggered the alarm, and providing in the message the additianl context and info gathered from Umbrella and Secure Workload.
- Integration with Secure Workload, to automatically block the connection with the IP and blacklist it if the evidence gathered is enough to have a certain degree of certainty.

# Try it yourself
In case you don't have a Secure Network Analytics solution to use, you can take advantage of the DevNet website and reserve a sandbox by following these steps:
1. [Follow this link](https://developer.cisco.com/docs/sandbox/#!security/overview)
2. Click on "Try It Out" in the Cisco Stealthwatch section (that's the former name for Secure Network Analytics). This will open a second window in yur browser.<br /> <img src="https://github.com/communikein/dne-stealthwatch-mission/blob/main/use-cases/images/step-0.png" width=70% height=70%>
3. In the top of the window, look for a blue bar. At its rightmost end you will find a "Reserve" button. Click on it. <br /><img src="https://github.com/communikein/dne-stealthwatch-mission/blob/main/use-cases/images/step-1.png" width=70% height=70%>
4. Enter the required details to reserver your instance (there is a maximum of 4 hours of reservation available).
5. Click on "Reserve". <br /><img src="https://github.com/communikein/dne-stealthwatch-mission/blob/main/use-cases/images/step-2.png" width=70% height=70%>
6. After 10-15 minutes an email will be sent to you with the details on how to access the sandbox.

# Setup the Secure Network Analytics SMC
If you are using a DevNet sandbox instance, you will need to run ```python3 setup.py``` since the traffic that the sandbox generates is not enough to trigger the security events. This script will edit the policy for the chosen security event to lower the threashold that would generate the alarm.

To run the script simply type:
```python
python3 setup.py <security_event_id>
```