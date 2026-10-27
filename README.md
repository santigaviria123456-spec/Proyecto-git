# Proyecto Git — Control de versiones

Proyecto académico de práctica para la tarea **“Control de Versiones con Git y GitHub”**. Contiene una página web sencilla y un historial Git con ramas, fusiones y un conflicto resuelto.

## Archivos

- `index.html`: estructura semántica de la página en español.
- `styles.css`: estilos responsivos.
- `README.md`: documentación y guía de publicación.
- `.git/`: historial local completo, ramas y commits de la práctica.

## Ver el sitio

Abre `index.html` en el navegador. No requiere instalación ni dependencias.

## Evidencia del historial

Desde esta carpeta ejecuta:

```bash
git log --oneline --graph --all
git branch
git status
```

El historial local incluye las ramas `main`, `feature/header`, `contenido`, `footer` y `prueba-reset`. El conflicto del pie de página se resolvió combinando el año y el correo de contacto.

## Publicar en tu propia cuenta de GitHub

1. Entra en https://github.com/new.
2. Crea un repositorio público llamado `proyecto-git`. Déjalo vacío: no agregues README, licencia ni `.gitignore` desde GitHub.
3. En la terminal, desde esta carpeta, configura el nombre y correo reales que usas en GitHub:

   ```bash
   git config user.name "Tu Nombre"
   git config user.email "tu-correo-de-github"
   ```

4. Agrega el remoto usando tu usuario real y publica `main`:

   ```bash
   git remote add origin https://github.com/TU_USUARIO/proyecto-git.git
   git push -u origin main
   ```

5. Publica las ramas de práctica que aún no estén en GitHub:

   ```bash
   git push -u origin feature/header
   git push -u origin contenido
   git push -u origin footer
   git push -u origin prueba-reset
   ```

6. Para cumplir el requisito de Pull Requests desde GitHub, crea un PR desde `feature/header` hacia `main` y fusiónalo en la interfaz. Repite el procedimiento para `contenido` y `footer` si GitHub permite esos PR con el historial ya integrado. Si el PR no puede crearse porque los cambios ya están presentes en `main`, crea una rama nueva con un cambio pequeño, publícala y abre/fusiona ese PR para mostrar el flujo de trabajo.

> **Importante:** el repositorio se entrega preparado localmente, pero el enlace público de GitHub solo existirá después de publicarlo desde una cuenta real. No se ha creado ni simulado una URL pública.

## Comandos de actualización y recuperación

```bash
git fetch origin
git log HEAD..origin/main --oneline
git pull origin main
git checkout -- index.html
```

Para practicar `reset` de forma segura, usa una rama temporal y evita hacerlo sobre `main`:

```bash
git switch -c practica-reset main
# Haz un cambio y crea un commit antes de probar reset.
git reset --soft HEAD~1
# Devuelve la rama al estado publicado cuando termines, si corresponde.
```

## Antes de entregar

- Publica el repositorio y copia la URL real de GitHub en Q10.
- Adjunta el ZIP completo, que incluye la carpeta `.git`.
- Opcional: toma una captura de `git log --oneline --graph --all`.
