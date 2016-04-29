# Ansible Role: zplug

Install zplug plugin in Linux, OSX.

## Requirements

Requiring git to clone the [zplug](https://github.com/b4b4r07/zplug) plugin.

## Role Variables

Available variables are listed below, along with default values (see defaults/main.yml):

    zplug_zshrc_path: /home/{{ zplug_user }}/.zplug

The path where zplug is installed.

    zplug_user: vagrant

Name of the user that should own the `{{ zplug_zshrc_path }}`, as would be fed to chown. The default is `vagrant`.

    zplug_group: {{ zplug_user }}

Group of the user that should own the `{{ zplug_zshrc_path }}`, as would be fed to chown. The default is `{{ zplug_user }}`.

    zplug_zshrc_content: |
        zplug "plugins/git", from:oh-my-zsh, if:"which git"

The content of `.zshrc` file. Please check [zplug](https://github.com/b4b4r07/zplug#example) document to fill in the content.

## Dependencies

geerlingguy.git

## Example Playbook

    - hosts: all
      vars_file:
        - vars/main.yml
      roles:
         - yeshacker.zplug

Inside `vars/main.yml`:
    zplug_zshrc_path: /home/vagrant/.zplug
    zplug_user: vagrant
    zplug_zshrc_content: |
      zplug "plugins/git", from:oh-my-zsh, if:"which git"
      zplug "themes/agnoster", from:oh-my-zsh

## License

MIT

## Author Information

This role was modified by yeshacker to be used in OSX originally created in 2016 by [Steven Ho](http://stevenjlho.github.io/)
