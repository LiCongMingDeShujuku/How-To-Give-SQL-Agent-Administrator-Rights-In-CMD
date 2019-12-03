![CLEVER DATA GIT REPO](https://raw.githubusercontent.com/LiCongMingDeShujuku/git-resources/master/0-clever-data-github.png "李聪明的数据库")

# 如何在CMD中授予SQL代理管理员权限
#### How To Give SQL Agent Administrator Rights In CMD
**发布-日期: 2016年11月9日 (评论)**



## Contents

- [中文](#中文)
- [English](#English)
- [SQL Logic](#Logic)
- [Build Info](#Build-Info)
- [Author](#Author)
- [License](#License) 


## 中文
如果你正在SQL Server Agent下创建作业进程，并且你希望从xp_cmdshell运行基于操作系统的命令，则可能会遇到SQL服务帐户没有以下3个权限的错误。

1. 备份文件和的权利。
2. 管理审计和安全日志的权利。
3. 调试程序的权利。

在大多数情况下，如果你的帐户在操作系统中具有管理员权限，并且你已直接登录，而不是使用SQL进程来运行CMD命令，则账户会自动假定这些权限；你只是使用了Command Prompt方式，并且明确通过“Run as Administrator”方式来打开它。


这些权限在安全体系结构中称为以下几种名称：

SeBackupPrivilege
SeDebugPrivilege
SeSecurityPrivilege

如果你有本地安全策略的权限，就可以轻松地添加这些内容，以下为如何添加它们。

转到StartàRun，运行secpol.msc

## English
If you’re creating a job process under the SQL Server Agent and you’re expecting to run an OS based command from xp_cmdshell you may run into an error where the SQL Service Account doesn’t have the following 3 rights.

1. The right to back up files and directories.
2. The right to manage auditing and the security log.
3. The right to debug programs.

In most cases these rights are automatically assumed if your account has Administrator rights in the OS, and you’re logged on directly but instead of using an SQL process to run the CMD command; you’re simply using Command Prompt, and you’ve already explicitly opened it using ‘Run as Administrator’.

In security architecture these privileges are knows as the following:

SeBackupPrivilege
SeDebugPrivilege
SeSecurityPrivilege

These are fairly easy to add if you’ve got rights to the local security policies, and here’s how to add them.

Go to Startà Run, and run secpol.msc


![#](images/01-如何在CMD中授予SQL代理管理员权限.png?raw=true "#")

Expand ‘Local Policies’, and select ‘User Rights Assignments’.
展开“Local Policies”，然后选择“User Rights Assignments”。

![#](images/02-如何在CMD中授予SQL代理管理员权限.png?raw=true "#")

You’ll need to click each one of these and ensure the SQL Service Accounts have been added to them. If you’re creating the  to run under another account that isn’t a service account then you’ll need to add it directly as well.

你需要单击其中每一个并确保已将SQL服务帐户添加到它们中。如果你要创建代理作业以在另一个非服务帐户的帐户下运行，那么你还需要直接添加它。


[![WorksEveryTime](https://forthebadge.com/images/badges/60-percent-of-the-time-works-every-time.svg)](https://shitday.de/)

## Build-Info

| Build Quality | Build History |
|--|--|
|<table><tr><td>[![Build-Status](https://ci.appveyor.com/api/projects/status/pjxh5g91jpbh7t84?svg?style=flat-square)](#)</td></tr><tr><td>[![Coverage](https://coveralls.io/repos/github/tygerbytes/ResourceFitness/badge.svg?style=flat-square)](#)</td></tr><tr><td>[![Nuget](https://img.shields.io/nuget/v/TW.Resfit.Core.svg?style=flat-square)](#)</td></tr></table>|<table><tr><td>[![Build history](https://buildstats.info/appveyor/chart/tygerbytes/resourcefitness)](#)</td></tr></table>|

## Author

- **李聪明的数据库 Lee's Clever Data**
- **Mike的数据库宝典 Mikes Database Collection**
- **李聪明的数据库** "Lee Songming"

[![Gist](https://img.shields.io/badge/Gist-李聪明的数据库-<COLOR>.svg)](https://gist.github.com/congmingshuju)
[![Twitter](https://img.shields.io/badge/Twitter-mike的数据库宝典-<COLOR>.svg)](https://twitter.com/mikesdatawork?lang=en)
[![Wordpress](https://img.shields.io/badge/Wordpress-mike的数据库宝典-<COLOR>.svg)](https://mikesdatawork.wordpress.com/)

---
## License
[![LicenseCCSA](https://img.shields.io/badge/License-CreativeCommonsSA-<COLOR>.svg)](https://creativecommons.org/share-your-work/licensing-types-examples/)

![Lee Songming](https://raw.githubusercontent.com/LiCongMingDeShujuku/git-resources/master/1-clever-data-github.png "李聪明的数据库")

