---
title: Comando dotnet tool install
description: El comando dotnet tool install instala la herramienta especificada de .NET Core en el equipo.
ms.date: 02/14/2020
ms.openlocfilehash: 723d25caa6009288dbb55d55f173b04d7b983450
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463359"
---
# <a name="dotnet-tool-install"></a><span data-ttu-id="61bf8-103">dotnet tool install</span><span class="sxs-lookup"><span data-stu-id="61bf8-103">dotnet tool install</span></span>

<span data-ttu-id="61bf8-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.1 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="61bf8-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="61bf8-105">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="61bf8-105">Name</span></span>

<span data-ttu-id="61bf8-106">`dotnet tool install`: instala la [herramienta de .NET Core](global-tools.md) especificada en el equipo.</span><span class="sxs-lookup"><span data-stu-id="61bf8-106">`dotnet tool install` - Installs the specified [.NET Core tool](global-tools.md) on your machine.</span></span>

## <a name="synopsis"></a><span data-ttu-id="61bf8-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="61bf8-107">Synopsis</span></span>

```dotnetcli
dotnet tool install <PACKAGE_NAME> -g|--global
    [--add-source <SOURCE>] [--configfile <FILE>]
    [--framework <FRAMEWORK>] [-v|--verbosity <LEVEL>]
    [--version <VERSION_NUMBER>]

dotnet tool install <PACKAGE_NAME> --tool-path <PATH>
    [--add-source <SOURCE>] [--configfile <FILE>]
    [--framework <FRAMEWORK>] [-v|--verbosity <LEVEL>]
    [--version <VERSION_NUMBER>]

dotnet tool install <PACKAGE_NAME>
    [--add-source <SOURCE>] [--configfile <FILE>]
    [--framework <FRAMEWORK>] [-v|--verbosity <LEVEL>]
    [--version <VERSION_NUMBER>]

dotnet tool install -h|--help
```

## <a name="description"></a><span data-ttu-id="61bf8-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="61bf8-108">Description</span></span>

<span data-ttu-id="61bf8-109">El comando `dotnet tool install` permite instalar en el equipo herramientas de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="61bf8-109">The `dotnet tool install` command provides a way for you to install .NET Core tools on your machine.</span></span> <span data-ttu-id="61bf8-110">Para usar el comando, especifique una de las siguientes opciones de instalación:</span><span class="sxs-lookup"><span data-stu-id="61bf8-110">To use the command, you specify one of the following installation options:</span></span>

* <span data-ttu-id="61bf8-111">Para instalar una herramienta global en la ubicación predeterminada, use la opción `--global`.</span><span class="sxs-lookup"><span data-stu-id="61bf8-111">To install a global tool in the default location, use the `--global` option.</span></span>
* <span data-ttu-id="61bf8-112">Para instalar una herramienta global en una ubicación personalizada, use la opción `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="61bf8-112">To install a global tool in a custom location,  use the `--tool-path` option.</span></span>
* <span data-ttu-id="61bf8-113">Para instalar una herramienta local, omita las opciones `--global` y `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="61bf8-113">To install a local tool, omit the `--global` and `--tool-path` options.</span></span>

<span data-ttu-id="61bf8-114">**Las herramientas locales están disponibles a partir del SDK de .NET Core 3.0.**</span><span class="sxs-lookup"><span data-stu-id="61bf8-114">**Local tools are available starting with .NET Core SDK 3.0.**</span></span>

<span data-ttu-id="61bf8-115">Las herramientas globales se instalan en los siguientes directorios de forma predeterminada cuando se especifica la opción `-g` o `--global`:</span><span class="sxs-lookup"><span data-stu-id="61bf8-115">Global tools are installed in the following directories by default when you specify the `-g` or `--global` option:</span></span>

| <span data-ttu-id="61bf8-116">SO</span><span class="sxs-lookup"><span data-stu-id="61bf8-116">OS</span></span>          | <span data-ttu-id="61bf8-117">Ruta de acceso</span><span class="sxs-lookup"><span data-stu-id="61bf8-117">Path</span></span>                          |
|-------------|-------------------------------|
| <span data-ttu-id="61bf8-118">Linux/macOS</span><span class="sxs-lookup"><span data-stu-id="61bf8-118">Linux/macOS</span></span> | `$HOME/.dotnet/tools`         |
| <span data-ttu-id="61bf8-119">Windows</span><span class="sxs-lookup"><span data-stu-id="61bf8-119">Windows</span></span>     | `%USERPROFILE%\.dotnet\tools` |

