---
title: Cambios importantes de .NET Framework a .NET Core
description: Enumera los cambios importantes de .NET Framework a .NET Core.
ms.date: 12/18/2019
ms.openlocfilehash: 6959bffab62cabc524062231db989de45c8c1498
ms.sourcegitcommit: ed3f926b6cdd372037bbcc214dc8f08a70366390
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2020
ms.locfileid: "76116489"
---
# <a name="breaking-changes-for-migration-from-net-framework-to-net-core"></a><span data-ttu-id="bf512-103">Cambios importantes para la migración desde .NET Framework a .NET Core</span><span class="sxs-lookup"><span data-stu-id="bf512-103">Breaking changes for migration from .NET Framework to .NET Core</span></span>

<span data-ttu-id="bf512-104">Si va a migrar una aplicación desde .NET Framework a .NET Core, los cambios más importantes que se enumeran en este artículo pueden afectar a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="bf512-104">If you're migrating an app from .NET Framework to .NET Core, the breaking changes listed in this article may affect you.</span></span> <span data-ttu-id="bf512-105">Los cambios importantes se agrupan por categoría y, dentro de esas categorías, por la versión de .NET Core en la que se realizaron.</span><span class="sxs-lookup"><span data-stu-id="bf512-105">Breaking changes are grouped by category, and within those categories, by the version of .NET Core they were introduced in.</span></span>

> [!NOTE]
> <span data-ttu-id="bf512-106">Este artículo no es una lista completa de los cambios importantes entre .NET Framework y .NET Core.</span><span class="sxs-lookup"><span data-stu-id="bf512-106">This article is not a complete list of breaking changes between .NET Framework and .NET Core.</span></span> <span data-ttu-id="bf512-107">Aquí se agregan los principales cambios importantes a medida que se conocen.</span><span class="sxs-lookup"><span data-stu-id="bf512-107">The most important breaking changes are added here as we become aware of them.</span></span>

## <a name="corefx"></a><span data-ttu-id="bf512-108">CoreFX</span><span class="sxs-lookup"><span data-stu-id="bf512-108">CoreFx</span></span>

