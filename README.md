# This repository is deprecated

This code is now located in our monorepo [here](https://github.com/reactioncommerce/reaction/tree/trunk/packages/api-plugin-email-smtp)



# api-plugin-email-smtp

[![npm (scoped)](https://img.shields.io/npm/v/@reactioncommerce/api-plugin-email-smtp.svg)](https://www.npmjs.com/package/@reactioncommerce/api-plugin-email-smtp)
[![CircleCI](https://circleci.com/gh/reactioncommerce/api-plugin-email-smtp.svg?style=svg)](https://circleci.com/gh/reactioncommerce/api-plugin-email-smtp)
[![semantic-release](https://img.shields.io/badge/%20%20%F0%9F%93%A6%F0%9F%9A%80-semantic--release-e10079.svg)](https://github.com/semantic-release/semantic-release)

## Summary

SMTP Email plugin for the [Reaction API](https://github.com/reactioncommerce/reaction)

# Registering Email Client

Mailchimp Open Commerce is made to work with almost all the email service out there. In the following guide we will provide the steps to configure MOC with Mailchimp's Transaction API (formerly Mandrill). Other services can be configured similarly.

1. Create an account on https://login.mailchimp.com/signup/
2. Navigate to Integration and then to Transactional Email and hit the launch app button. You should be at `https://mandrillapp.com/` URL now.
3. Navigate to Settings and hit the "+ New API Keys" to generate the new API Key.
4. Verify you domain using the various options available at https://mandrillapp.com/settings/sending-domains
5. In `reaction/.env` file add the `MAIL_URL=smtp://<ANY_USERNAME>:<KEY_GENERATED>@mandrillapp.com` environment variable.
6. Login as admin and naigate to `Settings` > `Shop` > `Email`. Make sure the shop email is set up up.
7. Run the following mutation for an existing user to verify the sending of email:

```graphql
mutation {
  sendVerificationEmail(email: "<YOUR_EMAIL>")
}
```

8. You should be able to see an email sent in the logs at: https://mandrillapp.com/settings/api.
9. Also you should have an email in your inbox.

## Developer Certificate of Origin

We use the [Developer Certificate of Origin (DCO)](https://developercertificate.org/) in lieu of a Contributor License Agreement for all contributions to Reaction Commerce open source projects. We request that contributors agree to the terms of the DCO and indicate that agreement by signing all commits made to Reaction Commerce projects by adding a line with your name and email address to every Git commit message contributed:

```
Signed-off-by: Jane Doe <jane.doe@example.com>
```

You can sign your commit automatically with Git by using `git commit -s` if you have your `user.name` and `user.email` set as part of your Git configuration.

We ask that you use your real name (please no anonymous contributions or pseudonyms). By signing your commit you are certifying that you have the right have the right to submit it under the open source license used by that particular Reaction Commerce project. You must use your real name (no pseudonyms or anonymous contributions are allowed.)

We use the [Probot DCO GitHub app](https://github.com/apps/dco) to check for DCO signoffs of every commit.

If you forget to sign your commits, the DCO bot will remind you and give you detailed instructions for how to amend your commits to add a signature.

## License

Copyright 2020 Reaction Commerce

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
