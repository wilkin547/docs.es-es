---
title: Comando dotnet restore
description: Aprenda a restaurar dependencias y herramientas específicas del proyecto con el comando dotnet restore.
ms.date: 02/27/2020
ms.openlocfilehash: f49f0cda4424a4cc54ab7d4d4c6f729919dc7e60
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463431"
---
# <a name="dotnet-restore"></a><span data-ttu-id="c421d-103">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="c421d-103">dotnet restore</span></span>

<span data-ttu-id="c421d-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.1 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="c421d-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="c421d-105">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="c421d-105">Name</span></span>

<span data-ttu-id="c421d-106">`dotnet restore`: restaura las dependencias y las herramientas de un proyecto.</span><span class="sxs-lookup"><span data-stu-id="c421d-106">`dotnet restore` - Restores the dependencies and tools of a project.</span></span>

## <a name="synopsis"></a><span data-ttu-id="c421d-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="c421d-107">Synopsis</span></span>

```dotnetcli
dotnet restore [<ROOT>] [--configfile <FILE>] [--disable-parallel]
    [-f|--force] [--force-evaluate] [--ignore-failed-sources]
    [--interactive] [--lock-file-path <LOCK_FILE_PATH>] [--locked-mode]
    [--no-cache] [--no-dependencies] [--packages <PACKAGES_DIRECTORY>]
    [-r|--runtime <RUNTIME_IDENTIFIER>] [-s|--source <SOURCE>]
    [--use-lockfile] [-v|--verbosity <LEVEL>]

dotnet restore -h|--help
```

## <a name="description"></a><span data-ttu-id="c421d-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="c421d-108">Description</span></span>

<span data-ttu-id="c421d-109">El comando `dotnet restore` usa NuGet para restaurar las dependencias, así como las herramientas específicas del proyecto que se especifican en el archivo project.json.</span><span class="sxs-lookup"><span data-stu-id="c421d-109">The `dotnet restore` command uses NuGet to restore dependencies as well as project-specific tools that are specified in the project file.</span></span> <span data-ttu-id="c421d-110">De forma predeterminada, la restauración de dependencias y herramientas se ejecuta en paralelo.</span><span class="sxs-lookup"><span data-stu-id="c421d-110">By default, the restoration of dependencies and tools are executed in parallel.</span></span>

<span data-ttu-id="c421d-111">Para restaurar las dependencias, NuGet necesita las fuentes donde se encuentran los paquetes.</span><span class="sxs-lookup"><span data-stu-id="c421d-111">To restore the dependencies, NuGet needs the feeds where the packages are located.</span></span> <span data-ttu-id="c421d-112">Las fuente se proporcionan normalmente mediante el archivo de configuración *nuget.config*.</span><span class="sxs-lookup"><span data-stu-id="c421d-112">Feeds are usually provided via the *nuget.config* configuration file.</span></span> <span data-ttu-id="c421d-113">Cuando se instala el SDK de .NET Core, se proporciona un archivo de configuración predeterminado.</span><span class="sxs-lookup"><span data-stu-id="c421d-113">A default configuration file is provided when the .NET Core SDK is installed.</span></span> <span data-ttu-id="c421d-114">Puede especificar más fuentes creando su propio archivo *nuget.config* en el directorio del proyecto.</span><span class="sxs-lookup"><span data-stu-id="c421d-114">You specify additional feeds by creating your own *nuget.config* file in the project directory.</span></span> <span data-ttu-id="c421d-115">Puede invalidar las fuentes *nuget.config* con la opción - `-s`.</span><span class="sxs-lookup"><span data-stu-id="c421d-115">You can override the *nuget.config* feeds with the - `-s` option.</span></span>

