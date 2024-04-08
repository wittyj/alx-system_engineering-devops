0x19. Postmortem Task


Issue Summary:
Duration: The outage occurred from 10:00 AM to 12:30 PM West African Time (WAT) here in Nigeria(UTC) on March 15, 2024.
Impact: The primary impact was on the user authentication service, resulting in users being unable to log in to their accounts. Approximately 30% of users attempting to access the service were affected.
Root Cause: The root cause of the outage was identified as a misconfiguration in the authentication service's database connection settings.
Timeline:
10:00 AM (WAT): Issue detected by monitoring alert indicating increased error rates in user authentication requests.
10:05 AM: Engineering team notified of the issue through automated alerting system.
10:10 AM: Investigation initiated to identify the source of the error rates.
10:30 AM: Initial assumption made that the issue might be related to a recent code deployment.
10:45 AM: Code deployment logs reviewed, but no anomalies found.
11:00 AM: Focus shifted to database connectivity after observing errors related to database queries.
11:30 AM: Database administrator (DBA) team escalated the issue to investigate the database connection settings.
12:00 PM: Misconfigured database connection settings identified as the root cause of the issue.
12:15 PM: Configuration corrected, and authentication service restarted.
12:30 PM: Service fully restored, and error rates return to normal levels.
Root Cause and Resolution:
Root Cause: The issue stemmed from a misconfiguration in the authentication service's database connection pool settings. The database connection pool was set to a lower limit than required, causing connections to be exhausted during peak usage periods.
Resolution: The issue was resolved by adjusting the database connection pool settings to ensure an adequate number of connections were available. Additionally, monitoring and alerting thresholds were adjusted to provide early detection of similar issues in the future.
Corrective and Preventative Measures:
Improvements/Fixes:
Review and optimize database connection pool settings across all services to prevent similar issues.
Implement automated testing of database connection configurations as part of the deployment pipeline.
Enhance monitoring and alerting capabilities to provide more granular insights into database performance and connectivity issues.
Tasks:
Conduct a thorough review of all database connection settings across the infrastructure.
Implement automated tests to verify database connection configurations during deployments.
Enhance monitoring thresholds to trigger alerts based on database performance metrics.
Schedule regular reviews and updates of database connection settings to align with evolving usage patterns.
By addressing the root cause and implementing corrective and preventative measures, we aim to minimize the risk of similar outages in the future and ensure a more resilient and reliable user authentication service. But of course, it will never occur again, because we're programmers, and we never make errors! 😉


