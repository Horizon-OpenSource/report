# Horizon - Contribution Guide

Este documento establece las reglas de trabajo colaborativo que deberán seguir todos los integrantes del equipo **Horizon** en los repositorios del proyecto.

Antes de realizar cualquier modificación, cada integrante deberá leer esta guía.

---

# 1. GitFlow Workflow

El proyecto utilizará **GitFlow** mediante el plugin **Git Flow Helper** de WebStorm.

Las ramas principales serán:

- `main`: contiene las versiones estables y entregables del proyecto.
- `develop`: contiene los cambios integrados durante el desarrollo.

Las ramas temporales serán:

- `feature/*`: desarrollo de nuevas funcionalidades, secciones o artefactos.
- `release/*`: preparación de una nueva versión para una entrega.
- `hotfix/*`: correcciones urgentes sobre una versión estable.

El flujo general será:

```text
main
  \
   develop
      \
       feature/*
```

> [!IMPORTANT]
> Ningún integrante debe trabajar directamente sobre `main` o `develop`.

---

# 2. Antes de empezar una tarea

Antes de crear una nueva feature, el integrante debe:

1. Abrir el proyecto en WebStorm.
2. Cambiar a la rama `develop`.
3. Actualizar `develop` para trabajar con los últimos cambios del equipo.
4. Verificar que no existan cambios pendientes.
5. Crear una nueva feature utilizando Git Flow Helper.

El flujo comienza siempre desde:

```text
develop
```

Luego:

```text
GitFlowHelper
→ Feature
→ Feature Start
```

---

# 3. Creación de una Feature

Cada tarea debe realizarse en su propia rama `feature/*`.

Al utilizar:

```text
GitFlowHelper
→ Feature
→ Feature Start
```

se debe escribir únicamente el nombre de la tarea.

Por ejemplo, si el integrante trabajará el Startup Profile:

```text
chapter-01-startup-profile
```

Git Flow Helper agregará automáticamente el prefijo:

```text
feature/chapter-01-startup-profile
```

> [!IMPORTANT]
> Si Git Flow Helper ya tiene configurado el prefijo `feature/`, no escribir manualmente `feature/` en el nombre.

---

# 4. Convención para nombres de ramas

El formato general será:

```text
feature/<area>-<tarea-especifica>
```

Los nombres deben:

- Estar escritos en inglés.
- Estar en minúsculas.
- Utilizar guiones `-` para separar palabras.
- Describir claramente el trabajo realizado.
- Representar una tarea específica.

## Ejemplos correctos

Startup Profile:

```text
feature/chapter-01-startup-profile
```

Diseño de entrevistas:

```text
feature/chapter-02-interview-design
```

User Stories:

```text
feature/chapter-03-user-stories
```

Perfil de un integrante:

```text
feature/member-profile-javier-tello
```

Landing Page:

```text
feature/hero-section
```

---

# 5. Nombres de ramas que se deben evitar

No utilizar nombres genéricos como:

```text
feature/javier
feature/rolando
feature/avance
feature/avance-1
feature/cambios
feature/trabajo
feature/documento
feature/final
feature/final-final
```

El nombre de la rama debe permitir identificar la tarea únicamente con leerlo.

Por ejemplo:

```text
feature/chapter-02-interview-analysis
```

permite saber inmediatamente qué trabajo contiene la rama.

---

# 6. Una tarea por Feature

Cada feature debe representar una tarea específica.

Por ejemplo, si un integrante tiene asignado:

```text
2.2.1 Diseño de entrevistas
```

deberá crear:

```text
feature/chapter-02-interview-design
```

Si después recibe otra tarea como:

```text
2.2.3 Análisis de entrevistas
```

deberá crear una nueva rama:

```text
feature/chapter-02-interview-analysis
```

No se debe reutilizar una feature terminada para una tarea diferente.

---

# 7. Conventional Commits

Todos los commits del proyecto deben seguir la convención **Conventional Commits**.

El formato general será:

```text
type(scope): description
```

Ejemplo:

```text
docs(chapter-01): add startup profile
```

La descripción debe:

- Ser breve.
- Indicar claramente qué cambio se realizó.
- Estar escrita en inglés.
- Comenzar en minúscula.

---

# 8. Tipos principales de Conventional Commits

## docs

Se utilizará para documentación.

Será el tipo más utilizado dentro del repositorio `report`.

Ejemplos:

```text
docs(report): add AV1 report structure
docs(chapter-01): add startup profile
docs(chapter-02): add interview design
docs(chapter-03): add user stories
docs(chapter-04): add landing page mockup
docs(chapter-05): add source code management
docs(sprint-01): add sprint backlog
```

---

## feat

Se utilizará cuando se agregue una nueva funcionalidad al software.

Ejemplos:

```text
feat(landing): add hero section
feat(auth): add login form
feat(profile): add user profile page
```

---

## fix

Se utilizará para corregir un error.

Ejemplo:

```text
fix(landing): correct navigation links
```

---

## refactor

Se utilizará para reorganizar código sin modificar su funcionalidad.

Ejemplo:

