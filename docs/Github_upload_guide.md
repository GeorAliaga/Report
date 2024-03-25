# Github_upload_guide.md

En este documento se detalla el flujo de trabajo que seguiremos en el equipo para el desarrollo del producto final.

## Naming conventions

Convenciones en la nomenclatura para ramas y mensajes de commit.

### Branches

Para las ramas, usaremos la estructura `<token>/<short-descriptive-name>`.

Los tokens que podemos usar son:

- `chore`: mejoras en temas de administración/mantenimiento del proyecto (i.e. actualización de dependencias).
- `docs`: creación/actualización de documentación (i.e.: guía de configuración del proyecto).
- `feature`: nuevas funcionalidades que serán incluidas en el proyecto. (i.e. visualización de cursos).
- `fix`: corrección de un bug esperado o inesperado (i.e. links rotos).
- `refactor`: mejoras/reescritura de features existentes, no agrega un cambio grande a lo que actualmente tiene. .
- `test`: agrega tests a un feature existente que no cuenta con los mismos (i.e. unit testing del componente de login).

#### Ejemplos

- chore/deps-upgrade
- docs/setup
- feature/project-roadmap
- fix/student-routing
- refactor/settings-components
- test/cohort

### Commits

Para los commits, seguiremos la estructura de los mensajes de commit es `<type>(<scope>): <subject>`.

- El `type` son tokens cortos similares a los de las ramas, pueden ser:

  - `feat` (feature)
  - `fix` (bug fix)
  - `docs` (documentation)
  - `style` (formatting, missing semi colons, …)
  - `refactor`
  - `test` (when adding missing tests)
  - `chore` (maintain).

- El `scope` hace referencia al lugar en donde se han trabajado los cambios (Puede ser omitido en algunas ocasiones).

- El `subject` debe cumpler algunas reglas más específicas:
  - En inglés, usar modo imperativo, past tense:
  - La primera letra en minúscula.
  - No poner punto al final

#### Ejemplos

- feat(cors): added cors support, with an allow all policy
- refactor(users): removed unnecessary size constraint for password hash
- fix(notes): modified incorrect dependency
- docs: added google docs url

## Workflow

Convenciones para el correcto desarrollo de la aplicación

### Development

En primer lugar, se tendrá la rama `main`, como una versión estable de producción, y la rama `develop`, para el desarrollo.

En la etapa de desarrollo, se trabajara cada feature, task, fix, etc., en una rama específica, siguiendo la convención de nomenclatura de ramas descrita anteriormente.

Cuando se completen todos los features para la entrega, todos los cambios de la rama `develop` serán subidos a la rama `main`.

### Steps

1.  Encontrarse en la rama de desarrollo `develop`
2.  Crear una rama para desarrollar la funcionalidad

        git checkout -b [nombre_rama]

    Si se desea subir la rama al github (en caso el desarrollo sea de 2 o más personas)

        git push --set-upstream origin [nombre_rama]

3.  Desarrollar lo planteado
4.  Una vez realizada la actividad, hacer los commits necesarios y subirlos a la rama

5.  Una vez la rama esté completa y no se realizarán más modificaciones, se realiza un merge con `develop`. Se verlo necesario, borrar la rama.

### Modo de trabajo

#### Report workflow

Se creará una rama por cada capítulo (o subcapítulo, dependiendo del número de índices que abarca). En la rama, se subirán los commits del desarrollo por cada integrante.

- Branch: feature/chapter-1

  - `feat(1.1.2)`: added Diego profile
  - `feat(1.2.2.1)`: added lean us problem statements
  - `feat(1.3)`: added segmentos objetivos

- Branch: feature/chapter-2.2
  - `feat(2.2.1)`: added disenho entrevistas
  - `feat(2.2.2)`: added interview 3

#### Frontend and backend workflow

Para el desarrollo de la aplicación, se creará una rama por `user story` y se desarrollarán los commits necesarios

- Branch: feature/user-story-15
  - `feat(users)`: added user_page.html
  - `feat(users)`: added user_page.css
  - `feat(users)`: added user_page.js
