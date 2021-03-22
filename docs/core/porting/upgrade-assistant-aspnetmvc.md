---
title: Actualización de aplicaciones de MVC de ASP.NET a .NET 5
description: Use el Asistente para actualización de .NET para actualizar una aplicación .NET Framework de MVC de ASP.NET existente a .NET 5. El Asistente para actualización de .NET es una herramienta de la CLI que ayuda a migrar una aplicación de .NET Framework a .NET 5.
author: ardalis
ms.date: 03/08/2021
ms.openlocfilehash: 421d8ce16bc1800451ee39c20c4746ea321fafd0
ms.sourcegitcommit: 46cfed35d79d70e08c313b9c664c7e76babab39e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/10/2021
ms.locfileid: "102604962"
---
# <a name="upgrade-an-aspnet-mvc-app-to-net-5-with-the-net-upgrade-assistant"></a><span data-ttu-id="fa133-104">Actualización de una aplicación ASP.NET de MVC a .NET 5 con el Asistente para actualización de .NET</span><span class="sxs-lookup"><span data-stu-id="fa133-104">Upgrade an ASP.NET MVC App to .NET 5 with the .NET Upgrade Assistant</span></span>

<span data-ttu-id="fa133-105">El [Asistente para actualización de .NET](upgrade-assistant-overview.md) es una herramienta de la línea de comandos que puede ayudar en la actualización de aplicaciones .NET Framework de MVC de ASP.NET a .NET 5.</span><span class="sxs-lookup"><span data-stu-id="fa133-105">The [.NET Upgrade Assistant](upgrade-assistant-overview.md) is a command-line tool that can assist with upgrading .NET Framework ASP.NET MVC apps to .NET 5.</span></span> <span data-ttu-id="fa133-106">En este artículo se proporciona:</span><span class="sxs-lookup"><span data-stu-id="fa133-106">This article provides:</span></span>

- <span data-ttu-id="fa133-107">Demostración de cómo se ejecuta la herramienta en una aplicación .NET Framework de MVC de ASP.NET</span><span class="sxs-lookup"><span data-stu-id="fa133-107">A demonstration of how to run the tool against a .NET Framework ASP.NET MVC app</span></span>
- <span data-ttu-id="fa133-108">Sugerencias de solución de problemas</span><span class="sxs-lookup"><span data-stu-id="fa133-108">Troubleshooting tips</span></span>

## <a name="upgrade-net-framework-aspnet-mvc-apps"></a><span data-ttu-id="fa133-109">Actualización de aplicaciones .NET Framework de ASP.NET de MVC</span><span class="sxs-lookup"><span data-stu-id="fa133-109">Upgrade .NET Framework ASP.NET MVC apps</span></span>

<span data-ttu-id="fa133-110">En esta sección se muestra cómo ejecutar el Asistente para actualización de .NET en una aplicación de MVC de ASP.NET recién creada para .NET Framework 4.6.1.</span><span class="sxs-lookup"><span data-stu-id="fa133-110">This section demonstrates running the .NET Upgrade Assistant against a newly created ASP.NET MVC app targeting .NET Framework 4.6.1.</span></span> <span data-ttu-id="fa133-111">Para obtener más información sobre cómo instalar la herramienta, consulte [Información general del Asistente para actualización de .NET](upgrade-assistant-overview.md).</span><span class="sxs-lookup"><span data-stu-id="fa133-111">For more information on how to install the tool, see [Overview of the .NET Upgrade Assistant](upgrade-assistant-overview.md).</span></span>

### <a name="initial-demo-setup"></a><span data-ttu-id="fa133-112">Configuración inicial de demo</span><span class="sxs-lookup"><span data-stu-id="fa133-112">Initial demo setup</span></span>

<span data-ttu-id="fa133-113">Si está ejecutando el Asistente para actualización de .NET en su propia aplicación .NET Framework, puede omitir este paso.</span><span class="sxs-lookup"><span data-stu-id="fa133-113">If you're running the .NET Upgrade Assistant against your own .NET Framework app, you can skip this step.</span></span> <span data-ttu-id="fa133-114">Si solo desea probarlo para ver cómo funciona, este paso le muestra cómo configurar un proyecto de ejemplo de MVC de ASP.NET y API web (.NET Framework) para usarlo.</span><span class="sxs-lookup"><span data-stu-id="fa133-114">If you just want to try it out to see how it works, this step shows you how to set up a sample ASP.NET MVC and Web API (.NET Framework) project to use.</span></span>

