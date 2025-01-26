# wget

Wget is a CLI tool which lets you download files and use REST API interactively. 
It supports HTTP, HTTPS, FTP and FTPS.

Here's some most common use cases:


* Direct File Download 

```
wget https://gitlab.com/parrotsec/project/documentation/-/raw/dev/docs/tools/wget.md
```

Launching this command will download directly the file inside the folder where the command has been launched. This is the basic command.

[![asciicast](https://asciinema.org/a/113463.png)](https://asciinema.org/a/113463)

![1](images/wget2/wget1.gif)

* Background download `wget -b`

``` 
wget -b http://www.kernel.org/pub/linux/kernel/v2.6/linux-2.6.39.2.tar.bz2
```
This option is very useful when starting a download on a remote machine via SSH. It will initiate the download in background, allowing the user to disconnect from the terminal once the command is launched.

![1](images/wget2/wget2.gif)

* Resuming interrupted or partially broken downloads `wget -c`

```
wget -c http://www.kernel.org/pub/linux/kernel/v2.6/linux-2.6.39.2.tar.bz2
```
A very useful command for downloading large files that may be interrupted before the complete download. Additionally, if a file with the same name as the one being downloaded already exists, the option is able to check its size and start downloading the remaining part of the file instead of downloading it again.

![1](images/wget2/wget3.gif)

* Maximum number of attempts `wget --tries`

```
wget --tries=10 http://www.kernel.org/pub/linux/kernel/v2.6/linux-2.6.39.2.tar.bz2
```

It can happen to encounter a particularly slow or crowded server. Therefore, it is necessary to set a maximum number of attempts to avoid getting stuck on this download. In this example, the maximum number of attempts has been set to 10.

![1](images/wget2/wget4.gif)

* Multiple Download `wget -i`

```
wget -i input.txt
```

A very powerful option. User can provide a text file as input to wget containing a series of URLs. The utility will sequentially download all the resources that the links listed in the text file point to, in this case is `input.txt`

![1](images/wget2/wget5.gif)

* Limiting download speed `wget –-limit-rate=`

```
wget --limit-rate=1k http://www.kernel.org/pub/linux/kernel/v3.0/testing/patch-3.0-rc4.bz2
```

If you need to limit the amount of bandwidth for downloads, wget allows the user to do so with the "limit-rate" option, and in the example shown, the limit has been set to 1kB/s. 

![1](images/wget2/wget6.gif)

