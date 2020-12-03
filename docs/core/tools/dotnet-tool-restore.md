---
title: Comando dotnet tool restore
description: El comando dotnet tool restore instala en el equipo las herramientas locales de .NET que se encuentran en el ámbito del directorio actual.
ms.date: 02/14/2020
ms.openlocfilehash: 3425bc6b78fd53f578c209013f83b006305dbb81
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96242934"
---
# <a name="dotnet-tool-restore"></a><span data-ttu-id="54735-103">dotnet tool restore</span><span class="sxs-lookup"><span data-stu-id="54735-103">dotnet tool restore</span></span>

<span data-ttu-id="54735-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 3.0 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="54735-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="54735-105">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="54735-105">Name</span></span>

<span data-ttu-id="54735-106">`dotnet tool restore`: instala las herramientas locales de .NET que se encuentran en el ámbito del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="54735-106">`dotnet tool restore` - Installs the .NET local tools that are in scope for the current directory.</span></span>

## <a name="synopsis"></a><span data-ttu-id="54735-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="54735-107">Synopsis</span></span>

```dotnetcli
dotnet tool restore
    [--configfile <FILE>] [--add-source <SOURCE>]
    [tool-manifest <PATH_TO_MANIFEST_FILE>] [--disable-parallel]
    [--ignore-failed-sources] [--no-cache] [--interactive]
    [-v|--verbosity <LEVEL>]

dotnet tool restore -h|--help
```

## <a name="description"></a><span data-ttu-id="54735-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="54735-108">Description</span></span>

<span data-ttu-id="54735-109">El comando `dotnet tool restore` busca el archivo de manifiesto de las herramientas que está en el ámbito del directorio actual e instala las herramientas que se indican en él.</span><span class="sxs-lookup"><span data-stu-id="54735-109">The `dotnet tool restore` command finds the tool manifest file that is in scope for the current directory and installs the tools that are listed in it.</span></span> <span data-ttu-id="54735-110">Para obtener información sobre los archivos de manifiesto, vea [Instalación de una herramienta local](global-tools.md#install-a-local-tool) e [Invocación de una herramienta local](global-tools.md#invoke-a-local-tool).</span><span class="sxs-lookup"><span data-stu-id="54735-110">For information about manifest files, see [Install a local tool](global-tools.md#install-a-local-tool) and [Invoke a local tool](global-tools.md#invoke-a-local-tool).</span></span>

## <a name="options"></a><span data-ttu-id="54735-111">Opciones</span><span class="sxs-lookup"><span data-stu-id="54735-111">Options</span></span>

- **`--configfile <FILE>`**

  <span data-ttu-id="54735-112">El archivo de configuración de NuGet (*nuget.config*) que se usará.</span><span class="sxs-lookup"><span data-stu-id="54735-112">The NuGet configuration (*nuget.config*) file to use.</span></span>

- **`--add-source <SOURCE>`**

  <span data-ttu-id="54735-113">Agrega un origen de paquete NuGet adicional que se usará durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="54735-113">Adds an additional NuGet package source to use during installation.</span></span>

- **`--tool-manifest <PATH>`**

  <span data-ttu-id="54735-114">Ruta de acceso al archivo de manifiesto.</span><span class="sxs-lookup"><span data-stu-id="54735-114">Path to the manifest file.</span></span>

- **`--disable-parallel`**

  <span data-ttu-id="54735-115">Impide que se restauren varios proyectos en paralelo.</span><span class="sxs-lookup"><span data-stu-id="54735-115">Prevent restoring multiple projects in parallel.</span></span>

- **`--ignore-failed-sources`**

  <span data-ttu-id="54735-116">Indica que los errores de origen de paquete se traten como advertencias.</span><span class="sxs-lookup"><span data-stu-id="54735-116">Treat package source failures as warnings.</span></span>

- **`--no-cache`**

  <span data-ttu-id="54735-117">Indica que no se almacenen en caché los paquetes ni las solicitudes HTTP.</span><span class="sxs-lookup"><span data-stu-id="54735-117">Do not cache packages and http requests.</span></span>

- **`--interactive`**

  <span data-ttu-id="54735-118">Permite que el comando se detenga y espere la entrada o acción del usuario (por ejemplo, completar la autenticación).</span><span class="sxs-lookup"><span data-stu-id="54735-118">Allows the command to stop and wait for user input or action (for example to complete authentication).</span></span>

- **`-h|--help`**

  <span data-ttu-id="54735-119">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="54735-119">Prints out a short help for the command.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="54735-120">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="54735-120">Sets the verbosity level of the command.</span></span> <span data-ttu-id="54735-121">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="54735-121">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

## <a name="example"></a><span data-ttu-id="54735-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="54735-122">Example</span></span>

- **`dotnet tool restore`**

  <span data-ttu-id="54735-123">Restaura las herramientas locales del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="54735-123">Restores local tools for the current directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="54735-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="54735-124">See also</span></span>

- [<span data-ttu-id="54735-125">Herramientas de .NET</span><span class="sxs-lookup"><span data-stu-id="54735-125">.NET tools</span></span>](global-tools.md)
- [<span data-ttu-id="54735-126">Tutorial: Instalación y uso de una herramienta local de .NET mediante la CLI de .NET</span><span class="sxs-lookup"><span data-stu-id="54735-126">Tutorial: Install and use a .NET local tool using the .NET CLI</span></span>](local-tools-how-to-use.md)