<span data-ttu-id="fa133-115">Con Visual Studio, cree un nuevo proyecto de aplicación web de ASP.NET con .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fa133-115">Using Visual Studio, create a new ASP.NET Web Application project using .NET Framework.</span></span>

:::image type="content" source="media/upgrade-assistant-aspnetmvc/new-project.png" alt-text="Nuevo proyecto de aplicación web de ASP.NET en Visual Studio":::

<span data-ttu-id="fa133-117">Asigne el nombre **AspNetMvcTest** al proyecto.</span><span class="sxs-lookup"><span data-stu-id="fa133-117">Name the project **AspNetMvcTest**.</span></span> <span data-ttu-id="fa133-118">Configure el proyecto para usar **.NET Framework 4.6.1**.</span><span class="sxs-lookup"><span data-stu-id="fa133-118">Configure the project to use **.NET Framework 4.6.1**.</span></span>

:::image type="content" source="media/upgrade-assistant-aspnetmvc/configure-project.png" alt-text="Configuración del proyecto de ASP.NET en Visual Studio":::

<span data-ttu-id="fa133-120">En el siguiente cuadro de diálogo, elija la aplicación **MVC** y, a continuación, seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="fa133-120">In the next dialog, choose **MVC** application, then select **Create**.</span></span>

:::image type="content" source="media/upgrade-assistant-aspnetmvc/create-mvc-webapi.png" alt-text="Creación de un proyecto de MVC de ASP.NET en Visual Studio":::

<span data-ttu-id="fa133-122">Revise el proyecto creado y sus archivos, especialmente los archivos de proyecto.</span><span class="sxs-lookup"><span data-stu-id="fa133-122">Review the created project and its files, especially its project file(s).</span></span>

### <a name="run-upgrade-assistant"></a><span data-ttu-id="fa133-123">Ejecución del asistente para actualización</span><span class="sxs-lookup"><span data-stu-id="fa133-123">Run upgrade-assistant</span></span>

<span data-ttu-id="fa133-124">Abra un terminal y desplácese hasta la carpeta en la que se encuentra el proyecto o la solución de destino.</span><span class="sxs-lookup"><span data-stu-id="fa133-124">Open a terminal and navigate to the folder where the target project or solution is located.</span></span> <span data-ttu-id="fa133-125">Ejecute el comando `upgrade-assistant`, pasando el nombre del proyecto de destino (puede ejecutar el comando desde cualquier lugar, siempre que la ruta de acceso al archivo de proyecto sea válida).</span><span class="sxs-lookup"><span data-stu-id="fa133-125">Run the `upgrade-assistant` command, passing in the name of the project you're targeting (you can run the command from anywhere, as long as the path to the project file is valid).</span></span>

```console
upgrade-assistant .\AspNetMvcTest.csproj
```

<span data-ttu-id="fa133-126">La herramienta se ejecuta y muestra una lista de los pasos que realizará.</span><span class="sxs-lookup"><span data-stu-id="fa133-126">The tool runs and shows you a list of the steps it will do.</span></span>

:::image type="content" source="media/upgrade-assistant-aspnetmvc/initial-run.png" alt-text="Pantalla inicial del Asistente para actualización de .NET":::

<span data-ttu-id="fa133-128">A medida que se completa cada paso, la herramienta proporciona un conjunto de comandos que permiten al usuario aplicar u omitir el paso siguiente, consultar más detalles, configurar el registro o salir del proceso.</span><span class="sxs-lookup"><span data-stu-id="fa133-128">As each step is completed, the tool provides a set of commands allowing the user to apply or skip the next step, see more details, configure logging, or exit the process.</span></span> <span data-ttu-id="fa133-129">Si la herramienta detecta que un paso no realizará ninguna acción, omite automáticamente ese paso y continua al paso siguiente hasta que llega a uno que tiene acciones por realizar.</span><span class="sxs-lookup"><span data-stu-id="fa133-129">If the tool detects that a step will perform no actions, it automatically skips that step and continues to the next step until it reaches one that has actions to perform.</span></span> <span data-ttu-id="fa133-130">Al presionar <kbd>Entrar</kbd>, se realizará el siguiente paso si no se realiza ninguna otra selección.</span><span class="sxs-lookup"><span data-stu-id="fa133-130">Pressing <kbd>Enter</kbd> will perform the next step if no other selection is made.</span></span>

