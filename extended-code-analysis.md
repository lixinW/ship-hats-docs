**Extended Code Analysis (XCA)** is an integrated tool in SHIP-HATS 2.0 that helps developers detect repeated source code vulnerabilities.

Developed by GovTech’s Cyber Security Group (CSG) , XCA is integrated and enabled for all SHIP-HATS 2.0 GitLab tenants. It helps to detect and prevent repeated vulnerabilities at scale through SHIP-HATS 2.0 GitLab repositories. Individual projects benefit from XCA scans with no additional configuration required.

## Integration with GitLab

XCA is designed to operate alongside other code scanning solutions and is deeply integrated with GitLab’s-native features. You can interact with XCA findings through the GitLab UI.

## XCA vs GitLab vs FOD

XCA augments existing code scanning solutions, such as GitLab SAST and Fortify-on-Demand SAST. While GitLab SAST and Fortify-on-Demand SAST provides generic rulesets to identify vulnerabilities, XCA provides custom rules based on past vulnerabilities and targets specific, known vulnerable code patterns with a high true positive rate instead of general code hygiene or potential vulnerabilities.


## FAQs

?>**Tip:** Click the triangle to view the answer.

<details>
  <summary style="font-size:20px"><b> Where can I access Security Vulnerabilities?	</b></summary><br>

### To access Security Vulnerabilities:
1. Navigate to the **Default** branch of your project.
1. In the left navigation, click **Security & Compliance** > **Vulnerability report**.
    
    XCA findings are marked as **XCA** under the **Identifier** and **Tool** columns.

</details>

---

<details>
  <summary style="font-size:20px"><b>Is XCA meant to replace my primary code-scanning solution? </b></summary><br>

No. XCA augments existing code scanning solutions. XCA provides custom rules based on past vulnerabilities that may not be available in generic default rulesets. Therefore, it targets specific, known vulnerable code patterns with a high true positive rate instead of general code hygiene or potential vulnerabilities.

</details>

---

<details>
  <summary style="font-size:20px"><b>Where can I find more information on XCA? </b></summary><br>

You can read more on XCA via the following resources:
- [XCA Rules](https://sgts.gitlab-dedicated.com/wog/gvt/acpd/RNI/XCA/XCA-rules) 
- [XCA CI - GitLab documentation](https://docs.gitlab.com/ee/user/admin_area/settings/continuous_integration.html#required-pipeline-configuration)
</details>

---


<details>
  <summary style="font-size:20px"><b>How can I activate or enable XCA? </b></summary><br>

XCA is integrated and enabled for all SHIP-HATS 2.0 GitLab tenants by default. No additional steps are required to activate or enable XCA.

---
<!--

## Components

XCA comprises of the following components:

- **XCA Rules:** custom rules written by Cybersecurity Group (CSG) cybersecurity specialists as well as developers across government.
- **XCA CI:** a required pipeline configuration that incorporates XCA scanning job transparently into all SHIP-HATS 2.0 GitLab pipelines which triggers an XCA scan on all new merge requests.

XCA augments existing code scans such as GitLab SAST, Fortify Source Code Analyzer (SCA), and Synk: XCA provides custom rules, crafted based on insecure code patterns identified through vulnerabilities discovered by CSG’s security testing and vulnerability disclosures and are not available in default rulesets by other code scanning solutions. 

XCA help detect and prevent repeated vulnerabilities at scale through SHIP-HATS 2.0 GitLab repositories: individual projects benefit from XCA scans with no additional configuration. 

## How it works?

XCA CI pipeline pulls an image that is pre-loaded with XCA Rules and invokes Semgrep: the scan output is formatted in GitLab’s SAST report schema which is seamlessly shown in GitLab’s built-in Vulnerability Report and Merge Request widgets.

## Why to use this? 

- **Scan your applications’ code for repeated vulnerabilities:** tap on CSG’s experience from multiple security tests and vulnerability disclosures to identify similar vulnerable code patterns in your applications.

- **High confidence rules:** XCA Rules are carefully crafted and curated by CSG, with strict quality tests to ensure a high true-positive rate of detected issues. Teams can therefore focus on remediating XCA findings over generic rulesets used by other general SAST solutions.

- **Agile ruleset:** XCA Rules are InnerSourced on SHIP-HATS 2.0 GitLab and welcomes contributions from developers and cybersecurity specialists. Contributed rules go through the same rigor of quality tests, which weeds out low confidence rules or improve a contributed rules’ quality.

- **Seamless Integration:** XCA is designed to operate alongside other code scanning solutions and is deeply integrated with GitLab’s-native features. Teams can interact with XCA findings through familiar GitLab UI, as with all other GitLab built-in tools.


## How to access? 


## Additional resources

-->