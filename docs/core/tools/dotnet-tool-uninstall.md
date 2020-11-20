---
title: Comando dotnet tool uninstall
description: El comando dotnet tool uninstall desinstala del equipo la herramienta especificada de .NET.
ms.date: 02/14/2020
ms.openlocfilehash: 34dffde8f9c930327c6b42d1d89bb4f511959fb2
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2020
ms.locfileid: "94634095"
---
# <a name="dotnet-tool-uninstall"></a><span data-ttu-id="0f227-103">dotnet tool uninstall</span><span class="sxs-lookup"><span data-stu-id="0f227-103">dotnet tool uninstall</span></span>

<span data-ttu-id="0f227-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.1 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="0f227-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="0f227-105">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="0f227-105">Name</span></span>

<span data-ttu-id="0f227-106">`dotnet tool uninstall`: desinstala la [herramienta de .NET](global-tools.md) especificada del equipo.</span><span class="sxs-lookup"><span data-stu-id="0f227-106">`dotnet tool uninstall` - Uninstalls the specified [.NET tool](global-tools.md) from your machine.</span></span>

## <a name="synopsis"></a><span data-ttu-id="0f227-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="0f227-107">Synopsis</span></span>

```dotnetcli
dotnet tool uninstall <PACKAGE_NAME> -g|--global

dotnet tool uninstall <PACKAGE_NAME> --tool-path <PATH>

dotnet tool uninstall <PACKAGE_NAME>

dotnet tool uninstall -h|--help
```

## <a name="description"></a><span data-ttu-id="0f227-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="0f227-108">Description</span></span>

<span data-ttu-id="0f227-109">El comando `dotnet tool uninstall` permite desinstalar del equipo herramientas de .NET.</span><span class="sxs-lookup"><span data-stu-id="0f227-109">The `dotnet tool uninstall` command provides a way for you to uninstall .NET tools from your machine.</span></span> <span data-ttu-id="0f227-110">Para usar el comando, especifique una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="0f227-110">To use the command, you specify one of the following options:</span></span>

* <span data-ttu-id="0f227-111">Para desinstalar una herramienta global que se instaló en la ubicación predeterminada, use la opción `--global`.</span><span class="sxs-lookup"><span data-stu-id="0f227-111">To uninstall a global tool that was installed in the default location, use the `--global` option.</span></span>
* <span data-ttu-id="0f227-112">Para desinstalar una herramienta global que se instaló en una ubicación personalizada, use la opción `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="0f227-112">To uninstall a global tool that was installed in a custom location,  use the `--tool-path` option.</span></span>
* <span data-ttu-id="0f227-113">Para desinstalar una herramienta local, omita las opciones `--global` y `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="0f227-113">To uninstall a local tool, omit the `--global` and `--tool-path` options.</span></span>

<span data-ttu-id="0f227-114">**Las herramientas locales están disponibles a partir del SDK de .NET Core 3.0.**</span><span class="sxs-lookup"><span data-stu-id="0f227-114">**Local tools are available starting with .NET Core SDK 3.0.**</span></span>

## <a name="arguments"></a><span data-ttu-id="0f227-115">Argumentos</span><span class="sxs-lookup"><span data-stu-id="0f227-115">Arguments</span></span>

- **`PACKAGE_NAME`**

  <span data-ttu-id="0f227-116">Nombre o identificador del paquete NuGet que contiene la herramienta de .NET que se va a desinstalar.</span><span class="sxs-lookup"><span data-stu-id="0f227-116">Name/ID of the NuGet package that contains the .NET tool to uninstall.</span></span> <span data-ttu-id="0f227-117">Para conocer el nombre el paquete, use el comando [dotnet tool list](dotnet-tool-list.md).</span><span class="sxs-lookup"><span data-stu-id="0f227-117">You can find the package name using the [dotnet tool list](dotnet-tool-list.md) command.</span></span>

## <a name="options"></a><span data-ttu-id="0f227-118">Opciones</span><span class="sxs-lookup"><span data-stu-id="0f227-118">Options</span></span>

