
# 1. Global settings
 **tag: global**
 
 its general setting for both w.m and w.a. These are high-level configurations that control core behavior such as logging, alerting, and system modes.
 
**Features:**
 email notification,logging options

 # 2. agent configuration
**tag: client** 

its used only on agent side. its tells about how agents are communicate with w.m

# 3. monitoring systems without agent 
**tag: clientless** 

its allows w.m to monitor the devices without agent install.

# 4. Managing Detection rules and DEcoders
**tag: ruleset** 

in this section we mentioned the rules and decoders dir to log analysis and alert generate

# 5. Controls Communication B/w Agent and Manager
**tag: remote**

its define how w.m receives the logs from agent (port, protocol,type(plin,secure))
# 6. Customize Alerting Behavior and Group Rules
**tad: rules**

configures how alerts are triggered and grouped, including: Alert severity threshold, Group-based email alerts, etc.
# 7. File Integrity Monitoring (FIM)
**tag: syscheck**

It tracks changes to important files and directories. File additions, modifications, and deletions . Changes to permissions, ownership, and content . Windows Registry key monitoring (on Windows)
# 8. Rootkit, Malware & Policy Violation Detection
**tag: rootcheck**

scan the system --> Known rootkits, Suspicious files or binaries , Misconfigurations or policy violations, Unusual system behavior or hidden processes
# 9. Custom Log File Monitoring
**tag: localfile**

this section tells Wazuh to monitor specific log files on our local system. Application logs, Custom software logs, System logs ( /var/log/auth.log, /var/log/syslog), Windows Event Logs 
# 10. Custom Commands for Active Response
**tag: command**

used to custom shell commands or scripts that Wazuh can execute, As part of active responses (blocking IP), As commands to be monitored via **<localfile>** with log_format as command or full_command
place the scrtpts in this location /var/ossec/active-response/bin/

# 11. Automated Threat Mitigation
**tag: active_response**

 automatically respond to detected threats by executing predefined commands (defined in the **<command>** section). Block malicious IPs, Disable user accounts, Run custom scripts

 # 12. wazuh module (wodle)
 **tag: wodle**

 Wodles enable specialized monitoring beyond basic log analysis. its collect more informtions, runnig cmds

 These modules extend Wazuh’s capabilities by integrating with other tools or collecting specialized data

 # 13. Security Configuration Assessment (SCA)
 **tag: sca**

 its like checklist to checks systems security (pass strength, firewall on?, file permission are safe, complience check)

 # 14. tagging or metadata
 **tag: lables**

 its allows us add metadata to agent and w.m. info like department, location, environment, asset type, or owner. These labels are stored and visible in the Wazuh dashboard (under agent details).

They can also be used in rules, queries, and automation.

# 15. Windows Registry Monitoring
**tag: registry**

monitor changes in the Windows Registry. it can detect if keys or values are added, deleted, or modified. its very important for detecting malware, persistence mechanisms, or unauthorized changes.

# 16. Wazuh own logs
**tag: logging**

This section tells Wazuh itself how to record its own events, like startup messages, errors, module activities, and alert processing.
path to store logs --> /var/ossec/logs/ossec.log

# 17. Wazuh Cluster Configuration
**tag: cluster**

used to connect multiple Wazuh managers for scalability, high availability, and redundancy. It allows managers to share alerts, configuration, and synchronization across nodes 

# 18. Vulnerability Scanning
**tag: vulnerability-detector**

 scans systems for known security vulnerabilities based in vulnerability databases like cve.


