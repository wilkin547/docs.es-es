---
title: "Creación de imágenes de Docker de .NET Core"
description: "Descripción de las imágenes de Docker y .NET Core"
keywords: .NET, .NET Core, Docker
author: spboyer
ms.author: shboyer
ms.date: 08/29/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-docker
ms.devlang: dotnet
ms.assetid: 03c28597-7e73-46d6-a9c3-f9cb55642739
ms.translationtype: HT
ms.sourcegitcommit: 9dc52f3a8c74c1aa575a83cb3bbd579b93fae9ae
ms.openlocfilehash: 0e679ffc22f52de5e2ce8194942efbb2f5299ee4
ms.contentlocale: es-es
ms.lasthandoff: 09/06/2017

---

#<a name="building-docker-images-for-net-core-applications"></a>Creación de imágenes de Docker para aplicaciones de .NET Core

 
> [!IMPORTANT]
> En estos momentos, estamos actualizando para .NET Core 2.0. Las instrucciones siguientes están obsoletas. Lamentamos las molestias.

Para ver una descripción de cómo usar .NET Core y Docker juntos, primero debemos conocer las diferentes imágenes de Docker que se ofrecen y cuándo es mejor usar cada una. Aquí examinaremos las variantes ofrecidas, compilaremos una API web ASP.NET Core, usaremos las herramientas de Yeoman Docker para crear un contenedor depurable y echaremos un vistazo a cómo Visual Studio Code puede ayudar en el proceso. 

## <a name="docker-image-optimizations"></a>Optimizaciones de imágenes de Docker

Al crear imágenes de Docker para desarrolladores, nos centramos en tres escenarios principales:

- Imágenes usadas para desarrollar aplicaciones .NET Core
- Imágenes usadas para crear aplicaciones .NET Core
- Imágenes usadas para ejecutar aplicaciones de .NET Core

