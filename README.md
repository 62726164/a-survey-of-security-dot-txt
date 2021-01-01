# ssdt - Survey security.txt files

A survey of [security.txt](https://tools.ietf.org/html/draft-foudil-securitytxt-10) files found on the Alexa Top 1 Million websites.

```bash
{"website" ["contacts"] "expires"}
{"github.com" ["https://hackerone.com/github"] ""}
{"google.com" ["https://g.co/vulnz" "mailto:security@google.com"] ""}
{"facebook.com" ["https://www.facebook.com/whitehat/report/"] ""}
{"linkedin.com" ["mailto:security@linkedin.com" "https://www.linkedin.com/help/linkedin/answer/62924"] ""}
{"cloudflare.com" ["https://hackerone.com/cloudflare" "mailto:security@cloudflare.com" "https://www.cloudflare.com/abuse/"] "sat, 20 mar 2021 13:24:05 -0700"}
```

## Build the program

```bash
$ make
```

## Run the program

```bash
$ ./ssdt -hosts top-1m-alexa.csv 2> err.txt > out.txt
```

## Remove invalid security.txt entries

```bash
$ grep -v "\[\]" out.txt
```

## Count results

```bash
$ grep -v "\[\]" out.txt | wc -l
```
## Notes

  * You may need to adjust the nofile limit in /etc/security/limits.conf
  * Read my [blog post](https://www.go350.com/posts/a-survey-of-security-dot-txt/) about why I wrote this.
