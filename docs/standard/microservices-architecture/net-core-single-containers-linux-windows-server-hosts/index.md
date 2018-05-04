---
title: Implementar aplicaciones web de .NET Core basadas en un solo contenedor en hosts de Linux o Windows Nano Server
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Implementar aplicaciones web de .NET Core basadas en un solo contenedor en hosts de Linux o Windows Nano Server
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: f429bc0c6e76c2be2e4f491768a15ab36ecb0d34
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="deploying-single-container-based-net-core-web-applications-on-linux-or-windows-nano-server-hosts"></a>Implementar aplicaciones web de .NET Core basadas en un solo contenedor en hosts de Linux o Windows Nano Server

*Puede usar contenedores de Docker para la implementación monolítica de aplicaciones web más sencillas. Esto mejora la integración continua y las canalizaciones de implementación continua y ayuda a llevar a cabo correctamente el proceso desde la implementación hasta la producción. Ya no se volverá a preguntar: "Funciona en mi equipo, ¿por qué no funciona en producción?".*

Una arquitectura basada en microservicios tiene muchas ventajas, pero a costa de una mayor complejidad. En algunos casos, los costos superan a las ventajas y podría resultarle más útil una aplicación de implementación monolítica que se ejecute en un solo contenedor o en unos pocos contenedores. 

Es posible que una aplicación monolítica no se pueda descomponer fácilmente en microservicios bien separados. Ya ha aprendido que estos se deben particionar por función: los microservicios deberían funcionar de manera independiente para proporcionar una aplicación más resistente. Si no puede proporcionar sectores de características de la aplicación, el hecho de separarla solo agrega complejidad.

Una aplicación podría no necesitar inicialmente el escalado de las características por separado. Supongamos que en una fase temprana del ciclo de vida de la aplicación de referencia eShopOnContainers, el tráfico no justificaba separar las características en diferentes microservicios. El tráfico era bastante reducido y el hecho de agregar recursos a un servicio normalmente suponía agregar recursos a todos los servicios. El trabajo adicional que suponía separar la aplicación en servicios diferenciados apenas proporcionaba beneficio.

Además, en las fases tempranas del desarrollo de una aplicación, es posible que no se tenga una idea clara de dónde están los límites funcionales naturales. Mientras desarrolla un producto mínimamente viable, puede que todavía no sea evidente la separación natural.

Algunas de estas condiciones pueden ser temporales. Podría empezar creando una aplicación monolítica y, más adelante, separar algunas características para desarrollarlas e implementarlas como microservicios. Otras condiciones podrían ser básicas para el espacio de problemas de la aplicación y, en consecuencia, tal vez no se pueda dividir nunca en varios microservicios.

La separación de una aplicación en varios procesos diferenciados también introduce una sobrecarga. La separación de funciones en procesos diferentes conlleva una mayor complejidad. Los protocolos de comunicación se vuelven más complejos. En lugar de llamadas a métodos, debe usar comunicaciones asincrónicas entre servicios. Cuando cambie a una arquitectura de microservicios, deberá agregar muchos de los bloques de creación que se implementan en la versión de microservicios de la aplicación eShopOnContainers: control de bus de eventos, reintentos y resistencia de mensajes, coherencia eventual y mucho más.

Una versión muy simplificada de eShopOnContainers (denominada [eShopWeb](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Web/WebMonolithic) e incluida en el mismo repositorio de GitHub) se ejecuta como una aplicación de MVC monolítica y, tal como se ha indicado, esta opción de diseño ofrece una serie de ventajas. Puede descargar de GitHub el código fuente para esta aplicación y ejecutarlo de forma local. Incluso esta aplicación monolítica se beneficia de la implementación en un entorno de contenedor.

Ante todo, la implementación en contenedor implica que cada instancia de la aplicación se ejecuta en el mismo entorno. Esto incluye el entorno de desarrollo donde tienen lugar las pruebas y el desarrollo iniciales. El equipo de desarrollo puede ejecutar la aplicación en un entorno en contenedor que coincida con el entorno de producción.

Además, las aplicaciones en contenedor se escalan horizontalmente con un costo menor. Como ya ha visto, el entorno en contenedor permite un mayor uso compartido de recursos que los entornos de máquina virtual tradicionales.

Por último, el hecho de incluir la aplicación en un contenedor fuerza la separación entre la lógica de negocios y el servidor de almacenamiento. Cuando la aplicación se escala horizontalmente, los diversos contenedores se basan en un único medio de almacenamiento físico. Normalmente, se trata de un servidor de alta disponibilidad que ejecuta una base de datos de SQL Server.

