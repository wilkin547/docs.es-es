---
title: CLI de .NET Core
titleSuffix: ''
description: Información general de la CLI de .NET Core y sus características.
ms.date: 02/13/2020
ms.openlocfilehash: d84f96889cabc3fb4521e39db25050aacdd11546
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "78156717"
---
# <a name="net-core-cli-overview"></a><span data-ttu-id="68a88-103">Información general sobre la CLI de .NET Core</span><span class="sxs-lookup"><span data-stu-id="68a88-103">.NET Core CLI overview</span></span>

<span data-ttu-id="68a88-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.1 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="68a88-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

<span data-ttu-id="68a88-105">La interfaz de la línea de comandos (CLI) de .NET Core es una cadena de herramientas multiplataforma para desarrollar, compilar, ejecutar y publicar aplicaciones .NET Core.</span><span class="sxs-lookup"><span data-stu-id="68a88-105">The .NET Core command-line interface (CLI) is a cross-platform toolchain for developing, building, running, and publishing .NET Core applications.</span></span>

<span data-ttu-id="68a88-106">La CLI de .NET Core se incluye con el [SDK de .NET Core](../sdk.md).</span><span class="sxs-lookup"><span data-stu-id="68a88-106">The .NET Core CLI is included with the [.NET Core SDK](../sdk.md).</span></span> <span data-ttu-id="68a88-107">Para más información sobre cómo instalar el SDK de .NET Core, consulte [Instalación del SDK de .NET Core](../install/sdk.md).</span><span class="sxs-lookup"><span data-stu-id="68a88-107">To learn how to install the .NET Core SDK, see [Install the .NET Core SDK](../install/sdk.md).</span></span>

## <a name="cli-commands"></a><span data-ttu-id="68a88-108">Comandos de la CLI</span><span class="sxs-lookup"><span data-stu-id="68a88-108">CLI commands</span></span>

<span data-ttu-id="68a88-109">De forma predeterminada, se instalan los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="68a88-109">The following commands are installed by default:</span></span>

### <a name="basic-commands"></a><span data-ttu-id="68a88-110">Comandos básicos</span><span class="sxs-lookup"><span data-stu-id="68a88-110">Basic commands</span></span>

- [<span data-ttu-id="68a88-111">new</span><span class="sxs-lookup"><span data-stu-id="68a88-111">new</span></span>](dotnet-new.md)
- [<span data-ttu-id="68a88-112">restore</span><span class="sxs-lookup"><span data-stu-id="68a88-112">restore</span></span>](dotnet-restore.md)
- [<span data-ttu-id="68a88-113">build</span><span class="sxs-lookup"><span data-stu-id="68a88-113">build</span></span>](dotnet-build.md)
- [<span data-ttu-id="68a88-114">publish</span><span class="sxs-lookup"><span data-stu-id="68a88-114">publish</span></span>](dotnet-publish.md)
- [<span data-ttu-id="68a88-115">run</span><span class="sxs-lookup"><span data-stu-id="68a88-115">run</span></span>](dotnet-run.md)
- [<span data-ttu-id="68a88-116">test</span><span class="sxs-lookup"><span data-stu-id="68a88-116">test</span></span>](dotnet-test.md)
- [<span data-ttu-id="68a88-117">vstest</span><span class="sxs-lookup"><span data-stu-id="68a88-117">vstest</span></span>](dotnet-vstest.md)
- [<span data-ttu-id="68a88-118">pack</span><span class="sxs-lookup"><span data-stu-id="68a88-118">pack</span></span>](dotnet-pack.md)
- [<span data-ttu-id="68a88-119">migrate</span><span class="sxs-lookup"><span data-stu-id="68a88-119">migrate</span></span>](dotnet-migrate.md)
- [<span data-ttu-id="68a88-120">clean</span><span class="sxs-lookup"><span data-stu-id="68a88-120">clean</span></span>](dotnet-clean.md)
- [<span data-ttu-id="68a88-121">sln</span><span class="sxs-lookup"><span data-stu-id="68a88-121">sln</span></span>](dotnet-sln.md)
- [<span data-ttu-id="68a88-122">help</span><span class="sxs-lookup"><span data-stu-id="68a88-122">help</span></span>](dotnet-help.md)
- [<span data-ttu-id="68a88-123">store</span><span class="sxs-lookup"><span data-stu-id="68a88-123">store</span></span>](dotnet-store.md)

