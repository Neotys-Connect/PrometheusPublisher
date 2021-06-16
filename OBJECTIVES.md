*   Implementation
    *   Python
        *   [Publishing metrics via PushGateway](https://github.com/prometheus/client_python#exporting-to-a-pushgateway)
*   Deployment
    *   Containerized
    *   Service that
        *   P1: Which tests?
            *   Filter
            *   When matches
            *   Process each test at a time (maybe in parallel threads)
            *   Once test is done, report final
        *   For each test
            *   P1: service health check
            *   P1: Polls high-level metrics from [NLW REST APIs](https://neoload-rest.saas.neotys.com/explore/#/Results/GetTestResultStatistics) and pushes them to Prometheus; every 10s
                *   VU count (global)
                *   /statistics incl.
                    *   Req and Transaction
                        *   Success / Error (derive Total and Rates)
            *   P1: Which elements[transactions]?
                *   P1: Limit to top 5; prioritize by what?
                *   P1: Report [metrics] on Transactions
            *   P2: SLA
                *   Pass/fail
                *   Percent of fails
            *   Px: provide API endpoint for historically reporting by test-result id
