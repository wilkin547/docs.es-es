---
title: Comando dotnet tool update
description: El comando dotnet tool update actualiza la herramienta de .NET Core en su equipo.
ms.date: 02/14/2020
ms.openlocfilehash: 497b052a8b9cfa9dca8d80316075fe7565d6b35a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "78847825"
---
# <a name="dotnet-tool-update"></a><span data-ttu-id="cb508-103">dotnet tool update</span><span class="sxs-lookup"><span data-stu-id="cb508-103">dotnet tool update</span></span>

<span data-ttu-id="cb508-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.1 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="cb508-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="cb508-105">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="cb508-105">Name</span></span>

<span data-ttu-id="cb508-106">`dotnet tool update`: actualiza la [herramienta de .NET Core](global-tools.md) especificada en el equipo.</span><span class="sxs-lookup"><span data-stu-id="cb508-106">`dotnet tool update` - Updates the specified [.NET Core tool](global-tools.md) on your machine.</span></span>

## <a name="synopsis"></a><span data-ttu-id="cb508-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="cb508-107">Synopsis</span></span>

```dotnetcli
dotnet tool update <PACKAGE_NAME> <-g|--global>
    [--configfile] [--framework] [-v|--verbosity]
    [--add-source]

dotnet tool update <PACKAGE_NAME> <--tool-path>
    [--configfile] [--framework] [-v|--verbosity]
    [--add-source]

dotnet tool update <PACKAGE_NAME>
    [--configfile] [--framework] [-v|--verbosity]
    [--add-source]

dotnet tool update <-h|--help>
```

## <a name="description"></a><span data-ttu-id="cb508-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="cb508-108">Description</span></span>

<span data-ttu-id="cb508-109">El comando `dotnet tool update` permite actualizar las herramientas de .NET Core en su equipo a la versión estable más reciente del paquete.</span><span class="sxs-lookup"><span data-stu-id="cb508-109">The `dotnet tool update` command provides a way for you to update .NET Core tools on your machine to the latest stable version of the package.</span></span> <span data-ttu-id="cb508-110">El comando desinstala y vuelve a instalar una herramienta, actualizándola de facto.</span><span class="sxs-lookup"><span data-stu-id="cb508-110">The command uninstalls and reinstalls a tool, effectively updating it.</span></span> <span data-ttu-id="cb508-111">Para usar el comando, especifique una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="cb508-111">To use the command, you specify one of the following options:</span></span>

* <span data-ttu-id="cb508-112">Para actualizar una herramienta global que se instaló en la ubicación predeterminada, use la opción `--global`.</span><span class="sxs-lookup"><span data-stu-id="cb508-112">To update a global tool that was installed in the default location, use the `--global` option</span></span>
* <span data-ttu-id="cb508-113">Para actualizar una herramienta global que se instaló en una ubicación personalizada, use la opción `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="cb508-113">To update a global tool that was installed in a custom location, use the `--tool-path` option.</span></span>
* <span data-ttu-id="cb508-114">Para actualizar una herramienta local, omita las opciones `--global` y `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="cb508-114">To update a local tool, omit the `--global` and `--tool-path` options.</span></span>

<span data-ttu-id="cb508-115">**Las herramientas locales están disponibles a partir del SDK de .NET Core 3.0.**</span><span class="sxs-lookup"><span data-stu-id="cb508-115">**Local tools are available starting with .NET Core SDK 3.0.**</span></span>

## <a name="arguments"></a><span data-ttu-id="cb508-116">Argumentos</span><span class="sxs-lookup"><span data-stu-id="cb508-116">Arguments</span></span>

- **`PACKAGE_NAME`**

  <span data-ttu-id="cb508-117">Nombre o identificador del paquete de NuGet que contiene la herramienta global de .NET Core que se quiere actualizar.</span><span class="sxs-lookup"><span data-stu-id="cb508-117">Name/ID of the NuGet package that contains the .NET Core global tool to update.</span></span> <span data-ttu-id="cb508-118">Para conocer el nombre el paquete, use el comando [dotnet tool list](dotnet-tool-list.md).</span><span class="sxs-lookup"><span data-stu-id="cb508-118">You can find the package name using the [dotnet tool list](dotnet-tool-list.md) command.</span></span>

## <a name="options"></a><span data-ttu-id="cb508-119">Opciones</span><span class="sxs-lookup"><span data-stu-id="cb508-119">Options</span></span>

- **`--add-source <SOURCE>`**

  <span data-ttu-id="cb508-120">Agrega un origen de paquete NuGet adicional que se usará durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="cb508-120">Adds an additional NuGet package source to use during installation.</span></span>