### <a name="project-modification-commands"></a><span data-ttu-id="68a88-124">Comandos de modificación del proyecto</span><span class="sxs-lookup"><span data-stu-id="68a88-124">Project modification commands</span></span>

- [<span data-ttu-id="68a88-125">add package</span><span class="sxs-lookup"><span data-stu-id="68a88-125">add package</span></span>](dotnet-add-package.md)
- [<span data-ttu-id="68a88-126">add reference</span><span class="sxs-lookup"><span data-stu-id="68a88-126">add reference</span></span>](dotnet-add-reference.md)
- [<span data-ttu-id="68a88-127">remove package</span><span class="sxs-lookup"><span data-stu-id="68a88-127">remove package</span></span>](dotnet-remove-package.md)
- [<span data-ttu-id="68a88-128">remove reference</span><span class="sxs-lookup"><span data-stu-id="68a88-128">remove reference</span></span>](dotnet-remove-reference.md)
- [<span data-ttu-id="68a88-129">list reference</span><span class="sxs-lookup"><span data-stu-id="68a88-129">list reference</span></span>](dotnet-list-reference.md)

### <a name="advanced-commands"></a><span data-ttu-id="68a88-130">Comandos avanzados</span><span class="sxs-lookup"><span data-stu-id="68a88-130">Advanced commands</span></span>

- [<span data-ttu-id="68a88-131">nuget delete</span><span class="sxs-lookup"><span data-stu-id="68a88-131">nuget delete</span></span>](dotnet-nuget-delete.md)
- [<span data-ttu-id="68a88-132">nuget locals</span><span class="sxs-lookup"><span data-stu-id="68a88-132">nuget locals</span></span>](dotnet-nuget-locals.md)
- [<span data-ttu-id="68a88-133">nuget push</span><span class="sxs-lookup"><span data-stu-id="68a88-133">nuget push</span></span>](dotnet-nuget-push.md)
- [<span data-ttu-id="68a88-134">msbuild</span><span class="sxs-lookup"><span data-stu-id="68a88-134">msbuild</span></span>](dotnet-msbuild.md)
- [<span data-ttu-id="68a88-135">dotnet install script</span><span class="sxs-lookup"><span data-stu-id="68a88-135">dotnet install script</span></span>](dotnet-install-script.md)

### <a name="tool-management-commands"></a><span data-ttu-id="68a88-136">Comandos de administración de herramientas</span><span class="sxs-lookup"><span data-stu-id="68a88-136">Tool management commands</span></span>

