---
title: Compilación de .NET Core a partir del código fuente
description: Obtenga información sobre cómo compilar .NET Core y la CLI de .NET Core a partir del código fuente.
author: bleroy
ms.date: 06/28/2017
ms.openlocfilehash: fe5431667d861d830c2ec56252e6e3e2ca08a866
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740918"
---
# <a name="build-net-core-from-source"></a>Compilación de .NET Core a partir del código fuente

La capacidad de compilar .NET Core a partir de su código fuente es importante en varios sentidos: facilita la portabilidad de .NET Core a nuevas plataformas, permite contribuciones y correcciones del producto y permite crear versiones personalizadas de .NET.
En este artículo, se proporcionan instrucciones para los desarrolladores que quieren compilar y distribuir sus propias versiones de .NET Core.

## <a name="build-the-clr-from-source"></a>Compilación de CLR a partir del código fuente

El código fuente de CLR de .NET Core puede encontrarse en el repositorio [dotnet/runtime](https://github.com/dotnet/runtime/) en GitHub.

Actualmente, la compilación depende de los siguientes requisitos previos:

- [Git](https://git-scm.com/)
- [CMake](https://cmake.org/)
- [Python](https://www.python.org/)
- un compilador de C++.

Para compilar CLR después de instalar estos requisitos previos, invoque el script de compilación (`build.cmd` en Windows, o `build.sh` en Linux y macOS) en la base del repositorio [dotnet/runtime](https://github.com/dotnet/runtime/).

La instalación de los componentes varía según el sistema operativo (SO). Consulte las instrucciones de compilación de su sistema operativo específico:

- [Windows](https://github.com/dotnet/coreclr/blob/master/Documentation/building/windows-instructions.md)
- [Linux](https://github.com/dotnet/coreclr/blob/master/Documentation/building/linux-instructions.md)
- [macOS](https://github.com/dotnet/coreclr/blob/master/Documentation/building/osx-instructions.md)
- [FreeBSD](https://github.com/dotnet/coreclr/blob/master/Documentation/building/freebsd-instructions.md)
- [NetBSD](https://github.com/dotnet/coreclr/blob/master/Documentation/building/netbsd-instructions.md)

No hay ninguna compilación cruzada entre sistemas operativos (solo para ARM, que se basa en X64).  
Debe estar en la plataforma concreta para compilar esa plataforma.  

La compilación tiene dos `buildTypes` principales:

- Debug (valor predeterminado): compila el tiempo de ejecución con las optimizaciones mínimas y las comprobaciones (aserciones) en tiempo de ejecución adicionales. Aunque esta reducción en el nivel de optimización y las comprobaciones adicionales ralentizan la ejecución en tiempo de ejecución, resultan útiles para realizar la depuración. Este es el valor recomendado para los entornos de desarrollo y pruebas.
- Release: compila el tiempo de ejecución con las optimizaciones completas y sin las comprobaciones en tiempo de ejecución adicionales. Aunque el rendimiento en tiempo de ejecución será mucho más rápido, puede tardar un poco más en compilarse y puede resultar complicado realizar la depuración. Pase `release` al script de compilación para seleccionar este tipo de compilación.

Además, de forma predeterminada, la compilación no solo crea los archivos ejecutables en tiempo de ejecución, sino que también compila todas las pruebas.
Hay bastantes pruebas, lo que exige una cantidad considerable de tiempo que no es necesario si tan solo se quiere experimentar con los cambios.
Para omitir las compilaciones de pruebas, agregue el argumento `skiptests` al script de compilación, como en el ejemplo siguiente (reemplace `.\build` con `./build.sh` en los equipos Unix):

```bat
    .\build skiptests
```

En el ejemplo anterior, se ha mostrado cómo compilar el tipo `Debug`, que tiene las comprobaciones (aserciones) en tiempo de desarrollo habilitadas y las optimizaciones deshabilitadas. Para compilar el tipo de versión (velocidad máxima), haga lo siguiente:

```bat
    .\build release skiptests
```

Puede encontrar más opciones de compilación con build si usa el calificador -? o -help.

### <a name="using-your-build"></a>Usar la compilación

La compilación coloca todos los archivos generados en el directorio `bin` en la base del repositorio.
Hay un directorio *bin\Log* que contiene archivos de registro generados durante la compilación (más útil cuando se produce un error en la compilación).
La salida real se coloca en un directorio *bin\Producto\[plataforma].[arquitectura de CPU].[tipo de compilación]* , como *bin\Producto\Windows_NT.x64.Release*.

Aunque el resultado de la compilación "sin procesar" a veces resulta útil, normalmente solo interesan los paquetes de NuGet, que se colocan en el subdirectorio `.nuget\pkg` del directorio de salida anterior.

Hay dos técnicas básicas para usar el nuevo tiempo de ejecución:

 1. **Use dotnet.exe y NuGet para crear una aplicación**.
    Vea [Usar la compilación](https://github.com/dotnet/runtime/blob/master/docs/workflow/testing/using-your-build.md) para obtener instrucciones sobre cómo crear un programa que use el nuevo tiempo de ejecución mediante paquetes de NuGet que acaba de crear y la interfaz de la línea de comandos (CLI) de "dotnet". Esta técnica es la forma probable en que los desarrolladores que no usan el tiempo de ejecución van a consumir el nuevo tiempo de ejecución.

 2. **Use corerun.exe para ejecutar una aplicación con archivos DLL sin empaquetar**.
    Este repositorio también define un host simple denominado corerun.exe que NO tiene ninguna dependencia en NuGet.
    Debe indicar al host de dónde obtiene los archivos DLL necesarios que usa y tiene que recopilarlos manualmente.
    Esta técnica se usa en todas las pruebas del repositorio [dotnet/runtime](https://github.com/dotnet/runtime), y es útil para el bucle local rápido "editar-compilar-depurar", como en el caso de las pruebas unitarias preliminares.
    Vea [Executing .NET Core Apps with CoreRun.exe](https://github.com/dotnet/runtime/blob/master/docs/workflow/testing/using-corerun.md) (Ejecutar aplicaciones de .NET Core con CoreRun.exe) para obtener más información sobre el uso de esta técnica.

## <a name="build-the-cli-from-source"></a>Compilar la CLI a partir del código fuente

El código fuente de la CLI de .NET Core puede encontrarse en el repositorio [dotnet/cli](https://github.com/dotnet/cli/) en GitHub.

Para compilar la CLI de .NET Core, necesita tener lo siguiente instalado en su equipo.

- Windows y Linux:
  - GIT en la ruta de acceso
- macOS:
  - GIT en la ruta de acceso
  - Xcode
  - OpenSSL

Para compilar, ejecute `build.cmd` en Windows, o `build.sh` en Linux y macOS desde la raíz. Si no quiere ejecutar pruebas, ejecute `build.cmd -t:Compile` o `./build.sh -t:Compile`. Para compilar la CLI en macOS Sierra, debe ejecutar `export DOTNET_RUNTIME_ID=osx.10.11-x64` para establecer la variable de entorno DOTNET_RUNTIME_ID.

### <a name="using-your-build"></a>Usar la compilación

Use el ejecutable `dotnet` de *artifacts/{os}-{arch}/stage2* para probar la CLI que acaba de crear. Si quiere usar la salida de compilación al invocar a `dotnet` desde la consola actual, también puede agregar *artifacts/{os}-{arch}/stage2* a la ruta de acceso.

## <a name="see-also"></a>Vea también

- [Entorno de ejecución .NET](https://github.com/dotnet/runtime/blob/master/README.md)
- [.NET Core CLI Developer Guide](https://github.com/dotnet/cli/blob/master/Documentation/project-docs/developer-guide.md) (Guía para desarrolladores de la CLI de .NET Core)
- [Empaquetado de distribución de .NET Core](./distribution-packaging.md)
