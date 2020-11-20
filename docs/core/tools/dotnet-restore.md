---
title: Comando dotnet restore
description: Aprenda a restaurar dependencias y herramientas específicas del proyecto con el comando dotnet restore.
ms.date: 02/27/2020
ms.openlocfilehash: dcb68d6c690f2e12b61cfdfa6dc288bd474721c1
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2020
ms.locfileid: "94634408"
---
# <a name="dotnet-restore"></a><span data-ttu-id="7f37f-103">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="7f37f-103">dotnet restore</span></span>

<span data-ttu-id="7f37f-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.1 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="7f37f-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="7f37f-105">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="7f37f-105">Name</span></span>

<span data-ttu-id="7f37f-106">`dotnet restore`: restaura las dependencias y las herramientas de un proyecto.</span><span class="sxs-lookup"><span data-stu-id="7f37f-106">`dotnet restore` - Restores the dependencies and tools of a project.</span></span>

## <a name="synopsis"></a><span data-ttu-id="7f37f-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="7f37f-107">Synopsis</span></span>

```dotnetcli
dotnet restore [<ROOT>] [--configfile <FILE>] [--disable-parallel]
    [-f|--force] [--force-evaluate] [--ignore-failed-sources]
    [--interactive] [--lock-file-path <LOCK_FILE_PATH>] [--locked-mode]
    [--no-cache] [--no-dependencies] [--packages <PACKAGES_DIRECTORY>]
    [-r|--runtime <RUNTIME_IDENTIFIER>] [-s|--source <SOURCE>]
    [--use-lock-file] [-v|--verbosity <LEVEL>]

dotnet restore -h|--help
```

## <a name="description"></a><span data-ttu-id="7f37f-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="7f37f-108">Description</span></span>

<span data-ttu-id="7f37f-109">El comando `dotnet restore` usa NuGet para restaurar las dependencias, así como las herramientas específicas del proyecto que se especifican en el archivo project.json.</span><span class="sxs-lookup"><span data-stu-id="7f37f-109">The `dotnet restore` command uses NuGet to restore dependencies as well as project-specific tools that are specified in the project file.</span></span>  <span data-ttu-id="7f37f-110">En la mayoría de los casos, no es necesario usar explícitamente el comando `dotnet restore`, ya que una restauración de NuGet se ejecuta implícitamente si es necesario al ejecutar los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="7f37f-110">In most cases, you don't need to explicitly use the `dotnet restore` command, since a NuGet restore is run implicitly if necessary when you run the following commands:</span></span>

- [`dotnet new`](dotnet-new.md)
- [`dotnet build`](dotnet-build.md)
- [`dotnet build-server`](dotnet-build-server.md)
- [`dotnet run`](dotnet-run.md)
- [`dotnet test`](dotnet-test.md)
- [`dotnet publish`](dotnet-publish.md)
- [`dotnet pack`](dotnet-pack.md)

<span data-ttu-id="7f37f-111">A veces, puede que no sea conveniente ejecutar la restauración de NuGet implícita con estos comandos.</span><span class="sxs-lookup"><span data-stu-id="7f37f-111">Sometimes, it might be inconvenient to run the implicit NuGet restore with these commands.</span></span> <span data-ttu-id="7f37f-112">Por ejemplo, algunos sistemas automatizados, como los sistemas de compilación, deben llamar a `dotnet restore` explícitamente para controlar cuándo se produce la restauración a fin de controlar el uso de la red.</span><span class="sxs-lookup"><span data-stu-id="7f37f-112">For example, some automated systems, such as build systems, need to call `dotnet restore` explicitly to control when the restore occurs so that they can control network usage.</span></span> <span data-ttu-id="7f37f-113">Para evitar la restauración de NuGet implícita, puede usar la marca `--no-restore` con cualquiera de estos comandos para deshabilitar la restauración implícita.</span><span class="sxs-lookup"><span data-stu-id="7f37f-113">To prevent the implicit NuGet restore, you can use the `--no-restore` flag with any of these commands to disable implicit restore.</span></span>

### <a name="specify-feeds"></a><span data-ttu-id="7f37f-114">Especificación de fuentes</span><span class="sxs-lookup"><span data-stu-id="7f37f-114">Specify feeds</span></span>

