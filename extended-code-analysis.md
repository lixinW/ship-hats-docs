[**Extended Code Analysis (XCA)**](https://www.developer.tech.gov.sg/products/categories/cybersecurity/xca/overview.html) is an integrated tool in SHIP-HATS 2.0 that helps developers detect repeated source code vulnerabilities.

Developed by GovTech’s Cyber Security Group (CSG) , XCA is integrated and enabled for all SHIP-HATS 2.0 GitLab tenants. It helps to detect and prevent repeated vulnerabilities at scale through SHIP-HATS 2.0 GitLab repositories. Individual projects benefit from XCA scans with no additional configuration required.

## Integration with GitLab

XCA is designed to operate alongside other code scanning solutions and is deeply integrated with GitLab’s-native features. You can interact with XCA findings through the GitLab UI.

## XCA vs GitLab vs FOD

XCA augments existing code scanning solutions, such as GitLab SAST and Fortify-on-Demand SAST. While GitLab SAST and Fortify-on-Demand SAST provides generic rulesets to identify vulnerabilities, XCA provides custom rules based on past vulnerabilities and targets specific, known vulnerable code patterns with a high true positive rate instead of general code hygiene or potential vulnerabilities.

## Access Security Vulnerabilities

### To access Security Vulnerabilities

1. In GitLab, navigate to the **Default** branch of your project.
1. In the left navigation, click **Security & Compliance** > **Vulnerability report**.
    
    XCA findings are marked as **XCA** under the **Identifier** and **Tool** columns.

## Additional Resources

You can read more on XCA via the following resources:
- [Extended Code Analysis (XCA) Overview](https://www.developer.tech.gov.sg/products/categories/cybersecurity/xca/overview.html)
- [XCA Rules](https://sgts.gitlab-dedicated.com/wog/gvt/acpd/RNI/XCA/XCA-rules) 
- [XCA CI - GitLab documentation](https://docs.gitlab.com/ee/user/admin_area/settings/continuous_integration.html#required-pipeline-configuration)


## FAQs

?>**Tip:** Click the triangle to view the answer.

<details>
  <summary style="font-size:20px"><b>Is XCA meant to replace my primary code-scanning solution? </b></summary><br>

No. XCA augments existing code scanning solutions. XCA provides custom rules based on past vulnerabilities that may not be available in generic default rulesets. Therefore, it targets specific, known vulnerable code patterns with a high true positive rate instead of general code hygiene or potential vulnerabilities.

</details>

---

<details>
  <summary style="font-size:20px"><b>Where can I find more information on XCA? </b></summary><br>

You can read more on XCA via the following resources:
- [Extended Code Analysis (XCA) Overview](https://www.developer.tech.gov.sg/products/categories/cybersecurity/xca/overview.html)
- [XCA Rules](https://sgts.gitlab-dedicated.com/wog/gvt/acpd/RNI/XCA/XCA-rules) 
- [XCA CI - GitLab documentation](https://docs.gitlab.com/ee/user/admin_area/settings/continuous_integration.html#required-pipeline-configuration)
</details>

---

<details>
  <summary style="font-size:20px"><b>How can I activate or enable XCA? </b></summary><br>

XCA is integrated and enabled for all SHIP-HATS 2.0 GitLab tenants by default. No additional steps are required to activate or enable XCA. It is triggered in the `.pre` stage for the **Default** branch and for **Merge Request events**.
