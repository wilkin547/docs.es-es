---
title: Almacenamiento de paquetes en tiempo de ejecución
description: Aprenda a usar el almacenamiento de paquetes en tiempo de ejecución para destinar manifiestos que usa .NET Core.
ms.date: 08/12/2017
ms.openlocfilehash: 4395370c3bb2d97511d549a63813022fb8cac4b7
ms.sourcegitcommit: c2c1269a81ffdcfc8675bcd9a8505b1a11ffb271
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/25/2020
ms.locfileid: "82158299"
---
# <a name="runtime-package-store"></a><span data-ttu-id="5b586-103">Almacenamiento de paquetes en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="5b586-103">Runtime package store</span></span>

<span data-ttu-id="5b586-104">A partir de .NET Core 2.0, es posible empaquetar e implementar aplicaciones en un conjunto conocido de paquetes que existen en el entorno de destino.</span><span class="sxs-lookup"><span data-stu-id="5b586-104">Starting with .NET Core 2.0, it's possible to package and deploy apps against a known set of packages that exist in the target environment.</span></span> <span data-ttu-id="5b586-105">Las ventajas son implementaciones más rápidas, menor uso de espacio en disco y un rendimiento de inicio mejorado en algunos casos.</span><span class="sxs-lookup"><span data-stu-id="5b586-105">The benefits are faster deployments, lower disk space usage, and improved startup performance in some cases.</span></span>

