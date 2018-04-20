Cost Reporter
=============

[This utility was written by FittedCloud](https://www.fittedcloud.com)

For more information about the software, see the blog post:

[An Open Source tool using AWS Cost Explorer APIs for Reporting AWS Costs](https://www.fittedcloud.com/blog/open-source-tool-reporting-aws-costs/)


Installation:
-------------
```
virtualenv -p python3 venv
source venv/bin/activate
pip install -r requirements.txt
```

Quick Start:
------------
```
$ python costreporter.py -a <aws access key> -s <aws secret key> -t <start-time as, YYYY-MM-DD>,<end-time as YYYY-MM-DD>
$ python costreporter.py -p <profile name> -t <start-time as, YYYY-MM-DD>,<end-time as YYYY-MM-DD>
```

For more information about options:
```
costreporter.py <options>
	Options are:

	--help - Display this help message
	-p --profile <profile name> - AWS profile name (can be used instead of -a and -s options)
	-a --accesskey <access key> - AWS access key
	-s --secretkey <secret key> - AWS secret key
	-r --regions <region1,region2,...> - A list of AWS regions.  If this option is omitted, all regions will be checked.
	-t --timerange - Time range as <start,end> time in format <YYYY-MM-DD>,<YYYY-MM-DD>
	-j --json - Output in JSON format.
	-c --csv - Output as CSV.  Not compatible with --json.
	-d --dimension <dimension> - Group output by dimension (examples: 'AZ','INSTANCE_TYPE','LINKED_ACCOUNT','OPERATION','PURCHASE_TYPE','REGION','SERVICE','USAGE_TYPE','USAGE_TYPE_GROUP','RECORD_TYPE','OPERATING_SYSTEM','TENANCY','SCOPE','PLATFORM','SUBSCRIPTION_ID','LEGAL_ENTITY_NAME','DEPLOYMENT_OPTION','DATABASE_ENGINE','CACHE_ENGINE','INSTANCE_TYPE_FAMILY')
	-g --tag <tag name> - Group by tag name (list of names in format Tag1,Tag2,...,TagN).
	-i --interval <interval> - Dumps stats at <interval> granularity.  Valid values are MONTHLY (default) and DAILY.	One of the following three parameters are required:
		1. Both the -a and -s options.
		2. The -p option.
		3. A valid AWS_DEFAULT_PROFILE environment variable.

	Depending on the number of EBS volumes being analyzed, this tool may take several minutes to run.
```
