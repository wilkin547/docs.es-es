---
title: Empaquetado de distribución de .NET Core
description: Obtenga información sobre cómo empaquetar, nombrar y versionar .NET Core para su distribución.
author: tmds
ms.date: 10/09/2019
ms.openlocfilehash: 3324a6a151fc6dc46a8f13ea17c89da99d108d82
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/11/2020
ms.locfileid: "88062891"
---
# <a name="net-core-distribution-packaging"></a>Empaquetado de distribución de .NET Core

Como .NET Core está disponible cada vez en más plataformas, resulta útil aprender cómo empaquetarlo, nombrarlo y versionarlo. De esta manera, los mantenedores de paquetes pueden ayudar a garantizar una experiencia coherente, independientemente de dónde los usuarios elijan ejecutar .NET. Este artículo resultará útil para los usuarios que:

- Intentan compilar .NET Core desde el origen.
- Desean realizar cambios en la CLI de .NET Core que pueden afectar a la distribución o a los paquetes generados resultantes.

## <a name="disk-layout"></a>Diseño de disco

Cuando se instala, .NET Core consta de varios componentes que están dispuestos tal y como se indica a continuación en el sistema de archivos:

```
{dotnet_root}                                     (*)
├── dotnet                       (1)
├── LICENSE.txt                  (8)
├── ThirdPartyNotices.txt        (8)
├── host                                          (*)
│   └── fxr                                       (*)
│       └── <fxr version>        (2)
├── sdk                                           (*)
│   ├── <sdk version>            (3)
│   └── NuGetFallbackFolder      (4)              (*)
├── packs                                         (*)
│   ├── Microsoft.AspNetCore.App.Ref              (*)
│   │   └── <aspnetcore ref version>     (11)
│   ├── Microsoft.NETCore.App.Ref                 (*)
│   │   └── <netcore ref version>        (12)
│   ├── Microsoft.NETCore.App.Host.<rid>          (*)
│   │   └── <apphost version>            (13)
│   ├── Microsoft.WindowsDesktop.App.Ref          (*)
│   │   └── <desktop ref version>        (14)
│   └── NETStandard.Library.Ref                   (*)
│       └── <netstandard version>        (15)
├── shared                                        (*)
│   ├── Microsoft.NETCore.App                     (*)
│   │   └── <runtime version>     (5)
│   ├── Microsoft.AspNetCore.App                  (*)
│   │   └── <aspnetcore version>  (6)
│   ├── Microsoft.AspNetCore.All                  (*)
│   │   └── <aspnetcore version>  (6)
│   └── Microsoft.WindowsDesktop.App              (*)
│       └── <desktop app version> (7)
└── templates                                     (*)
│   └── <templates version>      (17)
/
├── etc/dotnet
│       └── install_location     (16)
├── usr/share/man/man1
│       └── dotnet.1.gz          (9)
└── usr/bin
        └── dotnet               (10)
```

- (1) **dotnet**: el host (también conocido como "muxer") tiene dos roles diferentes: activar un entorno de ejecución para iniciar una aplicación y activar un SDK para enviarle comandos. El host es un ejecutable nativo (`dotnet.exe`).

Aunque hay un único host, la mayoría del resto de componentes está en directorios con versión (2,3,5,6). Esto significa que puede haber varias versiones en el sistema ya que se instalan en paralelo.

- (2) **host/fxr/\<fxr version>** contiene la lógica de resolución del marco que usa el host. El host usa la versión más reciente de hostfxr que está instalada. Hostfxr es responsable de seleccionar el entorno de ejecución adecuado cuando se ejecuta una aplicación de .NET Core. Por ejemplo, una aplicación compilada para .NET Core 2.0.0 utiliza el runtime de 2.0.5 cuando esté disponible. De forma similar, hostfxr selecciona el SDK adecuado durante el desarrollo.

- (3) **sdk/\<sdk version>** El SDK (también conocido como "las herramientas") es un conjunto de herramientas administradas que se usa para escribir y compilar aplicaciones y bibliotecas de .NET Core. El SDK incluye la CLI de .NET Core, los compiladores de lenguajes administrados, MSBuild y las tareas y los destinos de compilación asociados, NuGet, nuevas plantillas de proyecto, etc.

- (4) **sdk/NuGetFallbackFolder**: contiene una caché de paquetes NuGet que un SDK usa durante la operación de restauración, como cuando se ejecuta `dotnet restore` o `dotnet build`. Esta carpeta solo se usa antes de .NET Core 3.0. No se puede compilar desde el origen, porque contiene recursos binarios compilados previamente desde `nuget.org`.

