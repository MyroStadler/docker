# docker

This is a hard hat area.

```bash
docker login
cd medium
docker build --no-cache -t myrostadler/medium:0.0.0 -t myrostadler/medium:latest .
docker push myrostadler/medium:0.0.0 && docker push myrostadler/medium:latest
```

