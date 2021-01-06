---
title: Docker-gRPC para desarrolladores de WCF
description: Creación de imágenes de Docker para aplicaciones de ASP.NET Core gRPC
ms.date: 12/15/2020
ms.openlocfilehash: f662dbd67f00b828f3e1dfa47359a450dd1c5900
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938421"
---
# <a name="create-docker-images"></a>Creación de imágenes de Docker

En esta sección se describe la creación de imágenes de Docker para aplicaciones ASP.NET Core gRPC, listas para ejecutarse en Docker, Kubernetes u otros entornos de contenedores. La aplicación de ejemplo usada, con una aplicación web MVC ASP.NET Core y un servicio gRPC, está disponible en el repositorio [dotnet-Architecture/gRPC-for-WCF-Developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample) en github.

## <a name="microsoft-base-images-for-aspnet-core-applications"></a>Imágenes base de Microsoft para aplicaciones ASP.NET Core

Microsoft proporciona una variedad de imágenes base para compilar y ejecutar aplicaciones de .NET Core. Para crear una imagen ASP.NET Core 3,0, se usan dos imágenes base:

- Una imagen de SDK para compilar y publicar la aplicación.
- Una imagen en tiempo de ejecución para la implementación.

| Imagen | Descripción |
| ----- | ----------- |
| [mcr.microsoft.com/dotnet/sdk](https://hub.docker.com/_/microsoft-dotnet-sdk/) | Para compilar aplicaciones con `docker build` . No se va a usar en producción. |
| [mcr.microsoft.com/dotnet/aspnet](https://hub.docker.com/_/microsoft-dotnet-aspnet/) | Contiene las dependencias de tiempo de ejecución y ASP.NET Core. Para producción. |

Para cada imagen, hay cuatro variantes basadas en distintas distribuciones de Linux, diferenciadas por etiquetas.

| Etiqueta (s) de imagen | Linux | Notas |
| --------- | ----- | ----- |
| 5,0-validador, 5,0 | Debian 10 | La imagen predeterminada si no se especifica ninguna variante del sistema operativo. |
| 5,0-Alpine | Alpine 3,9 | Las imágenes de Alpine base son mucho más pequeñas que las de Debian o Ubuntu. |
| 5,0-disco | Ubuntu 19.04 | |
| 5,0-Bionic | Ubuntu 18.04 | |

La imagen de la base de Alpine es aproximadamente 100 MB, en comparación con 200 MB para las imágenes de Debian y Ubuntu. Es posible que algunos paquetes de software o bibliotecas no estén disponibles en la administración de paquetes de Alpine. Si no está seguro de la imagen que se va a usar, probablemente debería elegir el Debian predeterminado.

> [!IMPORTANT]
> Asegúrese de usar la misma variante de Linux para la compilación y el tiempo de ejecución. Es posible que las aplicaciones compiladas y publicadas en una variante no funcionen en otra.

## <a name="create-a-docker-image"></a>Cree una imagen de Docker.

Una imagen de Docker se define mediante un *Dockerfile*. Este *Dockerfile* es un archivo de texto que contiene todos los comandos necesarios para compilar la aplicación e instalar las dependencias necesarias para compilar o ejecutar la aplicación. En el ejemplo siguiente se muestra el Dockerfile más sencillo para una aplicación ASP.NET Core 5,0:

```dockerfile
FROM mcr.microsoft.com/dotnet/sdk:5.0 as build

WORKDIR /src

COPY ./StockKube.sln .
COPY ./src/StockData/StockData.csproj ./src/StockData/
COPY ./src/StockWeb/StockWeb.csproj ./src/StockWeb/

RUN dotnet restore

COPY . .

RUN dotnet publish --no-restore -c Release -o /published src/StockData/StockData.csproj

FROM mcr.microsoft.com/dotnet/aspnet:5.0 as runtime

# Uncomment the line below if running with HTTPS
# ENV ASPNETCORE_URLS=https://+:443

WORKDIR /app

COPY --from=build /published .

ENTRYPOINT [ "dotnet", "StockData.dll" ]
```

Dockerfile tiene dos partes: la primera usa la `sdk` imagen base para compilar y publicar la aplicación; la segunda crea una imagen en tiempo de ejecución de la `aspnet` base. Esto se debe a que la `sdk` imagen es de aproximadamente 900 MB, en comparación con aproximadamente 200 MB para la imagen en tiempo de ejecución, y la mayor parte de su contenido no es necesario en tiempo de ejecución.

### <a name="the-build-steps"></a>Pasos de compilación

| Paso | Descripción |
| ---- | ----------- |
| `FROM ...` | Declara la imagen base y asigna el `builder` alias. |
| `WORKDIR /src` | Crea el `/src` Directorio y lo establece como el directorio de trabajo actual. |
| `COPY . .` | Copia todo el directorio actual del host en el directorio actual de la imagen. |
| `RUN dotnet restore` | Restaura los paquetes externos (ASP.NET Core marco de trabajo de 3,0 se instala previamente con el SDK). |
| `RUN dotnet publish ...` | Compila y publica una compilación de versión. Tenga en cuenta que la `--runtime` marca no es necesaria. |

### <a name="the-runtime-image-steps"></a>Pasos de la imagen en tiempo de ejecución

| Paso | Descripción |
| ---- | ----------- |
| `FROM ...` | Declara una nueva imagen base. |
| `WORKDIR /app` | Crea el `/app` Directorio y lo establece como el directorio de trabajo actual. |
| `COPY --from=builder ...` | Copia la aplicación publicada de la imagen anterior mediante el uso del `builder` alias de la primera `FROM` línea. |
| `ENTRYPOINT [ ... ]` | Establece que el comando se ejecute cuando se inicie el contenedor. El `dotnet` comando de la imagen en tiempo de ejecución solo puede ejecutar archivos dll. |

### <a name="https-in-docker"></a>HTTPS en Docker

Imágenes base de Microsoft para Docker establezca la `ASPNETCORE_URLS` variable de entorno en `http://+:80` , lo que significa que Kestrel se ejecuta sin HTTPS en ese puerto. Si usa HTTPS con un certificado personalizado (como se describe en [aplicaciones gRPC autohospedadas](self-hosted.md)), debe invalidar esta configuración. Establezca la variable de entorno en la parte de creación de la imagen en tiempo de ejecución de su Dockerfile.

```dockerfile
# Runtime image creation
FROM mcr.microsoft.com/dotnet/aspnet:5.0

ENV ASPNETCORE_URLS=https://+:443
```

### <a name="the-dockerignore-file"></a>El archivo. dockerignore

De forma muy similar a `.gitignore` los archivos que excluyen determinados archivos y directorios del control de código fuente, el `.dockerignore` archivo se puede usar para excluir archivos y directorios de copiarse en la imagen durante la compilación. Este archivo no solo ahorra tiempo en la copia, sino que también puede evitar algunos errores que surgen cuando se `obj` copia el directorio del equipo en la imagen. Como mínimo, debe agregar entradas para `bin` y `obj` en el `.dockerignore` archivo.

```console
bin/
obj/
```

## <a name="build-the-image"></a>Compilación de la imagen

En el caso de una `StockKube.sln` solución que contenga dos aplicaciones diferentes `StockData` y `StockWeb` , es más sencillo colocar el Dockerfile para cada uno de ellos en el directorio base. En ese caso, para compilar la imagen, use el siguiente `docker build` comando desde el mismo directorio donde `.sln` reside el archivo.

```console
docker build -t stockdata:1.0.0 -f .\src\StockData\Dockerfile .
```

La marca con el nombre confuso `--tag` (que se puede acortar a `-t` ) especifica el nombre completo de la imagen, incluida la etiqueta real si se especifica. `.`Al final especifica el contexto en el que se ejecutará la compilación; el directorio de trabajo actual para los `COPY` comandos de Dockerfile.

Si tiene varias aplicaciones en una única solución, puede mantener el Dockerfile para cada aplicación en su propia carpeta, junto al `.csproj` archivo. Siga ejecutando el `docker build` comando desde el directorio base para asegurarse de que la solución y todos los proyectos se copian en la imagen. Puede especificar un Dockerfile debajo del directorio actual mediante la `--file` marca (o `-f` ).

```console
docker build -t stockdata:1.0.0 -f .\src\StockData\Dockerfile .
```

## <a name="run-the-image-in-a-container-on-your-machine"></a>Ejecutar la imagen en un contenedor en el equipo

Para ejecutar la imagen en la instancia de Docker local, use el `docker run` comando.

```console
docker run -ti -p 5000:80 stockdata:1.0.0
```

La `-ti` marca conecta el terminal actual al terminal del contenedor y se ejecuta en modo interactivo. El `-p 5000:80` Puerto de publicación (vínculos) 80 del contenedor al puerto 5000 en la interfaz de red de localhost.

## <a name="push-the-image-to-a-registry"></a>Inserte la imagen en un registro

Una vez que haya comprobado que la imagen funciona, inserte en un registro de Docker para que esté disponible en otros sistemas. Las redes internas deberán aprovisionar un registro de Docker. Esta actividad puede ser tan sencilla como la ejecución de la [propia `registry` imagen de Docker](https://docs.docker.com/registry/deploying/) (el registro de Docker se ejecuta en un contenedor de Docker), pero hay varias soluciones más completas disponibles. Para uso compartido externo y uso en la nube, hay varios registros administrados disponibles, como [Azure Container Registry](/azure/container-registry/) o [Docker Hub](https://docs.docker.com/docker-hub/repos/).

Para enviar a Docker Hub, Prefije el nombre de la imagen con el nombre de usuario o de la organización.

```console
docker tag stockdata:1.0.0 <myorg>/stockdata:1.0.0
docker push <myorg>/stockdata:1.0.0
```

Para enviar a un registro privado, Prefije el nombre de la imagen con el nombre de host del registro y el nombre de la organización.

```console
docker tag stockdata <internal-registry:5000>/<myorg>/stockdata:1.0.0
docker push <internal-registry:5000>/<myorg>/stockdata:1.0.0
```

Una vez que la imagen se encuentra en un registro, puede implementarla en hosts de Docker individuales o en un motor de orquestación de contenedores como Kubernetes.

>[!div class="step-by-step"]
>[Anterior](self-hosted.md)
>[Siguiente](kubernetes.md)
