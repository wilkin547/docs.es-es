---
title: "Uso de .NET Core SDK y herramientas de integración continua (CI) | Microsoft Docs"
description: "Uso de .NET Core SDK y herramientas de integración continua (CI)"
keywords: .NET, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 0d6e1e34-277c-4aaf-9880-3ebf81023857
translationtype: Human Translation
ms.sourcegitcommit: 796df1549a7553aa93158598d62338c02d4df73e
ms.openlocfilehash: 95c7f0f9911c7cb37c12afec74d0e942db77fbf6

---

# <a name="using-net-core-sdk-and-tools-in-continuous-integration-ci-net-core-tools-rc4"></a>Uso de .NET Core SDK y herramientas de integración continua (CI) (.NET Core Tools RC4)

> [!WARNING]
> Este tema se aplica a .NET Core Tools RC4. Para la versión .NET Core Tools Preview 2, consulte el tema [Uso de .NET Core SDK y herramientas de integración continua (CI)](../../tools/using-ci-with-cli.md).

## <a name="overview"></a>Información general
En este documento se describe el uso del SDK de .NET Core y sus herramientas en el servidor de compilación. En general, en un servidor de compilación de CI, desea automatizar la instalación de alguna manera. La automatización, idealmente, no debería requerir privilegios administrativos si fuera posible. 

Para las soluciones de CI de SaaS, hay varias opciones. En este documento se tratarán dos opciones muy populares, [TravisCI](https://travis-ci.org/) y [AppVeyor](https://www.appveyor.com/). Por supuesto, hay muchos otros servicios, pero los mecanismos de uso y la instalación deben ser similares.

## <a name="installation-options-for-ci-build-servers"></a>Opciones de instalación para los servidores de compilación de CI

## <a name="using-the-native-installers"></a>Uso de instaladores nativos
Si no representa ningún problema usar instaladores que requieren privilegios de administrador, pueden usarse los instaladores nativos para cada plataforma para configurar el servidor de compilación. Este enfoque, especialmente en el caso de los servidores de compilación de Linux, tiene la ventaja de la instalación automática de las dependencias necesarias para que se pueda ejecutar el SDK. Los instaladores nativos también instalarán una versión de todo el sistema del SDK, lo que puede ser deseable; si no es así, busque en el [uso de scripts del instalador](#using-the-installer-script) que se describe a continuación. 

El uso de este enfoque es sencillo. Para Linux, hay una opción de usar un administrador de paquetes basado en fuentes, como `apt-get` para Ubuntu o `yum` para CentOS o de usar los mismos paquetes (es decir, DEB o RPM). El primero requiere la configuración de la fuente que contiene los paquetes.

Para las plataformas de Windows, puede utilizar el MSI. 

Todos los archivos binarios se pueden encontrar en la [página de introducción de .NET Core](https://aka.ms/dotnetcoregs) que menciona los lanzamientos estables más recientes. Si desea utilizar las últimas versiones (y potencialmente inestables) o la versión más reciente, puede usar los vínculos del [repositorio CLI](https://github.com/dotnet/cli). 

## <a name="using-the-installer-script"></a>Uso del script del instalador
El uso del script del instalador permite la instalación sin derechos administrativos en el servidor de compilación. También permite una automatización muy fácil. El mismo script descargará los archivos ZIP o tarball necesarios y los descomprimirá. También agregará la ubicación de instalación en el equipo local a la ruta de acceso para que las herramientas estén disponibles para su invocación inmediatamente después de la instalación. 

El script del instalador se puede automatizar fácilmente al principio de la compilación para obtener e instalar la versión necesaria del SDK. La "versión necesaria" es cualquier versión necesaria de la aplicación que se está desarrollando. Puede elegir la ruta de acceso de instalación para instalar el SDK de forma local y, después, limpiar una vez finalizada la compilación. Esto ofrece encapsulación adicional y atomicidad al proceso de compilación. 

La referencia del script de instalación puede encontrarse en el documento [dotnet-install](dotnet-install-script.md). 

### <a name="dealing-with-the-dependencies"></a>Tratamiento de las dependencias
El uso del script del instalador significa que no se instalan automáticamente las dependencias nativas y que tiene que instalarlas si el sistema operativo en el que las va a instalar no las tiene. Puede ver la lista de requisitos previos en el [repositorio de CLI](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md). 

## <a name="ci-services-setup-examples"></a>Ejemplos de instalación de servicios de integración continua
Las siguientes secciones muestran ejemplos de configuraciones con las ofertas de SaaS de CI mencionadas. 

### <a name="travisci"></a>TravisCI

La opción [travis-ci](https://travis-ci.org/) se puede configurar para instalar el SDK de .NET Core mediante el lenguaje `csharp` y la clave `dotnet`.

Solo use:

```yaml
dotnet: 1.0.0-preview2-003121
```

Travis se puede ejecutar en un trabajo de `osx` (OS X 10.11) y de `linux` (Ubuntu 14.04) en una matriz de compilación, consulte [el ejemplo .travis.yml](https://github.com/dotnet/docs/blob/master/.travis.yml) para más información.

### <a name="appveyor"></a>AppVeyor

La opción [appveyor.com ci](https://www.appveyor.com/) ya tiene instalado el SDK .NET Core Preview 2 en la imagen de trabajo de compilación `Visual Studio 2015`.

Solo use:

```yaml
os: Visual Studio 2015
```

Es posible instalar una versión concreta del SDK de .NET Core, para ello, consulte [ejemplo de appveyor.yml](https://github.com/dotnet/docs/blob/master/appveyor.yml) para más información. 

En el ejemplo, se han descargado los archivos binarios del SDK de .NET Core, se han descomprimido en un subdirectorio y se han agregado a la variable de entorno `PATH`.

Se puede agregar una matriz de compilación para ejecutar las pruebas de integración con varias versiones del SDK de .NET Core.

```yaml
environment:
  matrix:
    - CLI_VERSION: 1.0.0-preview2-003121
    - CLI_VERSION: Latest

install:
  # .NET Core SDK binaries
  - ps: $url = "https://dotnetcli.blob.core.windows.net/dotnet/preview/Binaries/$($env:CLI_VERSION)/dotnet-dev-win-x64.$($env:CLI_VERSION.ToLower()).zip"
  # follow normal installation from binaries
```


<!--HONumber=Feb17_HO2-->


