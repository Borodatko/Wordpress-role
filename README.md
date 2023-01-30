Wordpress
=========

Ansible role for WordPress installation & configuration.


Dependencies
------------

 - RHEL7-based OS


Role Variables
--------------
| Name | Description | Type | Default Value|
|------|-------------|------|---------|
| ***defaults/main.yml*** |
| bin_path | path to binary | string | /usr/local/bin |
| tmp_path | temporary path | string | /tmp |
| ***yum.yml*** |
| repo_url | remi repository url | string | http://rpms.remirepo.net/enterprise/remi-release-7.rpm |
| repo_path | path to repositories directory | string | /etc/yum.repos.d |
| rpm_package | remi rpm package | string | {{ tmp_path }}/remi-release-7.rpm |
| ***php.yml*** |
| fpm_path | php-fpm directory | string | /etc/php-fpm.d |
| php_path | php directory | string | /var/lib/php |
| ***wordpress.yml*** |
| wordpress_version | wordpress version | string | 6.0 |
| wordpress_archive | downloaded archive | string | {{ tmp_path }}/wordpress-{{ wordpress_version }}.tar.gz |
| wordpress_tmp_path | temporary path | string | {{ tmp_path }}/wordpress |
| upload_dir | wordpress upload directory | string | {{ www_path }}/wp-content/uploads |
| wp_url | wp-cli download url | string | https://raw.githubusercontent.com/wp-cli/builds/gh-pages/phar/wp-cli.phar |
| username | local admin user | string | centos |
| nginx_path | path to nginx config | string | /etc/nginx/conf.d |
| www_path | path to webserver configs | string | /var/www/html |
| ***exporter.yml***|
| arch | architecture  | string | linux-amd64 |
| exporter_version | prometheus node exporter version | string | 1.3.1 |
| node_exporter_archive | downloaded archive | string | {{ tmp_path }}/node_exporter-{{ node_exporter_version }}.{{ arch }}.tar.gz |
| node_exporter_path_tmp | temporary path | string | {{ tmp_path }}/node_exporter-{{ node_exporter_version }}.{{ arch }} |
| systemd_path | systemd unit file path | string | /etc/systemd/system |
| ***template variables*** |
| server_name | webserver name | string | CHANGEME |
| db_host | mysql database ip address | string | CHANGEME |


Example Playbook
----------------

An example of using role:

```yaml
- name: Wordpress Provisioning
  hosts: wordpress
  roles:
    - Wordpress-role
```


License
-------

BSD-3-Clause


Author Information
------------------

Borodatko
