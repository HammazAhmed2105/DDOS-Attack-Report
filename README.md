# DDOS-Attack-Report
<h2>Scenario</h2>
Students are working on the blue team for a financial services organization (e.g. Edward Jones, etc.).  You are being asked to prepare a report for the CIO/CISO on an on-going security incident that is being executed against your company from an Eastern European based hacking group.

Although technical, the CIO/CISO is not "in the weeds" so your deliverable should be at the strategic level with a technical section for your team (or cyber insurance provider) for subsequent review.  Please feel free to make assumptions as needed as this is designed to measure your real-world applicability of the course content.

For this assignment, students should keep in mind that:

This is essentially a "capstone" like assessment for everything we've talked about in this course.  You can essentially apply anything you've learned in this class to this assignment.  You should be conducting both technical work via the tools you've learned and administrative reporting in this assignment.
Given the incident response frameworks you've researched in Week 6 (e.g. NIST, SANS, etc.), complete a blue team incident response report.  If the framework does not include an executive summary at the beginning, you must include one for your CIO/CISO.
Students can either re-create, use an existing, or assume the red team attack vector (e.g. phishing, lateral movement, PCAPs, etc.), but you should provide some documentation on what the attack looks like from the outside entity.
Students should generate representative screen shot artifacts as applicable to supplement their reports with tools we've covered in the class on ideas to counter this attack vector.
At a minimum, the report should include:
Executive Summary (which is essentially a summary of your detailed report below)
Detailed explanation on:
How the incident occurred
What happened during the incident
Short term remediations put into place
Long term remediations needed for the roadmap
What a claim needs to be made to our cyber insurance provider or whether we need to send a breach notification (and why)

<h2>Blue Team Incident Paper: Reporting of a DDoS Attack.</h2>

### Executive Summary:

JPMorgan Chase & Co. recently encountered a severe SYN Flood Attack, a form of Distributed Denial of Service (DDoS). The attack overwhelmed network resources, causing disruptions and potential denial of service. Immediate short-term remediations included traffic filtering, load balancing, and cloud-based DDoS protection. Aligned with the NIST framework, specific actions were taken in the identification, protection, detection, response, and recovery phases.

During the incident, abnormal TCP stream patterns, sudden CPU spikes, and Wireshark analysis indicated a coordinated attack. The attack was from an Eastern European based hacking group.

Short-term measures involved activating incident response, adjusting firewall settings, and applying traffic filters. Long-term roadmap considerations encompass network architecture review, Intrusion Prevention Systems (IPS) implementation, a DDoS mitigation plan, and ongoing security audits and training.

Insurance and breach notification considerations include a recommended claim to the cyber insurance provider and potential breach notifications, demonstrating a commitment to transparency and trust restoration.

The organization remains vigilant, continually enhancing its cybersecurity posture to mitigate future threats.

## Table 1: Incident Overview

| Aspect                       | Details                                                                |
|------------------------------|------------------------------------------------------------------------|
| Incident Type                | DDoS (SYN Flood Attack)                                              |
| Attack Methods               | 1. Volumetric Attacks: Overwhelming network bandwidth.                |
|                              | 2. Application Layer Attacks: Targeting specific applications or services. |
|                              | 3. Protocol Attacks: Exploiting vulnerabilities in network protocols. |
| Compromised Information       | No direct compromise of information; focus on service disruption.      |
| Impact                       | 1. Service Disruption: Website and online services unavailable.       |
|                              | 2. Loss of Revenue: Inability to conduct business.                    |
|                              | 3. Reputational Damage: Customer trust may be affected.               |
| Short-Term Remediations       | 1. Traffic Filtering: Identifying and blocking malicious traffic.     |
|                              | 2. Load Balancing: Distributing incoming traffic to maintain availability. |
|                              | 3. Cloud-based DDoS Protection: Leveraging specialized services.     |
| NIST Framework Phases        | 1. Identify: Recognize and understand the DDoS threat.                |
|                              | 2. Protect: Implement measures to safeguard against DDoS attacks.     |
|                              | 3. Detect: Monitor network and system activities for signs of DDoS.   |
|                              | 4. Respond: Execute an incident response plan when an attack occurs.   |
|                              | 5. Recover: Restore services and analyze the incident for improvements. |
| Specific Actions Aligned     | 1. Conduct Risk Assessment                                           |
|                              | 2. Implement DDoS Mitigation Solutions:                              |
|                              | 3. Monitor Network Traffic:                                          |
|                              | 4. Activate Incident Response Plan                                   |
|                              | 5. Post-Incident Analysis:                                           |

	
## Incident Occurrence:

