---
title: Cambios importantes en Windows Forms
description: Enumera los cambios importantes en Windows Forms para .NET Core.
ms.date: 01/08/2020
ms.openlocfilehash: beb9a42e4b5007f03480cd74f57bbfbbfc3f48b1
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556253"
---
# <a name="breaking-changes-in-windows-forms"></a><span data-ttu-id="6980b-103">Cambios importantes en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6980b-103">Breaking changes in Windows Forms</span></span>

<span data-ttu-id="6980b-104">Se ha agregado compatibilidad con Windows Forms a .NET Core, versión 3.0.</span><span class="sxs-lookup"><span data-stu-id="6980b-104">Windows Forms support was added to .NET Core in version 3.0.</span></span> <span data-ttu-id="6980b-105">En este artículo se enumeran los cambios importantes de Windows Forms por versión de .NET Core en la que se han incorporado.</span><span class="sxs-lookup"><span data-stu-id="6980b-105">This article lists breaking changes for Windows Forms by the .NET Core version in which they were introduced.</span></span> <span data-ttu-id="6980b-106">Si está actualizando una aplicación de Windows Forms desde .NET Framework o una versión anterior de .NET Core (3.0 o posterior), este artículo se aplica a su caso.</span><span class="sxs-lookup"><span data-stu-id="6980b-106">If you're upgrading a Windows Forms app from .NET Framework or from a previous version of .NET Core (3.0 or later), this article is applicable to you.</span></span>

