---
title: Cambios importantes en Windows Forms
description: Se enumeran los cambios importantes en Windows Forms para .NET Core 3.0 y 3.1.
ms.date: 09/08/2020
ms.openlocfilehash: b944f7eea89b61f41feb8eef99e949c2d6017960
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726436"
---
# <a name="breaking-changes-in-windows-forms-for-net-core-30-and-31"></a><span data-ttu-id="babef-103">Cambios importantes en Windows Forms para .NET Core 3.0 y 3.1</span><span class="sxs-lookup"><span data-stu-id="babef-103">Breaking changes in Windows Forms for .NET Core 3.0 and 3.1</span></span>

<span data-ttu-id="babef-104">Se ha agregado compatibilidad con Windows Forms a .NET Core, versión 3.0.</span><span class="sxs-lookup"><span data-stu-id="babef-104">Windows Forms support was added to .NET Core in version 3.0.</span></span> <span data-ttu-id="babef-105">En este artículo se enumeran los cambios importantes de Windows Forms por versión de .NET en la que se han incorporado.</span><span class="sxs-lookup"><span data-stu-id="babef-105">This article lists breaking changes for Windows Forms by the .NET version in which they were introduced.</span></span> <span data-ttu-id="babef-106">Si está actualizando una aplicación de Windows Forms desde .NET Framework o una versión anterior de .NET Core (3.0 o posterior), este artículo se aplica a su caso.</span><span class="sxs-lookup"><span data-stu-id="babef-106">If you're upgrading a Windows Forms app from .NET Framework or from a previous version of .NET Core (3.0 or later), this article applies to you.</span></span>

