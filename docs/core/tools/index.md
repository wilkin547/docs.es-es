---
title: Herramientas de la interfaz de línea de comandos (CLI) de .NET Core
description: Introducción a las herramientas y características de la interfaz de la línea de comandos (CLI) de .NET Core.
ms.date: 08/14/2017
ms.custom: seodec18
---
# <a name="net-core-command-line-interface-cli-tools"></a><span data-ttu-id="f81b8-103">Herramientas de la interfaz de la línea de comandos (CLI) de .NET Core</span><span class="sxs-lookup"><span data-stu-id="f81b8-103">.NET Core command-line interface (CLI) tools</span></span>

<span data-ttu-id="f81b8-104">La interfaz de la línea de comandos (CLI) de .NET Core es una nueva cadena de herramientas multiplataforma para el desarrollo de aplicaciones. NET.</span><span class="sxs-lookup"><span data-stu-id="f81b8-104">The .NET Core command-line interface (CLI) is a new cross-platform toolchain for developing .NET applications.</span></span> <span data-ttu-id="f81b8-105">La CLI es una base sobre la que pueden descansar herramientas de nivel superior, como los entornos de desarrollo integrados (IDE), los editores y los orquestadores de compilación.</span><span class="sxs-lookup"><span data-stu-id="f81b8-105">The CLI is a foundation upon which higher-level tools, such as Integrated Development Environments (IDEs), editors, and build orchestrators, can rest.</span></span>

## <a name="installation"></a><span data-ttu-id="f81b8-106">Instalación</span><span class="sxs-lookup"><span data-stu-id="f81b8-106">Installation</span></span>

<span data-ttu-id="f81b8-107">Puede usar los instaladores nativos o los scripts de shell de instalación:</span><span class="sxs-lookup"><span data-stu-id="f81b8-107">Either use the native installers or use the installation shell scripts:</span></span>

