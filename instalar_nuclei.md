# Pasos para instalar nuclei correctamente

### 1. Instalar GO

#### Buscamos la versión de Go

https://go.dev/doc/install

#### Descargamos GO

`wget https://go.dev/dl/go1.22.2.linux-amd64.tar.gz`

#### Eliminamos, si es que la hay, cualquier versión instalada de GO y además descomprimimos el archivo descargado en el paso anterior:

`rm -rf /usr/local/go && tar -C /usr/local -xzf go1.22.2.linux-amd64.tar.gz`

### 2. Hacemos un export del PATH de Go y lo pegamos en el archivo .profile para que prevalezca como parte del PATH:

`echo 'export PATH=$PATH:/usr/local/go/bin' >> .profile`

### 3. Hacemos un source .profile para que la shell actual tome ese cambio.

`source .profile`

### 4. Revisamos que se haya instalado correctamente con

`go version`

### 5. Instalamos nuclei cómo dice en su repositorio oficial:

`go install -v github.com/projectdiscovery/nuclei/v3/cmd/nuclei@latest`

### 6. Lo movemos a la carpeta de /usr/local/go/bin para que funcione

`mv go/bin/nuclei /usr/local/go/bin/`

¡Y listo!, tenemos nuclei andando en nuestra máquina.
