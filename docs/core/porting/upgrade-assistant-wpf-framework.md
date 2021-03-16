---
title: Actualización de las aplicaciones de WPF a .NET 5
description: Use el Asistente para actualización de .NET para actualizar una aplicación .NET Framework de WPF existente a .NET 5. El Asistente para actualización de .NET es una herramienta de la CLI que ayuda a migrar una aplicación de .NET Framework a .NET 5.
author: ardalis
ms.date: 02/25/2021
ms.openlocfilehash: e71cdc0ef5b72fcb7ae3985a26672e23ed0c1f12
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102108296"
---
# <a name="upgrade-a-wpf-app-to-net-5-with-the-net-upgrade-assistant"></a><span data-ttu-id="2c087-104">Actualización de una aplicación de WPF a .NET 5 con el Asistente para actualización de .NET</span><span class="sxs-lookup"><span data-stu-id="2c087-104">Upgrade a WPF App to .NET 5 with the .NET Upgrade Assistant</span></span>

<span data-ttu-id="2c087-105">El [Asistente para actualización de .NET](upgrade-assistant-overview.md) es una herramienta de la línea de comandos que puede ayudar en la actualización de aplicaciones .NET Framework de WPF a .NET 5.</span><span class="sxs-lookup"><span data-stu-id="2c087-105">The [.NET Upgrade Assistant](upgrade-assistant-overview.md) is a command-line tool that can assist with upgrading .NET Framework WPF apps to .NET 5.</span></span> <span data-ttu-id="2c087-106">En este artículo se proporciona:</span><span class="sxs-lookup"><span data-stu-id="2c087-106">This article provides:</span></span>

* <span data-ttu-id="2c087-107">Demostración de cómo se ejecuta la herramienta en una aplicación .NET Framework de WPF</span><span class="sxs-lookup"><span data-stu-id="2c087-107">A demonstration of how to run the tool against a .NET Framework WPF app</span></span>
* <span data-ttu-id="2c087-108">Sugerencias de solución de problemas</span><span class="sxs-lookup"><span data-stu-id="2c087-108">Troubleshooting tips</span></span>

## <a name="upgrade-net-framework-wpf-apps"></a><span data-ttu-id="2c087-109">Actualización de aplicaciones .NET Framework de WPF</span><span class="sxs-lookup"><span data-stu-id="2c087-109">Upgrade .NET Framework WPF apps</span></span>

<span data-ttu-id="2c087-110">En esta sección se muestra cómo ejecutar el Asistente para actualización de .NET en una aplicación de WPF recién creada para .NET Framework 4.6.1.</span><span class="sxs-lookup"><span data-stu-id="2c087-110">This section demonstrates running the .NET Upgrade Assistant against a newly created WPF app targeting .NET Framework 4.6.1.</span></span> <span data-ttu-id="2c087-111">Para obtener más información sobre cómo instalar la herramienta, consulte [Información general del Asistente para actualización de .NET](upgrade-assistant-overview.md).</span><span class="sxs-lookup"><span data-stu-id="2c087-111">For more information on how to install the tool, see [Overview of the .NET Upgrade Assistant](upgrade-assistant-overview.md).</span></span>

### <a name="initial-demo-setup"></a><span data-ttu-id="2c087-112">Configuración inicial de demo</span><span class="sxs-lookup"><span data-stu-id="2c087-112">Initial demo setup</span></span>

<span data-ttu-id="2c087-113">Si está ejecutando el Asistente para actualización de .NET en su propia aplicación .NET Framework, puede omitir este paso.</span><span class="sxs-lookup"><span data-stu-id="2c087-113">If you're running the .NET Upgrade Assistant against your own .NET Framework app, you can skip this step.</span></span> <span data-ttu-id="2c087-114">Si solo desea probarlo para ver cómo funciona, este paso le muestra cómo configurar un proyecto .NET de WPF de ejemplo para usarlo.</span><span class="sxs-lookup"><span data-stu-id="2c087-114">If you just want to try it out to see how it works, this step shows you how to set up a sample .NET WPF project to use.</span></span>

<span data-ttu-id="2c087-115">Con Visual Studio, cree una nueva aplicación de WPF con .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2c087-115">Using Visual Studio, create a new WPF App using .NET Framework.</span></span>

:::image type="content" source="media/upgrade-assistant-wpf-framework/new-project.png" alt-text="Nuevo proyecto de WPF en Visual Studio":::

