---
title: Cambios importantes en Windows Forms
description: Enumera los cambios importantes en Windows Forms para .NET Core.
ms.date: 01/08/2020
ms.openlocfilehash: 25c568a8a0092a9c4874419c64c7dcebea4dce9e
ms.sourcegitcommit: 2b3b2d684259463ddfc76ad680e5e09fdc1984d2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2020
ms.locfileid: "80888151"
---
# <a name="breaking-changes-in-windows-forms"></a><span data-ttu-id="143cd-103">Cambios importantes en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="143cd-103">Breaking changes in Windows Forms</span></span>

<span data-ttu-id="143cd-104">Se ha agregado compatibilidad con Windows Forms a .NET Core, versión 3.0.</span><span class="sxs-lookup"><span data-stu-id="143cd-104">Windows Forms support was added to .NET Core in version 3.0.</span></span> <span data-ttu-id="143cd-105">En este artículo se enumeran los cambios importantes de Windows Forms por versión de .NET Core en la que se han incorporado.</span><span class="sxs-lookup"><span data-stu-id="143cd-105">This article lists breaking changes for Windows Forms by the .NET Core version in which they were introduced.</span></span> <span data-ttu-id="143cd-106">Si está actualizando una aplicación de Windows Forms desde .NET Framework o una versión anterior de .NET Core (3.0 o posterior), este artículo se aplica a su caso.</span><span class="sxs-lookup"><span data-stu-id="143cd-106">If you're upgrading a Windows Forms app from .NET Framework or from a previous version of .NET Core (3.0 or later), this article is applicable to you.</span></span>

