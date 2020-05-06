---
title: Cambios importantes de .NET Framework a .NET Core
titleSuffix: ''
description: Enumera los cambios importantes de .NET Framework a .NET Core.
ms.date: 12/18/2019
ms.openlocfilehash: df5907e05c6a2aed478d64cc40c5d6f051f92f96
ms.sourcegitcommit: d7666f6e49c57a769612602ea7857b927294ce47
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2020
ms.locfileid: "82595707"
---
# <a name="breaking-changes-for-migration-from-net-framework-to-net-core"></a><span data-ttu-id="9129a-103">Cambios importantes para la migración desde .NET Framework a .NET Core</span><span class="sxs-lookup"><span data-stu-id="9129a-103">Breaking changes for migration from .NET Framework to .NET Core</span></span>

<span data-ttu-id="9129a-104">Si va a migrar una aplicación desde .NET Framework a .NET Core, los cambios más importantes que se enumeran en este artículo pueden afectar a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="9129a-104">If you're migrating an app from .NET Framework to .NET Core, the breaking changes listed in this article may affect you.</span></span> <span data-ttu-id="9129a-105">Los cambios importantes se agrupan por categoría y, dentro de esas categorías, por la versión de .NET Core en la que se realizaron.</span><span class="sxs-lookup"><span data-stu-id="9129a-105">Breaking changes are grouped by category, and within those categories, by the version of .NET Core in which they were introduced.</span></span>

> [!NOTE]
> <span data-ttu-id="9129a-106">Este artículo no es una lista completa de los cambios importantes entre .NET Framework y .NET Core.</span><span class="sxs-lookup"><span data-stu-id="9129a-106">This article is not a complete list of breaking changes between .NET Framework and .NET Core.</span></span> <span data-ttu-id="9129a-107">Aquí se agregan los principales cambios importantes a medida que se conocen.</span><span class="sxs-lookup"><span data-stu-id="9129a-107">The most important breaking changes are added here as we become aware of them.</span></span>

## <a name="core-net-libraries"></a><span data-ttu-id="9129a-108">Bibliotecas de Core .NET</span><span class="sxs-lookup"><span data-stu-id="9129a-108">Core .NET libraries</span></span>

