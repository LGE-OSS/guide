---
title: Copyright and license writing rules in source code
---

# Copyright and license writing rules in source code

In order to easily and clearly identify what license is and to whom the copyright belongs, it is necessary to correctly write the copyright and the license in the source code.

To ensure proper copyright and license writing in the source code, the following three rules must be observed.    
1. [Write the copyright and license on each file.](#-1-write-the-copyright-and-license-on-each-file)
2. [(Only with OSS Package) Add Open Source Software Package information file.](#2-add-open-source-software-package-information-file)
3. [(Source code distribution only) Add license text file.](#3-add-license-text-file)

## 1. Write the copyright and license on each file
Software developers write copyrights and licenses according to the rules to be followed on a case-by-case basis as follows:

| No  | Case | Rule |
| ------------- | ------------- | ------------- |
| 1 | In case of software developed by LGE | Write the copyright and license on each file. | 
| 2 | In case of including open source in LGE software |Do not modify/delete copyright and license information in the original open source.| 
| 3 | In case of including only certain files or functions in LGE software from open source | If the file already has the proper copyright and license information, do not modify/delete it. <br><br> If the file is missing copyright and license information, or if you copy only certain functions, write the copyright and license specified in the original open source in the file included in LGE software. |  

💁 **How to write license**    
SPDX-License-Identifier: [[SPDX License Identifier](https://spdx.org/licenses/)]  

ex 1. Apache-2.0
```
SPDX-License-Identifier: Apache-2.0
```

ex 2. LGE Proprietary License     
```
Copyright (c) 2020 LG Electronics Inc.    
SPDX-License-Identifier: LicenseRef-LGE-Proprietary       
```

## 2. Add Open Source Software Package information file
[⭐ This rule only applies if Open Source Software Package is included.]

Create a oss-pkg-info.yaml file (format : Yaml) and add it to the directory of the package, including the following information about the OSS Package. ex) oss-pkg-info.yaml    
If a file (ex-requirements.txt, pom.xml) already containing such information is present in the OSS Package directory, it can be replaced with this file.

```
libidn:
- version: "1.5"
  source name or path:
  - a.c
  - b.c
  license:
  - "GPL-3.0"
  - "LGPL-2.1"
  download location: "http://ftp.gnu.org/gnu/libidn"
  homepage: "https://www.gnu.org/software/libidn"
  copyright text: "Copyright (c) 2002-2007, Simon Josefsson"
node-backoff:
- version: "2.5.0"
  source name or path: "src/*"
  license: "MIT"
  download location: "https://github.com/MathieuTurcotte/node-backoff"
  homepage: "https://www.npmjs.com/package/backoff"
  copyright text: "Copyright (c) 2012 Mathieu Turcotte"
  exclude: True
rsync:
- version: "2.6.9"
  source name or path: "test/tool"
  license: "GPL-2.0"
  download location: "https://download.samba.org/pub/rsync/src"
  homepage: "http://rsync.samba.org"
- version: "3.1.2"
  source name or path: "test/tool"
  license: "GPL-3.0"
  download location: "https://download.samba.org/pub/rsync/src"
  homepage: "http://rsync.samba.org"
  copyright text:
  - "Copyright (c) 1996 Andrew Tridgell"
  - "Copyright (c) 1996 Paul Mackerras"
  - "Copyright (c) 2003-2015 Wayne Davison"
```

## 3. Add license text file
[⭐ This rule applies only when distributing source code.]

1. Creates a file representing the license of the Repository in the top directory of the project.
    - Download the license text file and change the file name to one of: LICENSE, LICENSE.md, LICENSE.txt, and NOTICE.
2. Create a directory named LICENSES in the top directory of your project, and include the license text file of the license included in the project.
    - If the project includes open source software under multiple licenses, include all of license text files.

