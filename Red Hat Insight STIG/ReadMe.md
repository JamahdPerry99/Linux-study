  Hey everyone! I’ll be talking about how to implement STIG on a Linux environment using Red Hat Insights to remediate STIG findings.  
Big shoutout to my bro **Kyle** for helping me with this one!

As a consultant working with organizations that leverage RHEL, staying STIG compliant can be a daunting, manual process. Red Hat Insights offers an integrated, scalable, and automated way to manage compliance. Let’s talk about it!

# What is Red Hat Insights?

  **Red Hat Insights** is a security risk management solution built into RHEL subscriptions. It continuously analyzes registered systems to identify:

- Potential vulnerabilities  
- Configuration gaps  
- Most importantly, compliance gaps against industry standards

# Why STIGs Matter

  STIGs (Security Technical Implementation Guides) provide detailed configuration guidance to secure information systems within the DoD and other federal environments.

They are often required for Authorization to Operate (ATO) packages under frameworks such as NIST RMF and FedRAMP.

# How to streamline STIG with Red Hat Insights

  # 1. Compliance Policies and Baselines
 Red Hat Insights provides prebuilt security policies, including **DISA STIG for RHEL**. These baselines can be tailored to your organization's specific requirements.

  # 2. Automated Scanning and Continuous Monitoring
 Once policies are deployed, Insights continuously scans for deviations such as:

- File system permissions  
- Service configurations  
- Installed software versions  
- Kernel parameters  

Findings are categorized by severity and compliance status, providing a real-time view of STIG adherence.

  # 3. Remediation Guidance

  Each finding includes detailed remediation guidance. For scalable fixes, Ansible playbooks can be generated directly from the Red Hat Insights console.

  # 4. Audit Readiness and Reporting

  Use the compliance dashboard to visualize STIG coverage and gaps. Exportable reports support RMF control evidence and ongoing audit requirements.

![Alt Text](https://github.com/JamahdPerry99/Linux-study/blob/62e41be714fc02c56cc0550e26d9fe08ed5b24fe/Red%20Hat%20Insight%20STIG/Compliance%20dashboard.png)

  # 5. integration with OpenSCAP

  Red Hat Insights leverages OpenSCAP, the industry-standard tool for compliance scanning, meeting DoD expectations for automation and standardization.


 
# Quick Step by Step Guide to use STIG with Red Hat Insights

  # 1. Set Up Scap Policies in Insight

  Please follow the link below to Red Hat documentation that walks you through how to set your security policy.
        https://docs.redhat.com/en/documentation/red_hat_insights/1-latest/html/assessing_and_monitoring_security_policy_compliance_of_rhel_systems/compliance-managing-policies_intro-compliance

  # 2. Register the system with Red Hat Insight

        sudo subscription-manager register
        sudo subscription-manager attach --auto
        sudo insights-client --register

  # 3. Install the compliance Scanner on RHEL

This will install openscap.
        
        sudo dnf install scap-security-guide openscap-scanner -y

Once installed, ensure the insight-client package is installed:

        sudo dnf install insights-client -y


  # 4. Run a compliance scan with Red Hat Insights

  Once your policy is created and the system is registered:

        sudo insights-client --compliance

  # 5. View results


  ![Alt Text](https://github.com/JamahdPerry99/Linux-study/blob/ecd4d7a3cc71a9db9812b1cc36e27b39752a270b/Red%20Hat%20Insight%20STIG/STIG%20results.png)



  # Final Thoughts

  STIG compliance isn’t a one time task it’s a continuous process.

Red Hat Insights helps organizations shift from reactive security to proactive hardening.
If you're managing a fleet of RHEL systems in federal, defense, or regulated cloud environments, adopting Red Hat Insights is not just smart, it's essential.


