#### Memory utilization

```
tuttu@Tuttu:/var/log/sysstat$ sar -t -r -f sa04
Linux 5.13.0-51-generic (Tuttu) 	04/07/22 	_x86_64_	(4 CPU)

10:46:25 AM IST  LINUX RESTART	(4 CPU)

10:48:00 AM IST kbmemfree   kbavail kbmemused  %memused kbbuffers  kbcached  kbcommit   %commit  kbactive   kbinact   kbdirty
10:50:01 AM IST    967832   2712424    748792     19.09     73444   1973916   4321324     71.79    796348   1782564      1012
10:52:02 AM IST    318636   2278172   1074836     27.41     83196   2270064   5972148     99.22    942016   2221360     12436
10:54:01 AM IST    319828   2282904   1094204     27.90     83932   2248552   5790896     96.21    945248   2235524       676
10:55:01 AM IST    334976   2298808   1088276     27.75     84172   2238344   5772056     95.89    945496   2226776       408
```
#### Process queue and load

```
tuttu@Tuttu:/var/log/sysstat$ sar -t -q -f sa04
Linux 5.13.0-51-generic (Tuttu) 	04/07/22 	_x86_64_	(4 CPU)

10:46:25 AM IST  LINUX RESTART	(4 CPU)

10:48:00 AM IST   runq-sz  plist-sz   ldavg-1   ldavg-5  ldavg-15   blocked
10:50:01 AM IST         1       560      2.39      2.40      1.17         0
10:52:02 AM IST         1       679      2.38      2.61      1.41         0
10:54:01 AM IST         0       658      1.04      2.01      1.33         0
10:55:01 AM IST         0       649      1.22      1.89      1.33         1
10:56:01 AM IST         0       651      1.14      1.75      1.32         0
10:58:01 AM IST         0       669      1.22      1.61      1.32         1
11:00:01 AM IST         0       665      1.12      1.45      1.29         1
```

#### Paging

```
tuttu@Tuttu:/var/log/sysstat$ sar -t -B -f sa04
Linux 5.13.0-51-generic (Tuttu) 	04/07/22 	_x86_64_	(4 CPU)

10:46:25 AM IST  LINUX RESTART	(4 CPU)

10:48:00 AM IST  pgpgin/s pgpgout/s   fault/s  majflt/s  pgfree/s pgscank/s pgscand/s pgsteal/s    %vmeff
10:50:01 AM IST   6146.74   1448.35   7713.12      9.51   8487.10      0.00      0.00      0.00      0.00
10:52:02 AM IST   2273.41    586.99   5669.88     13.41  10655.07    270.10      0.00    463.10    171.46
10:54:01 AM IST      5.39    213.64   1218.32      0.05   2948.97      0.00      0.00      0.00      0.00
10:55:01 AM IST      0.00    509.78    462.96      0.00   1157.34      0.00      0.00      0.00      0.00
10:56:01 AM IST      0.33     41.25    108.70      0.00    559.96      0.00      0.00      0.00      0.00
```

#### Swap writing

```
tuttu@Tuttu:/var/log/sysstat$ sar -t -W -f  sa04
Linux 5.13.0-51-generic (Tuttu) 	04/07/22 	_x86_64_	(4 CPU)

10:46:25 AM IST  LINUX RESTART	(4 CPU)

10:48:00 AM IST  pswpin/s pswpout/s
10:50:01 AM IST      0.00      0.00
10:52:02 AM IST      0.00      0.00
10:54:01 AM IST      0.00      0.00
10:55:01 AM IST      0.00      0.00
10:56:01 AM IST      0.00      0.00
10:58:01 AM IST      0.00      0.00
11:00:01 AM IST      0.00      0.00
11:02:01 AM IST      0.00      0.00
11:04:01 AM IST      0.00      0.00
11:05:01 AM IST      0.00      0.00
```

#### Swap statistics

```
tuttu@Tuttu:/var/log/sysstat$ sar -t -S -f sa04
Linux 5.13.0-51-generic (Tuttu) 	04/07/22 	_x86_64_	(4 CPU)

10:46:25 AM IST  LINUX RESTART	(4 CPU)

10:48:00 AM IST kbswpfree kbswpused  %swpused  kbswpcad   %swpcad
10:50:01 AM IST   2097148         0      0.00         0      0.00
10:52:02 AM IST   2097148         0      0.00         0      0.00
10:54:01 AM IST   2097148         0      0.00         0      0.00
10:55:01 AM IST   2097148         0      0.00         0      0.00
10:56:01 AM IST   2097148         0      0.00         0      0.00
10:58:01 AM IST   2097148         0      0.00         0      0.00
11:00:01 AM IST   2097148         0      0.00         0      0.00
11:02:01 AM IST   2097148         0      0.00         0      0.00
11:04:01 AM IST   2097148         0      0.00         0      0.000
```

|  Option  | Description|
---------|-----------
-f   |  Extract records from filename 
-t |  When reading data from a daily data file, indicate that sar should display the timestamps in the original locale time of the data file creator. Without this option, the sar command displays the timestamps in the user's locale time.
-r |  Report memory utilization statistics. 
-q |  Report queue length and load averages.
-B  |  Report paging statistics.
-W |  Report swapping statistics.
-S   |  Report swap space utilization statistics. 
