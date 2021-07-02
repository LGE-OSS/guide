---
sort: 1
---

# Step 1. Identification

1. The SW development team identifies open source and license to be used for software development, and designs software so as to prevent intellectual property leakage in consideration of the specific case terms of use of each open source license.
   <br>

2. The SW development team determines how to notify OSS when using open source in software for distribution.
   <br>

3. The SW development team complies with [copyright and license writing rules in source code](#rule).
   <br>

4. The SW development team and the team in charge of OSC identify open source and license through open source analysis.
   The identification step and activities are as follows.

```note
- **Source Code analysis**
    - This step identifies open source and its license by checking source code.
    - We recommend [`FOSSLight Source Scanner`](https://github.com/fosslight/fosslight_source_scanner) tool for more efficient analyzing source code.
- **Binary analysis**
    - This step identifies open source that may be missing from source code analysis procedure by checking all binary files included in software.
- **Dependency analysis**
    - This step identifies open source and license in the dependency list in software development environment that supports dependency management.
    - We recommend [`FOSSLight Dependency Scanner`](https://github.com/fosslight/fosslight_dependency_scanner) tool for more efficient analyzing dependency.
```

<br>

<a name="rule"></a> <details><summary>Note. Copyright and license writing rules in source code</summary>

> In order to easily and clearly identify what license is and to whom the copyright belongs, it is necessary to correctly write the copyright and the license in the source code.

To ensure proper copyright and license writing in the source code, the following three rules must be observed.    
1. Write the copyright and license on each file. 
2. (Only with OSS Package) Add Open Source Software Package information file.  
3. (Source code distribution only) Add license text file.  

### 1. Write the copyright and license on each file
Software developers write copyrights and licenses according to the rules to be followed on a case-by-case basis as follows:

| No  | Case | Rule |
| ------------- | ------------- | ------------- |
| 1 | In case of software developed by LGE | Write the copyright and license on each file. | 
| 2 | In case of including open source in LGE software |Do not modify/delete copyright and license information in the original open source.| 
| 3 | In case of including only certain files or functions in LGE software from open source | If the file already has the proper copyright and license information, do not modify/delete it. <br><br> If the file is missing copyright and license information, or if you copy only certain functions, write the copyright and license specified in the original open source in the file included in LGE software. |  

💁 **How to write license**    
SPDX-License-Identifier: [[SPDX License Identifier](https://spdx.org/licenses/)]     
- ex 1. Apche-2.0
    ```
    SPDX-License-Identifier: Apache-2.0
    ```
- ex 2. LGE Proprietary License    
    ```
    /*
   * Copyright (c) 2020 LG Electronics Inc.
   * SPDX-License-Identifier: LicenseRef-LGE-Proprietary
   */    
   ```

### 2. Add Open Source Software Package information file
⭐ This rule only applies if Open Source Software Package is included.

Create a oss-pkg-info.yaml file (format : Yaml) and add it to the directory of the package, including the following information about the OSS Package. ex) oss-pkg-info.yaml    
If a file (ex-requirements.txt, pom.xml) already containing such information is present in the OSS Package directory, it can be replaced with this file.

```
Open Source Software Package:
- name: glibc
  version: 2.28
  source: https://ftp.gnu.org/gnu/glibc
  license:
  - GPL-2.0
  - LGPL-2.1
  file : 
  - main.c
  - main.h
- name : dbus
  version : 1.9.14
  source : https://dbus.freedesktop.org/releases/dbus
  homepage : https://www.freedesktop.org
  license : GPL-2.0
  file : src/*
  copyright : |
   Copyright (c) 1992-2014 Free Software Foundation, Inc.
   Copyright (c) 2003 Philip Blundell 
- name : node-openssl
  version : 1.0.1
  source : https://github.com/131/node-openssl
  license : ISC
- name : bazel
  source : https://github.com/bazelbuild/bazel
  license : Apache-2.0
  file : build/
  exclude : True
  comment : Script for build
```

### 3. Add license text file
⭐ This rule applies only when distributing source code.

1. Creates a file representing the license of the Repository in the top directory of the project.
    - Download the license text file and change the file name to one of: LICENSE, LICENSE.md, LICENSE.txt, and NOTICE.
2. Create a directory named LICENSES in the top directory of your project, and include the license text file of the license included in the project.
    - If the project includes open source software under multiple licenses, include all of license text files.

</details>

<br>
<br>

```tip
You can use the open source tools for analyzing open source efficiently.
Please visit the [Tool](../../tool/osc_tool.md) page to learn more about open source tools.
```
