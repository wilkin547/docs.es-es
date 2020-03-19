---
title: Comando dotnet tool restore
description: El comando dotnet tool restore instala en el equipo las herramientas locales de .NET Core que se encuentran en el ámbito del directorio actual.
ms.date: 02/14/2020
ms.openlocfilehash: cb46f70afb58e482b6aedfddfbf5f3a0c40674f4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79146442"
---
# <a name="dotnet-tool-restore"></a><span data-ttu-id="ef6c8-103">dotnet tool restore</span><span class="sxs-lookup"><span data-stu-id="ef6c8-103">dotnet tool restore</span></span>

<span data-ttu-id="ef6c8-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 3.0 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="ef6c8-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="ef6c8-105">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="ef6c8-105">Name</span></span>

<span data-ttu-id="ef6c8-106">`dotnet tool restore`: instala en el equipo las herramientas locales de .NET Core que se encuentran en el ámbito del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="ef6c8-106">`dotnet tool restore` - Installs on your machine the .NET Core local tools that are in scope for the current directory.</span></span>

## <a name="synopsis"></a><span data-ttu-id="ef6c8-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="ef6c8-107">Synopsis</span></span>

```dotnetcli
dotnet tool restore <PACKAGE_NAME>
    [--configfile] [--add-source] [tool-manifest]
    [--disable-parallel] [--ignore-failed-sources]
    [--no-cache] [-interactive] [-v|--verbosity]

dotnet tool restore <-h|--help>
```

## <a name="description"></a><span data-ttu-id="ef6c8-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="ef6c8-108">Description</span></span>

<span data-ttu-id="ef6c8-109">El comando `dotnet tool restore` busca el archivo de manifiesto de las herramientas que está en el ámbito del directorio actual e instala las herramientas que se indican en él.</span><span class="sxs-lookup"><span data-stu-id="ef6c8-109">The `dotnet tool restore` command finds the tool manifest file that is in scope for the current directory and installs the tools that are listed in it.</span></span> <span data-ttu-id="ef6c8-110">Para obtener información sobre los archivos de manifiesto, vea [Instalación de una herramienta local](global-tools.md#install-a-local-tool) e [Invocación de una herramienta local](global-tools.md#invoke-a-local-tool).</span><span class="sxs-lookup"><span data-stu-id="ef6c8-110">For information about manifest files, see [Install a local tool](global-tools.md#install-a-local-tool) and [Invoke a local tool](global-tools.md#invoke-a-local-tool).</span></span>

## <a name="arguments"></a><span data-ttu-id="ef6c8-111">Argumentos</span><span class="sxs-lookup"><span data-stu-id="ef6c8-111">Arguments</span></span>

- **`PACKAGE_NAME`**

<span data-ttu-id="ef6c8-112">Nombre o identificador del paquete NuGet que contiene la herramienta de .NET Core que se quiere instalar.</span><span class="sxs-lookup"><span data-stu-id="ef6c8-112">Name/ID of the NuGet package that contains the .NET Core tool to install.</span></span>

## <a name="options"></a><span data-ttu-id="ef6c8-113">Opciones</span><span class="sxs-lookup"><span data-stu-id="ef6c8-113">Options</span></span>

- **`--configfile <FILE>`**

  <span data-ttu-id="ef6c8-114">El archivo de configuración de NuGet (*nuget.config*) que se usará.</span><span class="sxs-lookup"><span data-stu-id="ef6c8-114">The NuGet configuration (*nuget.config*) file to use.</span></span>

- **`--add-source <SOURCE>`**

  <span data-ttu-id="ef6c8-115">Agrega un origen de paquete NuGet adicional que se usará durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="ef6c8-115">Adds an additional NuGet package source to use during installation.</span></span>

- **`--tool-manifest <PATH>`**

  <span data-ttu-id="ef6c8-116">Ruta de acceso al archivo de manifiesto.</span><span class="sxs-lookup"><span data-stu-id="ef6c8-116">Path to the manifest file.</span></span>

- **`--disable-parallel`**

  <span data-ttu-id="ef6c8-117">Impide que se restauren varios proyectos en paralelo.</span><span class="sxs-lookup"><span data-stu-id="ef6c8-117">Prevent restoring multiple projects in parallel.</span></span>

- **`--ignore-failed-sources`**

  <span data-ttu-id="ef6c8-118">Indica que los errores de origen de paquete se traten como advertencias.</span><span class="sxs-lookup"><span data-stu-id="ef6c8-118">Treat package source failures as warnings.</span></span>

- **`--no-cache`**

  <span data-ttu-id="ef6c8-119">Indica que no se almacenen en caché los paquetes ni las solicitudes HTTP.</span><span class="sxs-lookup"><span data-stu-id="ef6c8-119">Do not cache packages and http requests.</span></span>

- **`--interactive`**

  <span data-ttu-id="ef6c8-120">Permite que el comando se detenga y espere la entrada o acción del usuario (por ejemplo, completar la autenticación).</span><span class="sxs-lookup"><span data-stu-id="ef6c8-120">Allows the command to stop and wait for user input or action (for example to complete authentication).</span></span>

- **`-h|--help`**

  <span data-ttu-id="ef6c8-121">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="ef6c8-121">Prints out a short help for the command.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="ef6c8-122">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="ef6c8-122">Sets the verbosity level of the command.</span></span> <span data-ttu-id="ef6c8-123">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="ef6c8-123">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

## <a name="example"></a><span data-ttu-id="ef6c8-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ef6c8-124">Example</span></span>

- **`dotnet tool restore`**

  <span data-ttu-id="ef6c8-125">Restaura las herramientas locales del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="ef6c8-125">Restores local tools for the current directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="ef6c8-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="ef6c8-126">See also</span></span>

- [<span data-ttu-id="ef6c8-127">Herramientas de .NET Core</span><span class="sxs-lookup"><span data-stu-id="ef6c8-127">.NET Core tools</span></span>](global-tools.md)
- [<span data-ttu-id="ef6c8-128">Tutorial: Instalación y uso de una herramienta local de .NET Core mediante la CLI de .NET Core</span><span class="sxs-lookup"><span data-stu-id="ef6c8-128">Tutorial: Install and use a .NET Core local tool using the .NET Core CLI</span></span>](local-tools-how-to-use.md)
