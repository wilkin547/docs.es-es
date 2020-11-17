---
title: Cambios importantes en Windows Forms
description: Enumera los cambios importantes en Windows Forms para .NET Core y .NET 5.
ms.date: 09/08/2020
ms.openlocfilehash: c79fd28b5c3b81ae7ddf1ef3f470601108b87705
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/10/2020
ms.locfileid: "94440795"
---
# <a name="breaking-changes-in-windows-forms"></a><span data-ttu-id="2f06f-103">Cambios importantes en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2f06f-103">Breaking changes in Windows Forms</span></span>

<span data-ttu-id="2f06f-104">Se ha agregado compatibilidad con Windows Forms a .NET Core, versión 3.0.</span><span class="sxs-lookup"><span data-stu-id="2f06f-104">Windows Forms support was added to .NET Core in version 3.0.</span></span> <span data-ttu-id="2f06f-105">En este artículo se enumeran los cambios importantes de Windows Forms por versión de .NET en la que se han incorporado.</span><span class="sxs-lookup"><span data-stu-id="2f06f-105">This article lists breaking changes for Windows Forms by the .NET version in which they were introduced.</span></span> <span data-ttu-id="2f06f-106">Si está actualizando una aplicación de Windows Forms desde .NET Framework o una versión anterior de .NET Core (3.0 o posterior), este artículo se aplica a su caso.</span><span class="sxs-lookup"><span data-stu-id="2f06f-106">If you're upgrading a Windows Forms app from .NET Framework or from a previous version of .NET Core (3.0 or later), this article applies to you.</span></span>

