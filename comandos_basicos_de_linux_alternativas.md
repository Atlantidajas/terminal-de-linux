# Alternativas a los comandos básicos de Linux

## Bat vs. Cat

**Cat** son las siglas de _conCAt_ es un comando que nos permite ver el contenido de un archivo en el terminal sin utilizar un editor.

Por su parte, **Bat** (que se define como _cat con alas_) suple a _cat_ en todas sus funciones, añadiendo otras útiles como son el resaltado automático de sintaxis para un amplio número de lenguajes de programación y marcado, la integración con Git (destacando las modificaciones), la paginación automática o la opción de mostrar caracteres no imprimibles.

* Página principal del proyecto: [https://github.com/sharkdp/bat](https://github.com/sharkdp/bat) 

![bat01][bat01]


Instalar _Bat_ en Debian/Ubuntu/Linux Mint desde el repositorio:

```bash
sudo apt install bat
```

Mostrar el contenido del fichero _index.html_ (previamente utilizamos el comando _wget_ para descargarlo desde una ubicación en Internet):

```bash
# Descargar un fichero html de ejemplo en la carpeta /tmp
wget https://raw.githubusercontent.com/ics-software-engineering/bootstrap-example-intro/master/index.html

batcat index.html
```

**Nota**: para salir de la visualización del fichero pulsamos la tecla _q_.

## Exa vs. Ls

**Exa** es una herramienta construida en el lenguaje de programación _Rust_ y es una alternativa al comando **cd** (CHange directory, cambiar de directorio). Tiene un aspecto más colorido, algo que nos ayuda a diferenciar la información y tipos de archivos. También resalta aspectos como las propiedades, el tamaño, la fecha de modificación, usuario, grupo o inodos.

* Página principal del proyecto: [https://github.com/ogham/exa](https://github.com/ogham/exa) 

![exa01][exa01]

Instalar Exa en Debian/Ubuntu/Linux Mint desde código fuente:

```bash
# Instalar Rust
sudo apt-get install libgit2-dev cmake -y
curl https://sh.rustup.rs –sSf | sh
source $HOME/.cargo/env

# Descargar código fuente de exa
sudo apt install git -y
cd /tmp
git clone https://github.com/ogham/exa.git
cd exa

# Crea el ejecutable a partir del código fuente
cargo build
cargo test

# Copiar el ejecutable a una carpeta del sistema
cd target/debug
sudo cp exa /usr/local/bin/
```

Listar los ficheros y subdirectorios del directorio actual:

```bash
exa -l
```

Listar los ficheros y subdirectorios del directorio actual (muestra más información que la opción anterior):

```bash
exa -bghHliS
```

Lista los ficheros ordenados por tamaño:

```bash
exa -l --reverse --sort=size
```

Lista los archivos en forma de árbol (salida similar al comando _tree_):

```bash
exa -T
```

## Find vs. Fd

TODO



[bat01]: ./img/bat01.png "Bat - Alternativa al comando Cat"
[exa01]: ./img/exa01.png "Exa - Alternativa al comando Ls"