---
name: memoria-central-setup
description: Manual portable para instalar o reparar un sistema de memoria central y enrutado por proyecto en OpenCode. Usar cuando se quiera replicar este entorno en otra máquina o reconstruirlo.
---

# Memoria central — setup portable

Este skill es un **manual de instalación**, no la memoria en vivo.

La memoria viva va en `AGENTS.md` (global y de carpeta), porque OpenCode la carga sola en cada sesión. Un skill solo se lee cuando se invoca o cuando encaja con la tarea: **no sirve para "recordar siempre"**.

## Qué deja instalado

- `~/central/MEMORIA_GLOBAL.md`: historial y memoria central.
- `~/central/AGENTS.md`: reglas de enrutado al abrir desde `central`.
- `~/central/proyectos/<proyecto>/AGENTS.md`: uno por proyecto (por ejemplo: web, trading, clases, automatizaciones).
- En `~/.config/opencode/AGENTS.md`: leer `MEMORIA_GLOBAL.md` al iniciar, actualizar el proyecto correspondiente y crear carpeta si aparece uno nuevo.
- Opcional: una carpeta `~/central/ideas/` para ideas sueltas, separada por proyecto y con una carpeta general.

## Pasos

1. Crear la carpeta central y los archivos `.md` indicados arriba.
2. En `MEMORIA_GLOBAL.md` guardar: quién es el usuario, proyectos, historial breve y regla de enrutado.
3. En `central/AGENTS.md` poner:
   - leer `MEMORIA_GLOBAL.md`;
   - escribir en `proyectos/<nombre>/AGENTS.md` según el proyecto;
   - si aparece un proyecto nuevo, crear su carpeta y su `AGENTS.md`;
   - reflejar lo importante también en la memoria global.
4. Agregar en `~/.config/opencode/AGENTS.md` la sección "Memoria central y enrutado por proyecto".
5. Abre OpenCode siempre desde `~/central` (`cd ~/central && opencode`) para que cargue las reglas de enrutado.
6. Verificar con: `find ~/central -maxdepth 3 -type f -o -type d | sort`.

## Elegir el modelo para ordenar archivos

Para ordenar, mover y borrar no hace falta un modelo grande: usa un modelo liviano de los disponibles en tu instalación (míralos con `/models`).

Si quieres fijarlo, hay dos formas:

- Una orden con `model:` en el frontmatter: `~/.config/opencode/commands/rapido.md`.
- Un subagente con `model:` en el frontmatter: `~/.config/opencode/agents/rapido.md`.

Sin eso, el modelo se elige desde la interfaz con `/models`.

## Reglas que no se cambian

- No borrar nada sin confirmación explícita del usuario.
- Responder en el idioma del usuario, directo y sin jerga innecesaria.
- La memoria viva siempre en `AGENTS.md`, nunca solo en un skill.

---
Hagen Laboratorio de IA. Úsalo, modifícalo y compártelo libremente.
