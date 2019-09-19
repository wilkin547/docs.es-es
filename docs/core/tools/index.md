---
title: Herramientas de la interfaz de línea de comandos (CLI) de .NET Core
description: Introducción a las herramientas y características de la interfaz de la línea de comandos (CLI) de .NET Core.
ms.date: 08/14/2017
ms.custom: seodec18
ms.openlocfilehash: 4ff5cfd6c5a70c92387911ab87ddea5cee80275e
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117395"
---
# <a name="net-core-command-line-interface-cli-tools"></a><span data-ttu-id="97287-103">Herramientas de la interfaz de la línea de comandos (CLI) de .NET Core</span><span class="sxs-lookup"><span data-stu-id="97287-103">.NET Core command-line interface (CLI) tools</span></span>

<span data-ttu-id="97287-104">La interfaz de la línea de comandos (CLI) de .NET Core es una nueva cadena de herramientas multiplataforma para el desarrollo de aplicaciones. NET.</span><span class="sxs-lookup"><span data-stu-id="97287-104">The .NET Core command-line interface (CLI) is a new cross-platform toolchain for developing .NET applications.</span></span> <span data-ttu-id="97287-105">La CLI es una base sobre la que pueden descansar herramientas de nivel superior, como los entornos de desarrollo integrados (IDE), los editores y los orquestadores de compilación.</span><span class="sxs-lookup"><span data-stu-id="97287-105">The CLI is a foundation upon which higher-level tools, such as Integrated Development Environments (IDEs), editors, and build orchestrators, can rest.</span></span>

## <a name="installation"></a><span data-ttu-id="97287-106">Instalación</span><span class="sxs-lookup"><span data-stu-id="97287-106">Installation</span></span>

<span data-ttu-id="97287-107">Puede usar los instaladores nativos o los scripts de shell de instalación:</span><span class="sxs-lookup"><span data-stu-id="97287-107">Either use the native installers or use the installation shell scripts:</span></span>