<span data-ttu-id="61bf8-120">Las herramientas locales se agregan a un archivo *tool-manifest.json* en un directorio *.config* en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="61bf8-120">Local tools are added to a *tool-manifest.json* file in a *.config* directory under the current directory.</span></span> <span data-ttu-id="61bf8-121">Si aún no existe un archivo de manifiesto, créelo ejecutando el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="61bf8-121">If a manifest file doesn't exist yet, create it by running the following command:</span></span>

```dotnetcli
dotnet new tool-manifest
```

<span data-ttu-id="61bf8-122">Para obtener más información, vea [Instalación de una herramienta local](global-tools.md#install-a-local-tool).</span><span class="sxs-lookup"><span data-stu-id="61bf8-122">For more information, see [Install a local tool](global-tools.md#install-a-local-tool).</span></span>

## <a name="arguments"></a><span data-ttu-id="61bf8-123">Argumentos</span><span class="sxs-lookup"><span data-stu-id="61bf8-123">Arguments</span></span>

- **`PACKAGE_NAME`**

  <span data-ttu-id="61bf8-124">Nombre o identificador del paquete NuGet que contiene la herramienta de .NET Core que se quiere instalar.</span><span class="sxs-lookup"><span data-stu-id="61bf8-124">Name/ID of the NuGet package that contains the .NET Core tool to install.</span></span>

## <a name="options"></a><span data-ttu-id="61bf8-125">Opciones</span><span class="sxs-lookup"><span data-stu-id="61bf8-125">Options</span></span>

- **`add-source <SOURCE>`**

  <span data-ttu-id="61bf8-126">Agrega un origen de paquete NuGet adicional que se usará durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="61bf8-126">Adds an additional NuGet package source to use during installation.</span></span>

- **`configfile <FILE>`**

  <span data-ttu-id="61bf8-127">El archivo de configuración de NuGet (*nuget.config*) que se usará.</span><span class="sxs-lookup"><span data-stu-id="61bf8-127">The NuGet configuration (*nuget.config*) file to use.</span></span>

- **`framework <FRAMEWORK>`**

  <span data-ttu-id="61bf8-128">Especifica el [marco de destino](../../standard/frameworks.md) para instalar la herramienta.</span><span class="sxs-lookup"><span data-stu-id="61bf8-128">Specifies the [target framework](../../standard/frameworks.md) to install the tool for.</span></span> <span data-ttu-id="61bf8-129">De forma predeterminada, el SDK de .NET Core intenta elegir la plataforma de destino más apropiada.</span><span class="sxs-lookup"><span data-stu-id="61bf8-129">By default, the .NET Core SDK tries to choose the most appropriate target framework.</span></span>

- **`-g|--global`**

  <span data-ttu-id="61bf8-130">Especifica que la instalación se realiza en todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="61bf8-130">Specifies that the installation is user wide.</span></span> <span data-ttu-id="61bf8-131">No se puede combinar con la opción `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="61bf8-131">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="61bf8-132">Al omitir `--global` y `--tool-path`, se especifica la instalación de una herramienta local.</span><span class="sxs-lookup"><span data-stu-id="61bf8-132">Omitting both `--global` and `--tool-path` specifies a local tool installation.</span></span>

- **`-h|--help`**

  <span data-ttu-id="61bf8-133">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="61bf8-133">Prints out a short help for the command.</span></span>

- **`tool-path <PATH>`**

  <span data-ttu-id="61bf8-134">Especifica la ubicación de donde se tiene que instalar la herramienta global.</span><span class="sxs-lookup"><span data-stu-id="61bf8-134">Specifies the location where to install the Global Tool.</span></span> <span data-ttu-id="61bf8-135">PATH puede ser una ruta absoluta o relativa.</span><span class="sxs-lookup"><span data-stu-id="61bf8-135">PATH can be absolute or relative.</span></span> <span data-ttu-id="61bf8-136">Si la ruta no existe, el comando intenta crearla.</span><span class="sxs-lookup"><span data-stu-id="61bf8-136">If PATH doesn't exist, the command tries to create it.</span></span> <span data-ttu-id="61bf8-137">Al omitir `--global` y `--tool-path`, se especifica la instalación de una herramienta local.</span><span class="sxs-lookup"><span data-stu-id="61bf8-137">Omitting both `--global` and `--tool-path` specifies a local tool installation.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="61bf8-138">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="61bf8-138">Sets the verbosity level of the command.</span></span> <span data-ttu-id="61bf8-139">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="61bf8-139">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

- **`--version <VERSION_NUMBER>`**

  <span data-ttu-id="61bf8-140">La versión de la herramienta que se va instalar.</span><span class="sxs-lookup"><span data-stu-id="61bf8-140">The version of the tool to install.</span></span> <span data-ttu-id="61bf8-141">De forma predeterminada, se instala la versión estable más reciente del paquete.</span><span class="sxs-lookup"><span data-stu-id="61bf8-141">By default, the latest stable package version is installed.</span></span> <span data-ttu-id="61bf8-142">Utilice esta opción para instalar la versión preliminar o versiones anteriores de la herramienta.</span><span class="sxs-lookup"><span data-stu-id="61bf8-142">Use this option to install preview or older versions of the tool.</span></span>

## <a name="examples"></a><span data-ttu-id="61bf8-143">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="61bf8-143">Examples</span></span>

- **`dotnet tool install -g dotnetsay`**

  <span data-ttu-id="61bf8-144">Instala [dotnetsay](https://www.nuget.org/packages/dotnetsay/) como herramienta global en la ubicación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="61bf8-144">Installs [dotnetsay](https://www.nuget.org/packages/dotnetsay/) as a global tool in the default location.</span></span>

- **`dotnet tool install dotnetsay --tool-path c:\global-tools`**

  <span data-ttu-id="61bf8-145">Instala [dotnetsay](https://www.nuget.org/packages/dotnetsay/) como herramienta global en un directorio específico de Windows.</span><span class="sxs-lookup"><span data-stu-id="61bf8-145">Installs [dotnetsay](https://www.nuget.org/packages/dotnetsay/) as a global tool in a specific Windows directory.</span></span>

- **`dotnet tool install dotnetsay --tool-path ~/bin`**

  <span data-ttu-id="61bf8-146">Instala [dotnetsay](https://www.nuget.org/packages/dotnetsay/) como herramienta global en un directorio específico de Linux/macOS.</span><span class="sxs-lookup"><span data-stu-id="61bf8-146">Installs [dotnetsay](https://www.nuget.org/packages/dotnetsay/) as a global tool in a specific Linux/macOS directory.</span></span>

- **`dotnet tool install -g dotnetsay --version 2.0.0`**

  <span data-ttu-id="61bf8-147">Instala la versión 2.0.0 de [dotnetsay](https://www.nuget.org/packages/dotnetsay/) como la herramienta global.</span><span class="sxs-lookup"><span data-stu-id="61bf8-147">Installs version 2.0.0 of [dotnetsay](https://www.nuget.org/packages/dotnetsay/) as a global tool.</span></span>

- **`dotnet tool install dotnetsay`**

  <span data-ttu-id="61bf8-148">Instala [dotnetsay](https://www.nuget.org/packages/dotnetsay/) como herramienta local del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="61bf8-148">Installs [dotnetsay](https://www.nuget.org/packages/dotnetsay/) as a local tool for the current directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="61bf8-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="61bf8-149">See also</span></span>

- [<span data-ttu-id="61bf8-150">Herramientas de .NET Core</span><span class="sxs-lookup"><span data-stu-id="61bf8-150">.NET Core tools</span></span>](global-tools.md)
- [<span data-ttu-id="61bf8-151">Tutorial: Instalación y uso de una herramienta global de .NET Core mediante la CLI de .NET Core</span><span class="sxs-lookup"><span data-stu-id="61bf8-151">Tutorial: Install and use a .NET Core global tool using the .NET Core CLI</span></span>](global-tools-how-to-use.md)
- [<span data-ttu-id="61bf8-152">Tutorial: Instalación y uso de una herramienta local de .NET Core mediante la CLI de .NET Core</span><span class="sxs-lookup"><span data-stu-id="61bf8-152">Tutorial: Install and use a .NET Core local tool using the .NET Core CLI</span></span>](local-tools-how-to-use.md)