- [<span data-ttu-id="9129a-109">Cambio del valor predeterminado de UseShellExecute</span><span class="sxs-lookup"><span data-stu-id="9129a-109">Change in default value of UseShellExecute</span></span>](#change-in-default-value-of-useshellexecute)
- [<span data-ttu-id="9129a-110">UnauthorizedAccessException producida por FileSystemInfo.Attributes</span><span class="sxs-lookup"><span data-stu-id="9129a-110">UnauthorizedAccessException thrown by FileSystemInfo.Attributes</span></span>](#unauthorizedaccessexception-thrown-by-filesysteminfoattributes)
- [<span data-ttu-id="9129a-111">No se admite el control de excepciones de estado de proceso dañado</span><span class="sxs-lookup"><span data-stu-id="9129a-111">Handling corrupted-process-state exceptions is not supported</span></span>](#handling-corrupted-state-exceptions-is-not-supported)
- [<span data-ttu-id="9129a-112">Las propiedades UriBuilder ya no anteponen caracteres iniciales</span><span class="sxs-lookup"><span data-stu-id="9129a-112">UriBuilder properties no longer prepend leading characters</span></span>](#uribuilder-properties-no-longer-prepend-leading-characters)

### <a name="net-core-21"></a><span data-ttu-id="9129a-113">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="9129a-113">.NET Core 2.1</span></span>

[!INCLUDE[Process.Start changes](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

***

### <a name="net-core-10"></a><span data-ttu-id="9129a-114">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="9129a-114">.NET Core 1.0</span></span>

[!INCLUDE [UnauthorizedAccessException thrown by FileSystemInfo.Attributes](~/includes/core-changes/corefx/1.0/filesysteminfo-attributes-exceptions.md)]

***

[!INCLUDE [corrupted-state-exceptions](~/includes/core-changes/corefx/1.0/corrupted-state-exceptions.md)]

***

[!INCLUDE [uribuilder-behavior-changes](../../../includes/core-changes/corefx/1.0/uribuilder-behavior-changes.md)]

***

## <a name="cryptography"></a><span data-ttu-id="9129a-115">Criptografía</span><span class="sxs-lookup"><span data-stu-id="9129a-115">Cryptography</span></span>

- [<span data-ttu-id="9129a-116">Se respeta el parámetro booleano de SignedCms.ComputeSignature</span><span class="sxs-lookup"><span data-stu-id="9129a-116">Boolean parameter of SignedCms.ComputeSignature is respected</span></span>](#boolean-parameter-of-signedcmscomputesignature-is-respected)

### <a name="net-core-21"></a><span data-ttu-id="9129a-117">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="9129a-117">.NET Core 2.1</span></span>

[!INCLUDE [Boolean parameter of SignedCms.ComputeSignature is respected](~/includes/core-changes/cryptography/2.1/compute-signature-silent-parameter.md)]

***

## <a name="windows-forms"></a><span data-ttu-id="9129a-118">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9129a-118">Windows Forms</span></span>

<span data-ttu-id="9129a-119">Se ha agregado compatibilidad con Windows Forms a .NET Core, versión 3.0.</span><span class="sxs-lookup"><span data-stu-id="9129a-119">Windows Forms support was added to .NET Core in version 3.0.</span></span> <span data-ttu-id="9129a-120">Si va a realizar la migración de una aplicación de Windows Forms desde .NET Framework a .NET Core, los cambios más importantes que se enumeran aquí pueden afectar a los usuarios de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="9129a-120">If you're migrating a Windows Forms app from .NET Framework to .NET Core, the breaking changes listed here may affect your app.</span></span>

- [<span data-ttu-id="9129a-121">Controles eliminados</span><span class="sxs-lookup"><span data-stu-id="9129a-121">Removed controls</span></span>](#removed-controls)
- [<span data-ttu-id="9129a-122">El evento CellFormatting no se produce si se muestra información en pantalla</span><span class="sxs-lookup"><span data-stu-id="9129a-122">CellFormatting event not raised if tooltip is shown</span></span>](#cellformatting-event-not-raised-if-tooltip-is-shown)
- [<span data-ttu-id="9129a-123">Se ha cambiado Control.DefaultFont a Segoe UI 9 pt</span><span class="sxs-lookup"><span data-stu-id="9129a-123">Control.DefaultFont changed to Segoe UI 9 pt</span></span>](#default-control-font-changed-to-segoe-ui-9-pt)
- [<span data-ttu-id="9129a-124">Se ha modernizado FolderBrowserDialog</span><span class="sxs-lookup"><span data-stu-id="9129a-124">Modernization of the FolderBrowserDialog</span></span>](#modernization-of-the-folderbrowserdialog)
- [<span data-ttu-id="9129a-125">Se ha quitado SerializableAttribute de algunos tipos de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9129a-125">SerializableAttribute removed from some Windows Forms types</span></span>](#serializableattribute-removed-from-some-windows-forms-types)
- [<span data-ttu-id="9129a-126">No se admite el modificador de compatibilidad AllowUpdateChildControlIndexForTabControls</span><span class="sxs-lookup"><span data-stu-id="9129a-126">AllowUpdateChildControlIndexForTabControls compatibility switch not supported</span></span>](#allowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported)
- [<span data-ttu-id="9129a-127">No se admite el modificador de compatibilidad DomainUpDown.UseLegacyScrolling</span><span class="sxs-lookup"><span data-stu-id="9129a-127">DomainUpDown.UseLegacyScrolling compatibility switch not supported</span></span>](#domainupdownuselegacyscrolling-compatibility-switch-not-supported)
- [<span data-ttu-id="9129a-128">No se admite el modificador de compatibilidad DoNotLoadLatestRichEditControl</span><span class="sxs-lookup"><span data-stu-id="9129a-128">DoNotLoadLatestRichEditControl compatibility switch not supported</span></span>](#donotloadlatestricheditcontrol-compatibility-switch-not-supported)
- [<span data-ttu-id="9129a-129">No se admite el modificador de compatibilidad DoNotSupportSelectAllShortcutInMultilineTextBox</span><span class="sxs-lookup"><span data-stu-id="9129a-129">DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported</span></span>](#donotsupportselectallshortcutinmultilinetextbox-compatibility-switch-not-supported)
- [<span data-ttu-id="9129a-130">No se admite el modificador de compatibilidad DontSupportReentrantFilterMessage</span><span class="sxs-lookup"><span data-stu-id="9129a-130">DontSupportReentrantFilterMessage compatibility switch not supported</span></span>](#dontsupportreentrantfiltermessage-compatibility-switch-not-supported)
- [<span data-ttu-id="9129a-131">No se admite el modificador de compatibilidad EnableVisualStyleValidation</span><span class="sxs-lookup"><span data-stu-id="9129a-131">EnableVisualStyleValidation compatibility switch not supported</span></span>](#enablevisualstylevalidation-compatibility-switch-not-supported)
- [<span data-ttu-id="9129a-132">No se admite el modificador de compatibilidad UseLegacyContextMenuStripSourceControlValue</span><span class="sxs-lookup"><span data-stu-id="9129a-132">UseLegacyContextMenuStripSourceControlValue compatibility switch not supported</span></span>](#uselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported)
- [<span data-ttu-id="9129a-133">No se admite el modificador de compatibilidad UseLegacyImages</span><span class="sxs-lookup"><span data-stu-id="9129a-133">UseLegacyImages compatibility switch not supported</span></span>](#uselegacyimages-compatibility-switch-not-supported)
- [<span data-ttu-id="9129a-134">Se ha cambiado el acceso para AccessibleObject.RuntimeIDFirstItem</span><span class="sxs-lookup"><span data-stu-id="9129a-134">Change of access for AccessibleObject.RuntimeIDFirstItem</span></span>](#change-of-access-for-accessibleobjectruntimeidfirstitem)
- [<span data-ttu-id="9129a-135">Se han quitado las API duplicadas de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9129a-135">Duplicated APIs removed from Windows Forms</span></span>](#duplicated-apis-removed-from-windows-forms)

### <a name="net-core-31"></a><span data-ttu-id="9129a-136">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="9129a-136">.NET Core 3.1</span></span>

[!INCLUDE[Removed controls](~/includes/core-changes/windowsforms/3.1/remove-controls-3.1.md)]

***

[!INCLUDE[CellFormatting event](~/includes/core-changes/windowsforms/3.1/cellformatting-event-not-raised.md)]

***

### <a name="net-core-30"></a><span data-ttu-id="9129a-137">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="9129a-137">.NET Core 3.0</span></span>

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

## <a name="see-also"></a><span data-ttu-id="9129a-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="9129a-138">See also</span></span>

- [<span data-ttu-id="9129a-139">API que siempre producen excepciones en .NET Core</span><span class="sxs-lookup"><span data-stu-id="9129a-139">APIs that always throw exceptions on .NET Core</span></span>](unsupported-apis.md)
- [<span data-ttu-id="9129a-140">Tecnologías de .NET Framework no disponibles en .NET Core</span><span class="sxs-lookup"><span data-stu-id="9129a-140">.NET Framework technologies unavailable on .NET Core</span></span>](../porting/net-framework-tech-unavailable.md)
