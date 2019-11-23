---
title: Docker-gRPC para desarrolladores de WCF
description: Creación de imágenes de Docker para aplicaciones de ASP.NET Core gRPC
ms.date: 09/02/2019
ms.openlocfilehash: a5aceb4b5270cb828965e990a62db4147012adff
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967838"
---
# <a name="docker"></a>Docker

En esta sección se tratará la creación de imágenes de Docker para aplicaciones ASP.NET Core gRPC, listas para ejecutarse en Docker, Kubernetes u otros entornos de contenedores. La aplicación de ejemplo usada, con una aplicación web MVC ASP.NET Core y un servicio gRPC, está disponible en el repositorio [dotnet-Architecture/gRPC-for-WCF-Developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample) en github.

## <a name="microsoft-base-images-for-aspnet-core-applications"></a>Imágenes base de Microsoft para aplicaciones ASP.NET Core

Microsoft proporciona una variedad de imágenes base para compilar y ejecutar aplicaciones de .NET Core. Para crear una imagen ASP.NET Core 3,0, se usan dos imágenes base: una imagen de SDK para compilar y publicar la aplicación, y una imagen en tiempo de ejecución para la implementación.

| Imagen | Descripción |
| ----- | ----------- |
| [mcr.microsoft.com/dotnet/core/sdk](https://hub.docker.com/_/microsoft-dotnet-core-sdk/) | Para compilar aplicaciones con `docker build`. No se va a usar en producción. |
| [mcr.microsoft.com/dotnet/core/aspnet](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) | Contiene las dependencias de tiempo de ejecución y ASP.NET Core. Para producción. |

Para cada imagen, hay cuatro variantes basadas en distintas distribuciones de Linux, diferenciadas por etiquetas.

| Etiqueta (s) de imagen | Linux | Notas |
| --------- | ----- | ----- |
| 3,0-validador, 3,0 | Debian 10 | La imagen predeterminada si no se especifica ninguna variante del sistema operativo. |
| 3,0-Alpine | Alpine 3,9 | Las imágenes de Alpine base son mucho más pequeñas que las de Debian o Ubuntu. |
| 3,0-disco | Ubuntu 19,04 | |
| 3,0-Bionic | Ubuntu 18.04 | |

La imagen de Alpine base es aproximadamente 100 MB, en comparación con 200 MB para las imágenes de Debian y Ubuntu, pero puede que algunos paquetes de software o bibliotecas no estén disponibles en la administración de paquetes de Alpine. Si no está seguro de la imagen que se va a usar, es mejor ajustarla al Debian predeterminado a menos que tenga una necesidad convincente de usar un distribución diferente.

> [!IMPORTANT]
> Asegúrese de usar la misma variante de Linux para la compilación y el tiempo de ejecución. Es posible que las aplicaciones compiladas y publicadas en una variante no funcionen en otra.

## <a name="create-a-docker-image"></a>Creación de una imagen de Docker

Una imagen de Docker se define mediante un *Dockerfile*, un archivo de texto que contiene todos los comandos necesarios para compilar la aplicación e instalar las dependencias necesarias para compilar o ejecutar la aplicación. En el ejemplo siguiente se muestra el Dockerfile más sencillo para una aplicación ASP.NET Core 3,0:

```dockerfile
# Application build steps
FROM mcr.microsoft.com/dotnet/core/sdk:3.0 as builder

WORKDIR /src

COPY . .

RUN dotnet restore

RUN dotnet publish -c Release -o /published src/StockData/StockData.csproj

# Runtime image creation
FROM mcr.microsoft.com/dotnet/core/aspnet:3.0

# Uncomment the line below if running with HTTPS
# ENV ASPNETCORE_URLS=https://+:443

WORKDIR /app

COPY --from=builder /published .

ENTRYPOINT [ "dotnet", "StockData.dll" ]
```

Dockerfile tiene dos partes: la primera usa la imagen base `sdk` para compilar y publicar la aplicación. la segunda crea una imagen en tiempo de ejecución de la base `aspnet`. Esto se debe a que la imagen de `sdk` es aproximadamente 900 MB en comparación con aproximadamente 200 MB para la imagen en tiempo de ejecución, y la mayor parte de su contenido no es necesario en tiempo de ejecución.

### <a name="the-build-steps"></a>Pasos de compilación

| Paso | Descripción |
| ---- | ----------- |
| `FROM ...` | Declara la imagen base y asigna el alias `builder` (vea la siguiente sección para obtener una explicación). |
| `WORKDIR /src` | Crea el directorio `/src` y lo establece como el directorio de trabajo actual. |
| `COPY . .` | Copia todo el directorio actual del host en el directorio actual de la imagen. |
| `RUN dotnet restore` | Restaura los paquetes externos (ASP.NET Core marco de trabajo de 3,0 se instala previamente con el SDK). |
| `RUN dotnet publish ...` | Compila y publica una compilación de versión. Tenga en cuenta que la marca `--runtime` no es necesaria. |

### <a name="the-runtime-image-steps"></a>Pasos de la imagen en tiempo de ejecución

| Paso | Descripción |
| ---- | ----------- |
| `FROM ...` | Declara una nueva imagen base. |
| `WORKDIR /app` | Crea el directorio `/app` y lo establece como el directorio de trabajo actual. |
| `COPY --from=builder ...` | Copia la aplicación publicada de la imagen anterior, mediante el `builder` alias de la primera línea `FROM`. |
| `ENTRYPOINT [ ... ]` | Establece que el comando se ejecute cuando se inicie el contenedor. El comando `dotnet` de la imagen en tiempo de ejecución solo puede ejecutar archivos DLL. |

### <a name="https-in-docker"></a>HTTPS en Docker

Imágenes base de Microsoft para Docker establezca la variable de entorno `ASPNETCORE_URLS` en `http://+:80`, lo que significa que Kestrel se ejecutará sin HTTPS en ese puerto. Si usa HTTPS con un certificado personalizado (como se describe en [la sección anterior](self-hosted.md)), debe invalidarlo estableciendo la variable **de entorno en la parte de creación** de la imagen en tiempo de ejecución de su Dockerfile.

```dockerfile
# Runtime image creation
FROM mcr.microsoft.com/dotnet/core/aspnet:3.0

ENV ASPNETCORE_URLS=https://+:443
```

### <a name="the-dockerignore-file"></a>El archivo. dockerignore

Al igual que los archivos de `.gitignore` que excluyen determinados archivos y directorios del control de código fuente, el archivo de `.dockerignore` se puede usar para excluir los archivos y directorios que se copian en la imagen durante la compilación. Esto no solo ahorra tiempo en la copia, sino que también puede evitar algunos errores confusos que surgen de tener (en particular) el directorio `obj` del equipo copiado en la imagen. Debe agregar al menos entradas para `bin` y `obj` al archivo `.dockerignore`.

```console
bin/
obj/
```

## <a name="build-the-image"></a>Compilar la imagen

Para una solución con una sola aplicación y, por lo tanto, un solo Dockerfile, es más sencillo colocar el Dockerfile en el directorio base; es decir, el mismo directorio que el archivo de `.sln`. En ese caso, para compilar la imagen, use el siguiente comando de `docker build` desde el directorio que contiene Dockerfile.

```console
docker build --tag stockdata .
```

La marca de `--tag` con el nombre confuso (que se puede acortar a `-t`) especifica el nombre completo de la imagen, *incluida* la etiqueta real si se especifica. El `.` al final especifica el *contexto* en el que se ejecutará la compilación; directorio de trabajo actual para los comandos `COPY` de Dockerfile.

Si tiene varias aplicaciones en una única solución, puede mantener el Dockerfile para cada aplicación en su propia carpeta, junto al archivo `.csproj`, pero debe ejecutar el comando `docker build` desde el directorio base para asegurarse de que la solución y todos los proyectos se copian en la imagen. Puede especificar un Dockerfile debajo del directorio actual mediante la marca `--file` (o `-f`).

```console
docker build --tag stockdata --file src/StockData/Dockerfile .
```

## <a name="run-the-image-in-a-container-on-your-machine"></a>Ejecutar la imagen en un contenedor en el equipo

Para ejecutar la imagen en la instancia de Docker local, use el comando `docker run`.

```console
docker run -ti -p 5000:80 stockdata
```

La marca de `-ti` conecta el terminal actual al terminal del contenedor y se ejecuta en modo interactivo. El `-p 5000:80` publica (vínculos) el puerto 80 en el contenedor en el puerto 80 en la interfaz de red de localhost.

## <a name="push-the-image-to-a-registry"></a>Inserte la imagen en un registro

Una vez que haya comprobado que la imagen funciona, debe insertarla en un registro de Docker para que esté disponible en otros sistemas. Las redes internas deberán aprovisionar un registro de Docker. Esto puede ser tan sencillo como la ejecución de la [propia imagen `registry` de Docker](https://docs.docker.com/registry/deploying/) (es decir, el registro de Docker se ejecuta en un contenedor de Docker), pero hay varias soluciones más completas disponibles. Para uso compartido externo y uso en la nube, hay varios registros administrados disponibles, como [Azure Container Registry](https://docs.microsoft.com/azure/container-registry/) o [Docker Hub](https://docs.docker.com/docker-hub/repos/).

Para enviarlo a Docker Hub, anteponga el nombre de la imagen al nombre de usuario o de la organización.

```console
docker tag stockdata myorg/stockdata
docker push myorg/stockdata
```

Para enviar a un registro privado, Prefije el nombre de la imagen con el nombre de host del registro y el nombre de la organización.

```console
docker tag stockdata internal-registry:5000/myorg/stockdata
docker push internal-registry:5000/myorg/stockdata
```

Una vez que la imagen se encuentra en un registro, puede implementarla en hosts de Docker individuales o en un motor de orquestación de contenedores como Kubernetes.

>[!div class="step-by-step"]
>[Anterior](self-hosted.md)
>[Siguiente](kubernetes.md)
