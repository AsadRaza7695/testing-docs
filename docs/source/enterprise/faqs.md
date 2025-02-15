# FAQs

**Q: What is Browsermon Enterprise?**
A: Browsermon Enterprise is a browser monitoring tool designed for enterprise environments. It includes advanced features such as centralized management, health checking, and license validation through the Watchdog server.

**Q: How does Browsermon Enterprise differ from the Community version?**
A: Community version is designed for use on a standalone computer, lacking client-server support. In contrast, enterprise version offers additional features such as Watchdog (centralized server), comprehensive 24x7 support, and advanced management capabilities.

**Q: What information does the controller send to the watchdog server?**
A: The controller sends the following details about itself to the `/api/check-license/` endpoint on the watchdog server:
- Unique ID (GUID)
- Hostname (computer name)
- Version (software version)
- IP addresses
- MAC address (network interface identifier)
- Operating system (OS)
- Label (machine identifier tag)

**Q: What ports need to be open for Browsermon Enterprise to function properly?**
A: The default ports that need to be open are 1514 for Grafana access, 9092 for Kafka communication, 9200 for eti based URLs classification and 5601 for watchdog. Additional ports may be required based on specific configurations.

**Q: How does the server match the controller information to configuration settings?**
A: The server reads the configuration and `mapping.conf` files, then uses the details from the controller (such as label, IP address, hostname, MAC address, and operating system) to find the best matching department.

**Q: How is the config identified on the bases of department (i.e HR, Staff, Accounts etc)?**
A: Once the right department is identified, the server selects the corresponding settings from the `browsermon-watchdog.conf` file. These settings are customized based on the controller's operating system.

**Q: What parameters does Browsermon capture?**
A: Browsermon captures 18 distinct browsing parameters, including hostname, operating system, browser type and version, profile information, URL visited, visit time, visit count, and URL classification. A detailed list is provided in the Features section.

**Q: How do I access the Grafana dashboard for data visualization?**
A: Grafana can be accessed via port 1514. Ensure that this port is open and navigate to `https://<server_ip>:1514` in your web browser to access the dashboard.

**Q: How does centralized management work with Watchdog?**
A: Watchdog acts as a centralized management server, registering all Browsermon instances in the enterprise. It performs health checks, license validation, and allows for centralized configuration management.

**Q: What should I do if Browsermon Enterprise is not capturing browser history?**
A: Ensure that the "stop saving history" option in the browser is disabled and sync is enabled. Verify the folder paths in the `browsermon.conf` file and check for errors. Restart the service and the computer if necessary.

**Q: Is Browsermon compatible with all browsers?**
A: Browsermon is specifically designed to work with Google Chrome , Mozilla Firefox Microsoft Edge and Safari browsers. It may not be compatible with other browsers due to differences in their architectures.

**Q: Can I monitor browsing activities in real-time?**
A: Yes, Browsermon offers real-time monitoring capabilities, allowing you to observe browsing activities as they happen. This can be useful for immediate insights into user behavior and security monitoring.

**Q: Is Browsermon Cross-Platform?**
A: Absolutely! Browsermon is designed to seamlessly operate on both Windows and Linux systems. Moreover, our flexible architecture allows us to cater to Mac users upon customer demand.

**Q: How can I export browser history data?**
A: Exporting monitored data is easy. Browsermon allows you to export data in both JSON and CSV formats. This flexibility enables you to analyze and present the data using various tools and methods.

**Q: Why Choose Browsermon Over Other Tools?**
A: Browsermon stands out as a unique and unparalleled tool for threat detection and forensic experts. It goes beyond conventional monitoring and able to aggregate data from different browsers and user profiles in parallel. It also generate user-friendly outputs in flexible JSON or CSV format, empowering you to effortlessly conduct threat correlation and forensic analysis. Additionally, features such as Kafka data storing mode, the Grafana dashboard, and URL threat classification using eti which detects phishing and malware threats based on an up-to-date threat intelligence database provide ease of use and enhanced security for the user.