* <span data-ttu-id="f81b8-108">Los instaladores nativos se usan principalmente en máquinas del desarrollador y usan el mecanismo de instalación nativo de cada plataforma compatible, por ejemplo, los paquetes DEB en Ubuntu o los paquetes MSI en Windows.</span><span class="sxs-lookup"><span data-stu-id="f81b8-108">The native installers are primarily used on developer's machines and use each supported platform's native install mechanism, for instance, DEB packages on Ubuntu or MSI bundles on Windows.</span></span> <span data-ttu-id="f81b8-109">Estos instaladores instalan y configuran el entorno para su uso inmediato por el desarrollador, pero requieren privilegios administrativos en la máquina.</span><span class="sxs-lookup"><span data-stu-id="f81b8-109">These installers install and configure the environment for immediate use by the developer but require administrative privileges on the machine.</span></span> <span data-ttu-id="f81b8-110">Puede ver las instrucciones de instalación en la [Guía de instalación de .NET Core](https://aka.ms/dotnetcoregs).</span><span class="sxs-lookup"><span data-stu-id="f81b8-110">You can view the installation instructions in the [.NET Core installation guide](https://aka.ms/dotnetcoregs).</span></span>
* <span data-ttu-id="f81b8-111">Los scripts de shell se usan principalmente para configurar servidores de compilación o cuando desee instalar las herramientas sin privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="f81b8-111">Shell scripts are primarily used for setting up build servers or when you wish to install the tools without administrative privileges.</span></span> <span data-ttu-id="f81b8-112">Los scripts de instalación no instalan los requisitos previos en la máquina, se deben instalar manualmente.</span><span class="sxs-lookup"><span data-stu-id="f81b8-112">Install scripts don't install prerequisites on the machine, which must be installed manually.</span></span> <span data-ttu-id="f81b8-113">Para más información, consulte el [tema de referencia sobre los scripts de instalación](dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="f81b8-113">For more information, see the [install script reference topic](dotnet-install-script.md).</span></span> <span data-ttu-id="f81b8-114">Para más información sobre cómo configurar la CLI en el servidor de compilación de integración continua (CI), consulte [Uso de .NET Core SDK y herramientas de integración continua (CI)](using-ci-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="f81b8-114">For information on how to set up CLI on your continuous integration (CI) build server, see [Using .NET Core SDK and tools in Continuous Integration (CI)](using-ci-with-cli.md).</span></span>

<span data-ttu-id="f81b8-115">De forma predeterminada, la CLI se instala en paralelo (SxS), para que varias versiones de las herramientas de la CLI puedan coexistir en una única máquina.</span><span class="sxs-lookup"><span data-stu-id="f81b8-115">By default, the CLI installs in a side-by-side (SxS) manner, so multiple versions of the CLI tools can coexist on a single machine.</span></span> <span data-ttu-id="f81b8-116">En la sección [Controlador](#driver) se explica más detalladamente cómo determinar qué versión usar en una máquina en la que hay varias versiones instaladas.</span><span class="sxs-lookup"><span data-stu-id="f81b8-116">Determining which version is used on a machine where multiple versions are installed is explained in more detail in the [Driver](#driver) section.</span></span>

## <a name="cli-commands"></a><span data-ttu-id="f81b8-117">Comandos de la CLI</span><span class="sxs-lookup"><span data-stu-id="f81b8-117">CLI commands</span></span>

<span data-ttu-id="f81b8-118">De forma predeterminada, se instalan los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="f81b8-118">The following commands are installed by default:</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="f81b8-119">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="f81b8-119">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="f81b8-120">**Comandos básicos**</span><span class="sxs-lookup"><span data-stu-id="f81b8-120">**Basic commands**</span></span>

* [<span data-ttu-id="f81b8-121">new</span><span class="sxs-lookup"><span data-stu-id="f81b8-121">new</span></span>](dotnet-new.md)
* [<span data-ttu-id="f81b8-122">restore</span><span class="sxs-lookup"><span data-stu-id="f81b8-122">restore</span></span>](dotnet-restore.md)
* [<span data-ttu-id="f81b8-123">build</span><span class="sxs-lookup"><span data-stu-id="f81b8-123">build</span></span>](dotnet-build.md)
* [<span data-ttu-id="f81b8-124">publish</span><span class="sxs-lookup"><span data-stu-id="f81b8-124">publish</span></span>](dotnet-publish.md)
* [<span data-ttu-id="f81b8-125">run</span><span class="sxs-lookup"><span data-stu-id="f81b8-125">run</span></span>](dotnet-run.md)
* [<span data-ttu-id="f81b8-126">test</span><span class="sxs-lookup"><span data-stu-id="f81b8-126">test</span></span>](dotnet-test.md)
* [<span data-ttu-id="f81b8-127">vstest</span><span class="sxs-lookup"><span data-stu-id="f81b8-127">vstest</span></span>](dotnet-vstest.md)
* [<span data-ttu-id="f81b8-128">pack</span><span class="sxs-lookup"><span data-stu-id="f81b8-128">pack</span></span>](dotnet-pack.md)
* [<span data-ttu-id="f81b8-129">migrate</span><span class="sxs-lookup"><span data-stu-id="f81b8-129">migrate</span></span>](dotnet-migrate.md)
* [<span data-ttu-id="f81b8-130">clean</span><span class="sxs-lookup"><span data-stu-id="f81b8-130">clean</span></span>](dotnet-clean.md)
* [<span data-ttu-id="f81b8-131">sln</span><span class="sxs-lookup"><span data-stu-id="f81b8-131">sln</span></span>](dotnet-sln.md)
* [<span data-ttu-id="f81b8-132">help</span><span class="sxs-lookup"><span data-stu-id="f81b8-132">help</span></span>](dotnet-help.md)
* [<span data-ttu-id="f81b8-133">store</span><span class="sxs-lookup"><span data-stu-id="f81b8-133">store</span></span>](dotnet-store.md)

<span data-ttu-id="f81b8-134">**Comandos de modificación del proyecto**</span><span class="sxs-lookup"><span data-stu-id="f81b8-134">**Project modification commands**</span></span>

* [<span data-ttu-id="f81b8-135">add package</span><span class="sxs-lookup"><span data-stu-id="f81b8-135">add package</span></span>](dotnet-add-package.md)
* [<span data-ttu-id="f81b8-136">add reference</span><span class="sxs-lookup"><span data-stu-id="f81b8-136">add reference</span></span>](dotnet-add-reference.md)
* [<span data-ttu-id="f81b8-137">remove package</span><span class="sxs-lookup"><span data-stu-id="f81b8-137">remove package</span></span>](dotnet-remove-package.md)
* [<span data-ttu-id="f81b8-138">remove reference</span><span class="sxs-lookup"><span data-stu-id="f81b8-138">remove reference</span></span>](dotnet-remove-reference.md)
* [<span data-ttu-id="f81b8-139">list reference</span><span class="sxs-lookup"><span data-stu-id="f81b8-139">list reference</span></span>](dotnet-list-reference.md)

<span data-ttu-id="f81b8-140">**Comandos avanzados**</span><span class="sxs-lookup"><span data-stu-id="f81b8-140">**Advanced commands**</span></span>

* [<span data-ttu-id="f81b8-141">nuget delete</span><span class="sxs-lookup"><span data-stu-id="f81b8-141">nuget delete</span></span>](dotnet-nuget-delete.md)
* [<span data-ttu-id="f81b8-142">nuget locals</span><span class="sxs-lookup"><span data-stu-id="f81b8-142">nuget locals</span></span>](dotnet-nuget-locals.md)
* [<span data-ttu-id="f81b8-143">nuget push</span><span class="sxs-lookup"><span data-stu-id="f81b8-143">nuget push</span></span>](dotnet-nuget-push.md)
* [<span data-ttu-id="f81b8-144">msbuild</span><span class="sxs-lookup"><span data-stu-id="f81b8-144">msbuild</span></span>](dotnet-msbuild.md)
* [<span data-ttu-id="f81b8-145">dotnet install script</span><span class="sxs-lookup"><span data-stu-id="f81b8-145">dotnet install script</span></span>](dotnet-install-script.md)

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="f81b8-146">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="f81b8-146">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="f81b8-147">**Comandos básicos**</span><span class="sxs-lookup"><span data-stu-id="f81b8-147">**Basic commands**</span></span>

* [<span data-ttu-id="f81b8-148">new</span><span class="sxs-lookup"><span data-stu-id="f81b8-148">new</span></span>](dotnet-new.md)
* [<span data-ttu-id="f81b8-149">restore</span><span class="sxs-lookup"><span data-stu-id="f81b8-149">restore</span></span>](dotnet-restore.md)
* [<span data-ttu-id="f81b8-150">build</span><span class="sxs-lookup"><span data-stu-id="f81b8-150">build</span></span>](dotnet-build.md)
* [<span data-ttu-id="f81b8-151">publish</span><span class="sxs-lookup"><span data-stu-id="f81b8-151">publish</span></span>](dotnet-publish.md)
* [<span data-ttu-id="f81b8-152">run</span><span class="sxs-lookup"><span data-stu-id="f81b8-152">run</span></span>](dotnet-run.md)
* [<span data-ttu-id="f81b8-153">test</span><span class="sxs-lookup"><span data-stu-id="f81b8-153">test</span></span>](dotnet-test.md)
* [<span data-ttu-id="f81b8-154">vstest</span><span class="sxs-lookup"><span data-stu-id="f81b8-154">vstest</span></span>](dotnet-vstest.md)
* [<span data-ttu-id="f81b8-155">pack</span><span class="sxs-lookup"><span data-stu-id="f81b8-155">pack</span></span>](dotnet-pack.md)
* [<span data-ttu-id="f81b8-156">migrate</span><span class="sxs-lookup"><span data-stu-id="f81b8-156">migrate</span></span>](dotnet-migrate.md)
* [<span data-ttu-id="f81b8-157">clean</span><span class="sxs-lookup"><span data-stu-id="f81b8-157">clean</span></span>](dotnet-clean.md)
* [<span data-ttu-id="f81b8-158">sln</span><span class="sxs-lookup"><span data-stu-id="f81b8-158">sln</span></span>](dotnet-sln.md)

<span data-ttu-id="f81b8-159">**Comandos de modificación del proyecto**</span><span class="sxs-lookup"><span data-stu-id="f81b8-159">**Project modification commands**</span></span>

* [<span data-ttu-id="f81b8-160">add package</span><span class="sxs-lookup"><span data-stu-id="f81b8-160">add package</span></span>](dotnet-add-package.md)
* [<span data-ttu-id="f81b8-161">add reference</span><span class="sxs-lookup"><span data-stu-id="f81b8-161">add reference</span></span>](dotnet-add-reference.md)
* [<span data-ttu-id="f81b8-162">remove package</span><span class="sxs-lookup"><span data-stu-id="f81b8-162">remove package</span></span>](dotnet-remove-package.md)
* [<span data-ttu-id="f81b8-163">remove reference</span><span class="sxs-lookup"><span data-stu-id="f81b8-163">remove reference</span></span>](dotnet-remove-reference.md)
* [<span data-ttu-id="f81b8-164">list reference</span><span class="sxs-lookup"><span data-stu-id="f81b8-164">list reference</span></span>](dotnet-list-reference.md)

<span data-ttu-id="f81b8-165">**Comandos avanzados**</span><span class="sxs-lookup"><span data-stu-id="f81b8-165">**Advanced commands**</span></span>

* [<span data-ttu-id="f81b8-166">nuget delete</span><span class="sxs-lookup"><span data-stu-id="f81b8-166">nuget delete</span></span>](dotnet-nuget-delete.md)
* [<span data-ttu-id="f81b8-167">nuget locals</span><span class="sxs-lookup"><span data-stu-id="f81b8-167">nuget locals</span></span>](dotnet-nuget-locals.md)
* [<span data-ttu-id="f81b8-168">nuget push</span><span class="sxs-lookup"><span data-stu-id="f81b8-168">nuget push</span></span>](dotnet-nuget-push.md)
* [<span data-ttu-id="f81b8-169">msbuild</span><span class="sxs-lookup"><span data-stu-id="f81b8-169">msbuild</span></span>](dotnet-msbuild.md)
* [<span data-ttu-id="f81b8-170">dotnet install script</span><span class="sxs-lookup"><span data-stu-id="f81b8-170">dotnet install script</span></span>](dotnet-install-script.md)

---

<span data-ttu-id="f81b8-171">La CLI adopta un modelo de extensibilidad que le permite especificar herramientas adicionales para sus proyectos.</span><span class="sxs-lookup"><span data-stu-id="f81b8-171">The CLI adopts an extensibility model that allows you to specify additional tools for your projects.</span></span> <span data-ttu-id="f81b8-172">Para más información, consulte el tema [Modelo de extensibilidad de la CLI de .NET Core](extensibility.md).</span><span class="sxs-lookup"><span data-stu-id="f81b8-172">For more information, see the [.NET Core CLI extensibility model](extensibility.md) topic.</span></span>

## <a name="command-structure"></a><span data-ttu-id="f81b8-173">Estructura de comandos</span><span class="sxs-lookup"><span data-stu-id="f81b8-173">Command structure</span></span>

<span data-ttu-id="f81b8-174">La estructura de comandos de la CLI consta del [controlador ("dotnet")](#driver), [el comando (o "verbo")](#command-verb) y posiblemente de los [argumentos de comandos](#arguments) y otras [opciones](#options).</span><span class="sxs-lookup"><span data-stu-id="f81b8-174">CLI command structure consists of [the driver ("dotnet")](#driver), [the command (or "verb")](#command-verb), and possibly command [arguments](#arguments) and [options](#options).</span></span> <span data-ttu-id="f81b8-175">Este patrón se puede ver en la mayoría de las operaciones de la CLI, como la creación de una nueva aplicación de consola y su ejecución desde la línea de comandos, como muestran los siguientes comandos cuando se ejecutan desde un directorio denominado *my_app* :</span><span class="sxs-lookup"><span data-stu-id="f81b8-175">You see this pattern in most CLI operations, such as creating a new console app and running it from the command line as the following commands show when executed from a directory named *my_app*:</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="f81b8-176">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="f81b8-176">.NET Core 2.x</span></span>](#tab/netcore2x)

```console
dotnet new console
dotnet build --output /build_output
dotnet /build_output/my_app.dll
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="f81b8-177">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="f81b8-177">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet new console
dotnet restore
dotnet build --output /build_output
dotnet /build_output/my_app.dll
```

---

### <a name="driver"></a><span data-ttu-id="f81b8-178">Controlador</span><span class="sxs-lookup"><span data-stu-id="f81b8-178">Driver</span></span>

<span data-ttu-id="f81b8-179">El controlador se denomina [dotnet](dotnet.md) y tiene dos responsabilidades, ejecutar una [aplicación dependiente del marco](../deploying/index.md) o ejecutar un comando.</span><span class="sxs-lookup"><span data-stu-id="f81b8-179">The driver is named [dotnet](dotnet.md) and has two responsibilities, either running a [framework-dependent app](../deploying/index.md) or executing a command.</span></span> <span data-ttu-id="f81b8-180">La única vez que se usa `dotnet` sin un comando es cuando se usa para iniciar una aplicación.</span><span class="sxs-lookup"><span data-stu-id="f81b8-180">The only time `dotnet` is used without a command is when it's used to start an application.</span></span>

<span data-ttu-id="f81b8-181">Para ejecutar una aplicación dependiente del marco, especifique la aplicación después del controlador, por ejemplo, `dotnet /path/to/my_app.dll`.</span><span class="sxs-lookup"><span data-stu-id="f81b8-181">To run a framework-dependent app, specify the app after the driver, for example, `dotnet /path/to/my_app.dll`.</span></span> <span data-ttu-id="f81b8-182">Cuando ejecute el comando desde la carpeta donde reside la DLL de la aplicación, simplemente ejecute `dotnet my_app.dll`.</span><span class="sxs-lookup"><span data-stu-id="f81b8-182">When executing the command from the folder where the app's DLL resides, simply execute `dotnet my_app.dll`.</span></span>

<span data-ttu-id="f81b8-183">Cuando se proporciona un comando para el controlador, `dotnet.exe` inicia el proceso de ejecución del comando de la CLI.</span><span class="sxs-lookup"><span data-stu-id="f81b8-183">When you supply a command to the driver, `dotnet.exe` starts the CLI command execution process.</span></span> <span data-ttu-id="f81b8-184">En primer lugar, el controlador determina la versión de SDK que se debe usar.</span><span class="sxs-lookup"><span data-stu-id="f81b8-184">First, the driver determines the version of the SDK to use.</span></span> <span data-ttu-id="f81b8-185">Si no se especifica la versión en las opciones de comando, el controlador usa la versión más reciente que esté disponible.</span><span class="sxs-lookup"><span data-stu-id="f81b8-185">If the version isn't specified in the command options, the driver uses the latest version available.</span></span> <span data-ttu-id="f81b8-186">Para especificar una versión distinta de la última versión instalada, use la opción `--fx-version <VERSION>` (consulte la referencia del [comando dotnet)](dotnet.md).</span><span class="sxs-lookup"><span data-stu-id="f81b8-186">To specify a version other than the latest installed version, use the `--fx-version <VERSION>` option (see the [dotnet command](dotnet.md) reference).</span></span> <span data-ttu-id="f81b8-187">Una vez determinada la versión del SDK, el controlador ejecuta el comando.</span><span class="sxs-lookup"><span data-stu-id="f81b8-187">Once the SDK version is determined, the driver executes the command.</span></span>

### <a name="command-verb"></a><span data-ttu-id="f81b8-188">Comando ("verbo")</span><span class="sxs-lookup"><span data-stu-id="f81b8-188">Command ("verb")</span></span>

<span data-ttu-id="f81b8-189">El comando (o "verbo") es simplemente un comando que realiza una acción.</span><span class="sxs-lookup"><span data-stu-id="f81b8-189">The command (or "verb") is simply a command that performs an action.</span></span> <span data-ttu-id="f81b8-190">Por ejemplo, `dotnet build` compila el código.</span><span class="sxs-lookup"><span data-stu-id="f81b8-190">For example, `dotnet build` builds your code.</span></span> <span data-ttu-id="f81b8-191">`dotnet publish` publica el código.</span><span class="sxs-lookup"><span data-stu-id="f81b8-191">`dotnet publish` publishes your code.</span></span> <span data-ttu-id="f81b8-192">Los comandos se implementan como una aplicación de consola usando una convención `dotnet {verb}`.</span><span class="sxs-lookup"><span data-stu-id="f81b8-192">The commands are implemented as a console application using a `dotnet {verb}` convention.</span></span>

### <a name="arguments"></a><span data-ttu-id="f81b8-193">Argumentos</span><span class="sxs-lookup"><span data-stu-id="f81b8-193">Arguments</span></span>

<span data-ttu-id="f81b8-194">Los argumentos que se pasan en la línea de comandos son los argumentos para el comando invocado.</span><span class="sxs-lookup"><span data-stu-id="f81b8-194">The arguments you pass on the command line are the arguments to the command invoked.</span></span> <span data-ttu-id="f81b8-195">Por ejemplo, cuando ejecuta `dotnet publish my_app.csproj`, el argumento `my_app.csproj` indica el proyecto que se publicará y se pasará al comando `publish`.</span><span class="sxs-lookup"><span data-stu-id="f81b8-195">For example when you execute `dotnet publish my_app.csproj`, the `my_app.csproj` argument indicates the project to publish and is passed to the `publish` command.</span></span>

### <a name="options"></a><span data-ttu-id="f81b8-196">Opciones</span><span class="sxs-lookup"><span data-stu-id="f81b8-196">Options</span></span>

<span data-ttu-id="f81b8-197">Las opciones que se pasan en la línea de comandos son las opciones para el comando que se invoca.</span><span class="sxs-lookup"><span data-stu-id="f81b8-197">The options you pass on the command line are the options to the command invoked.</span></span> <span data-ttu-id="f81b8-198">Por ejemplo, cuando ejecuta `dotnet publish --output /build_output`, la opción `--output` y su valor se pasan al comando `publish`.</span><span class="sxs-lookup"><span data-stu-id="f81b8-198">For example when you execute `dotnet publish --output /build_output`, the `--output` option and its value are passed to the `publish` command.</span></span>

## <a name="migration-from-projectjson"></a><span data-ttu-id="f81b8-199">Migración desde project.json</span><span class="sxs-lookup"><span data-stu-id="f81b8-199">Migration from project.json</span></span>

<span data-ttu-id="f81b8-200">Si usó herramientas de la versión preliminar 2 para producir proyectos basados en *project.json*, consulte el tema sobre [dotnet migrate](dotnet-migrate.md) para más información sobre cómo migrar su proyecto a MSBuild/*.csproj*  para usarlo con herramientas de versión.</span><span class="sxs-lookup"><span data-stu-id="f81b8-200">If you used Preview 2 tooling to produce *project.json*-based projects, consult the [dotnet migrate](dotnet-migrate.md) topic for information on migrating your project to MSBuild/*.csproj* for use with release tooling.</span></span> <span data-ttu-id="f81b8-201">Para los proyectos de .NET Core creados antes del lanzamiento de las herramientas de la versión preliminar 2, actualice manualmente el proyecto siguiendo las instrucciones que se indican en [Migración de DNX a CLI de .NET Core (project.json)](../migration/from-dnx.md) y, luego, use `dotnet migrate` o actualice directamente los proyectos.</span><span class="sxs-lookup"><span data-stu-id="f81b8-201">For .NET Core projects created prior to the release of Preview 2 tooling, either manually update the project following the guidance in [Migrating from DNX to .NET Core CLI (project.json)](../migration/from-dnx.md) and then use `dotnet migrate` or directly upgrade your projects.</span></span>

## <a name="see-also"></a><span data-ttu-id="f81b8-202">Vea también</span><span class="sxs-lookup"><span data-stu-id="f81b8-202">See also</span></span>

- [<span data-ttu-id="f81b8-203">dotnet/repositorio de GitHub de la CLI</span><span class="sxs-lookup"><span data-stu-id="f81b8-203">dotnet/CLI GitHub Repository</span></span>](https://github.com/dotnet/cli/)
- <span data-ttu-id="f81b8-204">[.NET Core installation guide](https://aka.ms/dotnetcoregs) (Guía de instalación de .NET Core)</span><span class="sxs-lookup"><span data-stu-id="f81b8-204">[.NET Core installation guide](https://aka.ms/dotnetcoregs)</span></span>
