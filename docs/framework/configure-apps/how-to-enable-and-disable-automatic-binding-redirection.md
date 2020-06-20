---
title: Habilitar o deshabilitar las redirecciones de enlace generadas automáticamente
description: Lea cómo habilitar o deshabilitar la redirección de enlace automática. Esta característica afecta a las aplicaciones de escritorio y Web Apps que tienen como destino .NET 4.5.1 o posterior.
ms.date: 10/30/2018
helpviewer_keywords:
- side-by-side execution, assembly binding redirection
- assemblies [.NET Framework], binding redirection
ms.assetid: 5fca42f3-bdce-4b81-a704-61e42c89d3ba
ms.openlocfilehash: edee95f6c3b2c2d74c4f1b68e0a65e5cb0e85f54
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2020
ms.locfileid: "85105388"
---
# <a name="how-to-enable-and-disable-automatic-binding-redirection"></a><span data-ttu-id="9e325-104">Procedimiento para habilitar y deshabilitar redireccionamiento de enlaces automático</span><span class="sxs-lookup"><span data-stu-id="9e325-104">How to: Enable and Disable Automatic Binding Redirection</span></span>

<span data-ttu-id="9e325-105">Al compilar aplicaciones en Visual Studio que tienen como destino la .NET Framework 4.5.1 y versiones posteriores, se pueden agregar automáticamente redirecciones de enlace al archivo de configuración de la aplicación para invalidar la unificación de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="9e325-105">When you compile apps in Visual Studio that target the .NET Framework 4.5.1 and later versions, binding redirects may be automatically added to the app configuration file to override assembly unification.</span></span> <span data-ttu-id="9e325-106">Las redirecciones de enlace se agregan si la aplicación o sus componentes hacen referencia a más de una versión del mismo ensamblado, incluso si se especifican manualmente las redirecciones de enlace en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="9e325-106">Binding redirects are added if your app or its components reference more than one version of the same assembly, even if you manually specify binding redirects in the configuration file for your app.</span></span> <span data-ttu-id="9e325-107">La característica de redirección de enlace automática afecta a las aplicaciones de escritorio y a las aplicaciones web que tienen como destino la .NET Framework 4.5.1 o una versión posterior, aunque el comportamiento es ligeramente diferente para una aplicación Web.</span><span class="sxs-lookup"><span data-stu-id="9e325-107">The automatic binding redirection feature affects desktop apps and web apps that target the .NET Framework 4.5.1 or a later version, although the behavior is slightly different for a web app.</span></span> <span data-ttu-id="9e325-108">Puede habilitar la redirección de enlace automática si tiene aplicaciones existentes destinadas a versiones anteriores de la .NET Framework, o puede deshabilitar esta característica si desea crear manualmente redirecciones de enlace.</span><span class="sxs-lookup"><span data-stu-id="9e325-108">You can enable automatic binding redirection if you have existing apps that target previous versions of the .NET Framework, or you can disable this feature if you want to manually author binding redirects.</span></span>

## <a name="disable-automatic-binding-redirects-in-desktop-apps"></a><span data-ttu-id="9e325-109">Deshabilitar las redirecciones de enlace automáticas en aplicaciones de escritorio</span><span class="sxs-lookup"><span data-stu-id="9e325-109">Disable automatic binding redirects in desktop apps</span></span>

<span data-ttu-id="9e325-110">Las redirecciones de enlace automáticas están habilitadas de forma predeterminada para las aplicaciones de escritorio de Windows destinadas a .NET Framework 4.5.1 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="9e325-110">Automatic binding redirects are enabled by default for Windows desktop apps that target the .NET Framework 4.5.1 and later versions.</span></span> <span data-ttu-id="9e325-111">Las redirecciones de enlace se agregan al archivo de configuración de salida (**app.config**) cuando se compila la aplicación e invalidan la unificación de ensamblados que, de lo contrario, podrían tener lugar.</span><span class="sxs-lookup"><span data-stu-id="9e325-111">The binding redirects are added to the output configuration (**app.config**) file when the app is compiled and override the assembly unification that might otherwise take place.</span></span> <span data-ttu-id="9e325-112">El archivo de **app.config** de origen no se ha modificado.</span><span class="sxs-lookup"><span data-stu-id="9e325-112">The source **app.config** file is not modified.</span></span> <span data-ttu-id="9e325-113">Puede deshabilitar esta característica modificando el archivo de proyecto de la aplicación o anulando la selección de una casilla en las propiedades del proyecto en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="9e325-113">You can disable this feature by modifying the project file for the app or by deselecting a checkbox in the project's properties in Visual Studio.</span></span>