- **`-g|--global`**

  <span data-ttu-id="0f227-119">Especifica que la herramienta que se va a quitar es de una instalación en el ámbito de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="0f227-119">Specifies that the tool to be removed is from a user-wide installation.</span></span> <span data-ttu-id="0f227-120">No se puede combinar con la opción `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="0f227-120">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="0f227-121">Al omitir `--global` y `--tool-path`, se especifica que la herramienta que se va a quitar es una herramienta local.</span><span class="sxs-lookup"><span data-stu-id="0f227-121">Omitting both `--global` and `--tool-path` specifies that the tool to be removed is a local tool.</span></span>

- **`-h|--help`**

  <span data-ttu-id="0f227-122">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="0f227-122">Prints out a short help for the command.</span></span>

- **`--tool-path <PATH>`**

  <span data-ttu-id="0f227-123">Especifica la ubicación de donde se tiene que desinstalar la herramienta.</span><span class="sxs-lookup"><span data-stu-id="0f227-123">Specifies the location where to uninstall the tool.</span></span> <span data-ttu-id="0f227-124">PATH puede ser una ruta absoluta o relativa.</span><span class="sxs-lookup"><span data-stu-id="0f227-124">PATH can be absolute or relative.</span></span> <span data-ttu-id="0f227-125">No se puede combinar con la opción `--global`.</span><span class="sxs-lookup"><span data-stu-id="0f227-125">Can't be combined with the `--global` option.</span></span> <span data-ttu-id="0f227-126">Al omitir `--global` y `--tool-path`, se especifica que la herramienta que se va a quitar es una herramienta local.</span><span class="sxs-lookup"><span data-stu-id="0f227-126">Omitting both `--global` and `--tool-path` specifies that the tool to be removed is a local tool.</span></span>

## <a name="examples"></a><span data-ttu-id="0f227-127">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="0f227-127">Examples</span></span>

- **`dotnet tool uninstall -g dotnetsay`**

  <span data-ttu-id="0f227-128">Desinstala la herramienta global [dotnetsay](https://www.nuget.org/packages/dotnetsay/).</span><span class="sxs-lookup"><span data-stu-id="0f227-128">Uninstalls the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) global tool.</span></span>

- **`dotnet tool uninstall dotnetsay --tool-path c:\global-tools`**

  <span data-ttu-id="0f227-129">Desinstala la herramienta global [dotnetsay](https://www.nuget.org/packages/dotnetsay/) de un directorio específico de Windows.</span><span class="sxs-lookup"><span data-stu-id="0f227-129">Uninstalls the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) global tool from a specific Windows directory.</span></span>

- **`dotnet tool uninstall dotnetsay --tool-path ~/bin`**

  <span data-ttu-id="0f227-130">Desinstala la herramienta global [dotnetsay](https://www.nuget.org/packages/dotnetsay/) de un directorio específico de Linux/macOS.</span><span class="sxs-lookup"><span data-stu-id="0f227-130">Uninstalls the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) global tool from a specific Linux/macOS directory.</span></span>

- **`dotnet tool uninstall dotnetsay`**

  <span data-ttu-id="0f227-131">Desinstala la herramienta local [dotnetsay](https://www.nuget.org/packages/dotnetsay/) del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="0f227-131">Uninstalls the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) local tool from the current directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="0f227-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="0f227-132">See also</span></span>

- [<span data-ttu-id="0f227-133">Herramientas de .NET</span><span class="sxs-lookup"><span data-stu-id="0f227-133">.NET tools</span></span>](global-tools.md)
- [<span data-ttu-id="0f227-134">Tutorial: Instalación y uso de una herramienta global de .NET mediante la CLI de .NET</span><span class="sxs-lookup"><span data-stu-id="0f227-134">Tutorial: Install and use a .NET global tool using the .NET CLI</span></span>](global-tools-how-to-use.md)
- [<span data-ttu-id="0f227-135">Tutorial: Instalación y uso de una herramienta local de .NET mediante la CLI de .NET</span><span class="sxs-lookup"><span data-stu-id="0f227-135">Tutorial: Install and use a .NET local tool using the .NET CLI</span></span>](local-tools-how-to-use.md)
