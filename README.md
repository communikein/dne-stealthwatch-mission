# DevNet Express - Cisco Secure Network Analytics Mission

# Mission: Retrieve security events and create host group​
In this mission, you will use Cisco Secure Network Analytics to identify and retrieve some Security Events and create a TAG (host group) containing the information retrieved.

# Objectives
The objective of this mission is to teach the following Cisco Secure Network Analytics:

- Identify the "Total High Traffic" Security Events. 
- Retrieve all the "Total High Traffic" Security Events
- Create a TAG (host group) containing the first 10 source IP addresses from the retrieved Security Events.
- Clean-up the environment (remove the TAG)
Note: Webex Teams is now known as Webex.

# Prerequisites
To complete this mission you need:

A development environment with typical tools and applications. If you are at a DevNet Event using a provided workstation, you are ready to go. If you are working from your own workstation, please click How to setup your own computer at the top of this page and follow the procedures to configure your workstation.
Lab infrastructure to target API calls and code. These labs and code examples will use the Cisco dCloud infrastructure, which is provided to you by your DevNet Express instructors.

You should also have an understanding of these foundational topics:
- The content in the "An introduction to the Cisco Secure Network Analytics APIs" Learning Lab.
- Ability to read and understand Python code samples and scripts. You can explore the Programming Fundamentals labs available on DevNet.

# Your mission, should you choose to accept it!
Your instructor will provide a code sample. Your mission is to complete the code sample by filling in missing data. The majority of the provided code sample is complete and accurate. You simply need to fix or update sections indicated in the code by MISSION marks. Pay attention to the TODO: and HINT: in the code, they will provide you with additional information and hints to proceed if you get stuck.

# The goal
1. Complete the code with MISSION and TODO indications.
2. Find the right Secure Network Security Event ID and fill in the API endpoint URLs.
3. Apply key concepts about Cisco Secure Network REST APIs learned in the labs and hands-on exercises.
4. Successfully execute the secure_network_mission.py script and review the results: a new TAG with your Webex username has been created containing the first 10 source IP addresses found from the Security Events.

# Starting the mission
1. Open secure_network_mission.py in a text editor.
2. Search for MISSION and TODO to find the sections to update. For example:

	```python
	# TODO: Find the search query ID, so as to later check the status and access the result.
	# HINT: The API documentation is your friend ;)
	env_lab.print_missing_mission_warn(env_lab.get_line())
	search_id = MISSION
	```

3. Within the code, replace MISSION with the correct value.
	- There may be more than one MISSION section in a code sample.
	- Each MISSION section may contain more than one element that needs updating.
	- Remember to remove the related 'env_lab.print_missing_mission_warn()' line after you filled-in the MISSION task.

# Caveats and gotchas
The only file that needs changes is secure_network_mission.py.
Only replace instances of MISSION within the code. Be careful not to replace characters before or after it.
A Cisco Secure Network API key and client key is required to complete the mission. This will be provided by your instructor.

# Verifying the solution
Have you successfully completed the mission? Let's find out.

# Running your code
Open a terminal and navigate to the root of the dne-security-code repository.
Navigate to the mission directory, intro-secure-network/mission.
	
	```
	cd intro-secure-network/mission
	```

Run the Python file that you edited for the mission.
	
	```
	python secure_network_mission.py
	```

# What to expect
If you successfully completed the mission, the script should complete without errors. The output will be similar to the following:

	```
	==> Logging in to the SMC
	Login SUCCESSFUL!

	==> Finding all Tenants available
	Found all the following tenants: [{'displayName': 'abc.inc', 'id': 132}]
	Working on Tenant ID is: 132

	==> Created query looking for all the hosts that generate high amount of traffic in the last 60 minutes.
	Generating results. Please wait...
	Search progress: 0.0%
	Search progress: 100.0%
	Search query completed!
	Total found events: 0
	Collected the following first 10 IP addresses: set()

	==> Creating new TAG named: [Elia Maracani] - High Traffic Hosts
	New tag (host group) successfully added
	{
	    "data": [
	        {
	            "id": 50081,
	            "name": "[Elia Maracani] - High Traffic Hosts",
	            "location": "OUTSIDE",
	            "ranges": [],
	            "description": "Hosts generating or receiving an unusually high amount of traffic.",
	            "hostBaselines": false,
	            "suppressExcludedServices": false,
	            "inverseSuppression": false,
	            "hostTrap": false,
	            "sendToCta": false,
	            "domainId": 132,
	            "parentId": 2147483647
	        }
	    ]
	}

	==> Sending message to Webex Space bragging for a completed mission! :D
	Message sent, StealthWatch Enterprise Mission Completed!!!

	==> Removing TAG 50081
	Tag 50081 has been successfully removed
	```

# Summary
Congratulations! You have used the Cisco Secure Network REST APIs to identify and retrieve some Security Events and create a TAG (host group) containing the information retrieved.

- You found the correct Security Event ID
- You identified all the "Total High Traffic" Security Events.
- You retrieved the first 10 source IP addresses from the Security Events.
- You created a TAG (host group) containing the IP addresses.
- You deleted a TAG from Cisco Secure Network.

Nice work! Now click the final right arrow below to complete this lab!