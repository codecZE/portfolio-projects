# Network Traffic Analysis & NIDS Engineering

## Snort Custom Rule Setup
Rule definition in `/etc/snort/rules/local.rules`:
```text
alert tcp any any -> $HOME_NET any (msg:"SUSPICIOUS TCP SYN Scan Detected"; flags:S,12; threshold:type threshold, track by_src, count 20, seconds 5; sid:1000001; rev:1;)
```

## Console Verification
Executing Snort on pcap trace:
```bash
snort -c /etc/snort/snort.conf -r syn_scan.pcap -A console
```
*Outcome:* Generated real-time alerts matching SID 1000001 upon detecting 20+ SYN packets sent without establishing full TCP handshakes.

## Zeek HTTP Protocol Analysis
Parsing HTTP connection logs (`http.log`):
```bash
zeek-cut id.orig_h id.resp_h host uri user_agent < http.log | grep -E "beacon|c2"
```
*Findings:* Identified outbound traffic to external remote host `203.0.113.50` every 60 seconds with non-standard minimal User-Agent string.
