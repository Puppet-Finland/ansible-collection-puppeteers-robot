# robot_controller

An Ansible role for configuring a Podman host that can run Robot Framework
scripts in Podman containers.

## Requirements

Currently this role only supports RHEL 9 and derivatives.

## Dependencies

This role depends on the
[containers.podman](https://galaxy.ansible.com/ui/repo/published/containers/podman/)
collection.

## Role variables

Mandatory variables are:

* *robot_controller_user_password*: password for the robot user on the host
* *robot_controller_deployment_key*: SSH key used to fetch Robot scripts from a remote Git repository

Some variables are optional:

* *robot_controller_user:* username for the robot user on the host and in the container (default: robot)
* *robot_controller_user_home:* home directory for the robot user on the host (default: /home/robot)
* *robot_controller_user_group:* name of the user group for the robot user (default: robot)
* *robot_controller_uid:* uid for the robot user on the host and in the container (default: 1461)
* *robot_controller_gid:* gid for the robot group on the host and in the container (default: 1461)

To force building the Robot container image from scratch change this variable to *false*:

* *robot_controller_use_podman_cache:* true

## License

BSD-2-Clause