La carpeta **shared** contiene marcos. Un marco compartido proporciona un conjunto de bibliotecas en una ubicación central para que las puedan usar diferentes aplicaciones.

- (5) **shared/Microsoft.NETCore.App/\<runtime version>** Este marco contiene el entorno de ejecución de .NET Core y compatibilidad con las bibliotecas administradas.

- (6) **shared/Microsoft.AspNetCore.{App,All}/\<aspnetcore version>** contiene las bibliotecas de ASP.NET Core. Las bibliotecas de `Microsoft.AspNetCore.App` se desarrollan y se admiten como parte del proyecto de .NET Core. Las bibliotecas de `Microsoft.AspNetCore.All` son un superconjunto que también contiene bibliotecas de terceros.

- (7) **shared/Microsoft.Desktop.App/\<desktop app version>** contiene las bibliotecas de escritorio de Windows. Esto no se incluye en plataformas que no son de Windows.

- (8) **LICENSE.txt,ThirdPartyNotices.txt**: son las licencias .NET Core y de bibliotecas de terceros que se usan en .NET Core.

- (9,10) **dotnet.1.gz, dotnet**: `dotnet.1.gz` es la página manual de dotnet. `dotnet` es un vínculo simbólico al host(1) de dotnet. Estos archivos se instalan en ubicaciones bien conocidas para la integración del sistema.

- (11,12) **Microsoft.NETCore.App.Ref,Microsoft.AspNetCore.App.Ref**: describe la API de una versión `x.y` de .NET Core y de ASP.NET Core respectivamente. Estos paquetes se utilizan al compilar para esas versiones de destino.

- (13) **Microsoft.NETCore.App.Host.\<rid>** contiene un binario nativo para la plataforma `rid`. Este binario es una plantilla cuando se compila una aplicación de .NET Core en un archivo binario nativo para esa plataforma.

- (14) **Microsoft.WindowsDesktop.App.Ref**: describe la API de la versión `x.y` de las aplicaciones de escritorio de Windows. Estos archivos se usan al compilar para ese destino. Esto no se proporciona en plataformas que no son de Windows.

- (15) **NETStandard.Library.Ref**: describe la API `x.y` de netstandard. Estos archivos se usan al compilar para ese destino.

- (16) **/etc/dotnet/install_location**: es un archivo que contiene la ruta de acceso completa a `{dotnet_root}`. La ruta de acceso puede terminar con una nueva línea. No es necesario agregar este archivo cuando la raíz es `/usr/share/dotnet`.

- (17) **templates**: contiene las plantillas que usa el SDK. Por ejemplo, `dotnet new` busca plantillas de proyecto aquí.

Varios paquetes usan las carpetas marcadas con `(*)`. Algunos formatos de paquete (por ejemplo, `rpm`) requieren un tratamiento especial de esas carpetas. El mantenedor de paquetes debe encargarse de esto.

## <a name="recommended-packages"></a>Paquetes recomendados

El control de versiones de .NET Core se basa en los números de versión `[major].[minor]` del componente del entorno de ejecución.
La versión del SDK usa el mismo valor `[major].[minor]` y tiene un valor `[patch]` independiente que combina la semántica de la característica y la revisión del SDK.
Por ejemplo: la versión 2.2.302 del SDK es la segunda versión de revisión de la tercera versión de características del SDK que admite el runtime 2.2. Para obtener más información sobre el funcionamiento del control de versiones, vea [Introducción a la creación de versiones de .NET Core](./versions/index.md).

Algunos de los paquetes incluyen parte del número de versión en su nombre. Esto permite instalar una versión concreta.
No se incluye el resto de la versión en el nombre de la versión. Esto permite al administrador de paquetes del sistema operativo actualizar los paquetes (por ejemplo, instalar automáticamente correcciones de seguridad). Los administradores de paquetes compatibles son específicos de Linux.

A continuación se enumeran los paquetes recomendados:

- `dotnet-sdk-[major].[minor]`: instala el SDK más reciente del runtime concreto.
  - **Versión:** \<sdk version>
  - **Ejemplo:** dotnet-sdk-2.1
  - **Contiene:** (3),(4)
  - **Dependencias:** `dotnet-runtime-[major].[minor]`, `aspnetcore-runtime-[major].[minor]`, `dotnet-targeting-pack-[major].[minor]`, `aspnetcore-targeting-pack-[major].[minor]`, `netstandard-targeting-pack-[netstandard_major].[netstandard_minor]`, `dotnet-apphost-pack-[major].[minor]` y `dotnet-templates-[major].[minor]`

