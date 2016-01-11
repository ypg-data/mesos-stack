# Mesos

Install the Mesos package from the Mesosphere package repository and configure
each node to use the Mesos DNS nodes as name server. Finally, disables services
automatically installed by the Mesos package and not used by the node based on
its assigned roles.

## Configuration

Defaults are set in `defaults/main.yml`.

 - `mesos_version`:

   This generally follows the Mesos version used by the DCOS community edition.
   `*` is automatically added after the version when installing, which permits
   to leave out version suffixes added by Mesosphere. Use `apt-policy mesos` to
   see available versions.  To install the latest use `latest`, to install most
   recent 0.11 release use `0.11`.

   Example:
   ```yaml
   mesos_version: "0.25.0"
   ```

 - `host_mappings`

   List defining additional `/etc/hosts` mappings. Each entry should define `ip`
   and `name`.
   
   Example:
   ```yaml
   host_mappings:
     - { ip: '52.7.220.1', name: 'docker-registry.example.org' }
   ```