<span data-ttu-id="fa133-131">En este ejemplo, cada vez se elige el paso Aplicar.</span><span class="sxs-lookup"><span data-stu-id="fa133-131">In this example, the apply step is chosen each time.</span></span> <span data-ttu-id="fa133-132">El primer paso es realizar una copia de seguridad del proyecto.</span><span class="sxs-lookup"><span data-stu-id="fa133-132">The first step is to back up the project.</span></span>

:::image type="content" source="media/upgrade-assistant-aspnetmvc/backup-project.png" alt-text="Copia de seguridad del proyecto en el Asistente para actualización de .NET":::

<span data-ttu-id="fa133-134">La herramienta solicita una ruta de acceso personalizada para la copia de seguridad o bien usar el valor predeterminado, que colocará la copia de seguridad del proyecto en la misma carpeta con una extensión `.backup`.</span><span class="sxs-lookup"><span data-stu-id="fa133-134">The tool prompts for a custom path for the backup, or to use the default, which will place the project backup in the same folder with a `.backup` extension.</span></span> <span data-ttu-id="fa133-135">El siguiente paso que realiza la herramienta es convertir el archivo de proyecto al estilo SDK.</span><span class="sxs-lookup"><span data-stu-id="fa133-135">The next step the tool does is to convert the project file to SDK style.</span></span>

:::image type="content" source="media/upgrade-assistant-aspnetmvc/convert-project.png" alt-text="Conversión del proyecto al estilo SDK en el Asistente para actualización de .NET":::

<span data-ttu-id="fa133-137">Una vez actualizado el formato del proyecto, el paso siguiente es actualizar el TFM del proyecto.</span><span class="sxs-lookup"><span data-stu-id="fa133-137">Once the project format has been updated, the next step is to update the TFM of the project.</span></span>

:::image type="content" source="media/upgrade-assistant-aspnetmvc/update-tfm.png" alt-text="TFM de actualización del Asistente para actualización de .NET":::

<span data-ttu-id="fa133-139">A continuación, la herramienta actualiza los paquetes NuGet del proyecto.</span><span class="sxs-lookup"><span data-stu-id="fa133-139">Next, the tool updates the project's NuGet packages.</span></span> <span data-ttu-id="fa133-140">Varios paquetes necesitan actualizaciones y se agrega un nuevo paquete de analizador.</span><span class="sxs-lookup"><span data-stu-id="fa133-140">Several packages need updates, and a new analyzer package is added.</span></span>

:::image type="content" source="media/upgrade-assistant-aspnetmvc/update-nuget-packages.png" alt-text="Actualización de los paquetes NuGet en el Asistente para actualización de .NET":::

<span data-ttu-id="fa133-142">Una vez actualizados los paquetes, el paso siguiente consiste en agregar archivos de plantilla, si los hay.</span><span class="sxs-lookup"><span data-stu-id="fa133-142">Once the packages are updated, the next step is to add template files, if any.</span></span> <span data-ttu-id="fa133-143">La herramienta observa que hay cuatro elementos de plantilla esperados que se deben agregar y, a continuación, los agrega.</span><span class="sxs-lookup"><span data-stu-id="fa133-143">The tool notes there are four expected template items that must be added, and then adds them.</span></span> <span data-ttu-id="fa133-144">Entre ellos, se incluyen los siguientes archivos:</span><span class="sxs-lookup"><span data-stu-id="fa133-144">These include the following files:</span></span>

- `Program.cs`
- `Startup.cs`
- `appsettings.json`
- `appsettings.Development.json`

<span data-ttu-id="fa133-145">Estos archivos se usan en ASP.NET Core para el [inicio](/aspnet/core/fundamentals/startup) y la [configuración de la aplicación](/aspnet/core/fundamentals/configuration).</span><span class="sxs-lookup"><span data-stu-id="fa133-145">These files are used by ASP.NET Core for [app startup](/aspnet/core/fundamentals/startup) and [configuration](/aspnet/core/fundamentals/configuration).</span></span>

:::image type="content" source="media/upgrade-assistant-aspnetmvc/add-template-files.png" alt-text="Adición de archivos de plantilla en el Asistente para actualización de .NET":::

