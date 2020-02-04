---
title: CLI de .NET Core
titleSuffix: ''
description: Información general de la CLI de .NET Core y sus características.
ms.date: 08/14/2017
ms.openlocfilehash: b0a8e0dd8cf77bb6f7567c27e9972f62515ec0f2
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2020
ms.locfileid: "76920479"
---
# <a name="net-core-cli-overview"></a><span data-ttu-id="50b7d-103">Información general sobre la CLI de .NET Core</span><span class="sxs-lookup"><span data-stu-id="50b7d-103">.NET Core CLI overview</span></span>

<span data-ttu-id="50b7d-104">La interfaz de la línea de comandos (CLI) de .NET Core es una cadena de herramientas multiplataforma para desarrollar, compilar, ejecutar y publicar aplicaciones .NET Core.</span><span class="sxs-lookup"><span data-stu-id="50b7d-104">The .NET Core command-line interface (CLI) is a cross-platform toolchain for developing, building, running, and publishing .NET Core applications.</span></span>

<span data-ttu-id="50b7d-105">La CLI de .NET Core se incluye con el [SDK de .NET Core](../sdk.md).</span><span class="sxs-lookup"><span data-stu-id="50b7d-105">The .NET Core CLI is included with the [.NET Core SDK](../sdk.md).</span></span> <span data-ttu-id="50b7d-106">Para más información sobre cómo instalar el SDK de .NET Core, consulte [Instalación del SDK de .NET Core](../install/sdk.md).</span><span class="sxs-lookup"><span data-stu-id="50b7d-106">To learn how to install the .NET Core SDK, see [Install the .NET Core SDK](../install/sdk.md).</span></span>

## <a name="cli-commands"></a><span data-ttu-id="50b7d-107">Comandos de la CLI</span><span class="sxs-lookup"><span data-stu-id="50b7d-107">CLI commands</span></span>

<span data-ttu-id="50b7d-108">De forma predeterminada, se instalan los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="50b7d-108">The following commands are installed by default:</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="50b7d-109">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="50b7d-109">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="50b7d-110">**Comandos básicos**</span><span class="sxs-lookup"><span data-stu-id="50b7d-110">**Basic commands**</span></span>

- [<span data-ttu-id="50b7d-111">new</span><span class="sxs-lookup"><span data-stu-id="50b7d-111">new</span></span>](dotnet-new.md)
- [<span data-ttu-id="50b7d-112">restore</span><span class="sxs-lookup"><span data-stu-id="50b7d-112">restore</span></span>](dotnet-restore.md)
- [<span data-ttu-id="50b7d-113">build</span><span class="sxs-lookup"><span data-stu-id="50b7d-113">build</span></span>](dotnet-build.md)
- [<span data-ttu-id="50b7d-114">publish</span><span class="sxs-lookup"><span data-stu-id="50b7d-114">publish</span></span>](dotnet-publish.md)
- [<span data-ttu-id="50b7d-115">run</span><span class="sxs-lookup"><span data-stu-id="50b7d-115">run</span></span>](dotnet-run.md)
- [<span data-ttu-id="50b7d-116">test</span><span class="sxs-lookup"><span data-stu-id="50b7d-116">test</span></span>](dotnet-test.md)
- [<span data-ttu-id="50b7d-117">vstest</span><span class="sxs-lookup"><span data-stu-id="50b7d-117">vstest</span></span>](dotnet-vstest.md)
- [<span data-ttu-id="50b7d-118">pack</span><span class="sxs-lookup"><span data-stu-id="50b7d-118">pack</span></span>](dotnet-pack.md)
- [<span data-ttu-id="50b7d-119">migrate</span><span class="sxs-lookup"><span data-stu-id="50b7d-119">migrate</span></span>](dotnet-migrate.md)
- [<span data-ttu-id="50b7d-120">clean</span><span class="sxs-lookup"><span data-stu-id="50b7d-120">clean</span></span>](dotnet-clean.md)
- [<span data-ttu-id="50b7d-121">sln</span><span class="sxs-lookup"><span data-stu-id="50b7d-121">sln</span></span>](dotnet-sln.md)
- [<span data-ttu-id="50b7d-122">help</span><span class="sxs-lookup"><span data-stu-id="50b7d-122">help</span></span>](dotnet-help.md)
- [<span data-ttu-id="50b7d-123">store</span><span class="sxs-lookup"><span data-stu-id="50b7d-123">store</span></span>](dotnet-store.md)

