# dotnetcore-sample-application

![Docker Image CI](https://github.com/practical-lab/dotnetcore-sample-application/workflows/Docker%20Image%20CI/badge.svg)

This is an example console application using dotnetcore.

## Development

The project also includes .devcontainer which means vscode remote-container can be used. Once devcontainer is launched, you can also fire the debugeer.

## Docker

Build image and run container in local.

### Multistage build

```bash
docker build -t practical-lab/dotnetcore-sample-application/console-application:0.1 .
```

### Run Container

```bash
docker run --rm practical-lab/dotnetcore-sample-application/console-application:0.1
```

## Github package

Push image to remote docker registry.

### Login

```bash
docker login docker.pkg.github.com -u owner --password-stdin
```

* Note you need to login with personal access token which packages can be accessed.

```bash
cat ~/TOKEN.txt | docker login docker.pkg.github.com -u USERNAME --password-stdin
```

### Build docker image with docker.pkg.github.com

```bash
docker build -t docker.pkg.github.com/practical-lab/dotnetcore-sample-application/console-application:0.1 .
```

### Push GitHub Package Registry

```bash
docker push docker.pkg.github.com/practical-lab/dotnetcore-sample-application/console-application:0.1
```

### Change the tag

```bash
docker tag docker.pkg.github.com/practical-lab/dotnetcore-sample-application:0.1 docker.pkg.github.com/practical-lab/dotnetcore-sample-application/console-application:0.1
```

## References

- [Creating a personal access token for the command line](https://help.github.com/en/github/authenticating-to-github/creating-a-personal-access-token-for-the-command-line)
- [【GitHub Actions】GitHub Package Registryを利用して同一Dockerイメージをjobで共有する](https://qiita.com/homines22/items/6d28461d97906e42f57c)