```text
refactor(profile): simplify profile component
```

---

## test

Se utilizará para agregar o modificar pruebas.

Ejemplo:

```text
test(profile): add profile component tests
```

---

## style

Se utilizará para cambios de presentación o formato que no alteren la funcionalidad.

Ejemplo:

```text
style(landing): improve responsive spacing
```

---

## chore

Se utilizará para configuraciones o mantenimiento del proyecto.

Ejemplos:

```text
chore: configure project repository
chore: update project dependencies
```

---

# 9. Rama y Commit no son lo mismo

Una rama GitFlow y un Conventional Commit cumplen funciones diferentes.

Ejemplo:

Rama:

```text
feature/chapter-02-interview-design
```

Commit:

```text
docs(chapter-02): add interview design
```

Por lo tanto:

```text
feature/... = rama GitFlow

docs(...) = Conventional Commit
```

---

# 10. Flujo obligatorio de trabajo

Cada integrante deberá seguir este flujo:

```text
develop
   ↓
Actualizar develop
   ↓
Feature Start
   ↓
feature/<tarea>
   ↓
Realizar cambios
   ↓
Conventional Commit
   ↓
Feature Publish
   ↓
Avisar al delegado
   ↓
Revisión
   ↓
Aprobación
   ↓
Feature Finish
   ↓
develop
```

---

# 11. Feature Publish

Cuando el integrante haya terminado su tarea y realizado sus commits deberá utilizar:

```text
GitFlowHelper
→ Feature
→ Feature Publish
```

Por ejemplo:

```text
feature/chapter-02-interview-design
```

Después de utilizar `Feature Publish`, la rama quedará publicada en GitHub para su revisión.

El integrante deberá comunicar al delegado:

```text
La rama feature/chapter-02-interview-design está lista para revisión.
```

> [!IMPORTANT]
> Después de `Feature Publish` NO se debe ejecutar inmediatamente `Feature Finish`.

Primero se debe esperar la revisión.

---

# 12. Diferencia entre Feature Publish y Feature Finish

## Feature Publish

`Feature Publish` publica la rama en GitHub.

Ejemplo:

```text
LOCAL

feature/chapter-02-interview-design

             ↓ Publish

GITHUB

feature/chapter-02-interview-design
```

La rama todavía NO ha sido integrada en `develop`.

---

## Feature Finish

`Feature Finish` integra los cambios de la feature nuevamente en:

```text
develop
```

Ejemplo:

```text
feature/chapter-02-interview-design
                    ↓
              Feature Finish
                    ↓
                 develop
```

Después de finalizar una feature, la rama `feature/*` puede eliminarse automáticamente.

Esto es normal.

Los cambios no desaparecen porque los commits ya fueron integrados en:

```text
develop
```

---

# 13. Revisión del delegado

Después de `Feature Publish`, el delegado revisará los cambios antes de permitir su integración en `develop`.

Se verificará principalmente:

- Que la tarea asignada esté completa.
- Que el contenido se encuentre en la sección correcta.
- Que no se hayan eliminado cambios de otros integrantes.
- Que no existan archivos innecesarios.
- Que los commits utilicen Conventional Commits.
- Que la rama tenga un nombre adecuado.
- Que los cambios correspondan únicamente a la tarea asignada.

Si existen observaciones, el integrante deberá corregirlas dentro de la misma feature y publicar los nuevos commits.

---

# 14. Feature Finish

Cuando el delegado confirme que los cambios están correctos, autorizará al integrante a finalizar su feature.

El integrante utilizará:

```text
GitFlowHelper
→ Feature
→ Feature Finish
```

La feature será integrada en:

```text
develop
```

Ejemplo:

```text
feature/chapter-02-interview-design
                    ↓
                 develop
```

Después del `Feature Finish`, es normal que la rama feature sea eliminada.

---

# 15. Ejemplo completo

Supongamos que un integrante tiene asignado:

```text
2.2.1 Diseño de entrevistas
```

Primero cambia a:

```text
develop
```

Luego utiliza:

```text
GitFlowHelper
→ Feature
→ Feature Start
```

Escribe:

```text
chapter-02-interview-design
```

Git Flow Helper crea:

```text
feature/chapter-02-interview-design
```

El integrante realiza sus cambios.

Después crea el commit:

```text
docs(chapter-02): add interview design
```

Luego utiliza:

```text
GitFlowHelper
→ Feature
→ Feature Publish
```

Y comunica:

```text
La rama feature/chapter-02-interview-design está lista para revisión.
```

El delegado revisa los cambios.

Si están correctos, autoriza:

```text
GitFlowHelper
→ Feature
→ Feature Finish
```

Finalmente:

```text
feature/chapter-02-interview-design
                    ↓
                 develop
```

---

# 16. Ejemplos de Features para el Project Report

Algunos ejemplos de nombres que podrán utilizarse son:

