# Deployment Report

## Fixes in `docker-compose.yaml` File

### Issues Identified
- **Port Naming**: Used non-numeric values `"eighty:80"` and `"eight thousand"`.
- **Volume Path Error**: Typo in the `nginx.conf` path (`nginx.confi`).
- **Missing Build Contexts**: No build contexts specified for `nginx` and `python-app`.
- **Network Driver Typo**: `bridge` misspelled as `bridg`.
- **Invalid Option**: Unrecognized option `compelex_option`.

### Resolution Steps
- **Corrected Port Mapping**: Changed to `"80:80"` for `nginx` and `"8000"` for `python-app`.
- **Fixed Volume Path**: Corrected to `./nginx/nginx.conf:/etc/nginx/nginx.conf`.
- **Added Build Contexts**: Set `build: context: ./nginx` for `nginx` and `build: context: ./python` for `python-app`.
- **Corrected Network Driver**: Changed to `driver: bridge`.
- **Removed Invalid Option**: Deleted `compelex_option`.

---

## Fixes in `Python/Dockerfile`

### Issues Identified
- **Directory Naming Error**: `WORKDIR` specified as `/appp`.
- **File Copy Error**: Incorrect filename `appy.py` in `COPY` command.
- **Package Name Typo**: `netiface` should be `netifaces`.
- **Port Naming Issue**: Used `"eight thousand"` instead of numeric port `8000`.
- **Command Syntax Error**: Misspelled `python` as `pythn` in `CMD` command.

### Resolution Steps
- **Corrected Directory Name**: Changed `WORKDIR /appp` to `WORKDIR /app`.
- **Corrected File Copy Path**: Updated `COPY appy.py /app` to `COPY app.py /app`.
- **Fixed Package Name**: Changed `netiface` to `netifaces` in `RUN` command.
- **Updated Port Exposure**: Replaced `"eight thousand"` with `8000`.
- **Corrected Command Syntax**: Updated `CMD` to `["python", "app.py"]`.

---

## Fixes in `nginx/Dockerfile`

### Issues Identified
- **Typo in Base Image Tag**: Used `nginx:latests` instead of `nginx:latest`.
- **Configuration File Copy Error**: Incorrect filename `nginix.conf` instead of `nginx.conf`.
- **HTML Directory Path Error**: Misnamed directory `htmll` instead of `html`.
- **Port Naming Issue**: Used `"eighty"` instead of numeric `80`.
- **Syntax Error in Command**: Misspelled `daemon off;` as `daemon of;`.

### Resolution Steps
- **Corrected Image Tag**: Changed `nginx:latests` to `nginx:latest`.
- **Fixed Configuration File Name**: Updated `COPY nginix.conf /etc/nginx/nginx.conf` to `COPY nginx.conf /etc/nginx/nginx.conf`.
- **Commented Out HTML Copy Step**: Removed unnecessary line to streamline the file.
- **Updated Port Exposure**: Replaced `"eighty"` with `80`.
- **Corrected Command Syntax**: Changed `daemon of;` to `daemon off;`.

---

## Fixes in `nginx/nginx.conf`

### Issues Identified
- **Typo in `worker_processes` Directive**: Written as `worker_process`.
- **Typo in `worker_connections` Directive**: Incorrectly specified as `worker_connection`.
- **Typo in Mime Types Include**: Incorrectly referenced `mime.typess` instead of `mime.types`.
- **Typo in Default Type Directive**: Written as `default_typ` instead of `default_type`.

### Resolution Steps
- **Corrected Directive Names**: Updated `worker_process` to `worker_processes` and `worker_connection` to `worker_connections`.
- **Fixed Mime Types Path**: Changed `include /etc/nginx/mime.typess;` to `include /etc/nginx/mime.types;`.
- **Updated Default Type Directive**: Corrected `default_typ` to `default_type`.

### Screenshots- https://drive.google.com/drive/folders/1sQ60OxgbNR8WljuHUbYhvrZLBdu7EkaU?usp=sharing