<span data-ttu-id="babef-107">En esta página se documentan los siguientes cambios importantes:</span><span class="sxs-lookup"><span data-stu-id="babef-107">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="babef-108">Cambio importante</span><span class="sxs-lookup"><span data-stu-id="babef-108">Breaking change</span></span> | <span data-ttu-id="babef-109">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="babef-109">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="babef-110">Controles eliminados</span><span class="sxs-lookup"><span data-stu-id="babef-110">Removed controls</span></span>](#removed-controls) | <span data-ttu-id="babef-111">3.1</span><span class="sxs-lookup"><span data-stu-id="babef-111">3.1</span></span> |
| [<span data-ttu-id="babef-112">El evento CellFormatting no se produce si se muestra información en pantalla</span><span class="sxs-lookup"><span data-stu-id="babef-112">CellFormatting event not raised if tooltip is shown</span></span>](#cellformatting-event-not-raised-if-tooltip-is-shown) | <span data-ttu-id="babef-113">3.1</span><span class="sxs-lookup"><span data-stu-id="babef-113">3.1</span></span> |
| [<span data-ttu-id="babef-114">Se ha cambiado Control.DefaultFont a Segoe UI 9 pt</span><span class="sxs-lookup"><span data-stu-id="babef-114">Control.DefaultFont changed to Segoe UI 9 pt</span></span>](#default-control-font-changed-to-segoe-ui-9-pt) | <span data-ttu-id="babef-115">3.0</span><span class="sxs-lookup"><span data-stu-id="babef-115">3.0</span></span> |
| [<span data-ttu-id="babef-116">Se ha modernizado FolderBrowserDialog</span><span class="sxs-lookup"><span data-stu-id="babef-116">Modernization of the FolderBrowserDialog</span></span>](#modernization-of-the-folderbrowserdialog) | <span data-ttu-id="babef-117">3.0</span><span class="sxs-lookup"><span data-stu-id="babef-117">3.0</span></span> |
| [<span data-ttu-id="babef-118">Se ha quitado SerializableAttribute de algunos tipos de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="babef-118">SerializableAttribute removed from some Windows Forms types</span></span>](#serializableattribute-removed-from-some-windows-forms-types) | <span data-ttu-id="babef-119">3.0</span><span class="sxs-lookup"><span data-stu-id="babef-119">3.0</span></span> |
| [<span data-ttu-id="babef-120">No se admite el modificador de compatibilidad AllowUpdateChildControlIndexForTabControls</span><span class="sxs-lookup"><span data-stu-id="babef-120">AllowUpdateChildControlIndexForTabControls compatibility switch not supported</span></span>](#allowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported) | <span data-ttu-id="babef-121">3.0</span><span class="sxs-lookup"><span data-stu-id="babef-121">3.0</span></span> |
| [<span data-ttu-id="babef-122">No se admite el modificador de compatibilidad DomainUpDown.UseLegacyScrolling</span><span class="sxs-lookup"><span data-stu-id="babef-122">DomainUpDown.UseLegacyScrolling compatibility switch not supported</span></span>](#domainupdownuselegacyscrolling-compatibility-switch-not-supported) | <span data-ttu-id="babef-123">3.0</span><span class="sxs-lookup"><span data-stu-id="babef-123">3.0</span></span> |
| [<span data-ttu-id="babef-124">No se admite el modificador de compatibilidad DoNotLoadLatestRichEditControl</span><span class="sxs-lookup"><span data-stu-id="babef-124">DoNotLoadLatestRichEditControl compatibility switch not supported</span></span>](#donotloadlatestricheditcontrol-compatibility-switch-not-supported) | <span data-ttu-id="babef-125">3.0</span><span class="sxs-lookup"><span data-stu-id="babef-125">3.0</span></span> |
| [<span data-ttu-id="babef-126">No se admite el modificador de compatibilidad DoNotSupportSelectAllShortcutInMultilineTextBox</span><span class="sxs-lookup"><span data-stu-id="babef-126">DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported</span></span>](#donotsupportselectallshortcutinmultilinetextbox-compatibility-switch-not-supported) | <span data-ttu-id="babef-127">3.0</span><span class="sxs-lookup"><span data-stu-id="babef-127">3.0</span></span> |
| [<span data-ttu-id="babef-128">No se admite el modificador de compatibilidad DontSupportReentrantFilterMessage</span><span class="sxs-lookup"><span data-stu-id="babef-128">DontSupportReentrantFilterMessage compatibility switch not supported</span></span>](#dontsupportreentrantfiltermessage-compatibility-switch-not-supported) | <span data-ttu-id="babef-129">3.0</span><span class="sxs-lookup"><span data-stu-id="babef-129">3.0</span></span> |
| [<span data-ttu-id="babef-130">No se admite el modificador de compatibilidad EnableVisualStyleValidation</span><span class="sxs-lookup"><span data-stu-id="babef-130">EnableVisualStyleValidation compatibility switch not supported</span></span>](#enablevisualstylevalidation-compatibility-switch-not-supported) | <span data-ttu-id="babef-131">3.0</span><span class="sxs-lookup"><span data-stu-id="babef-131">3.0</span></span> |
| [<span data-ttu-id="babef-132">No se admite el modificador de compatibilidad UseLegacyContextMenuStripSourceControlValue</span><span class="sxs-lookup"><span data-stu-id="babef-132">UseLegacyContextMenuStripSourceControlValue compatibility switch not supported</span></span>](#uselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported) | <span data-ttu-id="babef-133">3.0</span><span class="sxs-lookup"><span data-stu-id="babef-133">3.0</span></span> |
| [<span data-ttu-id="babef-134">No se admite el modificador de compatibilidad UseLegacyImages</span><span class="sxs-lookup"><span data-stu-id="babef-134">UseLegacyImages compatibility switch not supported</span></span>](#uselegacyimages-compatibility-switch-not-supported) | <span data-ttu-id="babef-135">3.0</span><span class="sxs-lookup"><span data-stu-id="babef-135">3.0</span></span> |

## <a name="net-core-31"></a><span data-ttu-id="babef-136">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="babef-136">.NET Core 3.1</span></span>

[!INCLUDE[Removed controls](~/includes/core-changes/windowsforms/3.1/remove-controls-3.1.md)]

***

[!INCLUDE[CellFormatting event](~/includes/core-changes/windowsforms/3.1/cellformatting-event-not-raised.md)]

<span data-ttu-id="babef-137">\*\*_</span><span class="sxs-lookup"><span data-stu-id="babef-137">\*\*_</span></span>

## <a name="net-core-30"></a><span data-ttu-id="babef-138">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="babef-138">.NET Core 3.0</span></span>

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

<span data-ttu-id="babef-139">_\*\*</span><span class="sxs-lookup"><span data-stu-id="babef-139">_\*\*</span></span>

## <a name="see-also"></a><span data-ttu-id="babef-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="babef-140">See also</span></span>

- [<span data-ttu-id="babef-141">Migración de una aplicación de Windows Forms a .NET Core</span><span class="sxs-lookup"><span data-stu-id="babef-141">Port a Windows Forms app to .NET Core</span></span>](/dotnet/desktop/winforms/migration/?view=netdesktop-5.0&preserve-view=true)
