# Managing JD Cloud OSS via S3cmd

## Introduction

S3cmd is a free command line tool client, used for uploading, retrieving and managing data on Amazon S3 and other cloud storage service providers (as JD Cloud OSS) using the S3 protocol. It is suitable to the senior users familiar with the command line program. It is also the ideal choice for batch processing of scripts and S3 automatic backup, and is triggered by cron, etc.

Customer scenario: API-level development and debugging

## Environment requirements

S3cmd environment requirement: S3cmd can run on Linux (Fedora, RedHat, SuSe, Ubuntu, Debian, etc.) and Apple MAC. Python 2.6 or higher revision is required. S3cmd version 2 also is compatible to Python 3.x.

Python revision view: Input python in the Linux shell environment and enter to view the Python version. The version is shown as follows:
```
Python 2.7.12 (default, Dec  4 2017, 14:50:18) 
[GCC 5.4.0 20160609] on linux2
Type "help", "copyright", "credits" or "license" for more information.
>>>
```
The python is successfully installed when the above indications are given. If the Python is not installed, it may obtain the Python installation package from the [official website of python](https://www.python.org/?spm=a2c4g.11186623.2.4.YmMQuB). Specific installation instructions on how to install and use Python are provided by the web service.

## Installation and usage

** Download S3cmd**
```
git clone https://github.com/s3tools/s3cmd.git
```
**Source code modification**

Use V4 signature rather than V2 signature, and log in the catalog below after downloading from https://github.com/s3tools/s3cmd.git.

File catalog: s3cmd/S3/S3.py, the 254th line is modified to be: self.endpoint_requires_signature_v4 = True

![](https://github.com/jdcloudcom/cn/blob/edit/image/Object-Storage-Service/OSS-091.png)

**S3cmd installation**
```
sudo cp -f s3cmd/ /usr/local/
sudo ln -s /usr/local/s3cmd/s3cmd /usr/bin/s3cmd
```

**Configuration file**

The configuration file is ~/.s3cfg and the content of used configuration file is as follows:
```
[default]
access_key = [you access key]
access_token = 
add_encoding_exts = 
add_headers = 
bucket_location = cn
ca_certs_file = 
cache_file = 
check_ssl_certificate = True
check_ssl_hostname = True
cloudfront_host = cloudfront.amazonaws.com
default_mime_type = binary/octet-stream
delay_updates = False
delete_after = False
delete_after_fetch = False
delete_removed = False
dry_run = False
enable_multipart = True
encrypt = False
expiry_date = 
expiry_days = 
expiry_prefix = 
follow_symlinks = False
force = False
get_continue = False
gpg_command = /usr/bin/gpg
gpg_decrypt = %(gpg_command)s -d --verbose --no-use-agent --batch --yes --passphrase-fd %(passphrase_fd)s -o %(output_file)s %(input_file)s
gpg_encrypt = %(gpg_command)s -c --verbose --no-use-agent --batch --yes --passphrase-fd %(passphrase_fd)s -o %(output_file)s %(input_file)s
gpg_passphrase = 
guess_mime_type = True
host_base = s3.cn-north-1.jcloudcs.com
host_bucket = %(bucket)s.s3.cn-north-1.jcloudcs.com
human_readable_sizes = False
invalidate_default_index_on_cf = False
invalidate_default_index_root_on_cf = True
invalidate_on_cf = False
kms_key = 
limit = -1
limitrate = 0
list_md5 = False
log_target_prefix = /home/eric/jcloud/s3.log
long_listing = False
max_delete = -1
mime_type = 
multipart_chunk_size_mb = 15
multipart_max_chunks = 10000
preserve_attrs = True
progress_meter = True
proxy_host = 
proxy_port = 0
put_continue = False
recursive = False
recv_chunk = 65536
reduced_redundancy = False
requester_pays = False
restore_days = 1
restore_priority = Standard
secret_key = [you secret key]
send_chunk = 65536
server_side_encryption = False
signature_v2 = False
simpledb_host = sdb.amazonaws.com
skip_existing = False
socket_timeout = 300
stats = False
stop_on_error = False
storage_class = 
urlencoding_mode = normal
use_http_expect = False
use_https = False
use_mime_magic = True
verbosity = WARNING
website_endpoint = http://%(bucket)s.s3-website-%(location)s.amazonaws.com/
website_error = 
website_index = index.html
```

**Check if S3cmd is available for use**

Input s3cmd and enter under the Linux shell environment and the use is available when the following indication is given:

![](https://github.com/jdcloudcom/cn/blob/edit/image/Object-Storage-Service/OSS-092.png)

Taking Make bucket as example, test whether S3cmd is available:

![](https://github.com/jdcloudcom/cn/blob/edit/image/Object-Storage-Service/OSS-093.png)

## Supported functions

Commands supported by S3cmd to JD Cloud OSS are listed as follows:

Commands：

<body link="#0563C1" vlink="#954F72">

<table border=0 cellpadding=0 cellspacing=0 width=406 style='border-collapse:
 collapse;table-layout:fixed;width:305pt'>
 <col width=69 style='width:152pt'>
 <col width=337 style='mso-width-source:userset;mso-width-alt:10773;width:453pt'>
 <tr height=19 style='height:14.5pt'>
  <td height=19 class=xl65 width=69 style=’height:14.5pt;width:152pt’>Function Type</td>
  <td class=xl66 width=337 style=’width:453pt’>Function Command</td>
 </tr>
 <tr height=19 style='height:14.0pt'>
  <td rowspan=24 height=588 class=xl67 width=69 style='border-bottom:1.0pt solid black;
  height:441.0pt;border-top:none;width:152pt’>Management Bucket</td>
  <td rowspan=2 class=xl70 width=337 style='border-bottom:1.0pt solid black;
  border-top:none;width:453pt'>Make bucket s3cmd<br>
    mb s3://BUCKET</td>
 </tr>
 <tr height=19 style='height:14.5pt'>
 </tr>
 <tr height=31 style='mso-height-source:userset;height:23.0pt'>
  <td rowspan=2 height=50 class=xl70 width=337 style='border-bottom:1.0pt solid black;
  height:37.5pt;border-top:none;width:453pt'>Remove bucket<br>
    s3cmd rb s3://BUCKET</td>
 </tr>
 <tr height=19 style='height:14.5pt'>
 </tr>
 <tr height=31 style='mso-height-source:userset;height:23.0pt'>
  <td rowspan=2 height=50 class=xl70 width=337 style='border-bottom:1.0pt solid black;
  height:37.5pt;border-top:none;width:453pt'>List objects or buckets<br>
    s3cmd ls [s3://BUCKET[/PREFIX]]</td>
 </tr>
 <tr height=19 style='height:14.5pt'>
 </tr>
 <tr height=31 style='mso-height-source:userset;height:23.0pt'>
  <td rowspan=2 height=50 class=xl70 width=337 style='border-bottom:1.0pt solid black;
  height:37.5pt;border-top:none;width:453pt'>Disk usage by buckets<br>
    s3cmd du [s3://BUCKET[/PREFIX]]</td>
 </tr>
 <tr height=19 style='height:14.5pt'>
 </tr>
 <tr height=31 style='mso-height-source:userset;height:23.0pt'>
  <td rowspan=2 height=50 class=xl70 width=337 style='border-bottom:1.0pt solid black;
  height:37.5pt;border-top:none;width:453pt'>Modify Access control list for
  Bucket or Files<br>
    s3cmd setacl s3://BUCKET[/OBJECT]</td>
 </tr>
 <tr height=19 style='height:14.5pt'>
 </tr>
 <tr height=31 style='mso-height-source:userset;height:23.0pt'>
  <td rowspan=2 height=50 class=xl70 width=337 style='border-bottom:1.0pt solid black;
  height:37.5pt;border-top:none;width:453pt'>Modify Bucket Policy<br>
    s3cmd setpolicy FILE s3://BUCKET</td>
 </tr>
 <tr height=19 style='height:14.5pt'>
 </tr>
 <tr height=31 style='mso-height-source:userset;height:23.0pt'>
  <td rowspan=2 height=50 class=xl70 width=337 style='border-bottom:1.0pt solid black;
  height:37.5pt;border-top:none;width:453pt'>Delete Bucket Policy<br>
    s3cmd delpolicy s3://BUCKET</td>
 </tr>
 <tr height=19 style='height:14.5pt'>
 </tr>
 <tr height=31 style='mso-height-source:userset;height:23.0pt'>
  <td rowspan=2 height=50 class=xl70 width=337 style='border-bottom:1.0pt solid black;
  height:37.5pt;border-top:none;width:453pt'>Modify Bucket CORS<br>
    s3cmd setcors FILE s3://BUCKET</td>
 </tr>
 <tr height=19 style='height:14.5pt'>
 </tr>
 <tr height=31 style='mso-height-source:userset;height:23.0pt'>
  <td rowspan=2 height=50 class=xl70 width=337 style='border-bottom:1.0pt solid black;
  height:37.5pt;border-top:none;width:453pt'>Delete Bucket CORS<br>
    s3cmd delcors s3://BUCKET</td>
 </tr>
 <tr height=19 style='height:14.5pt'>
 </tr>
 <tr height=31 style='mso-height-source:userset;height:23.0pt'>
  <td rowspan=2 height=50 class=xl70 width=337 style='border-bottom:1.0pt solid black;
  height:37.5pt;border-top:none;width:453pt'>Create Website from bucket<br>
    s3cmd ws-create s3://BUCKET</td>
 </tr>
 <tr height=19 style='height:14.5pt'>
 </tr>
 <tr height=31 style='mso-height-source:userset;height:23.0pt'>
  <td rowspan=2 height=50 class=xl70 width=337 style='border-bottom:1.0pt solid black;
  height:37.5pt;border-top:none;width:453pt'>Delete Website<br>
    s3cmd ws-delete s3://BUCKET</td>
 </tr>
 <tr height=19 style='height:14.5pt'>
 </tr>
 <tr height=31 style='mso-height-source:userset;height:23.0pt'>
  <td rowspan=2 height=50 class=xl70 width=337 style='border-bottom:1.0pt solid black;
  height:37.5pt;border-top:none;width:453pt'>Info about Website<br>
    s3cmd ws-info s3://BUCKET</td>
 </tr>
 <tr height=19 style='height:14.5pt'>
 </tr>
 <tr height=31 style='mso-height-source:userset;height:23.0pt'>
  <td rowspan=14 height=350 class=xl70 width=69 style='border-bottom:1.0pt solid black;
  height:262.5pt;border-top:none;width:152pt’>Management Object</td>
  <td rowspan=2 class=xl70 width=337 style='border-bottom:1.0pt solid black;
  border-top:none;width:453pt'>Put file into bucket<br>
    s3cmd put FILE [FILE...]s3://BUCKET[/PREFIX]</td>
 </tr>
 <tr height=19 style='height:14.5pt'>
 </tr>
 <tr height=31 style='mso-height-source:userset;height:23.0pt'>
  <td rowspan=2 height=50 class=xl70 width=337 style='border-bottom:1.0pt solid black;
  height:37.5pt;border-top:none;width:453pt'>Get file from bucket<br>
    s3cmd get s3://BUCKET/OBJECT LOCAL_FILE</td>
 </tr>
 <tr height=19 style='height:14.5pt'>
 </tr>
 <tr height=31 style='mso-height-source:userset;height:23.0pt'>
  <td rowspan=2 height=50 class=xl70 width=337 style='border-bottom:1.0pt solid black;
  height:37.5pt;border-top:none;width:453pt'>Delete file from bucket<br>
    s3cmd del s3://BUCKET/OBJECT</td>
 </tr>
 <tr height=19 style='height:14.5pt'>
 </tr>
 <tr height=31 style='mso-height-source:userset;height:23.0pt'>
  <td rowspan=2 height=50 class=xl70 width=337 style='border-bottom:1.0pt solid black;
  height:37.5pt;border-top:none;width:453pt'>Delete file from bucket (alias for
  del)<br>
    s3cmd rm s3://BUCKET/OBJECT</td>
 </tr>
 <tr height=19 style='height:14.5pt'>
 </tr>
 <tr height=31 style='mso-height-source:userset;height:23.0pt'>
  <td rowspan=2 height=50 class=xl70 width=337 style='border-bottom:1.0pt solid black;
  height:37.5pt;border-top:none;width:453pt'>Show multipart uploads<br>
    s3cmd multipart s3://BUCKET [Id]</td>
 </tr>
 <tr height=19 style='height:14.5pt'>
 </tr>
 <tr height=31 style='mso-height-source:userset;height:23.0pt'>
  <td rowspan=2 height=50 class=xl70 width=337 style='border-bottom:1.0pt solid black;
  height:37.5pt;border-top:none;width:453pt'>Abort a multipart upload<br>
    s3cmd abortmp s3://BUCKET/OBJECT Id</td>
 </tr>
 <tr height=19 style='height:14.5pt'>
 </tr>
 <tr height=31 style='mso-height-source:userset;height:23.0pt'>
  <td rowspan=2 height=50 class=xl70 width=337 style='border-bottom:1.0pt solid black;
  height:37.5pt;border-top:none;width:453pt'>List parts of a multipart
  upload<br>
    s3cmd listmp s3://BUCKET/OBJECT Id</td>
 </tr>
 <tr height=19 style='height:14.5pt'>
 </tr>
 <tr height=31 style='mso-height-source:userset;height:23.0pt'>
  <td rowspan=10 height=344 class=xl70 width=69 style='border-bottom:1.0pt solid black;
  height:258.5pt;border-top:none;width:152pt’>Other Function</td>
  <td rowspan=2 class=xl70 width=337 style='border-bottom:1.0pt solid black;
  border-top:none;width:453pt'>Sign arbitrary string using the secret &nbsp;
  key<br>
    s3cmd sign STRING-TO-SIGN</td>
 </tr>
 <tr height=19 style='height:14.5pt'>
 </tr>
 <tr height=46 style='mso-height-source:userset;height:34.5pt'>
  <td rowspan=3 height=84 class=xl70 width=337 style='border-bottom:1.0pt solid black;
  height:63.0pt;border-top:none;width:453pt'>Get various information about
  Buckets or &nbsp; Files<br>
    s3cmd info s3://BUCKET[/OBJECT]<br>
    Note: The bucket information display is not supported here and the displayed object information is incomplete </td>
 </tr>
 <tr height=19 style='height:14.0pt'>
 </tr>
 <tr height=19 style='height:14.5pt'>
 </tr>
 <tr height=107 style='mso-height-source:userset;height:80.5pt'>
  <td rowspan=3 height=145 class=xl70 width=337 style='border-bottom:1.0pt solid black;
  height:109.0pt;border-top:none;width:453pt'>Synchronize a directory tree to
  S3 (checks files freshness using size and md5 checksum, unless overridden by
  options, see below)<br>
    s3cmd sync LOCAL_DIR s3://BUCKET[/PREFIX] or s3://BUCKET[/PREFIX]
  LOCAL_DIR<br>
    Note: The automatic synchronization will not be made and please input this command to synchronize a catalog. </td>
 </tr>
 <tr height=19 style='height:14.0pt'>
 </tr>
 <tr height=19 style='height:14.5pt'>
 </tr>
 <tr height=46 style='mso-height-source:userset;height:34.5pt'>
  <td rowspan=2 height=65 class=xl70 width=337 style='border-bottom:1.0pt solid black;
  height:49.0pt;border-top:none;width:453pt'>Sign an S3 URL to provide limited
  public access with expiry s3cmd signurl &nbsp;&nbsp;<br>
    s3://BUCKET/OBJECT &lt;expiry_epoch|+expiry_offset&gt;</td>
 </tr>
 <tr height=19 style='height:14.5pt'>
 </tr>

</table>
