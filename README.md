<p align="center">
  <img src="./imgs/banner_00.jpg" alt="🌐 Web & Database — 42 Outer Core" width="100%">
</p>

Proyectos del dominio **Web y bases de datos** del currículo Outer Core en **[42 Málaga](https://www.42malaga.com/)**: aplicaciones full-stack, arquitectura MVC, Docker y seguridad web (OWASP).

[![42](https://img.shields.io/badge/42-Málaga-00babc?style=for-the-badge&logo=42)](https://www.42malaga.com/)
[![PHP](https://img.shields.io/badge/PHP-8.2-777BB4?style=for-the-badge&logo=php&logoColor=white)](https://www.php.net/)
[![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)](https://docs.docker.com/)
[![MySQL](https://img.shields.io/badge/MySQL-8.0-4479A1?style=for-the-badge&logo=mysql&logoColor=white)](https://dev.mysql.com/doc/)

> Este directorio es el repositorio **[42_web_database](https://github.com/STC71/42_web_database)** y, en el monorepo **[42_Outer_Core](https://github.com/STC71/42_Outer_Core)**, aparece como **submódulo** `web_database/`.

---

## Clonar correctamente

```bash
# Solo este dominio
git clone --recurse-submodules https://github.com/STC71/42_web_database.git

# Monorepo Outer Core (incluye este submódulo)
git clone --recurse-submodules https://github.com/STC71/42_Outer_Core.git
cd 42_Outer_Core
git submodule update --init --recursive
```

Sin `--recurse-submodules`, la carpeta `web_database/` puede quedar vacía o incompleta.

---

## Proyectos

| Proyecto | Tipo | Estado | Entrada |
|----------|------|--------|---------|
| **[Camagru](./camagru/)** | App web full-stack (tipo Instagram) | ✅ Completado + bonus | [README](./camagru/README.md) · [QUICKSTART](./camagru/QUICKSTART.md) |
| **[Darkly](./darkly/)** | Auditoría de seguridad web | ✅ Completado + bonus | [README](./darkly/README.md) |

---

## 📸 Camagru

Aplicación web **sin framework PHP** (requisito de evaluación): captura con webcam, stickers, subida de archivos, galería pública, likes, comentarios, autenticación con verificación por email y preferencias de usuario. Containerización Docker (“works as is”).

### Funcionalidad alineada al subject / eval

| Área | Contenido |
|------|-----------|
| Auth | Registro, email de verificación, login/logout, reset de contraseña |
| Editor | Webcam o upload, stickers, composición **en el servidor** (GD) |
| Galería | Pública, likes y comentarios (sesión), paginación / scroll |
| Notificaciones | **Email al autor de la foto solo cuando hay un comentario nuevo** (no por like); preferencia `notify_comments` activa por defecto y desactivable en Ajustes |
| Seguridad | `password_hash`, PDO + prepared statements, CSRF, escape XSS |
| Bonus | AJAX likes/comentarios, preview + drag del sticker, infinite scroll, **GIF animado (Imagick)** |
| Extra | i18n ES/EN/PT/DE/FR (banderas), Makefile, `test_auto.sh` / `test_eval.sh`, baja de cuenta opcional |

### Stack

- **Backend:** PHP 8.2, MVC propio (`app/controllers`, `models`, `views`, `core`)  
- **BD:** MySQL 8, PDO  
- **Frontend:** JavaScript vanilla, HTML5/CSS3  
- **DevOps:** Docker Compose (web + db + phpMyAdmin)

### Arranque rápido

```bash
cd camagru
make setup          # o cp .env.example .env
make all            # build + up
# App: http://localhost:8080
make test-full      # suite automática
make ext            # pdo_mysql / gd / imagick
```

Guía detallada: **[camagru/QUICKSTART.md](./camagru/QUICKSTART.md)**.

### Documentación en el árbol de Camagru

| Documento | Uso |
|-----------|-----|
| [README.md](./camagru/README.md) | Visión general y mapa de docs |
| [QUICKSTART.md](./camagru/QUICKSTART.md) | Docker, Mailtrap, permisos |
| [COMPLIANCE.md](./camagru/COMPLIANCE.md) | Checklist subject / hoja de evaluación |
| [PROJECT_OVERVIEW.md](./camagru/PROJECT_OVERVIEW.md) | Arquitectura |
| [php.md](./camagru/php.md) · [js.md](./camagru/js.md) · [css.md](./camagru/css.md) · [sql.md](./camagru/sql.md) · [docker.md](./camagru/docker.md) | Guías tech con ejemplos del repo |
| [app/](./camagru/app/README.md) · [app/lang/](./camagru/app/lang/README.md) | MVC e i18n |
| README por subcarpeta (`controllers`, `public`, …) | De lo general a lo concreto |

Repo dedicado (mismo proyecto): [STC71/42_camagru](https://github.com/STC71/42_camagru).

---

## 🌑 Darkly

Introducción a **seguridad web** y mentalidad OWASP: auditoría de un sitio vulnerable y documentación de explotación / mitigación.

### Objetivos

- Descubrir y documentar vulnerabilidades web clásicas  
- Entender impacto y vector de ataque  
- Interiorizar buenas prácticas de código seguro  

### Familias de vulnerabilidades cubiertas (resumen)

SQL Injection, XSS, File Inclusion, manipulación de cookies, spoofing de cabeceras HTTP, bypass de autenticación, upload inseguro, open redirect, information disclosure, manipulación de surveys, recuperación de cuenta, etc.

### Documentación

- [README del proyecto](./darkly/README.md)  
- [Guía de implementación](./darkly/IMPLEMENTATION_GUIDE.md) (si está presente en el árbol)

---

## Relación con Outer Core

```
42_Outer_Core/
└── web_database/          ← submódulo → 42_web_database
    ├── README.md          ← este archivo
    ├── camagru/
    └── darkly/
```

Índice global de proyectos: [README de 42_Outer_Core](https://github.com/STC71/42_Outer_Core/blob/main/README.md).

---

## Autor

**sternero** · 42 Málaga · [GitHub @STC71](https://github.com/STC71)

---

<p align="center">
  <b>Hecho con ❤️ por sternero en 42 Málaga — Octubre 2026</b>
</p>
