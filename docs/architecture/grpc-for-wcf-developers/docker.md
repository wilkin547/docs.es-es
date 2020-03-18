---
title: Docker - gRPC para desarrolladores de WCF
description: Creación de imágenes de Docker para aplicaciones gRPC de ASP.NET Core
ms.date: 09/02/2019
ms.openlocfilehash: e67c43f9486fbfe9a5d3e84e3b74770eb621f604
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79148119"
---
# <a name="create-docker-images"></a>Crear imágenes de Docker

En esta sección se describe la creación de imágenes de Docker para aplicaciones gRPC de ASP.NET Core, listas para ejecutarse en Docker, Kubernetes u otros entornos de contenedor. La aplicación de ejemplo utilizada, con una aplicación web ASP.NET Core MVC y un servicio gRPC, está disponible en el repositorio [dotnet-architecture/grpc-for-wcf-developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample) en GitHub.

## <a name="microsoft-base-images-for-aspnet-core-applications"></a>Imágenes base de Microsoft para aplicaciones ASP.NET Core

Microsoft proporciona una gama de imágenes base para compilar y ejecutar aplicaciones de .NET Core. Para crear una imagen ASP.NET Core 3.0, utilice dos imágenes base:

- Una imagen de SDK para compilar y publicar la aplicación.
- Una imagen en tiempo de ejecución para la implementación.

