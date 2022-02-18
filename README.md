Tika can be used for experiments without any additional applications.

How to install it:

1) docker-compose up -d
2) If you don't have curl installed you can install it locally. 

```
sudo snap install curl

```

4) Run this command as a test in your terminal:


```
cat <<EOT >> test.txt
Hello world from the Apache Tika Team (dev@tika.apache.org).
EOT
curl -T test.txt http://localhost:9998/meta

```

How to parse .pdf

Example:
Suppose your .pdf file is located here:

/home/sergey/Downloads/test.pdf

Then we can run comamnd:

```
curl -X PUT --data-binary @/home/sergey/Downloads/test.pdf http://localhost:9998/tika --header "Content-type: application/pdf"

```

This command will return parsed .pdf file content in xml. 

More info on how to use curl to test tika REST API

https://cwiki.apache.org/confluence/display/TIKA/TikaServer
