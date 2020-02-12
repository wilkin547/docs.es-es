---
title: Cambios importantes en Windows Forms
description: Enumera los cambios importantes en Windows Forms para .NET Core.
ms.date: 01/08/2020
ms.openlocfilehash: 7fba78382d011bc9d489924fa185a44e598c5a76
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2020
ms.locfileid: "77093024"
---
# <a name="breaking-changes-in-windows-forms"></a><span data-ttu-id="a3f98-103">Cambios importantes en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a3f98-103">Breaking changes in Windows Forms</span></span>

<span data-ttu-id="a3f98-104">Se ha agregado compatibilidad con Windows Forms a .NET Core, versión 3.0.</span><span class="sxs-lookup"><span data-stu-id="a3f98-104">Windows Forms support was added to .NET Core in version 3.0.</span></span> <span data-ttu-id="a3f98-105">En este artículo se enumeran los cambios importantes de Windows Forms por versión de .NET Core en la que se han incorporado.</span><span class="sxs-lookup"><span data-stu-id="a3f98-105">This article lists breaking changes for Windows Forms by the .NET Core version in which they were introduced.</span></span> <span data-ttu-id="a3f98-106">Si está actualizando una aplicación de Windows Forms desde .NET Framework o una versión anterior de .NET Core (3.0 o posterior), este artículo se aplica a su caso.</span><span class="sxs-lookup"><span data-stu-id="a3f98-106">If you're upgrading a Windows Forms app from .NET Framework or from a previous version of .NET Core (3.0 or later), this article is applicable to you.</span></span>

<span data-ttu-id="a3f98-107">En esta página se documentan los siguientes cambios importantes:</span><span class="sxs-lookup"><span data-stu-id="a3f98-107">The following breaking changes are documented on this page:</span></span>

- [<span data-ttu-id="a3f98-108">Controles eliminados</span><span class="sxs-lookup"><span data-stu-id="a3f98-108">Removed controls</span></span>](#removed-controls)
- [<span data-ttu-id="a3f98-109">El evento CellFormatting no se produce si se muestra información en pantalla</span><span class="sxs-lookup"><span data-stu-id="a3f98-109">CellFormatting event not raised if tooltip is shown</span></span>](#cellformatting-event-not-raised-if-tooltip-is-shown)
- [<span data-ttu-id="a3f98-110">Se ha cambiado Control.DefaultFont a Segoe UI 9 pt</span><span class="sxs-lookup"><span data-stu-id="a3f98-110">Control.DefaultFont changed to Segoe UI 9 pt</span></span>](#default-control-font-changed-to-segoe-ui-9-pt)
- [<span data-ttu-id="a3f98-111">Se ha modernizado FolderBrowserDialog</span><span class="sxs-lookup"><span data-stu-id="a3f98-111">Modernization of the FolderBrowserDialog</span></span>](#modernization-of-the-folderbrowserdialog)
- [<span data-ttu-id="a3f98-112">Se ha quitado SerializableAttribute de algunos tipos de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a3f98-112">SerializableAttribute removed from some Windows Forms types</span></span>](#serializableattribute-removed-from-some-windows-forms-types)
- [<span data-ttu-id="a3f98-113">No se admite el modificador de compatibilidad AllowUpdateChildControlIndexForTabControls</span><span class="sxs-lookup"><span data-stu-id="a3f98-113">AllowUpdateChildControlIndexForTabControls compatibility switch not supported</span></span>](#allowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported)
- [<span data-ttu-id="a3f98-114">No se admite el modificador de compatibilidad DomainUpDown.UseLegacyScrolling</span><span class="sxs-lookup"><span data-stu-id="a3f98-114">DomainUpDown.UseLegacyScrolling compatibility switch not supported</span></span>](#domainupdownuselegacyscrolling-compatibility-switch-not-supported)
- [<span data-ttu-id="a3f98-115">No se admite el modificador de compatibilidad DoNotLoadLatestRichEditControl</span><span class="sxs-lookup"><span data-stu-id="a3f98-115">DoNotLoadLatestRichEditControl compatibility switch not supported</span></span>](#donotloadlatestricheditcontrol-compatibility-switch-not-supported)
- [<span data-ttu-id="a3f98-116">No se admite el modificador de compatibilidad DoNotSupportSelectAllShortcutInMultilineTextBox</span><span class="sxs-lookup"><span data-stu-id="a3f98-116">DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported</span></span>](#donotsupportselectallshortcutinmultilinetextbox-compatibility-switch-not-supported)
- [<span data-ttu-id="a3f98-117">No se admite el modificador de compatibilidad DontSupportReentrantFilterMessage</span><span class="sxs-lookup"><span data-stu-id="a3f98-117">DontSupportReentrantFilterMessage compatibility switch not supported</span></span>](#dontsupportreentrantfiltermessage-compatibility-switch-not-supported)
- [<span data-ttu-id="a3f98-118">No se admite el modificador de compatibilidad EnableVisualStyleValidation</span><span class="sxs-lookup"><span data-stu-id="a3f98-118">EnableVisualStyleValidation compatibility switch not supported</span></span>](#enablevisualstylevalidation-compatibility-switch-not-supported)
- [<span data-ttu-id="a3f98-119">No se admite el modificador de compatibilidad UseLegacyContextMenuStripSourceControlValue</span><span class="sxs-lookup"><span data-stu-id="a3f98-119">UseLegacyContextMenuStripSourceControlValue compatibility switch not supported</span></span>](#uselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported)
- [<span data-ttu-id="a3f98-120">No se admite el modificador de compatibilidad UseLegacyImages</span><span class="sxs-lookup"><span data-stu-id="a3f98-120">UseLegacyImages compatibility switch not supported</span></span>](#uselegacyimages-compatibility-switch-not-supported)
- [<span data-ttu-id="a3f98-121">Se ha cambiado el acceso para AccessibleObject.RuntimeIDFirstItem</span><span class="sxs-lookup"><span data-stu-id="a3f98-121">Change of access for AccessibleObject.RuntimeIDFirstItem</span></span>](#change-of-access-for-accessibleobjectruntimeidfirstitem)
- [<span data-ttu-id="a3f98-122">Se han quitado las API duplicadas de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a3f98-122">Duplicated APIs removed from Windows Forms</span></span>](#duplicated-apis-removed-from-windows-forms)

## <a name="net-core-31"></a><span data-ttu-id="a3f98-123">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="a3f98-123">.NET Core 3.1</span></span>

[!INCLUDE[Removed controls](~/includes/core-changes/windowsforms/3.1/remove-controls-3.1.md)]

***

[!INCLUDE[CellFormatting event](~/includes/core-changes/windowsforms/3.1/cellformatting-event-not-raised.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="a3f98-124">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="a3f98-124">.NET Core 3.0</span></span>

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

## <a name="see-also"></a><span data-ttu-id="a3f98-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="a3f98-125">See also</span></span>

- [<span data-ttu-id="a3f98-126">Migración de una aplicación de Windows Forms a .NET Core</span><span class="sxs-lookup"><span data-stu-id="a3f98-126">Port a Windows Forms app to .NET Core</span></span>](../porting/winforms.md)
