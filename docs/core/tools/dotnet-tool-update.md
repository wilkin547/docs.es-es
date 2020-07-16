---
title: Comando dotnet tool update
description: El comando dotnet tool update actualiza la herramienta de .NET Core en su equipo.
ms.date: 07/08/2020
ms.openlocfilehash: 7c4bde44ac9964828074baeb1a697ba64ed17887
ms.sourcegitcommit: 67cf756b033c6173a1bbd1cbd5aef1fccac99e34
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2020
ms.locfileid: "86226626"
---
# <a name="dotnet-tool-update"></a><span data-ttu-id="6785e-103">dotnet tool update</span><span class="sxs-lookup"><span data-stu-id="6785e-103">dotnet tool update</span></span>

<span data-ttu-id="6785e-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.1 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="6785e-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="6785e-105">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="6785e-105">Name</span></span>

<span data-ttu-id="6785e-106">`dotnet tool update`: actualiza la [herramienta de .NET Core](global-tools.md) especificada en el equipo.</span><span class="sxs-lookup"><span data-stu-id="6785e-106">`dotnet tool update` - Updates the specified [.NET Core tool](global-tools.md) on your machine.</span></span>

## <a name="synopsis"></a><span data-ttu-id="6785e-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="6785e-107">Synopsis</span></span>

```dotnetcli
dotnet tool update <PACKAGE_ID> -g|--global
    [--configfile <FILE>] [--framework <FRAMEWORK>]
    [--add-source <SOURCE>] [--disable-parallel]
    [--ignore-failed-sources] [--interactive] [--no-cache]
    [-v|--verbosity <LEVEL>] [--version <VERSION>]

dotnet tool update <PACKAGE_ID> --tool-path <PATH>
    [--configfile <FILE>] [--framework <FRAMEWORK>]
    [--add-source <SOURCE>] [--disable-parallel]
    [--ignore-failed-sources] [--interactive] [--no-cache]
    [-v|--verbosity <LEVEL>] [--version <VERSION>]

dotnet tool update <PACKAGE_ID> --local
    [--configfile <FILE>] [--framework <FRAMEWORK>]
    [--add-source <SOURCE>] [--disable-parallel]
    [--ignore-failed-sources] [--interactive] [--no-cache]
    [--tool-manifest <PATH>]
    [-v|--verbosity <LEVEL>] [--version <VERSION>]

dotnet tool update -h|--help
```

## <a name="description"></a><span data-ttu-id="6785e-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="6785e-108">Description</span></span>

<span data-ttu-id="6785e-109">El comando `dotnet tool update` permite actualizar las herramientas de .NET Core en su equipo a la versión estable más reciente del paquete.</span><span class="sxs-lookup"><span data-stu-id="6785e-109">The `dotnet tool update` command provides a way for you to update .NET Core tools on your machine to the latest stable version of the package.</span></span> <span data-ttu-id="6785e-110">El comando desinstala y vuelve a instalar una herramienta, actualizándola de facto.</span><span class="sxs-lookup"><span data-stu-id="6785e-110">The command uninstalls and reinstalls a tool, effectively updating it.</span></span> <span data-ttu-id="6785e-111">Para usar el comando, especifique una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="6785e-111">To use the command, you specify one of the following options:</span></span>

