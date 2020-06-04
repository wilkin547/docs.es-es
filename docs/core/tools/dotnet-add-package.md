---
title: Comando dotnet add package
description: El comando “dotnet add package” constituye una opción práctica para agregar la referencia de un paquete de NuGet a un proyecto.
ms.date: 02/14/2020
ms.openlocfilehash: bc79fe8adf5f775ddce62f3877a8de945c6a18ab
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/26/2020
ms.locfileid: "83840902"
---
# <a name="dotnet-add-package"></a><span data-ttu-id="95686-103">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="95686-103">dotnet add package</span></span>

<span data-ttu-id="95686-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.x y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="95686-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="95686-105">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="95686-105">Name</span></span>

<span data-ttu-id="95686-106">`dotnet add package`: agrega una referencia de paquete a un archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="95686-106">`dotnet add package` - Adds a package reference to a project file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="95686-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="95686-107">Synopsis</span></span>

```dotnetcli
dotnet add [<PROJECT>] package <PACKAGE_NAME>
    [-f|--framework <FRAMEWORK>] [--interactive]
    [-n|--no-restore] [--package-directory <PACKAGE_DIRECTORY>]
    [-s|--source <SOURCE>] [-v|--version <VERSION>]

dotnet add package -h|--help
```

## <a name="description"></a><span data-ttu-id="95686-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="95686-108">Description</span></span>

<span data-ttu-id="95686-109">El comando `dotnet add package` constituye una opción práctica para agregar una referencia de paquete a un archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="95686-109">The `dotnet add package` command provides a convenient option to add a package reference to a project file.</span></span> <span data-ttu-id="95686-110">Después de ejecutar el comando, existe una comprobación de compatibilidad para garantizar que el paquete es compatible con los marcos del proyecto.</span><span class="sxs-lookup"><span data-stu-id="95686-110">After running the command, there's a compatibility check to ensure the package is compatible with the frameworks in the project.</span></span> <span data-ttu-id="95686-111">Si se pasa la comprobación, un elemento `<PackageReference>` se agrega al archivo del proyecto y [dotnet restore](dotnet-restore.md) se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="95686-111">If the check passes, a `<PackageReference>` element is added to the project file and [dotnet restore](dotnet-restore.md) is run.</span></span>

<span data-ttu-id="95686-112">Por ejemplo, si agrega `Newtonsoft.Json` a *ToDo.csproj* se producirá un resultado similar al del siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="95686-112">For example, adding `Newtonsoft.Json` to *ToDo.csproj* produces output similar to the following example:</span></span>

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

<span data-ttu-id="95686-113">El archivo *ToDo.csproj* contiene ahora un elemento [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files) para el paquete al que hace referencia.</span><span class="sxs-lookup"><span data-stu-id="95686-113">The *ToDo.csproj* file now contains a [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files) element for the referenced package.</span></span>

```xml
<PackageReference Include="Newtonsoft.Json" Version="12.0.1" />
```

### <a name="implicit-restore"></a><span data-ttu-id="95686-114">Restauración implícita</span><span class="sxs-lookup"><span data-stu-id="95686-114">Implicit restore</span></span>

[!INCLUDE[DotNet Restore Note](../../../includes/dotnet-restore-note.md)]

## <a name="arguments"></a><span data-ttu-id="95686-115">Argumentos</span><span class="sxs-lookup"><span data-stu-id="95686-115">Arguments</span></span>

- **`PROJECT`**

  <span data-ttu-id="95686-116">Especifica el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="95686-116">Specifies the project file.</span></span> <span data-ttu-id="95686-117">Si no se especifica, el comando busca uno en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="95686-117">If not specified, the command searches the current directory for one.</span></span>

- **`PACKAGE_NAME`**

  <span data-ttu-id="95686-118">La referencia de paquete que se va a agregar.</span><span class="sxs-lookup"><span data-stu-id="95686-118">The package reference to add.</span></span>

## <a name="options"></a><span data-ttu-id="95686-119">Opciones</span><span class="sxs-lookup"><span data-stu-id="95686-119">Options</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="95686-120">Agrega una referencia de paquete solo cuando se destina a un [marco](../../standard/frameworks.md) específico.</span><span class="sxs-lookup"><span data-stu-id="95686-120">Adds a package reference only when targeting a specific [framework](../../standard/frameworks.md).</span></span>

