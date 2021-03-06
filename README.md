1. Deploy this repo to Netlify using 
[![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/sgrove/secrets-test)

2. Go to https://authlify-dev.netlify.app/ to enable the addon

After it's deployed, you can hit three endpoints:

1. "/.netlify/functions/secrets" - see all enabled auths + secrets (sanitized so they're not exposed)
1. "/.netlify/functions/conditionalSecrets?skipSecrets=true" - an endpoint that can optionally retrieve secrets, useful to see the overhead of the current implementation
1. "/.netlify/functions/addIssueComment?comment=Hello there!" - an endpoint that requires GitHub to be authenticated with sufficient scopes (default should be fine). Will leave a comment on https://github.com/sgrove/blog/issues/66

Be sure to destroy the app after you finish testing so there are no leaked secrets.