The SYN Flood Attack exploited the TCP protocol by inundating our network with a high volume of SYN packets. These packets initiated the 3-way handshake but were not followed by the expected ACK responses, resulting in incomplete handshakes. The attacker aimed to exhaust our network resources, causing disruptions and potentially leading to a denial of service.
## What Happened During the Incident:

**Identification Through Packet Analysis:**
Abnormalities in TCP streams were observed in the pcap file. Filters targeting SYN packets and incomplete handshakes revealed a significant increase in traffic, signaling a potential attack. Unusually low time intervals between packets indicated a large number of requests in a short timeframe. TCP spurious transmissions and dup ACKs highlighted network congestion, likely induced by the SYN Flood Attack.
1. **Abnormalities in TCP Streams:**
   A comprehensive analysis of the pcap file revealed abnormalities in TCP streams, particularly an influx of SYN packets. Filters targeting SYN packets and incomplete handshakes highlighted a significant increase in traffic, indicating a potential attack.

2. **Sudden Increase in CPU Consumption:**
   There was a sudden peak during the attack, and a lot of resources were utilized. This was probably done to overload the CPU.
<img src="https://i.imgur.com/5QLrFcr.png" height="65%" width="65%" alt="Disk Sanitization Steps"/>

3. **Wireshark Analysis and Filter Usage:**
   To analyze the incident, our Incident Responders used Wireshark and the filter `tcp.flags.syn==1 && tcp.flags.ack==0`. This filter is designed to capture TCP packets that are part of the 3-way handshake. Missing a proper 3-way handshake can indicate a potential SYN Flood Attack. In fact, we observed numerous synchronization packets but found no sign of a complete handshake in the below image.
<img src="https://i.imgur.com/MxOminx.png" height="65%" width="65%" alt="Disk Sanitization Steps"/>
4. <b>Suspicious Time Interval of Packet Arrival:</b>
   According to incident responders, the time interval in which the packets are arriving is suspiciously low. This indicates an extremely large number of requests occurring in a brief interval of time, which is highly unusual and indicative of a potential attack.
<img src="https://i.imgur.com/reblTbv.png" height="30%" width="30%" alt="Disk Sanitization Steps"/>

5. **Observations on TCP Spurious Transmission and dup ACK:**
   Incident responders also observed an increase in "TCP Spurious Transmission," where the receiver is receiving a retransmitted segment even before the ACK packet is sent. This can be an indicator of a SYN Flood Attack. The below screenshot also highlights "TCP dup ACK," showing the arrival of multiple ACK packets. This is usually attributed to network congestion or packet loss, further indicating a potential SYN Flood Attack.
<img src="https://i.imgur.com/seB1sBv.png" height="65%" width="65%" alt="Disk Sanitization Steps"/>

<h2>Specific Actions Aligned with NIST:</h2>

1. **Identify (NIST Phase 1):**
   - Conduct Risk Assessment: Identify potential DDoS vulnerabilities in the existing network infrastructure.
   - Assess the impact of a SYN Flood Attack on critical systems and services.
   - Technical View on the Incident: Analyze packet captures (pcap file) to identify patterns of SYN Flood Attack. Use network monitoring tools to recognize abnormal traffic patterns.