### <a name="disable-through-project-properties"></a><span data-ttu-id="9e325-114">Deshabilitar a través de las propiedades del proyecto</span><span class="sxs-lookup"><span data-stu-id="9e325-114">Disable through project properties</span></span>

<span data-ttu-id="9e325-115">Si tiene Visual Studio 2017 versión 15,7 o posterior, puede deshabilitar fácilmente las redirecciones de enlace generadas automáticamente en las páginas de propiedades del proyecto.</span><span class="sxs-lookup"><span data-stu-id="9e325-115">If you have Visual Studio 2017 version 15.7 or later, you can easily disable autogenerated binding redirects in the project's property pages.</span></span>

1. <span data-ttu-id="9e325-116">Haga clic con el botón derecho en el proyecto en el **Explorador de soluciones** y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="9e325-116">Right-click the project in **Solution Explorer** and select **Properties**.</span></span>

2. <span data-ttu-id="9e325-117">En la página de la **aplicación** , desactive la opción **generar automáticamente redirecciones de enlace** .</span><span class="sxs-lookup"><span data-stu-id="9e325-117">On the **Application** page, uncheck the **Auto-generate binding redirects** option.</span></span>

3. <span data-ttu-id="9e325-118">Presione **Ctrl** + **S** para guardar el cambio.</span><span class="sxs-lookup"><span data-stu-id="9e325-118">Press **Ctrl**+**S** to save the change.</span></span>

### <a name="disable-manually-in-the-project-file"></a><span data-ttu-id="9e325-119">Deshabilitar manualmente en el archivo de proyecto</span><span class="sxs-lookup"><span data-stu-id="9e325-119">Disable manually in the project file</span></span>

1. <span data-ttu-id="9e325-120">Abra el archivo de proyecto para editarlo con uno de los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="9e325-120">Open the project file for editing using one of the following methods:</span></span>

   - <span data-ttu-id="9e325-121">En Visual Studio, seleccione el proyecto en **Explorador de soluciones**y, a continuación, elija **Abrir carpeta en el explorador de archivos** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="9e325-121">In Visual Studio, select the project in **Solution Explorer**, and then choose **Open Folder in File Explorer** from the shortcut menu.</span></span> <span data-ttu-id="9e325-122">En el explorador de archivos, busque el archivo de proyecto (. csproj o. vbproj) y ábralo en el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="9e325-122">In File Explorer, find the project (.csproj or .vbproj) file and open it in Notepad.</span></span>
   - <span data-ttu-id="9e325-123">En Visual Studio, en **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y elija **descargar el proyecto**.</span><span class="sxs-lookup"><span data-stu-id="9e325-123">In Visual Studio, in **Solution Explorer**, right-click the project and choose **Unload Project**.</span></span> <span data-ttu-id="9e325-124">Vuelva a hacer clic con el botón derecho en el proyecto descargado y, a continuación, elija **Editar [nombreDeProyecto. csproj]**.</span><span class="sxs-lookup"><span data-stu-id="9e325-124">Right-click the unloaded project again, and then choose **Edit [projectname.csproj]**.</span></span>

2. <span data-ttu-id="9e325-125">En el archivo de proyecto, busque la siguiente entrada de propiedad:</span><span class="sxs-lookup"><span data-stu-id="9e325-125">In the project file, find the following property entry:</span></span>

   ```xml
   <AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>
   ```

3. <span data-ttu-id="9e325-126">Cambie `true` a `false`:</span><span class="sxs-lookup"><span data-stu-id="9e325-126">Change `true` to `false`:</span></span>

   ```xml
   <AutoGenerateBindingRedirects>false</AutoGenerateBindingRedirects>
   ```

