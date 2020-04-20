---
title: Comando dotnet add package
description: El comando “dotnet add package” constituye una opción práctica para agregar la referencia de un paquete de NuGet a un proyecto.
ms.date: 02/14/2020
ms.openlocfilehash: 24a25cdab2aab30d52f8407adfda437f47437290
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463752"
---
# <a name="dotnet-add-package"></a>dotnet add package

**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.x y versiones posteriores

## <a name="name"></a>Name

`dotnet add package`: agrega una referencia de paquete a un archivo del proyecto.

## <a name="synopsis"></a>Sinopsis

```dotnetcli
dotnet add [<PROJECT>] package <PACKAGE_NAME>
    [-f|--framework <FRAMEWORK>] [--interactive]
    [-n|--no-restore] [--package-directory <PACKAGE_DIRECTORY>]
    [-s|--source <SOURCE>] [-v|--version <VERSION>]

dotnet add package -h|--help
```

## <a name="description"></a>Description

El comando `dotnet add package` constituye una opción práctica para agregar una referencia de paquete a un archivo del proyecto. Después de ejecutar el comando, existe una comprobación de compatibilidad para garantizar que el paquete es compatible con los marcos del proyecto. Si se pasa la comprobación, un elemento `<PackageReference>` se agrega al archivo del proyecto y [dotnet restore](dotnet-restore.md) se ejecuta.

[!INCLUDE[DotNet Restore Note](../../../includes/dotnet-restore-note.md)]

Por ejemplo, si agrega `Newtonsoft.Json` a *ToDo.csproj* se producirá un resultado similar al del siguiente ejemplo:

```console
Writing C:\Users\me\AppData\Local\Temp\tmp95A8.tmp
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

- **`PROJECT`**

  Especifica el archivo del proyecto. Si no se especifica, el comando busca uno en el directorio actual.

- **`PACKAGE_NAME`**

  La referencia de paquete que se va a agregar.

## <a name="options"></a>Opciones

- **`-f|--framework <FRAMEWORK>`**

  Agrega una referencia de paquete solo cuando se destina a un [marco](../../standard/frameworks.md) específico.

- **`-h|--help`**

  Imprime una corta ayuda para el comando.

- **`--interactive`**

  Permite que el comando se detenga y espere la entrada o acción del usuario (por ejemplo, completar la autenticación). Disponible desde el SDK de .NET Core 2.1, versión 2.1.400 o posterior.

- **`-n|--no-restore`**

  Agrega una referencia de paquete sin realizar una vista previa de restauración y una comprobación de compatibilidad.

- **`--package-directory <PACKAGE_DIRECTORY>`**

  Directorio donde quiere restaurar los paquetes. La ubicación predeterminada de restauración de paquetes es `%userprofile%\.nuget\packages` en Windows y `~/.nuget/packages` en macOS y Linux. Para obtener más información, vea [Administración de las carpetas de paquetes globales, de caché y temporales in NuGet](https://docs.microsoft.com/nuget/consume-packages/managing-the-global-packages-and-cache-folders).

- **`-s|--source <SOURCE>`**

  Origen del paquete NuGet que se usará durante la operación de restauración.

- **`-v|--version <VERSION>`**

  Versión del paquete. Consulte [NuGet package versioning](https://docs.microsoft.com/nuget/reference/package-versioning) (Control de versiones de paquetes NuGet).

## <a name="examples"></a>Ejemplos

- Agregar un paquete de NuGet `Newtonsoft.Json` a un proyecto:

  ```dotnetcli
  dotnet add package Newtonsoft.Json
  ```

- Agregar una versión específica de un paquete a un proyecto:

  ```dotnetcli
  dotnet add ToDo.csproj package Microsoft.Azure.DocumentDB.Core -v 1.0.0
  ```

- Agregar un paquete con un origen de NuGet específico:

  ```dotnetcli
  dotnet add package Microsoft.AspNetCore.StaticFiles -s https://dotnet.myget.org/F/dotnet-core/api/v3/index.json
  ```

## <a name="see-also"></a>Vea también

- [Administración de las carpetas de paquetes globales, de caché y temporales en NuGet](https://docs.microsoft.com/nuget/consume-packages/managing-the-global-packages-and-cache-folders)
- [Control de versiones de paquetes NuGet](https://docs.microsoft.com/nuget/reference/package-versioning)
