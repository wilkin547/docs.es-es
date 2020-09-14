---
title: Aplicación de archivo único
description: Obtenga información sobre qué es una aplicación de archivo único y por qué debería considerar el uso de este modelo de implementación de aplicaciones.
author: lakshanf
ms.author: lakshanf
ms.date: 08/28/2020
ms.openlocfilehash: 795ea98a9fd9d672b199eb2d9b24151340ef8246
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89495758"
---
# <a name="single-file-deployment-and-executable"></a><span data-ttu-id="4fcad-103">Implementación de archivo único y ejecutable</span><span class="sxs-lookup"><span data-stu-id="4fcad-103">Single file deployment and executable</span></span>

<span data-ttu-id="4fcad-104">La agrupación de todos los archivos dependientes de la aplicación en un único binario proporciona a un desarrollador de aplicaciones la opción atractiva de implementar y distribuir la aplicación como un único archivo.</span><span class="sxs-lookup"><span data-stu-id="4fcad-104">Bundling all application-dependent files into a single binary provides an application developer with the attractive option to deploy and distribute the application as a single file.</span></span> <span data-ttu-id="4fcad-105">Este modelo de implementación está disponible desde .NET Core 3.0 y se ha mejorado en .NET 5.0.</span><span class="sxs-lookup"><span data-stu-id="4fcad-105">This deployment model has been available since .NET Core 3.0 and has been enhanced in .NET 5.0.</span></span> <span data-ttu-id="4fcad-106">Anteriormente en .NET Core 3.0, cuando un usuario ejecuta la aplicación de archivo único, el host de .NET Core primero extrae todos los archivos en un directorio temporal antes de ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4fcad-106">Previously in .NET Core 3.0, when a user runs your single-file app, .NET Core host first extracts all files to a temporary directory before running the application.</span></span> <span data-ttu-id="4fcad-107">En .NET 5.0 se mejora esta experiencia al ejecutar directamente el código sin necesidad de extraer los archivos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4fcad-107">.NET 5.0 improves this experience by directly running the code without the need to extract the files from the app.</span></span>

