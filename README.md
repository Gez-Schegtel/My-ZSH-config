# Mi Configuración de Zsh

Este repositorio contiene mi archivo de configuración personal para Zsh (`.zshrc`). Utilizo enlaces simbólicos para mantener este archivo bajo control de versiones mientras el sistema lo lee desde su ubicación habitual.

> ¡Acordate que el archivo de configuración tiene un puntito adelante, así que está "oculto"!

## Instalación

Para utilizar esta configuración en un nuevo sistema, sigue estos pasos:

1. **Clonar el repositorio:**
   ```bash
   git clone https://github.com/Gez-Schegtel/My-ZSH-config.git
	 ```

2. **Hacer un respaldo del `.zshrc` actual (si existe):**
   ```bash
   mv ~/.zshrc ~/.zshrc.backup
   ```

3. **Crear el enlace simbólico:**
   ```bash
   ln -s ~/.zshrc-repo/.zshrc ~/.zshrc
   ```

## Modificaciones
Puedes editar el archivo modificando el enlace simbólico en `~/.zshrc` o directamente en este repositorio. Los cambios se aplicarán en ambos lados.