- **`--configfile <FILE>`**

  <span data-ttu-id="cb508-121">El archivo de configuración de NuGet (*nuget.config*) que se usará.</span><span class="sxs-lookup"><span data-stu-id="cb508-121">The NuGet configuration (*nuget.config*) file to use.</span></span>

- **`--framework <FRAMEWORK>`**

  <span data-ttu-id="cb508-122">Especifica la [plataforma de destino](../../standard/frameworks.md) para la que se actualiza la herramienta.</span><span class="sxs-lookup"><span data-stu-id="cb508-122">Specifies the [target framework](../../standard/frameworks.md) to update the tool for.</span></span>

- **`-g|--global`**

  <span data-ttu-id="cb508-123">Especifica que la actualización es para una herramienta del ámbito de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="cb508-123">Specifies that the update is for a user-wide tool.</span></span> <span data-ttu-id="cb508-124">No se puede combinar con la opción `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="cb508-124">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="cb508-125">Al omitir `--global` y `--tool-path`, se especifica que la herramienta que se va a actualizar es una herramienta local.</span><span class="sxs-lookup"><span data-stu-id="cb508-125">Omitting both `--global` and `--tool-path` specifies that the tool to be updated is a local tool.</span></span>

- **`-h|--help`**

  <span data-ttu-id="cb508-126">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="cb508-126">Prints out a short help for the command.</span></span>

- **`--tool-path <PATH>`**

  <span data-ttu-id="cb508-127">Especifica la ubicación en la que está instalada la herramienta global.</span><span class="sxs-lookup"><span data-stu-id="cb508-127">Specifies the location where the global tool is installed.</span></span> <span data-ttu-id="cb508-128">PATH puede ser una ruta absoluta o relativa.</span><span class="sxs-lookup"><span data-stu-id="cb508-128">PATH can be absolute or relative.</span></span> <span data-ttu-id="cb508-129">No se puede combinar con la opción `--global`.</span><span class="sxs-lookup"><span data-stu-id="cb508-129">Can't be combined with the `--global` option.</span></span> <span data-ttu-id="cb508-130">Al omitir `--global` y `--tool-path`, se especifica que la herramienta que se va a actualizar es una herramienta local.</span><span class="sxs-lookup"><span data-stu-id="cb508-130">Omitting both `--global` and `--tool-path` specifies that the tool to be updated is a local tool.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="cb508-131">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="cb508-131">Sets the verbosity level of the command.</span></span> <span data-ttu-id="cb508-132">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="cb508-132">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

## <a name="examples"></a><span data-ttu-id="cb508-133">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="cb508-133">Examples</span></span>

- **`dotnet tool update -g dotnetsay`**

  <span data-ttu-id="cb508-134">Actualiza la herramienta global [dotnetsay](https://www.nuget.org/packages/dotnetsay/).</span><span class="sxs-lookup"><span data-stu-id="cb508-134">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) global tool.</span></span>

- **`dotnet tool update dotnetsay --tool-path c:\global-tools`**

  <span data-ttu-id="cb508-135">Actualiza la herramienta global [dotnetsay](https://www.nuget.org/packages/dotnetsay/) ubicada en un directorio específico de Windows.</span><span class="sxs-lookup"><span data-stu-id="cb508-135">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) global tool located in a specific Windows directory.</span></span>

- **`dotnet tool update dotnetsay --tool-path ~/bin`**

  <span data-ttu-id="cb508-136">Actualiza la herramienta global [dotnetsay](https://www.nuget.org/packages/dotnetsay/) ubicada en un directorio específico de Linux/macOS.</span><span class="sxs-lookup"><span data-stu-id="cb508-136">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) global tool located in a specific Linux/macOS directory.</span></span>

- **`dotnet tool update dotnetsay`**

  <span data-ttu-id="cb508-137">Actualiza la herramienta local [dotnetsay](https://www.nuget.org/packages/dotnetsay/) instalada para el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="cb508-137">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) local tool installed for the current directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="cb508-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="cb508-138">See also</span></span>

- [<span data-ttu-id="cb508-139">Herramientas de .NET Core</span><span class="sxs-lookup"><span data-stu-id="cb508-139">.NET Core tools</span></span>](global-tools.md)
- [<span data-ttu-id="cb508-140">Tutorial: Instalación y uso de una herramienta global de .NET Core mediante la CLI de .NET Core</span><span class="sxs-lookup"><span data-stu-id="cb508-140">Tutorial: Install and use a .NET Core global tool using the .NET Core CLI</span></span>](global-tools-how-to-use.md)
- [<span data-ttu-id="cb508-141">Tutorial: Instalación y uso de una herramienta local de .NET Core mediante la CLI de .NET Core</span><span class="sxs-lookup"><span data-stu-id="cb508-141">Tutorial: Install and use a .NET Core local tool using the .NET Core CLI</span></span>](local-tools-how-to-use.md)
