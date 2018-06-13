---
title: Almacenamiento de paquetes en tiempo de ejecución
description: En este tema se explica el almacenamiento de paquetes en tiempo de ejecución y los manifiestos de destino que usa .NET Core.
author: bleroy
ms.author: mairaw
ms.date: 08/12/2017
ms.openlocfilehash: aba1939cda8459d8b0d9438a97545c19d3c1926d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33218708"
---
# <a name="runtime-package-store"></a><span data-ttu-id="919fb-103">Almacenamiento de paquetes en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="919fb-103">Runtime package store</span></span>

<span data-ttu-id="919fb-104">A partir de .NET Core 2.0, es posible empaquetar e implementar aplicaciones en un conjunto conocido de paquetes que existen en el entorno de destino.</span><span class="sxs-lookup"><span data-stu-id="919fb-104">Starting with .NET Core 2.0, it's possible to package and deploy apps against a known set of packages that exist in the target environment.</span></span> <span data-ttu-id="919fb-105">Las ventajas son implementaciones más rápidas, menor uso de espacio en disco y un rendimiento de inicio mejorado en algunos casos.</span><span class="sxs-lookup"><span data-stu-id="919fb-105">The benefits are faster deployments, lower disk space use, and improved startup performance in some cases.</span></span>

<span data-ttu-id="919fb-106">Esta característica se implementa como un *almacenamiento de paquetes en tiempo de ejecución*, que es un directorio en disco donde se almacenan los paquetes (normalmente en */usr/local/share/dotnet/store* en macOS/Linux y *C:/Program Files/dotnet/store* en Windows).</span><span class="sxs-lookup"><span data-stu-id="919fb-106">This feature is implemented as a *runtime package store*, which is a directory on disk where packages are stored (typically at */usr/local/share/dotnet/store* on macOS/Linux and *C:/Program Files/dotnet/store* on Windows).</span></span> <span data-ttu-id="919fb-107">En este directorio, existen subdirectorios para las arquitecturas y las [plataformas de destino](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="919fb-107">Under this directory, there are subdirectories for architectures and [target frameworks](../../standard/frameworks.md).</span></span> <span data-ttu-id="919fb-108">El diseño del archivo es similar a la manera en que los [activos de NuGet se colocan en el disco](/nuget/create-packages/supporting-multiple-target-frameworks#framework-version-folder-structure):</span><span class="sxs-lookup"><span data-stu-id="919fb-108">The file layout is similar to the way that [NuGet assets are laid out on disk](/nuget/create-packages/supporting-multiple-target-frameworks#framework-version-folder-structure):</span></span>

<span data-ttu-id="919fb-109">\dotnet</span><span class="sxs-lookup"><span data-stu-id="919fb-109">\dotnet</span></span>   
<span data-ttu-id="919fb-110">&nbsp;&nbsp;\store</span><span class="sxs-lookup"><span data-stu-id="919fb-110">&nbsp;&nbsp;\store</span></span>   
<span data-ttu-id="919fb-111">&nbsp;&nbsp;&nbsp;&nbsp;\x64</span><span class="sxs-lookup"><span data-stu-id="919fb-111">&nbsp;&nbsp;&nbsp;&nbsp;\x64</span></span>   
<span data-ttu-id="919fb-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\netcoreapp2.0</span><span class="sxs-lookup"><span data-stu-id="919fb-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\netcoreapp2.0</span></span>   
<span data-ttu-id="919fb-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\microsoft.applicationinsights</span><span class="sxs-lookup"><span data-stu-id="919fb-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\microsoft.applicationinsights</span></span>   
<span data-ttu-id="919fb-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\microsoft.aspnetcore</span><span class="sxs-lookup"><span data-stu-id="919fb-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\microsoft.aspnetcore</span></span>   
<span data-ttu-id="919fb-115">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;...</span><span class="sxs-lookup"><span data-stu-id="919fb-115">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;...</span></span>   
<span data-ttu-id="919fb-116">&nbsp;&nbsp;&nbsp;&nbsp;\x86</span><span class="sxs-lookup"><span data-stu-id="919fb-116">&nbsp;&nbsp;&nbsp;&nbsp;\x86</span></span>   
<span data-ttu-id="919fb-117">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\netcoreapp2.0</span><span class="sxs-lookup"><span data-stu-id="919fb-117">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\netcoreapp2.0</span></span>   
<span data-ttu-id="919fb-118">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\microsoft.applicationinsights</span><span class="sxs-lookup"><span data-stu-id="919fb-118">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\microsoft.applicationinsights</span></span>   
<span data-ttu-id="919fb-119">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\microsoft.aspnetcore</span><span class="sxs-lookup"><span data-stu-id="919fb-119">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\microsoft.aspnetcore</span></span>   
<span data-ttu-id="919fb-120">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;...</span><span class="sxs-lookup"><span data-stu-id="919fb-120">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;...</span></span>   

<span data-ttu-id="919fb-121">Un archivo de *manifiesto de destino* muestra los paquetes en el almacenamiento de paquetes en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="919fb-121">A *target manifest* file lists the packages in the runtime package store.</span></span> <span data-ttu-id="919fb-122">Los desarrolladores pueden dirigirse a este manifiesto cuando publican su aplicación.</span><span class="sxs-lookup"><span data-stu-id="919fb-122">Developers can target this manifest when publishing their app.</span></span> <span data-ttu-id="919fb-123">Normalmente, el propietario del entorno de producción de destino proporciona el manifiesto de destino.</span><span class="sxs-lookup"><span data-stu-id="919fb-123">The target manifest is typically provided by the owner of the targeted production environment.</span></span>

## <a name="preparing-a-runtime-environment"></a><span data-ttu-id="919fb-124">Preparación de un entorno en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="919fb-124">Preparing a runtime environment</span></span>

<span data-ttu-id="919fb-125">El administrador de un entorno en tiempo de ejecución puede optimizar aplicaciones para obtener implementaciones más rápidas y un menor uso de espacio en disco creando un almacenamiento de paquetes en tiempo de ejecución y el manifiesto de destino correspondiente.</span><span class="sxs-lookup"><span data-stu-id="919fb-125">The administrator of a runtime environment can optimize apps for faster deployments and lower disk space use by building a runtime package store and the corresponding target manifest.</span></span>

<span data-ttu-id="919fb-126">El primer paso consiste en crear un *manifiesto de almacenamiento de paquetes* que muestra los paquetes que forman el almacenamiento de paquetes en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="919fb-126">The first step is to create a *package store manifest* that lists the packages that compose the runtime package store.</span></span> <span data-ttu-id="919fb-127">El formato de archivo es compatible con el formato de archivo del proyecto (*csproj*).</span><span class="sxs-lookup"><span data-stu-id="919fb-127">This file format is compatible with the project file format (*csproj*).</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <ItemGroup>
    <PackageReference Include="<NUGET_PACKAGE>" Version="<VERSION>" />
    <!-- Include additional packages here -->
  </ItemGroup>
</Project>
```

<span data-ttu-id="919fb-128">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="919fb-128">**Example**</span></span>

<span data-ttu-id="919fb-129">El siguiente manifiesto de almacenamiento de paquetes de ejemplo (*packages.csproj*) se usa para agregar [`Newtonsoft.Json`](https://www.nuget.org/packages/Newtonsoft.Json/) y [`Moq`](https://www.nuget.org/packages/moq/) a un almacenamiento de paquetes en tiempo de ejecución:</span><span class="sxs-lookup"><span data-stu-id="919fb-129">The following example package store manifest (*packages.csproj*) is used to add [`Newtonsoft.Json`](https://www.nuget.org/packages/Newtonsoft.Json/) and [`Moq`](https://www.nuget.org/packages/moq/) to a runtime package store:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <ItemGroup>
    <PackageReference Include="Newtonsoft.Json" Version="10.0.3" />
    <PackageReference Include="Moq" Version="4.7.63" />
  </ItemGroup>
</Project>
```

<span data-ttu-id="919fb-130">Aprovisione el almacenamiento de paquetes en tiempo de ejecución ejecutando `dotnet store` con el manifiesto de almacenamiento de paquetes, el runtime y el marco:</span><span class="sxs-lookup"><span data-stu-id="919fb-130">Provision the runtime package store by executing `dotnet store` with the package store manifest, runtime, and framework:</span></span>

```console
dotnet store --manifest <PATH_TO_MANIFEST_FILE> --runtime <RUNTIME_IDENTIFIER> --framework <FRAMEWORK>
```

<span data-ttu-id="919fb-131">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="919fb-131">**Example**</span></span>

```console
dotnet store --manifest packages.csproj --runtime win10-x64 --framework netcoreapp2.0 --framework-version 2.0.0
```

<span data-ttu-id="919fb-132">Puede pasar varias rutas de manifiesto de almacenamiento de paquetes de destino a un único comando [`dotnet store`](../tools/dotnet-store.md) repitiendo la opción y la ruta en el comando.</span><span class="sxs-lookup"><span data-stu-id="919fb-132">You can pass multiple target package store manifest paths to a single [`dotnet store`](../tools/dotnet-store.md) command by repeating the option and path in the command.</span></span>

<span data-ttu-id="919fb-133">De manera predeterminada, el resultado del comando es un almacenamiento de paquetes en el subdirectorio *.dotnet/store* del perfil de usuario.</span><span class="sxs-lookup"><span data-stu-id="919fb-133">By default, the output of the command is a package store under the *.dotnet/store* subdirectory of the user's profile.</span></span> <span data-ttu-id="919fb-134">Puede especificar una ubicación diferente con la opción `--output <OUTPUT_DIRECTORY>`.</span><span class="sxs-lookup"><span data-stu-id="919fb-134">You can specify a different location using the `--output <OUTPUT_DIRECTORY>` option.</span></span> <span data-ttu-id="919fb-135">El directorio raíz del almacenamiento contiene un archivo *artifact.xml* de manifiesto de destino.</span><span class="sxs-lookup"><span data-stu-id="919fb-135">The root directory of the store contains a target manifest *artifact.xml* file.</span></span> <span data-ttu-id="919fb-136">Este archivo puede estar disponible para su descarga y usarse por los autores de aplicaciones que quieran dirigirse a este almacenamiento al realizar la publicación.</span><span class="sxs-lookup"><span data-stu-id="919fb-136">This file can be made available for download and be used by app authors who want to target this store when publishing.</span></span>

<span data-ttu-id="919fb-137">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="919fb-137">**Example**</span></span>

<span data-ttu-id="919fb-138">El siguiente archivo *artifact.xml* se genera después de ejecutar el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="919fb-138">The following *artifact.xml* file is produced after running the previous example.</span></span> <span data-ttu-id="919fb-139">Tenga en cuenta que [`Castle.Core`](https://www.nuget.org/packages/Castle.Core/) es una dependencia de `Moq`, de manera que se incluye automáticamente y aparece en el archivo de manifiesto *artifacts.xml*.</span><span class="sxs-lookup"><span data-stu-id="919fb-139">Note that [`Castle.Core`](https://www.nuget.org/packages/Castle.Core/) is a dependency of `Moq`, so it's included automatically and appears in the *artifacts.xml* manifest file.</span></span>

```xml
<StoreArtifacts>
  <Package Id="Newtonsoft.Json" Version="10.0.3" />
  <Package Id="Castle.Core" Version="4.1.0" />
  <Package Id="Moq" Version="4.7.63" />
</StoreArtifacts>
```

## <a name="publishing-an-app-against-a-target-manifest"></a><span data-ttu-id="919fb-140">Publicación de una aplicación en un manifiesto de destino</span><span class="sxs-lookup"><span data-stu-id="919fb-140">Publishing an app against a target manifest</span></span>

<span data-ttu-id="919fb-141">Si tiene un archivo de manifiesto de destino en disco, especifique la ruta al archivo al publicar su aplicación con el comando [`dotnet publish`](../tools/dotnet-publish.md):</span><span class="sxs-lookup"><span data-stu-id="919fb-141">If you have a target manifest file on disk, you specify the path to the file when publishing your app with the [`dotnet publish`](../tools/dotnet-publish.md) command:</span></span>

```console
dotnet publish --manifest <PATH_TO_MANIFEST_FILE>
```

<span data-ttu-id="919fb-142">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="919fb-142">**Example**</span></span>

```console
dotnet publish --manifest manifest.xml
```

<span data-ttu-id="919fb-143">Implemente la aplicación publicada resultante en un entorno que tenga los paquetes descritos en el manifiesto de destino.</span><span class="sxs-lookup"><span data-stu-id="919fb-143">You deploy the resulting published app to an environment that has the packages described in the target manifest.</span></span> <span data-ttu-id="919fb-144">Realizar esto incorrectamente produce errores en el inicio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="919fb-144">Failing to do so results in the app failing to start.</span></span>

<span data-ttu-id="919fb-145">Especifique varios manifiestos de destino al publicar una aplicación repitiendo la opción y la ruta (por ejemplo, `--manifest manifest1.xml --manifest manifest2.xml`).</span><span class="sxs-lookup"><span data-stu-id="919fb-145">Specify multiple target manifests when publishing an app by repeating the option and path (for example, `--manifest manifest1.xml --manifest manifest2.xml`).</span></span> <span data-ttu-id="919fb-146">Cuando realice esto, la aplicación se reduce para la unión de los paquetes especificados en los archivos de manifiesto de destino que se proporcionan para el comando.</span><span class="sxs-lookup"><span data-stu-id="919fb-146">When you do so, the app is trimmed for the union of packages specified in the target manifest files provided to the command.</span></span>

## <a name="specifying-target-manifests-in-the-project-file"></a><span data-ttu-id="919fb-147">Especificar los manifiestos de destino en el archivo del proyecto</span><span class="sxs-lookup"><span data-stu-id="919fb-147">Specifying target manifests in the project file</span></span>

<span data-ttu-id="919fb-148">Una alternativa de especificar manifiestos de destino con el comando [`dotnet publish`](../tools/dotnet-publish.md) es especificarlos en el archivo de proyecto como una lista de rutas separadas por punto y coma en una etiqueta **\<TargetManifestFiles>**.</span><span class="sxs-lookup"><span data-stu-id="919fb-148">An alternative to specifying target manifests with the [`dotnet publish`](../tools/dotnet-publish.md) command is to specify them in the project file as a semicolon-separated list of paths under a **\<TargetManifestFiles>** tag.</span></span>

```xml
<PropertyGroup>
  <TargetManifestFiles>manifest1.xml;manifest2.xml</TargetManifestFiles>
</PropertyGroup>
```

<span data-ttu-id="919fb-149">Especifique los manifiestos de destino en el archivo de proyecto solo cuando el entorno de destino de la aplicación sea muy conocido, como para los proyectos de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="919fb-149">Specify the target manifests in the project file only when the target environment for the app is well-known, such as for .NET Core projects.</span></span> <span data-ttu-id="919fb-150">Este no es el caso de los proyectos de código abierto.</span><span class="sxs-lookup"><span data-stu-id="919fb-150">This isn't the case for open-source projects.</span></span> <span data-ttu-id="919fb-151">Los usuarios de un proyecto de código abierto normalmente lo implementan en diferentes entornos de producción.</span><span class="sxs-lookup"><span data-stu-id="919fb-151">The users of an open-source project typically deploy it to different production environments.</span></span> <span data-ttu-id="919fb-152">Estos entornos de producción generalmente tienen diferentes conjuntos de paquetes preinstalados.</span><span class="sxs-lookup"><span data-stu-id="919fb-152">These production environments generally have different sets of packages pre-installed.</span></span> <span data-ttu-id="919fb-153">No puede realizar presuposiciones sobre el manifiesto de destino en dichos entornos, por lo que debe usar la opción `--manifest` de [`dotnet publish`](../tools/dotnet-publish.md).</span><span class="sxs-lookup"><span data-stu-id="919fb-153">You can't make assumptions about the target manifest in such environments, so you should use the `--manifest` option of [`dotnet publish`](../tools/dotnet-publish.md).</span></span>

## <a name="aspnet-core-implicit-store"></a><span data-ttu-id="919fb-154">Almacenamiento implícito de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="919fb-154">ASP.NET Core implicit store</span></span>

<span data-ttu-id="919fb-155">La característica de almacenamiento de paquetes en tiempo de ejecución se usa implícitamente por una aplicación de ASP.NET Core cuando la aplicación se implementa como una aplicación de [implementación dependiente del marco (FDD)](index.md#framework-dependent-deployments-fdd).</span><span class="sxs-lookup"><span data-stu-id="919fb-155">The runtime package store feature is used implicitly by an ASP.NET Core app when the app is deployed as a [framework-dependent deployment (FDD)](index.md#framework-dependent-deployments-fdd) app.</span></span> <span data-ttu-id="919fb-156">Los destinos en [`Microsoft.NET.Sdk.Web`](https://github.com/aspnet/websdk) incluyen manifiestos que hacen referencia al almacenamiento de paquetes implícito en el sistema de destino.</span><span class="sxs-lookup"><span data-stu-id="919fb-156">The targets in [`Microsoft.NET.Sdk.Web`](https://github.com/aspnet/websdk) include manifests referencing the implicit package store on the target system.</span></span> <span data-ttu-id="919fb-157">Además, cualquier aplicación de FDD que depende del paquete `Microsoft.AspNetCore.All` tiene como resultado una aplicación publicada que contiene solo la aplicación y sus activos y no los paquetes que se muestran en el metapaquete `Microsoft.AspNetCore.All`.</span><span class="sxs-lookup"><span data-stu-id="919fb-157">Additionally, any FDD app that depends on the `Microsoft.AspNetCore.All` package results in a published app that contains only the app and its assets and not the packages listed in the `Microsoft.AspNetCore.All` metapackage.</span></span> <span data-ttu-id="919fb-158">Se presupone que esos paquetes están presentes en el sistema de destino.</span><span class="sxs-lookup"><span data-stu-id="919fb-158">It's assumed that those packages are present on the target system.</span></span>

<span data-ttu-id="919fb-159">El almacenamiento de paquetes en tiempo de ejecución está instalado en el host cuando el SDK de .NET Core está instalado.</span><span class="sxs-lookup"><span data-stu-id="919fb-159">The runtime package store is installed on the host when the .NET Core SDK is installed.</span></span> <span data-ttu-id="919fb-160">Otros instaladores pueden proporcionar el almacenamiento de paquetes en tiempo de ejecución, incluidas las instalaciones Zip/tarball del SDK de .NET Core, `apt-get`, Red Hat Yum, la agrupación de hospedaje de Windows Server para .NET Core y las instalaciones manuales de almacenamiento de paquetes en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="919fb-160">Other installers may provide the runtime package store, including Zip/tarball installations of the .NET Core SDK, `apt-get`, Red Hat Yum, the .NET Core Windows Server Hosting bundle, and manual runtime package store installations.</span></span>

<span data-ttu-id="919fb-161">Al implementar una aplicación de [implementación dependiente del marco (FDD)](index.md#framework-dependent-deployments-fdd), asegúrese de que el entorno de destino tiene el SDK de .NET Core instalado.</span><span class="sxs-lookup"><span data-stu-id="919fb-161">When deploying a [framework-dependent deployment (FDD)](index.md#framework-dependent-deployments-fdd) app, make sure that the target environment has the .NET Core SDK installed.</span></span> <span data-ttu-id="919fb-162">Si la aplicación se implementa en un entorno que no incluye ASP.NET Core, puede rechazar el almacenamiento implícito especificando **\<PublishWithAspNetCoreTargetManifest>** en `false` en el archivo de proyecto como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="919fb-162">If the app is deployed to an environment that doesn't include ASP.NET Core, you can opt out of the implicit store by specifying  **\<PublishWithAspNetCoreTargetManifest>** set to `false` in the project file as in the following example:</span></span>

```xml
<PropertyGroup>
  <PublishWithAspNetCoreTargetManifest>false</PublishWithAspNetCoreTargetManifest>
</PropertyGroup>
```

> [!NOTE] 
> <span data-ttu-id="919fb-163">Para las aplicaciones de [implementación independiente (SCD)](index.md#self-contained-deployments-scd), se presupone que el sistema de destino no contiene necesariamente los paquetes de manifiesto necesarios.</span><span class="sxs-lookup"><span data-stu-id="919fb-163">For [self-contained deployment (SCD)](index.md#self-contained-deployments-scd) apps, it's assumed that the target system doesn't necessarily contain the required manifest packages.</span></span> <span data-ttu-id="919fb-164">Por lo tanto, **\<PublishWithAspNetCoreTargetManifest>** no puede establecerse en `true` para una aplicación de SCD.</span><span class="sxs-lookup"><span data-stu-id="919fb-164">Therefore, **\<PublishWithAspNetCoreTargetManifest>** cannot be set to `true` for an SCD app.</span></span>

<span data-ttu-id="919fb-165">Si implementa una aplicación con una dependencia de manifiesto que está presente en la implementación (el ensamblado está presente en la carpeta *bin*), el almacenamiento de paquetes en tiempo de ejecución *no se usa* en el host de ese ensamblado.</span><span class="sxs-lookup"><span data-stu-id="919fb-165">If you deploy an application with a manifest dependency that's present in the deployment (the assembly is present in the *bin* folder), the runtime package store *isn't used* on the host for that assembly.</span></span> <span data-ttu-id="919fb-166">El ensamblado de la carpeta *bin* se usa independientemente de su presencia en el almacenamiento de paquetes en tiempo de ejecución en el host.</span><span class="sxs-lookup"><span data-stu-id="919fb-166">The *bin* folder assembly is used regardless of its presence in the runtime package store on the host.</span></span>

<span data-ttu-id="919fb-167">La versión de la dependencia indicada en el manifiesto debe coincidir con la versión de la dependencia en el almacenamiento de paquetes en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="919fb-167">The version of the dependency indicated in the manifest must match the version of the dependency in the runtime package store.</span></span> <span data-ttu-id="919fb-168">Si no coinciden las versiones entre la dependencia del manifiesto de destino y la versión que existe en el almacenamiento de paquetes en tiempo de ejecución, y la aplicación no incluye la versión necesaria del paquete en su implementación, se produce un error en el inicio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="919fb-168">If you have a version mismatch between the dependency in the target manifest and the version that exists in the runtime package store and the app doesn't include the required version of the package in its deployment, the app fails to start.</span></span> <span data-ttu-id="919fb-169">La excepción incluye el nombre del manifiesto de destino que se ha llamado para el ensamblado del almacenamiento de paquetes en tiempo de ejecución, que le ayuda a solucionar los errores de coincidencia.</span><span class="sxs-lookup"><span data-stu-id="919fb-169">The exception includes the name of the target manifest that called for the runtime package store assembly, which helps you troubleshoot the mismatch.</span></span>

<span data-ttu-id="919fb-170">Cuando la implementación se *reduce* en su publicación, solo las versiones específicas de los paquetes de manifiesto que indique se retienen del resultado publicado.</span><span class="sxs-lookup"><span data-stu-id="919fb-170">When the deployment is *trimmed* on publish, only the specific versions of the manifest packages you indicate are withheld from the published output.</span></span> <span data-ttu-id="919fb-171">Los paquetes de las versiones indicadas deben estar presentes en el host para que se inicie la aplicación.</span><span class="sxs-lookup"><span data-stu-id="919fb-171">The packages at the versions indicated must be present on the host for the app to start.</span></span>

## <a name="see-also"></a><span data-ttu-id="919fb-172">Vea también</span><span class="sxs-lookup"><span data-stu-id="919fb-172">See also</span></span>
 [<span data-ttu-id="919fb-173">dotnet-publish</span><span class="sxs-lookup"><span data-stu-id="919fb-173">dotnet-publish</span></span>](../tools/dotnet-publish.md)  
 [<span data-ttu-id="919fb-174">dotnet-store</span><span class="sxs-lookup"><span data-stu-id="919fb-174">dotnet-store</span></span>](../tools/dotnet-store.md)  