<span data-ttu-id="2c087-117">Asigne el nombre **WpfTest** al proyecto.</span><span class="sxs-lookup"><span data-stu-id="2c087-117">Name the project **WpfTest**.</span></span> <span data-ttu-id="2c087-118">Configure el proyecto para usar **.NET Framework 4.6.1**.</span><span class="sxs-lookup"><span data-stu-id="2c087-118">Configure the project to use **.NET Framework 4.6.1**.</span></span>

:::image type="content" source="media/upgrade-assistant-wpf-framework/configure-project.png" alt-text="Configuración del proyecto de Windows Forms en Visual Studio":::

<span data-ttu-id="2c087-120">Revise el proyecto creado y sus archivos, especialmente los archivos de proyecto.</span><span class="sxs-lookup"><span data-stu-id="2c087-120">Review the created project and its files, especially its project file(s).</span></span>

### <a name="run-upgrade-assistant"></a><span data-ttu-id="2c087-121">Ejecución del asistente para actualización</span><span class="sxs-lookup"><span data-stu-id="2c087-121">Run upgrade-assistant</span></span>

<span data-ttu-id="2c087-122">Abra un terminal y desplácese hasta la carpeta en la que se encuentra el proyecto o la solución de destino.</span><span class="sxs-lookup"><span data-stu-id="2c087-122">Open a terminal and navigate to the folder where the target project or solution is located.</span></span> <span data-ttu-id="2c087-123">Ejecute el comando `upgrade-assistant`, pasando el nombre del proyecto de destino (puede ejecutar el comando desde cualquier lugar, siempre que la ruta de acceso al archivo de proyecto sea válida).</span><span class="sxs-lookup"><span data-stu-id="2c087-123">Run the `upgrade-assistant` command, passing in the name of the project you're targeting (you can run the command from anywhere, as long as the path to the project file is valid).</span></span>

```console
upgrade-assistant .\WpfTest.csproj
```

<span data-ttu-id="2c087-124">La herramienta se ejecuta y muestra una lista de los pasos que realizará.</span><span class="sxs-lookup"><span data-stu-id="2c087-124">The tool runs and shows you a list of the steps it will do.</span></span>

:::image type="content" source="media/upgrade-assistant-wpf-framework/initial-run.png" alt-text="Pantalla inicial del Asistente para actualización de .NET":::

<span data-ttu-id="2c087-126">A medida que se completa cada paso, la herramienta proporciona un conjunto de comandos que permiten al usuario aplicar u omitir el paso siguiente, consultar más detalles, configurar el registro o salir del proceso.</span><span class="sxs-lookup"><span data-stu-id="2c087-126">As each step is completed, the tool provides a set of commands allowing the user to apply or skip the next step, see more details, configure logging, or exit the process.</span></span> <span data-ttu-id="2c087-127">Si la herramienta detecta que un paso no realizará ninguna acción, omitirá automáticamente ese paso y continuará al paso siguiente hasta que llegue a uno que tenga acciones por realizar.</span><span class="sxs-lookup"><span data-stu-id="2c087-127">If the tool detects that a step will perform no actions, it will automatically skip that step and continue to the next step until it reaches one that will have actions to perform.</span></span> <span data-ttu-id="2c087-128">Al presionar Entrar, se realizará el siguiente paso si no se realiza ninguna otra selección.</span><span class="sxs-lookup"><span data-stu-id="2c087-128">Pressing enter will perform the next step if no other selection is made.</span></span>

<span data-ttu-id="2c087-129">En este ejemplo, cada vez se elige el paso Aplicar.</span><span class="sxs-lookup"><span data-stu-id="2c087-129">In this example, the apply step is chosen each time.</span></span> <span data-ttu-id="2c087-130">El primer paso es realizar una copia de seguridad del proyecto.</span><span class="sxs-lookup"><span data-stu-id="2c087-130">The first step is to back up the project.</span></span>

:::image type="content" source="media/upgrade-assistant-wpf-framework/backup-project.png" alt-text="Copia de seguridad del proyecto en el Asistente para actualización de .NET":::

<span data-ttu-id="2c087-132">La herramienta solicita una ruta de acceso personalizada para la copia de seguridad o bien usar el valor predeterminado, que colocará la copia de seguridad del proyecto en la misma carpeta con una extensión `.backup`.</span><span class="sxs-lookup"><span data-stu-id="2c087-132">The tool prompts for a custom path for the backup, or to use the default, which will place the project backup in the same folder with a `.backup` extension.</span></span> <span data-ttu-id="2c087-133">El siguiente paso que realiza la herramienta es convertir el archivo de proyecto al estilo SDK.</span><span class="sxs-lookup"><span data-stu-id="2c087-133">The next step the tool performs is to convert the project file to SDK style.</span></span>

