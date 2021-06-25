---
sort: 1
---

# Step 1. Identification

1. The SW development team identifies open source and license to be used for software development, and designs software so as to prevent intellectual property leakage in consideration of the specific case terms of use of each open source license.
   <br>

2. The SW development team determines how to notify OSS when using open source in software for distribution.
   <br>

3. The SW development team complies with copyright and license writing rules in source code.
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
<br>

```tip
You can use the open source tools for analyzing open source efficiently.
Please visit the [Tool](../../tool/osc_tool.md) page to learn more about open source tools.
```