## <a name="application-tour"></a>Paseo por la aplicación

La aplicación [eShopWeb](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Web/WebMonolithic) representa una parte de la aplicación eShopOnContainers que se ejecuta como una aplicación monolítica (una aplicación basada en MVC de ASP.NET Core que se ejecuta en .NET Core). Básicamente, proporciona las funciones de exploración del catálogo que se han descrito en secciones anteriores.

La aplicación usa una base de datos de SQL Server para el almacenamiento del catálogo. En las implementaciones basadas en contenedor, esta aplicación monolítica puede tener acceso al mismo almacén de datos que la aplicación basada en microservicios. La aplicación está configurada para ejecutar SQL Server en un contenedor junto con la aplicación monolítica. En un entorno de producción, SQL Server se ejecutaría en una máquina con alta disponibilidad, fuera del host de Docker. Para mayor comodidad en un entorno de desarrollo o de pruebas, se recomienda ejecutar SQL Server en su propio contenedor.

El conjunto de características iniciales solo permite examinar el catálogo. Mediante las actualizaciones se habilitará el conjunto completo de características de la aplicación en contenedor. En el libro electrónico [ASP.NET Web Application architecture practices](https://aka.ms/webappebook) (Prácticas de la arquitectura de aplicaciones web ASP.NET) y en la [aplicación de ejemplo eShopOnWeb](http://aka.ms/WebAppArchitecture) relacionada se describe una arquitectura de aplicaciones web monolítica más avanzada, aunque en este caso no se ejecuta en contenedores de Docker, ya que el escenario se centra en el desarrollo web simple con ASP.NET Core.

Aun así, la versión simplificada disponible en eShopOnContainers (eShopWeb) se ejecuta en un contenedor de Docker.

## <a name="docker-support"></a>Compatibilidad con Docker

El proyecto eShopOnWeb se ejecuta en .NET Core. Por lo tanto, se puede ejecutar en contenedores basados en Linux o en Windows. Tenga en cuenta que, para la implementación de Docker, le interesa usar el mismo tipo de host para SQL Server. Los contenedores basados en Linux permiten una superficie menor y son preferibles.

Visual Studio proporciona una plantilla de proyecto que agrega compatibilidad con Docker a una solución. Para ello, haga clic con el botón derecho en el proyecto y haga clic en **Agregar** y en **Compatibilidad con Docker**. La plantilla agrega un archivo Dockerfile al proyecto y un nuevo proyecto **docker-compose** que proporciona un archivo de inicio docker-compose.yml. Este paso ya se ha llevado a cabo en el proyecto eShopOnWeb descargado de GitHub. Verá que la solución contiene el proyecto **eShopOnWeb** y el proyecto **docker-compose** tal como se muestra en la figura 6-1.

![](./media/image1.png)

**Figura 6-1**. Proyecto **docker-compose** en una aplicación web de un solo contenedor.

Estos archivos son archivos estándar docker-compose, coherentes con cualquier proyecto de Docker. Puede usarlos con Visual Studio o desde la línea de comandos. Esta aplicación se ejecuta en .NET Core y usa contenedores de Linux, por lo que también puede codificar, compilar y ejecutar en un equipo Mac o en un equipo Linux.

El archivo docker-compose.yml contiene información sobre qué imágenes se van a compilar y qué contenedores se van a iniciar. Las plantillas especifican cómo se compila la imagen eshopweb y cómo se inician los contenedores de la aplicación. Debe agregar la dependencia en SQL Server. Para hacerlo, incluya una imagen para ella (por ejemplo, mssql-server-linux) y un servicio para la imagen sql.data de modo que Docker compile e inicie ese contenedor. Esta configuración se muestra en el ejemplo siguiente:

```yml
version: '2'

services:
  eshopweb:
    image: eshop/web
    build:
    context: ./eShopWeb
    dockerfile: Dockerfile
    depends_on:
      - sql.data

  sql.data:
    image: microsoft/mssql-server-linux
```

La directiva depends\_on le indica a Docker que la imagen eShopWeb depende de la imagen sql.data. Unas líneas por debajo se encuentran las instrucciones para compilar una imagen etiquetada como sql.data mediante la imagen microsoft/mssql-server-linux.

En el proyecto **docker-compose** se muestran los demás archivos docker-compose bajo el nodo principal docker-compose.yml. Esto ayuda a señalar visualmente la relación entre estos archivos. El archivo docker-compose-override.yml contiene los valores de configuración de ambos servicios, como las cadenas de conexión y otros valores para las aplicaciones.

En el ejemplo siguiente se muestra el archivo docker-compose.vs.debug.yml, que contiene los valores usados para la depuración en Visual Studio. En ese archivo, la imagen eshopweb tiene anexada la etiqueta de desarrollo. Esto ayuda a separar las imágenes de depuración de las imágenes de lanzamiento, para que no se implemente accidentalmente la información de depuración en un entorno de producción:

```yml
version: '2'
  
services:
  eshopweb:
    image: eshop/web:dev
    build:
    args:
    source: ${DOCKER_BUILD_SOURCE}
    environment:
      - DOTNET_USE_POLLING_FILE_WATCHER=1
    volumes:
      - ./eShopWeb:/app
      - ~/.nuget/packages:/root/.nuget/packages:ro
      - ~/clrdbg:/clrdbg:ro
    entrypoint: tail -f /dev/null
    labels:
      - "com.microsoft.visualstudio.targetoperatingsystem=linux"
```

El último archivo agregado es docker-compose.ci.build.yml, que se usaría desde la línea de comandos para compilar el proyecto desde un servidor CI. Este archivo compuesto inicia un contenedor de Docker que compila las imágenes necesarias para la aplicación. En el ejemplo siguiente se muestra el contenido del archivo docker-compose.ci.build.yml.

```yml
version: '2'
  
services:
  ci-build:
    image: microsoft/aspnetcore-build:latest
    volumes:
      - .:/src
    working_dir: /src
  command: /bin/bash -c "dotnet restore ./eShopWeb.sln && dotnet publish  ./eShopWeb.sln -c Release -o ./obj/Docker/publish"
```

**Nota**: A partir de .NET Core 2.0, el comando de restauración dotnet se ejecuta automáticamente cuando se ejecuta la publicación de dotnet.

Tenga en cuenta que la imagen es una imagen de compilación de ASP.NET Core. Esta imagen incluye las herramientas de compilación y el SDK para compilar la aplicación y crear las imágenes necesarias. Al ejecutar el proyecto **docker-compose** con este archivo, se inicia el contenedor de compilación desde la imagen y se compila la imagen de la aplicación en ese contenedor. Debe especificar ese archivo docker-compose como parte de la línea de comandos para compilar la aplicación en un contenedor de Docker y, después, iniciarlo.

En Visual Studio, puede ejecutar la aplicación en contenedores de Docker. Para ello, seleccione el proyecto **docker-compose** como proyecto de inicio y presione Ctrl+F5 (F5 para depurar), como haría con cualquier otra aplicación. Cuando se inicia el proyecto **docker-compose**, Visual Studio ejecuta **docker-compose** mediante el archivo docker-compose.yml, el archivo docker-compose.override.yml y uno de los archivos docker-compose.vs\*. Una vez que se ha iniciado la aplicación, Visual Studio abre automáticamente el explorador.

Si inicia la aplicación en el depurador, Visual Studio se asociará a la aplicación en ejecución en Docker.

## <a name="troubleshooting"></a>Solución de problemas

En esta sección se describen algunos de los problemas que pueden surgir cuando se ejecutan contenedores de manera local y se sugieren diversas correcciones.

### <a name="stopping-docker-containers"></a>Detener contenedores de Docker 

Después de iniciar la aplicación en contenedor, los contenedores siguen ejecutándose incluso después de que se haya detenido la depuración. Puede ejecutar el comando docker ps desde la línea de comandos para ver qué contenedores se están ejecutando. El comando docker stop detiene un contenedor en ejecución, tal como se muestra en la figura 6-2.

![](./media/image2.png)

**Figura 6-2**. Mostrar y detener contenedores con los comandos docker ps y docker stop de la CLI

Es posible que necesite detener procesos en ejecución cuando cambie entre diferentes configuraciones. En caso contrario, el contenedor que ejecuta la aplicación web usará el puerto para la aplicación (5106 en este ejemplo).

### <a name="adding-docker-to-your-projects"></a>Agregar Docker a los proyectos

El asistente que agrega compatibilidad con Docker se comunica con el proceso de Docker que se está ejecutando. El asistente no se ejecutará correctamente si Docker no está funcionando cuando se inicie el asistente. Además, el asistente examinará el contenedor que ha elegido actualmente para agregar la compatibilidad correcta con Docker. Si quiere agregar compatibilidad con contenedores de Windows, debe ejecutar el asistente mientras Docker se ejecuta con contenedores de Windows configurados. Si quiere agregar compatibilidad con contenedores de Linux, ejecute el asistente mientras Docker se ejecuta con contenedores de Linux configurados.

>[!div class="step-by-step"]
[Anterior] (../docker-application-development-process/docker-app-development-workflow.md) [Siguiente] (../containerize-net-framework-applications/index.md)