<span data-ttu-id="50b7d-124">**Comandos de modificación del proyecto**</span><span class="sxs-lookup"><span data-stu-id="50b7d-124">**Project modification commands**</span></span>

- [<span data-ttu-id="50b7d-125">add package</span><span class="sxs-lookup"><span data-stu-id="50b7d-125">add package</span></span>](dotnet-add-package.md)
- [<span data-ttu-id="50b7d-126">add reference</span><span class="sxs-lookup"><span data-stu-id="50b7d-126">add reference</span></span>](dotnet-add-reference.md)
- [<span data-ttu-id="50b7d-127">remove package</span><span class="sxs-lookup"><span data-stu-id="50b7d-127">remove package</span></span>](dotnet-remove-package.md)
- [<span data-ttu-id="50b7d-128">remove reference</span><span class="sxs-lookup"><span data-stu-id="50b7d-128">remove reference</span></span>](dotnet-remove-reference.md)
- [<span data-ttu-id="50b7d-129">list reference</span><span class="sxs-lookup"><span data-stu-id="50b7d-129">list reference</span></span>](dotnet-list-reference.md)

<span data-ttu-id="50b7d-130">**Comandos avanzados**</span><span class="sxs-lookup"><span data-stu-id="50b7d-130">**Advanced commands**</span></span>

- [<span data-ttu-id="50b7d-131">nuget delete</span><span class="sxs-lookup"><span data-stu-id="50b7d-131">nuget delete</span></span>](dotnet-nuget-delete.md)
- [<span data-ttu-id="50b7d-132">nuget locals</span><span class="sxs-lookup"><span data-stu-id="50b7d-132">nuget locals</span></span>](dotnet-nuget-locals.md)
- [<span data-ttu-id="50b7d-133">nuget push</span><span class="sxs-lookup"><span data-stu-id="50b7d-133">nuget push</span></span>](dotnet-nuget-push.md)
- [<span data-ttu-id="50b7d-134">msbuild</span><span class="sxs-lookup"><span data-stu-id="50b7d-134">msbuild</span></span>](dotnet-msbuild.md)
- [<span data-ttu-id="50b7d-135">dotnet install script</span><span class="sxs-lookup"><span data-stu-id="50b7d-135">dotnet install script</span></span>](dotnet-install-script.md)

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="50b7d-136">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="50b7d-136">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="50b7d-137">**Comandos básicos**</span><span class="sxs-lookup"><span data-stu-id="50b7d-137">**Basic commands**</span></span>

- [<span data-ttu-id="50b7d-138">new</span><span class="sxs-lookup"><span data-stu-id="50b7d-138">new</span></span>](dotnet-new.md)
- [<span data-ttu-id="50b7d-139">restore</span><span class="sxs-lookup"><span data-stu-id="50b7d-139">restore</span></span>](dotnet-restore.md)
- [<span data-ttu-id="50b7d-140">build</span><span class="sxs-lookup"><span data-stu-id="50b7d-140">build</span></span>](dotnet-build.md)
- [<span data-ttu-id="50b7d-141">publish</span><span class="sxs-lookup"><span data-stu-id="50b7d-141">publish</span></span>](dotnet-publish.md)
- [<span data-ttu-id="50b7d-142">run</span><span class="sxs-lookup"><span data-stu-id="50b7d-142">run</span></span>](dotnet-run.md)
- [<span data-ttu-id="50b7d-143">test</span><span class="sxs-lookup"><span data-stu-id="50b7d-143">test</span></span>](dotnet-test.md)
- [<span data-ttu-id="50b7d-144">vstest</span><span class="sxs-lookup"><span data-stu-id="50b7d-144">vstest</span></span>](dotnet-vstest.md)
- [<span data-ttu-id="50b7d-145">pack</span><span class="sxs-lookup"><span data-stu-id="50b7d-145">pack</span></span>](dotnet-pack.md)
- [<span data-ttu-id="50b7d-146">migrate</span><span class="sxs-lookup"><span data-stu-id="50b7d-146">migrate</span></span>](dotnet-migrate.md)
- [<span data-ttu-id="50b7d-147">clean</span><span class="sxs-lookup"><span data-stu-id="50b7d-147">clean</span></span>](dotnet-clean.md)
- [<span data-ttu-id="50b7d-148">sln</span><span class="sxs-lookup"><span data-stu-id="50b7d-148">sln</span></span>](dotnet-sln.md)