<span data-ttu-id="c421d-116">Para las dependencias, puede especificar dónde se colocan los paquetes restaurados durante la operación de restauración mediante el argumento `--packages`.</span><span class="sxs-lookup"><span data-stu-id="c421d-116">For dependencies, you specify where the restored packages are placed during the restore operation using the `--packages` argument.</span></span> <span data-ttu-id="c421d-117">Si no se especifica, se usa la caché de paquetes NuGet predeterminada, que se encuentra en el directorio `.nuget/packages` del directorio de inicio del usuario en todos los sistemas operativos.</span><span class="sxs-lookup"><span data-stu-id="c421d-117">If not specified, the default NuGet package cache is used, which is found in the `.nuget/packages` directory in the user's home directory on all operating systems.</span></span> <span data-ttu-id="c421d-118">Por ejemplo, */home/usuario1* en Linux o *C:\Usuarios\usuario1* en Windows.</span><span class="sxs-lookup"><span data-stu-id="c421d-118">For example, */home/user1* on Linux or *C:\Users\user1* on Windows.</span></span>

<span data-ttu-id="c421d-119">Para herramientas específicas del proyecto, `dotnet restore` restaura primero el paquete en el que se empaqueta la herramienta y, a continuación, continúa con la restauración de las dependencias de la herramienta especificadas en su project.json.</span><span class="sxs-lookup"><span data-stu-id="c421d-119">For project-specific tooling, `dotnet restore` first restores the package in which the tool is packed, and then proceeds to restore the tool's dependencies as specified in its project file.</span></span>

### <a name="nugetconfig-differences"></a><span data-ttu-id="c421d-120">Diferencias de nuget.config</span><span class="sxs-lookup"><span data-stu-id="c421d-120">nuget.config differences</span></span>

<span data-ttu-id="c421d-121">El comportamiento del comando `dotnet restore` depende de las opciones de configuración del archivo *nuget.config*, si existe.</span><span class="sxs-lookup"><span data-stu-id="c421d-121">The behavior of the `dotnet restore` command is affected by the settings in the *nuget.config* file, if present.</span></span> <span data-ttu-id="c421d-122">Por ejemplo, establecer `globalPackagesFolder` en *nuget.config* coloca los paquetes NuGet restaurados en la carpeta especificada.</span><span class="sxs-lookup"><span data-stu-id="c421d-122">For example, setting the `globalPackagesFolder` in *nuget.config* places the restored NuGet packages in the specified folder.</span></span> <span data-ttu-id="c421d-123">Esta es una alternativa para especificar la opción `--packages` en el comando `dotnet restore`.</span><span class="sxs-lookup"><span data-stu-id="c421d-123">This is an alternative to specifying the `--packages` option on the `dotnet restore` command.</span></span> <span data-ttu-id="c421d-124">Para más información, consulte la [referencia de nuget.config](/nuget/schema/nuget-config-file).</span><span class="sxs-lookup"><span data-stu-id="c421d-124">For more information, see the [nuget.config reference](/nuget/schema/nuget-config-file).</span></span>

<span data-ttu-id="c421d-125">Hay tres configuraciones específicas que `dotnet restore` omite:</span><span class="sxs-lookup"><span data-stu-id="c421d-125">There are three specific settings that `dotnet restore` ignores:</span></span>

