# bbscope
The ultimate scope gathering tool for HackerOne, Bugcrowd and Intigriti by sw33tLie.

## Install
```
GO111MODULE=on go get github.com/sw33tLie/bbscope
```

## Usage
```
bbscope (h1|bc|it) -t <session-token> <other flags>
```
How to get the session token:
- HackerOne: login, then grab the __Host-session cookie
- Bugcrowd: login, then grab the _crowdcontrol_session cookie
- Intigriti: login, then intercept a request to api.intigriti.com and look for the `Authentication: Bearer XXX` header. XXX is your token

## Flags

HackerOne:
```
$ bbscope h1 --help

  -b, --bbpOnly             Only fetch programs offering monetary rewards
  -c, --categories string   Scope categories, comma separated (Available: all, url, cidr, mobile, android, apple, other, hardware, code) (default "all")
  -h, --help                help for h1
  -p, --pvtOnly             Only fetch data from private programs
  -t, --token string        HackerOne session token (__Host-session cookie)
  -u, --urlsToo             Also print the program URL (on each line)
```
Bugcrowd:
```
$ bbscope bc --help

  -b, --bbpOnly             Only fetch programs offering monetary rewards
  -c, --categories string   Scope categories, comma separated (Available: all, url, api, mobile, android, apple, other, hardware) (default "all")
      --concurrency int     Concurrency (default 2)
  -h, --help                help for bc
  -l, --list                List programs instead of grabbing their scope
  -p, --pvtOnly             Only fetch data from private programs
  -t, --token string        Bugcrowd session token (_crowdcontrol_session cookie)
  -u, --urlsToo             Also print the program URL (on each line)
```

Intigriti:
```
$ bbscope it --help

  -b, --bbpOnly             Only fetch programs offering monetary rewards
  -c, --categories string   Scope categories, comma separated (Available: all, url, cidr, mobile, android, apple, device, other) (default "all")
  -h, --help                help for it
  -l, --list                List programs instead of grabbing their scope
  -p, --pvtOnly             Only fetch data from private programs
  -t, --token string        Intigriti Authentication Bearer Token (From api.intigriti.com)
  -u, --urlsToo             Also print the program URL (on each line)
```
