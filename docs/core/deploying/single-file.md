---
title: Aplicación de archivo único
description: Obtenga información sobre qué es una aplicación de archivo único y por qué debería considerar el uso de este modelo de implementación de aplicaciones.
author: lakshanf
ms.author: lakshanf
ms.date: 12/17/2020
ms.openlocfilehash: fb768fa6fe390fbe8390e441f4eb71c3172ad395
ms.sourcegitcommit: f2ab02d9a780819ca2e5310bbcf5cfe5b7993041
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2021
ms.locfileid: "99505431"
---
# <a name="single-file-deployment-and-executable"></a><span data-ttu-id="619b1-103">Implementación de archivo único y ejecutable</span><span class="sxs-lookup"><span data-stu-id="619b1-103">Single file deployment and executable</span></span>

<span data-ttu-id="619b1-104">La agrupación de todos los archivos dependientes de la aplicación en un único binario proporciona a un desarrollador de aplicaciones la opción atractiva de implementar y distribuir la aplicación como un único archivo.</span><span class="sxs-lookup"><span data-stu-id="619b1-104">Bundling all application-dependent files into a single binary provides an application developer with the attractive option to deploy and distribute the application as a single file.</span></span> <span data-ttu-id="619b1-105">Este modelo de implementación está disponible desde .NET Core 3.0 y se ha mejorado en .NET 5.0.</span><span class="sxs-lookup"><span data-stu-id="619b1-105">This deployment model has been available since .NET Core 3.0 and has been enhanced in .NET 5.0.</span></span> <span data-ttu-id="619b1-106">Anteriormente en .NET Core 3.0, cuando un usuario ejecuta la aplicación de archivo único, el host de .NET Core primero extrae todos los archivos en un directorio temporal antes de ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="619b1-106">Previously in .NET Core 3.0, when a user runs your single-file app, .NET Core host first extracts all files to a temporary directory before running the application.</span></span> <span data-ttu-id="619b1-107">En .NET 5.0 se mejora esta experiencia al ejecutar directamente el código sin necesidad de extraer los archivos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="619b1-107">.NET 5.0 improves this experience by directly running the code without the need to extract the files from the app.</span></span>

