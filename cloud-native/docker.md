# Intro

Docker - containerization platform

---

## List Images

```bash {copyable}
docker images
```

iTerm2 Plugin Aliases

```bash {copyable}
dils
```

---

## List Containers

```bash {copyable}
docker ps
```

```bash {copyable}
docker ps -a
```

iTerm2 Plugin Aliases

```bash {copyable}
dps
```

```bash {copyable}
dpsa
```

---

## Delete Image

```bash {copyable}
docker rmi foo:1.0.0
```

iTerm2 Plugin Aliases

```bash {copyable}
dirm foo:1.0.0
```

---

## Delete Container

foo is container id

```bash {copyable}
docker rm foo
```

iTerm2 Plugin Aliases

```bash {copyable}
drm foo
```

---

## Tag Image

```bash {copyable}
docker tag src:1.0.0 dest:1.0.0
```

iTerm2 Plugin Aliases

```bash {copyable}
dit src:1.0.0 dest:1.0.0
```

---

## Push Image

```bash {copyable}
docker push foo:1.0.0
```

iTerm2 Plugin Aliases

```bash {copyable}
dipu foo:1.0.0
``` 
