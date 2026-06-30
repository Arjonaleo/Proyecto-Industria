# Guía de Contribución - SGA / ORPEL

## Ramas

| Rama | Propósito |
|------|-----------|
| `master` | Versión estable - solo merge en hitos del Gantt |
| `develop` | Integración general del equipo |
| `feature/<nombre>` | Nueva funcionalidad |
| `fix/<nombre>` | Corrección de errores |
| `docs/<nombre>` | Documentación |
| `hotfix/<nombre>` | Corrección urgente en producción (F13) |

**Ejemplos:**
```
feature/catalogo-productos
feature/modulo-seguridad
fix/login-timeout
docs/ERS-revision-v2
hotfix/inventario-ajuste-produccion
```

---

## Formato de Commits

```
<tipo>(<scope>): <descripción corta en inglés>
```

El `scope` es el ID de tarea del Gantt - permite trazar cada commit al cronograma del proyecto.

| Tipo | Cuándo usarlo |
|------|--------------|
| `feat` | Nueva funcionalidad |
| `fix` | Corrección de bug |
| `docs` | Documentación |
| `chore` | Tareas de mantenimiento, dependencias y archivos de configuración del proyecto |
| `build` | Cambios en sistemas de compilación: Maven, npm, Gradle, scripts de build o CI/CD |
| `refactor` | Refactorización sin cambio funcional |
| `test` | Casos de prueba |
| `style` | Formato, espacios (sin lógica) |

**Ejemplos:**
```
feat(5.2): add user authentication module
feat(5.3): implement product catalog CRUD endpoints
docs(2.7): add requirements traceability matrix
fix(10.2): correct unit test for inventory entry
chore(4.3): configure SQL Server connection settings
test(10.4): add frontend regression tests for catalogs
```

---

## Commits Significativos

Cada commit debe representar un solo cambio logico. El historial de git es la bitacora del proyecto - cada entrada debe tener sentido por si sola.

**Reglas:**

- Un commit = un cambio logico. No mezclar bugfix con feature, ni refactor con documentacion.
- El mensaje debe describir que cambia y por que, no que archivos se tocaron.
- No usar mensajes vagos: `fix`, `changes`, `update`, `wip`, `arregle cosas` no aportan contexto.
- Si trabajaste en varias cosas al mismo tiempo, usa `git add -p` para separar los cambios en commits individuales.

**Ejemplos:**

| Mal | Bien |
|-----|------|
| `fix stuff` | `fix(5.2): correct null check in authentication filter` |
| `changes` | `feat(6.1): add product catalog search endpoint` |
| `update files` | `docs(2.2): add catalog analysis requirements` |
| `arregle el login` | `fix(5.2): handle expired session token on login` |

**Tip - separar cambios con `git add -p`:**

Si modificaste varios archivos con propositos distintos, en lugar de `git add .` usa:

```bash
git add -p
```

Git muestra cada bloque de cambio uno por uno. Elige cuales incluir en este commit (`y` para incluir, `n` para omitir). Resultado: 2 commits limpios en lugar de 1 commit mezclado.

---

## Flujo de Pull Requests

```
feature/* --> develop --> master
fix/*     -->              (solo en hitos del Gantt)
hotfix/*  ------------>
```

**Checklist antes de abrir el PR:**

- [ ] La rama fue creada desde `develop`, no desde `master`
- [ ] La rama esta actualizada con `develop` (`git pull origin develop`)
- [ ] El proyecto compila sin errores
- [ ] No hay archivos locales incluidos (`git status` limpio de `.env`, configs, herramientas)
- [ ] Los commits son individuales y con mensajes descriptivos
- [ ] El titulo del PR describe el cambio, no el archivo tocado

**Proceso:**

1. Abrir PR de `feature/<nombre>` → `develop`
2. Requiere aprobación de **Diego Lara (QA/Integrador)** antes del merge
3. El merge de `develop` → `master` ocurre únicamente en los hitos definidos en el Gantt
4. `hotfix/*` puede ir directo a `master` + backport a `develop`

---

## Reglas

- Commit messages must be written in English
- Incluir el scope (ID de tarea del Gantt) siempre que aplique
- No hacer push directo a `master` ni a `develop`
- No subir credenciales, archivos `.env` ni configuraciones locales
- La rama debe estar actualizada con `develop` antes de abrir PR

---

## Herramientas de Desarrollo

El uso de herramientas de asistencia como Copilot, Cursor, Codex u otras es personal y forma parte del entorno local de cada contribuidor.

No deben quedar archivos, metadatos ni referencias de estas herramientas en el repositorio.

Reglas:

- No subir carpetas de configuracion local como `.codex/`, `.cursor/`, `.agents/`, `.claude/` u otras similares.
- No agregar footers como `Co-Authored-By`, `Generated-By` o `Assisted-By` en commits.
- No mencionar herramientas de asistencia en mensajes de commit.
- Los commits deben aparecer bajo la identidad Git del contribuidor.
- Antes de commitear, revisar `git status` para confirmar que no se incluyan archivos locales.
