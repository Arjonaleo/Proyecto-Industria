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

## Flujo de Pull Requests

```
feature/* ──► develop ──► master
fix/*     ──►              (solo en hitos del Gantt)
hotfix/*  ──────────────►
```

1. Abrir PR de `feature/<nombre>` → `develop`
2. Requiere aprobación de **Diego Lara (QA/Integrador)** antes del merge
3. El merge de `develop` → `master` ocurre únicamente en los hitos definidos en el Gantt
4. `hotfix/*` puede ir directo a `master` + backport a `develop`

---

## Reglas

- Commit messages must be written in English
- Un commit por cambio lógico - no acumular cambios no relacionados
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
