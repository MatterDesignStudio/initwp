Init WP
============

A Wordpress development starter using composer

## Getting started

1. Clone this repo to your project folder
2. Modify the composer.json file to meet your requirements for the particular project (ie add/remove plugins, change the theme, etc)
 - You can find plugin paths and versions on http://wpackagist.org/ however as a general rule, it uses the same naming convention as what is on Wordpress and we should always use "dev-trunk" to get latest version.
3. Run the following commands in the project folder:
```bash
composer install
npm install
grunt
```
4. "git init" the project and commit project to repo.

That's it! Enjoy :)

__Make life simpler:__

Who wants to type all those commands everytime you want to create a project right? Heres a .bash_profile function to do it ;)

```bash
initwp() {
    git clone https://github.com/MatterDesignStudio/initwp.git $1;
    cd $1;
    composer install --prefer-dist -vvv --profile;
    npm install;
    grunt;
}
```

If you find your on a machine that has permission issues when running this, try this one instead:

```bash
initwp() {
    git clone https://github.com/MatterDesignStudio/initwp.git $1;
    cd $1;
    sudo composer install --prefer-dist -vvv --profile;
    sudo npm install;
    sudo grunt;
    cd ..;
    sudo chown -R newcaledonia:admin $1;
    cd $1;
}
```

Then just type in the folder you store all your projects (this process will create the project folder for you):

```bash
initwp project-name
```