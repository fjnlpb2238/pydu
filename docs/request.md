# Request

Utils for handling request.

## request.Filename

Supply several methods to get filename.

```python
Filename.from_url(url)
```

Detected filename as unicode or None.

```python
Filename.from_headers(headers)
```

Detect filename from Content-Disposition headers if present.
`headers` could be a dict, list or string.

```python
Filename.from_any(dst=None, headers=None, url=None)
```

Detect filename from dst or headers or url.


## request.download
```python
Filename.download(url, dst=None)
```

High level function, which downloads URL into tmp file in current
directory and then renames it to filename autodetected from either URL
or HTTP headers.
`url` indicates which url to download.
`dst` is the filename or directory of destination. `None` as default, means
download to current directory.


## request.check_connect
```python
check_connect(ip, port, retry=1, timeout=0.5)
```

Check whether given `ip` and `port` could connect or not.
It will `retry` and `timeout` on given.

```python
>>> from pydu.request import check_connect
>>> check_connect('http://www.baidu.com', 80)
'192.168.3.8'
```


## request.update_query_params
```python
update_query_params(url, params)
```

Update query params of given url and return new url.

```python
>>> from pydu.request import update_query_params
>>> update_query_params('http://example.com', {'foo': 1})
'http://example.com?foo=1'
```


## request.cookies_str_to_dict
```python
cookies_str_to_dict(cookies)
```

Convert cookies from str to dict.

```python
>>> from pydu.request import cookies_str_to_dict
>>> cookies_str_to_dict('a=a;b=b')
{'a': 'a', 'b': 'b'}
```