- <span data-ttu-id="97287-108">Los instaladores nativos se usan principalmente en máquinas del desarrollador y usan el mecanismo de instalación nativo de cada plataforma compatible, por ejemplo, los paquetes DEB en Ubuntu o los paquetes MSI en Windows.</span><span class="sxs-lookup"><span data-stu-id="97287-108">The native installers are primarily used on developer's machines and use each supported platform's native install mechanism, for instance, DEB packages on Ubuntu or MSI bundles on Windows.</span></span> <span data-ttu-id="97287-109">Estos instaladores instalan y configuran el entorno para su uso inmediato por el desarrollador, pero requieren privilegios administrativos en la máquina.</span><span class="sxs-lookup"><span data-stu-id="97287-109">These installers install and configure the environment for immediate use by the developer but require administrative privileges on the machine.</span></span> <span data-ttu-id="97287-110">Puede ver las instrucciones de instalación en la [Guía de instalación de .NET Core](https://aka.ms/dotnetcoregs).</span><span class="sxs-lookup"><span data-stu-id="97287-110">You can view the installation instructions in the [.NET Core installation guide](https://aka.ms/dotnetcoregs).</span></span>
- <span data-ttu-id="97287-111">Los scripts de shell se usan principalmente para configurar servidores de compilación o cuando desee instalar las herramientas sin privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="97287-111">Shell scripts are primarily used for setting up build servers or when you wish to install the tools without administrative privileges.</span></span> <span data-ttu-id="97287-112">Los scripts de instalación no instalan los requisitos previos en la máquina, se deben instalar manualmente.</span><span class="sxs-lookup"><span data-stu-id="97287-112">Install scripts don't install prerequisites on the machine, which must be installed manually.</span></span> <span data-ttu-id="97287-113">Para más información, consulte el [tema de referencia sobre los scripts de instalación](dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="97287-113">For more information, see the [install script reference topic](dotnet-install-script.md).</span></span> <span data-ttu-id="97287-114">Para más información sobre cómo configurar la CLI en el servidor de compilación de integración continua (CI), consulte [Uso de .NET Core SDK y herramientas de integración continua (CI)](using-ci-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="97287-114">For information on how to set up CLI on your continuous integration (CI) build server, see [Using .NET Core SDK and tools in Continuous Integration (CI)](using-ci-with-cli.md).</span></span>

<span data-ttu-id="97287-115">De forma predeterminada, la CLI se instala en paralelo (SxS), para que varias versiones de las herramientas de la CLI puedan coexistir en una única máquina.</span><span class="sxs-lookup"><span data-stu-id="97287-115">By default, the CLI installs in a side-by-side (SxS) manner, so multiple versions of the CLI tools can coexist on a single machine.</span></span> <span data-ttu-id="97287-116">En la sección [Controlador](#driver) se explica más detalladamente cómo determinar qué versión usar en una máquina en la que hay varias versiones instaladas.</span><span class="sxs-lookup"><span data-stu-id="97287-116">Determining which version is used on a machine where multiple versions are installed is explained in more detail in the [Driver](#driver) section.</span></span>

## <a name="cli-commands"></a><span data-ttu-id="97287-117">Comandos de la CLI</span><span class="sxs-lookup"><span data-stu-id="97287-117">CLI commands</span></span>

<span data-ttu-id="97287-118">De forma predeterminada, se instalan los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="97287-118">The following commands are installed by default:</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="97287-119">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="97287-119">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="97287-120">**Comandos básicos**</span><span class="sxs-lookup"><span data-stu-id="97287-120">**Basic commands**</span></span>

- [<span data-ttu-id="97287-121">new</span><span class="sxs-lookup"><span data-stu-id="97287-121">new</span></span>](dotnet-new.md)
- [<span data-ttu-id="97287-122">restore</span><span class="sxs-lookup"><span data-stu-id="97287-122">restore</span></span>](dotnet-restore.md)
- [<span data-ttu-id="97287-123">build</span><span class="sxs-lookup"><span data-stu-id="97287-123">build</span></span>](dotnet-build.md)
- [<span data-ttu-id="97287-124">publish</span><span class="sxs-lookup"><span data-stu-id="97287-124">publish</span></span>](dotnet-publish.md)
- [<span data-ttu-id="97287-125">run</span><span class="sxs-lookup"><span data-stu-id="97287-125">run</span></span>](dotnet-run.md)
- [<span data-ttu-id="97287-126">test</span><span class="sxs-lookup"><span data-stu-id="97287-126">test</span></span>](dotnet-test.md)
- [<span data-ttu-id="97287-127">vstest</span><span class="sxs-lookup"><span data-stu-id="97287-127">vstest</span></span>](dotnet-vstest.md)
- [<span data-ttu-id="97287-128">pack</span><span class="sxs-lookup"><span data-stu-id="97287-128">pack</span></span>](dotnet-pack.md)
- [<span data-ttu-id="97287-129">migrate</span><span class="sxs-lookup"><span data-stu-id="97287-129">migrate</span></span>](dotnet-migrate.md)
- [<span data-ttu-id="97287-130">clean</span><span class="sxs-lookup"><span data-stu-id="97287-130">clean</span></span>](dotnet-clean.md)
- [<span data-ttu-id="97287-131">sln</span><span class="sxs-lookup"><span data-stu-id="97287-131">sln</span></span>](dotnet-sln.md)
- [<span data-ttu-id="97287-132">help</span><span class="sxs-lookup"><span data-stu-id="97287-132">help</span></span>](dotnet-help.md)
- [<span data-ttu-id="97287-133">store</span><span class="sxs-lookup"><span data-stu-id="97287-133">store</span></span>](dotnet-store.md)

<span data-ttu-id="97287-134">**Comandos de modificación del proyecto**</span><span class="sxs-lookup"><span data-stu-id="97287-134">**Project modification commands**</span></span>

- [<span data-ttu-id="97287-135">add package</span><span class="sxs-lookup"><span data-stu-id="97287-135">add package</span></span>](dotnet-add-package.md)
- [<span data-ttu-id="97287-136">add reference</span><span class="sxs-lookup"><span data-stu-id="97287-136">add reference</span></span>](dotnet-add-reference.md)
- [<span data-ttu-id="97287-137">remove package</span><span class="sxs-lookup"><span data-stu-id="97287-137">remove package</span></span>](dotnet-remove-package.md)
- [<span data-ttu-id="97287-138">remove reference</span><span class="sxs-lookup"><span data-stu-id="97287-138">remove reference</span></span>](dotnet-remove-reference.md)
- [<span data-ttu-id="97287-139">list reference</span><span class="sxs-lookup"><span data-stu-id="97287-139">list reference</span></span>](dotnet-list-reference.md)

<span data-ttu-id="97287-140">**Comandos avanzados**</span><span class="sxs-lookup"><span data-stu-id="97287-140">**Advanced commands**</span></span>

- [<span data-ttu-id="97287-141">nuget delete</span><span class="sxs-lookup"><span data-stu-id="97287-141">nuget delete</span></span>](dotnet-nuget-delete.md)
- [<span data-ttu-id="97287-142">nuget locals</span><span class="sxs-lookup"><span data-stu-id="97287-142">nuget locals</span></span>](dotnet-nuget-locals.md)
- [<span data-ttu-id="97287-143">nuget push</span><span class="sxs-lookup"><span data-stu-id="97287-143">nuget push</span></span>](dotnet-nuget-push.md)
- [<span data-ttu-id="97287-144">msbuild</span><span class="sxs-lookup"><span data-stu-id="97287-144">msbuild</span></span>](dotnet-msbuild.md)
- [<span data-ttu-id="97287-145">dotnet install script</span><span class="sxs-lookup"><span data-stu-id="97287-145">dotnet install script</span></span>](dotnet-install-script.md)

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="97287-146">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="97287-146">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="97287-147">**Comandos básicos**</span><span class="sxs-lookup"><span data-stu-id="97287-147">**Basic commands**</span></span>

- [<span data-ttu-id="97287-148">new</span><span class="sxs-lookup"><span data-stu-id="97287-148">new</span></span>](dotnet-new.md)
- [<span data-ttu-id="97287-149">restore</span><span class="sxs-lookup"><span data-stu-id="97287-149">restore</span></span>](dotnet-restore.md)
- [<span data-ttu-id="97287-150">build</span><span class="sxs-lookup"><span data-stu-id="97287-150">build</span></span>](dotnet-build.md)
- [<span data-ttu-id="97287-151">publish</span><span class="sxs-lookup"><span data-stu-id="97287-151">publish</span></span>](dotnet-publish.md)
- [<span data-ttu-id="97287-152">run</span><span class="sxs-lookup"><span data-stu-id="97287-152">run</span></span>](dotnet-run.md)
- [<span data-ttu-id="97287-153">test</span><span class="sxs-lookup"><span data-stu-id="97287-153">test</span></span>](dotnet-test.md)
- [<span data-ttu-id="97287-154">vstest</span><span class="sxs-lookup"><span data-stu-id="97287-154">vstest</span></span>](dotnet-vstest.md)
- [<span data-ttu-id="97287-155">pack</span><span class="sxs-lookup"><span data-stu-id="97287-155">pack</span></span>](dotnet-pack.md)
- [<span data-ttu-id="97287-156">migrate</span><span class="sxs-lookup"><span data-stu-id="97287-156">migrate</span></span>](dotnet-migrate.md)
- [<span data-ttu-id="97287-157">clean</span><span class="sxs-lookup"><span data-stu-id="97287-157">clean</span></span>](dotnet-clean.md)
- [<span data-ttu-id="97287-158">sln</span><span class="sxs-lookup"><span data-stu-id="97287-158">sln</span></span>](dotnet-sln.md)

<span data-ttu-id="97287-159">**Comandos de modificación del proyecto**</span><span class="sxs-lookup"><span data-stu-id="97287-159">**Project modification commands**</span></span>

- [<span data-ttu-id="97287-160">add package</span><span class="sxs-lookup"><span data-stu-id="97287-160">add package</span></span>](dotnet-add-package.md)
- [<span data-ttu-id="97287-161">add reference</span><span class="sxs-lookup"><span data-stu-id="97287-161">add reference</span></span>](dotnet-add-reference.md)
- [<span data-ttu-id="97287-162">remove package</span><span class="sxs-lookup"><span data-stu-id="97287-162">remove package</span></span>](dotnet-remove-package.md)
- [<span data-ttu-id="97287-163">remove reference</span><span class="sxs-lookup"><span data-stu-id="97287-163">remove reference</span></span>](dotnet-remove-reference.md)
- [<span data-ttu-id="97287-164">list reference</span><span class="sxs-lookup"><span data-stu-id="97287-164">list reference</span></span>](dotnet-list-reference.md)

<span data-ttu-id="97287-165">**Comandos avanzados**</span><span class="sxs-lookup"><span data-stu-id="97287-165">**Advanced commands**</span></span>

- [<span data-ttu-id="97287-166">nuget delete</span><span class="sxs-lookup"><span data-stu-id="97287-166">nuget delete</span></span>](dotnet-nuget-delete.md)
- [<span data-ttu-id="97287-167">nuget locals</span><span class="sxs-lookup"><span data-stu-id="97287-167">nuget locals</span></span>](dotnet-nuget-locals.md)
- [<span data-ttu-id="97287-168">nuget push</span><span class="sxs-lookup"><span data-stu-id="97287-168">nuget push</span></span>](dotnet-nuget-push.md)
- [<span data-ttu-id="97287-169">msbuild</span><span class="sxs-lookup"><span data-stu-id="97287-169">msbuild</span></span>](dotnet-msbuild.md)
- [<span data-ttu-id="97287-170">dotnet install script</span><span class="sxs-lookup"><span data-stu-id="97287-170">dotnet install script</span></span>](dotnet-install-script.md)

---

<span data-ttu-id="97287-171">La CLI adopta un modelo de extensibilidad que le permite especificar herramientas adicionales para sus proyectos.</span><span class="sxs-lookup"><span data-stu-id="97287-171">The CLI adopts an extensibility model that allows you to specify additional tools for your projects.</span></span> <span data-ttu-id="97287-172">Para más información, consulte el tema [Modelo de extensibilidad de la CLI de .NET Core](extensibility.md).</span><span class="sxs-lookup"><span data-stu-id="97287-172">For more information, see the [.NET Core CLI extensibility model](extensibility.md) topic.</span></span>

## <a name="command-structure"></a><span data-ttu-id="97287-173">Estructura de comandos</span><span class="sxs-lookup"><span data-stu-id="97287-173">Command structure</span></span>

<span data-ttu-id="97287-174">La estructura de comandos de la CLI consta del [controlador ("dotnet")](#driver), [el comando](#command) y posiblemente de los [argumentos de comandos](#arguments) y otras [opciones](#options).</span><span class="sxs-lookup"><span data-stu-id="97287-174">CLI command structure consists of [the driver ("dotnet")](#driver), [the command](#command), and possibly command [arguments](#arguments) and [options](#options).</span></span> <span data-ttu-id="97287-175">Este patrón se puede ver en la mayoría de las operaciones de la CLI, como la creación de una nueva aplicación de consola y su ejecución desde la línea de comandos, como muestran los siguientes comandos cuando se ejecutan desde un directorio denominado *my_app* :</span><span class="sxs-lookup"><span data-stu-id="97287-175">You see this pattern in most CLI operations, such as creating a new console app and running it from the command line as the following commands show when executed from a directory named *my_app*:</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="97287-176">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="97287-176">.NET Core 2.x</span></span>](#tab/netcore2x)

```dotnetcli
dotnet new console
dotnet build --output /build_output
dotnet /build_output/my_app.dll
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="97287-177">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="97287-177">.NET Core 1.x</span></span>](#tab/netcore1x)

```dotnetcli
dotnet new console
dotnet restore
dotnet build --output /build_output
dotnet /build_output/my_app.dll
```

---

### <a name="driver"></a><span data-ttu-id="97287-178">Controlador</span><span class="sxs-lookup"><span data-stu-id="97287-178">Driver</span></span>

<span data-ttu-id="97287-179">El controlador se denomina [dotnet](dotnet.md) y tiene dos responsabilidades, ejecutar una [aplicación dependiente del marco](../deploying/index.md) o ejecutar un comando.</span><span class="sxs-lookup"><span data-stu-id="97287-179">The driver is named [dotnet](dotnet.md) and has two responsibilities, either running a [framework-dependent app](../deploying/index.md) or executing a command.</span></span> 

<span data-ttu-id="97287-180">Para ejecutar una aplicación dependiente del marco, especifique la aplicación después del controlador, por ejemplo, `dotnet /path/to/my_app.dll`.</span><span class="sxs-lookup"><span data-stu-id="97287-180">To run a framework-dependent app, specify the app after the driver, for example, `dotnet /path/to/my_app.dll`.</span></span> <span data-ttu-id="97287-181">Cuando ejecute el comando desde la carpeta donde reside la DLL de la aplicación, simplemente ejecute `dotnet my_app.dll`.</span><span class="sxs-lookup"><span data-stu-id="97287-181">When executing the command from the folder where the app's DLL resides, simply execute `dotnet my_app.dll`.</span></span> <span data-ttu-id="97287-182">Si quiere usar una versión específica del entorno de ejecución .NET Core, use la opción `--fx-version <VERSION>` (consulte la referencia del [comando dotnet](dotnet.md)).</span><span class="sxs-lookup"><span data-stu-id="97287-182">If you want to use a specific version of the .NET Core Runtime, use the `--fx-version <VERSION>` option (see the [dotnet command](dotnet.md) reference).</span></span>

<span data-ttu-id="97287-183">Cuando se proporciona un comando para el controlador, `dotnet.exe` inicia el proceso de ejecución del comando de la CLI.</span><span class="sxs-lookup"><span data-stu-id="97287-183">When you supply a command to the driver, `dotnet.exe` starts the CLI command execution process.</span></span> <span data-ttu-id="97287-184">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="97287-184">For example:</span></span>

```dotnetcli
dotnet build
```

<span data-ttu-id="97287-185">En primer lugar, el controlador determina la versión de SDK que se debe usar.</span><span class="sxs-lookup"><span data-stu-id="97287-185">First, the driver determines the version of the SDK to use.</span></span> <span data-ttu-id="97287-186">Si no hay ningún elemento ["global.json"](global-json.md), se usa la última versión del SDK disponible.</span><span class="sxs-lookup"><span data-stu-id="97287-186">If there is no ['global.json'](global-json.md), the latest version of the SDK available is used.</span></span> <span data-ttu-id="97287-187">Podría tratarse de una versión preliminar o de una versión estable, en función de lo último que esté disponible en el equipo.</span><span class="sxs-lookup"><span data-stu-id="97287-187">This might be either a preview or stable version, depending on what is latest on the machine.</span></span>  <span data-ttu-id="97287-188">Una vez determinada la versión del SDK, se ejecutará el comando.</span><span class="sxs-lookup"><span data-stu-id="97287-188">Once the SDK version is determined, it executes the command.</span></span>

### <a name="command"></a><span data-ttu-id="97287-189">Comando</span><span class="sxs-lookup"><span data-stu-id="97287-189">Command</span></span>

<span data-ttu-id="97287-190">El comando realiza una acción.</span><span class="sxs-lookup"><span data-stu-id="97287-190">The command performs an action.</span></span> <span data-ttu-id="97287-191">Por ejemplo, `dotnet build` compila código.</span><span class="sxs-lookup"><span data-stu-id="97287-191">For example, `dotnet build` builds code.</span></span> <span data-ttu-id="97287-192">`dotnet publish` publica el código.</span><span class="sxs-lookup"><span data-stu-id="97287-192">`dotnet publish` publishes code.</span></span> <span data-ttu-id="97287-193">Los comandos se implementan como una aplicación de consola usando una convención `dotnet {command}`.</span><span class="sxs-lookup"><span data-stu-id="97287-193">The commands are implemented as a console application using a `dotnet {command}` convention.</span></span>

### <a name="arguments"></a><span data-ttu-id="97287-194">Argumentos</span><span class="sxs-lookup"><span data-stu-id="97287-194">Arguments</span></span>

<span data-ttu-id="97287-195">Los argumentos que se pasan en la línea de comandos son los argumentos para el comando invocado.</span><span class="sxs-lookup"><span data-stu-id="97287-195">The arguments you pass on the command line are the arguments to the command invoked.</span></span> <span data-ttu-id="97287-196">Por ejemplo, cuando ejecuta `dotnet publish my_app.csproj`, el argumento `my_app.csproj` indica el proyecto que se publicará y se pasará al comando `publish`.</span><span class="sxs-lookup"><span data-stu-id="97287-196">For example when you execute `dotnet publish my_app.csproj`, the `my_app.csproj` argument indicates the project to publish and is passed to the `publish` command.</span></span>

### <a name="options"></a><span data-ttu-id="97287-197">Opciones</span><span class="sxs-lookup"><span data-stu-id="97287-197">Options</span></span>

<span data-ttu-id="97287-198">Las opciones que se pasan en la línea de comandos son las opciones para el comando que se invoca.</span><span class="sxs-lookup"><span data-stu-id="97287-198">The options you pass on the command line are the options to the command invoked.</span></span> <span data-ttu-id="97287-199">Por ejemplo, cuando ejecuta `dotnet publish --output /build_output`, la opción `--output` y su valor se pasan al comando `publish`.</span><span class="sxs-lookup"><span data-stu-id="97287-199">For example when you execute `dotnet publish --output /build_output`, the `--output` option and its value are passed to the `publish` command.</span></span>

## <a name="migration-from-projectjson"></a><span data-ttu-id="97287-200">Migración desde project.json</span><span class="sxs-lookup"><span data-stu-id="97287-200">Migration from project.json</span></span>

<span data-ttu-id="97287-201">Si usó herramientas de la versión preliminar 2 para producir proyectos basados en *project.json*, consulte el tema sobre [dotnet migrate](dotnet-migrate.md) para más información sobre cómo migrar su proyecto a MSBuild/ *.csproj*  para usarlo con herramientas de versión.</span><span class="sxs-lookup"><span data-stu-id="97287-201">If you used Preview 2 tooling to produce *project.json*-based projects, consult the [dotnet migrate](dotnet-migrate.md) topic for information on migrating your project to MSBuild/*.csproj* for use with release tooling.</span></span> <span data-ttu-id="97287-202">Para los proyectos de .NET Core creados antes del lanzamiento de las herramientas de la versión preliminar 2, actualice manualmente el proyecto siguiendo las instrucciones que se indican en [Migración de DNX a CLI de .NET Core (project.json)](../migration/from-dnx.md) y, luego, use `dotnet migrate` o actualice directamente los proyectos.</span><span class="sxs-lookup"><span data-stu-id="97287-202">For .NET Core projects created prior to the release of Preview 2 tooling, either manually update the project following the guidance in [Migrating from DNX to .NET Core CLI (project.json)](../migration/from-dnx.md) and then use `dotnet migrate` or directly upgrade your projects.</span></span>

## <a name="see-also"></a><span data-ttu-id="97287-203">Vea también</span><span class="sxs-lookup"><span data-stu-id="97287-203">See also</span></span>

- [<span data-ttu-id="97287-204">dotnet/repositorio de GitHub de la CLI</span><span class="sxs-lookup"><span data-stu-id="97287-204">dotnet/CLI GitHub Repository</span></span>](https://github.com/dotnet/cli/)
- <span data-ttu-id="97287-205">[.NET Core installation guide](https://aka.ms/dotnetcoregs) (Guía de instalación de .NET Core)</span><span class="sxs-lookup"><span data-stu-id="97287-205">[.NET Core installation guide](https://aka.ms/dotnetcoregs)</span></span>
