# ja3box

<img src="/pics/logo.png" width="500">

extract ja3 when sniffing or from a pcap (or pcapng ...).

about ja3(s): 
1. https://engineering.salesforce.com/tls-fingerprinting-with-ja3-and-ja3s-247362855967
2. https://xz.aliyun.com/t/3889

理论上支持 TLS/SSL 全版本提取（未全部测试，如有问题请提交 issue）

## Env

1. `pip install scapy`
2. `pip install colorama`
2. py3.x
3. macos or linux, maybe windows
4. run as root when in the online mode

## Example
> online mode

`sudo python ja3box.py -i en0`

<img src="/pics/online.png" width="600">

> offline mode

`sudo python ja3box.py -f test.pcap`

<img src="/pics/offline.png" width="600">

> output json

`sudo python ja3box.py -i en0 --json`

<img src="/pics/output-json.png">

> save json to file

`sudo python ja3box.py -i en0 -of test.json --json`

<img src="/pics/output-json-to-file.png" width="600">

### more
```
» sudo python ja3box.py -h
usage: ja3box.py [-h] [-i I] [-f F] [-of OF] [-bpf BPF] [--json] [--savepcap]
                 [-pf PF]

Version: 1.0; Running in Py3.x

optional arguments:
  -h, --help  show this help message and exit
  -i I        the interface you want to use
  -f F        local pcap filename(in the offline mode)
  -of OF      print result to? (default: stdout)
  -bpf BPF    yes, it is BPF
  --json      print result as json
  --savepcap  save the raw pcap
  -pf PF      eg. `-pf test`: save the raw pcap as test.pcap

```