¿Por qué tres imágenes?
Al desarrollar, compilar y ejecutar aplicaciones en contenedor, tenemos prioridades diferentes.
- **Desarrollo:** la rapidez con que se pueden iterar los cambios y la posibilidad de depurar los cambios. El tamaño de la imagen no es tan importante, sino que pueda hacer cambios en el código y verlos rápidamente. Algunas de las herramientas, como [yo docker](https://aka.ms/yodocker), disponibles para usarlas en Visual Studio Code emplean esta imagen durante la fase de desarrollo. 
- **Compilación:** lo que es necesario para compilar la aplicación. Esto incluye el compilador y cualquier otra dependencia para optimizar los archivos binarios. Esta imagen no es la imagen que se implementa, sino más bien una imagen que se utiliza para compilar el contenido que se coloca en una imagen de producción. Esta imagen se usaría de la integración continua o el entorno de compilación. Por ejemplo, en lugar de instalar todas las dependencias directamente en un agente de compilación, el agente de compilación crearía una instancia de una imagen de compilación para compilar la aplicación con todas las dependencias necesarias para compilar la aplicación contenida en la imagen. El agente de compilación solo necesita saber cómo ejecutar la imagen de Docker. 
- **Producción:** la rapidez con que puede implementar e iniciar la imagen. Esta imagen es pequeña, por lo que puede desplazarse rápidamente a través de la red desde el Registro a los hosts de Docker. El contenido está listo para ejecutar, lo que permite el tiempo más rápido desde la ejecución de Docker hasta el procesamiento de los resultados. En el modelo de Docker inmutable, no hay ninguna necesidad de compilación dinámica del código. El contenido que se coloca en esta imagen estaría limitado a los archivos binarios y al contenido necesario para ejecutar la aplicación. Por ejemplo, el resultado publicado mediante `dotnet publish` que contiene los archivos binarios compilados, imágenes y archivos .js y .css. Con el tiempo, verá imágenes que contienen paquetes anteriores a la compilación JIT.  

Aunque hay varias versiones de la imagen de .NET Core, comparten una o varias capas. La cantidad de espacio en disco necesario para almacenar o la diferencia para extraer del Registro es mucho menor que la totalidad porque todas las imágenes comparten la misma capa base y posiblemente otras.  

## <a name="docker-image-variations"></a>Variantes de imagen de Docker

Para lograr los objetivos anteriores, proporcionamos variantes de imágenes en [microsoft/dotnet](https://hub.docker.com/r/microsoft/dotnet/).

- `microsoft/dotnet:<version>-sdk`: esta es **microsoft/dotnet:1.0.0-preview2-sdk**. Esta imagen contiene el SDK de .NET Core que incluye .NET Core y las herramientas de línea de comandos (CLI). Esta imagen se asigna al **escenario de desarrollo**. Esta imagen se usaría para el desarrollo, la depuración y las pruebas unitarias locales. Por ejemplo, todo el desarrollo realizado antes de proteger el código. Esta imagen también puede usarse en sus escenarios de **compilación**.

- `microsoft/dotnet:<version>-core` : esta es **microsoft/dotnet:1.0.0-core**, que ejecuta aplicaciones [.NET Core portátiles](../deploying/index.md) y está optimizada para ejecutar la aplicación en **producción**. No contiene el SDK y tiene como fin tomar la salida optimizada de `dotnet publish`. El tiempo de ejecución portátil es ideal para escenarios de contenedor de Docker dado que la ejecución de varios contenedores se beneficia de las capas de imágenes compartidas.  

## <a name="alternative-images"></a>Imágenes nativas

Además de los escenarios optimizados de desarrollo, compilación y producción, proporcionamos imágenes adicionales:

- `microsoft/dotnet:<version>-onbuild`: esta es **microsoft/dotnet:1.0.0-preview2-onbuild**, que contiene desencadenadores [ONBUILD](https://docs.docker.com/engine/reference/builder/#/onbuild). La compilación [COPIA](https://docs.docker.com/engine/reference/builder/#/copy) la aplicación, ejecuta `dotnet restore` y crea una instrucción [ENTRYPOINT](https://docs.docker.com/engine/reference/builder/#/entrypoint) `dotnet run` para ejecutar la aplicación cuando se ejecuta la imagen de Docker. Aunque no es una imagen optimizada para producción, algunos pueden encontrarla útil para copiar simplemente su código fuente en una imagen y ejecutarlo. 

- `microsoft/dotnet:<version>-core-deps`: esta es **microsoft/dotnet:1.0.0-core-deps**. Si desea ejecutar aplicaciones autocontenidas, use esta imagen. Contiene el sistema operativo con todas las dependencias nativas necesarias en .NET Core. Esta imagen también puede usarse como base para sus propias compilaciones CoreFX o CoreCLR personalizadas. Aunque la variante **onbuild** está optimizada para colocar simplemente el código en una imagen y ejecutarlo, esta imagen está optimizada para tener solo las dependencias del sistema operativo necesarias para ejecutar aplicaciones .NET Core que tienen empaquetado el entorno de tiempo de ejecución .NET con la aplicación. Generalmente, esta imagen no está optimizada para ejecutar varios contenedores .NET Core en el mismo host, según cada imagen incluye el tiempo de ejecución de .NET Core dentro de la aplicación y no se beneficiará de las capas de imagen.   

Versiones más recientes de cada variante:

- `microsoft/dotnet` o `microsoft/dotnet:latest` (incluye el SDK)
- `microsoft/dotnet:onbuild`
- `microsoft/dotnet:core`
- `microsoft/dotnet:core-deps`

Esta es una lista de las imágenes después de `docker pull <imagename>` en una máquina de desarrollo para mostrar los distintos tamaños. Observe que la variante de desarrollo/compilación `microsoft/dotnet:1.0.0-preview2-sdk` es más grande dado que contiene el SDK para desarrollar y compilar la aplicación. La variante de producción, `microsoft/dotnet:core` es menor, ya que solo contiene el entorno de tiempo de ejecución de .NET Core. La imagen mínima que se puede usar en Linux, `core-deps`, es bastante más pequeña, sin embargo, la aplicación deberá hacer una copia privada del entorno de tiempo de ejecución de .NET con ella. Como los contenedores ya son barreras de aislamiento privadas, perderá esa optimización al ejecutar varios contenedores basados en dotnet. 

```
REPOSITORY          TAG                     IMAGE ID            SIZE
microsoft/dotnet    1.0.0-preview2-onbuild  19b6a6c4b1db        540.4 MB
microsoft/dotnet    onbuild                 19b6a6c4b1db        540.4 MB
microsoft/dotnet    1.0.0-preview2-sdk      a92c3d9ad0e7        540.4 MB
microsoft/dotnet    core                    5224a9f2a2aa        253.2 MB
microsoft/dotnet    1.0.0-core-deps         c981a2eebe0e        166.2 MB
microsoft/dotnet    core-deps               c981a2eebe0e        166.2 MB
microsoft/dotnet    latest                  03c10abbd08a        540.4 MB
microsoft/dotnet    1.0.0-core              b8da4a1fd280        253.2 MB
```

## <a name="prerequisites"></a>Requisitos previos

Para la compilación y ejecución, necesita tener instaladas algunas cosas:

- [Núcleo de .NET](http://dot.net)
- [Docker](https://www.docker.com/products/docker) para ejecutar sus contenedores de Docker localmente.
- [Node.js](https://nodejs.org/)
- [Generador de Yeoman para ASP.NET](https://github.com/omnisharp/generator-aspnet) para crear la aplicación de API web.
- [Generador de Yeoman para Docker](http://aka.ms/yodocker) de Microsoft.

Instale los generadores de Yeoman para ASP.NET Core y Docker mediante npm. 

```
npm install -g yo generator-aspnet generator-docker
```

> [!NOTE]
> En este ejemplo se usará [Visual Studio Code](http://code.visualstudio.com) en el editor.

## <a name="creating-the-web-api-application"></a>Creación de la aplicación de API web

Como punto de referencia, antes de que meter la aplicación en un contenedor, ejecútela localmente. 

La aplicación finalizada se encuentra en el [repositorio dotnet/docs en GitHub](https://github.com/dotnet/docs/tree/master/samples/core/docker/building-net-docker-images). Para obtener instrucciones de descarga, vea [Ejemplos y tutoriales](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

Cree un directorio para la aplicación.

Abra un comando o una sesión de terminal en ese directorio y use el generador de ASP.NET Yeoman escribiendo lo siguiente:
```
yo aspnet
```

Seleccione **Web API Application** (Aplicación API web) y escriba **api**.  Después de aplicar la técnica scaffolding a la aplicación, cambie al directorio `/api` y restaure las dependencias de NuGet mediante `dotnet restore`.

```
cd api
dotnet restore
```

Pruebe la aplicación con `dotnet run` y vaya a **http://localhost:5000/api/values**.

```javascript
[
    "value1",
    "value2"
]
```

Use `Ctrl+C` para detener la aplicación.

## <a name="adding-docker-support"></a>Adición de compatibilidad con Docker

Para agregar compatibilidad con Docker al proyecto es necesario usar el generador Yeoman de Microsoft. Actualmente se admiten proyectos .NET Core, Node.js y Go mediante la creación de un Dockerfile y scripts que ayudan a compilar y ejecutar proyectos dentro de contenedores. También se agregan archivos específicos de Visual Studio Code (launch.json, tasks.json) para la depuración del editor y la compatibilidad con la paleta de comandos.

```console
$ yo docker

     _-----_     ╭──────────────────────────╮
    |       |    │   Welcome to the Docker  │
    |--(o)--|    │        generator!        │
   `---------´   │     Let's add Docker     │
    ( _´U`_ )    │  container magic to your │
    /___A___\   /│           app!           │
     |  ~  |     ╰──────────────────────────╯
   __'.___.'__
 ´   `  |° ´ Y `

? What language is your project using? (Use arrow keys)
❯ .NET Core
  Golang
  Node.js
```

- Seleccione `.NET Core` como tipo de proyecto.
- `rtm` para la versión de .NET Core.
- `Y` el proyecto usa un servidor web.
- `5000` es el puerto en el que escucha la aplicación de API web (http://localhost:5000).
- `api` para el nombre de imagen.
- `api` para el nombre del servicio.
- `api` para el proyecto de redacción. 
- `Y` para sobrescribir el Dockerfile actual.

Cuando finalice el generador, los siguientes archivos se agregan al proyecto.

- .vscode/launch.json
- Dockerfile.debug
- Dockerfile
- docker-compose.debug.yml
- docker-compose.yml
- dockerTask.ps1
- dockerTask.sh
- .vscode/tasks.json

El generador crea dos Dockerfiles.

**Dockerfile.debug**: este archivo se basa en la imagen **microsoft/dotnet:1.0.0-preview2-sdk** que, si advierte por la lista de variantes de imágenes, incluye el SDK, la CLI y .NET Core y será la imagen usada para el desarrollo y la depuración (F5). Al incluir todos estos componentes se produce una imagen más grande con un tamaño aproximado de 540 MB.

**Dockerfile**: esta imagen es la imagen de lanzamiento basada en **microsoft/dotnet:1.0.0-core** y se debe usar en producción. Cuando se compila esta imagen es de 253 MB aproximadamente.

### <a name="creating-the-docker-images"></a>Creación de las imágenes de Docker
Mediante el script `dockerTask.sh` o `dockerTask.ps1`, podemos compilar o componer la imagen y el contenedor para la aplicación de **api** en un entorno específico. Compile la imagen **debug** mediante la ejecución del comando siguiente.

```bash
./dockerTask.sh build debug
```

La imagen compilará la aplicación ASP.NET, ejecutará `dotnet restore`, agregará el depurador a la imagen, establecerá un `ENTRYPOINT` y, finalmente, copiará la aplicación en la imagen. El resultado es una imagen de Docker llamada *api* con una `TAG` de *debug*.  Vea las imágenes en la máquina mediante `docker images`.

```bash
docker images

REPOSITORY          TAG                  IMAGE ID            CREATED             SIZE
api                 debug                70e89fbc5dbe        a few seconds ago   779.8 MB
```

Otra manera de generar la imagen y ejecutar la aplicación dentro del contenedor de Docker es abrir la aplicación en Visual Studio Code y usar las herramientas de depuración. 

Seleccione el icono de depuración en la barra de vistas del lado izquierdo de Visual Studio Code.

![icono de depuración de vscode](./media/building-net-docker-images/debugging_debugicon.png)

A continuación, toque el icono de reproducción o F5 para generar la imagen e iniciar la aplicación dentro del contenedor. Se iniciará la API web mediante el explorador web predeterminado en http://localhost:5000.

![Depuración con las herramientas de Docker de VSCode](./media/building-net-docker-images/docker-tools-vscode-f5.png)

Puede establecer puntos de interrupción en la aplicación, ejecutar paso a paso, etc. como si la aplicación se ejecutara localmente en la máquina de desarrollo en lugar de en el contenedor. La ventaja de depurar dentro del contenedor es que es la misma imagen que se implementaría en un entorno de producción.

La creación de la imagen de lanzamiento o de producción requiere la ejecución del comando desde el terminal pasando el nombre del entorno `release`.

```bash
./dockerTask build release
```

El comando crea la imagen basándose en la imagen base **microsoft/dotnet:core** más pequeña, [EXPONE](https://docs.docker.com/engine/reference/builder/#/expose) el puerto 5000, establece el [PUNTO DE ENTRADA](https://docs.docker.com/engine/reference/builder/#/entrypoint) para `dotnet api.dll` y lo copia en el directorio `/app`. No hay ningún depurador, SDK o `dotnet restore` que dé lugar a una imagen mucho más pequeña. La imagen se denomina **api** con una `TAG` de **latest**.

```
REPOSITORY          TAG                  IMAGE ID            CREATED             SIZE
api                 debug                70e89fbc5dbe        1 hour ago        779.8 MB
api                 latest               ef17184c8de6        1 hour ago        260.7 MB
```

## <a name="summary"></a>Resumen

Mediante el generador de Docker para agregar los archivos necesarios a nuestra aplicación de API web se facilita el proceso para crear las versiones de desarrollo y producción de las imágenes.  Las herramientas son multiplataforma. Proporcionan también un script de PowerShell para lograr los mismos resultados en la integración de Windows y Visual Studio Code y ofrecen depuración paso a paso de la aplicación dentro del contenedor. Si comprende las variantes de imagen y los escenarios de destino, puede optimizar el proceso de desarrollo de bucle interior y conseguir imágenes optimizadas para implementaciones de producción.  