<span data-ttu-id="619b1-108">La implementación de archivo único está disponible para el [modelo de implementación dependiente del marco](index.md#publish-framework-dependent) y [aplicaciones independientes](index.md#publish-self-contained).</span><span class="sxs-lookup"><span data-stu-id="619b1-108">Single File deployment is available for both the [framework-dependent deployment model](index.md#publish-framework-dependent) and [self-contained applications](index.md#publish-self-contained).</span></span> <span data-ttu-id="619b1-109">El tamaño del archivo único de una aplicación independiente será grande, ya que incluirá el runtime y las bibliotecas de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="619b1-109">The size of the single file in a self-contained application will be large since it will include the runtime and the framework libraries.</span></span> <span data-ttu-id="619b1-110">La opción de implementación de archivo único se puede combinar con las opciones de publicación [ReadyToRun](ready-to-run.md) y [Trim (una característica experimental de .NET 5.0)](trim-self-contained.md).</span><span class="sxs-lookup"><span data-stu-id="619b1-110">The single file deployment option can be combined with [ReadyToRun](ready-to-run.md) and [Trim (an experimental feature in .NET 5.0)](trim-self-contained.md) publish options.</span></span>

## <a name="api-incompatibility"></a><span data-ttu-id="619b1-111">Incompatibilidad de API</span><span class="sxs-lookup"><span data-stu-id="619b1-111">API incompatibility</span></span>

<span data-ttu-id="619b1-112">Algunas API no son compatibles con la implementación de un solo archivo y las aplicaciones pueden requerir modificaciones si usan estas API.</span><span class="sxs-lookup"><span data-stu-id="619b1-112">Some APIs are not compatible with single-file deployment and applications may require modification if they use these APIs.</span></span> <span data-ttu-id="619b1-113">Si usa un paquete o un marco de terceros, es posible que también pueda usar una de estas API y necesite modificarla.</span><span class="sxs-lookup"><span data-stu-id="619b1-113">If you use a third-party framework or package, it's possible that they may also use one of these APIs and need modification.</span></span> <span data-ttu-id="619b1-114">La causa más común de los problemas es la dependencia de las rutas de acceso de archivo de los archivos o DLL que se incluyen con la aplicación.</span><span class="sxs-lookup"><span data-stu-id="619b1-114">The most common cause of problems is dependence on file paths for files or DLLs shipped with the application.</span></span>

<span data-ttu-id="619b1-115">En la tabla siguiente se incluyen los detalles pertinentes de la API de la biblioteca del entorno de ejecución para el uso de un solo archivo.</span><span class="sxs-lookup"><span data-stu-id="619b1-115">The table below has the relevant runtime library API details for single-file use.</span></span>

| <span data-ttu-id="619b1-116">API</span><span class="sxs-lookup"><span data-stu-id="619b1-116">API</span></span>                            | <span data-ttu-id="619b1-117">Nota:</span><span class="sxs-lookup"><span data-stu-id="619b1-117">Note</span></span>                                                                   |
|--------------------------------|------------------------------------------------------------------------|
| `Assembly.Location`            | <span data-ttu-id="619b1-118">Devuelve una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="619b1-118">Returns an empty string.</span></span>                                               |
| `Module.FullyQualifiedName`    | <span data-ttu-id="619b1-119">Devuelve una cadena con el valor de `<Unknown>` o produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="619b1-119">Returns a string with the value of `<Unknown>` or throws an exception.</span></span> |
| `Module.Name`                  | <span data-ttu-id="619b1-120">Devuelve una cadena con el valor de `<Unknown>`.</span><span class="sxs-lookup"><span data-stu-id="619b1-120">Returns a string with the value of `<Unknown>`.</span></span>                        |
| `Assembly.GetFile`             | <span data-ttu-id="619b1-121">Produce <xref:System.IO.IOException>.</span><span class="sxs-lookup"><span data-stu-id="619b1-121">Throws <xref:System.IO.IOException>.</span></span>                                   |
| `Assembly.GetFiles`            | <span data-ttu-id="619b1-122">Produce <xref:System.IO.IOException>.</span><span class="sxs-lookup"><span data-stu-id="619b1-122">Throws <xref:System.IO.IOException>.</span></span>                                   |
| `Assembly.CodeBase`            | <span data-ttu-id="619b1-123">Produce <xref:System.PlatformNotSupportedException>.</span><span class="sxs-lookup"><span data-stu-id="619b1-123">Throws <xref:System.PlatformNotSupportedException>.</span></span>                    |
| `Assembly.EscapedCodeBase`     | <span data-ttu-id="619b1-124">Produce <xref:System.PlatformNotSupportedException>.</span><span class="sxs-lookup"><span data-stu-id="619b1-124">Throws <xref:System.PlatformNotSupportedException>.</span></span>                    |
| `AssemblyName.CodeBase`        | <span data-ttu-id="619b1-125">Devuelve `null`.</span><span class="sxs-lookup"><span data-stu-id="619b1-125">Returns `null`.</span></span>                                                        |
| `AssemblyName.EscapedCodeBase` | <span data-ttu-id="619b1-126">Devuelve `null`.</span><span class="sxs-lookup"><span data-stu-id="619b1-126">Returns `null`.</span></span>                                                        |

<span data-ttu-id="619b1-127">Tenemos algunas recomendaciones para solucionar escenarios comunes:</span><span class="sxs-lookup"><span data-stu-id="619b1-127">We have some recommendations for fixing common scenarios:</span></span>

* <span data-ttu-id="619b1-128">Para obtener acceso a los archivos que se encuentran junto al archivo ejecutable, use <xref:System.AppContext.BaseDirectory?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="619b1-128">To access files next to the executable, use <xref:System.AppContext.BaseDirectory?displayProperty=nameWithType>.</span></span>

* <span data-ttu-id="619b1-129">Para buscar el nombre del archivo ejecutable, use el primer elemento de <xref:System.Environment.GetCommandLineArgs?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="619b1-129">To find the file name of the executable, use the first element of <xref:System.Environment.GetCommandLineArgs?displayProperty=nameWithType>.</span></span>

* <span data-ttu-id="619b1-130">Para evitar el envío completo de archivos sueltos, considere la posibilidad de usar [recursos incrustados](../../framework/resources/creating-resource-files-for-desktop-apps.md).</span><span class="sxs-lookup"><span data-stu-id="619b1-130">To avoid shipping loose files entirely, consider using [embedded resources](../../framework/resources/creating-resource-files-for-desktop-apps.md).</span></span>

## <a name="attaching-a-debugger"></a><span data-ttu-id="619b1-131">Asociación de un depurador</span><span class="sxs-lookup"><span data-stu-id="619b1-131">Attaching a debugger</span></span>

<span data-ttu-id="619b1-132">En Linux, el único depurador que puede asociarse a los procesos de un solo archivo independientes o depurar los volcados de memoria es [SOS con LLDB](../diagnostics/dotnet-sos.md).</span><span class="sxs-lookup"><span data-stu-id="619b1-132">On Linux, the only debugger which can attach to self-contained single-file processes or debug crash dumps is [SOS with LLDB](../diagnostics/dotnet-sos.md).</span></span>

<span data-ttu-id="619b1-133">En Windows y Mac, Visual Studio y VS Code se pueden usar para depurar volcados de memoria.</span><span class="sxs-lookup"><span data-stu-id="619b1-133">On Windows and Mac, Visual Studio and VS Code can be used to debug crash dumps.</span></span> <span data-ttu-id="619b1-134">La asociación a un archivo ejecutable de un solo archivo independiente en ejecución requiere un archivo adicional: _mscordbi.{dll,so}_ .</span><span class="sxs-lookup"><span data-stu-id="619b1-134">Attaching to a running self-contained single-file executable requires an extra file: _mscordbi.{dll,so}_.</span></span>

<span data-ttu-id="619b1-135">Sin este archivo, Visual Studio puede producir el error "No se puede asociar al proceso.</span><span class="sxs-lookup"><span data-stu-id="619b1-135">Without this file Visual Studio may produce the error "Unable to attach to the process.</span></span> <span data-ttu-id="619b1-136">No se ha instalado un componente de depuración"</span><span class="sxs-lookup"><span data-stu-id="619b1-136">A debug component is not installed."</span></span> <span data-ttu-id="619b1-137">y VS Code puede generar el error "No se pudo asociar al proceso: Error desconocido: 0x80131c3c".</span><span class="sxs-lookup"><span data-stu-id="619b1-137">and VS Code may produce the error "Failed to attach to process: Unknown Error: 0x80131c3c."</span></span>

<span data-ttu-id="619b1-138">Para corregir estos errores, _mscordbi_ debe copiarse junto al archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="619b1-138">To fix these errors, _mscordbi_ needs to be copied next to the executable.</span></span> <span data-ttu-id="619b1-139">A _mscordbi_ se le aplica `publish` de forma predeterminada en el subdirectorio con el identificador del entorno de ejecución de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="619b1-139">_mscordbi_ is `publish`ed by default in the subdirectory with the application's runtime ID.</span></span> <span data-ttu-id="619b1-140">Por lo tanto, por ejemplo, si se publica un archivo ejecutable de un solo archivo independiente mediante la CLI de `dotnet` para Windows que usa los parámetros `-r win-x64`, el ejecutable se colocará en _bin/Debug/net5.0/win-x64/publish_.</span><span class="sxs-lookup"><span data-stu-id="619b1-140">So, for example, if one were to publish a self-contained single-file executable using the `dotnet` CLI for Windows using the parameters `-r win-x64`, the executable would be placed in _bin/Debug/net5.0/win-x64/publish_.</span></span> <span data-ttu-id="619b1-141">En _bin/Debug/net5.0/win-x64_ hay una copia de _mscordbi.dll_.</span><span class="sxs-lookup"><span data-stu-id="619b1-141">A copy of _mscordbi.dll_ would be present in _bin/Debug/net5.0/win-x64_.</span></span>

## <a name="other-considerations"></a><span data-ttu-id="619b1-142">Otras consideraciones</span><span class="sxs-lookup"><span data-stu-id="619b1-142">Other considerations</span></span>

<span data-ttu-id="619b1-143">De forma predeterminada, las aplicaciones de archivo único no agrupan bibliotecas nativas.</span><span class="sxs-lookup"><span data-stu-id="619b1-143">Single-file doesn't bundle native libraries by default.</span></span> <span data-ttu-id="619b1-144">En Linux, se realiza el enlace previo del runtime a la agrupación y solo se implementan bibliotecas nativas de la aplicación en el mismo directorio que la aplicación de archivo único.</span><span class="sxs-lookup"><span data-stu-id="619b1-144">On Linux, we prelink the runtime into the bundle and only application native libraries are deployed to the same directory as the single-file app.</span></span> <span data-ttu-id="619b1-145">En Windows, solo se realiza el enlace previo del código de hospedaje, y el runtime y las bibliotecas nativas de la aplicación se implementan en el mismo directorio que la aplicación de archivo único.</span><span class="sxs-lookup"><span data-stu-id="619b1-145">On Windows, we prelink only the hosting code and both the runtime and application native libraries are deployed to the same directory as the single-file app.</span></span> <span data-ttu-id="619b1-146">Esto permite garantizar una buena experiencia de depuración, que requiere que los archivos nativos se excluyan del archivo único.</span><span class="sxs-lookup"><span data-stu-id="619b1-146">This is to ensure a good debugging experience, which requires native files to be excluded from the single file.</span></span> <span data-ttu-id="619b1-147">Hay una opción para establecer una marca, `IncludeNativeLibrariesForSelfExtract`, a fin de incluir bibliotecas nativas en el paquete de archivo único, pero estos archivos se extraerán en un directorio temporal en el equipo cliente cuando se ejecute la aplicación de archivo único.</span><span class="sxs-lookup"><span data-stu-id="619b1-147">There is an option to set a flag, `IncludeNativeLibrariesForSelfExtract`, to include native libraries in the single file bundle, but these files will be extracted to a temporary directory in the client machine when the single file application is run.</span></span>

<span data-ttu-id="619b1-148">Si se especifica `IncludeAllContentForSelfExtract`, se extraerán todos los archivos antes de ejecutar el archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="619b1-148">Specifying `IncludeAllContentForSelfExtract` will extract all files before running the executable.</span></span> <span data-ttu-id="619b1-149">Esto permite conservar el comportamiento original de implementación de un solo archivo de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="619b1-149">This preserves the original .NET Core single-file deployment behavior.</span></span>

<span data-ttu-id="619b1-150">La aplicación de un solo archivo tendrá todos los archivos PDB relacionados junto con él y no se agrupará de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="619b1-150">Single-file application will have all related PDB files alongside it and will not be bundled by default.</span></span> <span data-ttu-id="619b1-151">Si desea incluir PDB dentro del ensamblado para los proyectos que se compilan, establezca `DebugType` en `embedded` tal y como se describe [a continuación](#include-pdb-files-inside-the-bundle) en detalle.</span><span class="sxs-lookup"><span data-stu-id="619b1-151">If you want to include PDBs inside the assembly for projects you build, set the `DebugType` to `embedded` as described [below](#include-pdb-files-inside-the-bundle) in detail.</span></span>

<span data-ttu-id="619b1-152">Los componentes administrados de C++ no son adecuados para la implementación de archivo único y se recomienda escribir aplicaciones en C# u otro lenguaje de C++ no administrado para que sean compatibles con un archivo único.</span><span class="sxs-lookup"><span data-stu-id="619b1-152">Managed C++ components aren't well suited for single-file deployment and we recommend that you write applications in C# or another non-managed C++ language to be single-file compatible.</span></span>

## <a name="exclude-files-from-being-embedded"></a><span data-ttu-id="619b1-153">Exclusión de archivos de la inserción</span><span class="sxs-lookup"><span data-stu-id="619b1-153">Exclude files from being embedded</span></span>

<span data-ttu-id="619b1-154">Algunos archivos se pueden excluir de forma explícita de su inserción en el único archivo si se establecen los metadatos siguientes:</span><span class="sxs-lookup"><span data-stu-id="619b1-154">Certain files can be explicitly excluded from being embedded in the single-file by setting following metadata:</span></span>

```xml
<ExcludeFromSingleFile>true</ExcludeFromSingleFile>
```

<span data-ttu-id="619b1-155">Por ejemplo, para colocar algunos archivos en el directorio de publicación pero no empaquetarlos en el archivo único:</span><span class="sxs-lookup"><span data-stu-id="619b1-155">For example, to place some files in the publish directory but not bundle them in the single-file:</span></span>

```xml
<ItemGroup>
  <Content Update="Plugin.dll">
    <CopyToPublishDirectory>PreserveNewest</CopyToPublishDirectory>
    <ExcludeFromSingleFile>true</ExcludeFromSingleFile>
  </Content>
</ItemGroup>
```

## <a name="include-pdb-files-inside-the-bundle"></a><span data-ttu-id="619b1-156">Inclusión de archivos PDB dentro de la agrupación</span><span class="sxs-lookup"><span data-stu-id="619b1-156">Include PDB files inside the bundle</span></span>

<span data-ttu-id="619b1-157">El archivo PDB de un ensamblado se puede insertar en el propio ensamblado (`.dll`) mediante la configuración siguiente.</span><span class="sxs-lookup"><span data-stu-id="619b1-157">The PDB file for an assembly can be embedded into the assembly itself (the `.dll`) using the setting below.</span></span> <span data-ttu-id="619b1-158">Puesto que los símbolos forman parte del ensamblado, también formarán parte de la aplicación de un solo archivo:</span><span class="sxs-lookup"><span data-stu-id="619b1-158">Since the symbols are part of the assembly, they will be part of the single-file application as well:</span></span>

```xml
<DebugType>embedded</DebugType>
```

<span data-ttu-id="619b1-159">Por ejemplo, agregue la siguiente propiedad al archivo de proyecto de un ensamblado para insertar el archivo PDB en ese ensamblado:</span><span class="sxs-lookup"><span data-stu-id="619b1-159">For example, add the following property to the project file of an assembly to embed the PDB file to that assembly:</span></span>

```xml
<PropertyGroup>
  <DebugType>embedded</DebugType>
</PropertyGroup>
```

## <a name="publish-a-single-file-app---sample-project-file"></a><span data-ttu-id="619b1-160">Publicación de una aplicación de archivo único: archivo de proyecto de ejemplo</span><span class="sxs-lookup"><span data-stu-id="619b1-160">Publish a single file app - sample project file</span></span>

<span data-ttu-id="619b1-161">Este es un archivo de proyecto de ejemplo que especifica la publicación de un archivo único:</span><span class="sxs-lookup"><span data-stu-id="619b1-161">Here's a sample project file that specifies single-file publishing:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>net5.0</TargetFramework>
    <PublishSingleFile>true</PublishSingleFile>
    <SelfContained>true</SelfContained>
    <RuntimeIdentifier>win-x64</RuntimeIdentifier>
    <PublishTrimmed>true</PublishTrimmed>
    <PublishReadyToRun>true</PublishReadyToRun>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="619b1-162">Estas propiedades tienen las siguientes funciones:</span><span class="sxs-lookup"><span data-stu-id="619b1-162">These properties have the following functions:</span></span>

* <span data-ttu-id="619b1-163">`PublishSingleFile`: habilita la publicación de un solo archivo.</span><span class="sxs-lookup"><span data-stu-id="619b1-163">`PublishSingleFile` - Enables single-file publishing.</span></span>
* <span data-ttu-id="619b1-164">`SelfContained`: determina si la aplicación será independiente o dependiente de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="619b1-164">`SelfContained` - Determines whether the app will be self-contained or framework-dependent.</span></span>
* <span data-ttu-id="619b1-165">`RuntimeIdentifier`: especifica el [sistema operativo y el tipo de CPU](../rid-catalog.md) que tiene como destino.</span><span class="sxs-lookup"><span data-stu-id="619b1-165">`RuntimeIdentifier` - Specifies the [OS and CPU type](../rid-catalog.md) you are targeting.</span></span>
* <span data-ttu-id="619b1-166">`PublishTrimmed`: habilita el uso del [recorte de ensamblados](trim-self-contained.md), que solo se admite para aplicaciones independientes.</span><span class="sxs-lookup"><span data-stu-id="619b1-166">`PublishTrimmed` - Enables use of [assembly trimming](trim-self-contained.md), which is only supported for self-contained apps.</span></span>
* <span data-ttu-id="619b1-167">`PublishReadyToRun`: habilita la [compilación Ahead Of Time (AOT)](ready-to-run.md).</span><span class="sxs-lookup"><span data-stu-id="619b1-167">`PublishReadyToRun` - Enables [ahead-of-time (AOT) compilation](ready-to-run.md).</span></span>

<span data-ttu-id="619b1-168">**Notas:**</span><span class="sxs-lookup"><span data-stu-id="619b1-168">**Notes:**</span></span>

* <span data-ttu-id="619b1-169">Las aplicaciones son específicas del sistema operativo y de la arquitectura.</span><span class="sxs-lookup"><span data-stu-id="619b1-169">Apps are OS and architecture-specific.</span></span> <span data-ttu-id="619b1-170">Debe publicar para cada configuración, como Linux x64, Linux ARM64, Windows x64, etc.</span><span class="sxs-lookup"><span data-stu-id="619b1-170">You need to publish for each configuration, such as Linux x64, Linux ARM64, Windows x64, and so forth.</span></span>
* <span data-ttu-id="619b1-171">Los archivos de configuración, como *\*.runtimeconfig.json*, se incluyen en el archivo único.</span><span class="sxs-lookup"><span data-stu-id="619b1-171">Configuration files, such as *\*.runtimeconfig.json*, are included in the single file.</span></span> <span data-ttu-id="619b1-172">Si se necesita un archivo de configuración adicional, puede colocarlo junto al archivo único.</span><span class="sxs-lookup"><span data-stu-id="619b1-172">If an additional configuration file is needed, you can place it beside the single file.</span></span>

## <a name="publish-a-single-file-app---cli"></a><span data-ttu-id="619b1-173">Publicación de una aplicación de archivo único: CLI</span><span class="sxs-lookup"><span data-stu-id="619b1-173">Publish a single file app - CLI</span></span>

<span data-ttu-id="619b1-174">Publique una aplicación de archivo único mediante el comando [dotnet publish](../tools/dotnet-publish.md).</span><span class="sxs-lookup"><span data-stu-id="619b1-174">Publish a single file application using the [dotnet publish](../tools/dotnet-publish.md) command.</span></span> <span data-ttu-id="619b1-175">Al publicar la aplicación, establezca las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="619b1-175">When you publish your app, set the following properties:</span></span>

- <span data-ttu-id="619b1-176">Publicación para un runtime concreto: `-r win-x64`</span><span class="sxs-lookup"><span data-stu-id="619b1-176">Publish for a specific runtime: `-r win-x64`</span></span>
- <span data-ttu-id="619b1-177">Publicación como archivo único: `-p:PublishSingleFile=true`</span><span class="sxs-lookup"><span data-stu-id="619b1-177">Publish as a single-file: `-p:PublishSingleFile=true`</span></span>

<span data-ttu-id="619b1-178">En el ejemplo siguiente se publica una aplicación para Windows como aplicación independiente de archivo único.</span><span class="sxs-lookup"><span data-stu-id="619b1-178">The following example publishes an app for Windows as a self-contained single file application.</span></span>

```dotnetcli
dotnet publish -r win-x64 -p:PublishSingleFile=true --self-contained true
```

<span data-ttu-id="619b1-179">En el ejemplo siguiente se publica una aplicación para Linux como una aplicación de archivo único dependiente del marco.</span><span class="sxs-lookup"><span data-stu-id="619b1-179">The following example publishes an app for Linux as a framework dependent single file application.</span></span>

```dotnetcli
dotnet publish -r linux-x64 -p:PublishSingleFile=true --self-contained false
```

<span data-ttu-id="619b1-180">Para obtener más información, vea [Publicación de aplicaciones .NET Core con la CLI de .NET Core](deploy-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="619b1-180">For more information, see [Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>

## <a name="publish-a-single-file-app---visual-studio"></a><span data-ttu-id="619b1-181">Publicación de una aplicación de archivo único: Visual Studio</span><span class="sxs-lookup"><span data-stu-id="619b1-181">Publish a single file app - Visual Studio</span></span>

<span data-ttu-id="619b1-182">Visual Studio crea perfiles de publicación reutilizables que controlan cómo se publica la aplicación.</span><span class="sxs-lookup"><span data-stu-id="619b1-182">Visual Studio creates reusable publishing profiles that control how your application is published.</span></span>

01. <span data-ttu-id="619b1-183">En el panel **Explorador de soluciones**, haga clic con el botón derecho en el proyecto que quiera publicar.</span><span class="sxs-lookup"><span data-stu-id="619b1-183">On the **Solution Explorer** pane, right-click on the project you want to publish.</span></span> <span data-ttu-id="619b1-184">Seleccione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="619b1-184">Select **Publish**.</span></span>

    :::image type="content" source="media/single-file/visual-studio-solution-explorer.png" alt-text="Explorador de soluciones con un menú contextual en el que se resalta la opción Publicar.":::

    <span data-ttu-id="619b1-186">Si todavía no tiene un perfil de publicación, siga las instrucciones para crear uno y elija el tipo de destino **Carpeta**.</span><span class="sxs-lookup"><span data-stu-id="619b1-186">If you don't already have a publishing profile, follow the instructions to create one and choose the **Folder** target-type.</span></span>

01. <span data-ttu-id="619b1-187">Elija **Editar**.</span><span class="sxs-lookup"><span data-stu-id="619b1-187">Choose **Edit**.</span></span>

    :::image type="content" source="media/single-file/visual-studio-publish-edit-settings.png" alt-text="Perfil de publicación de Visual Studio con el botón Editar.":::

01. <span data-ttu-id="619b1-189">En el cuadro de diálogo **Configuración de perfil**, establezca las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="619b1-189">In the **Profile settings** dialog, set the following options:</span></span>

    - <span data-ttu-id="619b1-190">Establezca el **modo de implementación** en **independiente** o **dependiente del marco**.</span><span class="sxs-lookup"><span data-stu-id="619b1-190">Set **Deployment mode** to **Self-contained** or **Framework-dependent**.</span></span>
    - <span data-ttu-id="619b1-191">Establezca **Tiempo de ejecución de destino** en la plataforma en la que quiera publicar.</span><span class="sxs-lookup"><span data-stu-id="619b1-191">Set **Target runtime** to the platform you want to publish to.</span></span> <span data-ttu-id="619b1-192">(Debe ser distinto de **portátil**).</span><span class="sxs-lookup"><span data-stu-id="619b1-192">(Must be something other than **Portable**.)</span></span>
    - <span data-ttu-id="619b1-193">Seleccione **Producir un único archivo**.</span><span class="sxs-lookup"><span data-stu-id="619b1-193">Select **Produce single file**.</span></span>

    <span data-ttu-id="619b1-194">Elija **Guardar** para guardar la configuración y volver al cuadro de diálogo **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="619b1-194">Choose **Save** to save the settings and return to the **Publish** dialog.</span></span>

    :::image type="content" source="media/single-file/visual-studio-publish-single-file-properties.png" alt-text="Cuadro de diálogo Configuración de perfil con las opciones Modo de implementación, Tiempo de ejecución de destino y Archivo único resaltadas.":::

01. <span data-ttu-id="619b1-196">Elija **Publicar** para publicar la aplicación como un archivo único.</span><span class="sxs-lookup"><span data-stu-id="619b1-196">Choose **Publish** to publish your app as a single file.</span></span>

<span data-ttu-id="619b1-197">Para obtener más información, vea [Publicación de aplicaciones .NET Core con Visual Studio](deploy-with-vs.md).</span><span class="sxs-lookup"><span data-stu-id="619b1-197">For more information, see [Publish .NET Core apps with Visual Studio](deploy-with-vs.md).</span></span>

## <a name="publish-a-single-file-app---visual-studio-for-mac"></a><span data-ttu-id="619b1-198">Publicación de una aplicación de archivo único: Visual Studio para Mac</span><span class="sxs-lookup"><span data-stu-id="619b1-198">Publish a single file app - Visual Studio for Mac</span></span>

<span data-ttu-id="619b1-199">Visual Studio para Mac no proporciona opciones para publicar la aplicación como un archivo único.</span><span class="sxs-lookup"><span data-stu-id="619b1-199">Visual Studio for Mac doesn't provide options to publish your app as a single file.</span></span> <span data-ttu-id="619b1-200">Tendrá que publicar de forma manual mediante las instrucciones de la sección [Publicación de una aplicación de archivo único: CLI](#publish-a-single-file-app---cli).</span><span class="sxs-lookup"><span data-stu-id="619b1-200">You'll need to publish manually by following the instructions from the [Publish a single file app - CLI](#publish-a-single-file-app---cli) section.</span></span> <span data-ttu-id="619b1-201">Para obtener más información, vea [Publicación de aplicaciones .NET Core con la CLI de .NET Core](deploy-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="619b1-201">For more information, see [Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="619b1-202">Vea también</span><span class="sxs-lookup"><span data-stu-id="619b1-202">See also</span></span>

- <span data-ttu-id="619b1-203">[Implementación de aplicaciones .NET Core](index.md).</span><span class="sxs-lookup"><span data-stu-id="619b1-203">[.NET Core application deployment](index.md).</span></span>
- <span data-ttu-id="619b1-204">[Publicación de aplicaciones .NET Core con la CLI de .NET Core](deploy-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="619b1-204">[Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>
- <span data-ttu-id="619b1-205">[Publicación de aplicaciones .NET Core con Visual Studio](deploy-with-vs.md).</span><span class="sxs-lookup"><span data-stu-id="619b1-205">[Publish .NET Core apps with Visual Studio](deploy-with-vs.md).</span></span>
- <span data-ttu-id="619b1-206">[Comando `dotnet publish`](../tools/dotnet-publish.md).</span><span class="sxs-lookup"><span data-stu-id="619b1-206">[`dotnet publish` command](../tools/dotnet-publish.md).</span></span>
