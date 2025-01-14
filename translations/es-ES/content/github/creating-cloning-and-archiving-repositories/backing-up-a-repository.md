---
title: Realizar una copia de seguridad de un repositorio
intro: 'Puedes utilizar{% if enterpriseServerVersions contains currentVersion or currentVersion == "github-ae@latest" %} Git y{% endif %} la API {% if currentVersion == "free-pro-team@latest" %}or a third-party tool {% endif %}para respaldar tu repositorio.'
redirect_from:
  - /articles/backing-up-a-repository
versions:
  free-pro-team: '*'
  enterprise-server: '*'
  github-ae: '*'
topics:
  - repositories
---

{% if currentVersion == "free-pro-team@latest" %}

Para descargar un archivo en tu repositorio, puedes usar la API para migraciones del usuario o la organizacion. Para obtener más información, consulta la sección "[Migraciones](/rest/reference/migrations)".
{% else %}

Puedes descargar y realizar una copia de seguridad de tus repositorios manualmente:

- Para descargar los datos Git de un repositorio en tu máquina local, necesitarás clonar el repositorio. Para obtener más información, consulta "[Clonar un repositorio](/articles/cloning-a-repository)".
- También puedes descargar las wiki de un repositorio. Para obtener más información, consulta "[Agregar o editar páginas wiki](/articles/adding-or-editing-wiki-pages)".

Cuando clonas un repositorio o wiki, solo se descargan los datos Git, como archivos de proyecto o historial de confirmaciones. Puedes usar nuestra API para exportar otros elementos de tu repositorio {% data variables.product.product_name %} en tu máquina local:

- [Problemas](/rest/reference/issues#list-issues-for-a-repository)
- [Solicitudes de cambios](/rest/reference/pulls#list-pull-requests)
- [Bifurcaciones](/rest/reference/repos#list-forks)
- [Comentarios](/rest/reference/issues#list-issue-comments-for-a-repository)
- [Hitos](/rest/reference/issues#list-milestones)
- [Etiquetas](/rest/reference/issues#list-labels-for-a-repository)
- [Observadores](/rest/reference/activity#list-watchers)
- [Fans](/rest/reference/activity#list-stargazers)
- [Proyectos](/rest/reference/projects#list-repository-projects)
{% endif %}

Una vez que tengas {% if enterpriseServerVersions contains currentVersion or currentVersion == "github-ae@latest" %}una versión local de todo el contenido que quieras respaldar, puedes crear un archivo zip y {% else %}descargar tu archivo, puedes {% endif %}copiarlo a un disco duro externo y/o cargarlo a algún servicio de respaldo basado en la nube, tal como [Google Drive](https://www.google.com/drive/) o [Dropbox](https://www.dropbox.com/).

{% if currentVersion == "free-pro-team@latest" %}
### Herramientas de copias de seguridad de terceros
Existe un número de herramientas de autoservicio que automatizan las copias de seguridad de los repositorios. A diferencia de los proyectos de archivo, los cuales archivan _todos_ los repositorios públicos de

{% data variables.product.product_name %} que no hayan decidido no participar y hacer que los datos sean accesibles para cualquiera, las herramientas de respaldo descargarán datos de los repositorios _específicos_ y los organizarán dentro de una rama o directorio nuevos. Para obtener más información acerca de los proyectos de archivo, consulta la sección "[Acerca de archivar contenido y datos en {% data variables.product.prodname_dotcom %}](/github/creating-cloning-and-archiving-repositories/about-archiving-content-and-data-on-github#about-the-github-archive-program)". Para obtener más información acerca de las herramientas de respaldo de autoservicio, consulta la [Categoría de utilidades de respaldo en {% data variables.product.prodname_marketplace %}](https://github.com/marketplace?category=backup-utilities).
{% endif %}