<span data-ttu-id="5b586-106">Esta característica se implementa como un *almacenamiento de paquetes en tiempo de ejecución*, que es un directorio en disco donde se almacenan los paquetes (normalmente en */usr/local/share/dotnet/store* en macOS/Linux y *C:/Program Files/dotnet/store* en Windows).</span><span class="sxs-lookup"><span data-stu-id="5b586-106">This feature is implemented as a *runtime package store*, which is a directory on disk where packages are stored (typically at */usr/local/share/dotnet/store* on macOS/Linux and *C:/Program Files/dotnet/store* on Windows).</span></span> <span data-ttu-id="5b586-107">En este directorio, existen subdirectorios para las arquitecturas y las [plataformas de destino](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="5b586-107">Under this directory, there are subdirectories for architectures and [target frameworks](../../standard/frameworks.md).</span></span> <span data-ttu-id="5b586-108">El diseño del archivo es similar a la manera en que los [activos de NuGet se colocan en el disco](/nuget/create-packages/supporting-multiple-target-frameworks#framework-version-folder-structure):</span><span class="sxs-lookup"><span data-stu-id="5b586-108">The file layout is similar to the way that [NuGet assets are laid out on disk](/nuget/create-packages/supporting-multiple-target-frameworks#framework-version-folder-structure):</span></span>

```
\dotnet
    \store
        \x64
            \netcoreapp2.0
                \microsoft.applicationinsights
                \microsoft.aspnetcore
                ...
        \x86
            \netcoreapp2.0
                \microsoft.applicationinsights
                \microsoft.aspnetcore
                ...
```

<span data-ttu-id="5b586-109">Un archivo de *manifiesto de destino* muestra los paquetes en el almacenamiento de paquetes en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="5b586-109">A *target manifest* file lists the packages in the runtime package store.</span></span> <span data-ttu-id="5b586-110">Los desarrolladores pueden dirigirse a este manifiesto cuando publican su aplicación.</span><span class="sxs-lookup"><span data-stu-id="5b586-110">Developers can target this manifest when publishing their app.</span></span> <span data-ttu-id="5b586-111">Normalmente, el propietario del entorno de producción de destino proporciona el manifiesto de destino.</span><span class="sxs-lookup"><span data-stu-id="5b586-111">The target manifest is typically provided by the owner of the targeted production environment.</span></span>

## <a name="preparing-a-runtime-environment"></a><span data-ttu-id="5b586-112">Preparación de un entorno en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="5b586-112">Preparing a runtime environment</span></span>

<span data-ttu-id="5b586-113">El administrador de un entorno en tiempo de ejecución puede optimizar aplicaciones para obtener implementaciones más rápidas y un menor uso de espacio en disco creando un almacenamiento de paquetes en tiempo de ejecución y el manifiesto de destino correspondiente.</span><span class="sxs-lookup"><span data-stu-id="5b586-113">The administrator of a runtime environment can optimize apps for faster deployments and lower disk space use by building a runtime package store and the corresponding target manifest.</span></span>

<span data-ttu-id="5b586-114">El primer paso consiste en crear un *manifiesto de almacenamiento de paquetes* que muestra los paquetes que forman el almacenamiento de paquetes en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="5b586-114">The first step is to create a *package store manifest* that lists the packages that compose the runtime package store.</span></span> <span data-ttu-id="5b586-115">El formato de archivo es compatible con el formato de archivo del proyecto (*csproj*).</span><span class="sxs-lookup"><span data-stu-id="5b586-115">This file format is compatible with the project file format (*csproj*).</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <ItemGroup>
    <PackageReference Include="NUGET_PACKAGE" Version="VERSION" />
    <!-- Include additional packages here -->
  </ItemGroup>
</Project>
```

<span data-ttu-id="5b586-116">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="5b586-116">**Example**</span></span>

<span data-ttu-id="5b586-117">El siguiente manifiesto de almacenamiento de paquetes de ejemplo (*packages.csproj*) se usa para agregar [`Newtonsoft.Json`](https://www.nuget.org/packages/Newtonsoft.Json/) y [`Moq`](https://www.nuget.org/packages/moq/) a un almacenamiento de paquetes en tiempo de ejecución:</span><span class="sxs-lookup"><span data-stu-id="5b586-117">The following example package store manifest (*packages.csproj*) is used to add [`Newtonsoft.Json`](https://www.nuget.org/packages/Newtonsoft.Json/) and [`Moq`](https://www.nuget.org/packages/moq/) to a runtime package store:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <ItemGroup>
    <PackageReference Include="Newtonsoft.Json" Version="10.0.3" />
    <PackageReference Include="Moq" Version="4.7.63" />
  </ItemGroup>
</Project>
```

<span data-ttu-id="5b586-118">Aprovisione el almacenamiento de paquetes en tiempo de ejecución ejecutando `dotnet store` con el manifiesto de almacenamiento de paquetes, el runtime y el marco:</span><span class="sxs-lookup"><span data-stu-id="5b586-118">Provision the runtime package store by executing `dotnet store` with the package store manifest, runtime, and framework:</span></span>

```dotnetcli
dotnet store --manifest <PATH_TO_MANIFEST_FILE> --runtime <RUNTIME_IDENTIFIER> --framework <FRAMEWORK>
```

<span data-ttu-id="5b586-119">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="5b586-119">**Example**</span></span>

```dotnetcli
dotnet store --manifest packages.csproj --runtime win10-x64 --framework netcoreapp2.0 --framework-version 2.0.0
```

<span data-ttu-id="5b586-120">Puede pasar varias rutas de manifiesto de almacenamiento de paquetes de destino a un único comando [`dotnet store`](../tools/dotnet-store.md) repitiendo la opción y la ruta en el comando.</span><span class="sxs-lookup"><span data-stu-id="5b586-120">You can pass multiple target package store manifest paths to a single [`dotnet store`](../tools/dotnet-store.md) command by repeating the option and path in the command.</span></span>

<span data-ttu-id="5b586-121">De manera predeterminada, el resultado del comando es un almacenamiento de paquetes en el subdirectorio *.dotnet/store* del perfil de usuario.</span><span class="sxs-lookup"><span data-stu-id="5b586-121">By default, the output of the command is a package store under the *.dotnet/store* subdirectory of the user's profile.</span></span> <span data-ttu-id="5b586-122">Puede especificar una ubicación diferente con la opción `--output <OUTPUT_DIRECTORY>`.</span><span class="sxs-lookup"><span data-stu-id="5b586-122">You can specify a different location using the `--output <OUTPUT_DIRECTORY>` option.</span></span> <span data-ttu-id="5b586-123">El directorio raíz del almacenamiento contiene un archivo *artifact.xml* de manifiesto de destino.</span><span class="sxs-lookup"><span data-stu-id="5b586-123">The root directory of the store contains a target manifest *artifact.xml* file.</span></span> <span data-ttu-id="5b586-124">Este archivo puede estar disponible para su descarga y usarse por los autores de aplicaciones que quieran dirigirse a este almacenamiento al realizar la publicación.</span><span class="sxs-lookup"><span data-stu-id="5b586-124">This file can be made available for download and be used by app authors who want to target this store when publishing.</span></span>

<span data-ttu-id="5b586-125">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="5b586-125">**Example**</span></span>

<span data-ttu-id="5b586-126">El siguiente archivo *artifact.xml* se genera después de ejecutar el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="5b586-126">The following *artifact.xml* file is produced after running the previous example.</span></span> <span data-ttu-id="5b586-127">Tenga en cuenta que [`Castle.Core`](https://www.nuget.org/packages/Castle.Core/) es una dependencia de `Moq`, de manera que se incluye automáticamente y aparece en el archivo de manifiesto *artifacts.xml*.</span><span class="sxs-lookup"><span data-stu-id="5b586-127">Note that [`Castle.Core`](https://www.nuget.org/packages/Castle.Core/) is a dependency of `Moq`, so it's included automatically and appears in the *artifacts.xml* manifest file.</span></span>

```xml
<StoreArtifacts>
  <Package Id="Newtonsoft.Json" Version="10.0.3" />
  <Package Id="Castle.Core" Version="4.1.0" />
  <Package Id="Moq" Version="4.7.63" />
</StoreArtifacts>
```

## <a name="publishing-an-app-against-a-target-manifest"></a><span data-ttu-id="5b586-128">Publicación de una aplicación en un manifiesto de destino</span><span class="sxs-lookup"><span data-stu-id="5b586-128">Publishing an app against a target manifest</span></span>

<span data-ttu-id="5b586-129">Si tiene un archivo de manifiesto de destino en disco, especifique la ruta al archivo al publicar su aplicación con el comando [`dotnet publish`](../tools/dotnet-publish.md):</span><span class="sxs-lookup"><span data-stu-id="5b586-129">If you have a target manifest file on disk, you specify the path to the file when publishing your app with the [`dotnet publish`](../tools/dotnet-publish.md) command:</span></span>

```dotnetcli
dotnet publish --manifest <PATH_TO_MANIFEST_FILE>
```

<span data-ttu-id="5b586-130">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="5b586-130">**Example**</span></span>

```dotnetcli
dotnet publish --manifest manifest.xml
```

<span data-ttu-id="5b586-131">Implemente la aplicación publicada resultante en un entorno que tenga los paquetes descritos en el manifiesto de destino.</span><span class="sxs-lookup"><span data-stu-id="5b586-131">You deploy the resulting published app to an environment that has the packages described in the target manifest.</span></span> <span data-ttu-id="5b586-132">Realizar esto incorrectamente produce errores en el inicio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5b586-132">Failing to do so results in the app failing to start.</span></span>

<span data-ttu-id="5b586-133">Especifique varios manifiestos de destino al publicar una aplicación repitiendo la opción y la ruta (por ejemplo, `--manifest manifest1.xml --manifest manifest2.xml`).</span><span class="sxs-lookup"><span data-stu-id="5b586-133">Specify multiple target manifests when publishing an app by repeating the option and path (for example, `--manifest manifest1.xml --manifest manifest2.xml`).</span></span> <span data-ttu-id="5b586-134">Cuando realice esto, la aplicación se reduce para la unión de los paquetes especificados en los archivos de manifiesto de destino que se proporcionan para el comando.</span><span class="sxs-lookup"><span data-stu-id="5b586-134">When you do so, the app is trimmed for the union of packages specified in the target manifest files provided to the command.</span></span>

<span data-ttu-id="5b586-135">Si implementa una aplicación con una dependencia de manifiesto que está presente en la implementación (el ensamblado está presente en la carpeta *bin*), el almacenamiento de paquetes en tiempo de ejecución *no se usa* en el host de ese ensamblado.</span><span class="sxs-lookup"><span data-stu-id="5b586-135">If you deploy an application with a manifest dependency that's present in the deployment (the assembly is present in the *bin* folder), the runtime package store *isn't used* on the host for that assembly.</span></span> <span data-ttu-id="5b586-136">El ensamblado de la carpeta *bin* se usa independientemente de su presencia en el almacenamiento de paquetes en tiempo de ejecución en el host.</span><span class="sxs-lookup"><span data-stu-id="5b586-136">The *bin* folder assembly is used regardless of its presence in the runtime package store on the host.</span></span>

<span data-ttu-id="5b586-137">La versión de la dependencia indicada en el manifiesto debe coincidir con la versión de la dependencia en el almacenamiento de paquetes en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="5b586-137">The version of the dependency indicated in the manifest must match the version of the dependency in the runtime package store.</span></span> <span data-ttu-id="5b586-138">Si no coinciden las versiones entre la dependencia del manifiesto de destino y la versión que existe en el almacenamiento de paquetes en tiempo de ejecución, y la aplicación no incluye la versión necesaria del paquete en su implementación, se produce un error en el inicio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5b586-138">If you have a version mismatch between the dependency in the target manifest and the version that exists in the runtime package store and the app doesn't include the required version of the package in its deployment, the app fails to start.</span></span> <span data-ttu-id="5b586-139">La excepción incluye el nombre del manifiesto de destino que se ha llamado para el ensamblado del almacenamiento de paquetes en tiempo de ejecución, que le ayuda a solucionar los errores de coincidencia.</span><span class="sxs-lookup"><span data-stu-id="5b586-139">The exception includes the name of the target manifest that called for the runtime package store assembly, which helps you troubleshoot the mismatch.</span></span>

<span data-ttu-id="5b586-140">Cuando la implementación se *reduce* en su publicación, solo las versiones específicas de los paquetes de manifiesto que indique se retienen del resultado publicado.</span><span class="sxs-lookup"><span data-stu-id="5b586-140">When the deployment is *trimmed* on publish, only the specific versions of the manifest packages you indicate are withheld from the published output.</span></span> <span data-ttu-id="5b586-141">Los paquetes de las versiones indicadas deben estar presentes en el host para que se inicie la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5b586-141">The packages at the versions indicated must be present on the host for the app to start.</span></span>

## <a name="specifying-target-manifests-in-the-project-file"></a><span data-ttu-id="5b586-142">Especificar los manifiestos de destino en el archivo del proyecto</span><span class="sxs-lookup"><span data-stu-id="5b586-142">Specifying target manifests in the project file</span></span>

<span data-ttu-id="5b586-143">Una alternativa de especificar manifiestos de destino con el comando [`dotnet publish`](../tools/dotnet-publish.md) es especificarlos en el archivo de proyecto como una lista de rutas separadas por punto y coma en una etiqueta **\<TargetManifestFiles>** .</span><span class="sxs-lookup"><span data-stu-id="5b586-143">An alternative to specifying target manifests with the [`dotnet publish`](../tools/dotnet-publish.md) command is to specify them in the project file as a semicolon-separated list of paths under a **\<TargetManifestFiles>** tag.</span></span>

```xml
<PropertyGroup>
  <TargetManifestFiles>manifest1.xml;manifest2.xml</TargetManifestFiles>
</PropertyGroup>
```

<span data-ttu-id="5b586-144">Especifique los manifiestos de destino en el archivo de proyecto solo cuando el entorno de destino de la aplicación sea muy conocido, como para los proyectos de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="5b586-144">Specify the target manifests in the project file only when the target environment for the app is well-known, such as for .NET Core projects.</span></span> <span data-ttu-id="5b586-145">Este no es el caso de los proyectos de código abierto.</span><span class="sxs-lookup"><span data-stu-id="5b586-145">This isn't the case for open-source projects.</span></span> <span data-ttu-id="5b586-146">Los usuarios de un proyecto de código abierto normalmente lo implementan en diferentes entornos de producción.</span><span class="sxs-lookup"><span data-stu-id="5b586-146">The users of an open-source project typically deploy it to different production environments.</span></span> <span data-ttu-id="5b586-147">Estos entornos de producción generalmente tienen diferentes conjuntos de paquetes preinstalados.</span><span class="sxs-lookup"><span data-stu-id="5b586-147">These production environments generally have different sets of packages pre-installed.</span></span> <span data-ttu-id="5b586-148">No puede realizar presuposiciones sobre el manifiesto de destino en dichos entornos, por lo que debe usar la opción `--manifest` de [`dotnet publish`](../tools/dotnet-publish.md).</span><span class="sxs-lookup"><span data-stu-id="5b586-148">You can't make assumptions about the target manifest in such environments, so you should use the `--manifest` option of [`dotnet publish`](../tools/dotnet-publish.md).</span></span>

## <a name="aspnet-core-implicit-store-net-core-20-only"></a><span data-ttu-id="5b586-149">Almacenamiento implícito de ASP.NET Core(solo .NET Core 2.0)</span><span class="sxs-lookup"><span data-stu-id="5b586-149">ASP.NET Core implicit store (.NET Core 2.0 only)</span></span>

<span data-ttu-id="5b586-150">El almacenamiento implícito de ASP.NET Core solo se aplica a ASP.NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="5b586-150">The ASP.NET Core implicit store applies only to ASP.NET Core 2.0.</span></span> <span data-ttu-id="5b586-151">Se recomienda encarecidamente que las aplicaciones usen ASP.NET Core 2.1 y versiones posteriores, que **no** usan almacenamiento implícito.</span><span class="sxs-lookup"><span data-stu-id="5b586-151">We strongly recommend applications use ASP.NET Core 2.1 and later, which does **not** use the implicit store.</span></span> <span data-ttu-id="5b586-152">ASP.NET Core 2.1 y versiones posteriores usan el marco de trabajo compartido.</span><span class="sxs-lookup"><span data-stu-id="5b586-152">ASP.NET Core 2.1 and later use the shared framework.</span></span>

<span data-ttu-id="5b586-153">En el caso de .NET Core 2.0, una aplicación de ASP NET Core usa implícitamente la característica de almacenamiento de paquetes en tiempo de ejecución cuando la aplicación se implementa como aplicación de [implementación dependiente del entorno de ejecución](index.md#publish-runtime-dependent).</span><span class="sxs-lookup"><span data-stu-id="5b586-153">For .NET Core 2.0, the runtime package store feature is used implicitly by an ASP.NET Core app when the app is deployed as a [runtime-dependent deployment](index.md#publish-runtime-dependent) app.</span></span> <span data-ttu-id="5b586-154">Los destinos en [`Microsoft.NET.Sdk.Web`](https://github.com/aspnet/websdk) incluyen manifiestos que hacen referencia al almacenamiento de paquetes implícito en el sistema de destino.</span><span class="sxs-lookup"><span data-stu-id="5b586-154">The targets in [`Microsoft.NET.Sdk.Web`](https://github.com/aspnet/websdk) include manifests referencing the implicit package store on the target system.</span></span> <span data-ttu-id="5b586-155">Además, cualquier aplicación dependiente del entorno de ejecución que dependa del paquete `Microsoft.AspNetCore.All` se traducirá en una aplicación publicada que solo contiene la aplicación y sus recursos, pero no los paquetes que se muestran en el metapaquete `Microsoft.AspNetCore.All`.</span><span class="sxs-lookup"><span data-stu-id="5b586-155">Additionally, any runtime-dependent app that depends on the `Microsoft.AspNetCore.All` package results in a published app that contains only the app and its assets and not the packages listed in the `Microsoft.AspNetCore.All` metapackage.</span></span> <span data-ttu-id="5b586-156">Se presupone que esos paquetes están presentes en el sistema de destino.</span><span class="sxs-lookup"><span data-stu-id="5b586-156">It's assumed that those packages are present on the target system.</span></span>

<span data-ttu-id="5b586-157">El almacenamiento de paquetes en tiempo de ejecución está instalado en el host cuando el SDK de .NET Core está instalado.</span><span class="sxs-lookup"><span data-stu-id="5b586-157">The runtime package store is installed on the host when the .NET Core SDK is installed.</span></span> <span data-ttu-id="5b586-158">Otros instaladores pueden proporcionar el almacenamiento de paquetes en tiempo de ejecución, incluidas las instalaciones Zip/tarball del SDK de .NET Core, `apt-get`, Red Hat Yum, la agrupación de hospedaje de Windows Server para .NET Core y las instalaciones manuales de almacenamiento de paquetes en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="5b586-158">Other installers may provide the runtime package store, including Zip/tarball installations of the .NET Core SDK, `apt-get`, Red Hat Yum, the .NET Core Windows Server Hosting bundle, and manual runtime package store installations.</span></span>

<span data-ttu-id="5b586-159">Al implementar una aplicación de [implementación dependiente del entorno de ejecución](index.md#publish-runtime-dependent), asegúrese de que el entorno de destino tiene el SDK de .NET Core instalado.</span><span class="sxs-lookup"><span data-stu-id="5b586-159">When deploying a [runtime-dependent deployment](index.md#publish-runtime-dependent) app, make sure that the target environment has the .NET Core SDK installed.</span></span> <span data-ttu-id="5b586-160">Si la aplicación se implementa en un entorno que no incluye ASP.NET Core, puede rechazar el almacenamiento implícito especificando **\<PublishWithAspNetCoreTargetManifest>** en `false` en el archivo de proyecto como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5b586-160">If the app is deployed to an environment that doesn't include ASP.NET Core, you can opt out of the implicit store by specifying  **\<PublishWithAspNetCoreTargetManifest>** set to `false` in the project file as in the following example:</span></span>

```xml
<PropertyGroup>
  <PublishWithAspNetCoreTargetManifest>false</PublishWithAspNetCoreTargetManifest>
</PropertyGroup>
```

> [!NOTE]
> <span data-ttu-id="5b586-161">En el caso de las aplicaciones de [implementación independiente](index.md#publish-self-contained), se presupone que el sistema de destino no contiene necesariamente los paquetes de manifiesto necesarios.</span><span class="sxs-lookup"><span data-stu-id="5b586-161">For [self-contained deployment](index.md#publish-self-contained) apps, it's assumed that the target system doesn't necessarily contain the required manifest packages.</span></span> <span data-ttu-id="5b586-162">Por lo tanto, **\<PublishWithAspNetCoreTargetManifest>** no puede establecerse en `true` para una aplicación independiente.</span><span class="sxs-lookup"><span data-stu-id="5b586-162">Therefore, **\<PublishWithAspNetCoreTargetManifest>** cannot be set to `true` for an self-contained app.</span></span>

## <a name="see-also"></a><span data-ttu-id="5b586-163">Vea también</span><span class="sxs-lookup"><span data-stu-id="5b586-163">See also</span></span>

- [<span data-ttu-id="5b586-164">dotnet-publish</span><span class="sxs-lookup"><span data-stu-id="5b586-164">dotnet-publish</span></span>](../tools/dotnet-publish.md)
- [<span data-ttu-id="5b586-165">dotnet-store</span><span class="sxs-lookup"><span data-stu-id="5b586-165">dotnet-store</span></span>](../tools/dotnet-store.md)
