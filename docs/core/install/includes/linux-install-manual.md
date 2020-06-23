---
ms.openlocfilehash: e7d35045892c62f759aad5067962ac5c15a9fb8b
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602703"
---

Tanto el SDK de .NET Core como .NET Core Runtime se pueden instalar manualmente una vez que se han descargado. Si instala el SDK de .NET Core, no necesita instalar el entorno de ejecución correspondiente. En primer lugar, descargue una versión binaria del SDK o del entorno de ejecución de uno de los siguientes sitios:

- ✔️ [Descargas de la versión preliminar de .NET 5.0](https://dotnet.microsoft.com/download/dotnet/5.0)
- ✔️ [Descargas de .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- ❌ [Descargas de .NET Core 3.0](https://dotnet.microsoft.com/download/dotnet-core/3.0)
- ❌ [Descargas de .NET Core 2.2](https://dotnet.microsoft.com/download/dotnet-core/2.2)
- ✔️ [Descargas de .NET Core 2.1](https://dotnet.microsoft.com/download/dotnet-core/2.1)

A continuación, extraiga el archivo descargado y use el comando `export` para establecer las variables que se utilizan en .NET Core. Luego, asegúrese de que .NET Core esté en PATH.

Para extraer el entorno de ejecución y hacer que los comandos de la CLI de .NET Core estén disponibles en el terminal, en primer lugar, descargue una versión binaria de .NET Core. Luego, abra un terminal y ejecute los siguientes comandos desde el directorio donde se guardó el archivo.

```bash
mkdir -p "$HOME/dotnet" && tar zxf aspnetcore-runtime-3.1.0-linux-x64.tar.gz -C "$HOME/dotnet"
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

> [!TIP]
> Los comandos `export` anteriores solo hacen que los comandos de la CLI de .NET Core estén disponibles para la sesión de terminal en la que se ha ejecutado.
>
> Puede editar el perfil del shell para agregar los comandos de forma permanente. Hay una serie de shells distintos disponibles para Linux, y cada uno de ellos tiene un perfil diferente. Por ejemplo:
>
> - **Shell de Bash**: *~/.bash_profile*, *~/.bashrc*
> - **Shell de Korn**: *~/.kshrc* or *.profile*
> - **Shell de Z**: *~/.zshrc* or *.zprofile*
>
> Edite el archivo de origen adecuado para el shell y agregue `:$HOME/dotnet` al final de la instrucción `PATH` existente. Si no se incluye ninguna instrucción `PATH`, agregue una nueva línea con `export PATH=$PATH:$HOME/dotnet`.
>
> Además, agregue `export DOTNET_ROOT=$HOME/dotnet` al final del archivo.

Este enfoque le permite instalar diferentes versiones en ubicaciones independientes y elegir explícitamente cuál usará cada aplicación.
