# OpenStack Keystone authentication plugin for StackStorm Community edition 

Cloned from [StackStorm/st2-auth-backend-keystone](https://github.com/StackStorm/st2-auth-backend-keystone)

## New Feature
- Fixed for Python 3
- Can select the user domain for OpenStack Keystone V3

## Installation
Install it to the vitrualenv of st2 using:
```
sudo /opt/stackstorm/st2/bin/pip install git+https://github.com/DonaldChung-HK/st2-auth-backend-keystone.git@master#egg=st2_auth_backend_keystone
```

### Configuration Options

| option           | required | default   | description                                              |
|------------------|----------|-----------|----------------------------------------------------------|
| keystone_url     | yes      |           | Keystone public URL (i.e. "http://example.com:5000")     |
| keystone_version | no       | 2         | Keystone API version                                     |
| domain           | no       | "default" | Domain ID of Keystone (only for keystone version 3)                                       |

### Configuration Example

Please refer to the authentication section in the StackStorm
[documentation](http://docs.stackstorm.com) for basic setup concept. The
following is an example of the auth section in the StackStorm configuration file for the flat-file
backend.

```
[auth]
mode = standalone
backend = keystone
backend_kwargs = {"keystone_url": "https://identity.example.com:5000", "keystone_version": 3, "domain": "default"}
enable = True
use_ssl = True
cert = /path/to/ssl/cert/file
key = /path/to/ssl/key/file
logging = /path/to/st2auth.logging.conf
api_url = https://myhost.example.com:9101
debug = False
```

## Copyright, License, and Contributors Agreement

Copyright 2015 StackStorm, Inc.

Licensed under the Apache License, Version 2.0 (the "License"); you may not use this work except in
compliance with the License. You may obtain a copy of the License in the [LICENSE](LICENSE) file,
or at: [http://www.apache.org/licenses/LICENSE-2.0](http://www.apache.org/licenses/LICENSE-2.0)

By contributing you agree that these contributions are your own (or approved by your employer) and 
you grant a full, complete, irrevocable copyright license to all users and developers of the
project, present and future, pursuant to the license of the project.