## <a name="enable-automatic-binding-redirects-manually"></a><span data-ttu-id="9e325-127">Habilitar las redirecciones de enlace automáticas manualmente</span><span class="sxs-lookup"><span data-stu-id="9e325-127">Enable automatic binding redirects manually</span></span>

<span data-ttu-id="9e325-128">Puede habilitar las redirecciones de enlace automáticas en las aplicaciones existentes destinadas a versiones anteriores de la .NET Framework o en los casos en los que no se le pide automáticamente que agregue una redirección.</span><span class="sxs-lookup"><span data-stu-id="9e325-128">You can enable automatic binding redirects in existing apps that target older versions of the .NET Framework, or in cases where you're not automatically prompted to add a redirect.</span></span> <span data-ttu-id="9e325-129">Si va a tener como destino una versión más reciente del marco pero no se le pide automáticamente que agregue una redirección, es probable que obtenga una salida de la compilación que sugiere que se reasignen los ensamblados.</span><span class="sxs-lookup"><span data-stu-id="9e325-129">If you're targeting a newer version of the framework but do not get automatically prompted to add a redirect, you'll likely get build output that suggests you remap assemblies.</span></span>

1. <span data-ttu-id="9e325-130">Abra el archivo de proyecto para editarlo con uno de los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="9e325-130">Open the project file for editing using one of the following methods:</span></span>

   - <span data-ttu-id="9e325-131">En Visual Studio, seleccione el proyecto en **Explorador de soluciones**y, a continuación, elija **Abrir carpeta en el explorador de archivos** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="9e325-131">In Visual Studio, select the project in **Solution Explorer**, and then choose **Open Folder in File Explorer** from the shortcut menu.</span></span> <span data-ttu-id="9e325-132">En el explorador de archivos, busque el archivo de proyecto (. csproj o. vbproj) y ábralo en el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="9e325-132">In File Explorer, find the project (.csproj or .vbproj) file and open it in Notepad.</span></span>
   - <span data-ttu-id="9e325-133">En Visual Studio, en **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y elija **descargar el proyecto**.</span><span class="sxs-lookup"><span data-stu-id="9e325-133">In Visual Studio, in **Solution Explorer**, right-click the project and choose **Unload Project**.</span></span> <span data-ttu-id="9e325-134">Vuelva a hacer clic con el botón derecho en el proyecto descargado y, a continuación, elija **Editar [nombreDeProyecto. csproj]**.</span><span class="sxs-lookup"><span data-stu-id="9e325-134">Right-click the unloaded project again, and then choose **Edit [projectname.csproj]**.</span></span>

2. <span data-ttu-id="9e325-135">Agregue el siguiente elemento al primer grupo de propiedades de configuración (bajo la \<PropertyGroup> etiqueta):</span><span class="sxs-lookup"><span data-stu-id="9e325-135">Add the following element to the first configuration property group (under the \<PropertyGroup> tag):</span></span>

   ```xml
   <AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>
   ```

   <span data-ttu-id="9e325-136">A continuación se muestra un ejemplo de archivo de proyecto con el elemento insertado:</span><span class="sxs-lookup"><span data-stu-id="9e325-136">The following shows an example project file with the element inserted:</span></span>

   ```xml
   <?xml version="1.0" encoding="utf-8"?>
   <Project ToolsVersion="12.0" DefaultTargets="Build" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
     <Import Project="$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props" Condition="Exists('$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props')" />
     <PropertyGroup>
       <Configuration Condition=" '$(Configuration)' == '' ">Debug</Configuration>
       <Platform Condition=" '$(Platform)' == '' ">AnyCPU</Platform>
       <ProjectGuid>{123334}</ProjectGuid>
       ...
       <AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>
     </PropertyGroup>
     ...
   </Project>
   ```

3. <span data-ttu-id="9e325-137">Compile la aplicación.</span><span class="sxs-lookup"><span data-stu-id="9e325-137">Compile your app.</span></span>

## <a name="enable-automatic-binding-redirects-in-web-apps"></a><span data-ttu-id="9e325-138">Habilitación de las redirecciones de enlace automáticas en Web Apps</span><span class="sxs-lookup"><span data-stu-id="9e325-138">Enable automatic binding redirects in web apps</span></span>