<span data-ttu-id="50b7d-149">**Comandos de modificación del proyecto**</span><span class="sxs-lookup"><span data-stu-id="50b7d-149">**Project modification commands**</span></span>

- [<span data-ttu-id="50b7d-150">add package</span><span class="sxs-lookup"><span data-stu-id="50b7d-150">add package</span></span>](dotnet-add-package.md)
- [<span data-ttu-id="50b7d-151">add reference</span><span class="sxs-lookup"><span data-stu-id="50b7d-151">add reference</span></span>](dotnet-add-reference.md)
- [<span data-ttu-id="50b7d-152">remove package</span><span class="sxs-lookup"><span data-stu-id="50b7d-152">remove package</span></span>](dotnet-remove-package.md)
- [<span data-ttu-id="50b7d-153">remove reference</span><span class="sxs-lookup"><span data-stu-id="50b7d-153">remove reference</span></span>](dotnet-remove-reference.md)
- [<span data-ttu-id="50b7d-154">list reference</span><span class="sxs-lookup"><span data-stu-id="50b7d-154">list reference</span></span>](dotnet-list-reference.md)

<span data-ttu-id="50b7d-155">**Comandos avanzados**</span><span class="sxs-lookup"><span data-stu-id="50b7d-155">**Advanced commands**</span></span>

- [<span data-ttu-id="50b7d-156">nuget delete</span><span class="sxs-lookup"><span data-stu-id="50b7d-156">nuget delete</span></span>](dotnet-nuget-delete.md)
- [<span data-ttu-id="50b7d-157">nuget locals</span><span class="sxs-lookup"><span data-stu-id="50b7d-157">nuget locals</span></span>](dotnet-nuget-locals.md)
- [<span data-ttu-id="50b7d-158">nuget push</span><span class="sxs-lookup"><span data-stu-id="50b7d-158">nuget push</span></span>](dotnet-nuget-push.md)
- [<span data-ttu-id="50b7d-159">msbuild</span><span class="sxs-lookup"><span data-stu-id="50b7d-159">msbuild</span></span>](dotnet-msbuild.md)
- [<span data-ttu-id="50b7d-160">dotnet install script</span><span class="sxs-lookup"><span data-stu-id="50b7d-160">dotnet install script</span></span>](dotnet-install-script.md)

---

<span data-ttu-id="50b7d-161">La CLI adopta un modelo de extensibilidad que le permite especificar herramientas adicionales para sus proyectos.</span><span class="sxs-lookup"><span data-stu-id="50b7d-161">The CLI adopts an extensibility model that allows you to specify additional tools for your projects.</span></span> <span data-ttu-id="50b7d-162">Para más información, consulte el tema [Modelo de extensibilidad de la CLI de .NET Core](extensibility.md).</span><span class="sxs-lookup"><span data-stu-id="50b7d-162">For more information, see the [.NET Core CLI extensibility model](extensibility.md) topic.</span></span>

## <a name="command-structure"></a><span data-ttu-id="50b7d-163">Estructura de comandos</span><span class="sxs-lookup"><span data-stu-id="50b7d-163">Command structure</span></span>