```text
feature/member-profile-javier-tello

feature/chapter-01-startup-profile
feature/chapter-01-solution-profile
feature/chapter-01-target-segments

feature/chapter-02-competitive-analysis
feature/chapter-02-interview-design
feature/chapter-02-interview-records
feature/chapter-02-interview-analysis
feature/chapter-02-user-personas
feature/chapter-02-user-task-matrix
feature/chapter-02-user-journey-mapping
feature/chapter-02-empathy-mapping
feature/chapter-02-ubiquitous-language

feature/chapter-03-user-stories
feature/chapter-03-impact-mapping
feature/chapter-03-product-backlog

feature/chapter-04-style-guidelines
feature/chapter-04-landing-wireframe
feature/chapter-04-landing-mockup

feature/chapter-05-source-code-management

feature/sprint-01-planning
feature/sprint-01-backlog
```

No es obligatorio utilizar exactamente estos nombres.

El nombre dependerá de la tarea asignada, pero deberá respetar la convención establecida.

---

# 17. Ejemplos para otros repositorios

La misma metodología será utilizada en los demás repositorios del proyecto.

## Landing Page

Ejemplos:

```text
feature/header-navigation
feature/hero-section
feature/about-product-section
feature/features-section
feature/contact-section
feature/footer-section
```

Ejemplo de commit:

```text
feat(landing): add hero section
```

---

## Frontend Web Application

Ejemplos:

```text
feature/login-page
feature/user-profile
feature/dashboard
feature/navigation-sidebar
```

Ejemplo:

```text
feat(profile): add user profile page
```

---

## Web Services

Ejemplos:

```text
feature-user-management
```

Utilizando GitFlow:

```text
feature/user-management
```

Otro ejemplo:

```text
feature/authentication
```

Commit:

```text
feat(auth): add authentication endpoint
```

---

# 18. main

La rama:

```text
main
```

contiene únicamente versiones estables y entregables del proyecto.

Los integrantes no deben realizar cambios directamente sobre esta rama.

El trabajo cotidiano NO se realiza en `main`.

---

# 19. develop

La rama:

```text
develop
```

es la rama principal de integración del equipo.

Todas las features:

```text
nacen desde develop
```

y después de ser revisadas:

```text
terminan nuevamente en develop
```

Flujo:

```text
develop
   \
    feature/*
         \
          develop
```

No realizar cambios directamente en `develop`.

---

# 20. Releases

Cuando todas las features correspondientes a una entrega estén terminadas e integradas en `develop`, se podrá preparar una release.

Las releases serán administradas principalmente por el delegado.

Ejemplo:

```text
release/0.1.0
```

Se utilizará **Semantic Versioning**:

```text
MAJOR.MINOR.PATCH
```

Ejemplos:

```text
0.1.0
0.2.0
1.0.0
```

El flujo será:

```text
develop
   ↓
release/x.x.x
   ↓
main
```

Las releases no deben ser creadas libremente por cada integrante.

---

# 21. Hotfixes

Los hotfixes serán utilizados únicamente para corregir errores urgentes presentes en una versión estable.

Ejemplo:

```text
hotfix/1.0.1
```

No utilizar `hotfix/*` para tareas normales del proyecto.

El desarrollo normal deberá realizarse mediante:

```text
feature/*
```

---

# 22. Reglas generales del equipo

No realizar commits directamente sobre:

```text
main
develop
```

No utilizar nombres genéricos para las ramas.

No trabajar diferentes tareas sin relación dentro de una misma feature.

No realizar commits utilizando la cuenta de otro integrante.

No enviar únicamente el trabajo al delegado para que este realice todos los commits.

Cada integrante debe realizar sus propias contribuciones mediante su cuenta de GitHub.

Cada integrante debe tener evidencia de participación mediante sus ramas y commits.

No ejecutar `Feature Finish` sin haber pasado primero por la revisión establecida.

No utilizar `release/*` o `hotfix/*` sin coordinación con el delegado.

---

# 23. Resumen del flujo

El flujo que deberá recordar cada integrante es:

```text
1. Ir a develop

        ↓

2. Actualizar develop

        ↓

3. GitFlowHelper
   Feature → Feature Start

        ↓

4. Trabajar en:

   feature/<tarea>

        ↓

5. Realizar Conventional Commits

        ↓

6. Feature Publish

        ↓

7. Avisar al delegado

        ↓

8. Revisión

        ↓

9. Aprobación

        ↓

10. Feature Finish

        ↓

11. Cambios integrados en develop
```

En forma resumida:

```text
develop
   ↓
feature/*
   ↓
commit
   ↓
Feature Publish
   ↓
revisión
   ↓
Feature Finish
   ↓
develop
```

---

# 24. Objetivo de esta guía

El objetivo de este flujo de trabajo es:

- Mantener organizado el desarrollo del proyecto.
- Evitar modificaciones directas en las ramas principales.
- Facilitar la revisión de los aportes.
- Mantener un historial de cambios claro.
- Identificar correctamente la participación de cada integrante.
- Aplicar GitFlow de manera consistente.
- Utilizar Conventional Commits.
- Mantener versiones del proyecto mediante Semantic Versioning.

Todos los integrantes del equipo **Horizon** deberán seguir estas reglas durante el desarrollo del proyecto.