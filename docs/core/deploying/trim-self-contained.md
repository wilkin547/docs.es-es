---
title: Recorte de aplicaciones autocontenidas
description: Obtenga información sobre cómo recortar aplicaciones autocontenidas para reducir su tamaño. .NET Core agrupa el tiempo de ejecución con una aplicación que se publica autocontenida y que, por lo general, incluye más tiempo de ejecución del que es necesario.
author: jamshedd
ms.author: jamshedd
ms.date: 04/03/2020
ms.openlocfilehash: 9c2994c98a2ebe6f45b056256c2bda28db017fbf
ms.sourcegitcommit: e7acba36517134238065e4d50bb4a1cfe47ebd06
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2020
ms.locfileid: "89465486"
---
# <a name="trim-self-contained-deployments-and-executables"></a><span data-ttu-id="7bf44-104">Recorte de implementaciones autocontenidas y ejecutables</span><span class="sxs-lookup"><span data-stu-id="7bf44-104">Trim self-contained deployments and executables</span></span>

<span data-ttu-id="7bf44-105">El [modelo de implementación dependiente del marco](index.md#publish-framework-dependent) ha sido el modelo de implementación más eficaz desde el inicio de .NET.</span><span class="sxs-lookup"><span data-stu-id="7bf44-105">The [framework-dependent deployment model](index.md#publish-framework-dependent) has been the most successful deployment model since the inception of .NET.</span></span> <span data-ttu-id="7bf44-106">En este escenario, el desarrollador de la aplicación agrupa solo la aplicación y los ensamblados de terceros con la expectativa de que las bibliotecas del entorno de ejecución y el marco de .NET estén disponibles en el equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="7bf44-106">In this scenario, the application developer bundles only the application and third-party assemblies with the expectation that the .NET runtime and framework libraries will be available in the client machine.</span></span> <span data-ttu-id="7bf44-107">Este modelo de implementación sigue siendo el dominante en .NET Core, pero hay algunos escenarios en los que el modelo dependiente del marco no es óptimo.</span><span class="sxs-lookup"><span data-stu-id="7bf44-107">This deployment model continues to be the dominant one in .NET Core as well but there are some scenarios where the framework-dependent model is not optimal.</span></span> <span data-ttu-id="7bf44-108">La alternativa es publicar una [aplicación independiente](index.md#publish-self-contained), donde el entorno de ejecución y el marco de .NET Core están agrupados con la aplicación y ensamblados de terceros.</span><span class="sxs-lookup"><span data-stu-id="7bf44-108">The alternative is to publish a [self-contained application](index.md#publish-self-contained), where the .NET Core runtime and framework are bundled together with the application and third-party assemblies.</span></span>

<span data-ttu-id="7bf44-109">El modelo de implementación trim independiente es una versión especializada del modelo de implementación independiente que está optimizado para reducir el tamaño de la implementación.</span><span class="sxs-lookup"><span data-stu-id="7bf44-109">The trim-self-contained deployment model is a specialized version of the self-contained deployment model that is optimized to reduce deployment size.</span></span> <span data-ttu-id="7bf44-110">Minimizar el tamaño de la implementación es un requisito fundamental para algunos escenarios del lado cliente, como las aplicaciones Blazor.</span><span class="sxs-lookup"><span data-stu-id="7bf44-110">Minimizing deployment size is a critical requirement for some client-side scenarios like Blazor applications.</span></span> <span data-ttu-id="7bf44-111">En función de la complejidad de la aplicación, solo se hace referencia a un subconjunto de ensamblados de marco, y se requiere un subconjunto del código en cada ensamblado para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7bf44-111">Depending on the complexity of the application, only a subset of the framework assemblies are referenced, and a subset of the code within each assembly is required to run the application.</span></span> <span data-ttu-id="7bf44-112">Las partes sin usar de las bibliotecas no son necesarias y se pueden recortar de la aplicación empaquetada.</span><span class="sxs-lookup"><span data-stu-id="7bf44-112">The unused parts of the libraries are unnecessary and can be trimmed from the packaged application.</span></span>

<span data-ttu-id="7bf44-113">No obstante, existe el riesgo de que el análisis del tiempo de compilación de la aplicación pueda causar errores en tiempo de ejecución, debido a que no puede analizar de forma confiable diversos patrones de código problemáticos (centrados en gran medida en el uso de la reflexión).</span><span class="sxs-lookup"><span data-stu-id="7bf44-113">However, there is a risk that the build time analysis of the application can cause failures at runtime, due to not being able to reliably analyze various problematic code patterns (largely centered on reflection use).</span></span> <span data-ttu-id="7bf44-114">Dado que no se puede garantizar la confiabilidad, este modelo de implementación se ofrece como una característica en versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="7bf44-114">Because reliability can't be guaranteed, this deployment model is offered as a preview feature.</span></span>

<span data-ttu-id="7bf44-115">El motor de análisis en tiempo de compilación proporciona advertencias al desarrollador de los patrones de código problemáticos para detectar qué otro código es necesario.</span><span class="sxs-lookup"><span data-stu-id="7bf44-115">The build time analysis engine provides warnings to the developer of code patterns that are problematic to detect which other code is required.</span></span> <span data-ttu-id="7bf44-116">El código se puede anotar con atributos para indicar al recortador qué más se debe incluir.</span><span class="sxs-lookup"><span data-stu-id="7bf44-116">Code can be annotated with attributes to tell the trimmer what else to include.</span></span> <span data-ttu-id="7bf44-117">Muchos patrones de reflexión se pueden reemplazar por la generación de código en tiempo de compilación mediante [generadores de código fuente](https://github.com/dotnet/roslyn/blob/master/docs/features/source-generators.md).</span><span class="sxs-lookup"><span data-stu-id="7bf44-117">Many reflection patterns can be replaced with build-time code generation using [Source Generators](https://github.com/dotnet/roslyn/blob/master/docs/features/source-generators.md).</span></span>

<span data-ttu-id="7bf44-118">El modo de recorte de las aplicaciones se configura con `TrimMode`.</span><span class="sxs-lookup"><span data-stu-id="7bf44-118">The trim mode for the applications is configured with the `TrimMode` setting.</span></span> <span data-ttu-id="7bf44-119">El valor predeterminado es `copyused` y agrupa los ensamblados a los que se hace referencia con la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7bf44-119">The default value is `copyused` and bundles referenced assemblies with the application.</span></span> <span data-ttu-id="7bf44-120">El valor `link` se usa con las aplicaciones WebAssembly de Blazor y recorta el código no usado dentro de los ensamblados.</span><span class="sxs-lookup"><span data-stu-id="7bf44-120">The `link` value is used with Blazor WebAssembly applications and trims unused code within assemblies.</span></span> <span data-ttu-id="7bf44-121">Las advertencias de análisis de recorte proporcionan información sobre patrones de código en los que no es posible realizar análisis de dependencias completas.</span><span class="sxs-lookup"><span data-stu-id="7bf44-121">Trim analysis warnings give information on code patterns where a full dependency analysis was not possible.</span></span> <span data-ttu-id="7bf44-122">Estas advertencias se suprimen de forma predeterminada y se pueden activar estableciendo la marca `SuppressTrimAnalysisWarnings` en `false`.</span><span class="sxs-lookup"><span data-stu-id="7bf44-122">These warnings are suppressed by default and can be turned on by setting the flag `SuppressTrimAnalysisWarnings` to `false`.</span></span> <span data-ttu-id="7bf44-123">Para obtener más información acerca de las opciones de recorte disponibles, vea [Opciones de recorte](trimming-options.md).</span><span class="sxs-lookup"><span data-stu-id="7bf44-123">For more information about the trim options available, see [Trimming options](trimming-options.md).</span></span>

> [!NOTE]
> <span data-ttu-id="7bf44-124">El recorte es una característica experimental en .NET Core 3.1, 5.0 y _solo_ está disponible para las aplicaciones que se publican independientes.</span><span class="sxs-lookup"><span data-stu-id="7bf44-124">Trimming is an experimental feature in .NET Core 3.1, 5.0 and is _only_ available to applications that are published self-contained.</span></span>

## <a name="prevent-assemblies-from-being-trimmed"></a><span data-ttu-id="7bf44-125">Impedir que los ensamblados se recorten</span><span class="sxs-lookup"><span data-stu-id="7bf44-125">Prevent assemblies from being trimmed</span></span>

<span data-ttu-id="7bf44-126">Hay escenarios en los que la función de recorte no podrá detectar referencias.</span><span class="sxs-lookup"><span data-stu-id="7bf44-126">There are scenarios in which the trimming functionality will fail to detect references.</span></span> <span data-ttu-id="7bf44-127">Por ejemplo, cuando se usa la reflexión en un ensamblado en tiempo de ejecución, ya sea por parte de la aplicación o por una biblioteca a la que haga referencia la aplicación, no se hace referencia directamente al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="7bf44-127">For example, when reflection is used on a runtime assembly, either by your application or a library that is referenced by your application, the assembly isn't directly referenced.</span></span> <span data-ttu-id="7bf44-128">El recorte desconoce estas referencias indirectas y excluirá la biblioteca de la carpeta publicada.</span><span class="sxs-lookup"><span data-stu-id="7bf44-128">Trimming is unaware of these indirect references and would exclude the library from the published folder.</span></span>

<span data-ttu-id="7bf44-129">Cuando el código hace referencia indirectamente a un ensamblado mediante la reflexión, puede evitar que el ensamblado se recorte con la configuración `<TrimmerRootAssembly>`.</span><span class="sxs-lookup"><span data-stu-id="7bf44-129">When the code is indirectly referencing an assembly through reflection, you can prevent the assembly from being trimmed with the `<TrimmerRootAssembly>` setting.</span></span> <span data-ttu-id="7bf44-130">En el ejemplo siguiente se muestra cómo evitar que un ensamblado llamado `System.Security` se recorte:</span><span class="sxs-lookup"><span data-stu-id="7bf44-130">The following example shows how to prevent an assembly called `System.Security` assembly from being trimmed:</span></span>

```xml
<ItemGroup>
    <TrimmerRootAssembly Include="System.Security" />
</ItemGroup>
```

## <a name="trim-your-app---cli"></a><span data-ttu-id="7bf44-131">Recorte de la aplicación: CLI</span><span class="sxs-lookup"><span data-stu-id="7bf44-131">Trim your app - CLI</span></span>

<span data-ttu-id="7bf44-132">Recorte la aplicación mediante el comando [dotnet publish](../tools/dotnet-publish.md).</span><span class="sxs-lookup"><span data-stu-id="7bf44-132">Trim your application using the [dotnet publish](../tools/dotnet-publish.md) command.</span></span> <span data-ttu-id="7bf44-133">Al publicar la aplicación, establezca las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="7bf44-133">When you publish your app, set the following properties:</span></span>

- <span data-ttu-id="7bf44-134">Publicar como una aplicación independiente para un entorno de ejecución específico: `-r win-x64`</span><span class="sxs-lookup"><span data-stu-id="7bf44-134">Publish as a self-contained app for a specific runtime: `-r win-x64`</span></span>
- <span data-ttu-id="7bf44-135">Habilitar recorte: `/p:PublishTrimmed=true`</span><span class="sxs-lookup"><span data-stu-id="7bf44-135">Enable trimming: `/p:PublishTrimmed=true`</span></span>

<span data-ttu-id="7bf44-136">En este ejemplo se publica una aplicación para Windows como independiente y se recorta la salida.</span><span class="sxs-lookup"><span data-stu-id="7bf44-136">The following example publishes an app for Windows as self-contained and trims the output.</span></span>

```xml
<PropertyGroup>
    <RuntimeIdentifier>win-x64</RuntimeIdentifier>
    <PublishTrimmed>true</PublishTrimmed>
</PropertyGroup>
```

<span data-ttu-id="7bf44-137">En este ejemplo se publica una aplicación en el modo de recorte agresivo en el que el código no usado dentro de los ensamblados se desactivará y se habilitarán las advertencias de recorte.</span><span class="sxs-lookup"><span data-stu-id="7bf44-137">The following example publishes an app in the aggressive trim mode where unused code within assemblies will be trimmed and trimmer warnings enabled.</span></span>

```xml
<PropertyGroup>
    <RuntimeIdentifier>win-x64</RuntimeIdentifier>
    <PublishTrimmed>true</PublishTrimmed>
    <TrimMode>link</TrimMode>
    <SuppressTrimAnalysisWarnings>false</SuppressTrimAnalysisWarnings>
</PropertyGroup>
```

<span data-ttu-id="7bf44-138">Para obtener más información, vea [Publicación de aplicaciones .NET Core con la CLI de .NET Core](deploy-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="7bf44-138">For more information, see [Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>

## <a name="trim-your-app---visual-studio"></a><span data-ttu-id="7bf44-139">Recorte de la aplicación: Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7bf44-139">Trim your app - Visual Studio</span></span>

<span data-ttu-id="7bf44-140">Visual Studio crea perfiles de publicación reutilizables que controlan cómo se publica la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7bf44-140">Visual Studio creates reusable publishing profiles that control how your application is published.</span></span>

01. <span data-ttu-id="7bf44-141">En el panel **Explorador de soluciones**, haga clic con el botón derecho en el proyecto que quiera publicar.</span><span class="sxs-lookup"><span data-stu-id="7bf44-141">On the **Solution Explorer** pane, right-click on the project you want to publish.</span></span> <span data-ttu-id="7bf44-142">Seleccione **Publicar...** .</span><span class="sxs-lookup"><span data-stu-id="7bf44-142">Select **Publish...**.</span></span>

    :::image type="content" source="media/trim-self-contained/visual-studio-solution-explorer.png" alt-text="Explorador de soluciones con un menú contextual en el que se resalta la opción Publicar.":::

    <span data-ttu-id="7bf44-144">Si todavía no tiene un perfil de publicación, siga las instrucciones para crear uno y elija el tipo de destino **Carpeta**.</span><span class="sxs-lookup"><span data-stu-id="7bf44-144">If you don't already have a publishing profile, follow the instructions to create one and choose the **Folder** target-type.</span></span>

01. <span data-ttu-id="7bf44-145">Elija **Editar**.</span><span class="sxs-lookup"><span data-stu-id="7bf44-145">Choose **Edit**.</span></span>

    :::image type="content" source="media/trim-self-contained/visual-studio-publish-edit-settings.png" alt-text="Perfil de publicación de Visual Studio con el botón Editar.":::

01. <span data-ttu-id="7bf44-147">En el cuadro de diálogo **Configuración de perfil**, establezca las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="7bf44-147">In the **Profile settings** dialog, set the following options:</span></span>

    - <span data-ttu-id="7bf44-148">Establezca **Modo de implementación** en **Independiente**.</span><span class="sxs-lookup"><span data-stu-id="7bf44-148">Set **Deployment mode** to **Self-contained**.</span></span>
    - <span data-ttu-id="7bf44-149">Establezca **Tiempo de ejecución de destino** en la plataforma en la que quiera publicar.</span><span class="sxs-lookup"><span data-stu-id="7bf44-149">Set **Target runtime** to the platform you want to publish to.</span></span>
    - <span data-ttu-id="7bf44-150">Seleccione **Quitar los ensamblados no usados (en versión preliminar)** .</span><span class="sxs-lookup"><span data-stu-id="7bf44-150">Select **Trim unused assemblies (in preview)**.</span></span>

    <span data-ttu-id="7bf44-151">Elija **Guardar** para guardar la configuración y volver al cuadro de diálogo **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="7bf44-151">Choose **Save** to save the settings and return to the **Publish** dialog.</span></span>

    :::image type="content" source="media/trim-self-contained/visual-studio-publish-properties.png" alt-text="Cuadro de diálogo Configuración de perfil con las opciones Modo de implementación, Tiempo de ejecución de destino y Quitar los ensamblados no usados resaltadas.":::

01. <span data-ttu-id="7bf44-153">Elija **Publicar** para publicar la aplicación recortada.</span><span class="sxs-lookup"><span data-stu-id="7bf44-153">Choose **Publish** to publish your app trimmed.</span></span>

<span data-ttu-id="7bf44-154">Para obtener más información, vea [Publicación de aplicaciones .NET Core con Visual Studio](deploy-with-vs.md).</span><span class="sxs-lookup"><span data-stu-id="7bf44-154">For more information, see [Publish .NET Core apps with Visual Studio](deploy-with-vs.md).</span></span>

## <a name="trim-your-app---visual-studio-for-mac"></a><span data-ttu-id="7bf44-155">Recorte de la aplicación: Visual Studio para Mac</span><span class="sxs-lookup"><span data-stu-id="7bf44-155">Trim your app - Visual Studio for Mac</span></span>

<span data-ttu-id="7bf44-156">Visual Studio para Mac no proporciona opciones para recortar la aplicación durante la publicación.</span><span class="sxs-lookup"><span data-stu-id="7bf44-156">Visual Studio for Mac doesn't provide options to trim your app during publish.</span></span> <span data-ttu-id="7bf44-157">Tendrá que publicar de forma manual mediante las instrucciones de la sección [Recorte de la aplicación: CLI](#trim-your-app---cli).</span><span class="sxs-lookup"><span data-stu-id="7bf44-157">You'll need to publish manually by following the instructions from the [Trim your app - CLI](#trim-your-app---cli) section.</span></span> <span data-ttu-id="7bf44-158">Para obtener más información, vea [Publicación de aplicaciones .NET Core con la CLI de .NET Core](deploy-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="7bf44-158">For more information, see [Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7bf44-159">Vea también</span><span class="sxs-lookup"><span data-stu-id="7bf44-159">See also</span></span>

- <span data-ttu-id="7bf44-160">[Implementación de aplicaciones .NET Core](index.md).</span><span class="sxs-lookup"><span data-stu-id="7bf44-160">[.NET Core application deployment](index.md).</span></span>
- <span data-ttu-id="7bf44-161">[Publicación de aplicaciones .NET Core con la CLI de .NET Core](deploy-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="7bf44-161">[Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>
- <span data-ttu-id="7bf44-162">[Publicación de aplicaciones .NET Core con Visual Studio](deploy-with-vs.md).</span><span class="sxs-lookup"><span data-stu-id="7bf44-162">[Publish .NET Core apps with Visual Studio](deploy-with-vs.md).</span></span>
- <span data-ttu-id="7bf44-163">[Comando dotnet publish](../tools/dotnet-publish.md).</span><span class="sxs-lookup"><span data-stu-id="7bf44-163">[dotnet publish command](../tools/dotnet-publish.md).</span></span>
