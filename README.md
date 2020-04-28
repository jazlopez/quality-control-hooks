### GIT Hook: commit-msg

Verify source code fulfills coding standards as described in .estlintrc file.

In order to use this hook you want to copy ```commit-msg``` file to your repository's hook directory.

By doing so it will register a hook that automatically run verifications to staged files every time you want to commit them.

If verification ends without error the commit will go thru normally. Otherwise it will abort until the code is modified to pass the verification.
  
```
cp commit-msg /PATH/TO/YOUR/REPOSITORY/.git/hooks/commit-msg
```

> For the hook to work it requires an .eslintrc file. if you do not have an existing .eslintrc in your project see .estlintrc.json.dist example file. You need to rename it to .eslintrc.json and place it in your project at top level directory.
>  
> ``cp .eslintrc.json.dist /PATH/TO/YOUR/REPOSITORY/.eslintrc.json``
>  

#### 1. GET STARTED

Code styling verification hook is built atop of ESLint and other additional plugins which all of them
are available to install via npm/yarn package manager.

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
npm install -g eslint@5.16.0 \ 
  eslint-config-standard@12.0.0 \ 
  eslint-plugin-import@2.17.3 \ 
  eslint-plugin-node@9.1.0 \
  eslint-plugin-promise@4.1.1 \
  eslint-plugin-standard@4.0.0
```

#### 2. DISABLE HOOK

Simply rename or delete commit-msg file to make the hook to stop source code verification.

```
# rename 
mv /PATH/TO/YOUR/REPOSITORY/.git/hooks/commit-msg /PATH/TO/YOUR/REPOSITORY/.git/hooks/commit-msg.disabled 

# delete
rm /PATH/TO/YOUR/REPOSITORY/.git/hooks/commit-msg
```

#### 3. VERSION

1.0.0    Initial
1.0.1    fix staged .js file mask

#### 4. CONTACT

[TFC Nutrias](mailto:tfc_nutrias@thermofisher.com)
