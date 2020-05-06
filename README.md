# dotnetcore-sample-application

This is an example console application using dotnetcore.

## Development

The project also includes .devcontainer which means vscode remote-container can be used. Once devcontainer is launched, you can also fire the debugeer.

## Docker

### Multistage build

```bash
docker build -t practical-lab/dotnetcore-sample-application:0.1 .
```

### Run Container

```bash
docker run --rm practical-lab/dotnetcore-sample-application:0.1
```