- [<span data-ttu-id="c421d-126">bindingRedirects</span><span class="sxs-lookup"><span data-stu-id="c421d-126">bindingRedirects</span></span>](/nuget/schema/nuget-config-file#bindingredirects-section)

  <span data-ttu-id="c421d-127">Los redireccionamientos de enlace no funcionan con elementos de `<PackageReference>` y .NET Core solo admite elementos de `<PackageReference>` para los paquetes NuGet.</span><span class="sxs-lookup"><span data-stu-id="c421d-127">Binding redirects don't work with `<PackageReference>` elements and .NET Core only supports `<PackageReference>` elements for NuGet packages.</span></span>

- [<span data-ttu-id="c421d-128">solution</span><span class="sxs-lookup"><span data-stu-id="c421d-128">solution</span></span>](/nuget/schema/nuget-config-file#solution-section)

  <span data-ttu-id="c421d-129">Esta configuración es específica para Visual Studio y no se aplica a .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c421d-129">This setting is Visual Studio specific and doesn't apply to .NET Core.</span></span> <span data-ttu-id="c421d-130">.NET Core no usa un archivo `packages.config` y, en su lugar, usa elementos de `<PackageReference>` para los paquetes NuGet.</span><span class="sxs-lookup"><span data-stu-id="c421d-130">.NET Core doesn't use a `packages.config` file and instead uses `<PackageReference>` elements for NuGet packages.</span></span>

- [<span data-ttu-id="c421d-131">trustedSigners</span><span class="sxs-lookup"><span data-stu-id="c421d-131">trustedSigners</span></span>](/nuget/schema/nuget-config-file#trustedsigners-section)

  <span data-ttu-id="c421d-132">Esta configuración no es aplicable porque [NuGet ya no admite la comprobación multiplataforma](https://github.com/NuGet/Home/issues/7939) de los paquetes de confianza.</span><span class="sxs-lookup"><span data-stu-id="c421d-132">This setting isn't applicable as [NuGet doesn't yet support cross-platform verification](https://github.com/NuGet/Home/issues/7939) of trusted packages.</span></span>

## <a name="implicit-restore"></a><span data-ttu-id="c421d-133">Restauración implícita</span><span class="sxs-lookup"><span data-stu-id="c421d-133">Implicit restore</span></span>

<span data-ttu-id="c421d-134">El comando `dotnet restore` se ejecuta de forma implícita si es necesario al ejecutar los comandos siguientes:</span><span class="sxs-lookup"><span data-stu-id="c421d-134">The `dotnet restore` command is run implicitly if necessary when you run the following commands:</span></span>

- [`dotnet new`](dotnet-new.md)
- [`dotnet build`](dotnet-build.md)
- [`dotnet build-server`](dotnet-build-server.md)
- [`dotnet run`](dotnet-run.md)
- [`dotnet test`](dotnet-test.md)
- [`dotnet publish`](dotnet-publish.md)
- [`dotnet pack`](dotnet-pack.md)

<span data-ttu-id="c421d-135">En la mayoría de los casos, no es necesario usar el comando `dotnet restore` de forma explícita.</span><span class="sxs-lookup"><span data-stu-id="c421d-135">In most cases, you don't need to explicitly use the `dotnet restore` command.</span></span>

<span data-ttu-id="c421d-136">En ocasiones, es posible que no sea conveniente ejecutar `dotnet restore` de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="c421d-136">Sometimes, it might be inconvenient to run `dotnet restore` implicitly.</span></span> <span data-ttu-id="c421d-137">Por ejemplo, algunos sistemas automatizados, como los sistemas de compilación, deben llamar a `dotnet restore` explícitamente para controlar cuándo se produce la restauración a fin de controlar el uso de la red.</span><span class="sxs-lookup"><span data-stu-id="c421d-137">For example, some automated systems, such as build systems, need to call `dotnet restore` explicitly to control when the restore occurs so that they can control network usage.</span></span> <span data-ttu-id="c421d-138">Para evitar que `dotnet restore` se ejecute de forma implícita, se puede usar la marca `--no-restore` con cualquiera de estos comandos para deshabilitar la restauración implícita.</span><span class="sxs-lookup"><span data-stu-id="c421d-138">To prevent `dotnet restore` from running implicitly, you can use the `--no-restore` flag with any of these commands to disable implicit restore.</span></span>

## <a name="arguments"></a><span data-ttu-id="c421d-139">Argumentos</span><span class="sxs-lookup"><span data-stu-id="c421d-139">Arguments</span></span>

- **`ROOT`**

  <span data-ttu-id="c421d-140">Ruta de acceso opcional del archivo de proyecto para restaurar.</span><span class="sxs-lookup"><span data-stu-id="c421d-140">Optional path to the project file to restore.</span></span>

## <a name="options"></a><span data-ttu-id="c421d-141">Opciones</span><span class="sxs-lookup"><span data-stu-id="c421d-141">Options</span></span>

- **`--configfile <FILE>`**

  <span data-ttu-id="c421d-142">El archivo de configuración de NuGet (*nuget.config*) que se usa para la operación de restauración.</span><span class="sxs-lookup"><span data-stu-id="c421d-142">The NuGet configuration file (*nuget.config*) to use for the restore operation.</span></span>

- **`--disable-parallel`**

  <span data-ttu-id="c421d-143">Deshabilita la restauración de varios proyectos en paralelo.</span><span class="sxs-lookup"><span data-stu-id="c421d-143">Disables restoring multiple projects in parallel.</span></span>

- **`--force`**

  <span data-ttu-id="c421d-144">Fuerza la resolución de todas las dependencias, incluso si la última restauración se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="c421d-144">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="c421d-145">Especificar esta marca es lo mismo que eliminar el archivo *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="c421d-145">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

- **`--force-evaluate`**

  <span data-ttu-id="c421d-146">Fuerza la restauración para volver a evaluar todas las dependencias aunque ya exista un archivo de bloqueo.</span><span class="sxs-lookup"><span data-stu-id="c421d-146">Forces restore to reevaluate all dependencies even if a lock file already exists.</span></span>

- **`-h|--help`**

  <span data-ttu-id="c421d-147">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="c421d-147">Prints out a short help for the command.</span></span>

- **`--ignore-failed-sources`**

  <span data-ttu-id="c421d-148">Solo se advierte sobre los orígenes con error si hay paquetes que satisfagan el requisito de versión.</span><span class="sxs-lookup"><span data-stu-id="c421d-148">Only warn about failed sources if there are packages meeting the version requirement.</span></span>

- **`--interactive`**

  <span data-ttu-id="c421d-149">Permite que el comando se detenga y espere la entrada o acción del usuario (por ejemplo, completar la autenticación).</span><span class="sxs-lookup"><span data-stu-id="c421d-149">Allows the command to stop and wait for user input or action (for example to complete authentication).</span></span> <span data-ttu-id="c421d-150">Desde .NET Core 2.1.400.</span><span class="sxs-lookup"><span data-stu-id="c421d-150">Since .NET Core 2.1.400.</span></span>

- **`--lock-file-path <LOCK_FILE_PATH>`**

  <span data-ttu-id="c421d-151">Ubicación de salida donde se escribe el archivo de bloqueo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="c421d-151">Output location where project lock file is written.</span></span> <span data-ttu-id="c421d-152">De forma predeterminada es *PROJECT_ROOT\packages.lock.json*.</span><span class="sxs-lookup"><span data-stu-id="c421d-152">By default, this is *PROJECT_ROOT\packages.lock.json*.</span></span>

- **`--locked-mode`**

  <span data-ttu-id="c421d-153">No permite actualizar el archivo de bloqueo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="c421d-153">Don't allow updating project lock file.</span></span>

- **`--no-cache`**

  <span data-ttu-id="c421d-154">Especifica que no se almacenen en caché los paquetes y las solicitudes HTTP.</span><span class="sxs-lookup"><span data-stu-id="c421d-154">Specifies to not cache packages and HTTP requests.</span></span>

- **`--no-dependencies`**

  <span data-ttu-id="c421d-155">Al restaurar un proyecto con referencias de proyecto a proyecto (P2P), se restaura el proyecto raíz y no las referencias.</span><span class="sxs-lookup"><span data-stu-id="c421d-155">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

- **`--packages <PACKAGES_DIRECTORY>`**

  <span data-ttu-id="c421d-156">Especifica el directorio de los paquetes restaurados.</span><span class="sxs-lookup"><span data-stu-id="c421d-156">Specifies the directory for restored packages.</span></span>

- **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="c421d-157">Especifica un tiempo de ejecución para la restauración del paquete.</span><span class="sxs-lookup"><span data-stu-id="c421d-157">Specifies a runtime for the package restore.</span></span> <span data-ttu-id="c421d-158">Se usa para restaurar los paquetes con tiempos de ejecución que no se enumeran explícitamente en la etiqueta `<RuntimeIdentifiers>` del archivo *.csproj*.</span><span class="sxs-lookup"><span data-stu-id="c421d-158">This is used to restore packages for runtimes not explicitly listed in the `<RuntimeIdentifiers>` tag in the *.csproj* file.</span></span> <span data-ttu-id="c421d-159">Para obtener una lista de identificadores de tiempo de ejecución (RID), consulte el [catálogo de RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="c421d-159">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="c421d-160">Para proporcionar varios RID; especifique esta opción varias veces.</span><span class="sxs-lookup"><span data-stu-id="c421d-160">Provide multiple RIDs by specifying this option multiple times.</span></span>

- **`-s|--source <SOURCE>`**

  <span data-ttu-id="c421d-161">Especifica un origen de paquetes de NuGet que se usará durante la operación de restauración.</span><span class="sxs-lookup"><span data-stu-id="c421d-161">Specifies a NuGet package source to use during the restore operation.</span></span> <span data-ttu-id="c421d-162">Este valor invalida todos los orígenes especificados en los archivos *nuget.config*.</span><span class="sxs-lookup"><span data-stu-id="c421d-162">This setting overrides all of the sources specified in the *nuget.config* files.</span></span> <span data-ttu-id="c421d-163">Al especificar esta opción varias veces, se pueden proporcionar varios orígenes.</span><span class="sxs-lookup"><span data-stu-id="c421d-163">Multiple sources can be provided by specifying this option multiple times.</span></span>

- **`--use-lockfile`**

  <span data-ttu-id="c421d-164">Habilita la generación del archivo de bloqueo del proyecto y su uso con la restauración.</span><span class="sxs-lookup"><span data-stu-id="c421d-164">Enables project lock file to be generated and used with restore.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="c421d-165">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="c421d-165">Sets the verbosity level of the command.</span></span> <span data-ttu-id="c421d-166">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="c421d-166">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="c421d-167">El valor predeterminado es `minimal`.</span><span class="sxs-lookup"><span data-stu-id="c421d-167">Default value is `minimal`.</span></span>

## <a name="examples"></a><span data-ttu-id="c421d-168">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="c421d-168">Examples</span></span>

- <span data-ttu-id="c421d-169">Restauración de dependencias y herramientas para el proyecto en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="c421d-169">Restore dependencies and tools for the project in the current directory:</span></span>

  ```dotnetcli
  dotnet restore
  ```

- <span data-ttu-id="c421d-170">Restauración de dependencias y herramientas para el proyecto `app1` encontrado en la ruta de acceso dada:</span><span class="sxs-lookup"><span data-stu-id="c421d-170">Restore dependencies and tools for the `app1` project found in the   given path:</span></span>

  ```dotnetcli
  dotnet restore ~/projects/app1/app1.csproj
  ```

- <span data-ttu-id="c421d-171">Restauración de dependencias y herramientas para el proyecto en el directorio actual con la ruta de acceso de archivo proporcionada como origen:</span><span class="sxs-lookup"><span data-stu-id="c421d-171">Restore the dependencies and tools for the project in the current   directory using the file path provided as the source:</span></span>

  ```dotnetcli
  dotnet restore -s c:\packages\mypackages
  ```

- <span data-ttu-id="c421d-172">Restauración de dependencias y herramientas para el proyecto en el directorio actual mediante las dos rutas de acceso de archivo proporcionadas como orígenes:</span><span class="sxs-lookup"><span data-stu-id="c421d-172">Restore the dependencies and tools for the project in the current   directory using the two file paths provided as sources:</span></span>

  ```dotnetcli
  dotnet restore -s c:\packages\mypackages -s c:\packages\myotherpackages
  ```

- <span data-ttu-id="c421d-173">Restauración de dependencias y herramientas para el proyecto en el directorio actual que muestra una salida detallada:</span><span class="sxs-lookup"><span data-stu-id="c421d-173">Restore dependencies and tools for the project in the current directory   showing detailed output:</span></span>

  ```dotnetcli
  dotnet restore --verbosity detailed
  ```