:::image type="content" source="media/upgrade-assistant-wpf-framework/convert-project.png" alt-text="Conversión del proyecto al estilo SDK en el Asistente para actualización de .NET":::

<span data-ttu-id="2c087-135">Una vez actualizado el formato del proyecto, el paso siguiente es actualizar el TFM del proyecto.</span><span class="sxs-lookup"><span data-stu-id="2c087-135">Once the project format has been updated, the next step is to update the TFM of the project.</span></span>

:::image type="content" source="media/upgrade-assistant-wpf-framework/update-tfm.png" alt-text="Conversión del proyecto al estilo SDK en el Asistente para actualización de .NET":::

<span data-ttu-id="2c087-137">A continuación, la herramienta actualiza los paquetes NuGet del proyecto.</span><span class="sxs-lookup"><span data-stu-id="2c087-137">Next, the tool updates the project's NuGet packages.</span></span>

:::image type="content" source="media/upgrade-assistant-wpf-framework/update-nuget-packages.png" alt-text="Actualización de los paquetes NuGet en el Asistente para actualización de .NET":::

<span data-ttu-id="2c087-139">Una vez actualizados los paquetes, el paso siguiente consiste en agregar archivos de plantilla, si los hay.</span><span class="sxs-lookup"><span data-stu-id="2c087-139">Once the packages are updated, the next step is to add template files, if any.</span></span> <span data-ttu-id="2c087-140">En este caso, no hay ningún archivo de plantilla que deba agregarse.</span><span class="sxs-lookup"><span data-stu-id="2c087-140">In this case, there are no template files that need to be added.</span></span> <span data-ttu-id="2c087-141">Este paso continúa y migra los archivos de configuración de la aplicación y actualiza el origen de C# para aplicar correcciones, como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="2c087-141">This step continues and migrates app config files and updates C# source to apply fixes, as shown below.</span></span> <span data-ttu-id="2c087-142">Este proyecto no necesitaba ningún archivo de configuración ni cambios de código fuente, por lo que estos pasos se realizaron automáticamente.</span><span class="sxs-lookup"><span data-stu-id="2c087-142">This project didn't need any config file or source code changes, so these steps proceeded automatically.</span></span>

:::image type="content" source="media/upgrade-assistant-wpf-framework/add-template-files.png" alt-text="Adición de archivos de plantilla y migración de la configuración en el Asistente para actualización de .NET":::

<span data-ttu-id="2c087-144">Como este es el último proyecto, el paso siguiente, "Pasar al siguiente proyecto", le pide que complete el proceso de migración de toda la solución.</span><span class="sxs-lookup"><span data-stu-id="2c087-144">Since this is the last project, the next step, "Move to next project", prompts to complete the process of migrating the entire solution.</span></span>

:::image type="content" source="media/upgrade-assistant-wpf-framework/complete-solution.png" alt-text="Compleción de la solución en el Asistente para actualización de .NET":::

<span data-ttu-id="2c087-146">Una vez completado este proceso, el proyecto de WPF migrado tendrá un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="2c087-146">Once this process has completed, the migrated WPF project will look something like this:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>net5.0-windows</TargetFramework>
    <OutputType>WinExe</OutputType>
    <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
    <UseWPF>true</UseWPF>
  </PropertyGroup>
  <ItemGroup>
    <PackageReference Include="Microsoft.CSharp" Version="4.7.0" />
    <PackageReference Include="Microsoft.DotNet.UpgradeAssistant.Extensions.Default.Analyzers" Version="0.2.211942">
      <PrivateAssets>all</PrivateAssets>
    </PackageReference>
    <PackageReference Include="Microsoft.Windows.Compatibility" Version="5.0.2" />
  </ItemGroup>
