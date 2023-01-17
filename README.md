##### NODE PACKAGE MANAGER [click here for more info official documentation](https://docs.npmjs.com/getting-started)
INTRODUCTON

Node.js has been taking the world by storm since 2009. Hundreds of thousands of systems have been built using Node.js,prompting the developer community to claim that "JavaScript is eating software"

One of the major factors of Node's success is npm - its popular package manager,which allows JavaScript developers to share useful packages like lodash and moment quickly and easily.

npm-Node Package Manager is the default package manager for Javascript runtime Node.js.

Use npm to :
- Adapt packages of code for your apps, or incorporate packages as they are.
- Download standalone tools you can use right away.
- Run packages without downloading using npx.
- Share code with any npm user, anywhere.
- Restrict code to specific developers.
- Create organizations to coordinate package maintenance, coding, and developers.
- Form virtual teams by using organizations.
- Manage multiple versions of code and code dependencies.
- Update applications easily when underlying code is updated.
- Discover multiple ways to solve the same puzzle.
- Find other developers who are working on similar problems and projects.



NPM consists of two main parts:
- A CLI (command-line interface) tool: for publishing and downloading packages
- an online repository that hosts JavaScript packages

Node installation comes with following binary executable inside bin

Verify installed node/npm/npx version

- node --version | -v
- npm --version  | -v
- npx --version  | -v

Node installation setup in local environment {where internet access is not available}
#################################################

     SEt NODE PATH PARIABLE 
    
        set PATH =%PATH%;P:\Softwae\node-v8.11.2-win-x64\node-v8.11.2-win-x64\
     change npm cache path 
    
        npm config set cache P:\Softwae\node-v8.11.2-win-x64\node-v8.11.2-win-x64\npm-cache --global
        
     change npm registry
    
        npm config set registry http://new-reg.net/artifactory/api/npm/npm --global
    

Node Version Manager nvm
    
    NVM makes it easy to switch between different versions of Node.js. Read more about it on the project's GitHub page.
    
    Once you have nvm installed, if you want to install the latest version of Node v12 just run:
    
        nvm install 12
    
    If you have multiple versions of Node.js installed on your workspace, you can switch to a specific version by writing:
        
        nvm use 10.19.0
        
    Make a Node version default
        
        In order to set a default version of Node for your workspace, just type:
       
        nvm alias default 12: Where the latest version of 12 is the version you want to be used by default.

Shorthand

    # install
    npm i <package>
    
    # uninstall
    npm un <package>
    
    # update
    npm up <package>
    
    Flags:
    -S is the same as --save, and -D is the same as --save-dev.

List globally installed packages:

    npm list -g --depth=0

Update npm

    If you use Node installed through nvm, it's good practice to update your version of npm with this command:
    nvm install-latest-npm
    
Uninstall global package

    npm -g uninstall <name> 
Upgrade npm on Windows
    
    npm-windows-upgrade
Update global packages:
    
    To see which packages need updating, use:

    npm outdated -g --depth=0

To update global packages individually you can use:

    npm update -g <package> <package> <package>

list available scripts to run

    npm run
Update npm

    npm install -g npm@latest
    
npm init : 

    Help us to convert every javascript or browser application into module/node project 
    which allows us to publish/install/use by  other developer around the world.
    
    package.json will be generated when npm init is run to initialise a JavaScript/Node.js project, with these basic metadata provided by developers:

               - name: the name of your JavaScript library/project
               - version: the version of your project. Often times, for application development, this field is often neglected as there's no apparent
                need for versioning opensource libraies. But still, it can come handy as a source of the deployment's version.
               - description: the project's description
               - license: the project's license 
	
Package.lock.json

    package.json ma direct packages haru list gareko hunxa i.e no transitive dependency ...every time we update/remove/add package 
    it will maintain package.lock.json which contains dependecies tree along with transitive dependency 
    which is used to recreate the exact version of dependecy for the given project when we move to another environment usaully.
    
npm scripts:
  
    npm run 
    can be run these scripts through npm command line tools.
 
 Global vs local
 ##########################3
    NPM INSTALL PACKAGE_NAME -g
    
        any package that is install as global can be access through out the machine
        and can also be access though command line tool .globally installed package can not be
        access using cmd.
        
        Package that are installed locally can not be
        access from command line.we ca access local install package through scripts .
        
 Local project ma install vayeko package is not available 
 on cmd tools.
 
 npm i express -g [install exrepss globally ,can not import into project using require ]
 
 npx recent version allows us to use locally installed package
 to run from command line tool.
 
 
 e.g npm prettier --write **/*.ts
 
 
 

 e.g npm format 

  {
  "scripts": {
    "build": "tsc",
    "format": "prettier --write **/*.ts",
    "format-check": "prettier --check **/*.ts",
    "lint": "eslint src/**/*.ts",
    "pack": "ncc build",
    "test": "jest",
    "all": "npm run build && npm run format && npm run lint && npm run pack && npm test"
  }
}

