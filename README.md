# ng-mobsf-step

This step lets you integrate development workflow with Mobile Security Framework. As a developer you can add the step to your pipleline. The step sends APK/IPA/ZIP file to the framework using MobSF API and runs penetration tests.

## How to use this Step

Add step definition. 
```YML
 comment:
    steps:
      - git::https://github.com/rusmichal/bitrise-step-ng-mobsf.git@master:
        title: ng-mobsf
        inputs:
        - mobsf_api_url: "$MOBSF_API_URL"
        - artifact_path: "$BITRISE_SIGNED_APK_PATH"
        - api_token: "$MOBSF_API_TOKEN"
```

`MOBSF_API_URL` - Provide API URL to instance of MobSF. It is used to upload application file and generating reports. (e.g. https://mobsf.company.com)

`BITRISE_SIGNED_APK_PATH` - Path to the build artifact file (.apk|.ipa). This is output variable of assemble step.

`MOBSF_API_TOKEN` - MobSF API requried authentication token. You can find it in API docs.


## How to contribute to this Step

1. Fork this repository
2. `git clone` it
3. Create a branch you'll work on
4. To use/test the step just follow the **How to use this Step** section
5. Do the changes you want to
6. Run/test the step before sending your contribution
  * You can also test the step in your `bitrise` project, either on your Mac or on [bitrise.io](https://www.bitrise.io)
  * You just have to replace the step ID in your project's `bitrise.yml` with either a relative path, or with a git URL format
  * (relative) path format: instead of `- original-step-id:` use `- path::./relative/path/of/script/on/your/Mac:`
  * direct git URL format: instead of `- original-step-id:` use `- git::https://github.com/user/step.git@branch:`
  * You can find more example of alternative step referencing at: https://github.com/bitrise-io/bitrise/blob/master/_examples/tutorials/steps-and-workflows/bitrise.yml
7. Once you're done just commit your changes & create a Pull Request

That's all ;)

License
-------
	Copyright 2019 Netguru

	Licensed under the Apache License, Version 2.0 (the "License");
	you may not use this file except in compliance with the License.
	You may obtain a copy of the License at

	    http://www.apache.org/licenses/LICENSE-2.0

	Unless required by applicable law or agreed to in writing, software
	distributed under the License is distributed on an "AS IS" BASIS,
	WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
	See the License for the specific language governing permissions and
	limitations under the License.
