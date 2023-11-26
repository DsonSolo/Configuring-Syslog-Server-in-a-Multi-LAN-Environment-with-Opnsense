**Implementing a Centralized Syslog Server in a Multi-LAN Environment
with Opnsense**

In this project, I undertook the task of setting up and managing a
Syslog Server within a multi-LAN environment. The scenario presented a
real-world challenge, simulating an employer's request to establish a
centralized system for managing alerts from various network devices.
This endeavor required a blend of network configuration, security
enhancement, and meticulous documentation.

The following report chronicles my step-by-step approach to fulfilling
the project requirements, encompassing the download and configuration of
Syslog Watcher, fortification of security measures, and detailed log
analysis. Each part of the project unfolds a specific aspect of my
technical proficiency and problem-solving skills in network
administration.

**Part 1: Setting Up Syslog Watcher**

I initiated this project by downloading Syslog Watcher and ensuring its
integrity by verifying the MD5 hash. The meticulous process involved
capturing a screenshot to demonstrate the matching MD5 hash.

<img src="./media/image1.emf" style="width:6.5in;height:4.68889in" />

**Figure 1. A Screenshot of Matching MD5 hash with the MD5 hash value
given by the Syslog Watcher Installer obtained from a trusted website**

Subsequently, I proceeded to install Syslog Watcher on PC1, configuring
both the server and manager components. To facilitate incoming
connections, I added a firewall exception, further substantiated by
relevant screenshots.

<img src="./media/image2.emf" style="width:6.5in;height:4.74722in" />

**Figure 2. Adding firewall exception to allow incoming connections via
Syslog Watcher**

The final step in this section involved configuring OPNsense to forward
its logs to Syslog Watcher, a crucial integration depicted through a
screenshot.

<img src="./media/image3.emf" style="width:6.5in;height:5.50278in" />

**Figure 3. Configuring Opnsense to forward its logs to Syslog watcher
on PC1**

<img src="./media/image4.emf" style="width:6.5in;height:5.75625in" />

**Figure 4. The Syslog Watcher Server accepting logs from OPNsense
Firewall**

<img src="./media/image5.emf" style="width:6.5in;height:5.73681in" />

**Figure 5. A Screenshot showing OPNsense logs going to Syslog Watcher**

**Part 2: Enhancing Security Logging and Windows Event Forwarding**

This phase focused on fortifying security measures. I configured PC2 to
log both successful and failed login attempts, capturing screenshots for
documentation.

<img src="./media/image6.emf" style="width:6.5in;height:5.42639in" />

<img src="./media/image7.emf" style="width:6.325in;height:4.45in" />

**Figure 6. Configuring PC2 Security to log successful and failed login
attempts**

The installation of SolarWinds Windows event forwarder on PC2 followed,
accompanied by the creation of a firewall rule to permit outgoing access
for the program.

<img src="./media/image8.emf" style="width:6.5in;height:4.87986in" />

<img src="./media/image9.emf" style="width:6.5in;height:5.52778in" />

**Figure 7. The Syslog Server is accepting logs forwarded from PC2**

<img src="./media/image10.emf" style="width:6.5in;height:5.52778in" />

**Figure 8. The Logs showing that PC2 forwarded Informational, Warning
and Notice messages to Syslog server on PC1**

The integration of Windows telnet features on PC2, connection to
specified telnet resources, and subsequent creation of a rule on
OPNsense to block telnet traffic for the guest network were methodically
executed, each step supported by pertinent screenshots.

<img src="./media/image11.emf" style="width:6.5in;height:5.39861in" />

**Figure 9. The window showing PC2 connecting to telehack.com via port
190**

<img src="./media/image12.emf" style="width:6.5in;height:5.44306in" />

**Figure 10. Configuring a rule on OPNsense firewall to block telnet
traffic for guest network**

<img src="./media/image13.emf" style="width:6.5in;height:3.86736in" />

<img src="./media/image14.emf" style="width:6.5in;height:4.27847in" />

**Figure 11. Configuring a rule on OPNsense firewall to block telnet
traffic for guest network**

<img src="./media/image15.emf" style="width:6.5in;height:5.36736in" />

**Figure 12. PC2 trying to make unsuccessful telnet connection with
PC1**

<img src="./media/image16.emf" style="width:6.5in;height:4.39444in" />

**Figure 13. Screenshot of firewall logging telnet connection forwarded
from PC2**

**Part 3: Log Analysis and Event Simulation**

In the final segment, I deliberately attempted 5 failed logins on PC2 to
analyze the logs in Syslog Watcher.

<img src="./media/image17.emf" style="width:6.5in;height:5.39444in" />

**Figure 14. Attempting 5 failed login on PC2 and Event Viewer showing
the log information**

This investigative process was complemented by a dedicated screenshot,
providing a clear visual representation of the logged events.

<img src="./media/image18.emf" style="width:6.5in;height:4.31458in" />

**Figure 15. A Dedicated screenshot of logged events in syslog watcher**

This conclusive part wrapped up the project, showcasing my ability to
systematically address specific requirements, troubleshoot
configurations, and thoroughly document the entire process.
