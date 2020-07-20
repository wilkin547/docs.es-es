---
title: CLI de .NET Core
titleSuffix: ''
description: Información general de la CLI de .NET Core y sus características.
ms.date: 02/13/2020
ms.openlocfilehash: f92151c85b4816fef1859e84ad94945445db1854
ms.sourcegitcommit: 3492dafceb5d4183b6b0d2f3bdf4a1abc4d5ed8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/16/2020
ms.locfileid: "86415967"
---
# <a name="net-core-cli-overview"></a><span data-ttu-id="bea44-103">Información general sobre la CLI de .NET Core</span><span class="sxs-lookup"><span data-stu-id="bea44-103">.NET Core CLI overview</span></span>

<span data-ttu-id="bea44-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.1 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="bea44-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

<span data-ttu-id="bea44-105">La interfaz de la línea de comandos (CLI) de .NET Core es una cadena de herramientas multiplataforma para desarrollar, compilar, ejecutar y publicar aplicaciones .NET Core.</span><span class="sxs-lookup"><span data-stu-id="bea44-105">The .NET Core command-line interface (CLI) is a cross-platform toolchain for developing, building, running, and publishing .NET Core applications.</span></span>

<span data-ttu-id="bea44-106">La CLI de .NET Core se incluye con el [SDK de .NET Core](../sdk.md).</span><span class="sxs-lookup"><span data-stu-id="bea44-106">The .NET Core CLI is included with the [.NET Core SDK](../sdk.md).</span></span> <span data-ttu-id="bea44-107">Para más información sobre cómo instalar el SDK de .NET Core, consulte [Instalación de .NET Core](../install/windows.md).</span><span class="sxs-lookup"><span data-stu-id="bea44-107">To learn how to install the .NET Core SDK, see [Install .NET Core](../install/windows.md).</span></span>

## <a name="cli-commands"></a><span data-ttu-id="bea44-108">Comandos de la CLI</span><span class="sxs-lookup"><span data-stu-id="bea44-108">CLI commands</span></span>

<span data-ttu-id="bea44-109">De forma predeterminada, se instalan los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="bea44-109">The following commands are installed by default:</span></span>

### <a name="basic-commands"></a><span data-ttu-id="bea44-110">Comandos básicos</span><span class="sxs-lookup"><span data-stu-id="bea44-110">Basic commands</span></span>

- [`new`](dotnet-new.md)
- [`restore`](dotnet-restore.md)
- [`build`](dotnet-build.md)
- [`publish`](dotnet-publish.md)
- [`run`](dotnet-run.md)
- [`test`](dotnet-test.md)
- [`vstest`](dotnet-vstest.md)
- [`pack`](dotnet-pack.md)
- [`migrate`](dotnet-migrate.md)
- [`clean`](dotnet-clean.md)
- [`sln`](dotnet-sln.md)
- [`help`](dotnet-help.md)
- [`store`](dotnet-store.md)

### <a name="project-modification-commands"></a><span data-ttu-id="bea44-111">Comandos de modificación del proyecto</span><span class="sxs-lookup"><span data-stu-id="bea44-111">Project modification commands</span></span>

- [`add package`](dotnet-add-package.md)
- [`add reference`](dotnet-add-reference.md)
- [`remove package`](dotnet-remove-package.md)
- [`remove reference`](dotnet-remove-reference.md)
- [`list reference`](dotnet-list-reference.md)

### <a name="advanced-commands"></a><span data-ttu-id="bea44-112">Comandos avanzados</span><span class="sxs-lookup"><span data-stu-id="bea44-112">Advanced commands</span></span>

- [`nuget delete`](dotnet-nuget-delete.md)
- [`nuget locals`](dotnet-nuget-locals.md)
- [`nuget push`](dotnet-nuget-push.md)
- [`msbuild`](dotnet-msbuild.md)
- [`dotnet install script`](dotnet-install-script.md)

### <a name="tool-management-commands"></a><span data-ttu-id="bea44-113">Comandos de administración de herramientas</span><span class="sxs-lookup"><span data-stu-id="bea44-113">Tool management commands</span></span>