<span data-ttu-id="4fcad-108">La implementación de archivo único está disponible para el [modelo de implementación dependiente del marco](index.md#publish-framework-dependent) y [aplicaciones independientes](index.md#publish-self-contained).</span><span class="sxs-lookup"><span data-stu-id="4fcad-108">Single File deployment is available for both the [framework-dependent deployment model](index.md#publish-framework-dependent) and [self-contained applications](index.md#publish-self-contained).</span></span> <span data-ttu-id="4fcad-109">El tamaño del archivo único de una aplicación independiente será grande, ya que incluirá el runtime y las bibliotecas de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4fcad-109">The size of the single file in a self-contained application will be large since it will include the runtime and the framework libraries.</span></span> <span data-ttu-id="4fcad-110">La opción de implementación de archivo único se puede combinar con las opciones de publicación [ReadyToRun](../tools/dotnet-publish.md) y [Trim (una característica experimental de .NET 5.0)](trim-self-contained.md).</span><span class="sxs-lookup"><span data-stu-id="4fcad-110">The single file deployment option can be combined with [ReadyToRun](../tools/dotnet-publish.md) and [Trim (an experimental feature in .NET 5.0)](trim-self-contained.md) publish options.</span></span>

<span data-ttu-id="4fcad-111">Hay algunos inconvenientes que debe tener en cuenta sobre el uso de un archivo único; en primer lugar, se utiliza la información de la ruta de acceso para localizar un archivo en relación con la ubicación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4fcad-111">There are some caveats that you need to be aware for single-file use, first of which is the use of path information to locate a file relative to the location of your application.</span></span> <span data-ttu-id="4fcad-112">La API <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType> devolverá una cadena vacía, que es el comportamiento predeterminado de los ensamblados cargados desde la memoria.</span><span class="sxs-lookup"><span data-stu-id="4fcad-112">The <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType> API will return an empty string, which is the default behavior for assemblies loaded from memory.</span></span> <span data-ttu-id="4fcad-113">El compilador generará una advertencia para esta API durante el tiempo de compilación para avisar al desarrollador del comportamiento concreto.</span><span class="sxs-lookup"><span data-stu-id="4fcad-113">The compiler will give a warning for this API during build time to alert the developer to the specific behavior.</span></span> <span data-ttu-id="4fcad-114">Si se necesita la ruta de acceso al directorio de la aplicación, la API <xref:System.AppContext.BaseDirectory?displayProperty=nameWithType> devolverá el directorio donde reside AppHost (el propio paquete de archivo único).</span><span class="sxs-lookup"><span data-stu-id="4fcad-114">If the path to the application directory is needed, the <xref:System.AppContext.BaseDirectory?displayProperty=nameWithType> API will return the directory where the AppHost (the single-file bundle itself) resides.</span></span> <span data-ttu-id="4fcad-115">Las aplicaciones administradas de C++ no son adecuadas para la implementación de archivo único y se recomienda escribir aplicaciones en C# para que sea compatibles con un archivo único.</span><span class="sxs-lookup"><span data-stu-id="4fcad-115">Managed C++ applications aren't well suited for single-file deployment and we recommend that you write applications in C# to be single-file compatible.</span></span>

<span data-ttu-id="4fcad-116">De forma predeterminada, las aplicaciones de archivo único no agrupan bibliotecas nativas.</span><span class="sxs-lookup"><span data-stu-id="4fcad-116">Single-file doesn't bundle native libraries by default.</span></span> <span data-ttu-id="4fcad-117">En Linux, se realiza el enlace previo del runtime a la agrupación y solo se implementan bibliotecas nativas de la aplicación en el mismo directorio que la aplicación de archivo único.</span><span class="sxs-lookup"><span data-stu-id="4fcad-117">On Linux, we prelink the runtime into the bundle and only application native libraries are deployed to the same directory as the single-file app.</span></span> <span data-ttu-id="4fcad-118">En Windows, solo se realiza el enlace previo del código de hospedaje, y el runtime y las bibliotecas nativas de la aplicación se implementan en el mismo directorio que la aplicación de archivo único.</span><span class="sxs-lookup"><span data-stu-id="4fcad-118">On Windows, we prelink only the hosting code and both the runtime and application native libraries are deployed to the same directory as the single-file app.</span></span> <span data-ttu-id="4fcad-119">Esto permite garantizar una buena experiencia de depuración, que requiere que los archivos nativos se excluyan del archivo único.</span><span class="sxs-lookup"><span data-stu-id="4fcad-119">This is to ensure a good debugging experience, which requires native files to be excluded from the single file.</span></span> <span data-ttu-id="4fcad-120">Hay una opción para establecer una marca, `IncludeNativeLibrariesForSelfExtract`, a fin de incluir bibliotecas nativas en el paquete de archivo único, pero estos archivos se extraerán en un directorio temporal en el equipo cliente cuando se ejecute la aplicación de archivo único.</span><span class="sxs-lookup"><span data-stu-id="4fcad-120">There is an option to set a flag, `IncludeNativeLibrariesForSelfExtract`, to include native libraries in the single file bundle, but these files will be extracted to a temporary directory in the client machine when the single file application is run.</span></span>

## <a name="exclude-files-from-being-embedded"></a><span data-ttu-id="4fcad-121">Exclusión de archivos de la inserción</span><span class="sxs-lookup"><span data-stu-id="4fcad-121">Exclude files from being embedded</span></span>

<span data-ttu-id="4fcad-122">Algunos archivos se pueden excluir de forma explícita de su inserción en el único archivo si se establecen los metadatos siguientes:</span><span class="sxs-lookup"><span data-stu-id="4fcad-122">Certain files can be explicitly excluded from being embedded in the single-file by setting following metadata:</span></span>

```xml
<ExcludeFromSingleFile>true</ExcludeFromSingleFile>
```

<span data-ttu-id="4fcad-123">Por ejemplo, para colocar algunos archivos en el directorio de publicación pero no empaquetarlos en el archivo único:</span><span class="sxs-lookup"><span data-stu-id="4fcad-123">For example, to place some files in the publish directory but not bundle them in the single-file:</span></span>

```xml
<ItemGroup>
  <Content Update="Plugin.dll">
    <CopyToPublishDirectory>PreserveNewest</CopyToPublishDirectory>
    <ExcludeFromSingleFile>true</ExcludeFromSingleFile>
  </Content>
</ItemGroup>
```

## <a name="publish-a-single-file-app---cli"></a><span data-ttu-id="4fcad-124">Publicación de una aplicación de archivo único: CLI</span><span class="sxs-lookup"><span data-stu-id="4fcad-124">Publish a single file app - CLI</span></span>

<span data-ttu-id="4fcad-125">Publique una aplicación de archivo único mediante el comando [dotnet publish](../tools/dotnet-publish.md).</span><span class="sxs-lookup"><span data-stu-id="4fcad-125">Publish a single file application using the [dotnet publish](../tools/dotnet-publish.md) command.</span></span> <span data-ttu-id="4fcad-126">Al publicar la aplicación, establezca las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="4fcad-126">When you publish your app, set the following properties:</span></span>

- <span data-ttu-id="4fcad-127">Publicación para un runtime concreto: `-r win-x64`</span><span class="sxs-lookup"><span data-stu-id="4fcad-127">Publish for a specific runtime: `-r win-x64`</span></span>
- <span data-ttu-id="4fcad-128">Publicación como archivo único: `-p:PublishSingleFile=true`</span><span class="sxs-lookup"><span data-stu-id="4fcad-128">Publish as a single-file: `-p:PublishSingleFile=true`</span></span>

<span data-ttu-id="4fcad-129">En el ejemplo siguiente se publica una aplicación para Windows como aplicación independiente de archivo único.</span><span class="sxs-lookup"><span data-stu-id="4fcad-129">The following example publishes an app for Windows as a self-contained single file application.</span></span>

```dotnetcli
dotnet publish -r win-x64 -p:PublishSingleFile=true --self-contained true
```

<span data-ttu-id="4fcad-130">En el ejemplo siguiente se publica una aplicación para Linux como una aplicación de archivo único dependiente del marco.</span><span class="sxs-lookup"><span data-stu-id="4fcad-130">The following example publishes an app for Linux as a framework dependent single file application.</span></span>

```dotnetcli
dotnet publish -r linux-x64 -p:PublishSingleFile=true --self-contained false
```

<span data-ttu-id="4fcad-131">Para obtener más información, vea [Publicación de aplicaciones .NET Core con la CLI de .NET Core](deploy-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="4fcad-131">For more information, see [Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>

## <a name="publish-a-single-file-app---visual-studio"></a><span data-ttu-id="4fcad-132">Publicación de una aplicación de archivo único: Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4fcad-132">Publish a single file app - Visual Studio</span></span>

<span data-ttu-id="4fcad-133">Visual Studio crea perfiles de publicación reutilizables que controlan cómo se publica la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4fcad-133">Visual Studio creates reusable publishing profiles that control how your application is published.</span></span>

01. <span data-ttu-id="4fcad-134">En el panel **Explorador de soluciones**, haga clic con el botón derecho en el proyecto que quiera publicar.</span><span class="sxs-lookup"><span data-stu-id="4fcad-134">On the **Solution Explorer** pane, right-click on the project you want to publish.</span></span> <span data-ttu-id="4fcad-135">Seleccione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="4fcad-135">Select **Publish**.</span></span>

    :::image type="content" source="media/single-file/visual-studio-solution-explorer.png" alt-text="Explorador de soluciones con un menú contextual en el que se resalta la opción Publicar.":::

    <span data-ttu-id="4fcad-137">Si todavía no tiene un perfil de publicación, siga las instrucciones para crear uno y elija el tipo de destino **Carpeta**.</span><span class="sxs-lookup"><span data-stu-id="4fcad-137">If you don't already have a publishing profile, follow the instructions to create one and choose the **Folder** target-type.</span></span>

01. <span data-ttu-id="4fcad-138">Elija **Editar**.</span><span class="sxs-lookup"><span data-stu-id="4fcad-138">Choose **Edit**.</span></span>

    :::image type="content" source="media/single-file/visual-studio-publish-edit-settings.png" alt-text="Perfil de publicación de Visual Studio con el botón Editar.":::

01. <span data-ttu-id="4fcad-140">En el cuadro de diálogo **Configuración de perfil**, establezca las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="4fcad-140">In the **Profile settings** dialog, set the following options:</span></span>

    - <span data-ttu-id="4fcad-141">Establezca **Modo de implementación** en **Independiente**.</span><span class="sxs-lookup"><span data-stu-id="4fcad-141">Set **Deployment mode** to **Self-contained**.</span></span>
    - <span data-ttu-id="4fcad-142">Establezca **Tiempo de ejecución de destino** en la plataforma en la que quiera publicar.</span><span class="sxs-lookup"><span data-stu-id="4fcad-142">Set **Target runtime** to the platform you want to publish to.</span></span>
    - <span data-ttu-id="4fcad-143">Seleccione **Producir un único archivo**.</span><span class="sxs-lookup"><span data-stu-id="4fcad-143">Select **Produce single file**.</span></span>

    <span data-ttu-id="4fcad-144">Elija **Guardar** para guardar la configuración y volver al cuadro de diálogo **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="4fcad-144">Choose **Save** to save the settings and return to the **Publish** dialog.</span></span>

    :::image type="content" source="media/single-file/visual-studio-publish-single-file-properties.png" alt-text="Cuadro de diálogo Configuración de perfil con las opciones Modo de implementación, Tiempo de ejecución de destino y Archivo único resaltadas.":::

01. <span data-ttu-id="4fcad-146">Elija **Publicar** para publicar la aplicación como un archivo único.</span><span class="sxs-lookup"><span data-stu-id="4fcad-146">Choose **Publish** to publish your app as a single file.</span></span>

<span data-ttu-id="4fcad-147">Para obtener más información, vea [Publicación de aplicaciones .NET Core con Visual Studio](deploy-with-vs.md).</span><span class="sxs-lookup"><span data-stu-id="4fcad-147">For more information, see [Publish .NET Core apps with Visual Studio](deploy-with-vs.md).</span></span>

## <a name="publish-a-single-file-app---visual-studio-for-mac"></a><span data-ttu-id="4fcad-148">Publicación de una aplicación de archivo único: Visual Studio para Mac</span><span class="sxs-lookup"><span data-stu-id="4fcad-148">Publish a single file app - Visual Studio for Mac</span></span>

<span data-ttu-id="4fcad-149">Visual Studio para Mac no proporciona opciones para publicar la aplicación como un archivo único.</span><span class="sxs-lookup"><span data-stu-id="4fcad-149">Visual Studio for Mac doesn't provide options to publish your app as a single file.</span></span> <span data-ttu-id="4fcad-150">Tendrá que publicar de forma manual mediante las instrucciones de la sección [Publicación de una aplicación de archivo único: CLI](#publish-a-single-file-app---cli).</span><span class="sxs-lookup"><span data-stu-id="4fcad-150">You'll need to publish manually by following the instructions from the [Publish a single file app - CLI](#publish-a-single-file-app---cli) section.</span></span> <span data-ttu-id="4fcad-151">Para obtener más información, vea [Publicación de aplicaciones .NET Core con la CLI de .NET Core](deploy-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="4fcad-151">For more information, see [Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4fcad-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="4fcad-152">See also</span></span>

- <span data-ttu-id="4fcad-153">[Implementación de aplicaciones .NET Core](index.md).</span><span class="sxs-lookup"><span data-stu-id="4fcad-153">[.NET Core application deployment](index.md).</span></span>
- <span data-ttu-id="4fcad-154">[Publicación de aplicaciones .NET Core con la CLI de .NET Core](deploy-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="4fcad-154">[Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>
- <span data-ttu-id="4fcad-155">[Publicación de aplicaciones .NET Core con Visual Studio](deploy-with-vs.md).</span><span class="sxs-lookup"><span data-stu-id="4fcad-155">[Publish .NET Core apps with Visual Studio](deploy-with-vs.md).</span></span>
- <span data-ttu-id="4fcad-156">[Comando `dotnet publish`](../tools/dotnet-publish.md).</span><span class="sxs-lookup"><span data-stu-id="4fcad-156">[`dotnet publish` command](../tools/dotnet-publish.md).</span></span>