<span data-ttu-id="9e325-139">Las redirecciones de enlace automáticas se implementan de forma diferente para las aplicaciones web.</span><span class="sxs-lookup"><span data-stu-id="9e325-139">Automatic binding redirects are implemented differently for web apps.</span></span> <span data-ttu-id="9e325-140">Dado que el archivo de configuración de origen (**web.config**) debe modificarse para las aplicaciones Web, las redirecciones de enlace no se agregan automáticamente al archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="9e325-140">Because the source configuration (**web.config**) file must be modified for web apps, binding redirects are not automatically added to the configuration file.</span></span> <span data-ttu-id="9e325-141">Sin embargo, Visual Studio le notifica los conflictos de enlace, por lo que podrá agregar redirecciones de enlace para resolverlos.</span><span class="sxs-lookup"><span data-stu-id="9e325-141">However, Visual Studio notifies you of binding conflicts, and you can add binding redirects to resolve the conflicts.</span></span> <span data-ttu-id="9e325-142">Dado que siempre se le pide que agregue redirecciones de enlace, no necesita deshabilitar explícitamente esta característica para una aplicación Web.</span><span class="sxs-lookup"><span data-stu-id="9e325-142">Because you're always prompted to add binding redirects, you don't need to explicitly disable this feature for a web app.</span></span>

<span data-ttu-id="9e325-143">Para agregar redirecciones de enlace a un archivo **web.config** :</span><span class="sxs-lookup"><span data-stu-id="9e325-143">To add binding redirects to a **web.config** file:</span></span>

1. <span data-ttu-id="9e325-144">En Visual Studio, compile la aplicación y compruebe si hay advertencias de compilación.</span><span class="sxs-lookup"><span data-stu-id="9e325-144">In Visual Studio, compile the app, and check for build warnings.</span></span>

   <span data-ttu-id="9e325-145">![Advertencia de compilación para conflictos de referencia de ensamblado](./media/clr-assemblyrefwarning.png "CLR_AssemblyRefWarning")</span><span class="sxs-lookup"><span data-stu-id="9e325-145">![Build warning for assembly reference conflicts](./media/clr-assemblyrefwarning.png "CLR_AssemblyRefWarning")</span></span>

2. <span data-ttu-id="9e325-146">Si hay conflictos de enlace de ensamblados, se mostrará una advertencia.</span><span class="sxs-lookup"><span data-stu-id="9e325-146">If there are assembly binding conflicts, a warning appears.</span></span> <span data-ttu-id="9e325-147">Haga doble clic en la advertencia o seleccione la advertencia y presione **entrar**.</span><span class="sxs-lookup"><span data-stu-id="9e325-147">Double-click the warning, or select the warning and press **Enter**.</span></span>

   <span data-ttu-id="9e325-148">Un cuadro de diálogo que le permite agregar automáticamente las redirecciones de enlace necesarias al archivo de origen **web.config** aparece.</span><span class="sxs-lookup"><span data-stu-id="9e325-148">A dialog box that enables you to automatically add the necessary binding redirects to the source **web.config** file appears.</span></span>

   <span data-ttu-id="9e325-149">![Cuadro de diálogo de permiso de redireccionamiento de enlace](./media/clr-addbindingredirect.png "CLR_AddBindingRedirect")</span><span class="sxs-lookup"><span data-stu-id="9e325-149">![Binding redirect permission dialog](./media/clr-addbindingredirect.png "CLR_AddBindingRedirect")</span></span>

## <a name="see-also"></a><span data-ttu-id="9e325-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="9e325-150">See also</span></span>

- [<span data-ttu-id="9e325-151">Elemento \<bindingRedirect></span><span class="sxs-lookup"><span data-stu-id="9e325-151">\<bindingRedirect> Element</span></span>](./file-schema/runtime/bindingredirect-element.md)
- [<span data-ttu-id="9e325-152">Redirigir versiones de ensamblado</span><span class="sxs-lookup"><span data-stu-id="9e325-152">Redirecting Assembly Versions</span></span>](redirect-assembly-versions.md)
