---
title: Herramientas de la interfaz de línea de comandos (CLI) de .NET Core
description: Introducción a las herramientas y características de la interfaz de la línea de comandos (CLI) de .NET Core.
ms.date: 08/14/2017
ms.openlocfilehash: f19dcb19fb9d0203b3d3795c3fdc0b026c4c60e3
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163220"
---
# <a name="net-core-command-line-interface-cli-tools"></a><span data-ttu-id="40a8e-103">Herramientas de la interfaz de la línea de comandos (CLI) de .NET Core</span><span class="sxs-lookup"><span data-stu-id="40a8e-103">.NET Core command-line interface (CLI) tools</span></span>

<span data-ttu-id="40a8e-104">La interfaz de la línea de comandos (CLI) de .NET Core es una cadena de herramientas multiplataforma para el desarrollo de aplicaciones. NET.</span><span class="sxs-lookup"><span data-stu-id="40a8e-104">The .NET Core command-line interface (CLI) is a cross-platform toolchain for developing .NET applications.</span></span> <span data-ttu-id="40a8e-105">La CLI es una base sobre la que pueden descansar herramientas de nivel superior, como los entornos de desarrollo integrados (IDE), los editores y los orquestadores de compilación.</span><span class="sxs-lookup"><span data-stu-id="40a8e-105">The CLI is a foundation upon which higher-level tools, such as integrated development environments (IDEs), editors, and build orchestrators, can rest.</span></span>

## <a name="installation"></a><span data-ttu-id="40a8e-106">Instalación</span><span class="sxs-lookup"><span data-stu-id="40a8e-106">Installation</span></span>

<span data-ttu-id="40a8e-107">Puede usar los instaladores nativos o los scripts de shell de instalación:</span><span class="sxs-lookup"><span data-stu-id="40a8e-107">Either use the native installers or use the installation shell scripts:</span></span>

