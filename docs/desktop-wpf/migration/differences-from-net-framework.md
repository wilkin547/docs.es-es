---
title: Diferencias entre .NET Framework y .NET Core
description: Describe las diferencias entre la implementación de .NET Framework de Windows Presentation Foundation (WPF) y .NET Core WPF. Al migrar la aplicación, debe tener en cuenta estas incompatibilidades.
author: thraka
ms.date: 09/21/2019
ms.author: adegeo
ms.openlocfilehash: 4386654aad205e3c9f2cbd986d7b812e261e737f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "81433137"
---
# <a name="differences-in-wpf"></a><span data-ttu-id="ceaff-104">Diferencias en WPF</span><span class="sxs-lookup"><span data-stu-id="ceaff-104">Differences in WPF</span></span>

<span data-ttu-id="ceaff-105">En este artículo se describen las diferencias entre Windows Presentation Foundation (WPF) en .NET Core y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ceaff-105">This article describes the differences between Windows Presentation Foundation (WPF) on .NET Core and .NET Framework.</span></span> <span data-ttu-id="ceaff-106">WPF para .NET Core es un marco de [código abierto](https://github.com/dotnet/wpf) bifurcado desde el código fuente original de WPF para .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ceaff-106">WPF for .NET Core is an [open-source framework](https://github.com/dotnet/wpf) forked from the original WPF for .NET Framework source code.</span></span>

<span data-ttu-id="ceaff-107">Hay algunas características de .NET Framework que .NET Core no admite.</span><span class="sxs-lookup"><span data-stu-id="ceaff-107">There are a few features of .NET Framework that .NET Core doesn't support.</span></span> <span data-ttu-id="ceaff-108">Para obtener más información sobre tecnologías no admitidas, vea Tecnologías de [.NET Framework no disponibles en .NET Core](../../core/porting/net-framework-tech-unavailable.md).</span><span class="sxs-lookup"><span data-stu-id="ceaff-108">For more information on unsupported technologies, see [.NET Framework technologies unavailable on .NET Core](../../core/porting/net-framework-tech-unavailable.md).</span></span>

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

## <a name="sdk-style-projects"></a><span data-ttu-id="ceaff-109">Proyectos al estilo SDK</span><span class="sxs-lookup"><span data-stu-id="ceaff-109">SDK-style projects</span></span>

<span data-ttu-id="ceaff-110">.NET Core usa archivos de proyecto de estilo SDK.</span><span class="sxs-lookup"><span data-stu-id="ceaff-110">.NET Core uses SDK-style project files.</span></span> <span data-ttu-id="ceaff-111">Estos archivos de proyecto son diferentes de los archivos de proyecto tradicionales de .NET Framework administrados por Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ceaff-111">These project files are different from the traditional .NET Framework project files managed by Visual Studio.</span></span> <span data-ttu-id="ceaff-112">Para migrar las aplicaciones WPF de .NET Framework a .NET Core, debe convertir los proyectos.</span><span class="sxs-lookup"><span data-stu-id="ceaff-112">To migrate your .NET Framework WPF apps to .NET Core, you must convert your projects.</span></span> <span data-ttu-id="ceaff-113">Para obtener más información, vea [Migrar aplicaciones WPF a .NET Core 3.0](convert-project-from-net-framework.md).</span><span class="sxs-lookup"><span data-stu-id="ceaff-113">For more information, see [Migrate WPF apps to .NET Core 3.0](convert-project-from-net-framework.md).</span></span>

## <a name="nuget-package-references"></a><span data-ttu-id="ceaff-114">Referencias de paquetes de NuGet</span><span class="sxs-lookup"><span data-stu-id="ceaff-114">NuGet package references</span></span>

<span data-ttu-id="ceaff-115">Si la aplicación .NET Framework enumera sus dependencias NuGet en [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files) un archivo *packages.config,* migre al formato:</span><span class="sxs-lookup"><span data-stu-id="ceaff-115">If your .NET Framework app lists its NuGet dependencies in a *packages.config* file, migrate to the [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files) format:</span></span>

1. <span data-ttu-id="ceaff-116">En Visual Studio, abra el **panel Explorador de soluciones.**</span><span class="sxs-lookup"><span data-stu-id="ceaff-116">In Visual Studio, open the **Solution Explorer** pane.</span></span>
1. <span data-ttu-id="ceaff-117">En el proyecto WPF, haga clic con el botón secundario en **packages.config** > **Migrate packages.config a PackageReference**.</span><span class="sxs-lookup"><span data-stu-id="ceaff-117">In your WPF project, right-click **packages.config** > **Migrate packages.config to PackageReference**.</span></span>

![Actualización a PackageReference](media/differences-from-net-framework/package-reference-migration.png)

<span data-ttu-id="ceaff-119">Aparecerá un cuadro de diálogo que muestra las dependencias NuGet calculadas de nivel superior y que pregunta qué otros paquetes NuGet se deben promocionar al nivel superior.</span><span class="sxs-lookup"><span data-stu-id="ceaff-119">A dialog will appear showing calculated top-level NuGet dependencies and asking which other NuGet packages should be promoted to top level.</span></span> <span data-ttu-id="ceaff-120">Seleccione **Aceptar** y el archivo *packages.config* se `<PackageReference>` quitará del proyecto y los elementos se agregarán al archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="ceaff-120">Select **OK** and the *packages.config* file will be removed from the project and `<PackageReference>` elements will be added to the project file.</span></span>

<span data-ttu-id="ceaff-121">Cuando el `<PackageReference>`proyecto usa , los paquetes no se almacenan localmente en una carpeta *Packages,* se almacenan globalmente.</span><span class="sxs-lookup"><span data-stu-id="ceaff-121">When your project uses `<PackageReference>`, packages aren't stored locally in a *Packages* folder, they're stored globally.</span></span> <span data-ttu-id="ceaff-122">Abra el archivo de `<Analyzer>` proyecto y quite los elementos que hace referencia a la carpeta *Paquetes.*</span><span class="sxs-lookup"><span data-stu-id="ceaff-122">Open the project file and remove any `<Analyzer>` elements that referred to the *Packages* folder.</span></span> <span data-ttu-id="ceaff-123">Estos analizadores se incluyen automáticamente con las referencias de paquete NuGet.</span><span class="sxs-lookup"><span data-stu-id="ceaff-123">These analyzers are automatically included with the NuGet package references.</span></span>

## <a name="code-access-security"></a><span data-ttu-id="ceaff-124">Seguridad de acceso del código</span><span class="sxs-lookup"><span data-stu-id="ceaff-124">Code Access Security</span></span>

<span data-ttu-id="ceaff-125">.NET Core o WPF para .NET Core no admiten la seguridad de acceso de código (CAS).</span><span class="sxs-lookup"><span data-stu-id="ceaff-125">Code Access Security (CAS) is not supported by .NET Core or WPF for .NET Core.</span></span> <span data-ttu-id="ceaff-126">Todas las funciones relacionadas con CAS se tratan bajo la suposición de plena confianza.</span><span class="sxs-lookup"><span data-stu-id="ceaff-126">All CAS-related functionality is treated under the assumption of full-trust.</span></span> <span data-ttu-id="ceaff-127">WPF para .NET Core quita el código relacionado con CAS.</span><span class="sxs-lookup"><span data-stu-id="ceaff-127">WPF for .NET Core removes CAS-related code.</span></span> <span data-ttu-id="ceaff-128">La superficie de API pública de estos tipos todavía existe para garantizar que las llamadas a estos tipos se realicen correctamente.</span><span class="sxs-lookup"><span data-stu-id="ceaff-128">The public API surface of these types still exists to ensure that calls into these types succeed.</span></span>

<span data-ttu-id="ceaff-129">Los tipos relacionados con CAS definidos públicamente se movieron fuera de los ensamblados WPFWPF y en los ensamblados CoreFX.</span><span class="sxs-lookup"><span data-stu-id="ceaff-129">Publicly defined CAS-related types were moved out of the WPF assemblies and into the CoreFX assemblies.</span></span> <span data-ttu-id="ceaff-130">Los ensamblados de WPFWPF tienen el acceso a tipos establecido en la nueva ubicación de los tipos movidos.</span><span class="sxs-lookup"><span data-stu-id="ceaff-130">The WPF assemblies have type-forwarding set to the new location of the moved types.</span></span>

| <span data-ttu-id="ceaff-131">Ensamblaje de origen</span><span class="sxs-lookup"><span data-stu-id="ceaff-131">Source assembly</span></span> | <span data-ttu-id="ceaff-132">Ensamblaje de destino</span><span class="sxs-lookup"><span data-stu-id="ceaff-132">Target assembly</span></span> | <span data-ttu-id="ceaff-133">Tipo</span><span class="sxs-lookup"><span data-stu-id="ceaff-133">Type</span></span>                |
| --------------- | --------------- | ------------------- |
| <span data-ttu-id="ceaff-134">*WindowsBase.dll*</span><span class="sxs-lookup"><span data-stu-id="ceaff-134">*WindowsBase.dll*</span></span> | <span data-ttu-id="ceaff-135">*System.Security.Permissions.dll*</span><span class="sxs-lookup"><span data-stu-id="ceaff-135">*System.Security.Permissions.dll*</span></span> | <xref:System.Security.Permissions.MediaPermission> <br /> <xref:System.Security.Permissions.MediaPermissionAttribute> <br /> <xref:System.Security.Permissions.MediaPermissionAudio> <br /> <xref:System.Security.Permissions.MediaPermissionImage> <br /> <xref:System.Security.Permissions.MediaPermissionVideo> <br /> <xref:System.Security.Permissions.WebBrowserPermission> <br /> <xref:System.Security.Permissions.WebBrowserPermissionAttribute> <br /> <xref:System.Security.Permissions.WebBrowserPermissionLevel> |
| <span data-ttu-id="ceaff-136">*System.Xaml.dll*</span><span class="sxs-lookup"><span data-stu-id="ceaff-136">*System.Xaml.dll*</span></span> | <span data-ttu-id="ceaff-137">*System.Security.Permissions.dll*</span><span class="sxs-lookup"><span data-stu-id="ceaff-137">*System.Security.Permissions.dll*</span></span> | <xref:System.Xaml.Permissions.XamlLoadPermission> |
| <span data-ttu-id="ceaff-138">*System.Xaml.dll*</span><span class="sxs-lookup"><span data-stu-id="ceaff-138">*System.Xaml.dll*</span></span> | <span data-ttu-id="ceaff-139">*System.Windows.Extension.dll*</span><span class="sxs-lookup"><span data-stu-id="ceaff-139">*System.Windows.Extension.dll*</span></span>    | <xref:System.Xaml.Permissions.XamlAccessLevel><br/> |

> [!NOTE]
> <span data-ttu-id="ceaff-140">Para minimizar la fricción de portabilidad, se retuvo la funcionalidad para almacenar `XamlAccessLevel` y recuperar información relacionada con las siguientes propiedades en el tipo.</span><span class="sxs-lookup"><span data-stu-id="ceaff-140">In order to minimize porting friction, the functionality for storing and retrieving information related to the following properties was retained in the `XamlAccessLevel` type.</span></span>
>
> - `PrivateAccessToTypeName`
> - `AssemblyNameString`

## <a name="next-steps"></a><span data-ttu-id="ceaff-141">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="ceaff-141">Next steps</span></span>

- [<span data-ttu-id="ceaff-142">Aprenda a migrar una aplicación WPF de .NET Framework a .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ceaff-142">Learn how to port a .NET Framework WPF app to .NET Core.</span></span>](convert-project-from-net-framework.md)