<span data-ttu-id="50b7d-164">La estructura de comandos de la CLI consta del [controlador ("dotnet")](#driver), [el comando](#command) y posiblemente de los [argumentos de comandos](#arguments) y otras [opciones](#options).</span><span class="sxs-lookup"><span data-stu-id="50b7d-164">CLI command structure consists of [the driver ("dotnet")](#driver), [the command](#command), and possibly command [arguments](#arguments) and [options](#options).</span></span> <span data-ttu-id="50b7d-165">Este patrón se puede ver en la mayoría de las operaciones de la CLI, como la creación de una nueva aplicación de consola y su ejecución desde la línea de comandos, como muestran los siguientes comandos cuando se ejecutan desde un directorio denominado *my_app* :</span><span class="sxs-lookup"><span data-stu-id="50b7d-165">You see this pattern in most CLI operations, such as creating a new console app and running it from the command line as the following commands show when executed from a directory named *my_app*:</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="50b7d-166">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="50b7d-166">.NET Core 2.x</span></span>](#tab/netcore2x)

```dotnetcli
dotnet new console
dotnet build --output /build_output
dotnet /build_output/my_app.dll
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="50b7d-167">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="50b7d-167">.NET Core 1.x</span></span>](#tab/netcore1x)

```dotnetcli
dotnet new console
dotnet restore
dotnet build --output /build_output
dotnet /build_output/my_app.dll
```

---

### <a name="driver"></a><span data-ttu-id="50b7d-168">Controlador</span><span class="sxs-lookup"><span data-stu-id="50b7d-168">Driver</span></span>

<span data-ttu-id="50b7d-169">El controlador se denomina [dotnet](dotnet.md) y tiene dos responsabilidades, ejecutar una [aplicación dependiente del marco](../deploying/index.md) o ejecutar un comando.</span><span class="sxs-lookup"><span data-stu-id="50b7d-169">The driver is named [dotnet](dotnet.md) and has two responsibilities, either running a [framework-dependent app](../deploying/index.md) or executing a command.</span></span> 

<span data-ttu-id="50b7d-170">Para ejecutar una aplicación dependiente del marco, especifique la aplicación después del controlador, por ejemplo, `dotnet /path/to/my_app.dll`.</span><span class="sxs-lookup"><span data-stu-id="50b7d-170">To run a framework-dependent app, specify the app after the driver, for example, `dotnet /path/to/my_app.dll`.</span></span> <span data-ttu-id="50b7d-171">Cuando ejecute el comando desde la carpeta donde reside la DLL de la aplicación, simplemente ejecute `dotnet my_app.dll`.</span><span class="sxs-lookup"><span data-stu-id="50b7d-171">When executing the command from the folder where the app's DLL resides, simply execute `dotnet my_app.dll`.</span></span> <span data-ttu-id="50b7d-172">Si quiere usar una versión específica del entorno de ejecución .NET Core, use la opción `--fx-version <VERSION>` (consulte la referencia del [comando dotnet](dotnet.md)).</span><span class="sxs-lookup"><span data-stu-id="50b7d-172">If you want to use a specific version of the .NET Core Runtime, use the `--fx-version <VERSION>` option (see the [dotnet command](dotnet.md) reference).</span></span>

<span data-ttu-id="50b7d-173">Cuando se proporciona un comando para el controlador, `dotnet.exe` inicia el proceso de ejecución del comando de la CLI.</span><span class="sxs-lookup"><span data-stu-id="50b7d-173">When you supply a command to the driver, `dotnet.exe` starts the CLI command execution process.</span></span> <span data-ttu-id="50b7d-174">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="50b7d-174">For example:</span></span>

```dotnetcli
dotnet build
```

<span data-ttu-id="50b7d-175">En primer lugar, el controlador determina la versión de SDK que se debe usar.</span><span class="sxs-lookup"><span data-stu-id="50b7d-175">First, the driver determines the version of the SDK to use.</span></span> <span data-ttu-id="50b7d-176">Si no hay ningún elemento ["global.json"](global-json.md), se usa la última versión del SDK disponible.</span><span class="sxs-lookup"><span data-stu-id="50b7d-176">If there is no ['global.json'](global-json.md), the latest version of the SDK available is used.</span></span> <span data-ttu-id="50b7d-177">Podría tratarse de una versión preliminar o de una versión estable, en función de lo último que esté disponible en el equipo.</span><span class="sxs-lookup"><span data-stu-id="50b7d-177">This might be either a preview or stable version, depending on what is latest on the machine.</span></span>  <span data-ttu-id="50b7d-178">Una vez determinada la versión del SDK, se ejecutará el comando.</span><span class="sxs-lookup"><span data-stu-id="50b7d-178">Once the SDK version is determined, it executes the command.</span></span>

### <a name="command"></a><span data-ttu-id="50b7d-179">Comando</span><span class="sxs-lookup"><span data-stu-id="50b7d-179">Command</span></span>

<span data-ttu-id="50b7d-180">El comando realiza una acción.</span><span class="sxs-lookup"><span data-stu-id="50b7d-180">The command performs an action.</span></span> <span data-ttu-id="50b7d-181">Por ejemplo, `dotnet build` compila código.</span><span class="sxs-lookup"><span data-stu-id="50b7d-181">For example, `dotnet build` builds code.</span></span> <span data-ttu-id="50b7d-182">`dotnet publish` publica el código.</span><span class="sxs-lookup"><span data-stu-id="50b7d-182">`dotnet publish` publishes code.</span></span> <span data-ttu-id="50b7d-183">Los comandos se implementan como una aplicación de consola usando una convención `dotnet {command}`.</span><span class="sxs-lookup"><span data-stu-id="50b7d-183">The commands are implemented as a console application using a `dotnet {command}` convention.</span></span>

### <a name="arguments"></a><span data-ttu-id="50b7d-184">Argumentos</span><span class="sxs-lookup"><span data-stu-id="50b7d-184">Arguments</span></span>

<span data-ttu-id="50b7d-185">Los argumentos que se pasan en la línea de comandos son los argumentos para el comando invocado.</span><span class="sxs-lookup"><span data-stu-id="50b7d-185">The arguments you pass on the command line are the arguments to the command invoked.</span></span> <span data-ttu-id="50b7d-186">Por ejemplo, cuando ejecuta `dotnet publish my_app.csproj`, el argumento `my_app.csproj` indica el proyecto que se publicará y se pasará al comando `publish`.</span><span class="sxs-lookup"><span data-stu-id="50b7d-186">For example when you execute `dotnet publish my_app.csproj`, the `my_app.csproj` argument indicates the project to publish and is passed to the `publish` command.</span></span>

### <a name="options"></a><span data-ttu-id="50b7d-187">Opciones</span><span class="sxs-lookup"><span data-stu-id="50b7d-187">Options</span></span>

<span data-ttu-id="50b7d-188">Las opciones que se pasan en la línea de comandos son las opciones para el comando que se invoca.</span><span class="sxs-lookup"><span data-stu-id="50b7d-188">The options you pass on the command line are the options to the command invoked.</span></span> <span data-ttu-id="50b7d-189">Por ejemplo, cuando ejecuta `dotnet publish --output /build_output`, la opción `--output` y su valor se pasan al comando `publish`.</span><span class="sxs-lookup"><span data-stu-id="50b7d-189">For example when you execute `dotnet publish --output /build_output`, the `--output` option and its value are passed to the `publish` command.</span></span>

## <a name="migration-from-projectjson"></a><span data-ttu-id="50b7d-190">Migración desde project.json</span><span class="sxs-lookup"><span data-stu-id="50b7d-190">Migration from project.json</span></span>

<span data-ttu-id="50b7d-191">Si usó herramientas de la versión preliminar 2 para producir proyectos basados en *project.json*, consulte el tema sobre [dotnet migrate](dotnet-migrate.md) para más información sobre cómo migrar su proyecto a MSBuild/ *.csproj*  para usarlo con herramientas de versión.</span><span class="sxs-lookup"><span data-stu-id="50b7d-191">If you used Preview 2 tooling to produce *project.json*-based projects, consult the [dotnet migrate](dotnet-migrate.md) topic for information on migrating your project to MSBuild/*.csproj* for use with release tooling.</span></span> <span data-ttu-id="50b7d-192">Para los proyectos de .NET Core creados antes del lanzamiento de las herramientas de la versión preliminar 2, actualice manualmente el proyecto siguiendo las instrucciones que se indican en [Migración de DNX a CLI de .NET Core (project.json)](../migration/from-dnx.md) y, luego, use `dotnet migrate` o actualice directamente los proyectos.</span><span class="sxs-lookup"><span data-stu-id="50b7d-192">For .NET Core projects created prior to the release of Preview 2 tooling, either manually update the project following the guidance in [Migrating from DNX to .NET Core CLI (project.json)](../migration/from-dnx.md) and then use `dotnet migrate` or directly upgrade your projects.</span></span>

## <a name="see-also"></a><span data-ttu-id="50b7d-193">Vea también</span><span class="sxs-lookup"><span data-stu-id="50b7d-193">See also</span></span>

- [<span data-ttu-id="50b7d-194">Repositorio de GitHub dotnet/sdk</span><span class="sxs-lookup"><span data-stu-id="50b7d-194">dotnet/sdk GitHub repository</span></span>](https://github.com/dotnet/sdk/)
- <span data-ttu-id="50b7d-195">[.NET Core installation guide](https://aka.ms/dotnetcoregs) (Guía de instalación de .NET Core)</span><span class="sxs-lookup"><span data-stu-id="50b7d-195">[.NET Core installation guide](https://aka.ms/dotnetcoregs)</span></span>
