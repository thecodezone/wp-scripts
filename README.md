
CZ WordPress Scripts
--------------------

Helpful scripts for working with WordPress. 

## Setup

```
cd ~/DevKinsta/public/your-site
git clone git@github.com:thecodezone/wp-scripts.git scripts
cp scripts/wp-cli.yml.example wp-cli.yml
```

After copying wp-cli.yml to your root WordPress folder, open it and plugin your environment settings from DevKinsta and Kinsta. 

### WP CLI

### Environments

- *development:* Your local development environment. Likely DevKinsta. 
- *staging:* The staging environment. Likely Kinsta. 
- *producction:* The production environment. Likely Kinsta. 

Once you've configured [WP CLI](https://developer.wordpress.org/cli/commands/), you can run CLI commands in each environment by using an `@alias` (`development` `@staging`, `@production`). For example:

> wp @production user list 

## Scripts

### scripts/sync

The sync script copies databases, uploads and plugins between sites. 

> **Note:** theme files are not synced. Theme files should be downloaded using git.

The sync script
> scripts/sync [env] [env]

Sync from production to development
> scripts/sync production development

Sync from production to staging
> scripts/sync production/staging
