<!-- l10n-sync: source-file="README.md" -->
🌐 [English](README.md) | Español | [Português (Brasil)](README.pt_BR.md) | [한국어](README.ko.md)

# 🎮 Mona Mayhem

**Taller de VS Code y GitHub Copilot CLI** — Construye una Arena de Batalla de Contribuciones de GitHub

Una plantilla de taller para construir un sitio web con temática de arcade retro con Astro que compara los gráficos de contribuciones de GitHub de dos usuarios. Este es el **punto de partida**: construirás la aplicación paso a paso con GitHub Copilot.

![Mona Mayhem Screenshot](https://github.com/user-attachments/assets/5eca79e2-cb9f-4e93-aa0d-23666ebde3b7)
*Lo que construirás al final del taller*

## 📚 Taller

El taller admite dos itinerarios: sigue el que mejor se adapte a tu forma de trabajar.

- **Itinerario de VS Code** — Chat, Plan Mode, Agent Mode, background agents y flujos de revisión integrados en el editor.
- **Itinerario de CLI** — `copilot`, contexto `@file`, `/plan`, ediciones autónomas, `/fleet`, `/delegate` y `/review`.

| Parte | Título | Enfoque de Copilot |
|-------|--------|--------------------|
| [00](workshop/es/00-overview.md) | Visión general | Selección de itinerario y objetivos de aprendizaje |
| [01](workshop/es/01-setup.md) | Configuración e ingeniería de contexto | Instrucciones, permisos y configuración del entorno |
| [02](workshop/es/02-plan-and-scaffold.md) | Planificar y estructurar | Planificación de la API y la arquitectura de páginas |
| [03](workshop/es/03-agent-mode.md) | Construir el juego | Implementación agéntica e iteración |
| [04](workshop/es/04-design-vibes.md) | Temas design-first | Planificación e implementación del diseño visual |
| [05](workshop/es/05-polish.md) | Pulido y trabajo en paralelo | Paralelismo, revisiones y pasadas de calidad |
| [06](workshop/es/06-bonus.md) | Bonus y extensiones | Ideas de funciones abiertas y experimentos adicionales con Copilot |

## 🚀 Inicio rápido

1. **Crea primero tu propio repositorio** de una de estas dos formas:
   - haciendo clic en **Use this template** para crear un repositorio nuevo, o
   - haciendo un fork de este repositorio.
2. Elige tu itinerario de taller:
   - **VS Code:** clona tu repositorio y ábrelo en VS Code.
   - **GitHub Copilot CLI:** clona tu repositorio en local, instala `copilot` y trabaja desde tu terminal.
3. Sigue la [guía del taller](workshop/es/00-overview.md)

## Requisitos previos

### Compartidos

- GitHub Copilot (Pro, Business o Enterprise)
- Git
- Node.js

### Itinerario de VS Code

- VS Code v1.107+
- Extensión de GitHub Copilot con la sesión iniciada

### Itinerario de CLI

- GitHub Copilot CLI (`copilot`)
- Node.js 22+ si vas a instalar la CLI mediante `npm install -g @github/copilot`
- O Homebrew / WinGet si prefieres instalarla con un gestor de paquetes nativo

## Stack tecnológico

- **Framework**: [Astro](https://astro.build/) v6
- **Runtime**: Node.js con el adaptador [@astrojs/node](https://docs.astro.build/en/guides/integrations-guide/node/)
- **Fuente**: Press Start 2P (fuente de estética retro)
- **API**: API del gráfico de contribuciones de GitHub

## Notas de despliegue

### Configuración actual de GitHub Pages

El flujo de trabajo en `.github/workflows/deploy.yml` despliega actualmente el contenido estático del taller y la documentación desde `docs/` y `workshop/` en GitHub Pages. No compila ni despliega la aplicación Astro de `src/`.

### Si quieres desplegar la aplicación Astro en GitHub Pages

GitHub Pages es un alojamiento estático, por lo que la aplicación Astro debe usar salida estática.

1. Cambia `output` en `astro.config.mjs` de `server` a `static`.
2. Elimina el adaptador de Node (`@astrojs/node`) de `astro.config.mjs` y de `package.json`.
3. Actualiza el flujo de trabajo de GitHub Actions para que ejecute `npm ci` y `npm run build`, y luego suba `dist/` como artefacto de Pages.
4. Si despliegas en una página de proyecto (`https://<user>.github.io/<repo>/`), configura `site` y `base` en `astro.config.mjs`.

Si planeas mantener las rutas de la API en ejecución en producción, usa una plataforma con servidor en lugar de GitHub Pages (por ejemplo, Vercel, Netlify o un host de Node).

## Licencia

MIT
