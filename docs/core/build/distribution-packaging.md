---
title: Empaquetado de distribución de .NET Core
description: Obtenga información sobre cómo empaquetar, nombrar y versionar .NET Core para su distribución.
author: tmds
ms.date: 03/02/2018
ms.custom: seodec18
ms.openlocfilehash: 5d23147c8a38fbeea9e88c0a18e1f220e854fec1
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/28/2019
ms.locfileid: "70105412"
---
# <a name="net-core-distribution-packaging"></a>Empaquetado de distribución de .NET Core

Como .NET Core está disponible cada vez en más plataformas, resulta útil aprender cómo empaquetarlo, nombrarlo y versionarlo. De esta manera, los mantenedores de paquetes pueden ayudar a garantizar una experiencia coherente, independientemente de dónde los usuarios elijan ejecutar .NET. Este artículo resultará útil para los usuarios que:

- Intentan compilar .NET Core desde el origen.
- Desean realizar cambios en la CLI de .NET Core que pueden afectar a la distribución o a los paquetes generados resultantes.

## <a name="disk-layout"></a>Diseño de disco

Cuando se instala, .NET Core consta de varios componentes que están dispuestos tal y como se indica a continuación en el sistema de archivos:

```
.
├── dotnet                       (1)
├── LICENSE.txt                  (8)
├── ThirdPartyNotices.txt        (8)
├── host
│   └── fxr
│       └── <fxr version>        (2)
├── sdk
│   ├── <sdk version>            (3)
│   └── NuGetFallbackFolder      (4)
└── shared
    ├── Microsoft.NETCore.App
    │   └── <runtime version>    (5)
    └── Microsoft.AspNetCore.App
        └── <aspnetcore version> (6)
    └── Microsoft.AspNetCore.All
        └── <aspnetcore version> (7)
/
├─usr/share/man/man1
│       └── dotnet.1.gz          (9)
└─usr/bin
        └── dotnet               (10)
```

- (1) **dotnet**: el host (también conocido como "muxer") tiene dos roles diferentes: activar un entorno de ejecución para iniciar una aplicación y activar un SDK para enviarle comandos. El host es un ejecutable nativo (`dotnet.exe`).

Aunque hay un único host, la mayoría del resto de componentes está en directorios con versión (2,3,5,6). Esto significa que puede haber varias versiones en el sistema ya que se instalan en paralelo.

- (2) **host/fxr/\<versión de fxr>** : contiene la lógica de resolución del marco que usa el host. El host usa la versión más reciente de hostfxr que está instalada. Hostfxr es responsable de seleccionar el entorno de ejecución adecuado cuando se ejecuta una aplicación de .NET Core. Por ejemplo, una aplicación compilada para .NET Core 2.0.0 utiliza el runtime de 2.0.5 cuando esté disponible. De forma similar, hostfxr selecciona el SDK adecuado durante el desarrollo.

- (3) **sdk/\<versión sdk>** : el SDK (también conocido como "las herramientas") es un conjunto de herramientas administradas que se usan para escribir y compilar aplicaciones y bibliotecas de .NET Core. El SDK incluye la interfaz de línea de comandos (CLI) de .NET Core, los compiladores de lenguajes administrados, MSBuild y las tareas y los destinos de compilación asociados, NuGet, nuevas plantillas de proyecto, etcétera.

- (4) **sdk/NuGetFallbackFolder**: contiene una caché de paquetes NuGet que un SDK usa durante la operación de restauración, como cuando se ejecuta `dotnet restore` o `dotnet build /t:Restore`.

La carpeta **shared** contiene marcos. Un marco compartido proporciona un conjunto de bibliotecas en una ubicación central para que las puedan usar diferentes aplicaciones.

- (5) **shared/Microsoft.NETCore.App/\<versión del entorno de ejecución>** : este marco contiene el entorno de ejecución de .NET Core y compatibilidad con las bibliotecas administradas.

