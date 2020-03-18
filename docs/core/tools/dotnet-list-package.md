---
title: Comando dotnet list package
description: El comando "dotnet list package" ofrece una opción práctica para mostrar las referencias de paquete de un proyecto o una solución.
ms.date: 02/14/2020
ms.openlocfilehash: 1cb52b8de10b2eef2ef7465f04316e9446318763
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "78157237"
---
# <a name="dotnet-list-package"></a><span data-ttu-id="b4486-103">dotnet list package</span><span class="sxs-lookup"><span data-stu-id="b4486-103">dotnet list package</span></span>

<span data-ttu-id="b4486-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.2 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="b4486-104">**This article applies to:** ✔️ .NET Core 2.2 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="b4486-105">Name</span><span class="sxs-lookup"><span data-stu-id="b4486-105">Name</span></span>

<span data-ttu-id="b4486-106">`dotnet list package`: muestra las referencias de paquete de un proyecto o una solución.</span><span class="sxs-lookup"><span data-stu-id="b4486-106">`dotnet list package` - Lists the package references for a project or solution.</span></span>

## <a name="synopsis"></a><span data-ttu-id="b4486-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="b4486-107">Synopsis</span></span>

```dotnetcli
dotnet list [<PROJECT>|<SOLUTION>] package [--config] [--framework] [--highest-minor] [--highest-patch]
   [--include-prerelease] [--include-transitive] [--interactive] [--outdated] [--source]
dotnet list package [-h|--help]
```

## <a name="description"></a><span data-ttu-id="b4486-108">Description</span><span class="sxs-lookup"><span data-stu-id="b4486-108">Description</span></span>

<span data-ttu-id="b4486-109">El comando `dotnet list package` ofrece una opción práctica para mostrar todas las referencias de paquete de NuGet de una solución o un proyecto específico.</span><span class="sxs-lookup"><span data-stu-id="b4486-109">The `dotnet list package` command provides a convenient option to list all NuGet package references for a specific project or a solution.</span></span> <span data-ttu-id="b4486-110">Primero deberá crear el proyecto para tener los recursos necesarios para que este comando se procese.</span><span class="sxs-lookup"><span data-stu-id="b4486-110">You first need to build the project in order to have the assets needed for this command to process.</span></span> <span data-ttu-id="b4486-111">En el ejemplo siguiente se muestra la salida del comando `dotnet list package` para el proyecto [SentimentAnalysis](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis):</span><span class="sxs-lookup"><span data-stu-id="b4486-111">The following example shows the output of the `dotnet list package` command for the [SentimentAnalysis](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) project:</span></span>

```output
Project 'SentimentAnalysis' has the following package references
   [netcoreapp2.1]:
   Top-level Package               Requested   Resolved
   > Microsoft.ML                  1.4.0       1.4.0
   > Microsoft.NETCore.App   (A)   [2.1.0, )   2.1.0

(A) : Auto-referenced package.
```