- **`-h|--help`**

  <span data-ttu-id="95686-121">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="95686-121">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="95686-122">Permite que el comando se detenga y espere la entrada o acción del usuario (por ejemplo, completar la autenticación).</span><span class="sxs-lookup"><span data-stu-id="95686-122">Allows the command to stop and wait for user input or action (for example, to complete authentication).</span></span> <span data-ttu-id="95686-123">Disponible desde el SDK de .NET Core 2.1, versión 2.1.400 o posterior.</span><span class="sxs-lookup"><span data-stu-id="95686-123">Available since .NET Core 2.1 SDK, version 2.1.400 or later.</span></span>

- **`-n|--no-restore`**

  <span data-ttu-id="95686-124">Agrega una referencia de paquete sin realizar una vista previa de restauración y una comprobación de compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="95686-124">Adds a package reference without performing a restore preview and compatibility check.</span></span>

- **`--package-directory <PACKAGE_DIRECTORY>`**

  <span data-ttu-id="95686-125">Directorio donde quiere restaurar los paquetes.</span><span class="sxs-lookup"><span data-stu-id="95686-125">The directory where to restore the packages.</span></span> <span data-ttu-id="95686-126">La ubicación predeterminada de restauración de paquetes es `%userprofile%\.nuget\packages` en Windows y `~/.nuget/packages` en macOS y Linux.</span><span class="sxs-lookup"><span data-stu-id="95686-126">The default package restore location is `%userprofile%\.nuget\packages` on Windows and `~/.nuget/packages` on macOS and Linux.</span></span> <span data-ttu-id="95686-127">Para obtener más información, vea [Administración de las carpetas de paquetes globales, de caché y temporales in NuGet](https://docs.microsoft.com/nuget/consume-packages/managing-the-global-packages-and-cache-folders).</span><span class="sxs-lookup"><span data-stu-id="95686-127">For more information, see [Managing the global packages, cache, and temp folders in NuGet](https://docs.microsoft.com/nuget/consume-packages/managing-the-global-packages-and-cache-folders).</span></span>

- **`-s|--source <SOURCE>`**

  <span data-ttu-id="95686-128">URI del origen del paquete NuGet que se usará durante la operación de restauración.</span><span class="sxs-lookup"><span data-stu-id="95686-128">The URI of the NuGet package source to use during the restore operation.</span></span>

- **`-v|--version <VERSION>`**

  <span data-ttu-id="95686-129">Versión del paquete.</span><span class="sxs-lookup"><span data-stu-id="95686-129">Version of the package.</span></span> <span data-ttu-id="95686-130">Consulte [NuGet package versioning](https://docs.microsoft.com/nuget/reference/package-versioning) (Control de versiones de paquetes NuGet).</span><span class="sxs-lookup"><span data-stu-id="95686-130">See [NuGet package versioning](https://docs.microsoft.com/nuget/reference/package-versioning).</span></span>

## <a name="examples"></a><span data-ttu-id="95686-131">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="95686-131">Examples</span></span>

- <span data-ttu-id="95686-132">Agregar un paquete de NuGet `Newtonsoft.Json` a un proyecto:</span><span class="sxs-lookup"><span data-stu-id="95686-132">Add `Newtonsoft.Json` NuGet package to a project:</span></span>

  ```dotnetcli
  dotnet add package Newtonsoft.Json
  ```

- <span data-ttu-id="95686-133">Agregar una versión específica de un paquete a un proyecto:</span><span class="sxs-lookup"><span data-stu-id="95686-133">Add a specific version of a package to a project:</span></span>

  ```dotnetcli
  dotnet add ToDo.csproj package Microsoft.Azure.DocumentDB.Core -v 1.0.0
  ```

- <span data-ttu-id="95686-134">Agregar un paquete con un origen de NuGet específico:</span><span class="sxs-lookup"><span data-stu-id="95686-134">Add a package using a specific NuGet source:</span></span>

  ```dotnetcli
  dotnet add package Microsoft.AspNetCore.StaticFiles -s https://dotnet.myget.org/F/dotnet-core/api/v3/index.json
  ```

## <a name="see-also"></a><span data-ttu-id="95686-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="95686-135">See also</span></span>

- [<span data-ttu-id="95686-136">Administración de las carpetas de paquetes globales, de caché y temporales en NuGet</span><span class="sxs-lookup"><span data-stu-id="95686-136">Managing the global packages, cache, and temp folders in NuGet</span></span>](https://docs.microsoft.com/nuget/consume-packages/managing-the-global-packages-and-cache-folders)
- [<span data-ttu-id="95686-137">Control de versiones de paquetes NuGet</span><span class="sxs-lookup"><span data-stu-id="95686-137">NuGet package versioning</span></span>](https://docs.microsoft.com/nuget/reference/package-versioning)