<span data-ttu-id="fa133-147">A continuación, la herramienta migra los archivos de configuración.</span><span class="sxs-lookup"><span data-stu-id="fa133-147">Next, the tool migrates config files.</span></span> <span data-ttu-id="fa133-148">La herramienta identifica la configuración de la aplicación, deshabilita las secciones de configuración no admitidas y, a continuación, migra los valores de configuración de `appSettings`.</span><span class="sxs-lookup"><span data-stu-id="fa133-148">The tool identifies app settings and disables unsupported configuration sections, then migrates the `appSettings` configuration values.</span></span>

:::image type="content" source="media/upgrade-assistant-aspnetmvc/migrate-config.png" alt-text="Migración de la configuración en el Asistente para actualización de .NET":::

<span data-ttu-id="fa133-150">La herramienta completa la migración de los archivos de configuración con la migración de `system.web.webPages.razor/pages/namespaces`.</span><span class="sxs-lookup"><span data-stu-id="fa133-150">The tool completes the migration of config files by migrating `system.web.webPages.razor/pages/namespaces`.</span></span>

:::image type="content" source="media/upgrade-assistant-aspnetmvc/migrate-config2.png" alt-text="Migración de la configuración del Asistente para actualización de .NET completada":::

<span data-ttu-id="fa133-152">La herramienta aplica correcciones conocidas para migrar las referencias de C# a sus nuevos homólogos.</span><span class="sxs-lookup"><span data-stu-id="fa133-152">The tool applies known fixes to migrate C# references to their new counterparts.</span></span>

:::image type="content" source="media/upgrade-assistant-aspnetmvc/update-csharp.png" alt-text="Actualización del origen de C# en el Asistente para actualización de .NET":::

<span data-ttu-id="fa133-154">Como este es el último proyecto, el paso siguiente, "Pasar al siguiente proyecto", le pide que complete el proceso de migración de toda la solución.</span><span class="sxs-lookup"><span data-stu-id="fa133-154">Since this is the last project, the next step, "Move to next project", prompts to complete the process of migrating the entire solution.</span></span>

:::image type="content" source="media/upgrade-assistant-aspnetmvc/complete-solution.png" alt-text="Compleción de la solución en el Asistente para actualización de .NET":::

<span data-ttu-id="fa133-156">Una vez completado este proceso, abra el archivo del proyecto y revíselo.</span><span class="sxs-lookup"><span data-stu-id="fa133-156">Once this process has completed, open the project file and review it.</span></span> <span data-ttu-id="fa133-157">Busque archivos estáticos como los siguientes:</span><span class="sxs-lookup"><span data-stu-id="fa133-157">Look for static files like these:</span></span>

```xml
  <ItemGroup>
    <Content Include="fonts\glyphicons-halflings-regular.woff2" />
    <Content Include="fonts\glyphicons-halflings-regular.woff" />
    <Content Include="fonts\glyphicons-halflings-regular.ttf" />
    <Content Include="fonts\glyphicons-halflings-regular.eot" />
    <Content Include="Content\bootstrap.min.css.map" />
    <Content Include="Content\bootstrap.css.map" />
    <Content Include="Content\bootstrap-theme.min.css.map" />
    <Content Include="Content\bootstrap-theme.css.map" />
    <Content Include="Scripts\jquery-3.4.1.slim.min.map" />
    <Content Include="Scripts\jquery-3.4.1.min.map" />
  </ItemGroup>
```

<span data-ttu-id="fa133-158">Los archivos estáticos que debe proporcionar el servidor web deben trasladarse a una carpeta adecuada dentro de una carpeta de nivel raíz denominada `wwwroot`.</span><span class="sxs-lookup"><span data-stu-id="fa133-158">Static files that should be served by the web server should be moved to an appropriate folder within a root level folder named `wwwroot`.</span></span> <span data-ttu-id="fa133-159">Consulte [Archivos estáticos en ASP.NET Core](/aspnet/core/fundamentals/static-files?view=aspnetcore-5.0&preserve-view=true) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="fa133-159">See [Static files in ASP.NET Core](/aspnet/core/fundamentals/static-files?view=aspnetcore-5.0&preserve-view=true) for details.</span></span> <span data-ttu-id="fa133-160">Una vez que se han trasladado los archivos, se pueden eliminar los elementos `<Content>` del archivo del proyecto correspondientes a estos archivos.</span><span class="sxs-lookup"><span data-stu-id="fa133-160">Once the files have been moved, the `<Content>` elements in the project file corresponding to these files can be deleted.</span></span> <span data-ttu-id="fa133-161">De hecho, se pueden quitar todos los elementos `<Content>` y sus grupos contenedores.</span><span class="sxs-lookup"><span data-stu-id="fa133-161">In fact, all `<Content>` elements and their containing groups can be removed.</span></span> <span data-ttu-id="fa133-162">Además, debe quitarse cualquier `<PackageReference>` en una biblioteca del lado del cliente como `bootstrap` o `jQuery`.</span><span class="sxs-lookup"><span data-stu-id="fa133-162">Also, any `<PackageReference>` to a client-side library like `bootstrap` or `jQuery` should be removed.</span></span>

