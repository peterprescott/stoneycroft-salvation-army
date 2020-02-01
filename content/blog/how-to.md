---
title: "How To Add To This Website"
date: 2020-02-01T16:55:26Z
draft: true
---

## Open Invitation
If you have a computer and an internet connection then you're welcome to help develop this site.

## Installing Necessary Tools
If you're on Windows, then start by opening [Powershell](https://en.wikipedia.org/wiki/PowerShell).

You'll need to have [git](https://git-scm.com/) (for version control) and [Hugo](https://gohugo.io/) (for automatically building websites) installed. Check if they are by typing these lines of code into Powershell: `git version`, `hugo version`.

I'll preface the ones I want you to type with arrows: **>>>** -- but don't type the arrows. And then I'll show you the first few lines of what came up on my system -- you might get slightly different versions. 

```
>>> git version
git version 2.22.0.windows.1

>>> hugo version
Hugo Static Site Generator v0.57.2-A849CB2D windows/amd64 BuildDate: 2019-08-17T17:54:13Z
```

If you haven't done this sort of thing before they probably aren't. Not to worry!

The easiest way to get them properly installed is to use [Choco](https://chocolatey.org/install), which makes installing things as easy as typing two words. But we do have to install that first... Make sure you're running Powershell as an Administrator (right-click on the Powershell icon and select **Run as Administrator**), and then copy this command:
`Set-ExecutionPolicy Bypass -Scope Process -Force; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))`

```
>>> Set-ExecutionPolicy Bypass -Scope Process -Force; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))

Getting latest version of the Chocolatey package for download.
Getting Chocolatey from https://chocolatey.org/api/v2/package/chocolatey/0.10.15.
Extracting C:\Users\presc\AppData\Local\Temp\chocolatey\chocInstall\chocolatey.zip to C:\Users\presc\AppData\Local\Temp\chocolatey\chocInstall...
```

You should then see the system download and install Choco for you. Check that it has worked: `choco`.

```
>>> choco

Chocolatey v0.10.15
Please run 'choco -?' or 'choco <command> -?' for help menu.
```
<a id="env_variables"></a>
(If it hasn't, you may need to select **Edit the system environment variables** from the Start Menu, then click **Environment Variables**, select **Path** from the **System Variables**, click **Edit**, and then add as **New** the name of the folder where Choco has been saved -- which will be something like this: `C:\ProgramData\chocolatey\bin`).

Once Choco is installed, you can easily install git and hugo:
```
>>> choco install git -y
Installing the following packages:
git
By installing you accept licenses for the packages...

>>> choco install hugo -y
Installing the following packages:
hugo
By installing you accept licenses for the packages...
```

## Clone the Site and Run a Local Version

Now you can use `git` to clone a copy of this website onto your own computer, and run a local version using Hugo:
```
>>> git clone https://github.com/peterprescott/stoneycroft-salvation-army
Cloning into 'stoneycroft-salvation-army'...
remote: Enumerating objects: 123, done.
remote: Counting objects: 100% (123/123), done.
remote: Compressing objects: 100% (92/92), done.
remote: Total 123 (delta 43), reused 103 (delta 26), pack-reused 0
Receiving objects: 100% (123/123), 33.49 MiB | 3.04 MiB/s, done.
Resolving deltas: 100% (43/43), done.

>>> cd stoneycroft-salvation-army

>>> hugo serve -D
Building sites …
                   | EN
+------------------+----+
  Pages            | 21
  Paginator pages  |  1
  Non-page files   |  0
  Static files     | 12
  Processed images |  0
  Aliases          |  4
  Sitemaps         |  1
  Cleaned          |  0

Total in 390 ms
Watching for changes in C:\Users\presc\gitDrive\demoeg\stoneycroft-salvation-army\{archetypes,content,layouts,static}
Watching for config changes in C:\Users\presc\gitDrive\demoeg\stoneycroft-salvation-army\config.toml
Environment: "development"
Serving pages from memory
Running in Fast Render Mode. For full rebuilds on change: hugo server --disableFastRender
Web Server is available at //localhost:1313/ (bind address 127.0.0.1)
Press Ctrl+C to stop
```

Open your web-browser (Google Chrome, or Mozilla Firefox, or Microsoft Edge, or whatever you use), and ask for the webpage `localhost:1313` and you should see a copy of the webpage.

## Add a New Sermon Page
Now open another instance of Powershell, and we'll create a new sermon page.

First make sure you're working in the same directory as the website files:
```
cd stoneycroft-salvation-army
```

Then adding a new sermon page just uses Hugo's `new` command -- but let's make sure the new page is created in the `sermons` subfolder of the `content` folder: `hugo new content/sermons/demo.md`

```
>>> hugo new content/sermons/demo.md
content\sermons\demo.md created
```

Go back to your webbrowser and look at the sermons page on the local website (`localhost:1313/sermons`) and you should see a new sermon has now been added to the list: **Demo**. Click on the title, and it will take you to the automatically generated page, which obviously now needs filling in.

To do that you just need to edit the textfile that Hugo has just made for us: `content/sermons/demo.md`.

It's important when editing text files that you don't try and use a word-processor (like Microsoft Word), because they add lots of invisible and in this case unnecessary (and worse) extra bits, which will mess up the whole process. Instead you can just use **Notepad**; or if you've got a spare ten seconds, I recommend you download [**Geany**](https://www.geany.org/) (pronounced [*genie*](https://www.youtube.com/watch?v=pa53XoJwudE): `choco install geany`.

```
>>> choco install geany
Chocolatey v0.10.15
Installing the following packages:
geany...
```


