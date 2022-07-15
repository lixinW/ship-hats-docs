# Automated Testing

Refer to [pCloudy CLI](pcloudy-cli) tool to get started with mobile automated testing.

If you need technical assistance on connecting to pcloudy devices, please raise a service request [here](https://jira.ship.gov.sg/servicedesk/customer/portal/11/create/149).

### Usage of Pabot

Pabot allows parallel execution of tests. However, there is a known issue where the path of the embedded screenshots in the log file does not align with the filepath of the screenshots taken when tests fail. They are stored under the `pabot_results/` folder instead.

We strongly encourage you to use Robot Framework i.e. `robot` command, where the screenshots are well embedded into the HTML report generated.


[pCloudy CLI](pcloudy-cli.md ':include')

