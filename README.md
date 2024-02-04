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

| Aspect                  | Details                                                                                      |
|-------------------------|----------------------------------------------------------------------------------------------|
| Incident Type           | DDoS (SYN Flood Attack)                                                                    |
| Attack Methods          | 1. Volumetric Attacks: Overwhelming network bandwidth.                                        |
|                         | 2. Application Layer Attacks: Targeting specific applications or services.                   |
|                         | 3. Protocol Attacks: Exploiting vulnerabilities in network protocols.                         |
| Compromised Information  | No direct compromise of information; focus on service disruption.                               |
| Impact                  | 1. Service Disruption: Website and online services unavailable.                               |
|                         | 2. Loss of Revenue: Inability to conduct business.                                            |
|                         | 3. Reputational Damage: Customer trust may be affected.                                       |
| Short-Term Remediations  | 1. Traffic Filtering: Identifying and blocking malicious traffic.                              |
|                         | 2. Load Balancing: Distributing incoming traffic to maintain availability.                    |
|                         | 3. Cloud-based DDoS Protection: Leveraging specialized services.                               |
| NIST Framework Phases   | 1. Identify: Recognize and understand the DDoS threat.                                        |
|                         | 2. Protect: Implement measures to safeguard against DDoS attacks.                              |
|                         | 3. Detect: Monitor network and system activities for signs of DDoS.                            |
|                         | 4. Respond: Execute an incident response plan when an attack occurs.                            |
|                         | 5. Recover: Restore services and analyze the incident for improvements.                         |

	