<span data-ttu-id="143cd-107">En esta página se documentan los siguientes cambios importantes:</span><span class="sxs-lookup"><span data-stu-id="143cd-107">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="143cd-108">Cambio importante</span><span class="sxs-lookup"><span data-stu-id="143cd-108">Breaking change</span></span> | <span data-ttu-id="143cd-109">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="143cd-109">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="143cd-110">Las API de WinForms inician ahora la excepción ArgumentNullException</span><span class="sxs-lookup"><span data-stu-id="143cd-110">WinForms APIs now throw ArgumentNullException</span></span>](#winforms-apis-now-throw-argumentnullexception) | <span data-ttu-id="143cd-111">5.0</span><span class="sxs-lookup"><span data-stu-id="143cd-111">5.0</span></span> |
| [<span data-ttu-id="143cd-112">Controles eliminados</span><span class="sxs-lookup"><span data-stu-id="143cd-112">Removed controls</span></span>](#removed-controls) | <span data-ttu-id="143cd-113">3.1</span><span class="sxs-lookup"><span data-stu-id="143cd-113">3.1</span></span> |
| [<span data-ttu-id="143cd-114">El evento CellFormatting no se produce si se muestra información en pantalla</span><span class="sxs-lookup"><span data-stu-id="143cd-114">CellFormatting event not raised if tooltip is shown</span></span>](#cellformatting-event-not-raised-if-tooltip-is-shown) | <span data-ttu-id="143cd-115">3.1</span><span class="sxs-lookup"><span data-stu-id="143cd-115">3.1</span></span> |
| [<span data-ttu-id="143cd-116">Se ha cambiado Control.DefaultFont a Segoe UI 9 pt</span><span class="sxs-lookup"><span data-stu-id="143cd-116">Control.DefaultFont changed to Segoe UI 9 pt</span></span>](#default-control-font-changed-to-segoe-ui-9-pt) | <span data-ttu-id="143cd-117">3.0</span><span class="sxs-lookup"><span data-stu-id="143cd-117">3.0</span></span> |
| [<span data-ttu-id="143cd-118">Se ha modernizado FolderBrowserDialog</span><span class="sxs-lookup"><span data-stu-id="143cd-118">Modernization of the FolderBrowserDialog</span></span>](#modernization-of-the-folderbrowserdialog) | <span data-ttu-id="143cd-119">3.0</span><span class="sxs-lookup"><span data-stu-id="143cd-119">3.0</span></span> |
| [<span data-ttu-id="143cd-120">Se ha quitado SerializableAttribute de algunos tipos de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="143cd-120">SerializableAttribute removed from some Windows Forms types</span></span>](#serializableattribute-removed-from-some-windows-forms-types) | <span data-ttu-id="143cd-121">3.0</span><span class="sxs-lookup"><span data-stu-id="143cd-121">3.0</span></span> |
| [<span data-ttu-id="143cd-122">No se admite el modificador de compatibilidad AllowUpdateChildControlIndexForTabControls</span><span class="sxs-lookup"><span data-stu-id="143cd-122">AllowUpdateChildControlIndexForTabControls compatibility switch not supported</span></span>](#allowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported) | <span data-ttu-id="143cd-123">3.0</span><span class="sxs-lookup"><span data-stu-id="143cd-123">3.0</span></span> |
| [<span data-ttu-id="143cd-124">No se admite el modificador de compatibilidad DomainUpDown.UseLegacyScrolling</span><span class="sxs-lookup"><span data-stu-id="143cd-124">DomainUpDown.UseLegacyScrolling compatibility switch not supported</span></span>](#domainupdownuselegacyscrolling-compatibility-switch-not-supported) | <span data-ttu-id="143cd-125">3.0</span><span class="sxs-lookup"><span data-stu-id="143cd-125">3.0</span></span> |
| [<span data-ttu-id="143cd-126">No se admite el modificador de compatibilidad DoNotLoadLatestRichEditControl</span><span class="sxs-lookup"><span data-stu-id="143cd-126">DoNotLoadLatestRichEditControl compatibility switch not supported</span></span>](#donotloadlatestricheditcontrol-compatibility-switch-not-supported) | <span data-ttu-id="143cd-127">3.0</span><span class="sxs-lookup"><span data-stu-id="143cd-127">3.0</span></span> |
| [<span data-ttu-id="143cd-128">No se admite el modificador de compatibilidad DoNotSupportSelectAllShortcutInMultilineTextBox</span><span class="sxs-lookup"><span data-stu-id="143cd-128">DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported</span></span>](#donotsupportselectallshortcutinmultilinetextbox-compatibility-switch-not-supported) | <span data-ttu-id="143cd-129">3.0</span><span class="sxs-lookup"><span data-stu-id="143cd-129">3.0</span></span> |
| [<span data-ttu-id="143cd-130">No se admite el modificador de compatibilidad DontSupportReentrantFilterMessage</span><span class="sxs-lookup"><span data-stu-id="143cd-130">DontSupportReentrantFilterMessage compatibility switch not supported</span></span>](#dontsupportreentrantfiltermessage-compatibility-switch-not-supported) | <span data-ttu-id="143cd-131">3.0</span><span class="sxs-lookup"><span data-stu-id="143cd-131">3.0</span></span> |
| [<span data-ttu-id="143cd-132">No se admite el modificador de compatibilidad EnableVisualStyleValidation</span><span class="sxs-lookup"><span data-stu-id="143cd-132">EnableVisualStyleValidation compatibility switch not supported</span></span>](#enablevisualstylevalidation-compatibility-switch-not-supported) | <span data-ttu-id="143cd-133">3.0</span><span class="sxs-lookup"><span data-stu-id="143cd-133">3.0</span></span> |
| [<span data-ttu-id="143cd-134">No se admite el modificador de compatibilidad UseLegacyContextMenuStripSourceControlValue</span><span class="sxs-lookup"><span data-stu-id="143cd-134">UseLegacyContextMenuStripSourceControlValue compatibility switch not supported</span></span>](#uselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported) | <span data-ttu-id="143cd-135">3.0</span><span class="sxs-lookup"><span data-stu-id="143cd-135">3.0</span></span> |
| [<span data-ttu-id="143cd-136">No se admite el modificador de compatibilidad UseLegacyImages</span><span class="sxs-lookup"><span data-stu-id="143cd-136">UseLegacyImages compatibility switch not supported</span></span>](#uselegacyimages-compatibility-switch-not-supported) | <span data-ttu-id="143cd-137">3.0</span><span class="sxs-lookup"><span data-stu-id="143cd-137">3.0</span></span> |
| [<span data-ttu-id="143cd-138">Se ha cambiado el acceso para AccessibleObject.RuntimeIDFirstItem</span><span class="sxs-lookup"><span data-stu-id="143cd-138">Change of access for AccessibleObject.RuntimeIDFirstItem</span></span>](#change-of-access-for-accessibleobjectruntimeidfirstitem) | <span data-ttu-id="143cd-139">3.0</span><span class="sxs-lookup"><span data-stu-id="143cd-139">3.0</span></span> |
| [<span data-ttu-id="143cd-140">Se han quitado las API duplicadas de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="143cd-140">Duplicated APIs removed from Windows Forms</span></span>](#duplicated-apis-removed-from-windows-forms) | <span data-ttu-id="143cd-141">3.0</span><span class="sxs-lookup"><span data-stu-id="143cd-141">3.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="143cd-142">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="143cd-142">.NET 5.0</span></span>

[!INCLUDE [null-args-cause-argumentnullexception](../../../includes/core-changes/windowsforms/5.0/null-args-cause-argumentnullexception.md)]

***

## <a name="net-core-31"></a><span data-ttu-id="143cd-143">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="143cd-143">.NET Core 3.1</span></span>

[!INCLUDE[Removed controls](~/includes/core-changes/windowsforms/3.1/remove-controls-3.1.md)]

***

[!INCLUDE[CellFormatting event](~/includes/core-changes/windowsforms/3.1/cellformatting-event-not-raised.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="143cd-144">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="143cd-144">.NET Core 3.0</span></span>

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

[!INCLUDE[Change of access for AccessibleObject.RuntimeIDFirstItem](~/includes/core-changes/windowsforms/3.0/changed-access-for-runtimeidfirstitem.md)]

***

[!INCLUDE[Duplicated APIs removed from Windows Forms](~/includes/core-changes/windowsforms/3.0/remove-duplicated-apis.md)]

***

## <a name="see-also"></a><span data-ttu-id="143cd-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="143cd-145">See also</span></span>

- [<span data-ttu-id="143cd-146">Migración de una aplicación de Windows Forms a .NET Core</span><span class="sxs-lookup"><span data-stu-id="143cd-146">Port a Windows Forms app to .NET Core</span></span>](../porting/winforms.md)
