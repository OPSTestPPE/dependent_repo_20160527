# This is an example that tell you how to reference a depdent repository

1. You should add your dependent repository information at the root .openpublishing.publish.config.json.
   Here's an example:
   ```opconfig_sample
{
  "need_generate_pdf": false,
  "need_generate_intellisense": false,
  "docsets_to_publish": [
    {
      "docset_name": "fenxu_dp_repo_20160527",
      "build_source_folder": "fenxu_dp_repo_20160527",
      "build_output_subfolder": "fenxu_dp_repo_20160527",
      "locale": "en-us",
      "version": 0,
      "open_to_public_contributors": true,
      "type_mapping": {
        "Conceptual": "Content",
        "ManagedReference": "Content",
        "RestApi": "Content"
      },
      "build_entry_point": "docs"
    }
  ],
  "dependent_repositories": [
        {
            "path_to_root": "fenxu_dp_repo_20160527/token",
            "url": "https://github.com/fenxu/dependent_repo_20160527_token",
            "branch": "master"
        },
        {
            "path_to_root": "fenxu_dp_repo_20160527/code",
            "url": "https://github.com/fenxu/dependent_repo_20160527_token2",
            "branch": "develop"
        }
    ],
  "skip_source_output_uploading": false
}
   ```

2. Then you can begin to ref the include the token/article under that folder. In my config, you can see that I put the one dependent repositoy under token folder and the other under code folder at the root.
   So you can write include as this: `[!INCLUDE[Include a hello token here](token/dependent_repo_20160527_token/Token/hello.md)]`
   Here's build result:
   [!INCLUDE[Include a hello token here](token/dependent_repo_20160527_token/Token/hello.md)]
   
   Also you can ref the code at the code folder as this:
   `[!CODE-cs[Include an cs code snippet](code/dependent_repo_20160527_token2/Code/sampleCS.cs)]`
   Here's build result:
   [!CODE-cs[Include an cs code snippet](code/dependent_repo_20160527_token2/Code/sampleCS.cs)]

3. For the image ref in another repository, sample `![Ref an image from another repository](token/dependent_repo_20160527_token/Image/app-settings.png)`
   Here's build result:
   ![Ref an image from another repository](token/dependent_repo_20160527_token/Image/app-settings.png)