<span data-ttu-id="2f06f-107">En esta página se documentan los siguientes cambios importantes:</span><span class="sxs-lookup"><span data-stu-id="2f06f-107">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="2f06f-108">Cambio importante</span><span class="sxs-lookup"><span data-stu-id="2f06f-108">Breaking change</span></span> | <span data-ttu-id="2f06f-109">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="2f06f-109">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="2f06f-110">TextFormatFlags.ModifyString está obsoleto</span><span class="sxs-lookup"><span data-stu-id="2f06f-110">TextFormatFlags.ModifyString is obsolete</span></span>](#textformatflagsmodifystring-is-obsolete) | <span data-ttu-id="2f06f-111">5.0</span><span class="sxs-lookup"><span data-stu-id="2f06f-111">5.0</span></span> |
| [<span data-ttu-id="2f06f-112">DataGridView ya no restablece las fuentes para los estilos de celda personalizados</span><span class="sxs-lookup"><span data-stu-id="2f06f-112">DataGridView no longer resets fonts for customized cell styles</span></span>](#datagridview-no-longer-resets-fonts-for-customized-cell-styles) | <span data-ttu-id="2f06f-113">5.0</span><span class="sxs-lookup"><span data-stu-id="2f06f-113">5.0</span></span> |
| [<span data-ttu-id="2f06f-114">OutputType establecido en WinExe para aplicaciones de WPF y WinForms</span><span class="sxs-lookup"><span data-stu-id="2f06f-114">OutputType set to WinExe for WPF and WinForms apps</span></span>](#outputtype-set-to-winexe-for-wpf-and-winforms-apps) | <span data-ttu-id="2f06f-115">5.0</span><span class="sxs-lookup"><span data-stu-id="2f06f-115">5.0</span></span> |
| [<span data-ttu-id="2f06f-116">Excepción InvalidOperationException por parte de las API relacionadas con DataGridView</span><span class="sxs-lookup"><span data-stu-id="2f06f-116">DataGridView-related APIs now throw InvalidOperationException</span></span>](#datagridview-related-apis-now-throw-invalidoperationexception) | <span data-ttu-id="2f06f-117">5.0</span><span class="sxs-lookup"><span data-stu-id="2f06f-117">5.0</span></span> |
| [<span data-ttu-id="2f06f-118">Uso de Microsoft.NET.Sdk por parte de las aplicaciones de WinForms y WPF</span><span class="sxs-lookup"><span data-stu-id="2f06f-118">WinForms and WPF apps use Microsoft.NET.Sdk</span></span>](#winforms-and-wpf-apps-use-microsoftnetsdk) | <span data-ttu-id="2f06f-119">5.0</span><span class="sxs-lookup"><span data-stu-id="2f06f-119">5.0</span></span> |
| [<span data-ttu-id="2f06f-120">Controles de la barra de estado quitados</span><span class="sxs-lookup"><span data-stu-id="2f06f-120">Removed status bar controls</span></span>](#removed-status-bar-controls) | <span data-ttu-id="2f06f-121">5.0</span><span class="sxs-lookup"><span data-stu-id="2f06f-121">5.0</span></span> |
| [<span data-ttu-id="2f06f-122">Los métodos de WinForms inician ahora la excepción ArgumentException</span><span class="sxs-lookup"><span data-stu-id="2f06f-122">WinForms methods now throw ArgumentException</span></span>](#winforms-methods-now-throw-argumentexception) | <span data-ttu-id="2f06f-123">5.0</span><span class="sxs-lookup"><span data-stu-id="2f06f-123">5.0</span></span> |
| [<span data-ttu-id="2f06f-124">Los métodos de WinForms inician ahora la excepción ArgumentNullException</span><span class="sxs-lookup"><span data-stu-id="2f06f-124">WinForms methods now throw ArgumentNullException</span></span>](#winforms-methods-now-throw-argumentnullexception) | <span data-ttu-id="2f06f-125">5.0</span><span class="sxs-lookup"><span data-stu-id="2f06f-125">5.0</span></span> |
| [<span data-ttu-id="2f06f-126">Ahora, las propiedades de WinForms producen ArgumentOutOfRangeException</span><span class="sxs-lookup"><span data-stu-id="2f06f-126">WinForms properties now throw ArgumentOutOfRangeException</span></span>](#winforms-properties-now-throw-argumentoutofrangeexception) | <span data-ttu-id="2f06f-127">5.0</span><span class="sxs-lookup"><span data-stu-id="2f06f-127">5.0</span></span> |
| [<span data-ttu-id="2f06f-128">Controles eliminados</span><span class="sxs-lookup"><span data-stu-id="2f06f-128">Removed controls</span></span>](#removed-controls) | <span data-ttu-id="2f06f-129">3.1</span><span class="sxs-lookup"><span data-stu-id="2f06f-129">3.1</span></span> |
| [<span data-ttu-id="2f06f-130">El evento CellFormatting no se produce si se muestra información en pantalla</span><span class="sxs-lookup"><span data-stu-id="2f06f-130">CellFormatting event not raised if tooltip is shown</span></span>](#cellformatting-event-not-raised-if-tooltip-is-shown) | <span data-ttu-id="2f06f-131">3.1</span><span class="sxs-lookup"><span data-stu-id="2f06f-131">3.1</span></span> |
| [<span data-ttu-id="2f06f-132">Se ha cambiado Control.DefaultFont a Segoe UI 9 pt</span><span class="sxs-lookup"><span data-stu-id="2f06f-132">Control.DefaultFont changed to Segoe UI 9 pt</span></span>](#default-control-font-changed-to-segoe-ui-9-pt) | <span data-ttu-id="2f06f-133">3.0</span><span class="sxs-lookup"><span data-stu-id="2f06f-133">3.0</span></span> |
| [<span data-ttu-id="2f06f-134">Se ha modernizado FolderBrowserDialog</span><span class="sxs-lookup"><span data-stu-id="2f06f-134">Modernization of the FolderBrowserDialog</span></span>](#modernization-of-the-folderbrowserdialog) | <span data-ttu-id="2f06f-135">3.0</span><span class="sxs-lookup"><span data-stu-id="2f06f-135">3.0</span></span> |
| [<span data-ttu-id="2f06f-136">Se ha quitado SerializableAttribute de algunos tipos de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2f06f-136">SerializableAttribute removed from some Windows Forms types</span></span>](#serializableattribute-removed-from-some-windows-forms-types) | <span data-ttu-id="2f06f-137">3.0</span><span class="sxs-lookup"><span data-stu-id="2f06f-137">3.0</span></span> |
| [<span data-ttu-id="2f06f-138">No se admite el modificador de compatibilidad AllowUpdateChildControlIndexForTabControls</span><span class="sxs-lookup"><span data-stu-id="2f06f-138">AllowUpdateChildControlIndexForTabControls compatibility switch not supported</span></span>](#allowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported) | <span data-ttu-id="2f06f-139">3.0</span><span class="sxs-lookup"><span data-stu-id="2f06f-139">3.0</span></span> |
| [<span data-ttu-id="2f06f-140">No se admite el modificador de compatibilidad DomainUpDown.UseLegacyScrolling</span><span class="sxs-lookup"><span data-stu-id="2f06f-140">DomainUpDown.UseLegacyScrolling compatibility switch not supported</span></span>](#domainupdownuselegacyscrolling-compatibility-switch-not-supported) | <span data-ttu-id="2f06f-141">3.0</span><span class="sxs-lookup"><span data-stu-id="2f06f-141">3.0</span></span> |
| [<span data-ttu-id="2f06f-142">No se admite el modificador de compatibilidad DoNotLoadLatestRichEditControl</span><span class="sxs-lookup"><span data-stu-id="2f06f-142">DoNotLoadLatestRichEditControl compatibility switch not supported</span></span>](#donotloadlatestricheditcontrol-compatibility-switch-not-supported) | <span data-ttu-id="2f06f-143">3.0</span><span class="sxs-lookup"><span data-stu-id="2f06f-143">3.0</span></span> |
| [<span data-ttu-id="2f06f-144">No se admite el modificador de compatibilidad DoNotSupportSelectAllShortcutInMultilineTextBox</span><span class="sxs-lookup"><span data-stu-id="2f06f-144">DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported</span></span>](#donotsupportselectallshortcutinmultilinetextbox-compatibility-switch-not-supported) | <span data-ttu-id="2f06f-145">3.0</span><span class="sxs-lookup"><span data-stu-id="2f06f-145">3.0</span></span> |
| [<span data-ttu-id="2f06f-146">No se admite el modificador de compatibilidad DontSupportReentrantFilterMessage</span><span class="sxs-lookup"><span data-stu-id="2f06f-146">DontSupportReentrantFilterMessage compatibility switch not supported</span></span>](#dontsupportreentrantfiltermessage-compatibility-switch-not-supported) | <span data-ttu-id="2f06f-147">3.0</span><span class="sxs-lookup"><span data-stu-id="2f06f-147">3.0</span></span> |
| [<span data-ttu-id="2f06f-148">No se admite el modificador de compatibilidad EnableVisualStyleValidation</span><span class="sxs-lookup"><span data-stu-id="2f06f-148">EnableVisualStyleValidation compatibility switch not supported</span></span>](#enablevisualstylevalidation-compatibility-switch-not-supported) | <span data-ttu-id="2f06f-149">3.0</span><span class="sxs-lookup"><span data-stu-id="2f06f-149">3.0</span></span> |
| [<span data-ttu-id="2f06f-150">No se admite el modificador de compatibilidad UseLegacyContextMenuStripSourceControlValue</span><span class="sxs-lookup"><span data-stu-id="2f06f-150">UseLegacyContextMenuStripSourceControlValue compatibility switch not supported</span></span>](#uselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported) | <span data-ttu-id="2f06f-151">3.0</span><span class="sxs-lookup"><span data-stu-id="2f06f-151">3.0</span></span> |
| [<span data-ttu-id="2f06f-152">No se admite el modificador de compatibilidad UseLegacyImages</span><span class="sxs-lookup"><span data-stu-id="2f06f-152">UseLegacyImages compatibility switch not supported</span></span>](#uselegacyimages-compatibility-switch-not-supported) | <span data-ttu-id="2f06f-153">3.0</span><span class="sxs-lookup"><span data-stu-id="2f06f-153">3.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="2f06f-154">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="2f06f-154">.NET 5.0</span></span>

[!INCLUDE [modifystring-field-of-textformatflags-obsolete](../../../includes/core-changes/windowsforms/5.0/modifystring-field-of-textformatflags-obsolete.md)]

***

[!INCLUDE [datagridview-doesnt-reset-custom-font-settings](../../../includes/core-changes/windowsforms/5.0/datagridview-doesnt-reset-custom-font-settings.md)]

<span data-ttu-id="2f06f-155">\*\*_</span><span class="sxs-lookup"><span data-stu-id="2f06f-155">\*\*_</span></span>

[!INCLUDE [automatically-infer-winexe-output-type](../../../includes/core-changes/windowsforms/5.0/automatically-infer-winexe-output-type.md)]

_*_

[!INCLUDE [null-owner-causes-invalidoperationexception](../../../includes/core-changes/windowsforms/5.0/null-owner-causes-invalidoperationexception.md)]

_*_

[!INCLUDE [sdk-and-target-framework-change](../../../includes/core-changes/windowsforms/5.0/sdk-and-target-framework-change.md)]

_*_

[!INCLUDE [winforms-deprecated-controls](../../../includes/core-changes/windowsforms/5.0/winforms-deprecated-controls.md)]

_*_

[!INCLUDE [invalid-args-cause-argumentexception](../../../includes/core-changes/windowsforms/5.0/invalid-args-cause-argumentexception.md)]

_*_

[!INCLUDE [null-args-cause-argumentnullexception](../../../includes/core-changes/windowsforms/5.0/null-args-cause-argumentnullexception.md)]

_*_

[!INCLUDE [invalid-args-cause-argumentoutofrangeexception](../../../includes/core-changes/windowsforms/5.0/invalid-args-cause-argumentoutofrangeexception.md)]

_*_

## <a name="net-core-31"></a><span data-ttu-id="2f06f-156">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="2f06f-156">.NET Core 3.1</span></span>

[!INCLUDE[Removed controls](~/includes/core-changes/windowsforms/3.1/remove-controls-3.1.md)]

_*_

[!INCLUDE[CellFormatting event](~/includes/core-changes/windowsforms/3.1/cellformatting-event-not-raised.md)]

_*_

## <a name="net-core-30"></a><span data-ttu-id="2f06f-157">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="2f06f-157">.NET Core 3.0</span></span>

[!INCLUDE[Control.DefaultFont changed to Segoe UI 9pt](~/includes/core-changes/windowsforms/3.0/control-defaultfont-changed.md)]

_*_

[!INCLUDE[Modernization of the FolderBrowserDialog](~/includes/core-changes/windowsforms/3.0/modernized-folderbrowserdialog.md)]

_*_

[!INCLUDE[SerializableAttribute removed from some Windows Forms types](~/includes/core-changes/windowsforms/3.0/remove-serializationattribute.md)]

_*_

[!INCLUDE[Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-allowupdatechildcontrolindexfortabcontrols.md)]

_*_

[!INCLUDE[Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacyscrolling.md)]

_*_

[!INCLUDE[Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-donotloadlatestricheditcontrol.md)]

_*_

[!INCLUDE[Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-donotsupportselectallshortcutinmultilinetextbox.md)]

_*_

[!INCLUDE[Switch.System.Windows.Forms.DontSupportReentrantFilterMessage compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-dontsupportreentrantfiltermessage.md)]

_*_

[!INCLUDE[Switch.System.Windows.Forms.EnableVisualStyleValidation compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-enablevisualstylevalidation.md)]

_*_

[!INCLUDE[Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacycontextmenustripsourcecontrolvalue.md)]

_*_

[!INCLUDE[Switch.System.Windows.Forms.UseLegacyImages compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacyimages.md)]

<span data-ttu-id="2f06f-158">_\*\*</span><span class="sxs-lookup"><span data-stu-id="2f06f-158">_\*\*</span></span>

## <a name="see-also"></a><span data-ttu-id="2f06f-159">Vea también</span><span class="sxs-lookup"><span data-stu-id="2f06f-159">See also</span></span>

- [<span data-ttu-id="2f06f-160">Migración de una aplicación de Windows Forms a .NET Core</span><span class="sxs-lookup"><span data-stu-id="2f06f-160">Port a Windows Forms app to .NET Core</span></span>](/dotnet/desktop/winforms/migration/?view=netdesktop-5.0&preserve-view=true)
