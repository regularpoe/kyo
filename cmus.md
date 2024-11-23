# TIL - cmus

## Set password and start cmus

```sh
> cmus
> :set passwd=password
> cmus --listen 0.0.0.0
```

## Check if cmus is running as it should `sudo netstat -tulpn | grep LISTEN`

```sh
> cmus-remote --server localhost --passwd password -C status
```