- `aspnetcore-runtime-[major].[minor]`: instala un runtime concreto de ASP.NET Core.
  - **Versión:** \<aspnetcore runtime version>
  - **Ejemplo:** aspnetcore-runtime-2.1
  - **Contiene:** (6)
  - **Dependencias:** `dotnet-runtime-[major].[minor]`

- `dotnet-runtime-deps-[major].[minor]` _(Opcional)_ : instala las dependencias para ejecutar aplicaciones independientes.
  - **Version:** \<runtime version>
  - **Ejemplo:** dotnet-runtime-deps-2.1
  - **Dependencias:** _dependencias específicas de la distribución_

- `dotnet-runtime-[major].[minor]`: instala un runtime concreto.
  - **Versión:** \<runtime version>
  - **Ejemplo:** dotnet-runtime-2.1
  - **Contiene:** (5)
  - **Dependencias:** `dotnet-hostfxr-[major].[minor]` y `dotnet-runtime-deps-[major].[minor]`

- `dotnet-hostfxr-[major].[minor]`: dependencia.
  - **Versión:** \<runtime version>
  - **Ejemplo:** dotnet-hostfxr-3.0
  - **Contiene:** (2)
  - **Dependencias:** `dotnet-host`

- `dotnet-host`: dependencia.
  - **Versión:** \<runtime version>
  - **Ejemplo:** dotnet-host
  - **Contiene:** (1), (8), (9), (10), (16)

- `dotnet-apphost-pack-[major].[minor]`: dependencia.
  - **Versión:** \<runtime version>
  - **Contiene:** (13)

- `dotnet-targeting-pack-[major].[minor]`: permite establecer como destino un runtime que no sea el más reciente.
  - **Versión:** \<runtime version>
  - **Contiene:** (12)

- `aspnetcore-targeting-pack-[major].[minor]`: permite establecer como destino un runtime que no sea el más reciente.
  - **Versión:** \<aspnetcore runtime version>
  - **Contiene:** (11)

- `netstandard-targeting-pack-[netstandard_major].[netstandard_minor]`: permite establecer como destino una versión de netstandard.
  - **Versión:** \<sdk version>
  - **Contiene:** (15)

- `dotnet-templates-[major].[minor]`
  - **Versión:** \<sdk version>
  - **Contiene:** (15)

`dotnet-runtime-deps-[major].[minor]` requiere el conocimiento de las _dependencias concretas de distribución_. Dado que el sistema de compilación de distribución puede derivar esto de forma automática, el paquete es opcional, en cuyo caso estas dependencias se agregan directamente al paquete `dotnet-runtime-[major].[minor]`.

Cuando el contenido del paquete se encuentra en una carpeta con versión, el nombre del paquete `[major].[minor]` coincide con el nombre de la carpeta con versión. En todos los paquetes, excepto en `netstandard-targeting-pack-[netstandard_major].[netstandard_minor]`, esto también coincide con la versión de .NET Core.

Las dependencias entre paquetes deben usar un requisito de versión _igual o mayor que_. Por ejemplo, `dotnet-sdk-2.2:2.2.401` requiere `aspnetcore-runtime-2.2 >= 2.2.6`. Esto hace posible que el usuario actualice su instalación mediante un paquete raíz (por ejemplo, `dnf update dotnet-sdk-2.2`).

La mayoría de las distribuciones requieren que todos los artefactos se compilen desde el origen. Esto tiene algún impacto en los paquetes:

- Las bibliotecas de terceros de `shared/Microsoft.AspNetCore.All` no se pueden compilar fácilmente desde el origen. Por tanto, se omite esa carpeta en el paquete `aspnetcore-runtime`.

- La carpeta `NuGetFallbackFolder` se rellena con artefactos binarios desde `nuget.org`. Debe permanecer vacía.

Es posible que varios paquetes `dotnet-sdk` proporcionen los mismos archivos para la carpeta `NuGetFallbackFolder`. Para evitar problemas con el administrador de paquetes, estos archivos deben ser idénticos (suma de comprobación, fecha de modificación, etc.).

## <a name="building-packages"></a>Compilar paquetes

El repositorio [dotnet/source-build](https://github.com/dotnet/source-build) proporciona instrucciones sobre cómo crear un paquete tarball de origen del SDK de .NET Core y todos sus componentes. La salida del repositorio de compilación de código fuente coincide con el diseño que se describe en la primera sección de este artículo.
