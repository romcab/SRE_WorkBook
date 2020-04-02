# SRE_WorkBook
A brief summary of the SRE workbook by Google

	- Foreword by Andrew Clay Shafer
		○ Dev and ops can and should work together
		○ System administration will become like software development
		○ CAMS for Culture, Automation, Metrics, and Sharing
		○ I consider DevOps a loose generic set of principles and SRE an advanced explicit implementation
		○ Learning isn’t collecting information. Learning is changing behavior
	- How SRE Relates to DevOps
		○ class SRE implements interface DevOps
		○ DevOps is a loose set of practices, guidelines, and culture designed to break down silos in IT development, operations, networking, and security. Articulated by John Willis, Damon Edwards, and Jez Humble, CA(L)MS—which stands for Culture, Automation, Lean (as in Lean management; also see continuous delivery), Measurement, and Sharing—is a useful acronym for remembering the key points of DevOps philosophy. 
	- Background on SRE
		○ SRE Principles
			§ Operations is a software problem
			§ Manage by SLO
			§ Work to minimize Toil
			§ Automate
				□ Google's hard limit 50%
			§ Move fast by reducing cost of failures
				□ Reduced mean time to repair (MTTR)
			§ Share ownership with dev
				□ In general, an SRE has particular expertise around the availability, latency, performance, efficiency, change management, monitoring, emergency response, and capacity planning of the service(s) they are looking after
			§ Use the same tooling regardless of job title, funcation
		○ Implementing SLOs
			§ Why sre's need slo
				□ SLOs are a tool to help determine what engineering work to prioritize
			§ SLI - service level indicator
			§ What to measure
				□ # of http req/total of http (success rate)
			§ Reliability Targets and Error Budgets
				□ Identify slo and what it covers
				□ SLO is a target percentage and the error budget is 100% minus the SLO.
				□ Create alerting tool for SLI
			§ SLI can use the following sources
				□ Application server Logs
				□ Load balancer monitoring
				□ Black-box monitoring
				□ Client-side instrumentation
			§ Dashboard and Reports for SLO Compliance
			§ Summary
				□ SLOs are the tool by which you measure your service’s reliability.
				□ Error budgets are a tool for balancing reliability with other engineering work, and a great way to decide which projects will have the most impact.
		○ SLO Engineering Case Studies
		○ Monitoring
			§ metrics, text logging, structured event logging, distributed tracing, and event introspection
			§ SRE's focus is structured logging and metrics
			§ Why monitor
				□ Alert on conditions that require attention.
				□ Investigate and diagnose those issues.
				□ Display information about the system visually.
				□ Gain insight into trends in resource usage or service health for long-term planning.
				□ Compare the behavior of the system before and after a change, or between two groups in an experiment.
			§ Desirable features of monitoring system
				□ Speed
				□ Calculations
				□ Interfaces
				□ Alerts
			§ Tools
				□ Prometheus
				□ Influxdb
				□ Alert manager
				□ Grafana
				□ Statsd + prometheus
		○ Alerting on SLO's
		○ Eliminating TOIL
			§ toil as the repetitive, predictable, constant stream of tasks related to maintaining a service
		○ Simplicity
			§ Simplicity is a natural goal for SREs because simple systems tend to be reliable and easy to run
			§ As an SRE, pushing for simplicity is an important part of your job description
		○ Introducing Non-Abstract Large System Design
			§ reliability to be the most critical feature of any production system
			§ NALSD combines elements of capacity planning, component isolation, and graceful system degradation that are crucial to highly available production systems
			§ Design Process
				□ Is it possible?
				□ Can we do better?
				□ Is it feasible?
					® Is it possible to scale this design, given constraints on money, hardware, and so on? If necessary, what distributed design would satisfy the requirements?
				□ Is it resilient?
			§ Initial Requirements
				□ Produces SLO
			§ One machine
				□ The simplest starting point is to consider running our entire application on a single computer.
		○ Data Processing Pipeline
			§ Data processing is a complex field that’s constantly evolving to meet the demands of larger data sets, intensive data transformations, and a desire for fast, reliable, and inexpensive results.
The Extract Transform Load (ETL) model is a common paradigm in data processing: data is extracted from a source, transformed, and possibly denormalized, and then “reloaded” into a specialized format