<span data-ttu-id="fa133-163">De forma predeterminada, el proyecto se convertirá como una biblioteca de clases.</span><span class="sxs-lookup"><span data-stu-id="fa133-163">By default, the project will be converted as a class library.</span></span> <span data-ttu-id="fa133-164">Cambie el atributo `Sdk` de la primera línea a `Microsoft.NET.Sdk.Web` y establezca `<TargetFramework>` en `net5.0`.</span><span class="sxs-lookup"><span data-stu-id="fa133-164">Change the first line's `Sdk` attribute to `Microsoft.NET.Sdk.Web` and set the `<TargetFramework>` to `net5.0`.</span></span> <span data-ttu-id="fa133-165">Compile el proyecto.</span><span class="sxs-lookup"><span data-stu-id="fa133-165">Compile the project.</span></span> <span data-ttu-id="fa133-166">En este momento, el número de errores debería ser bastante pequeño.</span><span class="sxs-lookup"><span data-stu-id="fa133-166">At this point, the number of errors should be fairly small.</span></span> <span data-ttu-id="fa133-167">Al portar un nuevo proyecto de MVC de ASP.NET 4.6.1, los errores restantes hacen referencia a archivos de la carpeta `App_Start`:</span><span class="sxs-lookup"><span data-stu-id="fa133-167">When porting a new ASP.NET 4.6.1 MVC project, the remaining errors refer to files in the `App_Start` folder:</span></span>

- <span data-ttu-id="fa133-168">BundleConfig.cs</span><span class="sxs-lookup"><span data-stu-id="fa133-168">BundleConfig.cs</span></span>
- <span data-ttu-id="fa133-169">FilterConfig.cs</span><span class="sxs-lookup"><span data-stu-id="fa133-169">FilterConfig.cs</span></span>
- <span data-ttu-id="fa133-170">RouteConfig.cs</span><span class="sxs-lookup"><span data-stu-id="fa133-170">RouteConfig.cs</span></span>

<span data-ttu-id="fa133-171">Estos archivos (y toda la carpeta `App_Start`) se pueden eliminar.</span><span class="sxs-lookup"><span data-stu-id="fa133-171">These files - and the entire `App_Start` folder - can be deleted.</span></span> <span data-ttu-id="fa133-172">Del mismo modo, los archivos `Global.asax` y `Global.asax.cs` se pueden quitar.</span><span class="sxs-lookup"><span data-stu-id="fa133-172">Likewise, the `Global.asax` and `Global.asax.cs` files can be removed.</span></span>