-g garera mainly liveserver haru install garinxa

Dependencies 
	==dependencies==npm install express --save[meants to be used for production enviroment]
	==devDependencies ==npm install express --save-dev	[meants to be used for development and testing environments]
	 understanding version in npm package[major.minor.patch]
		^:latest minor release. 
		   For example, a ^1.0.4 specification might install version 1.3.0 if that's the latest minor version in the 1 major series
	    ~: latest patch release. In the same way as ^ for minor releases, ~1.0.4 specification might install version 1.0.7 
		if that's the latest minor version in the 1.0 minor series.
	
	
	
####npm install --production
     The npm install command will install the devDependencies along other dependencies when run inside a package directory, in a development environment (the default).
     
     In version 8.x and above use --omit=dev flag to install only regular dependencies:
     
     npm install --omit=dev
     This will install only dependencies, and not devDependencies, regardless of the value of the NODE_ENV environment variable.
     
     If you use 6.x or an earlier version, you need to use the --only=prod flag instead.
     
     Note:
     Before v3.3.0 of npm (2015-08-13), the option was called --production, i.e.
     
     npm install --production
     You may also need --no-optional flag.

   NPM AUDIT

        With the humongous number of packages that have been published and can easily be installed, npm packages are susceptible to bad authors with malicious intentions.
        
        Realising that there was an issue in the ecosystem, the npm.js organisation came up with the idea of npm audit. They maintain a list of security loopholes that developers can audit their dependencies against using the npm audit command.
        
        npm audit gives developers information about the vulnerabilities and whether there're versions with remediations to upgrade to. For example,
        
        
        If the remediations are available in the next non-breaking version upgrades, npm audit fix can be used to upgrade the affected dependencies' versions automatically.
        
        
LIST Of Commonly used commands

    npm help 
    npm start help ==>for online documentation
    npm start -h ==>quick help
    
    npm root: Display npm root
    npm bin: Display npm bin
    npm repo :open repo->github in browser
    npm ls:display all dependencies from package.json
    
        npm ls --depth 1 :display first level dependency i.e no transitive dependency
        npm ls --dev:display dev dependency
        npm ls --prod :display prod dependency
        npm ls -global :list globally installed node package
       
    
    npm init
    npm i /install express
    npm i /install express -g
    npm i /install express --save
    npm i /install express --save-dev
    npm uninstall express
    npm audit: Run a security audit
    npm cache clean --force


###NPM COMMANDS LIST
####################################
    - npm : JavaScript package manager
    - npm access: Set access level on published packages
    - npm adduser: Add a registry user account
    - npm audit : Run a security audit
    - npm bin : Display npm bin folder
    - npm bugs: Bugs for a package in a web browser maybe
    - npm build: Build a package
    - npm cache: Manipulates packages cache
    - npm ci: Install a project with a clean slate
    - npm completion: Tab completion for npm
    - npm config: Manage the npm configuration files
    - npm dedupe: Reduce duplication
    - npm deprecate: Deprecate a version of a package
    - npm dist-tag: Modify package distribution tags
    - npm docs: Docs for a package in a web browser maybe
    - npm doctor: Check your environments
    - npm edit: Edit an installed package
    - npm explore: Browse an installed package
    - npm fund: Retrieve funding information
    - npm help: Search npm help documentation
    - npm help-search: Get help on npm
    - npm hook: Manage registry hooks
    - npm init: Create a package.json file
    - npm install: Install a package
    - npm install-ci-test: Install a project with a clean slate and run tests
    - npm install-test: Install package(s) and run tests
    - npm link: Symlink a package folder
    - npm logout: Log out of the registry
    - npm ls: List installed packages
    - npm org: Manage orgs
    - npm outdated: Check for outdated packages
    - npm owner: Manage package owners
    - npm pack: Create a tarball from a package
    - npm ping: Ping npm registry
    - npm prefix: Display prefix
    - npm profile: Change settings on your registry profile
    - npm prune: Remove extraneous packages
    - npm publish: Publish a package
    - npm rebuild: Rebuild a package
    - npm repo: Open package repository page in the browser
    - npm restart: Restart a package
    - npm root: Display npm root
    - npm run-script: Run arbitrary package scripts
    - npm search: Search for packages
    - npm shrinkwrap: Lock down dependency versions for publication
    - npm star: Mark your favorite packages
    - npm stars: View packages marked as favorites
    - npm start: Start a package
    - npm stop: Stop a package
    - npm team: Manage organization teams and team memberships
    - npm test: Test a package
    - npm token: Manage your authentication tokens
    - npm uninstall: Remove a package
    - npm unpublish: Remove a package from the registry
    - npm update: Update a package
    - npm version: Bump a package version
    - npm view: View registry info
    - npm whoami: Display npm username