* <span data-ttu-id="6785e-112">Para actualizar una herramienta global que se instaló en la ubicación predeterminada, use la opción `--global`.</span><span class="sxs-lookup"><span data-stu-id="6785e-112">To update a global tool that was installed in the default location, use the `--global` option</span></span>
* <span data-ttu-id="6785e-113">Para actualizar una herramienta global que se instaló en una ubicación personalizada, use la opción `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="6785e-113">To update a global tool that was installed in a custom location, use the `--tool-path` option.</span></span>
* <span data-ttu-id="6785e-114">Para actualizar una herramienta local, use la opción `--local`.</span><span class="sxs-lookup"><span data-stu-id="6785e-114">To update a local tool, use the `--local` option.</span></span>

<span data-ttu-id="6785e-115">**Las herramientas locales están disponibles a partir del SDK de .NET Core 3.0.**</span><span class="sxs-lookup"><span data-stu-id="6785e-115">**Local tools are available starting with .NET Core SDK 3.0.**</span></span>

## <a name="arguments"></a><span data-ttu-id="6785e-116">Argumentos</span><span class="sxs-lookup"><span data-stu-id="6785e-116">Arguments</span></span>

- **`PACKAGE_ID`**

  <span data-ttu-id="6785e-117">Nombre o identificador del paquete de NuGet que contiene la herramienta global de .NET Core que se quiere actualizar.</span><span class="sxs-lookup"><span data-stu-id="6785e-117">Name/ID of the NuGet package that contains the .NET Core global tool to update.</span></span> <span data-ttu-id="6785e-118">Para conocer el nombre el paquete, use el comando [dotnet tool list](dotnet-tool-list.md).</span><span class="sxs-lookup"><span data-stu-id="6785e-118">You can find the package name using the [dotnet tool list](dotnet-tool-list.md) command.</span></span>

## <a name="options"></a><span data-ttu-id="6785e-119">Opciones</span><span class="sxs-lookup"><span data-stu-id="6785e-119">Options</span></span>

- **`--add-source <SOURCE>`**

  <span data-ttu-id="6785e-120">Agrega un origen de paquete NuGet adicional que se usará durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="6785e-120">Adds an additional NuGet package source to use during installation.</span></span>

- **`--configfile <FILE>`**

  <span data-ttu-id="6785e-121">El archivo de configuración de NuGet (*nuget.config*) que se usará.</span><span class="sxs-lookup"><span data-stu-id="6785e-121">The NuGet configuration (*nuget.config*) file to use.</span></span>

- **`--disable-parallel`**

  <span data-ttu-id="6785e-122">Impide que se restauren varios proyectos en paralelo.</span><span class="sxs-lookup"><span data-stu-id="6785e-122">Prevent restoring multiple projects in parallel.</span></span>

- **`--framework <FRAMEWORK>`**

  <span data-ttu-id="6785e-123">Especifica la [plataforma de destino](../../standard/frameworks.md) para la que se actualiza la herramienta.</span><span class="sxs-lookup"><span data-stu-id="6785e-123">Specifies the [target framework](../../standard/frameworks.md) to update the tool for.</span></span>

- **`--ignore-failed-sources`**

  <span data-ttu-id="6785e-124">Indica que los errores de origen de paquete se traten como advertencias.</span><span class="sxs-lookup"><span data-stu-id="6785e-124">Treat package source failures as warnings.</span></span>

- **`--interactive`**

  <span data-ttu-id="6785e-125">Permite que el comando se detenga y espere la entrada o acción del usuario (por ejemplo, completar la autenticación).</span><span class="sxs-lookup"><span data-stu-id="6785e-125">Allows the command to stop and wait for user input or action (for example to complete authentication).</span></span>

- **`--local`**

  <span data-ttu-id="6785e-126">Actualice la herramienta y el manifiesto de la herramienta local.</span><span class="sxs-lookup"><span data-stu-id="6785e-126">Update the tool and the local tool manifest.</span></span> <span data-ttu-id="6785e-127">No se puede combinar con la opción `--global`.</span><span class="sxs-lookup"><span data-stu-id="6785e-127">Can't be combined with the `--global` option.</span></span>

- **`--no-cache`**

  <span data-ttu-id="6785e-128">Indica que no se almacenen en caché los paquetes ni las solicitudes HTTP.</span><span class="sxs-lookup"><span data-stu-id="6785e-128">Do not cache packages and HTTP requests.</span></span>

- **`--tool-manifest <PATH>`**

  <span data-ttu-id="6785e-129">Ruta de acceso al archivo de manifiesto.</span><span class="sxs-lookup"><span data-stu-id="6785e-129">Path to the manifest file.</span></span>

- **`--tool-path <PATH>`**

  <span data-ttu-id="6785e-130">Especifica la ubicación en la que está instalada la herramienta global.</span><span class="sxs-lookup"><span data-stu-id="6785e-130">Specifies the location where the global tool is installed.</span></span> <span data-ttu-id="6785e-131">PATH puede ser una ruta absoluta o relativa.</span><span class="sxs-lookup"><span data-stu-id="6785e-131">PATH can be absolute or relative.</span></span> <span data-ttu-id="6785e-132">No se puede combinar con la opción `--global`.</span><span class="sxs-lookup"><span data-stu-id="6785e-132">Can't be combined with the `--global` option.</span></span> <span data-ttu-id="6785e-133">Al omitir `--global` y `--tool-path`, se especifica que la herramienta que se va a actualizar es una herramienta local.</span><span class="sxs-lookup"><span data-stu-id="6785e-133">Omitting both `--global` and `--tool-path` specifies that the tool to be updated is a local tool.</span></span>

- **`--version <VERSION>`**

  <span data-ttu-id="6785e-134">El intervalo de versiones del paquete de herramientas al que se actualiza.</span><span class="sxs-lookup"><span data-stu-id="6785e-134">The version range of the tool package to update to.</span></span> <span data-ttu-id="6785e-135">Esto no se puede usar para degradar versiones, primero debe `uninstall` versiones más recientes.</span><span class="sxs-lookup"><span data-stu-id="6785e-135">This cannot be used to downgrade versions, you must `uninstall` newer versions first.</span></span>

- **`-g|--global`**

  <span data-ttu-id="6785e-136">Especifica que la actualización es para una herramienta del ámbito de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="6785e-136">Specifies that the update is for a user-wide tool.</span></span> <span data-ttu-id="6785e-137">No se puede combinar con la opción `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="6785e-137">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="6785e-138">Al omitir `--global` y `--tool-path`, se especifica que la herramienta que se va a actualizar es una herramienta local.</span><span class="sxs-lookup"><span data-stu-id="6785e-138">Omitting both `--global` and `--tool-path` specifies that the tool to be updated is a local tool.</span></span>

