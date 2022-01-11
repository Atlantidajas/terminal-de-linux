# Alternativas a los comandos básicos de Linux

## Cat vs. Bat

**Cat** son las siglas de _conCAt_ es un comando que nos permite ver el contenido de un archivo en el terminal sin utilizar un editor.

Por su parte, **bat** (que se define como _cat con alas_) suple a _cat_ en todas sus funciones, añadiendo otras útiles como son el resaltado automático de sintaxis para un amplio número de lenguajes de programación y marcado, la integración con Git (destacando las modificaciones), la paginación automática o la opción de mostrar caracteres no imprimibles.

Instalar Bat:

```bash
sudo apt install bat
```

Mostrar el contenido del fichero index.html (previamente utilizamos el comando _wget_ para descargarlo)

```bash
wget https://raw.githubusercontent.com/ics-software-engineering/bootstrap-example-intro/master/index.html
batcat index.html
```

## Cd vs. Exa (Z)

Posiblemente el comando más usado a la hora de trabajar con la terminal, **cd** (siglas en inglés de "cambiar de directorio") hace exactamente eso, permitirnos ir cambiando de directorio (carpeta) para ejecutar los comandos pertinentes en cada uno.

![exa_01][exa_01]


Instalar Exa:

```bash
sudo apt-get install libgit2-dev cmake -y
curl https://sh.rustup.rs –sSf | sh
source $HOME/.cargo/env

sudo apt install git -y
git clone https://github.com/ogham/exa.git
cd exa

cargo build
cargo test
cd target/debug

sudo cp exa /usr/local/bin/
```

Listar los ficheros del directorio actual:

```bash
exa -l
```

## Find vs. Fd

TODO



[exa_01]: ./img/exa01.png "Exa - Alternativa al comando Ls"