- (6,7) **shared/Microsoft.AspNetCore.{App,All}/\<versión de aspnetcore>** : contiene las bibliotecas de ASP.NET Core. Las bibliotecas de `Microsoft.AspNetCore.App` se desarrollan y se admiten como parte del proyecto de .NET Core. Las bibliotecas de `Microsoft.AspNetCore.All` son un superconjunto que también contiene bibliotecas de terceros.

- (8) **LICENSE.txt,ThirdPartyNotices.txt**: son las licencias .NET Core y de bibliotecas de terceros que se usan en .NET Core.

- (9,10) **dotnet.1.gz, dotnet**: `dotnet.1.gz` es la página manual de dotnet. `dotnet` es un vínculo simbólico al host(1) de dotnet. Estos archivos se instalan en ubicaciones bien conocidas para la integración del sistema.

## <a name="recommended-packages"></a>Paquetes recomendados

El control de versiones de .NET Core se basa en los números de versión `[major].[minor]` del componente del entorno de ejecución.
La versión del SDK usa el mismo valor `[major].[minor]` y tiene un valor `[patch]` independiente que combina la semántica de la característica y la revisión del SDK.
Por ejemplo:  la versión 2.2.302 del SDK es la segunda versión de revisión de la tercera versión de características del SDK que admite el runtime 2.2. Para obtener más información sobre el funcionamiento del control de versiones, vea [.NET Core versioning overview](../versions/index.md) (Introducción al control de versiones de .NET Core).

Algunos de los paquetes incluyen parte del número de versión en su nombre. Esto permite instalar una versión concreta.
No se incluye el resto de la versión en el nombre de la versión. Esto permite al administrador de paquetes del sistema operativo actualizar los paquetes (por ejemplo, instalar automáticamente correcciones de seguridad). Los administradores de paquetes compatibles son específicos de Linux.

En la tabla siguiente se muestran los paquetes recomendados:

| nombre                                    | Ejemplo                | Caso de uso: Instalar...           | Contiene           | Dependencias                                   | Versión            |
|-----------------------------------------|------------------------|---------------------------------|--------------------|------------------------------------------------|--------------------|
| dotnet-sdk-[versión principal]                      | dotnet-sdk-2           | SDK más reciente del entorno de ejecución principal    |                    | dotnet-sdk-[versión principal].[versión secundaria más reciente]               | \<versión del sdk>     |
| dotnet-sdk-[versión principal].[versión secundaria]              | dotnet-sdk-2.1         | SDK más reciente del entorno de ejecución concreto |                    | dotnet-sdk-[versión principal].[versión secundaria].[característica del SDK más reciente]xx | \<versión del SDK>     |
| dotnet-sdk-[versión principal].[versión secundaria].[característica del SDK]xx | dotnet-sdk-2.1.3xx     | Versión de características específica del SDK    | (3),(4)            | aspnetcore-runtime-[versión principal].[versión secundaria]             | \<versión del SDK>     |
| aspnetcore-runtime-[versión principal].[versión secundaria]      | aspnetcore-runtime-2.1 | Entorno de ejecución concreto de ASP.NET Core   | (6),[(7)]          | dotnet-runtime-[versión principal].[versión secundaria]                 | \<versión del entorno de ejecución> |
| dotnet-runtime-[versión principal].[versión secundaria]          | dotnet-runtime-2.1     | Entorno de ejecución concreto                | (5)                | host-fxr:\<versión del entorno de ejecución>+                   | \<versión del entorno de ejecución> |
| dotnet-host-fxr                         | dotnet-host-fxr        | _dependencia_                    | (2)                | host:\<versión del entorno de ejecución>+                       | \<versión del entorno de ejecución> |
| dotnet-host                             | dotnet-host            | _dependencia_                    | (1),(8),(9),(10)   |                                                | \<versión del entorno de ejecución> |

La mayoría de las distribuciones requieren que todos los artefactos se compilen desde el origen. Esto tiene algún impacto en los paquetes:

- Las bibliotecas de terceros de `shared/Microsoft.AspNetCore.All` no se pueden compilar fácilmente desde el origen. Por tanto, se omite esa carpeta en el paquete `aspnetcore-runtime`.

- La carpeta `NuGetFallbackFolder` se rellena con artefactos binarios desde `nuget.org`. Debe permanecer vacía.

