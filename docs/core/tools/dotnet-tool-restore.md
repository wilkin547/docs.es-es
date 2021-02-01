---
title: Comando dotnet tool restore
description: El comando dotnet tool restore instala en el equipo las herramientas locales de .NET que se encuentran en el ámbito del directorio actual.
ms.date: 02/14/2020
ms.openlocfilehash: 87bdfb77cda361b800f107c565cbbed6ad75ec78
ms.sourcegitcommit: 4d5e25a46aa7cd0d29b4b9227b92987354d444c4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98794859"
---
# <a name="dotnet-tool-restore"></a><span data-ttu-id="735ff-103">dotnet tool restore</span><span class="sxs-lookup"><span data-stu-id="735ff-103">dotnet tool restore</span></span>

<span data-ttu-id="735ff-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 3.0 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="735ff-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="735ff-105">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="735ff-105">Name</span></span>

<span data-ttu-id="735ff-106">`dotnet tool restore`: instala las herramientas locales de .NET que se encuentran en el ámbito del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="735ff-106">`dotnet tool restore` - Installs the .NET local tools that are in scope for the current directory.</span></span>

## <a name="synopsis"></a><span data-ttu-id="735ff-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="735ff-107">Synopsis</span></span>

```dotnetcli
dotnet tool restore
    [--configfile <FILE>] [--add-source <SOURCE>]
    [--tool-manifest <PATH_TO_MANIFEST_FILE>] [--disable-parallel]
    [--ignore-failed-sources] [--no-cache] [--interactive]
    [-v|--verbosity <LEVEL>]

dotnet tool restore -h|--help
```

## <a name="description"></a><span data-ttu-id="735ff-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="735ff-108">Description</span></span>

<span data-ttu-id="735ff-109">El comando `dotnet tool restore` busca el archivo de manifiesto de las herramientas que está en el ámbito del directorio actual e instala las herramientas que se indican en él.</span><span class="sxs-lookup"><span data-stu-id="735ff-109">The `dotnet tool restore` command finds the tool manifest file that is in scope for the current directory and installs the tools that are listed in it.</span></span> <span data-ttu-id="735ff-110">Para obtener información sobre los archivos de manifiesto, vea [Instalación de una herramienta local](global-tools.md#install-a-local-tool) e [Invocación de una herramienta local](global-tools.md#invoke-a-local-tool).</span><span class="sxs-lookup"><span data-stu-id="735ff-110">For information about manifest files, see [Install a local tool](global-tools.md#install-a-local-tool) and [Invoke a local tool](global-tools.md#invoke-a-local-tool).</span></span>

## <a name="options"></a><span data-ttu-id="735ff-111">Opciones</span><span class="sxs-lookup"><span data-stu-id="735ff-111">Options</span></span>

- **`--configfile <FILE>`**

  <span data-ttu-id="735ff-112">El archivo de configuración de NuGet (*nuget.config*) que se usará.</span><span class="sxs-lookup"><span data-stu-id="735ff-112">The NuGet configuration (*nuget.config*) file to use.</span></span>

- **`--add-source <SOURCE>`**

  <span data-ttu-id="735ff-113">Agrega un origen de paquete NuGet adicional que se usará durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="735ff-113">Adds an additional NuGet package source to use during installation.</span></span>

- **`--tool-manifest <PATH>`**

  <span data-ttu-id="735ff-114">Ruta de acceso al archivo de manifiesto.</span><span class="sxs-lookup"><span data-stu-id="735ff-114">Path to the manifest file.</span></span>

- **`--disable-parallel`**

  <span data-ttu-id="735ff-115">Impide que se restauren varios proyectos en paralelo.</span><span class="sxs-lookup"><span data-stu-id="735ff-115">Prevent restoring multiple projects in parallel.</span></span>

- **`--ignore-failed-sources`**

  <span data-ttu-id="735ff-116">Indica que los errores de origen de paquete se traten como advertencias.</span><span class="sxs-lookup"><span data-stu-id="735ff-116">Treat package source failures as warnings.</span></span>

- **`--no-cache`**

  <span data-ttu-id="735ff-117">Indica que no se almacenen en caché los paquetes ni las solicitudes HTTP.</span><span class="sxs-lookup"><span data-stu-id="735ff-117">Do not cache packages and http requests.</span></span>

- **`--interactive`**

  <span data-ttu-id="735ff-118">Permite que el comando se detenga y espere la entrada o acción del usuario (por ejemplo, completar la autenticación).</span><span class="sxs-lookup"><span data-stu-id="735ff-118">Allows the command to stop and wait for user input or action (for example to complete authentication).</span></span>

- **`-h|--help`**

  <span data-ttu-id="735ff-119">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="735ff-119">Prints out a short help for the command.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="735ff-120">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="735ff-120">Sets the verbosity level of the command.</span></span> <span data-ttu-id="735ff-121">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="735ff-121">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

## <a name="example"></a><span data-ttu-id="735ff-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="735ff-122">Example</span></span>

- **`dotnet tool restore`**

  <span data-ttu-id="735ff-123">Restaura las herramientas locales del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="735ff-123">Restores local tools for the current directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="735ff-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="735ff-124">See also</span></span>

- [<span data-ttu-id="735ff-125">Herramientas de .NET</span><span class="sxs-lookup"><span data-stu-id="735ff-125">.NET tools</span></span>](global-tools.md)
- [<span data-ttu-id="735ff-126">Tutorial: Instalación y uso de una herramienta local de .NET mediante la CLI de .NET</span><span class="sxs-lookup"><span data-stu-id="735ff-126">Tutorial: Install and use a .NET local tool using the .NET CLI</span></span>](local-tools-how-to-use.md)
