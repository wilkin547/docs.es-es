---
title: Novedades de .NET Core 3.1
description: Conozca las nuevas características que se encuentran en .NET Core 3.1.
dev_langs:
- csharp
author: adegeo
ms.author: adegeo
ms.date: 12/04/2019
ms.openlocfilehash: 8d086c5c595197894e01a347f82b2c6341263fc5
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102104970"
---
# <a name="whats-new-in-net-core-31"></a><span data-ttu-id="9e857-103">Novedades de .NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="9e857-103">What's new in .NET Core 3.1</span></span>

<span data-ttu-id="9e857-104">En este artículo se describen las novedades de .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="9e857-104">This article describes what is new in .NET Core 3.1.</span></span> <span data-ttu-id="9e857-105">Esta versión contiene ligeras mejoras de .NET Core 3.0, y se centra en pequeñas correcciones, pero importantes.</span><span class="sxs-lookup"><span data-stu-id="9e857-105">This release contains minor improvements to .NET Core 3.0, focusing on small, but important, fixes.</span></span> <span data-ttu-id="9e857-106">La característica más importante sobre .NET Core 3.1 es que es una versión de [soporte técnico a largo plazo (LTS)](#long-term-support).</span><span class="sxs-lookup"><span data-stu-id="9e857-106">The most important feature about .NET Core 3.1 is that it's a [long-term support (LTS)](#long-term-support) release.</span></span>

<span data-ttu-id="9e857-107">Si usa Visual Studio 2019, tendrá que actualizar a [Visual Studio 2019, versión 16.4 o posterior](https://visualstudio.microsoft.com/downloads/) para trabajar con proyectos de .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="9e857-107">If you're using Visual Studio 2019, you must update to [Visual Studio 2019 version 16.4 or later](https://visualstudio.microsoft.com/downloads/) to work with .NET Core 3.1 projects.</span></span> <span data-ttu-id="9e857-108">Para obtener información sobre las novedades de la versión 16.4 de Visual Studio, vea [Novedades de la versión 16.4 de Visual Studio 2019](/visualstudio/releases/2019/release-notes-v16.4#whats-new-in-visual-studio-2019-version-164).</span><span class="sxs-lookup"><span data-stu-id="9e857-108">For information on what's new in Visual Studio version 16.4, see [What's New in Visual Studio 2019 version 16.4](/visualstudio/releases/2019/release-notes-v16.4#whats-new-in-visual-studio-2019-version-164).</span></span>

<span data-ttu-id="9e857-109">Visual Studio para Mac también admite e incluye .NET Core 3.1 en Visual Studio para Mac 8.4.</span><span class="sxs-lookup"><span data-stu-id="9e857-109">Visual Studio for Mac also supports and includes .NET Core 3.1 in Visual Studio for Mac 8.4.</span></span>

<span data-ttu-id="9e857-110">Para más información sobre la versión, consulte el [anuncio de .NET Core 3.1](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-1/).</span><span class="sxs-lookup"><span data-stu-id="9e857-110">For more information about the release, see the [.NET Core 3.1 announcement](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-1/).</span></span>

- <span data-ttu-id="9e857-111">[Descargue .NET Core 3.1 y empiece a trabajar](https://dotnet.microsoft.com/download/dotnet/3.1) en Windows, macOS o Linux.</span><span class="sxs-lookup"><span data-stu-id="9e857-111">[Download and get started with .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet/3.1) on Windows, macOS, or Linux.</span></span>

## <a name="long-term-support"></a><span data-ttu-id="9e857-112">Compatibilidad a largo plazo</span><span class="sxs-lookup"><span data-stu-id="9e857-112">Long-term support</span></span>

<span data-ttu-id="9e857-113">.NET Core 3.1 es una versión LTS con soporte técnico de Microsoft durante los próximos tres años.</span><span class="sxs-lookup"><span data-stu-id="9e857-113">.NET Core 3.1 is an LTS release with support from Microsoft for the next three years.</span></span> <span data-ttu-id="9e857-114">Se recomienda encarecidamente mover las aplicaciones a .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="9e857-114">It's highly recommended that you move your apps to .NET Core 3.1.</span></span> <span data-ttu-id="9e857-115">El ciclo de vida actual de otras versiones principales es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="9e857-115">The current lifecycle of other major releases is as follows:</span></span>

| <span data-ttu-id="9e857-116">Release</span><span class="sxs-lookup"><span data-stu-id="9e857-116">Release</span></span> | <span data-ttu-id="9e857-117">Nota</span><span class="sxs-lookup"><span data-stu-id="9e857-117">Note</span></span> |
| ------- | ---- |
| <span data-ttu-id="9e857-118">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="9e857-118">.NET Core 3.0</span></span> | <span data-ttu-id="9e857-119">Fin del ciclo de vida el 3 de marzo de 2020.</span><span class="sxs-lookup"><span data-stu-id="9e857-119">End of life on March 3, 2020.</span></span>     |
| <span data-ttu-id="9e857-120">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="9e857-120">.NET Core 2.2</span></span> | <span data-ttu-id="9e857-121">Fin del ciclo de vida el 23 de diciembre de 2019.</span><span class="sxs-lookup"><span data-stu-id="9e857-121">End of life on December 23, 2019.</span></span> |
| <span data-ttu-id="9e857-122">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="9e857-122">.NET Core 2.1</span></span> | <span data-ttu-id="9e857-123">Fin del ciclo de vida el 21 de agosto de 2021.</span><span class="sxs-lookup"><span data-stu-id="9e857-123">End of life on August 21, 2021.</span></span>    |

<span data-ttu-id="9e857-124">Para más información, consulte la [directiva de soporte técnico de .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="9e857-124">For more information, see the [.NET Core support policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).</span></span>

## <a name="macos-apphost-and-notarization"></a><span data-ttu-id="9e857-125">appHost y certificación de macOS</span><span class="sxs-lookup"><span data-stu-id="9e857-125">macOS appHost and notarization</span></span>

<span data-ttu-id="9e857-126">*Solo para macOS*</span><span class="sxs-lookup"><span data-stu-id="9e857-126">*macOS only*</span></span>

<span data-ttu-id="9e857-127">A partir del SDK de .NET Core 3.1 para macOS, la configuración de appHost está deshabilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="9e857-127">Starting with the notarized .NET Core SDK 3.1 for macOS, the appHost setting is disabled by default.</span></span> <span data-ttu-id="9e857-128">Para obtener más información, vea [Certificación de macOS Catalina y el impacto en las descargas y proyectos de .NET Core](../install/macos-notarization-issues.md).</span><span class="sxs-lookup"><span data-stu-id="9e857-128">For more information, see [macOS Catalina Notarization and the impact on .NET Core downloads and projects](../install/macos-notarization-issues.md).</span></span>

<span data-ttu-id="9e857-129">Cuando la configuración de appHost está habilitada, .NET Core genera un ejecutable Mach-O nativo al compilar o publicar.</span><span class="sxs-lookup"><span data-stu-id="9e857-129">When the appHost setting is enabled, .NET Core generates a native Mach-O executable when you build or publish.</span></span> <span data-ttu-id="9e857-130">La aplicación se ejecuta en el contexto de appHost cuando se ejecuta desde el código fuente con el comando `dotnet run` o mediante el inicio directo del ejecutable Mach-O.</span><span class="sxs-lookup"><span data-stu-id="9e857-130">Your app runs in the context of the appHost when it is run from source code with the `dotnet run` command, or by starting the Mach-O executable directly.</span></span>

<span data-ttu-id="9e857-131">Sin appHost, la única manera en la que un usuario puede iniciar una aplicación [dependiente del marco](../deploying/index.md#publish-framework-dependent) es con el comando `dotnet <filename.dll>`.</span><span class="sxs-lookup"><span data-stu-id="9e857-131">Without the appHost, the only way a user can start a [framework-dependent](../deploying/index.md#publish-framework-dependent) app is with the `dotnet <filename.dll>` command.</span></span> <span data-ttu-id="9e857-132">Siempre se crea un instancia de appHost al publicar la aplicación de manera [independiente](../deploying/index.md#publish-self-contained).</span><span class="sxs-lookup"><span data-stu-id="9e857-132">An appHost is always created when you publish your app [self-contained](../deploying/index.md#publish-self-contained).</span></span>

<span data-ttu-id="9e857-133">Puede configurar appHost en el nivel de proyecto, o bien cambiar la instancia de appHost de un comando `dotnet` específico con el parámetro `-p:UseAppHost`:</span><span class="sxs-lookup"><span data-stu-id="9e857-133">You can either configure the appHost at the project level, or toggle the appHost for a specific `dotnet` command with the `-p:UseAppHost` parameter:</span></span>

- <span data-ttu-id="9e857-134">Archivo del proyecto</span><span class="sxs-lookup"><span data-stu-id="9e857-134">Project file</span></span>

  ```xml
  <PropertyGroup>
    <UseAppHost>true</UseAppHost>
  </PropertyGroup>
  ```

- <span data-ttu-id="9e857-135">Parámetro de línea de comandos</span><span class="sxs-lookup"><span data-stu-id="9e857-135">Command-line parameter</span></span>

  ```dotnetcli
  dotnet run -p:UseAppHost=true
  ```

<span data-ttu-id="9e857-136">Para obtener más información sobre la configuración de `UseAppHost`, vea [Propiedades de MSBuild para Microsoft.NET.Sdk](../project-sdk/msbuild-props.md#useapphost).</span><span class="sxs-lookup"><span data-stu-id="9e857-136">For more information about the `UseAppHost` setting, see [MSBuild properties for Microsoft.NET.Sdk](../project-sdk/msbuild-props.md#useapphost).</span></span>

## <a name="windows-forms"></a><span data-ttu-id="9e857-137">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9e857-137">Windows Forms</span></span>

<span data-ttu-id="9e857-138">*Solo Windows*</span><span class="sxs-lookup"><span data-stu-id="9e857-138">*Windows only*</span></span>

> [!WARNING]
> <span data-ttu-id="9e857-139">Hay cambios importantes en Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="9e857-139">There are breaking changes in Windows Forms.</span></span>

<span data-ttu-id="9e857-140">Se incluyeron controles heredados en Windows Forms que llevan un tiempo sin estar disponibles en el cuadro de herramientas del diseñador de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="9e857-140">Legacy controls were included in Windows Forms that have been unavailable in the Visual Studio Designer Toolbox for some time.</span></span> <span data-ttu-id="9e857-141">Estos controles se volvieron a reemplazar por otros nuevos en .NET Framework 2.0 y</span><span class="sxs-lookup"><span data-stu-id="9e857-141">These were replaced with new controls back in .NET Framework 2.0.</span></span> <span data-ttu-id="9e857-142">se han quitado del SDK de escritorio para .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="9e857-142">These have been removed from the Desktop SDK for .NET Core 3.1.</span></span>

| <span data-ttu-id="9e857-143">Control eliminado</span><span class="sxs-lookup"><span data-stu-id="9e857-143">Removed control</span></span> | <span data-ttu-id="9e857-144">Reemplazo recomendado</span><span class="sxs-lookup"><span data-stu-id="9e857-144">Recommended replacement</span></span> | <span data-ttu-id="9e857-145">API asociadas eliminadas</span><span class="sxs-lookup"><span data-stu-id="9e857-145">Associated APIs removed</span></span> |
| --------------- | ----------------------- | ----------------------- |
| <span data-ttu-id="9e857-146">DataGrid</span><span class="sxs-lookup"><span data-stu-id="9e857-146">DataGrid</span></span>        | <xref:System.Windows.Forms.DataGridView>      | <span data-ttu-id="9e857-147">DataGridCell</span><span class="sxs-lookup"><span data-stu-id="9e857-147">DataGridCell</span></span><br/><span data-ttu-id="9e857-148">DataGridRow</span><span class="sxs-lookup"><span data-stu-id="9e857-148">DataGridRow</span></span><br/><span data-ttu-id="9e857-149">DataGridTableCollection</span><span class="sxs-lookup"><span data-stu-id="9e857-149">DataGridTableCollection</span></span><br/><span data-ttu-id="9e857-150">DataGridColumnCollection</span><span class="sxs-lookup"><span data-stu-id="9e857-150">DataGridColumnCollection</span></span><br/><span data-ttu-id="9e857-151">DataGridTableStyle</span><span class="sxs-lookup"><span data-stu-id="9e857-151">DataGridTableStyle</span></span><br/><span data-ttu-id="9e857-152">DataGridColumnStyle</span><span class="sxs-lookup"><span data-stu-id="9e857-152">DataGridColumnStyle</span></span><br/><span data-ttu-id="9e857-153">DataGridLineStyle</span><span class="sxs-lookup"><span data-stu-id="9e857-153">DataGridLineStyle</span></span><br/><span data-ttu-id="9e857-154">DataGridParentRowsLabel</span><span class="sxs-lookup"><span data-stu-id="9e857-154">DataGridParentRowsLabel</span></span><br/><span data-ttu-id="9e857-155">DataGridParentRowsLabelStyle</span><span class="sxs-lookup"><span data-stu-id="9e857-155">DataGridParentRowsLabelStyle</span></span><br/><span data-ttu-id="9e857-156">DataGridBoolColumn</span><span class="sxs-lookup"><span data-stu-id="9e857-156">DataGridBoolColumn</span></span><br/><span data-ttu-id="9e857-157">DataGridTextBox</span><span class="sxs-lookup"><span data-stu-id="9e857-157">DataGridTextBox</span></span><br/><span data-ttu-id="9e857-158">GridColumnStylesCollection</span><span class="sxs-lookup"><span data-stu-id="9e857-158">GridColumnStylesCollection</span></span><br/><span data-ttu-id="9e857-159">GridTableStylesCollection</span><span class="sxs-lookup"><span data-stu-id="9e857-159">GridTableStylesCollection</span></span><br/><span data-ttu-id="9e857-160">HitTestType</span><span class="sxs-lookup"><span data-stu-id="9e857-160">HitTestType</span></span> |
| <span data-ttu-id="9e857-161">ToolBar</span><span class="sxs-lookup"><span data-stu-id="9e857-161">ToolBar</span></span>         | <xref:System.Windows.Forms.ToolStrip>         | <span data-ttu-id="9e857-162">ToolBarAppearance</span><span class="sxs-lookup"><span data-stu-id="9e857-162">ToolBarAppearance</span></span> |
| <span data-ttu-id="9e857-163">ToolBarButton</span><span class="sxs-lookup"><span data-stu-id="9e857-163">ToolBarButton</span></span>   | <xref:System.Windows.Forms.ToolStripButton>   | <span data-ttu-id="9e857-164">ToolBarButtonClickEventArgs</span><span class="sxs-lookup"><span data-stu-id="9e857-164">ToolBarButtonClickEventArgs</span></span><br/><span data-ttu-id="9e857-165">ToolBarButtonClickEventHandler</span><span class="sxs-lookup"><span data-stu-id="9e857-165">ToolBarButtonClickEventHandler</span></span><br/><span data-ttu-id="9e857-166">ToolBarButtonStyle</span><span class="sxs-lookup"><span data-stu-id="9e857-166">ToolBarButtonStyle</span></span><br/><span data-ttu-id="9e857-167">ToolBarTextAlign</span><span class="sxs-lookup"><span data-stu-id="9e857-167">ToolBarTextAlign</span></span> |
| <span data-ttu-id="9e857-168">ContextMenu</span><span class="sxs-lookup"><span data-stu-id="9e857-168">ContextMenu</span></span>     | <xref:System.Windows.Forms.ContextMenuStrip>  |  |
| :::no-loc text="Menu"::: | <xref:System.Windows.Forms.ToolStripDropDown><br/><xref:System.Windows.Forms.ToolStripDropDownMenu> | <span data-ttu-id="9e857-169">MenuItemCollection</span><span class="sxs-lookup"><span data-stu-id="9e857-169">MenuItemCollection</span></span> |
| <span data-ttu-id="9e857-170">MainMenu</span><span class="sxs-lookup"><span data-stu-id="9e857-170">MainMenu</span></span>        | <xref:System.Windows.Forms.MenuStrip>         |  |
| <span data-ttu-id="9e857-171">MenuItem</span><span class="sxs-lookup"><span data-stu-id="9e857-171">MenuItem</span></span>        | <xref:System.Windows.Forms.ToolStripMenuItem> |  |

<span data-ttu-id="9e857-172">Se recomienda actualizar las aplicaciones a .NET Core 3.1 y pasar a los controles de reemplazo.</span><span class="sxs-lookup"><span data-stu-id="9e857-172">We recommend you update your applications to .NET Core 3.1 and move to the replacement controls.</span></span> <span data-ttu-id="9e857-173">Reemplazar los controles es un proceso sencillo; se trata básicamente de "buscar y reemplazar" el tipo.</span><span class="sxs-lookup"><span data-stu-id="9e857-173">Replacing the controls is a straightforward process, essentially "find and replace" on the type.</span></span>

## <a name="ccli"></a><span data-ttu-id="9e857-174">C++/CLI</span><span class="sxs-lookup"><span data-stu-id="9e857-174">C++/CLI</span></span>

<span data-ttu-id="9e857-175">*Solo Windows*</span><span class="sxs-lookup"><span data-stu-id="9e857-175">*Windows only*</span></span>

<span data-ttu-id="9e857-176">Se ha agregado compatibilidad con la creación de proyectos de C++/CLI (lo que también se conoce como "C++ administrado").</span><span class="sxs-lookup"><span data-stu-id="9e857-176">Support has been added for creating C++/CLI (also known as "managed C++") projects.</span></span> <span data-ttu-id="9e857-177">Los archivos binarios generados a partir de estos proyectos son compatibles con .NET Core 3.0 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="9e857-177">Binaries produced from these projects are compatible with .NET Core 3.0 and later versions.</span></span>

<span data-ttu-id="9e857-178">Para agregar compatibilidad con C++/CLI a Visual Studio 2019 versión 16.4, instale la [carga de trabajo Desarrollo para el escritorio con C++](/cpp/build/vscpp-step-0-installation?view=vs-2019#step-4---choose-workloads).</span><span class="sxs-lookup"><span data-stu-id="9e857-178">To add support for C++/CLI in Visual Studio 2019 version 16.4, install the [Desktop development with C++ workload](/cpp/build/vscpp-step-0-installation?view=vs-2019#step-4---choose-workloads).</span></span> <span data-ttu-id="9e857-179">Esta carga de trabajo agrega dos plantillas a Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="9e857-179">This workload adds two templates to Visual Studio:</span></span>

- <span data-ttu-id="9e857-180">Biblioteca de clases de CLR (.NET Core)</span><span class="sxs-lookup"><span data-stu-id="9e857-180">CLR Class Library (.NET Core)</span></span>
- <span data-ttu-id="9e857-181">Proyecto vacío de CLR (.NET Core)</span><span class="sxs-lookup"><span data-stu-id="9e857-181">CLR Empty Project (.NET Core)</span></span>

## <a name="next-steps"></a><span data-ttu-id="9e857-182">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="9e857-182">Next steps</span></span>

- [<span data-ttu-id="9e857-183">Revise los cambios importantes entre .NET Core 3.0 y 3.1.</span><span class="sxs-lookup"><span data-stu-id="9e857-183">Review the breaking changes between .NET Core 3.0 and 3.1.</span></span>](../compatibility/3.1.md)
- <span data-ttu-id="9e857-184">[Revise los cambios importantes de .NET Core 3.1 para aplicaciones de Windows Forms](../compatibility/winforms.md#net-core-31).</span><span class="sxs-lookup"><span data-stu-id="9e857-184">[Review the breaking changes in .NET Core 3.1 for Windows Forms apps.](../compatibility/winforms.md#net-core-31)</span></span>