2. **Protect (NIST Phase 2):**
   - Implement DDoS Mitigation Solutions: Deploy firewalls with SYN flood protection capabilities.
   - Utilize load balancers to distribute incoming traffic and prevent resource exhaustion. Consider implementing DDoS protection services, including cloud-based solutions.
   - Network Architecture Review: Assess and enhance the scalability and resilience of the current network architecture. Identify and address potential bottlenecks that could be exploited in future attacks.
3. **Detect (NIST Phase 3):**
   - Monitor Network Traffic: Utilize intrusion detection systems (IDS) to detect anomalies and potential DDoS attacks. Implement traffic analysis tools to identify unusual patterns in network communication.

4. **Respond (NIST Phase 4):**
   - Activate Incident Response Plan: Execute predefined incident response steps to minimize damage during the attack.
   - Adjust firewall settings to filter and block malicious traffic effectively.
   - Traffic Filtering and Rate Limiting: Apply filters to identify and block malicious SYN packets. Implement rate limiting mechanisms to control the number of connection requests from a single source.

5. **Recover (NIST Phase 5):**
   - Post-Incident Analysis: Conduct a thorough analysis of the incident to enhance future DDoS preparedness. Identify areas of improvement in the incident response plan for better resilience.

<h2>Short Term Remidiations</h2>

1. **Incident Response Activation:**
   The incident was escalated to the Incident Response Team Manager for further investigation. Immediate monitoring and logging of network activities were initiated to contain the impact. Emergency measures, such as adjusting firewall settings to filter malicious traffic, were implemented to mitigate ongoing risks.

2. **Traffic Filtering and Rate Limiting:**
   Filters were applied to the network to identify and block malicious SYN packets. Rate limiting mechanisms were deployed to restrict the number of connection requests from a single source, mitigating the impact of the attack.

<h2>Long-Term Remediations Needed for the Roadmap:</h2>

1. **Network Architecture Review:**
   Evaluate and enhance the scalability and resilience of our network architecture to better withstand volumetric attacks.

2. **Intrusion Prevention Systems (IPS):**
   Implement or enhance IPS to detect and block malicious network activities in real-time.

3. **Distributed Denial of Service (DDoS) Mitigation Plan:**
   Develop a comprehensive DDoS mitigation plan to ensure timely and effective responses to various types of attacks.

4. **Regular Security Audits and Training:**
   Conduct regular security audits to identify vulnerabilities and weaknesses. Provide ongoing cybersecurity training to employees to enhance awareness and response capabilities.

<h2>Insurance and Breach Notification Considerations: </h2>

### Insurance Claim:
- A claim should be made to the cyber insurance provider due to the severity of the SYN Flood Attack.
- Costs associated with incident response, system recovery, and potential business disruptions may be covered.

<h2>Breach Notification</h2>

### Breach Notification:
- A breach notification may be necessary if the attack resulted in unauthorized access, data compromise, or service disruptions affecting customers.
- Consult legal counsel to determine compliance with relevant data protection regulations and contractual obligations.
- Timely communication with affected parties is crucial for transparency and trust restoration.

### References:
1. Goss, A. (2023, December 12). How to use Wireshark to capture network traffic (2024). StationX. [Link](https://www.stationx.net/how-to-use-wireshark-to-capture-network-traffic/)

2. Increase AWS visibility & improve cloud security - Red Canary. (2023, December 8). Red Canary. [Link](https://redcanary.com/resources/guides/aws-visibility-cloud-security/?_bt=684688588777&_bk=cloud%20data%20security&_bm=b&_bn=g&_bg=158423595964&gad_source=1&gclid=CjwKCAiA1fqrBhA1EiwAMU5m_35WuIiV-55OPvUGPrJqCZC1TSS7a3RQK4LgRvGUNN5ZQHZ9xLZqHhoCALIQAvD_BwE)

3. Wikipedia contributors. (2023b, December 15). Denial-of-service attack. Wikipedia. [Link](https://en.wikipedia.org/wiki/Denial-of-service_attack)

<h1>© Hammaz Ahmed 2024. All rights reserved.
</h1>
