# Mi configuración de Zsh

Mi archivo de configuración personal de Zsh (`.zshrc`), con control de versiones.

El archivo real vive en este repositorio y `~/.zshrc` es un **enlace simbólico** que apunta a él. Así Zsh lo lee desde su lugar de siempre, pero git lo versiona sin que mi carpeta personal tenga que ser un repositorio.

> 💡 El archivo empieza con un punto, así que está "oculto". Para verlo: `ls -a`.

## Instalación

1. **Clonar el repositorio en `~/.zshrc-repo`:**
   ```bash
   git clone https://github.com/Gez-Schegtel/My-ZSH-config.git ~/.zshrc-repo
   ```

2. **Hacer un respaldo del `.zshrc` actual** (si no existe, este paso da error y se puede saltear):
   ```bash
   mv ~/.zshrc ~/.zshrc.backup
   ```

3. **Crear el enlace simbólico:**
   ```bash
   ln -s ~/.zshrc-repo/.zshrc ~/.zshrc
   ```

4. **Aplicar la configuración:** abrí una terminal nueva o ejecutá `exec zsh`.

Para comprobar que quedó bien:
```bash
ls -l ~/.zshrc
# lrwxrwxrwx ... /home/usuario/.zshrc -> /home/usuario/.zshrc-repo/.zshrc
```

> `ln -s` toma primero el archivo real y después el lugar donde se crea el enlace: `ln -s DESTINO ENLACE`.

## Modificar la configuración

Editá `~/.zshrc` como siempre. Como es un enlace, el cambio se hace directamente sobre el archivo del repositorio.

Para guardar la versión:
```bash
cd ~/.zshrc-repo
git add .zshrc
git commit -m "Describe el cambio"
git push
```

## Desinstalar

Se borra el enlace (no el archivo del repositorio) y se restaura el respaldo:
```bash
rm ~/.zshrc
mv ~/.zshrc.backup ~/.zshrc
```

## ⚠️ Antes de subir cambios

No pongas contraseñas, tokens ni claves de API en el `.zshrc`: este repositorio es público y quedarían expuestos en el historial de git. Si necesitás variables secretas, guardalas en un archivo aparte que no esté en el repositorio y cargalo desde el `.zshrc`.
