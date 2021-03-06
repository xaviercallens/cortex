# CLI commands

_WARNING: you are on the master branch, please refer to the docs on the branch that matches your `cortex version`_

## deploy

```text
create or update apis

Usage:
  cortex deploy [CONFIG_FILE] [flags]

Flags:
  -e, --env string   environment (default "default")
  -f, --force        override the in-progress api update
  -h, --help         help for deploy
  -r, --refresh      re-deploy with cleared cache and rolling updates
```

## get

```text
get information about apis

Usage:
  cortex get [API_NAME] [flags]

Flags:
  -e, --env string   environment (default "default")
  -h, --help         help for get
  -w, --watch        re-run the command every second
```

## logs

```text
stream logs from an api

Usage:
  cortex logs API_NAME [flags]

Flags:
  -e, --env string   environment (default "default")
  -h, --help         help for logs
```

## refresh

```text
restart all replicas for an api (witout downtime)

Usage:
  cortex refresh API_NAME [flags]

Flags:
  -e, --env string   environment (default "default")
  -f, --force        override the in-progress api update
  -h, --help         help for refresh
```

## predict

```text
make a prediction request using a json file

Usage:
  cortex predict API_NAME JSON_FILE [flags]

Flags:
      --debug        predict with debug mode
  -e, --env string   environment (default "default")
  -h, --help         help for predict
```

## delete

```text
delete an api

Usage:
  cortex delete API_NAME [flags]

Flags:
  -e, --env string   environment (default "default")
  -f, --force        delete the api without confirmation
  -h, --help         help for delete
  -c, --keep-cache   keep cached data for the api
```

## cluster up

```text
spin up a cluster

Usage:
  cortex cluster up [flags]

Flags:
  -c, --config string   path to a cluster configuration file
  -e, --env string      environment (default "default")
  -h, --help            help for up
```

## cluster info

```text
get information about a cluster

Usage:
  cortex cluster info [flags]

Flags:
  -c, --config string   path to a cluster configuration file
  -d, --debug           save the current cluster state to a file
  -e, --env string      environment (default "default")
  -h, --help            help for info
```

## cluster update

```text
update a cluster

Usage:
  cortex cluster update [flags]

Flags:
  -c, --config string   path to a cluster configuration file
  -e, --env string      environment (default "default")
  -h, --help            help for update
```

## cluster down

```text
spin down a cluster

Usage:
  cortex cluster down [flags]

Flags:
  -c, --config string   path to a cluster configuration file
  -h, --help            help for down
```

## version

```text
print the cli and cluster versions

Usage:
  cortex version [flags]

Flags:
  -e, --env string   environment (default "default")
  -h, --help         help for version
```

## configure

```text
configure the cli

Usage:
  cortex configure [flags]

Flags:
  -k, --aws-access-key-id string       set the aws access key id without prompting
  -s, --aws-secret-access-key string   set the aws secret access key without prompting
  -e, --env string                     environment (default "default")
  -h, --help                           help for configure
  -o, --operator-endpoint string       set the operator endpoint without prompting
  -p, --print                          print the configuration
```

## completion

```text
generate bash completion scripts

add this to your bashrc or bash profile:
  source <(cortex completion)
or run:
  echo 'source <(cortex completion)' >> ~/.bash_profile  # mac
  echo 'source <(cortex completion)' >> ~/.bashrc  # linux

this will also add the "cx" alias (note: cli completion requires the bash_completion package to be installed on your system)

Usage:
  cortex completion [flags]

Flags:
  -h, --help   help for completion
```
