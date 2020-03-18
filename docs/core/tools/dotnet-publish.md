---
title: Comando dotnet publish
description: El comando dotnet publish publica el proyecto o la solución de .NET Core en un directorio.
ms.date: 02/24/2020
ms.openlocfilehash: c34618409c9a539043c84c7e03daa8aa249d64f6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79146560"
---
# <a name="dotnet-publish"></a><span data-ttu-id="590d6-103">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="590d6-103">dotnet publish</span></span>

<span data-ttu-id="590d6-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.1 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="590d6-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="590d6-105">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="590d6-105">Name</span></span>

<span data-ttu-id="590d6-106">`dotnet publish`: publica la aplicación y sus dependencias en una carpeta para la implementación en un sistema de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="590d6-106">`dotnet publish` - Publishes the application and its dependencies to a folder for deployment to a hosting system.</span></span>

## <a name="synopsis"></a><span data-ttu-id="590d6-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="590d6-107">Synopsis</span></span>

```dotnetcli
dotnet publish [<PROJECT>|<SOLUTION>] [-c|--configuration]
    [-f|--framework] [--force] [--interactive] [--manifest]
    [--no-build] [--no-dependencies] [--no-restore] [--nologo]
    [-o|--output] [-r|--runtime] [--self-contained]
    [--no-self-contained] [-v|--verbosity] [--version-suffix]

dotnet publish [-h|--help]
```

## <a name="description"></a><span data-ttu-id="590d6-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="590d6-108">Description</span></span>

<span data-ttu-id="590d6-109">`dotnet publish`: compila la aplicación, lee sus dependencias especificadas en el archivo de proyecto y publica el conjunto resultante de archivos en un directorio.</span><span class="sxs-lookup"><span data-stu-id="590d6-109">`dotnet publish` compiles the application, reads through its dependencies specified in the project file, and publishes the resulting set of files to a directory.</span></span> <span data-ttu-id="590d6-110">La salida incluye los recursos siguientes:</span><span class="sxs-lookup"><span data-stu-id="590d6-110">The output includes the following assets:</span></span>

- <span data-ttu-id="590d6-111">Código de lenguaje intermedio (IL) en un ensamblado con una extensión *dll*.</span><span class="sxs-lookup"><span data-stu-id="590d6-111">Intermediate Language (IL) code in an assembly with a *dll* extension.</span></span>
- <span data-ttu-id="590d6-112">Un archivo *.deps.json* que incluye todas las dependencias del proyecto.</span><span class="sxs-lookup"><span data-stu-id="590d6-112">A *.deps.json* file that includes all of the dependencies of the project.</span></span>
- <span data-ttu-id="590d6-113">Un archivo *.runtime.config.json* en el que se especifica el tiempo de ejecución compartido que espera la aplicación, así como otras opciones de configuración para el tiempo de ejecución (por ejemplo, el tipo de recolección de elementos no utilizados).</span><span class="sxs-lookup"><span data-stu-id="590d6-113">A *.runtimeconfig.json* file that specifies the shared runtime that the application expects, as well as other configuration options for the runtime (for example, garbage collection type).</span></span>
- <span data-ttu-id="590d6-114">Las dependencias de la aplicación, que se copian de la caché de NuGet a la carpeta de salida.</span><span class="sxs-lookup"><span data-stu-id="590d6-114">The application's dependencies, which are copied from the NuGet cache into the output folder.</span></span>

<span data-ttu-id="590d6-115">La salida del comando `dotnet publish` está lista para la implementación en un sistema de hospedaje (por ejemplo, un servidor, un equipo PC o Mac, un portátil) para la ejecución.</span><span class="sxs-lookup"><span data-stu-id="590d6-115">The `dotnet publish` command's output is ready for deployment to a hosting system (for example, a server, PC, Mac, laptop) for execution.</span></span> <span data-ttu-id="590d6-116">Es la única manera admitida oficialmente para preparar la aplicación para la implementación.</span><span class="sxs-lookup"><span data-stu-id="590d6-116">It's the only officially supported way to prepare the application for deployment.</span></span> <span data-ttu-id="590d6-117">Dependiendo del tipo de implementación que especifique el proyecto, el sistema de hospedaje puede o no tener instalado el entorno de tiempo de ejecución compartido de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="590d6-117">Depending on the type of deployment that the project specifies, the hosting system may or may not have the .NET Core shared runtime installed on it.</span></span>

## <a name="arguments"></a><span data-ttu-id="590d6-118">Argumentos</span><span class="sxs-lookup"><span data-stu-id="590d6-118">Arguments</span></span>

