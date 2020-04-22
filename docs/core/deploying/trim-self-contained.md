---
title: Recorte de aplicaciones autocontenidas
description: Obtenga información sobre cómo recortar aplicaciones autocontenidas para reducir su tamaño. .NET Core agrupa el tiempo de ejecución con una aplicación que se publica autocontenida y que, por lo general, incluye más tiempo de ejecución del que es necesario.
author: jamshedd
ms.author: jamshedd
ms.date: 04/03/2020
ms.openlocfilehash: bb8ac88c5e16b7fd20a7670e4ad76dbe4b44da1b
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242932"
---
# <a name="trim-self-contained-deployments-and-executables"></a><span data-ttu-id="7e1c0-104">Recorte de implementaciones autocontenidas y ejecutables</span><span class="sxs-lookup"><span data-stu-id="7e1c0-104">Trim self-contained deployments and executables</span></span>

<span data-ttu-id="7e1c0-105">Al publicar una aplicación autocontenida, el tiempo de ejecución de .NET Core se agrupa junto con la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7e1c0-105">When publishing an application self-contained, the .NET Core runtime is bundled together with the application.</span></span> <span data-ttu-id="7e1c0-106">Esta agrupación agrega una cantidad considerable de contenido a la aplicación empaquetada.</span><span class="sxs-lookup"><span data-stu-id="7e1c0-106">This bundling adds a significant amount of content to your packaged application.</span></span> <span data-ttu-id="7e1c0-107">En lo que respecta a la implementación de la aplicación, el tamaño suele ser un factor importante.</span><span class="sxs-lookup"><span data-stu-id="7e1c0-107">When it comes to deploying your application, size is often an important factor.</span></span> <span data-ttu-id="7e1c0-108">Mantener lo más pequeño posible el tamaño de la aplicación del paquete suele ser un objetivo para los desarrolladores de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="7e1c0-108">Keeping the size of the package application as small as possible is typically a goal for application developers.</span></span>

<span data-ttu-id="7e1c0-109">En función de la complejidad de la aplicación, solo se necesita un subconjunto del tiempo de ejecución para ejecutarla.</span><span class="sxs-lookup"><span data-stu-id="7e1c0-109">Depending on the complexity of the application, only a subset of the runtime is required to run the application.</span></span> <span data-ttu-id="7e1c0-110">Estas partes sin usar del tiempo de ejecución no son necesarias y se pueden recortar de la aplicación empaquetada.</span><span class="sxs-lookup"><span data-stu-id="7e1c0-110">These unused parts of the runtime are unnecessary and can be trimmed from the packaged application.</span></span>

<span data-ttu-id="7e1c0-111">La característica recorte funciona examinando los archivos binarios de la aplicación para descubrir y compilar un gráfico de los ensamblados en tiempo de ejecución necesarios.</span><span class="sxs-lookup"><span data-stu-id="7e1c0-111">The trimming feature works by examining the application binaries to discover and build a graph of the required runtime assemblies.</span></span> <span data-ttu-id="7e1c0-112">Se excluyen los ensamblados en tiempo de ejecución restantes a los que no se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="7e1c0-112">The remaining runtime assemblies that aren't referenced are excluded.</span></span>

> [!NOTE]
> <span data-ttu-id="7e1c0-113">El recorte es una característica experimental en .NET Core 3.1 y _solo_ está disponible para las aplicaciones que se publican autocontenidas.</span><span class="sxs-lookup"><span data-stu-id="7e1c0-113">Trimming is an experimental feature in .NET Core 3.1 and is _only_ available to applications that are published self-contained.</span></span>

## <a name="prevent-assemblies-from-being-trimmed"></a><span data-ttu-id="7e1c0-114">Impedir que los ensamblados se recorten</span><span class="sxs-lookup"><span data-stu-id="7e1c0-114">Prevent assemblies from being trimmed</span></span>

<span data-ttu-id="7e1c0-115">Hay escenarios en los que la función de recorte no podrá detectar referencias.</span><span class="sxs-lookup"><span data-stu-id="7e1c0-115">There are scenarios in which the trimming functionality will fail to detect references.</span></span> <span data-ttu-id="7e1c0-116">Por ejemplo, cuando se usa la reflexión en un ensamblado en tiempo de ejecución, ya sea por parte de la aplicación o por una biblioteca a la que haga referencia la aplicación, no se hace referencia directamente al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="7e1c0-116">For example, when reflection is used on a runtime assembly, either by your application or a library that is referenced by your application, the assembly isn't directly referenced.</span></span> <span data-ttu-id="7e1c0-117">El recorte desconoce estas referencias indirectas y excluirá la biblioteca de la carpeta publicada.</span><span class="sxs-lookup"><span data-stu-id="7e1c0-117">Trimming is unaware of these indirect references and would exclude the library from the published folder.</span></span>