<span data-ttu-id="6980b-107">En esta página se documentan los siguientes cambios importantes:</span><span class="sxs-lookup"><span data-stu-id="6980b-107">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="6980b-108">Cambio importante</span><span class="sxs-lookup"><span data-stu-id="6980b-108">Breaking change</span></span> | <span data-ttu-id="6980b-109">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="6980b-109">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="6980b-110">Controles de la barra de estado quitados</span><span class="sxs-lookup"><span data-stu-id="6980b-110">Removed status bar controls</span></span>](#removed-status-bar-controls) | <span data-ttu-id="6980b-111">5.0</span><span class="sxs-lookup"><span data-stu-id="6980b-111">5.0</span></span> |
| [<span data-ttu-id="6980b-112">Los métodos de WinForms inician ahora la excepción ArgumentException</span><span class="sxs-lookup"><span data-stu-id="6980b-112">WinForms methods now throw ArgumentException</span></span>](#winforms-methods-now-throw-argumentexception) | <span data-ttu-id="6980b-113">5.0</span><span class="sxs-lookup"><span data-stu-id="6980b-113">5.0</span></span> |
| [<span data-ttu-id="6980b-114">Los métodos de WinForms inician ahora la excepción ArgumentNullException</span><span class="sxs-lookup"><span data-stu-id="6980b-114">WinForms methods now throw ArgumentNullException</span></span>](#winforms-methods-now-throw-argumentnullexception) | <span data-ttu-id="6980b-115">5.0</span><span class="sxs-lookup"><span data-stu-id="6980b-115">5.0</span></span> |
| [<span data-ttu-id="6980b-116">Ahora, las propiedades de WinForms producen ArgumentOutOfRangeException</span><span class="sxs-lookup"><span data-stu-id="6980b-116">WinForms properties now throw ArgumentOutOfRangeException</span></span>](#winforms-properties-now-throw-argumentoutofrangeexception) | <span data-ttu-id="6980b-117">5.0</span><span class="sxs-lookup"><span data-stu-id="6980b-117">5.0</span></span> |
| [<span data-ttu-id="6980b-118">Controles eliminados</span><span class="sxs-lookup"><span data-stu-id="6980b-118">Removed controls</span></span>](#removed-controls) | <span data-ttu-id="6980b-119">3.1</span><span class="sxs-lookup"><span data-stu-id="6980b-119">3.1</span></span> |
| [<span data-ttu-id="6980b-120">El evento CellFormatting no se produce si se muestra información en pantalla</span><span class="sxs-lookup"><span data-stu-id="6980b-120">CellFormatting event not raised if tooltip is shown</span></span>](#cellformatting-event-not-raised-if-tooltip-is-shown) | <span data-ttu-id="6980b-121">3.1</span><span class="sxs-lookup"><span data-stu-id="6980b-121">3.1</span></span> |
| [<span data-ttu-id="6980b-122">Se ha cambiado Control.DefaultFont a Segoe UI 9 pt</span><span class="sxs-lookup"><span data-stu-id="6980b-122">Control.DefaultFont changed to Segoe UI 9 pt</span></span>](#default-control-font-changed-to-segoe-ui-9-pt) | <span data-ttu-id="6980b-123">3.0</span><span class="sxs-lookup"><span data-stu-id="6980b-123">3.0</span></span> |
| [<span data-ttu-id="6980b-124">Se ha modernizado FolderBrowserDialog</span><span class="sxs-lookup"><span data-stu-id="6980b-124">Modernization of the FolderBrowserDialog</span></span>](#modernization-of-the-folderbrowserdialog) | <span data-ttu-id="6980b-125">3.0</span><span class="sxs-lookup"><span data-stu-id="6980b-125">3.0</span></span> |
| [<span data-ttu-id="6980b-126">Se ha quitado SerializableAttribute de algunos tipos de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6980b-126">SerializableAttribute removed from some Windows Forms types</span></span>](#serializableattribute-removed-from-some-windows-forms-types) | <span data-ttu-id="6980b-127">3.0</span><span class="sxs-lookup"><span data-stu-id="6980b-127">3.0</span></span> |
| [<span data-ttu-id="6980b-128">No se admite el modificador de compatibilidad AllowUpdateChildControlIndexForTabControls</span><span class="sxs-lookup"><span data-stu-id="6980b-128">AllowUpdateChildControlIndexForTabControls compatibility switch not supported</span></span>](#allowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported) | <span data-ttu-id="6980b-129">3.0</span><span class="sxs-lookup"><span data-stu-id="6980b-129">3.0</span></span> |
| [<span data-ttu-id="6980b-130">No se admite el modificador de compatibilidad DomainUpDown.UseLegacyScrolling</span><span class="sxs-lookup"><span data-stu-id="6980b-130">DomainUpDown.UseLegacyScrolling compatibility switch not supported</span></span>](#domainupdownuselegacyscrolling-compatibility-switch-not-supported) | <span data-ttu-id="6980b-131">3.0</span><span class="sxs-lookup"><span data-stu-id="6980b-131">3.0</span></span> |
| [<span data-ttu-id="6980b-132">No se admite el modificador de compatibilidad DoNotLoadLatestRichEditControl</span><span class="sxs-lookup"><span data-stu-id="6980b-132">DoNotLoadLatestRichEditControl compatibility switch not supported</span></span>](#donotloadlatestricheditcontrol-compatibility-switch-not-supported) | <span data-ttu-id="6980b-133">3.0</span><span class="sxs-lookup"><span data-stu-id="6980b-133">3.0</span></span> |
| [<span data-ttu-id="6980b-134">No se admite el modificador de compatibilidad DoNotSupportSelectAllShortcutInMultilineTextBox</span><span class="sxs-lookup"><span data-stu-id="6980b-134">DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported</span></span>](#donotsupportselectallshortcutinmultilinetextbox-compatibility-switch-not-supported) | <span data-ttu-id="6980b-135">3.0</span><span class="sxs-lookup"><span data-stu-id="6980b-135">3.0</span></span> |
| [<span data-ttu-id="6980b-136">No se admite el modificador de compatibilidad DontSupportReentrantFilterMessage</span><span class="sxs-lookup"><span data-stu-id="6980b-136">DontSupportReentrantFilterMessage compatibility switch not supported</span></span>](#dontsupportreentrantfiltermessage-compatibility-switch-not-supported) | <span data-ttu-id="6980b-137">3.0</span><span class="sxs-lookup"><span data-stu-id="6980b-137">3.0</span></span> |
| [<span data-ttu-id="6980b-138">No se admite el modificador de compatibilidad EnableVisualStyleValidation</span><span class="sxs-lookup"><span data-stu-id="6980b-138">EnableVisualStyleValidation compatibility switch not supported</span></span>](#enablevisualstylevalidation-compatibility-switch-not-supported) | <span data-ttu-id="6980b-139">3.0</span><span class="sxs-lookup"><span data-stu-id="6980b-139">3.0</span></span> |
| [<span data-ttu-id="6980b-140">No se admite el modificador de compatibilidad UseLegacyContextMenuStripSourceControlValue</span><span class="sxs-lookup"><span data-stu-id="6980b-140">UseLegacyContextMenuStripSourceControlValue compatibility switch not supported</span></span>](#uselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported) | <span data-ttu-id="6980b-141">3.0</span><span class="sxs-lookup"><span data-stu-id="6980b-141">3.0</span></span> |
| [<span data-ttu-id="6980b-142">No se admite el modificador de compatibilidad UseLegacyImages</span><span class="sxs-lookup"><span data-stu-id="6980b-142">UseLegacyImages compatibility switch not supported</span></span>](#uselegacyimages-compatibility-switch-not-supported) | <span data-ttu-id="6980b-143">3.0</span><span class="sxs-lookup"><span data-stu-id="6980b-143">3.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="6980b-144">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="6980b-144">.NET 5.0</span></span>

[!INCLUDE [winforms-deprecated-controls](../../../includes/core-changes/windowsforms/5.0/winforms-deprecated-controls.md)]

***

[!INCLUDE [invalid-args-cause-argumentexception](../../../includes/core-changes/windowsforms/5.0/invalid-args-cause-argumentexception.md)]

***

[!INCLUDE [null-args-cause-argumentnullexception](../../../includes/core-changes/windowsforms/5.0/null-args-cause-argumentnullexception.md)]

***

[!INCLUDE [invalid-args-cause-argumentoutofrangeexception](../../../includes/core-changes/windowsforms/5.0/invalid-args-cause-argumentoutofrangeexception.md)]

***

## <a name="net-core-31"></a><span data-ttu-id="6980b-145">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="6980b-145">.NET Core 3.1</span></span>

[!INCLUDE[Removed controls](~/includes/core-changes/windowsforms/3.1/remove-controls-3.1.md)]

***

[!INCLUDE[CellFormatting event](~/includes/core-changes/windowsforms/3.1/cellformatting-event-not-raised.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="6980b-146">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="6980b-146">.NET Core 3.0</span></span>

[!INCLUDE[Control.DefaultFont changed to Segoe UI 9pt](~/includes/core-changes/windowsforms/3.0/control-defaultfont-changed.md)]

***

[!INCLUDE[Modernization of the FolderBrowserDialog](~/includes/core-changes/windowsforms/3.0/modernized-folderbrowserdialog.md)]

***

[!INCLUDE[SerializableAttribute removed from some Windows Forms types](~/includes/core-changes/windowsforms/3.0/remove-serializationattribute.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-allowupdatechildcontrolindexfortabcontrols.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacyscrolling.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-donotloadlatestricheditcontrol.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-donotsupportselectallshortcutinmultilinetextbox.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.DontSupportReentrantFilterMessage compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-dontsupportreentrantfiltermessage.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.EnableVisualStyleValidation compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-enablevisualstylevalidation.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacycontextmenustripsourcecontrolvalue.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.UseLegacyImages compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacyimages.md)]

***

## <a name="see-also"></a><span data-ttu-id="6980b-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="6980b-147">See also</span></span>

- [<span data-ttu-id="6980b-148">Migración de una aplicación de Windows Forms a .NET Core</span><span class="sxs-lookup"><span data-stu-id="6980b-148">Port a Windows Forms app to .NET Core</span></span>](../porting/winforms.md)