<span data-ttu-id="7f37f-115">Para restaurar las dependencias, NuGet necesita las fuentes donde se encuentran los paquetes.</span><span class="sxs-lookup"><span data-stu-id="7f37f-115">To restore the dependencies, NuGet needs the feeds where the packages are located.</span></span> <span data-ttu-id="7f37f-116">Las fuente se proporcionan normalmente mediante el archivo de configuración *nuget.config*.</span><span class="sxs-lookup"><span data-stu-id="7f37f-116">Feeds are usually provided via the *nuget.config* configuration file.</span></span> <span data-ttu-id="7f37f-117">Cuando se instala el SDK de .NET, se proporciona un archivo de configuración predeterminado.</span><span class="sxs-lookup"><span data-stu-id="7f37f-117">A default configuration file is provided when the .NET SDK is installed.</span></span> <span data-ttu-id="7f37f-118">Para especificar fuentes adicionales, realice una de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="7f37f-118">To specify additional feeds, do one of the following:</span></span>

- <span data-ttu-id="7f37f-119">Cree su propio archivo *nuget.config* en el directorio del proyecto.</span><span class="sxs-lookup"><span data-stu-id="7f37f-119">Create your own *nuget.config* file in the project directory.</span></span> <span data-ttu-id="7f37f-120">Para obtener más información, vea [Configuraciones comunes de NuGet](/nuget/consume-packages/configuring-nuget-behavior) y [Diferencias de nuget.config](#nugetconfig-differences) más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="7f37f-120">For more information, see [Common NuGet configurations](/nuget/consume-packages/configuring-nuget-behavior) and [nuget.config differences](#nugetconfig-differences) later in this article.</span></span>
- <span data-ttu-id="7f37f-121">Use comandos de `dotnet nuget` como [`dotnet nuget add source`](dotnet-nuget-add-source.md).</span><span class="sxs-lookup"><span data-stu-id="7f37f-121">Use `dotnet nuget` commands such as [`dotnet nuget add source`](dotnet-nuget-add-source.md).</span></span>

<span data-ttu-id="7f37f-122">Puede invalidar las fuentes *nuget.config* con la opción `-s`.</span><span class="sxs-lookup"><span data-stu-id="7f37f-122">You can override the *nuget.config* feeds with the `-s` option.</span></span>

<span data-ttu-id="7f37f-123">Para obtener información sobre cómo usar las fuentes autenticadas, vea [Consumir paquetes desde fuentes autenticadas](/nuget/consume-packages/consuming-packages-authenticated-feeds).</span><span class="sxs-lookup"><span data-stu-id="7f37f-123">For information about how to use authenticated feeds, see [Consuming packages from authenticated feeds](/nuget/consume-packages/consuming-packages-authenticated-feeds).</span></span>

### <a name="global-packages-folder"></a><span data-ttu-id="7f37f-124">Carpeta de paquetes globales</span><span class="sxs-lookup"><span data-stu-id="7f37f-124">Global packages folder</span></span>

<span data-ttu-id="7f37f-125">Para las dependencias, puede especificar dónde se colocan los paquetes restaurados durante la operación de restauración mediante el argumento `--packages`.</span><span class="sxs-lookup"><span data-stu-id="7f37f-125">For dependencies, you can specify where the restored packages are placed during the restore operation using the `--packages` argument.</span></span> <span data-ttu-id="7f37f-126">Si no se especifica, se usa la caché de paquetes NuGet predeterminada, que se encuentra en el directorio `.nuget/packages` del directorio de inicio del usuario en todos los sistemas operativos.</span><span class="sxs-lookup"><span data-stu-id="7f37f-126">If not specified, the default NuGet package cache is used, which is found in the `.nuget/packages` directory in the user's home directory on all operating systems.</span></span> <span data-ttu-id="7f37f-127">Por ejemplo, */home/usuario1* en Linux o *C:\Usuarios\usuario1* en Windows.</span><span class="sxs-lookup"><span data-stu-id="7f37f-127">For example, */home/user1* on Linux or *C:\Users\user1* on Windows.</span></span>

### <a name="project-specific-tooling"></a><span data-ttu-id="7f37f-128">Herramientas específicas del proyecto</span><span class="sxs-lookup"><span data-stu-id="7f37f-128">Project-specific tooling</span></span>

<span data-ttu-id="7f37f-129">Para herramientas específicas del proyecto, `dotnet restore` restaura primero el paquete en el que se empaqueta la herramienta y, a continuación, continúa con la restauración de las dependencias de la herramienta especificadas en su project.json.</span><span class="sxs-lookup"><span data-stu-id="7f37f-129">For project-specific tooling, `dotnet restore` first restores the package in which the tool is packed, and then proceeds to restore the tool's dependencies as specified in its project file.</span></span>

### <a name="nugetconfig-differences"></a><span data-ttu-id="7f37f-130">Diferencias de nuget.config</span><span class="sxs-lookup"><span data-stu-id="7f37f-130">nuget.config differences</span></span>

<span data-ttu-id="7f37f-131">El comportamiento del comando `dotnet restore` depende de las opciones de configuración del archivo *nuget.config*, si existe.</span><span class="sxs-lookup"><span data-stu-id="7f37f-131">The behavior of the `dotnet restore` command is affected by the settings in the *nuget.config* file, if present.</span></span> <span data-ttu-id="7f37f-132">Por ejemplo, establecer `globalPackagesFolder` en *nuget.config* coloca los paquetes NuGet restaurados en la carpeta especificada.</span><span class="sxs-lookup"><span data-stu-id="7f37f-132">For example, setting the `globalPackagesFolder` in *nuget.config* places the restored NuGet packages in the specified folder.</span></span> <span data-ttu-id="7f37f-133">Esta es una alternativa para especificar la opción `--packages` en el comando `dotnet restore`.</span><span class="sxs-lookup"><span data-stu-id="7f37f-133">This is an alternative to specifying the `--packages` option on the `dotnet restore` command.</span></span> <span data-ttu-id="7f37f-134">Para más información, consulte la [referencia de nuget.config](/nuget/schema/nuget-config-file).</span><span class="sxs-lookup"><span data-stu-id="7f37f-134">For more information, see the [nuget.config reference](/nuget/schema/nuget-config-file).</span></span>

<span data-ttu-id="7f37f-135">Hay tres configuraciones específicas que `dotnet restore` omite:</span><span class="sxs-lookup"><span data-stu-id="7f37f-135">There are three specific settings that `dotnet restore` ignores:</span></span>

- [<span data-ttu-id="7f37f-136">bindingRedirects</span><span class="sxs-lookup"><span data-stu-id="7f37f-136">bindingRedirects</span></span>](/nuget/schema/nuget-config-file#bindingredirects-section)

  <span data-ttu-id="7f37f-137">Los redireccionamientos de enlace no funcionan con elementos de `<PackageReference>` y .NET solo admite elementos de `<PackageReference>` para los paquetes NuGet.</span><span class="sxs-lookup"><span data-stu-id="7f37f-137">Binding redirects don't work with `<PackageReference>` elements and .NET only supports `<PackageReference>` elements for NuGet packages.</span></span>

- [<span data-ttu-id="7f37f-138">solution</span><span class="sxs-lookup"><span data-stu-id="7f37f-138">solution</span></span>](/nuget/schema/nuget-config-file#solution-section)

  <span data-ttu-id="7f37f-139">Esta configuración es específica para Visual Studio y no se aplica a .NET.</span><span class="sxs-lookup"><span data-stu-id="7f37f-139">This setting is Visual Studio specific and doesn't apply to .NET.</span></span> <span data-ttu-id="7f37f-140">.NET no usa un archivo `packages.config` y, en su lugar, usa elementos de `<PackageReference>` para los paquetes NuGet.</span><span class="sxs-lookup"><span data-stu-id="7f37f-140">.NET doesn't use a `packages.config` file and instead uses `<PackageReference>` elements for NuGet packages.</span></span>

- [<span data-ttu-id="7f37f-141">trustedSigners</span><span class="sxs-lookup"><span data-stu-id="7f37f-141">trustedSigners</span></span>](/nuget/schema/nuget-config-file#trustedsigners-section)

  <span data-ttu-id="7f37f-142">Esta configuración no es aplicable porque [NuGet ya no admite la comprobación multiplataforma](https://github.com/NuGet/Home/issues/7939) de los paquetes de confianza.</span><span class="sxs-lookup"><span data-stu-id="7f37f-142">This setting isn't applicable as [NuGet doesn't yet support cross-platform verification](https://github.com/NuGet/Home/issues/7939) of trusted packages.</span></span>

## <a name="arguments"></a><span data-ttu-id="7f37f-143">Argumentos</span><span class="sxs-lookup"><span data-stu-id="7f37f-143">Arguments</span></span>

- **`ROOT`**

  <span data-ttu-id="7f37f-144">Ruta de acceso opcional del archivo de proyecto para restaurar.</span><span class="sxs-lookup"><span data-stu-id="7f37f-144">Optional path to the project file to restore.</span></span>

## <a name="options"></a><span data-ttu-id="7f37f-145">Opciones</span><span class="sxs-lookup"><span data-stu-id="7f37f-145">Options</span></span>

- **`--configfile <FILE>`**

  <span data-ttu-id="7f37f-146">El archivo de configuración de NuGet (*nuget.config*) que se usa para la operación de restauración.</span><span class="sxs-lookup"><span data-stu-id="7f37f-146">The NuGet configuration file (*nuget.config*) to use for the restore operation.</span></span>

- **`--disable-parallel`**

  <span data-ttu-id="7f37f-147">Deshabilita la restauración de varios proyectos en paralelo.</span><span class="sxs-lookup"><span data-stu-id="7f37f-147">Disables restoring multiple projects in parallel.</span></span>

- **`--force`**

  <span data-ttu-id="7f37f-148">Fuerza la resolución de todas las dependencias, incluso si la última restauración se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="7f37f-148">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="7f37f-149">Especificar esta marca es lo mismo que eliminar el archivo *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="7f37f-149">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

- **`--force-evaluate`**

  <span data-ttu-id="7f37f-150">Fuerza la restauración para volver a evaluar todas las dependencias aunque ya exista un archivo de bloqueo.</span><span class="sxs-lookup"><span data-stu-id="7f37f-150">Forces restore to reevaluate all dependencies even if a lock file already exists.</span></span>

- **`-h|--help`**

  <span data-ttu-id="7f37f-151">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="7f37f-151">Prints out a short help for the command.</span></span>

- **`--ignore-failed-sources`**

  <span data-ttu-id="7f37f-152">Solo se advierte sobre los orígenes con error si hay paquetes que satisfagan el requisito de versión.</span><span class="sxs-lookup"><span data-stu-id="7f37f-152">Only warn about failed sources if there are packages meeting the version requirement.</span></span>

- **`--interactive`**

  <span data-ttu-id="7f37f-153">Permite que el comando se detenga y espere la entrada o acción del usuario (por ejemplo, completar la autenticación).</span><span class="sxs-lookup"><span data-stu-id="7f37f-153">Allows the command to stop and wait for user input or action (for example to complete authentication).</span></span> <span data-ttu-id="7f37f-154">Desde .NET Core 2.1.400.</span><span class="sxs-lookup"><span data-stu-id="7f37f-154">Since .NET Core 2.1.400.</span></span>

- **`--lock-file-path <LOCK_FILE_PATH>`**

  <span data-ttu-id="7f37f-155">Ubicación de salida donde se escribe el archivo de bloqueo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="7f37f-155">Output location where project lock file is written.</span></span> <span data-ttu-id="7f37f-156">De forma predeterminada es *PROJECT_ROOT\packages.lock.json*.</span><span class="sxs-lookup"><span data-stu-id="7f37f-156">By default, this is *PROJECT_ROOT\packages.lock.json*.</span></span>

- **`--locked-mode`**

  <span data-ttu-id="7f37f-157">No permite actualizar el archivo de bloqueo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="7f37f-157">Don't allow updating project lock file.</span></span>

- **`--no-cache`**

  <span data-ttu-id="7f37f-158">Especifica que no se almacenen en caché las solicitudes HTTP.</span><span class="sxs-lookup"><span data-stu-id="7f37f-158">Specifies to not cache HTTP requests.</span></span>

- **`--no-dependencies`**

  <span data-ttu-id="7f37f-159">Al restaurar un proyecto con referencias de proyecto a proyecto (P2P), se restaura el proyecto raíz y no las referencias.</span><span class="sxs-lookup"><span data-stu-id="7f37f-159">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

- **`--packages <PACKAGES_DIRECTORY>`**

  <span data-ttu-id="7f37f-160">Especifica el directorio de los paquetes restaurados.</span><span class="sxs-lookup"><span data-stu-id="7f37f-160">Specifies the directory for restored packages.</span></span>

- **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="7f37f-161">Especifica un tiempo de ejecución para la restauración del paquete.</span><span class="sxs-lookup"><span data-stu-id="7f37f-161">Specifies a runtime for the package restore.</span></span> <span data-ttu-id="7f37f-162">Se usa para restaurar los paquetes con tiempos de ejecución que no se enumeran explícitamente en la etiqueta `<RuntimeIdentifiers>` del archivo *.csproj*.</span><span class="sxs-lookup"><span data-stu-id="7f37f-162">This is used to restore packages for runtimes not explicitly listed in the `<RuntimeIdentifiers>` tag in the *.csproj* file.</span></span> <span data-ttu-id="7f37f-163">Para obtener una lista de identificadores de tiempo de ejecución (RID), consulte el [catálogo de RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="7f37f-163">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="7f37f-164">Para proporcionar varios RID; especifique esta opción varias veces.</span><span class="sxs-lookup"><span data-stu-id="7f37f-164">Provide multiple RIDs by specifying this option multiple times.</span></span>

- **`-s|--source <SOURCE>`**

  <span data-ttu-id="7f37f-165">Especifica el URI del origen del paquete NuGet que se usará durante la operación de restauración.</span><span class="sxs-lookup"><span data-stu-id="7f37f-165">Specifies the URI of the NuGet package source to use during the restore operation.</span></span> <span data-ttu-id="7f37f-166">Este valor invalida todos los orígenes especificados en los archivos *nuget.config*.</span><span class="sxs-lookup"><span data-stu-id="7f37f-166">This setting overrides all of the sources specified in the *nuget.config* files.</span></span> <span data-ttu-id="7f37f-167">Al especificar esta opción varias veces, se pueden proporcionar varios orígenes.</span><span class="sxs-lookup"><span data-stu-id="7f37f-167">Multiple sources can be provided by specifying this option multiple times.</span></span>

- **`--use-lock-file`**

  <span data-ttu-id="7f37f-168">Habilita la generación del archivo de bloqueo del proyecto y su uso con la restauración.</span><span class="sxs-lookup"><span data-stu-id="7f37f-168">Enables project lock file to be generated and used with restore.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="7f37f-169">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="7f37f-169">Sets the verbosity level of the command.</span></span> <span data-ttu-id="7f37f-170">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="7f37f-170">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="7f37f-171">El valor predeterminado es `minimal`.</span><span class="sxs-lookup"><span data-stu-id="7f37f-171">Default value is `minimal`.</span></span>

## <a name="examples"></a><span data-ttu-id="7f37f-172">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="7f37f-172">Examples</span></span>

- <span data-ttu-id="7f37f-173">Restauración de dependencias y herramientas para el proyecto en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="7f37f-173">Restore dependencies and tools for the project in the current directory:</span></span>

  ```dotnetcli
  dotnet restore
  ```

- <span data-ttu-id="7f37f-174">Restauración de dependencias y herramientas para el proyecto `app1` encontrado en la ruta de acceso dada:</span><span class="sxs-lookup"><span data-stu-id="7f37f-174">Restore dependencies and tools for the `app1` project found in the given path:</span></span>

  ```dotnetcli
  dotnet restore ./projects/app1/app1.csproj
  ```

- <span data-ttu-id="7f37f-175">Restauración de dependencias y herramientas para el proyecto en el directorio actual con la ruta de acceso de archivo proporcionada como origen:</span><span class="sxs-lookup"><span data-stu-id="7f37f-175">Restore the dependencies and tools for the project in the current   directory using the file path provided as the source:</span></span>

  ```dotnetcli
  dotnet restore -s c:\packages\mypackages
  ```

- <span data-ttu-id="7f37f-176">Restauración de dependencias y herramientas para el proyecto en el directorio actual mediante las dos rutas de acceso de archivo proporcionadas como orígenes:</span><span class="sxs-lookup"><span data-stu-id="7f37f-176">Restore the dependencies and tools for the project in the current   directory using the two file paths provided as sources:</span></span>

  ```dotnetcli
  dotnet restore -s c:\packages\mypackages -s c:\packages\myotherpackages
  ```

- <span data-ttu-id="7f37f-177">Restauración de dependencias y herramientas para el proyecto en el directorio actual que muestra una salida detallada:</span><span class="sxs-lookup"><span data-stu-id="7f37f-177">Restore dependencies and tools for the project in the current directory   showing detailed output:</span></span>

  ```dotnetcli
  dotnet restore --verbosity detailed
  ```
