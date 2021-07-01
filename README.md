# FastAPI Docker Image

This repo contains a `Dockerfile` to build
a Linux [Docker](https://www.docker.com) image containing the Microsoft
[SQL Server Tools](https://docs.microsoft.com/en-us/sql/linux/sql-server-linux-setup-tools?view=sql-server-linux-2017), Microsoft's
[ODBC driver for SQL Server](https://docs.microsoft.com/en-us/sql/connect/odbc/microsoft-odbc-driver-for-sql-server?view=sql-server-linux-2017)
and a working Python 3.8 environment based on the
[Mamba](https://github.com/mamba-org/mamba) environment management system.


## Usage

To instantiate an ephemeral container from the image, mount the current
directory within the container, and open a bash prompt within the `base` conda
Python environment:

```bash
docker run -it --rm -v $(pwd):/home/docker/work blueogive/fastapi-docker:latest
```

## Relevant Documentation

By default, ou will be running as a regular user, `docker`, within the container.
If you opt to run as `root` within the container, the image includes the
[gosu](https://github.com/tianon/gosu) utility, allowing you to conveniently 
execute commands as other, less privileged, users:

```bash
gosu 1000:100 dtexec /F path/to/package
```

Contributions are welcome.