- **`PROJECT|SOLUTION`**

  <span data-ttu-id="590d6-119">El archivo de proyecto o solución que se va a publicar.</span><span class="sxs-lookup"><span data-stu-id="590d6-119">The project or solution to publish.</span></span>
  
  * <span data-ttu-id="590d6-120">`PROJECT` es la ruta de acceso y el nombre de archivo de un archivo de proyecto de [C#](csproj.md), F# o Visual Basic, o bien la ruta de acceso a un directorio que contiene un archivo de proyecto de C#, F# o Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="590d6-120">`PROJECT` is the path and filename of a [C#](csproj.md), F#, or Visual Basic project file, or the path to a directory that contains a C#, F#, or Visual Basic project file.</span></span> <span data-ttu-id="590d6-121">Si no se especifica el directorio, se toma como predeterminado el actual.</span><span class="sxs-lookup"><span data-stu-id="590d6-121">If the directory is not specified, it defaults to the current directory.</span></span>

  * <span data-ttu-id="590d6-122">`SOLUTION` es la ruta de acceso y el nombre de archivo de un archivo de solución (extensión *.sln*), o bien la ruta de acceso a un directorio que contiene un archivo de solución.</span><span class="sxs-lookup"><span data-stu-id="590d6-122">`SOLUTION` is the path and filename of a solution file (*.sln* extension), or the path to a directory that contains a solution file.</span></span> <span data-ttu-id="590d6-123">Si no se especifica el directorio, se toma como predeterminado el actual.</span><span class="sxs-lookup"><span data-stu-id="590d6-123">If the directory is not specified, it defaults to the current directory.</span></span> <span data-ttu-id="590d6-124">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="590d6-124">Available since .NET Core 3.0 SDK.</span></span>

## <a name="options"></a><span data-ttu-id="590d6-125">Opciones</span><span class="sxs-lookup"><span data-stu-id="590d6-125">Options</span></span>

- **`-c|--configuration <CONFIGURATION>`**

  <span data-ttu-id="590d6-126">Define la configuración de compilación.</span><span class="sxs-lookup"><span data-stu-id="590d6-126">Defines the build configuration.</span></span> <span data-ttu-id="590d6-127">El valor predeterminado para la mayoría de los proyectos es `Debug`, pero puede invalidar los valores de configuración de compilación en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="590d6-127">The default for most projects is `Debug`, but you can override the build configuration settings in your project.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="590d6-128">Publica la aplicación para el [marco de trabajo de destino especificado](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="590d6-128">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="590d6-129">Debe especificar el marco de trabajo de destino en el archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="590d6-129">You must specify the target framework in the project file.</span></span>

- **`--force`**

  <span data-ttu-id="590d6-130">Fuerza la resolución de todas las dependencias, incluso si la última restauración se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="590d6-130">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="590d6-131">Especificar esta marca es lo mismo que eliminar el archivo *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="590d6-131">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

- **`-h|--help`**

  <span data-ttu-id="590d6-132">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="590d6-132">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="590d6-133">Permite que el comando se detenga y espere una entrada o una acción del usuario.</span><span class="sxs-lookup"><span data-stu-id="590d6-133">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="590d6-134">Por ejemplo, para completar la autenticación.</span><span class="sxs-lookup"><span data-stu-id="590d6-134">For example, to complete authentication.</span></span> <span data-ttu-id="590d6-135">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="590d6-135">Available since .NET Core 3.0 SDK.</span></span>

- **`--manifest <PATH_TO_MANIFEST_FILE>`**

  <span data-ttu-id="590d6-136">Especifica uno o varios [manifiestos de destino](../deploying/runtime-store.md) que se usarán para recortar el conjunto de paquetes publicados con la aplicación.</span><span class="sxs-lookup"><span data-stu-id="590d6-136">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="590d6-137">El archivo de manifiesto es parte de la salida del [comando `dotnet store`](dotnet-store.md).</span><span class="sxs-lookup"><span data-stu-id="590d6-137">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="590d6-138">Para especificar varios manifiestos, agregue la opción `--manifest` para cada manifiesto.</span><span class="sxs-lookup"><span data-stu-id="590d6-138">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span>

- **`--no-build`**

  <span data-ttu-id="590d6-139">No compila el proyecto antes de publicarlo.</span><span class="sxs-lookup"><span data-stu-id="590d6-139">Doesn't build the project before publishing.</span></span> <span data-ttu-id="590d6-140">También establece la marca `--no-restore` de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="590d6-140">It also implicitly sets the `--no-restore` flag.</span></span>

- **`--no-dependencies`**

  <span data-ttu-id="590d6-141">Omite las referencias de proyecto a proyecto y solo restaura el proyecto raíz.</span><span class="sxs-lookup"><span data-stu-id="590d6-141">Ignores project-to-project references and only restores the root project.</span></span>

- **`--nologo`**

  <span data-ttu-id="590d6-142">No se muestra la pancarta de inicio ni el mensaje de copyright.</span><span class="sxs-lookup"><span data-stu-id="590d6-142">Doesn't display the startup banner or the copyright message.</span></span> <span data-ttu-id="590d6-143">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="590d6-143">Available since .NET Core 3.0 SDK.</span></span>

- **`--no-restore`**

  <span data-ttu-id="590d6-144">No ejecuta una restauración implícita al ejecutar el comando.</span><span class="sxs-lookup"><span data-stu-id="590d6-144">Doesn't execute an implicit restore when running the command.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="590d6-145">Especifica la ruta de acceso del directorio de salida.</span><span class="sxs-lookup"><span data-stu-id="590d6-145">Specifies the path for the output directory.</span></span> <span data-ttu-id="590d6-146">Si no se especifica, el valor predeterminado es *./bin/[configuration]/[framework]/publish/* para un archivo ejecutable dependiente del tiempo de ejecución y archivos binarios multiplataforma.</span><span class="sxs-lookup"><span data-stu-id="590d6-146">If not specified, it defaults to *./bin/[configuration]/[framework]/publish/* for a runtime-dependent executable and cross-platform binaries.</span></span> <span data-ttu-id="590d6-147">El valor predeterminado es *./bin/[configuration]/[framework]/[runtime]/publish/* para un archivo ejecutable independiente.</span><span class="sxs-lookup"><span data-stu-id="590d6-147">It defaults to *./bin/[configuration]/[framework]/[runtime]/publish/* for a self-contained executable.</span></span>

  <span data-ttu-id="590d6-148">Si la ruta de acceso es relativa, el directorio de salida generado es relativo a la ubicación del archivo de proyecto, no al directorio de trabajo actual.</span><span class="sxs-lookup"><span data-stu-id="590d6-148">If the path is relative, the output directory generated is relative to the project file location, not to the current working directory.</span></span>

- **`--self-contained [true|false]`**

  <span data-ttu-id="590d6-149">Publica el tiempo de ejecución de .NET Core con la aplicación para que no sea necesario tener instalado el tiempo de ejecución en la máquina de destino.</span><span class="sxs-lookup"><span data-stu-id="590d6-149">Publishes the .NET Core runtime with your application so the runtime doesn't need to be installed on the target machine.</span></span> <span data-ttu-id="590d6-150">Si se especifica un identificador de tiempo de ejecución, el valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="590d6-150">Default is `true` if a runtime identifier is specified.</span></span> <span data-ttu-id="590d6-151">Para obtener más información, vea [Publicación de aplicaciones .NET Core](../deploying/index.md) y [Publicación de aplicaciones .NET Core con la CLI de .NET Core](../deploying/deploy-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="590d6-151">For more information, see [.NET Core application publishing](../deploying/index.md) and [Publish .NET Core apps with the .NET Core CLI](../deploying/deploy-with-cli.md).</span></span>

- **`--no-self-contained`**

  <span data-ttu-id="590d6-152">Equivalente a `--self-contained false`.</span><span class="sxs-lookup"><span data-stu-id="590d6-152">Equivalent to `--self-contained false`.</span></span> <span data-ttu-id="590d6-153">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="590d6-153">Available since .NET Core 3.0 SDK.</span></span>

- **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="590d6-154">Publica la aplicación para un determinado entorno de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="590d6-154">Publishes the application for a given runtime.</span></span> <span data-ttu-id="590d6-155">Para obtener una lista de identificadores de tiempo de ejecución (RID), consulte el [catálogo de RID](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="590d6-155">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="590d6-156">Para obtener más información, vea [Publicación de aplicaciones .NET Core](../deploying/index.md) y [Publicación de aplicaciones .NET Core con la CLI de .NET Core](../deploying/deploy-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="590d6-156">For more information, see [.NET Core application publishing](../deploying/index.md) and [Publish .NET Core apps with the .NET Core CLI](../deploying/deploy-with-cli.md).</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="590d6-157">Establece el nivel de detalle del comando.</span><span class="sxs-lookup"><span data-stu-id="590d6-157">Sets the verbosity level of the command.</span></span> <span data-ttu-id="590d6-158">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="590d6-158">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="590d6-159">El valor predeterminado es `minimal`.</span><span class="sxs-lookup"><span data-stu-id="590d6-159">Default value is `minimal`.</span></span>

- **`--version-suffix <VERSION_SUFFIX>`**

  <span data-ttu-id="590d6-160">Define el sufijo de versión para reemplazar el asterisco (`*`) en el campo de versión del archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="590d6-160">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

## <a name="examples"></a><span data-ttu-id="590d6-161">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="590d6-161">Examples</span></span>

- <span data-ttu-id="590d6-162">Cree un [archivo binario multiplataforma dependiente del tiempo de ejecución ](../deploying/index.md#produce-a-cross-platform-binary) para el proyecto en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="590d6-162">Create a [runtime-dependent cross-platform binary](../deploying/index.md#produce-a-cross-platform-binary) for the project in the current directory:</span></span>

  ```dotnetcli
  dotnet publish
  ```

  <span data-ttu-id="590d6-163">A partir del SDK de .NET Core 3.0, en este ejemplo también se crea un [ ejecutable dependiente del tiempo de ejecución](../deploying/index.md#publish-runtime-dependent) para la plataforma actual.</span><span class="sxs-lookup"><span data-stu-id="590d6-163">Starting with .NET Core 3.0 SDK, this example also creates a [runtime-dependent executable](../deploying/index.md#publish-runtime-dependent) for the current platform.</span></span>

- <span data-ttu-id="590d6-164">Cree un [ejecutable independiente](../deploying/index.md#publish-self-contained) para el proyecto en el directorio actual, para un tiempo de ejecución específico:</span><span class="sxs-lookup"><span data-stu-id="590d6-164">Create a [self-contained executable](../deploying/index.md#publish-self-contained) for the project in the current directory, for a specific runtime:</span></span>

  ```dotnetcli
  dotnet publish --runtime osx.10.11-x64
  ```

  <span data-ttu-id="590d6-165">El RID debe estar en el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="590d6-165">The RID must be in the project file.</span></span>

- <span data-ttu-id="590d6-166">Cree un [ejecutable dependiente del tiempo de ejecución](../deploying/index.md#publish-runtime-dependent) para el proyecto en el directorio actual, para una plataforma específica:</span><span class="sxs-lookup"><span data-stu-id="590d6-166">Create a [runtime-dependent executable](../deploying/index.md#publish-runtime-dependent) for the project in the current directory, for a specific platform:</span></span>

  ```dotnetcli
  dotnet publish --runtime osx.10.11-x64 --self-contained false
  ```

  <span data-ttu-id="590d6-167">El RID debe estar en el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="590d6-167">The RID must be in the project file.</span></span> <span data-ttu-id="590d6-168">Este ejemplo se aplica al SDK de .NET Core 3.0 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="590d6-168">This example applies to .NET Core 3.0 SDK and later versions.</span></span>

- <span data-ttu-id="590d6-169">Publique el proyecto en el directorio actual, para un tiempo de ejecución específico y una plataforma de destino:</span><span class="sxs-lookup"><span data-stu-id="590d6-169">Publish the project in the current directory, for a specific runtime and target framework:</span></span>

  ```dotnetcli
  dotnet publish --framework netcoreapp3.1 --runtime osx.10.11-x64
  ```

- <span data-ttu-id="590d6-170">Publique el archivo del proyecto especificado:</span><span class="sxs-lookup"><span data-stu-id="590d6-170">Publish the specified project file:</span></span>

  ```dotnetcli
  dotnet publish ~/projects/app1/app1.csproj
  ```

- <span data-ttu-id="590d6-171">Publique la aplicación actual pero sin restaurar las referencias de proyecto a proyecto (P2P), solo el proyecto raíz, durante la operación de restauración:</span><span class="sxs-lookup"><span data-stu-id="590d6-171">Publish the current application but don't restore project-to-project (P2P) references, just the root project during the restore operation:</span></span>

  ```dotnetcli
  dotnet publish --no-dependencies
  ```

## <a name="see-also"></a><span data-ttu-id="590d6-172">Vea también</span><span class="sxs-lookup"><span data-stu-id="590d6-172">See also</span></span>

- [<span data-ttu-id="590d6-173">Información general sobre la publicación de aplicaciones de .NET Core</span><span class="sxs-lookup"><span data-stu-id="590d6-173">.NET Core application publishing overview</span></span>](../deploying/index.md)
- [<span data-ttu-id="590d6-174">Publicación de aplicaciones .NET Core con la CLI de .NET Core</span><span class="sxs-lookup"><span data-stu-id="590d6-174">Publish .NET Core apps with the .NET Core CLI</span></span>](../deploying/deploy-with-cli.md)
- [<span data-ttu-id="590d6-175">Marcos de trabajo de destino</span><span class="sxs-lookup"><span data-stu-id="590d6-175">Target frameworks</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="590d6-176">Catálogo de identificadores de tiempo de ejecución (RID)</span><span class="sxs-lookup"><span data-stu-id="590d6-176">Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
- <span data-ttu-id="590d6-177">[Trabajo con la certificación de macOS Catalina](../install/macos-notarization-issues.md) Para obtener más información, vea los recursos siguientes:</span><span class="sxs-lookup"><span data-stu-id="590d6-177">[Working with macOS Catalina Notarization](../install/macos-notarization-issues.md) For more information, see he following resources:</span></span>
- [<span data-ttu-id="590d6-178">Estructura de directorios de una aplicación publicada</span><span class="sxs-lookup"><span data-stu-id="590d6-178">Directory structure of a published application</span></span>](/aspnet/core/hosting/directory-structure)