- [`tool install`](dotnet-tool-install.md)
- [`tool list`](dotnet-tool-list.md)
- [`tool update`](dotnet-tool-update.md)
- <span data-ttu-id="bea44-114">[`tool restore`](global-tools.md#install-a-local-tool) Disponible a partir del SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="bea44-114">[`tool restore`](global-tools.md#install-a-local-tool) Available since .NET Core SDK 3.0.</span></span>
- <span data-ttu-id="bea44-115">[`tool run`](global-tools.md#invoke-a-local-tool) Disponible a partir del SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="bea44-115">[`tool run`](global-tools.md#invoke-a-local-tool) Available since .NET Core SDK 3.0.</span></span>
- [`tool uninstall`](dotnet-tool-uninstall.md)

<span data-ttu-id="bea44-116">Las herramientas son aplicaciones de consola que se instalan mediante paquetes NuGet y se invocan desde el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="bea44-116">Tools are console applications that are installed from NuGet packages and are invoked from the command prompt.</span></span> <span data-ttu-id="bea44-117">Puede encargarse de escribir las herramientas o instalar las escritas por terceros.</span><span class="sxs-lookup"><span data-stu-id="bea44-117">You can write tools yourself or install tools written by third parties.</span></span> <span data-ttu-id="bea44-118">Las herramientas también se denominan herramientas globales, herramientas de ruta de acceso de herramientas y herramientas locales.</span><span class="sxs-lookup"><span data-stu-id="bea44-118">Tools are also known as global tools, tool-path tools, and local tools.</span></span> <span data-ttu-id="bea44-119">Para obtener más información, vea [Información general sobre las herramientas de .NET Core](global-tools.md).</span><span class="sxs-lookup"><span data-stu-id="bea44-119">For more information, see [.NET Core tools overview](global-tools.md).</span></span>

## <a name="command-structure"></a><span data-ttu-id="bea44-120">Estructura de comandos</span><span class="sxs-lookup"><span data-stu-id="bea44-120">Command structure</span></span>

<span data-ttu-id="bea44-121">La estructura de comandos de la CLI consta del [controlador ("dotnet")](#driver), [el comando](#command) y posiblemente de los [argumentos de comandos](#arguments) y otras [opciones](#options).</span><span class="sxs-lookup"><span data-stu-id="bea44-121">CLI command structure consists of [the driver ("dotnet")](#driver), [the command](#command), and possibly command [arguments](#arguments) and [options](#options).</span></span> <span data-ttu-id="bea44-122">Este patrón se puede ver en la mayoría de las operaciones de la CLI, como la creación de una nueva aplicación de consola y su ejecución desde la línea de comandos, como muestran los siguientes comandos cuando se ejecutan desde un directorio denominado *my_app*:</span><span class="sxs-lookup"><span data-stu-id="bea44-122">You see this pattern in most CLI operations, such as creating a new console app and running it from the command line as the following commands show when executed from a directory named *my_app*:</span></span>

```dotnetcli
dotnet new console
dotnet build --output /build_output
dotnet /build_output/my_app.dll
```

### <a name="driver"></a><span data-ttu-id="bea44-123">Controlador</span><span class="sxs-lookup"><span data-stu-id="bea44-123">Driver</span></span>

<span data-ttu-id="bea44-124">El controlador se denomina [dotnet](dotnet.md) y tiene dos responsabilidades, ejecutar una [aplicación dependiente del marco](../deploying/index.md) o ejecutar un comando.</span><span class="sxs-lookup"><span data-stu-id="bea44-124">The driver is named [dotnet](dotnet.md) and has two responsibilities, either running a [framework-dependent app](../deploying/index.md) or executing a command.</span></span>

<span data-ttu-id="bea44-125">Para ejecutar una aplicación dependiente del marco, especifique la aplicación después del controlador, por ejemplo, `dotnet /path/to/my_app.dll`.</span><span class="sxs-lookup"><span data-stu-id="bea44-125">To run a framework-dependent app, specify the app after the driver, for example, `dotnet /path/to/my_app.dll`.</span></span> <span data-ttu-id="bea44-126">Cuando ejecute el comando desde la carpeta donde reside la DLL de la aplicación, simplemente ejecute `dotnet my_app.dll`.</span><span class="sxs-lookup"><span data-stu-id="bea44-126">When executing the command from the folder where the app's DLL resides, simply execute `dotnet my_app.dll`.</span></span> <span data-ttu-id="bea44-127">Si quiere usar una versión específica del entorno de ejecución .NET Core, use la opción `--fx-version <VERSION>` (consulte la referencia del [comando dotnet](dotnet.md)).</span><span class="sxs-lookup"><span data-stu-id="bea44-127">If you want to use a specific version of the .NET Core Runtime, use the `--fx-version <VERSION>` option (see the [dotnet command](dotnet.md) reference).</span></span>

<span data-ttu-id="bea44-128">Cuando se proporciona un comando para el controlador, `dotnet.exe` inicia el proceso de ejecución del comando de la CLI.</span><span class="sxs-lookup"><span data-stu-id="bea44-128">When you supply a command to the driver, `dotnet.exe` starts the CLI command execution process.</span></span> <span data-ttu-id="bea44-129">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bea44-129">For example:</span></span>

```dotnetcli
dotnet build
```

<span data-ttu-id="bea44-130">En primer lugar, el controlador determina la versión de SDK que se debe usar.</span><span class="sxs-lookup"><span data-stu-id="bea44-130">First, the driver determines the version of the SDK to use.</span></span> <span data-ttu-id="bea44-131">Si no hay ningún archivo [global.json](global-json.md), se usa la última versión del SDK disponible.</span><span class="sxs-lookup"><span data-stu-id="bea44-131">If there is no [global.json](global-json.md) file, the latest version of the SDK available is used.</span></span> <span data-ttu-id="bea44-132">Podría tratarse de una versión preliminar o de una versión estable, en función de lo último que esté disponible en el equipo.</span><span class="sxs-lookup"><span data-stu-id="bea44-132">This might be either a preview or stable version, depending on what is latest on the machine.</span></span>  <span data-ttu-id="bea44-133">Una vez determinada la versión del SDK, se ejecutará el comando.</span><span class="sxs-lookup"><span data-stu-id="bea44-133">Once the SDK version is determined, it executes the command.</span></span>

### <a name="command"></a><span data-ttu-id="bea44-134">Comando</span><span class="sxs-lookup"><span data-stu-id="bea44-134">Command</span></span>

<span data-ttu-id="bea44-135">El comando realiza una acción.</span><span class="sxs-lookup"><span data-stu-id="bea44-135">The command performs an action.</span></span> <span data-ttu-id="bea44-136">Por ejemplo, `dotnet build` compila código.</span><span class="sxs-lookup"><span data-stu-id="bea44-136">For example, `dotnet build` builds code.</span></span> <span data-ttu-id="bea44-137">`dotnet publish` publica el código.</span><span class="sxs-lookup"><span data-stu-id="bea44-137">`dotnet publish` publishes code.</span></span> <span data-ttu-id="bea44-138">Los comandos se implementan como una aplicación de consola usando una convención `dotnet {command}`.</span><span class="sxs-lookup"><span data-stu-id="bea44-138">The commands are implemented as a console application using a `dotnet {command}` convention.</span></span>

### <a name="arguments"></a><span data-ttu-id="bea44-139">Argumentos</span><span class="sxs-lookup"><span data-stu-id="bea44-139">Arguments</span></span>

<span data-ttu-id="bea44-140">Los argumentos que se pasan en la línea de comandos son los argumentos para el comando invocado.</span><span class="sxs-lookup"><span data-stu-id="bea44-140">The arguments you pass on the command line are the arguments to the command invoked.</span></span> <span data-ttu-id="bea44-141">Por ejemplo, cuando ejecuta `dotnet publish my_app.csproj`, el argumento `my_app.csproj` indica el proyecto que se publicará y se pasa al comando `publish`.</span><span class="sxs-lookup"><span data-stu-id="bea44-141">For example, when you execute `dotnet publish my_app.csproj`, the `my_app.csproj` argument indicates the project to publish and is passed to the `publish` command.</span></span>

### <a name="options"></a><span data-ttu-id="bea44-142">Opciones</span><span class="sxs-lookup"><span data-stu-id="bea44-142">Options</span></span>

<span data-ttu-id="bea44-143">Las opciones que se pasan en la línea de comandos son las opciones para el comando que se invoca.</span><span class="sxs-lookup"><span data-stu-id="bea44-143">The options you pass on the command line are the options to the command invoked.</span></span> <span data-ttu-id="bea44-144">Por ejemplo, cuando ejecuta `dotnet publish --output /build_output`, la opción `--output` y su valor se pasan al comando `publish`.</span><span class="sxs-lookup"><span data-stu-id="bea44-144">For example, when you execute `dotnet publish --output /build_output`, the `--output` option and its value are passed to the `publish` command.</span></span>

## <a name="see-also"></a><span data-ttu-id="bea44-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="bea44-145">See also</span></span>

- [<span data-ttu-id="bea44-146">Repositorio de GitHub dotnet/sdk</span><span class="sxs-lookup"><span data-stu-id="bea44-146">dotnet/sdk GitHub repository</span></span>](https://github.com/dotnet/sdk/)
- <span data-ttu-id="bea44-147">[.NET Core installation guide](../install/windows.md) (Guía de instalación de .NET Core)</span><span class="sxs-lookup"><span data-stu-id="bea44-147">[.NET Core installation guide](../install/windows.md)</span></span>