- <span data-ttu-id="40a8e-108">Los instaladores nativos se usan principalmente en máquinas del desarrollador y usan el mecanismo de instalación nativo de cada plataforma compatible, por ejemplo, los paquetes DEB en Ubuntu o los paquetes MSI en Windows.</span><span class="sxs-lookup"><span data-stu-id="40a8e-108">The native installers are primarily used on developer's machines and use each supported platform's native install mechanism, for instance, DEB packages on Ubuntu or MSI bundles on Windows.</span></span> <span data-ttu-id="40a8e-109">Estos instaladores instalan y configuran el entorno para su uso inmediato por el desarrollador, pero requieren privilegios administrativos en la máquina.</span><span class="sxs-lookup"><span data-stu-id="40a8e-109">These installers install and configure the environment for immediate use by the developer but require administrative privileges on the machine.</span></span> <span data-ttu-id="40a8e-110">Puede ver las instrucciones de instalación en la [Guía de instalación de .NET Core](https://aka.ms/dotnetcoregs).</span><span class="sxs-lookup"><span data-stu-id="40a8e-110">You can view the installation instructions in the [.NET Core installation guide](https://aka.ms/dotnetcoregs).</span></span>
- <span data-ttu-id="40a8e-111">Los scripts de shell se usan principalmente para configurar servidores de compilación o cuando desee instalar las herramientas sin privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="40a8e-111">Shell scripts are primarily used for setting up build servers or when you wish to install the tools without administrative privileges.</span></span> <span data-ttu-id="40a8e-112">Los scripts de instalación no instalan los requisitos previos en la máquina, se deben instalar manualmente.</span><span class="sxs-lookup"><span data-stu-id="40a8e-112">Install scripts don't install prerequisites on the machine, which must be installed manually.</span></span> <span data-ttu-id="40a8e-113">Para más información, consulte el [tema de referencia sobre los scripts de instalación](dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="40a8e-113">For more information, see the [install script reference topic](dotnet-install-script.md).</span></span> <span data-ttu-id="40a8e-114">Para más información sobre cómo configurar la CLI en el servidor de compilación de integración continua (CI), consulte [Uso de .NET Core SDK y herramientas de integración continua (CI)](using-ci-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="40a8e-114">For information on how to set up CLI on your continuous integration (CI) build server, see [Using .NET Core SDK and tools in Continuous Integration (CI)](using-ci-with-cli.md).</span></span>

<span data-ttu-id="40a8e-115">De forma predeterminada, la CLI se instala en paralelo (SxS), para que varias versiones de las herramientas de la CLI puedan coexistir en una única máquina.</span><span class="sxs-lookup"><span data-stu-id="40a8e-115">By default, the CLI installs in a side-by-side (SxS) manner, so multiple versions of the CLI tools can coexist on a single machine.</span></span> <span data-ttu-id="40a8e-116">En la sección [Controlador](#driver) se explica más detalladamente cómo determinar qué versión usar en una máquina en la que hay varias versiones instaladas.</span><span class="sxs-lookup"><span data-stu-id="40a8e-116">Determining which version is used on a machine where multiple versions are installed is explained in more detail in the [Driver](#driver) section.</span></span>

## <a name="cli-commands"></a><span data-ttu-id="40a8e-117">Comandos de la CLI</span><span class="sxs-lookup"><span data-stu-id="40a8e-117">CLI commands</span></span>

<span data-ttu-id="40a8e-118">De forma predeterminada, se instalan los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="40a8e-118">The following commands are installed by default:</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="40a8e-119">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="40a8e-119">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="40a8e-120">**Comandos básicos**</span><span class="sxs-lookup"><span data-stu-id="40a8e-120">**Basic commands**</span></span>

- [<span data-ttu-id="40a8e-121">new</span><span class="sxs-lookup"><span data-stu-id="40a8e-121">new</span></span>](dotnet-new.md)
- [<span data-ttu-id="40a8e-122">restore</span><span class="sxs-lookup"><span data-stu-id="40a8e-122">restore</span></span>](dotnet-restore.md)
- [<span data-ttu-id="40a8e-123">build</span><span class="sxs-lookup"><span data-stu-id="40a8e-123">build</span></span>](dotnet-build.md)
- [<span data-ttu-id="40a8e-124">publish</span><span class="sxs-lookup"><span data-stu-id="40a8e-124">publish</span></span>](dotnet-publish.md)
- [<span data-ttu-id="40a8e-125">run</span><span class="sxs-lookup"><span data-stu-id="40a8e-125">run</span></span>](dotnet-run.md)
- [<span data-ttu-id="40a8e-126">test</span><span class="sxs-lookup"><span data-stu-id="40a8e-126">test</span></span>](dotnet-test.md)
- [<span data-ttu-id="40a8e-127">vstest</span><span class="sxs-lookup"><span data-stu-id="40a8e-127">vstest</span></span>](dotnet-vstest.md)
- [<span data-ttu-id="40a8e-128">pack</span><span class="sxs-lookup"><span data-stu-id="40a8e-128">pack</span></span>](dotnet-pack.md)
- [<span data-ttu-id="40a8e-129">migrate</span><span class="sxs-lookup"><span data-stu-id="40a8e-129">migrate</span></span>](dotnet-migrate.md)
- [<span data-ttu-id="40a8e-130">clean</span><span class="sxs-lookup"><span data-stu-id="40a8e-130">clean</span></span>](dotnet-clean.md)
- [<span data-ttu-id="40a8e-131">sln</span><span class="sxs-lookup"><span data-stu-id="40a8e-131">sln</span></span>](dotnet-sln.md)
- [<span data-ttu-id="40a8e-132">help</span><span class="sxs-lookup"><span data-stu-id="40a8e-132">help</span></span>](dotnet-help.md)
- [<span data-ttu-id="40a8e-133">store</span><span class="sxs-lookup"><span data-stu-id="40a8e-133">store</span></span>](dotnet-store.md)

<span data-ttu-id="40a8e-134">**Comandos de modificación del proyecto**</span><span class="sxs-lookup"><span data-stu-id="40a8e-134">**Project modification commands**</span></span>

- [<span data-ttu-id="40a8e-135">add package</span><span class="sxs-lookup"><span data-stu-id="40a8e-135">add package</span></span>](dotnet-add-package.md)
- [<span data-ttu-id="40a8e-136">add reference</span><span class="sxs-lookup"><span data-stu-id="40a8e-136">add reference</span></span>](dotnet-add-reference.md)
- [<span data-ttu-id="40a8e-137">remove package</span><span class="sxs-lookup"><span data-stu-id="40a8e-137">remove package</span></span>](dotnet-remove-package.md)
- [<span data-ttu-id="40a8e-138">remove reference</span><span class="sxs-lookup"><span data-stu-id="40a8e-138">remove reference</span></span>](dotnet-remove-reference.md)
- [<span data-ttu-id="40a8e-139">list reference</span><span class="sxs-lookup"><span data-stu-id="40a8e-139">list reference</span></span>](dotnet-list-reference.md)

<span data-ttu-id="40a8e-140">**Comandos avanzados**</span><span class="sxs-lookup"><span data-stu-id="40a8e-140">**Advanced commands**</span></span>

- [<span data-ttu-id="40a8e-141">nuget delete</span><span class="sxs-lookup"><span data-stu-id="40a8e-141">nuget delete</span></span>](dotnet-nuget-delete.md)
- [<span data-ttu-id="40a8e-142">nuget locals</span><span class="sxs-lookup"><span data-stu-id="40a8e-142">nuget locals</span></span>](dotnet-nuget-locals.md)
- [<span data-ttu-id="40a8e-143">nuget push</span><span class="sxs-lookup"><span data-stu-id="40a8e-143">nuget push</span></span>](dotnet-nuget-push.md)
- [<span data-ttu-id="40a8e-144">msbuild</span><span class="sxs-lookup"><span data-stu-id="40a8e-144">msbuild</span></span>](dotnet-msbuild.md)
- [<span data-ttu-id="40a8e-145">dotnet install script</span><span class="sxs-lookup"><span data-stu-id="40a8e-145">dotnet install script</span></span>](dotnet-install-script.md)

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="40a8e-146">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="40a8e-146">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="40a8e-147">**Comandos básicos**</span><span class="sxs-lookup"><span data-stu-id="40a8e-147">**Basic commands**</span></span>

- [<span data-ttu-id="40a8e-148">new</span><span class="sxs-lookup"><span data-stu-id="40a8e-148">new</span></span>](dotnet-new.md)
- [<span data-ttu-id="40a8e-149">restore</span><span class="sxs-lookup"><span data-stu-id="40a8e-149">restore</span></span>](dotnet-restore.md)
- [<span data-ttu-id="40a8e-150">build</span><span class="sxs-lookup"><span data-stu-id="40a8e-150">build</span></span>](dotnet-build.md)
- [<span data-ttu-id="40a8e-151">publish</span><span class="sxs-lookup"><span data-stu-id="40a8e-151">publish</span></span>](dotnet-publish.md)
- [<span data-ttu-id="40a8e-152">run</span><span class="sxs-lookup"><span data-stu-id="40a8e-152">run</span></span>](dotnet-run.md)
- [<span data-ttu-id="40a8e-153">test</span><span class="sxs-lookup"><span data-stu-id="40a8e-153">test</span></span>](dotnet-test.md)
- [<span data-ttu-id="40a8e-154">vstest</span><span class="sxs-lookup"><span data-stu-id="40a8e-154">vstest</span></span>](dotnet-vstest.md)
- [<span data-ttu-id="40a8e-155">pack</span><span class="sxs-lookup"><span data-stu-id="40a8e-155">pack</span></span>](dotnet-pack.md)
- [<span data-ttu-id="40a8e-156">migrate</span><span class="sxs-lookup"><span data-stu-id="40a8e-156">migrate</span></span>](dotnet-migrate.md)
- [<span data-ttu-id="40a8e-157">clean</span><span class="sxs-lookup"><span data-stu-id="40a8e-157">clean</span></span>](dotnet-clean.md)
- [<span data-ttu-id="40a8e-158">sln</span><span class="sxs-lookup"><span data-stu-id="40a8e-158">sln</span></span>](dotnet-sln.md)

<span data-ttu-id="40a8e-159">**Comandos de modificación del proyecto**</span><span class="sxs-lookup"><span data-stu-id="40a8e-159">**Project modification commands**</span></span>

- [<span data-ttu-id="40a8e-160">add package</span><span class="sxs-lookup"><span data-stu-id="40a8e-160">add package</span></span>](dotnet-add-package.md)
- [<span data-ttu-id="40a8e-161">add reference</span><span class="sxs-lookup"><span data-stu-id="40a8e-161">add reference</span></span>](dotnet-add-reference.md)
- [<span data-ttu-id="40a8e-162">remove package</span><span class="sxs-lookup"><span data-stu-id="40a8e-162">remove package</span></span>](dotnet-remove-package.md)
- [<span data-ttu-id="40a8e-163">remove reference</span><span class="sxs-lookup"><span data-stu-id="40a8e-163">remove reference</span></span>](dotnet-remove-reference.md)
- [<span data-ttu-id="40a8e-164">list reference</span><span class="sxs-lookup"><span data-stu-id="40a8e-164">list reference</span></span>](dotnet-list-reference.md)

<span data-ttu-id="40a8e-165">**Comandos avanzados**</span><span class="sxs-lookup"><span data-stu-id="40a8e-165">**Advanced commands**</span></span>

- [<span data-ttu-id="40a8e-166">nuget delete</span><span class="sxs-lookup"><span data-stu-id="40a8e-166">nuget delete</span></span>](dotnet-nuget-delete.md)
- [<span data-ttu-id="40a8e-167">nuget locals</span><span class="sxs-lookup"><span data-stu-id="40a8e-167">nuget locals</span></span>](dotnet-nuget-locals.md)
- [<span data-ttu-id="40a8e-168">nuget push</span><span class="sxs-lookup"><span data-stu-id="40a8e-168">nuget push</span></span>](dotnet-nuget-push.md)
- [<span data-ttu-id="40a8e-169">msbuild</span><span class="sxs-lookup"><span data-stu-id="40a8e-169">msbuild</span></span>](dotnet-msbuild.md)
- [<span data-ttu-id="40a8e-170">dotnet install script</span><span class="sxs-lookup"><span data-stu-id="40a8e-170">dotnet install script</span></span>](dotnet-install-script.md)

---

<span data-ttu-id="40a8e-171">La CLI adopta un modelo de extensibilidad que le permite especificar herramientas adicionales para sus proyectos.</span><span class="sxs-lookup"><span data-stu-id="40a8e-171">The CLI adopts an extensibility model that allows you to specify additional tools for your projects.</span></span> <span data-ttu-id="40a8e-172">Para más información, consulte el tema [Modelo de extensibilidad de la CLI de .NET Core](extensibility.md).</span><span class="sxs-lookup"><span data-stu-id="40a8e-172">For more information, see the [.NET Core CLI extensibility model](extensibility.md) topic.</span></span>

## <a name="command-structure"></a><span data-ttu-id="40a8e-173">Estructura de comandos</span><span class="sxs-lookup"><span data-stu-id="40a8e-173">Command structure</span></span>

<span data-ttu-id="40a8e-174">La estructura de comandos de la CLI consta del [controlador ("dotnet")](#driver), [el comando](#command) y posiblemente de los [argumentos de comandos](#arguments) y otras [opciones](#options).</span><span class="sxs-lookup"><span data-stu-id="40a8e-174">CLI command structure consists of [the driver ("dotnet")](#driver), [the command](#command), and possibly command [arguments](#arguments) and [options](#options).</span></span> <span data-ttu-id="40a8e-175">Este patrón se puede ver en la mayoría de las operaciones de la CLI, como la creación de una nueva aplicación de consola y su ejecución desde la línea de comandos, como muestran los siguientes comandos cuando se ejecutan desde un directorio denominado *my_app* :</span><span class="sxs-lookup"><span data-stu-id="40a8e-175">You see this pattern in most CLI operations, such as creating a new console app and running it from the command line as the following commands show when executed from a directory named *my_app*:</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="40a8e-176">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="40a8e-176">.NET Core 2.x</span></span>](#tab/netcore2x)

```dotnetcli
dotnet new console
dotnet build --output /build_output
dotnet /build_output/my_app.dll
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="40a8e-177">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="40a8e-177">.NET Core 1.x</span></span>](#tab/netcore1x)

```dotnetcli
dotnet new console
dotnet restore
dotnet build --output /build_output
dotnet /build_output/my_app.dll
```

---

### <a name="driver"></a><span data-ttu-id="40a8e-178">Controlador</span><span class="sxs-lookup"><span data-stu-id="40a8e-178">Driver</span></span>

<span data-ttu-id="40a8e-179">El controlador se denomina [dotnet](dotnet.md) y tiene dos responsabilidades, ejecutar una [aplicación dependiente del marco](../deploying/index.md) o ejecutar un comando.</span><span class="sxs-lookup"><span data-stu-id="40a8e-179">The driver is named [dotnet](dotnet.md) and has two responsibilities, either running a [framework-dependent app](../deploying/index.md) or executing a command.</span></span> 

<span data-ttu-id="40a8e-180">Para ejecutar una aplicación dependiente del marco, especifique la aplicación después del controlador, por ejemplo, `dotnet /path/to/my_app.dll`.</span><span class="sxs-lookup"><span data-stu-id="40a8e-180">To run a framework-dependent app, specify the app after the driver, for example, `dotnet /path/to/my_app.dll`.</span></span> <span data-ttu-id="40a8e-181">Cuando ejecute el comando desde la carpeta donde reside la DLL de la aplicación, simplemente ejecute `dotnet my_app.dll`.</span><span class="sxs-lookup"><span data-stu-id="40a8e-181">When executing the command from the folder where the app's DLL resides, simply execute `dotnet my_app.dll`.</span></span> <span data-ttu-id="40a8e-182">Si quiere usar una versión específica del entorno de ejecución .NET Core, use la opción `--fx-version <VERSION>` (consulte la referencia del [comando dotnet](dotnet.md)).</span><span class="sxs-lookup"><span data-stu-id="40a8e-182">If you want to use a specific version of the .NET Core Runtime, use the `--fx-version <VERSION>` option (see the [dotnet command](dotnet.md) reference).</span></span>

<span data-ttu-id="40a8e-183">Cuando se proporciona un comando para el controlador, `dotnet.exe` inicia el proceso de ejecución del comando de la CLI.</span><span class="sxs-lookup"><span data-stu-id="40a8e-183">When you supply a command to the driver, `dotnet.exe` starts the CLI command execution process.</span></span> <span data-ttu-id="40a8e-184">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="40a8e-184">For example:</span></span>

```dotnetcli
dotnet build
```

<span data-ttu-id="40a8e-185">En primer lugar, el controlador determina la versión de SDK que se debe usar.</span><span class="sxs-lookup"><span data-stu-id="40a8e-185">First, the driver determines the version of the SDK to use.</span></span> <span data-ttu-id="40a8e-186">Si no hay ningún elemento ["global.json"](global-json.md), se usa la última versión del SDK disponible.</span><span class="sxs-lookup"><span data-stu-id="40a8e-186">If there is no ['global.json'](global-json.md), the latest version of the SDK available is used.</span></span> <span data-ttu-id="40a8e-187">Podría tratarse de una versión preliminar o de una versión estable, en función de lo último que esté disponible en el equipo.</span><span class="sxs-lookup"><span data-stu-id="40a8e-187">This might be either a preview or stable version, depending on what is latest on the machine.</span></span>  <span data-ttu-id="40a8e-188">Una vez determinada la versión del SDK, se ejecutará el comando.</span><span class="sxs-lookup"><span data-stu-id="40a8e-188">Once the SDK version is determined, it executes the command.</span></span>

### <a name="command"></a><span data-ttu-id="40a8e-189">Comando</span><span class="sxs-lookup"><span data-stu-id="40a8e-189">Command</span></span>

<span data-ttu-id="40a8e-190">El comando realiza una acción.</span><span class="sxs-lookup"><span data-stu-id="40a8e-190">The command performs an action.</span></span> <span data-ttu-id="40a8e-191">Por ejemplo, `dotnet build` compila código.</span><span class="sxs-lookup"><span data-stu-id="40a8e-191">For example, `dotnet build` builds code.</span></span> <span data-ttu-id="40a8e-192">`dotnet publish` publica el código.</span><span class="sxs-lookup"><span data-stu-id="40a8e-192">`dotnet publish` publishes code.</span></span> <span data-ttu-id="40a8e-193">Los comandos se implementan como una aplicación de consola usando una convención `dotnet {command}`.</span><span class="sxs-lookup"><span data-stu-id="40a8e-193">The commands are implemented as a console application using a `dotnet {command}` convention.</span></span>

### <a name="arguments"></a><span data-ttu-id="40a8e-194">Argumentos</span><span class="sxs-lookup"><span data-stu-id="40a8e-194">Arguments</span></span>

<span data-ttu-id="40a8e-195">Los argumentos que se pasan en la línea de comandos son los argumentos para el comando invocado.</span><span class="sxs-lookup"><span data-stu-id="40a8e-195">The arguments you pass on the command line are the arguments to the command invoked.</span></span> <span data-ttu-id="40a8e-196">Por ejemplo, cuando ejecuta `dotnet publish my_app.csproj`, el argumento `my_app.csproj` indica el proyecto que se publicará y se pasará al comando `publish`.</span><span class="sxs-lookup"><span data-stu-id="40a8e-196">For example when you execute `dotnet publish my_app.csproj`, the `my_app.csproj` argument indicates the project to publish and is passed to the `publish` command.</span></span>

### <a name="options"></a><span data-ttu-id="40a8e-197">Opciones</span><span class="sxs-lookup"><span data-stu-id="40a8e-197">Options</span></span>

<span data-ttu-id="40a8e-198">Las opciones que se pasan en la línea de comandos son las opciones para el comando que se invoca.</span><span class="sxs-lookup"><span data-stu-id="40a8e-198">The options you pass on the command line are the options to the command invoked.</span></span> <span data-ttu-id="40a8e-199">Por ejemplo, cuando ejecuta `dotnet publish --output /build_output`, la opción `--output` y su valor se pasan al comando `publish`.</span><span class="sxs-lookup"><span data-stu-id="40a8e-199">For example when you execute `dotnet publish --output /build_output`, the `--output` option and its value are passed to the `publish` command.</span></span>

## <a name="migration-from-projectjson"></a><span data-ttu-id="40a8e-200">Migración desde project.json</span><span class="sxs-lookup"><span data-stu-id="40a8e-200">Migration from project.json</span></span>

<span data-ttu-id="40a8e-201">Si usó herramientas de la versión preliminar 2 para producir proyectos basados en *project.json*, consulte el tema sobre [dotnet migrate](dotnet-migrate.md) para más información sobre cómo migrar su proyecto a MSBuild/ *.csproj*  para usarlo con herramientas de versión.</span><span class="sxs-lookup"><span data-stu-id="40a8e-201">If you used Preview 2 tooling to produce *project.json*-based projects, consult the [dotnet migrate](dotnet-migrate.md) topic for information on migrating your project to MSBuild/*.csproj* for use with release tooling.</span></span> <span data-ttu-id="40a8e-202">Para los proyectos de .NET Core creados antes del lanzamiento de las herramientas de la versión preliminar 2, actualice manualmente el proyecto siguiendo las instrucciones que se indican en [Migración de DNX a CLI de .NET Core (project.json)](../migration/from-dnx.md) y, luego, use `dotnet migrate` o actualice directamente los proyectos.</span><span class="sxs-lookup"><span data-stu-id="40a8e-202">For .NET Core projects created prior to the release of Preview 2 tooling, either manually update the project following the guidance in [Migrating from DNX to .NET Core CLI (project.json)](../migration/from-dnx.md) and then use `dotnet migrate` or directly upgrade your projects.</span></span>

## <a name="see-also"></a><span data-ttu-id="40a8e-203">Vea también</span><span class="sxs-lookup"><span data-stu-id="40a8e-203">See also</span></span>

- [<span data-ttu-id="40a8e-204">dotnet/repositorio de GitHub de la CLI</span><span class="sxs-lookup"><span data-stu-id="40a8e-204">dotnet/CLI GitHub Repository</span></span>](https://github.com/dotnet/cli/)
- <span data-ttu-id="40a8e-205">[.NET Core installation guide](https://aka.ms/dotnetcoregs) (Guía de instalación de .NET Core)</span><span class="sxs-lookup"><span data-stu-id="40a8e-205">[.NET Core installation guide](https://aka.ms/dotnetcoregs)</span></span>