<span data-ttu-id="7e1c0-118">Cuando el código hace referencia indirectamente a un ensamblado mediante la reflexión, puede evitar que el ensamblado se recorte con la configuración `<TrimmerRootAssembly>`.</span><span class="sxs-lookup"><span data-stu-id="7e1c0-118">When the code is indirectly referencing an assembly through reflection, you can prevent the assembly from being trimmed with the `<TrimmerRootAssembly>` setting.</span></span> <span data-ttu-id="7e1c0-119">En el ejemplo siguiente se muestra cómo evitar que un ensamblado llamado `System.Security` se recorte:</span><span class="sxs-lookup"><span data-stu-id="7e1c0-119">The following example shows how to prevent an assembly called `System.Security` assembly from being trimmed:</span></span>

```xml
<ItemGroup>
    <TrimmerRootAssembly Include="System.Security" />
</ItemGroup>
```

## <a name="trim-your-app---cli"></a><span data-ttu-id="7e1c0-120">Recorte de la aplicación: CLI</span><span class="sxs-lookup"><span data-stu-id="7e1c0-120">Trim your app - CLI</span></span>

<span data-ttu-id="7e1c0-121">Recorte la aplicación mediante el comando [dotnet publish](../tools/dotnet-publish.md).</span><span class="sxs-lookup"><span data-stu-id="7e1c0-121">Trim your application using the [dotnet publish](../tools/dotnet-publish.md) command.</span></span> <span data-ttu-id="7e1c0-122">Al publicar la aplicación, establezca las tres opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="7e1c0-122">When you publish your app, set the following three settings:</span></span>

- <span data-ttu-id="7e1c0-123">Publicación como independiente: `--self-contained true`</span><span class="sxs-lookup"><span data-stu-id="7e1c0-123">Publish as self-contained: `--self-contained true`</span></span>
- <span data-ttu-id="7e1c0-124">Deshabilitar la publicación de un solo archivo: `-p:PublishSingleFile=false`</span><span class="sxs-lookup"><span data-stu-id="7e1c0-124">Disable single-file publishing: `-p:PublishSingleFile=false`</span></span>
- <span data-ttu-id="7e1c0-125">Habilitar recorte: `p:PublishTrimmed=true`</span><span class="sxs-lookup"><span data-stu-id="7e1c0-125">Enable trimming: `p:PublishTrimmed=true`</span></span>

<span data-ttu-id="7e1c0-126">En el ejemplo siguiente se publica una aplicación para Windows 10 como independiente y se recorta la salida.</span><span class="sxs-lookup"><span data-stu-id="7e1c0-126">The following example publishes an app for Windows 10 as self-contained and trims the output.</span></span>

```dotnetcli
dotnet publish -c Release -r win10-x64 --self-contained true -p:PublishSingleFile=false -p:PublishTrimmed=true
```

