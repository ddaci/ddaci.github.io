---
date: 2017-04-13T11:15:58-04:00
description: "tutorial"
featured_image: ""
tags: []
title: "Tutorial - static website with Hugo and Github pages"
---

This tutorial will help you build and host your static website. 
[link to the video on youtube](https://youtu.be/LcKkrVuezSo)
1. Install powershell 7 on a windows system
Check the version of PowerShell you have on your system, open PowerShell and type
$PSVersionTable.PSVersion
To install PowerShell 7 on your system using Winget  type the following command t
winget install --id Microsoft.Powershell --source winget
2. Install Visual studio code
3. Install Go
4. Setup a github account and github desktop
5. Installing Hugo using Chocolatey 
Chocolatey is a popular package manager for Windows that simplifies the installation of software and manages dependencies neatly. 
Step 1: Install Chocolatey 
Open PowerShell 7 as an Administrator and type:
Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))
Step 2: Install Hugo extended Using Chocolatey
choco install hugo-extended -confirm
6. Install Dart Sass using Chocolatey
choco install sass

Resourses
1. here you can copy the code for the hugo.toml file https://github.com/ddaci/ddaci.github.io/blob/master/hugo.toml
2. here you can copy the code for the hugo.yaml file
https://github.com/ddaci/ddaci.github.io/blob/master/.github/workflows/hugo.yaml
3.here you can copy the folder content https://github.com/ddaci/ddaci.github.io/tree/master/content
4.here you can copy the folder static
https://github.com/ddaci/ddaci.github.io/tree/master/static