</Project>
```

<span data-ttu-id="2c087-147">Tenga en cuenta que el Asistente para actualización de .NET también agrega analizadores al proyecto que ayudan a continuar el proceso de actualización.</span><span class="sxs-lookup"><span data-stu-id="2c087-147">Notice that the .NET Upgrade Assistant also adds analyzers to the project that assist with continuing the upgrade process.</span></span>

## <a name="troubleshooting-tips"></a><span data-ttu-id="2c087-148">Sugerencias de solución de problemas</span><span class="sxs-lookup"><span data-stu-id="2c087-148">Troubleshooting tips</span></span>

<span data-ttu-id="2c087-149">Hay varios problemas conocidos que pueden producirse al usar el Asistente para actualización de .NET.</span><span class="sxs-lookup"><span data-stu-id="2c087-149">There are several known problems that can occur when using the .NET Upgrade Assistant.</span></span> <span data-ttu-id="2c087-150">En algunos casos, se trata de problemas con la [herramienta try-convert](https://github.com/dotnet/try-convert) que el Asistente para actualización de .NET usa internamente.</span><span class="sxs-lookup"><span data-stu-id="2c087-150">In some cases, these are problems with the [try-convert tool](https://github.com/dotnet/try-convert) that the .NET Upgrade Assistant uses internally.</span></span> <span data-ttu-id="2c087-151">Esta herramienta se actualiza con frecuencia para abordar más escenarios, por lo que debe asegurarse de que está usando una versión reciente.</span><span class="sxs-lookup"><span data-stu-id="2c087-151">This tool is being frequently updated to address more scenarios, so make sure you're using a recent version.</span></span>

- <span data-ttu-id="2c087-152">La herramienta try-convert debe instalarse y actualizarse al menos a la versión _0.7.21201_.</span><span class="sxs-lookup"><span data-stu-id="2c087-152">The try-convert tool must be installed and updated to at least version _0.7.21201_.</span></span>
- <span data-ttu-id="2c087-153">Las versiones anteriores de la herramienta try-convert no admitían archivos de destino o de propiedades personalizados.</span><span class="sxs-lookup"><span data-stu-id="2c087-153">Earlier versions of the try-convert tool didn't support custom target or props files.</span></span> <span data-ttu-id="2c087-154">Si no puede actualizar a la versión más reciente, es posible que tenga que resolver manualmente estos problemas.</span><span class="sxs-lookup"><span data-stu-id="2c087-154">If you can't upgrade to the latest version, you may need to manually address these issues.</span></span> <span data-ttu-id="2c087-155">Si el archivo de proyecto de destino incluye referencias a destinos o archivos de propiedades personalizados, puede que sea necesario eliminar manualmente estas referencias del archivo antes de ejecutar el Asistente para actualización de .NET en él.</span><span class="sxs-lookup"><span data-stu-id="2c087-155">If the target project file includes references to custom targets or props files, these references may need to be manually deleted from the file before the .NET Upgrade Assistant is run against it.</span></span>

<span data-ttu-id="2c087-156">[El repositorio de GitHub de la herramienta](https://github.com/dotnet/upgrade-assistant#troubleshooting-common-issues) contiene más sugerencias para la solución de problemas y problemas conocidos.</span><span class="sxs-lookup"><span data-stu-id="2c087-156">[The tool's GitHub repository](https://github.com/dotnet/upgrade-assistant#troubleshooting-common-issues) has more troubleshooting tips and known issues.</span></span>

## <a name="see-also"></a><span data-ttu-id="2c087-157">Vea también</span><span class="sxs-lookup"><span data-stu-id="2c087-157">See also</span></span>

- [<span data-ttu-id="2c087-158">Actualización de una aplicación de Windows Forms a .NET 5 con el Asistente para actualización de .NET</span><span class="sxs-lookup"><span data-stu-id="2c087-158">Upgrade a Windows Forms App to .NET 5 with the .NET Upgrade Assistant</span></span>](upgrade-assistant-winforms-framework.md)
- [<span data-ttu-id="2c087-159">Actualización de una aplicación ASP.NET de MVC a .NET 5 con el Asistente para actualización de .NET</span><span class="sxs-lookup"><span data-stu-id="2c087-159">Upgrade an ASP.NET MVC App to .NET 5 with the .NET Upgrade Assistant</span></span>](upgrade-assistant-aspnetmvc.md)
- [<span data-ttu-id="2c087-160">Información general sobre el Asistente para actualización de .NET</span><span class="sxs-lookup"><span data-stu-id="2c087-160">Overview of the .NET Upgrade Assistant</span></span>](upgrade-assistant-overview.md)
- [<span data-ttu-id="2c087-161">Repositorio de GitHub del Asistente para actualización de .NET</span><span class="sxs-lookup"><span data-stu-id="2c087-161">.NET Upgrade Assistant GitHub Repository</span></span>](https://github.com/dotnet/upgrade-assistant)
