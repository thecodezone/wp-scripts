
<p align="center">
  <a href="https://codezone.io/">
    <img alt="CodeZone" src="https://prismic-io.s3.amazonaws.com/codezone/5f2169a6-d854-478d-b0d4-93e8b18d0bb7_cz-lines-orange-dark.svg" height="100">
  </a>
</p>


CZ WordPress Scripts
--------------------

Helpful scripts for working with WordPress. 

## Setup

```
cd ~/your-wordpress-install-dir
git clone git@github.com:thecodezone/wp-scripts.git scripts
cp scripts/wp-cli.yml.example wp-cli.yml
```

After copying wp-cli.yml to your root WordPress folder, open it and plug in your environment settings from Kinsta or your another web host. 

### WP CLI

### Environments

- *development:* Your local development environment. Likely Docker. 
- *staging:* The staging environment. Likely Kinsta. 
- *production:* The production environment. Likely Kinsta. 

Once you've configured [WP CLI](https://developer.wordpress.org/cli/commands/), you can run CLI commands in each environment by using an `@alias` (`development` `@staging`, `@production`). For example:

> wp @production user list 

## Scripts

### scripts/setup

Configure the WP-CLI so that you can run commands in each environment.

> scripts/setup

### scripts/sync

The sync script copies databases, uploads and plugins between sites. 

> **Note:** theme files are not synced. Theme files should be downloaded using git.

The sync script
> scripts/sync [env] [env]

Sync from production to development if your development environment is remote or Docker-based
> scripts/sync production development

Sync from production to development if your development runs environment is on your local machine outside of a VM
> scripts/sync production development --local

Sync from production to staging
> scripts/sync production/staging

### scripts/clonein

The clonein script clones a git repository into an existing directory. This is useful for WordPress
sites with the git root in the root of the WordPress install instead of in the theme folder.

Clone into your existing directory. 

> scripts/clonein git@github.com:thecodezone/your-repo.git .

Clone a theme into a fresh WordPress install.

> wp core download your-folder
> scripts/clonein git@github.com:thecodezone/your-repo.git your-folder
