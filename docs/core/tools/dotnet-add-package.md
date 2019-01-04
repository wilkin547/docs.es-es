---
title: Comando dotnet add package
description: El comando “dotnet add package” constituye una opción práctica para agregar la referencia de un paquete de NuGet a un proyecto.
ms.date: 12/04/2018
ms.openlocfilehash: 159b208feafb82e267629ea47dcef02d6b575055
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53170007"
---
# <a name="dotnet-add-package"></a><span data-ttu-id="d86db-103">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="d86db-103">dotnet add package</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="d86db-104">nombre</span><span class="sxs-lookup"><span data-stu-id="d86db-104">Name</span></span>

<span data-ttu-id="d86db-105">`dotnet add package`: agrega una referencia de paquete a un archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="d86db-105">`dotnet add package` - Adds a package reference to a project file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="d86db-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="d86db-106">Synopsis</span></span>

`dotnet add [<PROJECT>] package <PACKAGE_NAME> [-h|--help] [-f|--framework] [--interactive] [-n|--no-restore] [--package-directory] [-s|--source] [-v|--version]`

## <a name="description"></a><span data-ttu-id="d86db-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="d86db-107">Description</span></span>

<span data-ttu-id="d86db-108">El comando `dotnet add package` constituye una opción práctica para agregar una referencia de paquete a un archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="d86db-108">The `dotnet add package` command provides a convenient option to add a package reference to a project file.</span></span> <span data-ttu-id="d86db-109">Después de ejecutar el comando, existe una comprobación de compatibilidad para garantizar que el paquete es compatible con los marcos del proyecto.</span><span class="sxs-lookup"><span data-stu-id="d86db-109">After running the command, there's a compatibility check to ensure the package is compatible with the frameworks in the project.</span></span> <span data-ttu-id="d86db-110">Si se pasa la comprobación, un elemento `<PackageReference>` se agrega al archivo del proyecto y [dotnet restore](dotnet-restore.md) se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="d86db-110">If the check passes, a `<PackageReference>` element is added to the project file and [dotnet restore](dotnet-restore.md) is run.</span></span>

[!INCLUDE[DotNet Restore Note](../../../includes/dotnet-restore-note.md)]

<span data-ttu-id="d86db-111">Por ejemplo, si agrega `Newtonsoft.Json` a *ToDo.csproj* se producirá un resultado similar al del siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d86db-111">For example, adding `Newtonsoft.Json` to *ToDo.csproj* produces output similar to the following example:</span></span>

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

<span data-ttu-id="d86db-112">El archivo *ToDo.csproj* contiene ahora un elemento [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files) para el paquete al que hace referencia.</span><span class="sxs-lookup"><span data-stu-id="d86db-112">The *ToDo.csproj* file now contains a [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files) element for the referenced package.</span></span>

```xml
<PackageReference Include="Newtonsoft.Json" Version="12.0.1" />
```

## <a name="arguments"></a><span data-ttu-id="d86db-113">Argumentos</span><span class="sxs-lookup"><span data-stu-id="d86db-113">Arguments</span></span>

* **`PROJECT`**

  <span data-ttu-id="d86db-114">Especifica el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="d86db-114">Specifies the project file.</span></span> <span data-ttu-id="d86db-115">Si no se especifica, el comando busca uno en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="d86db-115">If not specified, the command searches the current directory for one.</span></span>

* **`PACKAGE_NAME`**

  <span data-ttu-id="d86db-116">La referencia de paquete que se va a agregar.</span><span class="sxs-lookup"><span data-stu-id="d86db-116">The package reference to add.</span></span>

## <a name="options"></a><span data-ttu-id="d86db-117">Opciones</span><span class="sxs-lookup"><span data-stu-id="d86db-117">Options</span></span>

* **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="d86db-118">Agrega una referencia de paquete solo cuando se destina a un [marco](../../standard/frameworks.md) específico.</span><span class="sxs-lookup"><span data-stu-id="d86db-118">Adds a package reference only when targeting a specific [framework](../../standard/frameworks.md).</span></span>

* **`-h|--help`**

  <span data-ttu-id="d86db-119">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="d86db-119">Prints out a short help for the command.</span></span>

* **`--interactive`**

  <span data-ttu-id="d86db-120">Permite que el comando se detenga y espere la entrada o acción del usuario (por ejemplo, completar la autenticación).</span><span class="sxs-lookup"><span data-stu-id="d86db-120">Allows the command to stop and wait for user input or action (for example to complete authentication).</span></span> <span data-ttu-id="d86db-121">Disponible desde el SDK de .NET Core 2.1, versión 2.1.400 o posterior.</span><span class="sxs-lookup"><span data-stu-id="d86db-121">Available since .NET Core 2.1 SDK, version 2.1.400 or later.</span></span>

* **`-n|--no-restore`**

  <span data-ttu-id="d86db-122">Agrega una referencia de paquete sin realizar una vista previa de restauración y una comprobación de compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="d86db-122">Adds a package reference without performing a restore preview and compatibility check.</span></span>

* **`--package-directory <PACKAGE_DIRECTORY>`**

  <span data-ttu-id="d86db-123">Restaura el paquete al directorio especificado.</span><span class="sxs-lookup"><span data-stu-id="d86db-123">Restores the package to the specified directory.</span></span>

* **`-s|--source <SOURCE>`**

  <span data-ttu-id="d86db-124">Usa un origen de paquete específico NuGet durante la operación de restauración.</span><span class="sxs-lookup"><span data-stu-id="d86db-124">Uses a specific NuGet package source during the restore operation.</span></span>

* **`-v|--version <VERSION>`**

  <span data-ttu-id="d86db-125">Versión del paquete.</span><span class="sxs-lookup"><span data-stu-id="d86db-125">Version of the package.</span></span>

## <a name="examples"></a><span data-ttu-id="d86db-126">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="d86db-126">Examples</span></span>

* <span data-ttu-id="d86db-127">Agregar un paquete de NuGet `Newtonsoft.Json` a un proyecto:</span><span class="sxs-lookup"><span data-stu-id="d86db-127">Add `Newtonsoft.Json` NuGet package to a project:</span></span>

  ```console
  dotnet add package Newtonsoft.Json
  ```

* <span data-ttu-id="d86db-128">Agregar una versión específica de un paquete a un proyecto:</span><span class="sxs-lookup"><span data-stu-id="d86db-128">Add a specific version of a package to a project:</span></span>

  ```console
  dotnet add ToDo.csproj package Microsoft.Azure.DocumentDB.Core -v 1.0.0
  ```

* <span data-ttu-id="d86db-129">Agregar un paquete con un origen de NuGet específico:</span><span class="sxs-lookup"><span data-stu-id="d86db-129">Add a package using a specific NuGet source:</span></span>

  ```console
  dotnet add package Microsoft.AspNetCore.StaticFiles -s https://dotnet.myget.org/F/dotnet-core/api/v3/index.json
  ```