---
title: "Catálogo de identificadores de entorno de ejecución (RID) de .NET Core"
description: "Obtenga información sobre el identificador en tiempo de ejecución (RID) y sobre cómo se usan los RID en .NET Core."
keywords: .NET, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 08/22/2016
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: b2032f5d-771f-48d9-917c-587d9509035c
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 3490fb639efd223dc36190324bdf3a06bc23c10e
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---

# <a name="net-core-runtime-identifier-rid-catalog"></a>Catálogo de identificadores de entorno de ejecución (RID) de .NET Core

## <a name="what-are-rids"></a>¿Qué son los RID?
RID es la abreviatura de *identificador de entorno de ejecución*. Los RID se usan para identificar los sistemas operativos de destino donde se ejecutará una aplicación o un recurso (es decir, un ensamblado). Tienen el siguiente aspecto: "ubuntu.14.04-x64", "win7-x64", "osx.10.11-x64". En el caso de los paquetes con dependencias nativas, designará las plataformas en las que se puede restaurar el paquete. 

Es importante tener en cuenta que los RID son, en realidad, cadenas opacas. Esto significa que deben coincidir de manera exacta para que las operaciones las usen en algún trabajo. Como ejemplo, consideremos el caso de [Elementary OS](https://elementary.io/), un clon sencillo de Ubuntu 14.04. A pesar de que .NET Core y la CLI funcionan sobre esa versión de Ubuntu, si intenta usarlas en Elementary OS sin ninguna modificación, se producirá un error en la operación de restauración de cualquier paquete. Esto sucede porque actualmente no tenemos un RID que designe a Elementary OS como plataforma. 

Los RID que representan sistemas operativos concretos normalmente siguen este patrón: `[os].[version]-[arch]`, donde:
- `[os]` es el moniker del sistema operativo, por ejemplo `ubuntu`.
- `[version]` es la versión del sistema operativo con formato de número de versión separada por punto (`.`), por ejemplo `15.10`; es lo suficientemente preciso para habilitar de manera razonable los recursos a fin de que usen como destino las API de plataforma de sistema operativo que representa esa versión.
  - **No** se deben tratar como versiones de marketing, debido a que, a menudo, representan varias versiones discretas del sistema operativo con un área expuesta de API de plataforma diferente.
- `[arch]` es la arquitectura del procesador, por ejemplo, `x86`, `x64`, `arm`, `arm64`, etc.

El gráfico de los RID está definido en un paquete llamado `Microsoft.NETCore.Platforms` en un archivo llamado `runtime.json`, que puede ver en el [repositorio de CoreFX](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json). Si usa este archivo, verá que algunos de los RID tienen una instrucción `"#import"`. Se trata de instrucciones de compatibilidad. Esto significa que un RID que tiene importado un RID puede ser un destino para la restauración de los paquetes de ese RID. Probablemente sea un poco confuso, pero mejor veamos un ejemplo. Echemos un vistazo a macOS:

```json
"osx.10.11-x64": {
    "#import": [ "osx.10.11", "osx.10.10-x64" ]
}
```
El RID anterior especifica que `osx.10.11-x64` importa `osx.10.10-x64`. Esto significa que, cuando se restauran los paquetes, NuGet podrá restaurar los paquetes que especifiquen que necesitan `osx.10.10-x64` en `osx.10.11-x64`.

El ejemplo de un gráfico de RID levemente más grande:  

- `win10-arm`
  - `win10`
  - `win81-arm`
    - `win81`
    - `win8-arm`
      - `win8`
        - `win7`
          - `win`
            - `any`

A la larga, todos los RID se asignarán de vuelta al RID `any` raíz.

A pesar de que se ven muy fáciles de usar, hay algunos aspectos especiales de los RID que debe considerar cuando trabaja con ellos:

* Son **cadenas opacas** y se deben tratar como cajas negras.
    * No debe construir los RID mediante programación.
* Debe usar los RID que ya están definidos para la plataforma y este documento así lo muestra.
* Los RID deben ser específicos para que no supongan nada más allá del valor real del RID. Consulte este documento para determinar los RID que necesita para una plataforma determinada.

## <a name="using-rids"></a>Uso de los RID
Para usar los RID, debe saber con qué RID cuenta. Se agregan RID nuevos a la plataforma de manera habitual. Para obtener la versión más reciente, revise el archivo [runtime.json](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json) que se encuentra en el repositorio CoreFX.

> [!NOTE]
> Estamos trabajando para que esta información se convierta en un formato más interactivo. Cuando eso suceda, se actualizará esta página para que tenga como destino la herramienta o su documentación de uso. 

## <a name="windows-rids"></a>RID de Windows

* Windows 7/Windows Server 2008 R2
    * `win7-x64`
    * `win7-x86`
* Windows 8/Windows Server 2012
    * `win8-x64`
    * `win8-x86`
    * `win8-arm`
* Windows 8.1/Windows Server 2012 R2
    * `win81-x64`
    * `win81-x86`
    * `win81-arm`
* Windows 10/Windows Server 2016
    * `win10-x64`
    * `win10-x86`
    * `win10-arm`
    * `win10-arm64`

## <a name="linux-rids"></a>RID de Linux

* Red Hat Enterprise Linux
    * `rhel.7-x64`
* Ubuntu
    * `ubuntu.14.04-x64`
    * `ubuntu.14.10-x64`
    * `ubuntu.15.04-x64`
    * `ubuntu.15.10-x64`
    * `ubuntu.16.04-x64`
    * `ubuntu.16.10-x64`
* CentOS
    * `centos.7-x64`
* Debian
    * `debian.8-x64`
* Fedora
    * `fedora.23-x64`
    * `fedora.24-x64`
* OpenSUSE
    * `opensuse.13.2-x64`
    * `opensuse.42.1-x64`
* Oracle Linux
    * `ol.7-x64`
    * `ol.7.0-x64`
    * `ol.7.1-x64`
    * `ol.7.2-x64`
* Derivadas de Ubuntu admitidas actualmente 
    * `linuxmint.17-x64`
    * `linuxmint.17.1-x64`
    * `linuxmint.17.2-x64`
    * `linuxmint.17.3-x64`
    * `linuxmint.18-x64`

## <a name="os-x-rids"></a>RID de OS X

* `osx.10.10-x64`
* `osx.10.11-x64`
* `osx.10.12-x64`