Es posible que varios paquetes `dotnet-sdk` proporcionen los mismos archivos para la carpeta `NuGetFallbackFolder`. Para evitar problemas con el administrador de paquetes, estos archivos deben ser idénticos (suma de comprobación, fecha de modificación, etc.).

### <a name="preview-versions"></a>Versiones preliminares

Los mantenedores de paquetes pueden decidir proporcionar versiones preliminares del marco compartido y del SDK. Pueden proporcionarse versiones preliminares con los paquetes `dotnet-sdk-[major].[minor].[sdk feat]xx`, `aspnetcore-runtime-[major].[minor]` y `dotnet-runtime-[major].[minor]`. Para las versiones preliminares, la versión principal del paquete debe establecerse en cero. De esta manera, se instalará la versión final como una actualización del paquete.

### <a name="patch-packages"></a>Paquetes de revisión

Puesto que una versión de revisión de un paquete puede ocasionar un cambio importante, es posible que un mantenedor de paquetes quiera proporcionar _paquetes de revisión_. Estos paquetes permiten instalar una versión de revisión concreta que no se actualiza automáticamente. Solo use paquetes de revisión en circunstancias excepcionales ya que no están actualizados con correcciones (de seguridad).

En la tabla siguiente se muestran los paquetes recomendados y los **paquetes de revisión**:

| nombre                                           | Ejemplo                  | Contiene         | Dependencias                                              |
|------------------------------------------------|--------------------------|------------------|-----------------------------------------------------------|
| dotnet-sdk-[versión principal]                             | dotnet-sdk-2             |                  | dotnet-sdk-[versión principal].[versión secundaria más reciente del SDK]                     |
| dotnet-sdk-[versión principal].[versión secundaria]                     | dotnet-sdk-2.1           |                  | dotnet-sdk-[versión principal].[versión secundaria].[característica del SDK más reciente]xx            |
| dotnet-sdk-[versión principal].[versión secundaria].[característica del SDK]xx        | dotnet-sdk-2.1.3xx       |                  | dotnet-sdk-[versión principal].[versión secundaria].[revisión más reciente del SDK]             |
| **dotnet-sdk-[versión principal].[versión secundaria].[revisión]**         | dotnet-sdk-2.1.300       | (3),(4)          | aspnetcore-runtime-[versión principal].[versión secundaria].[revisión del entorno de ejecución del SDK]    |
| aspnetcore-runtime-[versión principal].[versión secundaria]             | aspnetcore-runtime-2.1   |                  | aspnetcore-runtime-[versión principal].[versión principal].[revisión más reciente del entorno de ejecución] |
| **aspnetcore-runtime-[versión principal].[versión secundaria].[revisión]** | aspnetcore-runtime-2.1.0 | (6),[(7)]        | dotnet-runtime-[versión principal].[versión secundaria].[revisión]                    |
| dotnet-runtime-[versión principal].[versión secundaria]                 | dotnet-runtime-2.1       |                  | dotnet-runtime-[versión principal].[versión secundaria].[revisión más reciente del entorno de ejecución]     |
| **dotnet-runtime-[versión principal].[versión secundaria].[revisión]**     | dotnet-runtime-2.1.0     | (5)              | host-fxr:\<versión del entorno de ejecución>+                              |
| dotnet-host-fxr                                | dotnet-host-fxr          | (2)              | host:\<versión del entorno de ejecución>+                                  |
| dotnet-host                                    | dotnet-host              | (1),(8),(9),(10) |                                                           |

Una alternativa al uso de paquetes de revisión es _anclar_ los paquetes a una versión concreta mediante el administrador de paquetes. Para evitar que afecte a otros usuarios o aplicaciones, estas aplicaciones pueden compilarse e implementarse en un contenedor.

## <a name="building-packages"></a>Compilar paquetes

El repositorio [dotnet/source-build](https://github.com/dotnet/source-build) proporciona instrucciones sobre cómo crear un paquete tarball de origen del SDK de .NET Core y todos sus componentes. La salida del repositorio de compilación de código fuente coincide con el diseño que se describe en la primera sección de este artículo.
