---
title: Comando dotnet add package
description: El comando “dotnet add package” constituye una opción práctica para agregar la referencia de un paquete de NuGet a un proyecto.
ms.date: 04/24/2019
ms.openlocfilehash: 82f178026b46eb0237243b8ae49d17fbcc1af6ec
ms.sourcegitcommit: ffd7dd79468a81bbb0d6449f6d65513e050c04c4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2019
ms.locfileid: "65959240"
---
# <a name="dotnet-add-package"></a>dotnet add package

**Este artículo se aplica a: ✓** SDK de .NET Core 1.x y versiones posteriores

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a>nombre

`dotnet add package`: agrega una referencia de paquete a un archivo del proyecto.

## <a name="synopsis"></a>Sinopsis

`dotnet add [<PROJECT>] package <PACKAGE_NAME> [-h|--help] [-f|--framework] [--interactive] [-n|--no-restore] [--package-directory] [-s|--source] [-v|--version]`

## <a name="description"></a>Descripción

El comando `dotnet add package` constituye una opción práctica para agregar una referencia de paquete a un archivo del proyecto. Después de ejecutar el comando, existe una comprobación de compatibilidad para garantizar que el paquete es compatible con los marcos del proyecto. Si se pasa la comprobación, un elemento `<PackageReference>` se agrega al archivo del proyecto y [dotnet restore](dotnet-restore.md) se ejecuta.

[!INCLUDE[DotNet Restore Note](../../../includes/dotnet-restore-note.md)]

Por ejemplo, si agrega `Newtonsoft.Json` a *ToDo.csproj* se producirá un resultado similar al del siguiente ejemplo:

```console
  Writing C:\Users\mairaw\AppData\Local\Temp\tmp95A8.tmp
info : Adding PackageReference for package 'Newtonsoft.Json' into project 'C:\projects\ToDo\ToDo.csproj'.
log  : Restoring packages for C:\Temp\projects\consoleproj\consoleproj.csproj...
info :   GET https://api.nuget.org/v3-flatcontainer/newtonsoft.json/index.json
info :   OK https://api.nuget.org/v3-flatcontainer/newtonsoft.json/index.json 79ms
info :   GET https://api.nuget.org/v3-flatcontainer/newtonsoft.json/12.0.1/newtonsoft.json.12.0.1.nupkg
info :   OK https://api.nuget.org/v3-flatcontainer/newtonsoft.json/12.0.1/newtonsoft.json.12.0.1.nupkg 232ms
log  : Installing Newtonsoft.Json 12.0.1.
info : Package 'Newtonsoft.Json' is compatible with all the specified frameworks in project 'C:\projects\ToDo\ToDo.csproj'.
info : PackageReference for package 'Newtonsoft.Json' version '12.0.1' added to file 'C:\projects\ToDo\ToDo.csproj'.
```

El archivo *ToDo.csproj* contiene ahora un elemento [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files) para el paquete al que hace referencia.

```xml
<PackageReference Include="Newtonsoft.Json" Version="12.0.1" />
```

## <a name="arguments"></a>Argumentos

* **`PROJECT`**

  Especifica el archivo del proyecto. Si no se especifica, el comando busca uno en el directorio actual.

* **`PACKAGE_NAME`**

  La referencia de paquete que se va a agregar.

## <a name="options"></a>Opciones

* **`-f|--framework <FRAMEWORK>`**

  Agrega una referencia de paquete solo cuando se destina a un [marco](../../standard/frameworks.md) específico.

* **`-h|--help`**

  Imprime una corta ayuda para el comando.

* **`--interactive`**

  Permite que el comando se detenga y espere la entrada o acción del usuario (por ejemplo, completar la autenticación). Disponible desde el SDK de .NET Core 2.1, versión 2.1.400 o posterior.

* **`-n|--no-restore`**

  Agrega una referencia de paquete sin realizar una vista previa de restauración y una comprobación de compatibilidad.

* **`--package-directory <PACKAGE_DIRECTORY>`**

  Directorio donde quiere restaurar los paquetes.

* **`-s|--source <SOURCE>`**

  Origen del paquete NuGet que se usará durante la operación de restauración.

* **`-v|--version <VERSION>`**

  Versión del paquete. Consulte [NuGet package versioning](https://docs.microsoft.com/nuget/reference/package-versioning) (Control de versiones de paquetes NuGet).

## <a name="examples"></a>Ejemplos

* Agregar un paquete de NuGet `Newtonsoft.Json` a un proyecto:

  ```console
  dotnet add package Newtonsoft.Json
  ```

* Agregar una versión específica de un paquete a un proyecto:

  ```console
  dotnet add ToDo.csproj package Microsoft.Azure.DocumentDB.Core -v 1.0.0
  ```

* Agregar un paquete con un origen de NuGet específico:

  ```console
  dotnet add package Microsoft.AspNetCore.StaticFiles -s https://dotnet.myget.org/F/dotnet-core/api/v3/index.json
  ```