| Imagen | Descripción |
| ----- | ----------- |
| [mcr.microsoft.com/dotnet/core/sdk](https://hub.docker.com/_/microsoft-dotnet-core-sdk/) | Para crear `docker build`aplicaciones con . No se debe utilizar en producción. |
| [mcr.microsoft.com/dotnet/core/aspnet](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) | Contiene el tiempo de ejecución y ASP.NET dependencias principales. Para la producción. |

Para cada imagen, hay cuatro variantes basadas en diferentes distribuciones de Linux, distinguidas por etiquetas.

| Etiqueta(s) de imagen (s) | Linux | Notas |
| --------- | ----- | ----- |
| 3.0-buster, 3.0 | Debian 10 | La imagen predeterminada si no se especifica ninguna variante del sistema operativo. |
| 3.0-alpino | Alpine 3.9 | Las imágenes base alpinas son mucho más pequeñas que las de Debian o Ubuntu. |
| 3.0-disco | Ubuntu 19.04 | |
| 3.0-biónico | Ubuntu 18.04 | |

La imagen base Alpine es de alrededor de 100 MB, en comparación con 200 MB para las imágenes de Debian y Ubuntu. Algunos paquetes de software o bibliotecas podrían no estar disponibles en la gestión de paquetes de Alpine. Si no está seguro de qué imagen utilizar, probablemente debería elegir el Debian predeterminado.

> [!IMPORTANT]
> Asegúrese de utilizar la misma variante de Linux para la compilación y el tiempo de ejecución. Es posible que las aplicaciones creadas y publicadas en una variante no funcionen en otra.

## <a name="create-a-docker-image"></a>Cree una imagen de Docker.

Una imagen de Docker se define mediante un *Dockerfile*. Se trata de un archivo de texto que contiene todos los comandos necesarios para compilar la aplicación e instalar las dependencias necesarias para compilar o ejecutar la aplicación. En el ejemplo siguiente se muestra el Dockerfile más sencillo para una aplicación ASP.NET Core 3.0:

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

El Dockerfile tiene dos partes: `sdk` la primera utiliza la imagen base para compilar y publicar la aplicación; el segundo crea una `aspnet` imagen en tiempo de ejecución desde la base. Esto se `sdk` debe a que la imagen es de alrededor de 900 MB, en comparación con alrededor de 200 MB para la imagen en tiempo de ejecución, y la mayoría de su contenido es innecesario en tiempo de ejecución.

### <a name="the-build-steps"></a>Los pasos de construcción

| Paso | Descripción |
| ---- | ----------- |
| `FROM ...` | Declara la imagen base y `builder` asigna el alias. |
| `WORKDIR /src` | Crea `/src` el directorio y lo establece como el directorio de trabajo actual. |
| `COPY . .` | Copia todo debajo del directorio actual en el host en el directorio actual de la imagen. |
| `RUN dotnet restore` | Restaura los paquetes externos (ASP.NET Framework Core 3.0 está preinstalado con el SDK). |
| `RUN dotnet publish ...` | Compila y publica una versión de lanzamiento. Tenga en `--runtime` cuenta que la marca no es necesaria. |

### <a name="the-runtime-image-steps"></a>Los pasos de la imagen en tiempo de ejecución

| Paso | Descripción |
| ---- | ----------- |
| `FROM ...` | Declara una nueva imagen base. |
| `WORKDIR /app` | Crea `/app` el directorio y lo establece como el directorio de trabajo actual. |
| `COPY --from=builder ...` | Copia la aplicación publicada de la imagen `builder` anterior, `FROM` utilizando el alias de la primera línea. |
| `ENTRYPOINT [ ... ]` | Establece el comando que se ejecutará cuando se inicie el contenedor. El `dotnet` comando de la imagen en tiempo de ejecución solo puede ejecutar archivos DLL. |

### <a name="https-in-docker"></a>HTTPS en Docker

Las imágenes base `ASPNETCORE_URLS` de `http://+:80`Microsoft para Docker establecen la variable de entorno en , lo que significa que Kestrel se ejecuta sin HTTPS en ese puerto. Si usa HTTPS con un certificado personalizado (como se describe en [Aplicaciones gRPC autohospedadas),](self-hosted.md)debe invalidarlo. Establezca la variable de entorno en la parte de creación de imágenes en tiempo de ejecución del Dockerfile.

```dockerfile
# Runtime image creation
FROM mcr.microsoft.com/dotnet/core/aspnet:3.0

ENV ASPNETCORE_URLS=https://+:443
```

### <a name="the-dockerignore-file"></a>El archivo .dockerignore

Al `.gitignore` igual que los archivos que excluyen determinados archivos y directorios del control de código fuente, el `.dockerignore` archivo se puede utilizar para excluir archivos y directorios de ser copiados en la imagen durante la compilación. Esto no sólo ahorra tiempo copiando, sino que también `obj` puede evitar algunos errores que surgen de tener el directorio de su PC copiado en la imagen. Como mínimo, debe agregar entradas `bin` `obj` para `.dockerignore` y a su archivo.

```console
bin/
obj/
```

## <a name="build-the-image"></a>Compilación de la imagen

Para una solución con una sola aplicación y, por lo tanto, un solo Dockerfile, es más sencillo colocar el Dockerfile en el directorio base. En otras palabras, colóquelo `.sln` en el mismo directorio que el archivo. En ese caso, para compilar la `docker build` imagen, utilice el siguiente comando desde el directorio que contiene El Dockerfile.

```console
docker build --tag stockdata .
```

La marca `--tag` con nombre confuso (que `-t`se puede acortar a ) especifica el nombre completo de la imagen, incluida la etiqueta real si se especifica. El `.` final especifica el contexto en el que se ejecutará la compilación; el directorio de `COPY` trabajo actual para los comandos en el Dockerfile.

Si tiene varias aplicaciones dentro de una única solución, puede mantener el `.csproj` Dockerfile para cada aplicación en su propia carpeta, junto al archivo. Debe ejecutar el `docker build` comando desde el directorio base para asegurarse de que la solución y todos los proyectos se copian en la imagen. Puede especificar un Dockerfile debajo del `--file` directorio `-f`actual mediante el indicador (o ).

```console
docker build --tag stockdata --file src/StockData/Dockerfile .
```

## <a name="run-the-image-in-a-container-on-your-machine"></a>Ejecute la imagen en un contenedor de su máquina

Para ejecutar la imagen en la `docker run` instancia de Docker local, utilice el comando.

```console
docker run -ti -p 5000:80 stockdata
```

El `-ti` indicador conecta el terminal actual al terminal del contenedor y se ejecuta en modo interactivo. Publica `-p 5000:80` (enlaces) el puerto 80 en el contenedor al puerto 5000 en la interfaz de red localhost.

## <a name="push-the-image-to-a-registry"></a>Inserte la imagen en un registro

Después de comprobar que la imagen funciona, insóquela en un registro de Docker para que esté disponible en otros sistemas. Las redes internas tendrán que aprovisionar un registro de Docker. Esto puede ser tan simple como ejecutar la [propia `registry` imagen de Docker](https://docs.docker.com/registry/deploying/) (el registro de Docker se ejecuta en un contenedor de Docker), pero hay varias soluciones más completas disponibles. Para uso compartido externo y uso en la nube, hay varios registros administrados disponibles, como [Azure Container Registry](https://docs.microsoft.com/azure/container-registry/) o Docker [Hub](https://docs.docker.com/docker-hub/repos/).

Para insertar en Docker Hub, prefije el nombre de la imagen con el nombre de usuario u organización.

```console
docker tag stockdata myorg/stockdata
docker push myorg/stockdata
```

Para insertar en un registro privado, prefije el nombre de la imagen con el nombre de host del registro y el nombre de la organización.

```console
docker tag stockdata internal-registry:5000/myorg/stockdata
docker push internal-registry:5000/myorg/stockdata
```

Una vez que la imagen está en un registro, puede implementarla en hosts de Docker individuales o en un motor de orquestación de contenedores como Kubernetes.

>[!div class="step-by-step"]
>[Anterior](self-hosted.md)
>[Siguiente](kubernetes.md)