<span data-ttu-id="fa133-173">En este momento, los únicos errores que quedan están relacionados con la unión.</span><span class="sxs-lookup"><span data-stu-id="fa133-173">At this point the only errors that remain are related to bundling.</span></span> <span data-ttu-id="fa133-174">Hay [varias maneras de configurar la unión y la minificación en ASP.NET Core](/aspnet/core/migration/mvc?view=aspnetcore-5.0&preserve-view=true#configure-bundling-and-minification).</span><span class="sxs-lookup"><span data-stu-id="fa133-174">There are [several ways to configure bundling and minification in ASP.NET Core](/aspnet/core/migration/mvc?view=aspnetcore-5.0&preserve-view=true#configure-bundling-and-minification).</span></span> <span data-ttu-id="fa133-175">Elija la que sea más conveniente para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="fa133-175">Choose whatever makes the most sense for your project.</span></span>

## <a name="troubleshooting-tips"></a><span data-ttu-id="fa133-176">Sugerencias de solución de problemas</span><span class="sxs-lookup"><span data-stu-id="fa133-176">Troubleshooting tips</span></span>

<span data-ttu-id="fa133-177">Hay varios problemas conocidos que pueden producirse al usar el Asistente para actualización de .NET.</span><span class="sxs-lookup"><span data-stu-id="fa133-177">There are several known problems that can occur when using the .NET Upgrade Assistant.</span></span> <span data-ttu-id="fa133-178">En algunos casos, se trata de problemas con la [herramienta try-convert](https://github.com/dotnet/try-convert) que el Asistente para actualización de .NET usa internamente.</span><span class="sxs-lookup"><span data-stu-id="fa133-178">In some cases, these are problems with the [try-convert tool](https://github.com/dotnet/try-convert) that the .NET Upgrade Assistant uses internally.</span></span> <span data-ttu-id="fa133-179">Esta herramienta se actualiza con frecuencia para abordar más escenarios, por lo que debe asegurarse de que está usando una versión reciente.</span><span class="sxs-lookup"><span data-stu-id="fa133-179">This tool is being frequently updated to address more scenarios, so make sure you're using a recent version.</span></span>

- <span data-ttu-id="fa133-180">La herramienta **try-convert** debe instalarse y actualizarse al menos a la versión _0.7.212201_.</span><span class="sxs-lookup"><span data-stu-id="fa133-180">The **try-convert** tool must be installed and updated to at least version _0.7.212201_.</span></span>
- <span data-ttu-id="fa133-181">Las versiones anteriores de la herramienta **try-convert** no admitían archivos de destino o de propiedades personalizados.</span><span class="sxs-lookup"><span data-stu-id="fa133-181">Earlier versions of the **try-convert** tool didn't support custom target or props files.</span></span> <span data-ttu-id="fa133-182">Si no puede actualizar a la versión más reciente, es posible que tenga que resolver manualmente estos problemas.</span><span class="sxs-lookup"><span data-stu-id="fa133-182">If you can't upgrade to the latest version, you may need to manually address these issues.</span></span> <span data-ttu-id="fa133-183">Si el archivo de proyecto de destino incluye referencias a destinos o archivos de propiedades personalizados, puede que sea necesario eliminar manualmente estas referencias del archivo antes de ejecutar el Asistente para actualización de .NET en él.</span><span class="sxs-lookup"><span data-stu-id="fa133-183">If the target project file includes references to custom targets or props files, these references may need to be manually deleted from the file before the .NET Upgrade Assistant is run against it.</span></span>

```xml
<Import Project="packages\Microsoft.CodeDom.Providers.DotNetCompilerPlatform.2.0.1\build\net46\Microsoft.CodeDom.Providers.DotNetCompilerPlatform.props" Condition="Exists('packages\Microsoft.CodeDom.Providers.DotNetCompilerPlatform.2.0.1\build\net46\Microsoft.CodeDom.Providers.DotNetCompilerPlatform.props')" />
```

<span data-ttu-id="fa133-184">[El repositorio de GitHub de la herramienta](https://github.com/dotnet/upgrade-assistant#troubleshooting-common-issues) contiene más sugerencias para la solución de problemas y problemas conocidos.</span><span class="sxs-lookup"><span data-stu-id="fa133-184">[The tool's GitHub repository](https://github.com/dotnet/upgrade-assistant#troubleshooting-common-issues) has more troubleshooting tips and known issues.</span></span>

## <a name="see-also"></a><span data-ttu-id="fa133-185">Vea también</span><span class="sxs-lookup"><span data-stu-id="fa133-185">See also</span></span>

- [<span data-ttu-id="fa133-186">Actualización de una aplicación de WPF a .NET 5 con el Asistente para actualización de .NET</span><span class="sxs-lookup"><span data-stu-id="fa133-186">Upgrade a WPF App to .NET 5 with the .NET Upgrade Assistant</span></span>](upgrade-assistant-wpf-framework.md)
- [<span data-ttu-id="fa133-187">Actualización de una aplicación de Windows Forms a .NET 5 con el Asistente para actualización de .NET</span><span class="sxs-lookup"><span data-stu-id="fa133-187">Upgrade a Windows Forms App to .NET 5 with the .NET Upgrade Assistant</span></span>](upgrade-assistant-winforms-framework.md)
- [<span data-ttu-id="fa133-188">Información general sobre el Asistente para actualización de .NET</span><span class="sxs-lookup"><span data-stu-id="fa133-188">Overview of the .NET Upgrade Assistant</span></span>](upgrade-assistant-overview.md)
- [<span data-ttu-id="fa133-189">Repositorio de GitHub del Asistente para actualización de .NET</span><span class="sxs-lookup"><span data-stu-id="fa133-189">.NET Upgrade Assistant GitHub Repository</span></span>](https://github.com/dotnet/upgrade-assistant)