- **`-h|--help`**

  <span data-ttu-id="6785e-139">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="6785e-139">Prints out a short help for the command.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="6785e-140">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="6785e-140">Sets the verbosity level of the command.</span></span> <span data-ttu-id="6785e-141">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="6785e-141">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

## <a name="examples"></a><span data-ttu-id="6785e-142">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="6785e-142">Examples</span></span>

- **`dotnet tool update -g dotnetsay`**

  <span data-ttu-id="6785e-143">Actualiza la herramienta global [dotnetsay](https://www.nuget.org/packages/dotnetsay/).</span><span class="sxs-lookup"><span data-stu-id="6785e-143">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) global tool.</span></span>

- **`dotnet tool update dotnetsay --tool-path c:\global-tools`**

  <span data-ttu-id="6785e-144">Actualiza la herramienta global [dotnetsay](https://www.nuget.org/packages/dotnetsay/) ubicada en un directorio específico de Windows.</span><span class="sxs-lookup"><span data-stu-id="6785e-144">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) global tool located in a specific Windows directory.</span></span>

- **`dotnet tool update dotnetsay --tool-path ~/bin`**

  <span data-ttu-id="6785e-145">Actualiza la herramienta global [dotnetsay](https://www.nuget.org/packages/dotnetsay/) ubicada en un directorio específico de Linux/macOS.</span><span class="sxs-lookup"><span data-stu-id="6785e-145">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) global tool located in a specific Linux/macOS directory.</span></span>

- **`dotnet tool update dotnetsay`**

  <span data-ttu-id="6785e-146">Actualiza la herramienta local [dotnetsay](https://www.nuget.org/packages/dotnetsay/) instalada para el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="6785e-146">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) local tool installed for the current directory.</span></span>

- **`dotnet tool update -g dotnetsay --version 2.0.*`**

  <span data-ttu-id="6785e-147">Actualiza la herramienta global [dotnetsay](https://www.nuget.org/packages/dotnetsay/) a la última versión de revisión, con una versión principal de `2` y una versión secundaria de `0`.</span><span class="sxs-lookup"><span data-stu-id="6785e-147">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) global tool to the latest patch version, with a major version of `2`, and a minor version of `0`.</span></span>

- **`dotnet tool update -g dotnetsay --version (2.0.*,2.1.4)`**

  <span data-ttu-id="6785e-148">Actualiza la herramienta global [dotnetsay](https://www.nuget.org/packages/dotnetsay/) a la versión más baja del intervalo especificado `(> 2.0.0 && < 2.1.4)`; se instalará la versión `2.1.0`.</span><span class="sxs-lookup"><span data-stu-id="6785e-148">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) global tool to the lowest version within the specified range `(> 2.0.0 && < 2.1.4)`, version `2.1.0` would be installed.</span></span> <span data-ttu-id="6785e-149">Para obtener más información sobre los intervalos de versiones semánticas, consulte [Intervalos de versiones de empaquetado de NuGet](/nuget/concepts/package-versioning#version-ranges).</span><span class="sxs-lookup"><span data-stu-id="6785e-149">For more information on semantic versioning ranges, see [NuGet packaging version ranges](/nuget/concepts/package-versioning#version-ranges).</span></span>

## <a name="see-also"></a><span data-ttu-id="6785e-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="6785e-150">See also</span></span>

- [<span data-ttu-id="6785e-151">Herramientas de .NET Core</span><span class="sxs-lookup"><span data-stu-id="6785e-151">.NET Core tools</span></span>](global-tools.md)
- [<span data-ttu-id="6785e-152">Versionamiento semántico</span><span class="sxs-lookup"><span data-stu-id="6785e-152">Semantic versioning</span></span>](https://semver.org)
- [<span data-ttu-id="6785e-153">Tutorial: Instalación y uso de una herramienta global de .NET Core mediante la CLI de .NET Core</span><span class="sxs-lookup"><span data-stu-id="6785e-153">Tutorial: Install and use a .NET Core global tool using the .NET Core CLI</span></span>](global-tools-how-to-use.md)
- [<span data-ttu-id="6785e-154">Tutorial: Instalación y uso de una herramienta local de .NET Core mediante la CLI de .NET Core</span><span class="sxs-lookup"><span data-stu-id="6785e-154">Tutorial: Install and use a .NET Core local tool using the .NET Core CLI</span></span>](local-tools-how-to-use.md)
