# Introduction
With the config transpiler, cloud-config files can be converted to Ignition JSON format.

# Usage
```
curl -O docker-compose.yml https://github.com/Cube-Earth/dockerfile-tools-coreos-ct/docker-compose.yml
docker-compose pull

docker-compose run --rm coreos-tool << EOF
storage:
  files:
    - path: /home/core/.bashrc
      filesystem: root
      contents:
        inline: |
          . /usr/share/skel/.bashrc
          alias ll="ls -l"
      mode: 0644
      user:
        id: 500
      group:
        id: 501
EOF
```
# References
https://github.com/coreos/container-linux-config-transpiler