<span data-ttu-id="b4486-112">La columna **Requested** hace referencia a la versión de paquete especificada en el archivo del proyecto y puede ser un intervalo.</span><span class="sxs-lookup"><span data-stu-id="b4486-112">The **Requested** column refers to the package version specified in the project file and can be a range.</span></span> <span data-ttu-id="b4486-113">La columna **Resolved** muestra la versión que el proyecto usa actualmente y siempre se trata de un valor único.</span><span class="sxs-lookup"><span data-stu-id="b4486-113">The **Resolved** column lists the version that the project is currently using and is always a single value.</span></span> <span data-ttu-id="b4486-114">Los paquetes que tienen `(A)` junto al nombre representan [referencias implícitas de paquete](csproj.md#implicit-package-references) que se deducen de la configuración del proyecto (tipo de `Sdk`, propiedad `<TargetFramework>` o `<TargetFrameworks>`, etc.).</span><span class="sxs-lookup"><span data-stu-id="b4486-114">The packages displaying an `(A)` right next to their names represent [implicit package references](csproj.md#implicit-package-references) that are inferred from your project settings (`Sdk` type, `<TargetFramework>` or `<TargetFrameworks>` property, etc.)</span></span>

<span data-ttu-id="b4486-115">Use la opción `--outdated` para averiguar si hay disponibles más recientes de los paquetes que usa en los proyectos.</span><span class="sxs-lookup"><span data-stu-id="b4486-115">Use the `--outdated` option to find out if there are newer versions available of the packages you're using in your projects.</span></span> <span data-ttu-id="b4486-116">De manera predeterminada, `--outdated` muestra los paquetes estables más recientes, a menos que la versión resuelta también sea una versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="b4486-116">By default, `--outdated` lists the latest stable packages unless the resolved version is also a prerelease version.</span></span> <span data-ttu-id="b4486-117">Para incluir versiones preliminares cuando se muestren versiones más recientes, especifique también la opción `--include-prerelease`.</span><span class="sxs-lookup"><span data-stu-id="b4486-117">To include prerelease versions when listing newer versions, also specify the `--include-prerelease` option.</span></span> <span data-ttu-id="b4486-118">En los ejemplos siguientes se muestra la salida del comando `dotnet list package --outdated --include-prerelease` para el mismo proyecto, tal como en el ejemplo anterior:</span><span class="sxs-lookup"><span data-stu-id="b4486-118">The following examples shows the output of the `dotnet list package --outdated --include-prerelease` command for the same project as the previous example:</span></span>

```output
The following sources were used:
   https://api.nuget.org/v3/index.json
   C:\Program Files (x86)\Microsoft SDKs\NuGetPackages\

Project `SentimentAnalysis` has the following updates to its packages
   [netcoreapp2.1]:
   Top-level Package      Requested   Resolved   Latest
   > Microsoft.ML         1.4.0       1.4.0      1.5.0-preview
```

<span data-ttu-id="b4486-119">Si tiene que averiguar si el proyecto tiene dependencias transitivas, use la opción `--include-transitive`.</span><span class="sxs-lookup"><span data-stu-id="b4486-119">If you need to find out whether your project has transitive dependencies, use the `--include-transitive` option.</span></span> <span data-ttu-id="b4486-120">Las dependencias transitivas se producen cuando se agrega un paquete al proyecto que, a su vez, se basa en otro paquete.</span><span class="sxs-lookup"><span data-stu-id="b4486-120">Transitive dependencies occur when you add a package to your project that in turn relies on another package.</span></span> <span data-ttu-id="b4486-121">En el ejemplo siguiente se muestra la salida de la ejecución del comando `dotnet list package --include-transitive` en el proyecto [HelloPlugin](https://github.com/dotnet/samples/tree/master/core/extensions/AppWithPlugin/HelloPlugin), que muestra paquetes de nivel superior y los paquetes de los que dependen:</span><span class="sxs-lookup"><span data-stu-id="b4486-121">The following example shows the output from running the `dotnet list package --include-transitive` command for the [HelloPlugin](https://github.com/dotnet/samples/tree/master/core/extensions/AppWithPlugin/HelloPlugin) project, which displays top-level packages and the packages they depend on:</span></span>

```output
Project 'HelloPlugin' has the following package references
   [netcoreapp3.0]:
   Transitive Package      Resolved
   > PluginBase            1.0.0
```

## <a name="arguments"></a><span data-ttu-id="b4486-122">Argumentos</span><span class="sxs-lookup"><span data-stu-id="b4486-122">Arguments</span></span>

`PROJECT | SOLUTION`

<span data-ttu-id="b4486-123">El archivo de proyecto o solución donde se operará.</span><span class="sxs-lookup"><span data-stu-id="b4486-123">The project or solution file to operate on.</span></span> <span data-ttu-id="b4486-124">Si no se especifica, el comando busca uno en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="b4486-124">If not specified, the command searches the current directory for one.</span></span> <span data-ttu-id="b4486-125">Si se encuentra más de una solución o proyecto, se genera un error.</span><span class="sxs-lookup"><span data-stu-id="b4486-125">If more than one solution or project is found, an error is thrown.</span></span>

## <a name="options"></a><span data-ttu-id="b4486-126">Opciones</span><span class="sxs-lookup"><span data-stu-id="b4486-126">Options</span></span>

- **`--config <SOURCE>`**

  <span data-ttu-id="b4486-127">Los orígenes de NuGet que se usarán al buscar paquetes más recientes.</span><span class="sxs-lookup"><span data-stu-id="b4486-127">The NuGet sources to use when searching for newer packages.</span></span> <span data-ttu-id="b4486-128">Requiere la opción `--outdated`.</span><span class="sxs-lookup"><span data-stu-id="b4486-128">Requires the `--outdated` option.</span></span>

- **`--framework <FRAMEWORK>`**

  <span data-ttu-id="b4486-129">Muestra solo los paquetes aplicables al [marco de destino](../../standard/frameworks.md) especificado.</span><span class="sxs-lookup"><span data-stu-id="b4486-129">Displays only the packages applicable for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="b4486-130">Para especificar varios marcos, repita la opción varias veces.</span><span class="sxs-lookup"><span data-stu-id="b4486-130">To specify multiple frameworks, repeat the option multiple times.</span></span> <span data-ttu-id="b4486-131">Por ejemplo: `--framework netcoreapp2.2 --framework netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="b4486-131">For example: `--framework netcoreapp2.2 --framework netstandard2.0`.</span></span>

- **`-h|--help`**

  <span data-ttu-id="b4486-132">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="b4486-132">Prints out a short help for the command.</span></span>

- **`--highest-minor`**

  <span data-ttu-id="b4486-133">Considere solo los paquetes con un número de versión principal coincidente al buscar paquetes más recientes.</span><span class="sxs-lookup"><span data-stu-id="b4486-133">Considers only the packages with a matching major version number when searching for newer packages.</span></span> <span data-ttu-id="b4486-134">Requiere la opción `--outdated`.</span><span class="sxs-lookup"><span data-stu-id="b4486-134">Requires the `--outdated` option.</span></span>

- **`--highest-patch`**

  <span data-ttu-id="b4486-135">Considere solo los paquetes con número de versión principal y secundario coincidente al buscar paquetes más recientes.</span><span class="sxs-lookup"><span data-stu-id="b4486-135">Considers only the packages with a matching major and minor version numbers when searching for newer packages.</span></span> <span data-ttu-id="b4486-136">Requiere la opción `--outdated`.</span><span class="sxs-lookup"><span data-stu-id="b4486-136">Requires the `--outdated` option.</span></span>

- **`--include-prerelease`**

  <span data-ttu-id="b4486-137">Considere los paquetes con versiones preliminares al buscar paquetes más recientes.</span><span class="sxs-lookup"><span data-stu-id="b4486-137">Considers packages with prerelease versions when searching for newer packages.</span></span> <span data-ttu-id="b4486-138">Requiere la opción `--outdated`.</span><span class="sxs-lookup"><span data-stu-id="b4486-138">Requires the `--outdated` option.</span></span>

- **`--include-transitive`**

  <span data-ttu-id="b4486-139">Enumera los paquetes transitivos, además de los paquetes de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="b4486-139">Lists transitive packages, in addition to the top-level packages.</span></span> <span data-ttu-id="b4486-140">Al especificar esta opción, recibe una lista de paquetes de los que dependen los paquetes de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="b4486-140">When specifying this option, you get a list of packages that the top-level packages depend on.</span></span>

- **`--interactive`**

  <span data-ttu-id="b4486-141">Permite que el comando se detenga y espere una entrada o una acción del usuario.</span><span class="sxs-lookup"><span data-stu-id="b4486-141">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="b4486-142">Por ejemplo, para completar la autenticación.</span><span class="sxs-lookup"><span data-stu-id="b4486-142">For example, to complete authentication.</span></span> <span data-ttu-id="b4486-143">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="b4486-143">Available since .NET Core 3.0 SDK.</span></span>

- **`--outdated`**

  <span data-ttu-id="b4486-144">Enumera los paquetes con versiones más recientes disponibles.</span><span class="sxs-lookup"><span data-stu-id="b4486-144">Lists packages that have newer versions available.</span></span>

- **`-s|--source <SOURCE>`**

  <span data-ttu-id="b4486-145">Los orígenes de NuGet que se usarán al buscar paquetes más recientes.</span><span class="sxs-lookup"><span data-stu-id="b4486-145">The NuGet sources to use when searching for newer packages.</span></span> <span data-ttu-id="b4486-146">Requiere la opción `--outdated`.</span><span class="sxs-lookup"><span data-stu-id="b4486-146">Requires the `--outdated` option.</span></span>

## <a name="examples"></a><span data-ttu-id="b4486-147">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="b4486-147">Examples</span></span>

- <span data-ttu-id="b4486-148">Muestre las referencias de paquete de un proyecto específico:</span><span class="sxs-lookup"><span data-stu-id="b4486-148">List package references of a specific project:</span></span>

  ```dotnetcli
  dotnet list SentimentAnalysis.csproj package
  ```

- <span data-ttu-id="b4486-149">Muestre las referencias de paquete que tienen versiones más recientes disponibles, incluidas versiones preliminares:</span><span class="sxs-lookup"><span data-stu-id="b4486-149">List package references that have newer versions available, including prerelease versions:</span></span>

  ```dotnetcli
  dotnet list package --outdated --include-prerelease
  ```

- <span data-ttu-id="b4486-150">Muestre las referencias de paquete para un marco de destino específico:</span><span class="sxs-lookup"><span data-stu-id="b4486-150">List package references for a specific target framework:</span></span>

  ```dotnetcli
  dotnet list package --framework netcoreapp3.0
  ```
