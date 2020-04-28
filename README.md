### GIT Hook: commit-msg

Verify source code fulfills coding standards as described in .estlintrc file.

In order to use this hook you want to copy ```commit-msg``` file to your repository's hook directory.

By doing so it will register a hook that automatically run verifications to staged files every time you want to commit them.

If verification ends without error the commit will go thru normally. Otherwise it will abort until the code is modified to pass the verification.

#### 1. GET STARTED

Code styling verification hook is built atop of ESLint and other additional plugins which all of them
are available to install via npm/yarn package manager.

```
git commit app/scripts/app.js -m "fo"

# Running commit-msg git hook
# ------------------------------------------------------
# Location:      /Users/jaziel.lopez/WebstormProjects/aig-pcp-frontend
# Branch:        development
# Last revision: e2179815833a1ab4d77e66a5bdb52acd380072ae

...please stand by eslint had started to verify staged changes...


/Users/jaziel.lopez/WebstormProjects/aig-pcp-frontend/app/scripts/app.js
   15:11  error  'angular' is not defined                    no-undef
   45:12  error  Strings must use doublequote                quotes
   47:11  error  Strings must use doublequote                quotes
   54:1   error  'angular' is not defined                    no-undef
   62:1   error  Expected indentation of 5 tabs but found 4  indent
   63:1   error  Expected indentation of 5 tabs but found 4  indent
   64:1   error  Expected indentation of 4 tabs but found 3  indent
   76:28  error  Strings must use doublequote                quotes
   83:28  error  Strings must use doublequote                quotes
   90:28  error  Strings must use doublequote                quotes
   97:28  error  Strings must use doublequote                quotes
  104:28  error  Strings must use doublequote                quotes
  111:28  error  Strings must use doublequote                quotes
  117:28  error  Strings must use doublequote                quotes
  123:28  error  Strings must use doublequote                quotes
  142:22  error  'angular' is not defined                    no-undef
  154:3   error  'angular' is not defined                    no-undef
  155:4   error  'angular' is not defined                    no-undef

✖ 18 problems (18 errors, 0 warnings)
  13 errors and 0 warnings potentially fixable with the `--fix` option.

# Sorry!
# Your Commit Had Been Rejected
# Code you are trying to commit did not pass code style verification
# See /Users/jaziel.lopez/WebstormProjects/aig-pcp-frontend/.eslintrc for guidelines
# Apply fix(es) and commit again
# Good bye...
```

##### 1.1  SYSTEM REQUIREMENTS

Hooks are built atop of a set of NodeJS utilities; therefore it has to be installed in your system and must match minimal version set to 6.14.0

> If you are not sure if your system meets NodeJS requirement visit nodeJS official documentation for more information.

##### 1.2 NODEJS MODULE REQUIREMENTS

Make sure your system has installed the following plugins and tools.
 
* eslint  5.16.0
* eslint-config-standard 12.0.0
* eslint-plugin-import 2.17.3
* eslint-plugin-node 9.1.0
* eslint-plugin-promise 4.1.1
* eslint-plugin-standard 4.0.0

######  1.2.1 INSTALLATION

```
# Run install script 

./install.sh

```

#### 2. ENABLE HOOK

Simply copy commit-msg file into any of your javascript based projects you want to eslint before proceed with commit.

```
# copy hook file to your desired project 
# allow execution of commit-msg file 

cp commit-msg /PATH/TO/YOUR/REPOSITORY/.git/hooks/commit-msg
chmod +x /PATH/TO/YOUR/REPOSITORY/.git/hooks/commit-msg

# copy eslint rules to your desired project
cp .eslintrc.json.dist /PATH/TO/YOUR/REPOSITORY/.eslintrc.json
```

#### 3. DISABLE HOOK

Simply rename or delete commit-msg file to make the hook to stop source code verification.

```
# rename 
mv /PATH/TO/YOUR/REPOSITORY/.git/hooks/commit-msg /PATH/TO/YOUR/REPOSITORY/.git/hooks/commit-msg.disabled 

# delete
rm /PATH/TO/YOUR/REPOSITORY/.git/hooks/commit-msg
```

#### 4. VERSION

1.0.0    Initial
1.0.1    fix staged .js file mask

#### 5. CONTACT

[TFC Nutrias](mailto:tfc_nutrias@thermofisher.com)
[Jaziel Lopez](mailto:jaziel.lopez@thermofisher.com)
