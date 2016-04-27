# Ansible Role: Symfony 2

An Ansible role that can configure a Symfony (2, or 3) application.

Never heard of Ansible? It's an awesome system's automation / management tool - you can [watch a tutorial series on Ansible 1.x at CodeReviewVideos][1].

## Requirements

For the configuration with nginx the directories for sites must already exist (e.g. nginx has to be installed). For this I recommend geerlingguy.nginx role.

This role is aimed at Symfony 3 websites. I have no immediate requirement / plans for integration with Symfony 2. The endless march of progress must continue. Feel free to submit a pull request to add this in, if wanted, or fork freely.

PHP has to be installed for running various tasks (composer, bin/console, etc)
Composer has to be installed in PATH as "composer" for running "composer install". Again, I recommend geerlingguy roles for this.

## Role Variables

Available variables are listed below, along with default values:

```
symfony_project_root: "/var/www/{{ ansible_fqdn }}"

symfony_web_server: "nginx"
symfony_web_server_user: "www-data"
symfony_web_server_group: "www-data"

symfony2_bash_completion: true

symfony_composer_install: true
symfony_clear_cache: true

# not very useful for customisation, but ok for the needs of one site per box
# don't need ansible_fqdn here, as likely the symfony2_project_root has been overridden in the playbook or vars
symfony_cache_path: "{{ symfony_project_root }}/var/cache"
symfony_log_path: "{{ symfony_project_root }}/var/logs"
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