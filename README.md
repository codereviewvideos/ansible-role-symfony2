# Ansible Role: Symfony 3

An Ansible role that can configure a Symfony 3 application.

The repo name is unfortunate.

Never heard of Ansible? It's an awesome system's automation / management tool - you can [watch a tutorial series on Ansible 1.x at CodeReviewVideos][1].

## Requirements

For the configuration with nginx the directories for sites must already exist (e.g. nginx has to be installed). For this I recommend geerlingguy.nginx role.

This role is aimed at Symfony 3 websites. I have no immediate requirement / plans for integration with Symfony 2. The endless march of progress must continue. Feel free to submit a pull request to add this in, if wanted, or fork freely.

PHP has to be installed for running various tasks (composer, bin/console, etc)
Composer has to be installed in PATH as "composer" for running "composer install". Again, I recommend geerlingguy roles for this.

## Role Variables

Available variables are listed below, along with default values:

```
symfony_web_server: "nginx"
symfony_web_server_user: "www-data"
symfony_web_server_group: "www-data"

symfony2_bash_completion: true

symfony_composer_install: true
symfony_clear_cache: true
```

## Dependencies

None

## Example Playbook

    - hosts: all
      roles:
        - { role: symfony2 }

## License

MIT



[1]: https://codereviewvideos.com/course/ansible-tutorial
