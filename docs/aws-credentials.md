Before using Up you need to first provide your AWS account credentials so that resources can be created. There are a number of ways to do that, which are outlined here.

## Via environment variables

Using environment variables only, you may specify the following:

- `AWS_ACCESS_KEY_ID` AWS account access key
- `AWS_SECRET_ACCESS_KEY` AWS account secret key
- `AWS_REGION` AWS region

If you have multiple AWS projects you may want to consider using a tool such as [direnv](http://direnv.net/) to localize and automatically set the variables when
you're working on a project.

## Via ~/.aws files

Using the `~/.aws/credentials` file to store credentials, allowing you to specify `AWS_PROFILE` so Up knows which project to reference. To read more on configuring these files view [Configuring the AWS CLI](http://docs.aws.amazon.com/cli/latest/userguide/cli-chap-getting-started.html).

Here's an example of `~/.aws/credentials`, where `export AWS_PROFILE=myapp` would activate these settings.

```
[myapp]
aws_access_key_id = xxxxxxxx
aws_secret_access_key = xxxxxxxxxxxxxxxxxxxxxxxx
```

## Via project configuration

You may store the profile name in the `up.json` file itself as shown in the following snippet. This is typically ideal since it ensures that you do not accidentally have a different environment set.

```json
{
  "profile": "myapp"
}
```