<span data-ttu-id="7e1c0-127">Para obtener más información, vea [Publicación de aplicaciones .NET Core con la CLI de .NET Core](deploy-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="7e1c0-127">For more information, see [Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>

## <a name="trim-your-app---visual-studio"></a><span data-ttu-id="7e1c0-128">Recorte de la aplicación: Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7e1c0-128">Trim your app - Visual Studio</span></span>

<span data-ttu-id="7e1c0-129">Visual Studio crea perfiles de publicación reutilizables que controlan cómo se publica la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7e1c0-129">Visual Studio creates reusable publishing profiles that control how your application is published.</span></span>

01. <span data-ttu-id="7e1c0-130">En el panel **Explorador de soluciones**, haga clic con el botón derecho en el proyecto que quiera publicar.</span><span class="sxs-lookup"><span data-stu-id="7e1c0-130">On the **Solution Explorer** pane, right-click on the project you want to publish.</span></span> <span data-ttu-id="7e1c0-131">Seleccione **Publicar...** .</span><span class="sxs-lookup"><span data-stu-id="7e1c0-131">Select **Publish...**.</span></span>

    :::image type="content" source="media/trim-self-contained/visual-studio-solution-explorer.png" alt-text="Explorador de soluciones con un menú contextual en el que se resalta la opción Publicar.":::

    <span data-ttu-id="7e1c0-133">Si todavía no tiene un perfil de publicación, siga las instrucciones para crear uno y elija el tipo de destino **Carpeta**.</span><span class="sxs-lookup"><span data-stu-id="7e1c0-133">If you don't already have a publishing profile, follow the instructions to create one and choose the **Folder** target-type.</span></span>

01. <span data-ttu-id="7e1c0-134">Elija **Editar**.</span><span class="sxs-lookup"><span data-stu-id="7e1c0-134">Choose **Edit**.</span></span>

    :::image type="content" source="media/trim-self-contained/visual-studio-publish-edit-settings.png" alt-text="Perfil de publicación de Visual Studio con el botón Editar.":::

01. <span data-ttu-id="7e1c0-136">En el cuadro de diálogo **Configuración de perfil**, establezca las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="7e1c0-136">In the **Profile settings** dialog, set the following options:</span></span>

    - <span data-ttu-id="7e1c0-137">Establezca **Modo de implementación** en **Independiente**.</span><span class="sxs-lookup"><span data-stu-id="7e1c0-137">Set **Deployment mode** to **Self-contained**.</span></span>
    - <span data-ttu-id="7e1c0-138">Establezca **Tiempo de ejecución de destino** en la plataforma en la que quiera publicar.</span><span class="sxs-lookup"><span data-stu-id="7e1c0-138">Set **Target runtime** to the platform you want to publish to.</span></span>
    - <span data-ttu-id="7e1c0-139">Seleccione **Quitar los ensamblados no usados (en versión preliminar)** .</span><span class="sxs-lookup"><span data-stu-id="7e1c0-139">Select **Trim unused assemblies (in preview)**.</span></span>

    <span data-ttu-id="7e1c0-140">Elija **Guardar** para guardar la configuración y volver al cuadro de diálogo **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="7e1c0-140">Choose **Save** to save the settings and return to the **Publish** dialog.</span></span>

    :::image type="content" source="media/trim-self-contained/visual-studio-publish-properties.png" alt-text="Cuadro de diálogo Configuración de perfil con las opciones Modo de implementación, Tiempo de ejecución de destino y Quitar los ensamblados no usados resaltadas.":::

01. <span data-ttu-id="7e1c0-142">Elija **Publicar** para publicar la aplicación recortada.</span><span class="sxs-lookup"><span data-stu-id="7e1c0-142">Choose **Publish** to publish your app trimmed.</span></span>

<span data-ttu-id="7e1c0-143">Para obtener más información, vea [Publicación de aplicaciones .NET Core con Visual Studio](deploy-with-vs.md).</span><span class="sxs-lookup"><span data-stu-id="7e1c0-143">For more information, see [Publish .NET Core apps with Visual Studio](deploy-with-vs.md).</span></span>

## <a name="trim-your-app---visual-studio-for-mac"></a><span data-ttu-id="7e1c0-144">Recorte de la aplicación: Visual Studio para Mac</span><span class="sxs-lookup"><span data-stu-id="7e1c0-144">Trim your app - Visual Studio for Mac</span></span>

<span data-ttu-id="7e1c0-145">Visual Studio para Mac no proporciona opciones para recortar la aplicación durante la publicación.</span><span class="sxs-lookup"><span data-stu-id="7e1c0-145">Visual Studio for Mac doesn't provide options to trim your app during publish.</span></span> <span data-ttu-id="7e1c0-146">Tendrá que publicar de forma manual mediante las instrucciones de la sección [Recorte de la aplicación: CLI](#trim-your-app---cli).</span><span class="sxs-lookup"><span data-stu-id="7e1c0-146">You'll need to publish manually by following the instructions from the [Trim your app - CLI](#trim-your-app---cli) section.</span></span> <span data-ttu-id="7e1c0-147">Para obtener más información, vea [Publicación de aplicaciones .NET Core con la CLI de .NET Core](deploy-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="7e1c0-147">For more information, see [Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7e1c0-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="7e1c0-148">See also</span></span>

- <span data-ttu-id="7e1c0-149">[Implementación de aplicaciones .NET Core](index.md).</span><span class="sxs-lookup"><span data-stu-id="7e1c0-149">[.NET Core application deployment](index.md).</span></span>
- <span data-ttu-id="7e1c0-150">[Publicación de aplicaciones .NET Core con la CLI de .NET Core](deploy-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="7e1c0-150">[Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>
- <span data-ttu-id="7e1c0-151">[Publicación de aplicaciones .NET Core con Visual Studio](deploy-with-vs.md).</span><span class="sxs-lookup"><span data-stu-id="7e1c0-151">[Publish .NET Core apps with Visual Studio](deploy-with-vs.md).</span></span>
- <span data-ttu-id="7e1c0-152">[Comando dotnet publish](../tools/dotnet-publish.md).</span><span class="sxs-lookup"><span data-stu-id="7e1c0-152">[dotnet publish command](../tools/dotnet-publish.md).</span></span>