- [<span data-ttu-id="68a88-137">tool install</span><span class="sxs-lookup"><span data-stu-id="68a88-137">tool install</span></span>](dotnet-tool-install.md)
- [<span data-ttu-id="68a88-138">tool list</span><span class="sxs-lookup"><span data-stu-id="68a88-138">tool list</span></span>](dotnet-tool-list.md)
- [<span data-ttu-id="68a88-139">tool update</span><span class="sxs-lookup"><span data-stu-id="68a88-139">tool update</span></span>](dotnet-tool-update.md)
- <span data-ttu-id="68a88-140">[tool restore](global-tools.md#install-a-local-tool) **Disponible a partir del SDK de .NET Core 3.0**</span><span class="sxs-lookup"><span data-stu-id="68a88-140">[tool restore](global-tools.md#install-a-local-tool) **Available starting with .NET Core SDK 3.0**</span></span>
- <span data-ttu-id="68a88-141">[tool run](global-tools.md#invoke-a-local-tool) **Disponible a partir del SDK de .NET Core 3.0**</span><span class="sxs-lookup"><span data-stu-id="68a88-141">[tool run](global-tools.md#invoke-a-local-tool) **Available starting with .NET Core SDK 3.0**</span></span>
- [<span data-ttu-id="68a88-142">tool uninstall</span><span class="sxs-lookup"><span data-stu-id="68a88-142">tool uninstall</span></span>](dotnet-tool-uninstall.md)

<span data-ttu-id="68a88-143">Las herramientas son aplicaciones de consola que se instalan mediante paquetes de NuGet y se invocan desde el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="68a88-143">Tools are console applications that are installed from NuGet packages and are invoked from the command prompt.</span></span> <span data-ttu-id="68a88-144">Puede encargarse de escribir las herramientas o instalar las escritas por terceros.</span><span class="sxs-lookup"><span data-stu-id="68a88-144">You can write tools yourself or install tools written by third parties.</span></span> <span data-ttu-id="68a88-145">Las herramientas también se denominan herramientas globales, herramientas de ruta de acceso de herramientas y herramientas locales.</span><span class="sxs-lookup"><span data-stu-id="68a88-145">Tools are also known as global tools, tool-path tools, and local tools.</span></span> <span data-ttu-id="68a88-146">Para obtener más información, vea [Información general sobre las herramientas de .NET Core](global-tools.md).</span><span class="sxs-lookup"><span data-stu-id="68a88-146">For more information, see [.NET Core tools overview](global-tools.md).</span></span>

## <a name="command-structure"></a><span data-ttu-id="68a88-147">Estructura de comandos</span><span class="sxs-lookup"><span data-stu-id="68a88-147">Command structure</span></span>

<span data-ttu-id="68a88-148">La estructura de comandos de la CLI consta del [controlador ("dotnet")](#driver), [el comando](#command) y posiblemente de los [argumentos de comandos](#arguments) y otras [opciones](#options).</span><span class="sxs-lookup"><span data-stu-id="68a88-148">CLI command structure consists of [the driver ("dotnet")](#driver), [the command](#command), and possibly command [arguments](#arguments) and [options](#options).</span></span> <span data-ttu-id="68a88-149">Este patrón se puede ver en la mayoría de las operaciones de la CLI, como la creación de una nueva aplicación de consola y su ejecución desde la línea de comandos, como muestran los siguientes comandos cuando se ejecutan desde un directorio denominado *my_app* :</span><span class="sxs-lookup"><span data-stu-id="68a88-149">You see this pattern in most CLI operations, such as creating a new console app and running it from the command line as the following commands show when executed from a directory named *my_app*:</span></span>

```dotnetcli
dotnet new console
dotnet build --output /build_output
dotnet /build_output/my_app.dll
```

### <a name="driver"></a><span data-ttu-id="68a88-150">Controlador</span><span class="sxs-lookup"><span data-stu-id="68a88-150">Driver</span></span>

<span data-ttu-id="68a88-151">El controlador se denomina [dotnet](dotnet.md) y tiene dos responsabilidades, ejecutar una [aplicación dependiente del marco](../deploying/index.md) o ejecutar un comando.</span><span class="sxs-lookup"><span data-stu-id="68a88-151">The driver is named [dotnet](dotnet.md) and has two responsibilities, either running a [framework-dependent app](../deploying/index.md) or executing a command.</span></span>

<span data-ttu-id="68a88-152">Para ejecutar una aplicación dependiente del marco, especifique la aplicación después del controlador, por ejemplo, `dotnet /path/to/my_app.dll`.</span><span class="sxs-lookup"><span data-stu-id="68a88-152">To run a framework-dependent app, specify the app after the driver, for example, `dotnet /path/to/my_app.dll`.</span></span> <span data-ttu-id="68a88-153">Cuando ejecute el comando desde la carpeta donde reside la DLL de la aplicación, simplemente ejecute `dotnet my_app.dll`.</span><span class="sxs-lookup"><span data-stu-id="68a88-153">When executing the command from the folder where the app's DLL resides, simply execute `dotnet my_app.dll`.</span></span> <span data-ttu-id="68a88-154">Si quiere usar una versión específica del entorno de ejecución .NET Core, use la opción `--fx-version <VERSION>` (consulte la referencia del [comando dotnet](dotnet.md)).</span><span class="sxs-lookup"><span data-stu-id="68a88-154">If you want to use a specific version of the .NET Core Runtime, use the `--fx-version <VERSION>` option (see the [dotnet command](dotnet.md) reference).</span></span>

<span data-ttu-id="68a88-155">Cuando se proporciona un comando para el controlador, `dotnet.exe` inicia el proceso de ejecución del comando de la CLI.</span><span class="sxs-lookup"><span data-stu-id="68a88-155">When you supply a command to the driver, `dotnet.exe` starts the CLI command execution process.</span></span> <span data-ttu-id="68a88-156">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="68a88-156">For example:</span></span>

```dotnetcli
dotnet build
```

<span data-ttu-id="68a88-157">En primer lugar, el controlador determina la versión de SDK que se debe usar.</span><span class="sxs-lookup"><span data-stu-id="68a88-157">First, the driver determines the version of the SDK to use.</span></span> <span data-ttu-id="68a88-158">Si no hay ningún archivo [global.json](global-json.md), se usa la última versión del SDK disponible.</span><span class="sxs-lookup"><span data-stu-id="68a88-158">If there is no [global.json](global-json.md) file, the latest version of the SDK available is used.</span></span> <span data-ttu-id="68a88-159">Podría tratarse de una versión preliminar o de una versión estable, en función de lo último que esté disponible en el equipo.</span><span class="sxs-lookup"><span data-stu-id="68a88-159">This might be either a preview or stable version, depending on what is latest on the machine.</span></span>  <span data-ttu-id="68a88-160">Una vez determinada la versión del SDK, se ejecutará el comando.</span><span class="sxs-lookup"><span data-stu-id="68a88-160">Once the SDK version is determined, it executes the command.</span></span>

### <a name="command"></a><span data-ttu-id="68a88-161">Comando</span><span class="sxs-lookup"><span data-stu-id="68a88-161">Command</span></span>

<span data-ttu-id="68a88-162">El comando realiza una acción.</span><span class="sxs-lookup"><span data-stu-id="68a88-162">The command performs an action.</span></span> <span data-ttu-id="68a88-163">Por ejemplo, `dotnet build` compila código.</span><span class="sxs-lookup"><span data-stu-id="68a88-163">For example, `dotnet build` builds code.</span></span> <span data-ttu-id="68a88-164">`dotnet publish` publica el código.</span><span class="sxs-lookup"><span data-stu-id="68a88-164">`dotnet publish` publishes code.</span></span> <span data-ttu-id="68a88-165">Los comandos se implementan como una aplicación de consola usando una convención `dotnet {command}`.</span><span class="sxs-lookup"><span data-stu-id="68a88-165">The commands are implemented as a console application using a `dotnet {command}` convention.</span></span>

### <a name="arguments"></a><span data-ttu-id="68a88-166">Argumentos</span><span class="sxs-lookup"><span data-stu-id="68a88-166">Arguments</span></span>

<span data-ttu-id="68a88-167">Los argumentos que se pasan en la línea de comandos son los argumentos para el comando invocado.</span><span class="sxs-lookup"><span data-stu-id="68a88-167">The arguments you pass on the command line are the arguments to the command invoked.</span></span> <span data-ttu-id="68a88-168">Por ejemplo, cuando ejecuta `dotnet publish my_app.csproj`, el argumento `my_app.csproj` indica el proyecto que se publicará y se pasará al comando `publish`.</span><span class="sxs-lookup"><span data-stu-id="68a88-168">For example when you execute `dotnet publish my_app.csproj`, the `my_app.csproj` argument indicates the project to publish and is passed to the `publish` command.</span></span>

### <a name="options"></a><span data-ttu-id="68a88-169">Opciones</span><span class="sxs-lookup"><span data-stu-id="68a88-169">Options</span></span>

<span data-ttu-id="68a88-170">Las opciones que se pasan en la línea de comandos son las opciones para el comando que se invoca.</span><span class="sxs-lookup"><span data-stu-id="68a88-170">The options you pass on the command line are the options to the command invoked.</span></span> <span data-ttu-id="68a88-171">Por ejemplo, cuando ejecuta `dotnet publish --output /build_output`, la opción `--output` y su valor se pasan al comando `publish`.</span><span class="sxs-lookup"><span data-stu-id="68a88-171">For example when you execute `dotnet publish --output /build_output`, the `--output` option and its value are passed to the `publish` command.</span></span>

## <a name="see-also"></a><span data-ttu-id="68a88-172">Vea también</span><span class="sxs-lookup"><span data-stu-id="68a88-172">See also</span></span>

- [<span data-ttu-id="68a88-173">Repositorio de GitHub dotnet/sdk</span><span class="sxs-lookup"><span data-stu-id="68a88-173">dotnet/sdk GitHub repository</span></span>](https://github.com/dotnet/sdk/)
- <span data-ttu-id="68a88-174">[.NET Core installation guide](../install/sdk.md) (Guía de instalación de .NET Core)</span><span class="sxs-lookup"><span data-stu-id="68a88-174">[.NET Core installation guide](../install/sdk.md)</span></span>