- [<span data-ttu-id="bf512-109">Cambio del valor predeterminado de UseShellExecute</span><span class="sxs-lookup"><span data-stu-id="bf512-109">Change in default value of UseShellExecute</span></span>](#change-in-default-value-of-useshellexecute)

### <a name="net-core-21"></a><span data-ttu-id="bf512-110">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="bf512-110">.NET Core 2.1</span></span>

[!INCLUDE[Process.Start changes](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

***

## <a name="windows-forms"></a><span data-ttu-id="bf512-111">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bf512-111">Windows Forms</span></span>

<span data-ttu-id="bf512-112">Se ha agregado compatibilidad con Windows Forms a .NET Core, versión 3.0.</span><span class="sxs-lookup"><span data-stu-id="bf512-112">Windows Forms support was added to .NET Core in version 3.0.</span></span> <span data-ttu-id="bf512-113">Si va a realizar la migración de una aplicación de Windows Forms desde .NET Framework a .NET Core, los cambios más importantes que se enumeran aquí pueden afectar a los usuarios de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="bf512-113">If you're migrating a Windows Forms app from .NET Framework to .NET Core, the breaking changes listed here may affect your app.</span></span>

- [<span data-ttu-id="bf512-114">Controles eliminados</span><span class="sxs-lookup"><span data-stu-id="bf512-114">Removed controls</span></span>](#removed-controls)
- [<span data-ttu-id="bf512-115">El evento CellFormatting no se produce si se muestra información en pantalla.</span><span class="sxs-lookup"><span data-stu-id="bf512-115">CellFormatting event not raised if tooltip is shown</span></span>](#cellformatting-event-not-raised-if-tooltip-is-shown)
- [<span data-ttu-id="bf512-116">Se ha cambiado Control.DefaultFont a Segoe UI 9 pt.</span><span class="sxs-lookup"><span data-stu-id="bf512-116">Control.DefaultFont changed to Segoe UI 9 pt</span></span>](#default-control-font-changed-to-segoe-ui-9-pt)
- [<span data-ttu-id="bf512-117">Se ha modernizado FolderBrowserDialog.</span><span class="sxs-lookup"><span data-stu-id="bf512-117">Modernization of the FolderBrowserDialog</span></span>](#modernization-of-the-folderbrowserdialog)
- [<span data-ttu-id="bf512-118">Se ha quitado el atributo SerializableAttribute de algunos tipos de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="bf512-118">SerializableAttribute removed from some Windows Forms types</span></span>](#serializableattribute-removed-from-some-windows-forms-types)
- [<span data-ttu-id="bf512-119">No se admite el modificador de compatibilidad AllowUpdateChildControlIndexForTabControls.</span><span class="sxs-lookup"><span data-stu-id="bf512-119">AllowUpdateChildControlIndexForTabControls compatibility switch not supported</span></span>](#allowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported)
- [<span data-ttu-id="bf512-120">No se admite el modificador de compatibilidad DomainUpDown.UseLegacyScrolling.</span><span class="sxs-lookup"><span data-stu-id="bf512-120">DomainUpDown.UseLegacyScrolling compatibility switch not supported</span></span>](#domainupdownuselegacyscrolling-compatibility-switch-not-supported)
- [<span data-ttu-id="bf512-121">No se admite el modificador de compatibilidad DoNotLoadLatestRichEditControl.</span><span class="sxs-lookup"><span data-stu-id="bf512-121">DoNotLoadLatestRichEditControl compatibility switch not supported</span></span>](#donotloadlatestricheditcontrol-compatibility-switch-not-supported)
- [<span data-ttu-id="bf512-122">No se admite el modificador de compatibilidad DoNotSupportSelectAllShortcutInMultilineTextBox.</span><span class="sxs-lookup"><span data-stu-id="bf512-122">DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported</span></span>](#donotsupportselectallshortcutinmultilinetextbox-compatibility-switch-not-supported)
- [<span data-ttu-id="bf512-123">No se admite el modificador de compatibilidad DontSupportReentrantFilterMessage.</span><span class="sxs-lookup"><span data-stu-id="bf512-123">DontSupportReentrantFilterMessage compatibility switch not supported</span></span>](#dontsupportreentrantfiltermessage-compatibility-switch-not-supported)
- [<span data-ttu-id="bf512-124">No se admite el modificador de compatibilidad EnableVisualStyleValidation.</span><span class="sxs-lookup"><span data-stu-id="bf512-124">EnableVisualStyleValidation compatibility switch not supported</span></span>](#enablevisualstylevalidation-compatibility-switch-not-supported)
- [<span data-ttu-id="bf512-125">No se admite el modificador de compatibilidad UseLegacyContextMenuStripSourceControlValue.</span><span class="sxs-lookup"><span data-stu-id="bf512-125">UseLegacyContextMenuStripSourceControlValue compatibility switch not supported</span></span>](#uselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported)
- [<span data-ttu-id="bf512-126">No se admite el modificador de compatibilidad UseLegacyImages.</span><span class="sxs-lookup"><span data-stu-id="bf512-126">UseLegacyImages compatibility switch not supported</span></span>](#uselegacyimages-compatibility-switch-not-supported)
- [<span data-ttu-id="bf512-127">Se ha cambiado el acceso para AccessibleObject.RuntimeIDFirstItem.</span><span class="sxs-lookup"><span data-stu-id="bf512-127">Change of access for AccessibleObject.RuntimeIDFirstItem</span></span>](#change-of-access-for-accessibleobjectruntimeidfirstitem)
- [<span data-ttu-id="bf512-128">Se han quitado las API duplicadas de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="bf512-128">Duplicated APIs removed from Windows Forms</span></span>](#duplicated-apis-removed-from-windows-forms)

### <a name="net-core-31"></a><span data-ttu-id="bf512-129">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="bf512-129">.NET Core 3.1</span></span>

[!INCLUDE[Removed controls](~/includes/core-changes/windowsforms/3.1/remove-controls-3.1.md)]

***

[!INCLUDE[CellFormatting event](~/includes/core-changes/windowsforms/3.1/cellformatting-event-not-raised.md)]

***

### <a name="net-core-30"></a><span data-ttu-id="bf512-130">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="bf512-130">.NET Core 3.0</span></span>

[!INCLUDE[Control.DefaultFont changed to Segoe UI 9 pt](~/includes/core-changes/windowsforms/3.0/control-defaultfont-changed.md)]

***

[!INCLUDE[Modernization of the FolderBrowserDialog](~/includes/core-changes/windowsforms/3.0/modernized-folderbrowserdialog.md)]

***

[!INCLUDE[SerializableAttribute removed from some Windows Forms types](~/includes/core-changes/windowsforms/3.0/remove-serializationattribute.md)]

***

[!INCLUDE[AllowUpdateChildControlIndexForTabControls compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-allowupdatechildcontrolindexfortabcontrols.md)]

***

[!INCLUDE[DomainUpDown.UseLegacyScrolling compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacyscrolling.md)]

***

[!INCLUDE[DoNotLoadLatestRichEditControl compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-donotloadlatestricheditcontrol.md)]

***

[!INCLUDE[DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-donotsupportselectallshortcutinmultilinetextbox.md)]

***

[!INCLUDE[DontSupportReentrantFilterMessage compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-dontsupportreentrantfiltermessage.md)]

***

[!INCLUDE[EnableVisualStyleValidation compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-enablevisualstylevalidation.md)]

***

[!INCLUDE[UseLegacyContextMenuStripSourceControlValue compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacycontextmenustripsourcecontrolvalue.md)]

***

[!INCLUDE[UseLegacyImages compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacyimages.md)]

***

[!INCLUDE[Change of access for AccessibleObject.RuntimeIDFirstItem](~/includes/core-changes/windowsforms/3.0/changed-access-for-runtimeidfirstitem.md)]

***

[!INCLUDE[Duplicated APIs removed from Windows Forms](~/includes/core-changes/windowsforms/3.0/remove-duplicated-apis.md)]

***

## <a name="see-also"></a><span data-ttu-id="bf512-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="bf512-131">See also</span></span>

- [<span data-ttu-id="bf512-132">API que siempre producen excepciones en .NET Core</span><span class="sxs-lookup"><span data-stu-id="bf512-132">APIs that always throw exceptions on .NET Core</span></span>](unsupported-apis.md)
- [<span data-ttu-id="bf512-133">Tecnologías de .NET Framework no disponibles en .NET Core</span><span class="sxs-lookup"><span data-stu-id="bf512-133">.NET Framework technologies unavailable on .NET Core</span></span>](../porting/net-framework-tech-unavailable.md)