**Q: Is Browsermon open source?**
A: Yes, the Community version of Browsermon is open source, and you can access the code on GitHub at the following link: [Browsermon GitHub Repository](https://github.com/eunomatix/browsermon)

**Q: How does Browsermon handle data privacy and security?**
A: Browsermon is designed with data privacy and integrity in mind. Browsermon doesn't allow capturing the browsing payloads (HTML pages, form data, cookies and other user private data).

**Q: Will Browsermon slow down my computer or interrupt my browsing?**
A: No, Browsermon is designed to be non-intrusive. It operates seamlessly behind the scenes, regardless of your operating system, without causing disruptions or interfering with other data on the system.

**Q: Is Browsermon suitable for both individual and enterprise use?**
A: Yes, browsermon offers flexible pricing plans designed to cater to the needs of individuals, growing teams, and businesses, ensuring that they align perfectly with various goals and requirements.

**Q: Can Browsermon be tailored to different organizational needs?**
A: Browsermon's flexible architecture allows it to be customized to meet the unique monitoring requirements of various organizations, from small businesses to large enterprises.

**Q: What if I encounter technical issues with Browsermon?**
A: If you encounter technical issues, first consult the user guide and documentation for troubleshooting tips. If the problem persists, you can contact our dedicated support team for assistance, by emailing at support@browsermon.ai

**Q: Can I customize the monitoring parameters?**
A: You can email new feature requirement at support@browsermon.ai, our engineering team will review and add the feature in future release (if feasible).

**Q: Is Browsermon suitable for forensic analysis?**
A: Yes, Browsermon's comprehensive logs and detailed data collection make it suitable for forensic analysis. It can aid in reconstructing digital activities and understanding user behaviors.

**Q: Does Browsermon support multiple users and profiles?**
A: Indeed, Browsermon is a robust solution that efficiently gathers data from all users within the operating system, encompassing various browser profiles. This ensures comprehensive insights into user behavior and preferences.

**Q: Does running Browsermon require administrative privileges?**
A: Yes, Browsermon is crafted to monitor all users and their diverse browser profiles within the operating system. To ensure optimal functionality and data collection, it is essential to run Browsermon with administrative privileges.

**Q: Can Browsermon be integrated with existing security information and event management (SIEM) systems, such as Splunk?**
A: Browsermon offers seamless integration with popular SIEM systems, including Splunk. Users can export the captured browsing activity data in either CSV or JSON format and effortlessly incorporate it into their Splunk environment. This integration empowers organizations to centralize and correlate browser activity data with other security events, enabling a comprehensive analysis of potential threats. By leveraging the flexibility of exporting data to Splunk, Browsermon provides an efficient solution for enhancing security monitoring and analysis within the context of broader SIEM operations

**Q: What is Browsermon Watchdog?**
A: Watchdog serves as a centralized management and licensing server for Browsermon agents installed in the enterprise. Watchdog operates on a dedicated Linux server (or VM) and registers all enterprise Browsermon instances to perform health checking and validate licenses.

**Q: Which language is used to develop Browsermon?**
A: Python is the primary programming language used to construct Browsermon and its associated components.

**Q: Why Browsermon is better than any industry EDR (endpoint detection and response) for browser artifact collection?**
A: Browsermon is designed specifically to work seamlessly with all types of browsers (Microsoft Edge, Chrome, Firefox, etc) on any Linux and Windows endpoints. Whereas, conventional EDRs monitor limited types of browsers and do not collect rich artifacts required for deep forensic analysis. Browsermon also provides easy exportable formats (including JSON and CSV) and can be further ingested into any security analytical platform (like Splunk, Elastic, etc). It also features eti-based URL classification, which detects phishing and malware threats using an up-to-date threat intelligence database, ensuring enhanced security and threat detection.

**Q: Can Browsermon log multiple browsers active on an endpoint in parallel?**
A: Browsermon is a multi-threaded agent and can discover and log all active browser profiles created by multiple active users on endpoints.

**Q: What authentication privileges are required by Browsermon?**
A: Browsermon needs privileged access (root/administrator) to the OS in order to collect browser artifacts.

**Q: How do I troubleshoot issues with the Watchdog server?**
A: Check the Watchdog server logs located at `/var/log/watchdog/` and ensure the server is running using `systemctl status watchdog.service`. Verify configuration settings in the `watchdog.conf` file and ensure all required ports are open.

**Q: How can I generate a troubleshooting report?**
A: Use the Browsermon troubleshooter by running `browsermon_ts troubleshoot -v` for a standard report or `browsermon_ts troubleshoot -vv` for a comprehensive report. This will collect logs and relevant information into a `browsermon_archive.zip` file for further analysis.

**Q: How do I troubleshoot issues with the license validation process?**
A: Check the watchdog server logs for any errors related to license validation. Ensure that the GUID and other details sent by the controller are correctly formatted and all required information is included. Verify that the number of active devices does not exceed the allowed limit.

**Q: What can I do if the configuration is not matching the controller's details correctly?**
A: Verify that the details sent by the controller (label, IP address, hostname, MAC address, and operating system) are correct and match the criteria specified in the mapping files. Check the configuration files for any errors or discrepancies.

**Q: What happens if Browsermon gets disconnected from the Watchdog server?**
A: When disconnected, the controller attempts to reconnect 10 times with a 30-minute interval between each attempt (total 5 hours). If all attempts fail, the controller shuts down while reader processes continue running as zombies. These zombie processes continue collecting data but lose supervision features like configuration reload and automatic restart. To resolve this:

- Stop zombie processes: ```Stop-Process -Name "browsermon" -Force```
- Restart the service: ```Restart-Service -Name "browsermon"```

**Q: What happens if a URL is queried multiple times?**
A: The first time a URL is classified, its result is stored in the cache. On subsequent visits to the same URL, the system retrieves the classification from the cache, bypassing eti, which reduces processing time and network traffic. Cache settings can be set by user inisde browsermon.conf.

**Q: During an update how to ensure log processing resume from the last recorded position**
A: For optimal continuity, maintain the same logdir path as used in previous versions. This ensures the new version will resume log processing from the last recorded position.

**Q: What is the EUNOMATIX Threat Intelligence (ETI) Service?**
A: ETI is a free threat intelligence service for EUNOMATIX customers that collects and provides real-time malicious URL detection using open-source intelligence (OSINT) feeds such as URLhaus and PhishTank.

**Q: How often is the ETI database updated?**
A: ETI is synchronized every 24 hours through an automated scheduler, ensuring that the latest threat intelligence data is available.

**Q: Where is the collected threat intelligence data stored?**
A: All collected URL feeds are stored in an eti database running on port 9200.

**Q: What happens if I run the Watchdog installer script on an existing installation?**
A: When you run the Watchdog installer script, it will prompt you to confirm whether you want to update the existing files in the Watchdog installation directory. If you choose "Yes," the files will be updated. If you choose "No," the existing files will remain unchanged, and new files will not be copied over.

**Q: What should I be aware of when running the installation in Kafka mode?**
A: If you are running the installation in Kafka mode, do not delete or remove the volumes. Doing so may result in the loss of Kafka and MongoDB data, as these services rely on persistent storage to retain information.
