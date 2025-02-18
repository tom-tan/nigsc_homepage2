---
id: faq_hcptools
title: FAQ (Archaea tools(formerly HCPtools))
---


## When transferring files, do I always have to specify the transfer source and transfer destination with absolute paths?

The path on the user's computer can be specified as either an absolute or relative path.

However, the path of the personal genome analysis section cannot be specified as a relative path.It must be specified as an absolute path.

Below are input examples for the user's computer path.

Both input examples 1 and 2 mean the same thing, so you can execute them whichever you prefer.


- Upload the file `upload_ex1.txt` in the home directory of the user's computer to the user's home directory in the personal genome analysis section.

Input example 1: When specifying by absolute path
```
hcp --user uesrname C:\Users\uesrname\upload_ex1.txt gwa.ddbj.nig.ac.jp:upload_ex1.txt
```

Input example 2: When specifying by relative path
```
hcp --user uesrname upload_ex1.txt gwa.ddbj.nig.ac.jp:upload_ex1.txt
```


- Upload files by specifying a directory.

Input example 1: When specifying by absolute path
```
hcp --user uesrname C:\Users\uesrname\HCP_upload\upload_ex1.txt gwa.ddbj.nig.ac.jp:/home/uesrname/HCP_upload/upload_ex1.txt
```

Input example 2: When specifying by relative path
```
hcp --user uesrname .\HCP_upload\upload_ex1.txt gwa.ddbj.nig.ac.jp:/home/uesrname/HCP_upload/upload_ex1.txt
```


- Download the file `download_ex1.txt` from the user's home directory in the personal genome analysis section to the home directory of the user's computer.

Input example 1: When specifying by absolute path
```
hcp --user uesrname gwa.ddbj.nig.ac.jp:download_ex1.txt C:\Users\uesrname\download_ex1.txt
```

Input example 2: When specifying by relative path
```
hcp --user uesrname gwa.ddbj.nig.ac.jp:download_ex1.txt .\download_ex1.txt
```

- Download files by specifying the directory.

Input example 1: When specifying by absolute path
```
hcp --user uesrname gwa.ddbj.nig.ac.jp:/home/uesrname/HCP_upload/upload_ex1.txt C:\Users\uesrname\HCP_upload\upload_ex1.txt
```

Input example 2: When specifying by relative path
```
hcp --user uesrname gwa.ddbj.nig.ac.jp:/home/uesrname/HCP_upload/upload_ex1.txt .\HCP_upload\upload_ex1.txt
```


## Is it possible to specify a directory for file transfer?

Yes.

You can see an example of an upload executed when a directory is specified below.

For downloads, you can also specify a directory for file transfer by specifying it in the same way as for uploads.

- If you want to specify the source directory.
```
hcp --user username C:\Users\username\HCPtools_upload_test\upload_ex1.txt gwa.ddbj.nig.ac.jp:upload_ex1.txt
```

- If you want to specify the directory to upload.
```
hcp --user username C:\Users\username\upload_ex1.txt gwa.ddbj.nig.ac.jp:/home/username/HCPtools_upload/upload_ex1.txt
```

- If you want to specify a directory for both the source and the upload.
```
hcp --user username C:\Users\username\HCPtools_upload_test\upload_ex1.txt gwa.ddbj.nig.ac.jp:/home/username/HCPtools_upload/upload_ex1.txt
```


## When specifying the upload or download destination, is it necessary to specify the file name?

Yes.

If you do not specify a file name, the following error message will be output and the file cannot be transferred.

```
2022/03/11 14:28:54 00006070:INFO :Negotiation error is set (A001).
2022/03/11 14:28:54 00006070:INFO :A response on negotiation has an error. So it was finished in failure.
2022/03/11 14:28:54 00006070:INFO :An information exchange for operation was failed.
2022/03/11 14:28:54 00006070:INFO :File is not found.hcp::node:HcpnException @ hcp::node::HcpnEndPointTransfer:L454 :  > hcp::proto::HcppException @ hcp::proto::HcppSession:L1209 :
```


## [<u>HCP tools Command Overview p.10</u>](/pdf/HCPtools_overview_en.pdf) says that only Windows 10 is supported. Is it not available for Windows 11?

Yes, it can be used on Windows 11.

