### 1. List some logging and visualization tools available in the market with the preferred senario to use one over other.
-> They are<br/>
 1.ELK Stack<br/>
   The ELK Stack is a collection of three open-source products — Elasticsearch, Logstash, and Kibana. ELK stack provides centralized logging in order to identify problems with servers or applications. It allows you to search all the logs in a single place. It also helps to find issues in multiple servers by connecting logs during a specific time frame.<br/>
 2.SolarWinds Papertrail<br/>
   SolarWinds Papertrail is a hosted log management tool designed to help you collect and monitor logs from your servers, applications, databases, networking devices, syslog, cloud, and more.<br/>
 3.LogDNA<br/>
   LogDNA is a highly scalable log management and analytics solution designed to help you get quick results for your search queries even when handling massive log volumes. It can auto-parse your incoming logs and offers intelligent alert features.<br/>
 4.Graylog<br/>
   Graylog offers free (open-source) and paid (enterprise) versions of its log monitoring software with advanced log analytics features. This powerful tool makes it possible to monitor large and complex IT environments with logs.<br/>
 5.LogFusion<br/>
   LogFusion is another real-time log monitoring tool popular among IT and software development teams. It allows you to tail logs for a view of your live environment. This tool can read text log files from a wide range of supported log formats, covering all common server and application debug logs.
 6.Netwrix Event Log Manager<br/>
   Tool to monitor Windows event logs in an enterprise network, the native event viewer might not be able to serve your purpose because it shows logs on the computer where it’s installed. This is where Netwrix Event Log Manager can help.<br/>
 7.XpoLog<br/>
   XpoLog is an advanced log monitoring tool designed to collect log data in your distributed IT environment from a wide range of servers, applications, and services. Its automated log parsing and tagging, its smart indexing, and its faster search can help you quickly pinpoint issues and bottlenecks. <br/>
 8.Sumo Logic<br/>
   Sumo Logic is a cloud-based solution offering a comprehensive set of log monitoring and analytics features. <br/>
----------------------------------------------------------------------------<br/>
### 2. Mention 10 best practises when logging. Why is log formatting necessary?
-> 10 best practises are:<br/>
 1.Log at the Proper Level<br/>
   Use a different log level per log statement in your application.<br/>
 2.Write Meaningful Log Messages<br/>
   This might probably be the most important best practice. There’s nothing worse than cryptic log entries assuming you have a deep understanding of the program internals.<br/>
 3.Add Context to Your Log Messages<br/>
   Without proper context,those messages are only noise, they don’t add value and consume space that could have been useful during troubleshooting.<br/>
 4.Log in Machine Parseable Format<br/>
   Log entries are really good for humans but very poor for machines. Sometimes it is not enough to manually read log files, you need to perform some automated processing (for instance for alerting or auditing). <br/>
 5.Don’t Log Too Much or Too Little<br/>
   Too much log and it will really become hard to get any value from it. When manually browsing such logs, there is too much clutter which when trying to troubleshoot a production issue at 3AM is not a good thing.Too little log and you risk to not be able to troubleshoot problems: troubleshooting is like solving a difficult puzzle, you need to get enough material for this.<br/>
 6.Don’t Log Sensitive Information<br/>
   First, the obvious bits. Make sure you never log:<br/>
    Passwords<br/>
    Credit card numbers<br/>
    Social security numbers<br/>
 7.Log in JSON<br/>
   Log and look at the data manually in a file or the standard output then the planned logging will be more than fine.<br/>
 8.Keep the Log Structure Consistent<br/>
   The structure of your log events should be consistent. This is not only true within a single application or set of microservices, but should be applied across your whole application stack.  <br/>
 9.Keep the Audience in Mind<br/>
   The developer may be looking at the logs for troubleshooting or during debugging sessions. For such people, logs can be detailed, technical, and include very deep information related to how the system is running. Such a person will also have access to the code or will even know the code and you can assume that.<br/>
 10.Use a Log Management Solution to Centralize & Monito<br/>
   when the amount of data grows it quickly becomes difficult and slow to troubleshoot this way When this happens, consider using a log management solution to centralize and monitor your logs<br/>
   
Log formatting is crucial to achieving readable log files.The main problem with log files, and the need for a structured format, is that they are typically unstructured text data, making it difficult to query the logs for any useful information. A log format is a structured format that allows logs to be machine-readable and easily parsed. This is the power of using structured logs and a log management system that supports them. The ability to translate raw data into something immediately comprehensible and easy to read is one of the must-have features of log management software.
