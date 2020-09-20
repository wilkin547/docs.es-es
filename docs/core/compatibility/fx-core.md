---
title: Cambios importantes de .NET Framework a .NET Core
titleSuffix: ''
description: Enumera los cambios importantes de .NET Framework a las versiones de 1.0 a 3.1 de .NET Core.
ms.date: 05/05/2020
ms.openlocfilehash: 5904a359813b6d07bd2a27d882ade4395efe3256
ms.sourcegitcommit: 1e8382d0ce8b5515864f8fbb178b9fd692a7503f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2020
ms.locfileid: "89656371"
---
# <a name="breaking-changes-for-migration-from-net-framework-to-net-core"></a><span data-ttu-id="60a10-103">Cambios importantes para la migración desde .NET Framework a .NET Core</span><span class="sxs-lookup"><span data-stu-id="60a10-103">Breaking changes for migration from .NET Framework to .NET Core</span></span>

<span data-ttu-id="60a10-104">Si va a migrar una aplicación desde .NET Framework a las versiones de 1.0 a 3.1 de .NET Core, los cambios más importantes que se enumeran en este artículo pueden afectarle.</span><span class="sxs-lookup"><span data-stu-id="60a10-104">If you're migrating an app from .NET Framework to .NET Core versions 1.0 through 3.1, the breaking changes listed in this article may affect you.</span></span> <span data-ttu-id="60a10-105">Los cambios importantes se agrupan por categoría y, dentro de esas categorías, por la versión de .NET Core en la que se realizaron.</span><span class="sxs-lookup"><span data-stu-id="60a10-105">Breaking changes are grouped by category, and within those categories, by the version of .NET Core in which they were introduced.</span></span>

> [!NOTE]
> <span data-ttu-id="60a10-106">Este artículo no es una lista completa de los cambios importantes entre .NET Framework y .NET Core.</span><span class="sxs-lookup"><span data-stu-id="60a10-106">This article is not a complete list of breaking changes between .NET Framework and .NET Core.</span></span> <span data-ttu-id="60a10-107">Aquí se agregan los principales cambios importantes a medida que se conocen.</span><span class="sxs-lookup"><span data-stu-id="60a10-107">The most important breaking changes are added here as we become aware of them.</span></span>

## <a name="core-net-libraries"></a><span data-ttu-id="60a10-108">Bibliotecas de Core .NET</span><span class="sxs-lookup"><span data-stu-id="60a10-108">Core .NET libraries</span></span>

- [<span data-ttu-id="60a10-109">Cambio del valor predeterminado de UseShellExecute</span><span class="sxs-lookup"><span data-stu-id="60a10-109">Change in default value of UseShellExecute</span></span>](#change-in-default-value-of-useshellexecute)
- [<span data-ttu-id="60a10-110">UnauthorizedAccessException producida por FileSystemInfo.Attributes</span><span class="sxs-lookup"><span data-stu-id="60a10-110">UnauthorizedAccessException thrown by FileSystemInfo.Attributes</span></span>](#unauthorizedaccessexception-thrown-by-filesysteminfoattributes)
- [<span data-ttu-id="60a10-111">No se admite el control de excepciones de estado de proceso dañado</span><span class="sxs-lookup"><span data-stu-id="60a10-111">Handling corrupted-process-state exceptions is not supported</span></span>](#handling-corrupted-state-exceptions-is-not-supported)
- [<span data-ttu-id="60a10-112">Las propiedades UriBuilder ya no anteponen caracteres iniciales</span><span class="sxs-lookup"><span data-stu-id="60a10-112">UriBuilder properties no longer prepend leading characters</span></span>](#uribuilder-properties-no-longer-prepend-leading-characters)
- [<span data-ttu-id="60a10-113">Process.StartInfo produce una excepción InvalidOperationException para los procesos que no se iniciaron</span><span class="sxs-lookup"><span data-stu-id="60a10-113">Process.StartInfo throws InvalidOperationException for processes you didn't start</span></span>](#processstartinfo-throws-invalidoperationexception-for-processes-you-didnt-start)

### <a name="net-core-21"></a><span data-ttu-id="60a10-114">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="60a10-114">.NET Core 2.1</span></span>

[!INCLUDE[Process.Start changes](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

***

### <a name="net-core-10"></a><span data-ttu-id="60a10-115">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="60a10-115">.NET Core 1.0</span></span>

[!INCLUDE [UnauthorizedAccessException thrown by FileSystemInfo.Attributes](~/includes/core-changes/corefx/1.0/filesysteminfo-attributes-exceptions.md)]

***

[!INCLUDE [corrupted-state-exceptions](~/includes/core-changes/corefx/1.0/corrupted-state-exceptions.md)]

***

[!INCLUDE [uribuilder-behavior-changes](../../../includes/core-changes/corefx/1.0/uribuilder-behavior-changes.md)]

***

[!INCLUDE [startinfo-throws-exception](../../../includes/core-changes/corefx/1.0/startinfo-throws-exception.md)]

***

## <a name="cryptography"></a><span data-ttu-id="60a10-116">Criptografía</span><span class="sxs-lookup"><span data-stu-id="60a10-116">Cryptography</span></span>

- [<span data-ttu-id="60a10-117">Se respeta el parámetro booleano de SignedCms.ComputeSignature</span><span class="sxs-lookup"><span data-stu-id="60a10-117">Boolean parameter of SignedCms.ComputeSignature is respected</span></span>](#boolean-parameter-of-signedcmscomputesignature-is-respected)

### <a name="net-core-21"></a><span data-ttu-id="60a10-118">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="60a10-118">.NET Core 2.1</span></span>

[!INCLUDE [Boolean parameter of SignedCms.ComputeSignature is respected](~/includes/core-changes/cryptography/2.1/compute-signature-silent-parameter.md)]

***

## <a name="msbuild"></a><span data-ttu-id="60a10-119">MSBuild</span><span class="sxs-lookup"><span data-stu-id="60a10-119">MSBuild</span></span>

- [<span data-ttu-id="60a10-120">Cambio de nombre de archivo de manifiesto del recurso</span><span class="sxs-lookup"><span data-stu-id="60a10-120">Resource manifest file name change</span></span>](#resource-manifest-file-name-change)

### <a name="net-core-30"></a><span data-ttu-id="60a10-121">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="60a10-121">.NET Core 3.0</span></span>

[!INCLUDE[Resource file names](~/includes/core-changes/msbuild/3.0/resource-manifest-name.md)]

***

## <a name="networking"></a><span data-ttu-id="60a10-122">Redes</span><span class="sxs-lookup"><span data-stu-id="60a10-122">Networking</span></span>

- [<span data-ttu-id="60a10-123">WebClient.CancelAsync no siempre se cancela inmediatamente</span><span class="sxs-lookup"><span data-stu-id="60a10-123">WebClient.CancelAsync doesn't always cancel immediately</span></span>](#webclientcancelasync-doesnt-always-cancel-immediately)

### <a name="net-core-20"></a><span data-ttu-id="60a10-124">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="60a10-124">.NET Core 2.0</span></span>

[!INCLUDE [behavior-change-webclient-cancelasync](../../../includes/core-changes/networking/2.0/behavior-change-webclient-cancelasync.md)]

***

## <a name="windows-forms"></a><span data-ttu-id="60a10-125">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="60a10-125">Windows Forms</span></span>

<span data-ttu-id="60a10-126">Se ha agregado compatibilidad con Windows Forms a .NET Core, versión 3.0.</span><span class="sxs-lookup"><span data-stu-id="60a10-126">Windows Forms support was added to .NET Core in version 3.0.</span></span> <span data-ttu-id="60a10-127">Si va a realizar la migración de una aplicación de Windows Forms desde .NET Framework a .NET Core, los cambios más importantes que se enumeran aquí pueden afectar a los usuarios de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="60a10-127">If you're migrating a Windows Forms app from .NET Framework to .NET Core, the breaking changes listed here may affect your app.</span></span>

- [<span data-ttu-id="60a10-128">Controles eliminados</span><span class="sxs-lookup"><span data-stu-id="60a10-128">Removed controls</span></span>](#removed-controls)
- [<span data-ttu-id="60a10-129">El evento CellFormatting no se produce si se muestra información en pantalla</span><span class="sxs-lookup"><span data-stu-id="60a10-129">CellFormatting event not raised if tooltip is shown</span></span>](#cellformatting-event-not-raised-if-tooltip-is-shown)
- [<span data-ttu-id="60a10-130">Se ha cambiado Control.DefaultFont a Segoe UI 9 pt</span><span class="sxs-lookup"><span data-stu-id="60a10-130">Control.DefaultFont changed to Segoe UI 9 pt</span></span>](#default-control-font-changed-to-segoe-ui-9-pt)
- [<span data-ttu-id="60a10-131">Se ha modernizado FolderBrowserDialog</span><span class="sxs-lookup"><span data-stu-id="60a10-131">Modernization of the FolderBrowserDialog</span></span>](#modernization-of-the-folderbrowserdialog)
- [<span data-ttu-id="60a10-132">Se ha quitado SerializableAttribute de algunos tipos de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="60a10-132">SerializableAttribute removed from some Windows Forms types</span></span>](#serializableattribute-removed-from-some-windows-forms-types)
- [<span data-ttu-id="60a10-133">No se admite el modificador de compatibilidad AllowUpdateChildControlIndexForTabControls</span><span class="sxs-lookup"><span data-stu-id="60a10-133">AllowUpdateChildControlIndexForTabControls compatibility switch not supported</span></span>](#allowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported)
- [<span data-ttu-id="60a10-134">No se admite el modificador de compatibilidad DomainUpDown.UseLegacyScrolling</span><span class="sxs-lookup"><span data-stu-id="60a10-134">DomainUpDown.UseLegacyScrolling compatibility switch not supported</span></span>](#domainupdownuselegacyscrolling-compatibility-switch-not-supported)
- [<span data-ttu-id="60a10-135">No se admite el modificador de compatibilidad DoNotLoadLatestRichEditControl</span><span class="sxs-lookup"><span data-stu-id="60a10-135">DoNotLoadLatestRichEditControl compatibility switch not supported</span></span>](#donotloadlatestricheditcontrol-compatibility-switch-not-supported)
- [<span data-ttu-id="60a10-136">No se admite el modificador de compatibilidad DoNotSupportSelectAllShortcutInMultilineTextBox</span><span class="sxs-lookup"><span data-stu-id="60a10-136">DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported</span></span>](#donotsupportselectallshortcutinmultilinetextbox-compatibility-switch-not-supported)
- [<span data-ttu-id="60a10-137">No se admite el modificador de compatibilidad DontSupportReentrantFilterMessage</span><span class="sxs-lookup"><span data-stu-id="60a10-137">DontSupportReentrantFilterMessage compatibility switch not supported</span></span>](#dontsupportreentrantfiltermessage-compatibility-switch-not-supported)
- [<span data-ttu-id="60a10-138">No se admite el modificador de compatibilidad EnableVisualStyleValidation</span><span class="sxs-lookup"><span data-stu-id="60a10-138">EnableVisualStyleValidation compatibility switch not supported</span></span>](#enablevisualstylevalidation-compatibility-switch-not-supported)
- [<span data-ttu-id="60a10-139">No se admite el modificador de compatibilidad UseLegacyContextMenuStripSourceControlValue</span><span class="sxs-lookup"><span data-stu-id="60a10-139">UseLegacyContextMenuStripSourceControlValue compatibility switch not supported</span></span>](#uselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported)
- [<span data-ttu-id="60a10-140">No se admite el modificador de compatibilidad UseLegacyImages</span><span class="sxs-lookup"><span data-stu-id="60a10-140">UseLegacyImages compatibility switch not supported</span></span>](#uselegacyimages-compatibility-switch-not-supported)

### <a name="net-core-31"></a><span data-ttu-id="60a10-141">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="60a10-141">.NET Core 3.1</span></span>

[!INCLUDE[Removed controls](~/includes/core-changes/windowsforms/3.1/remove-controls-3.1.md)]

***

[!INCLUDE[CellFormatting event](~/includes/core-changes/windowsforms/3.1/cellformatting-event-not-raised.md)]

***

### <a name="net-core-30"></a><span data-ttu-id="60a10-142">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="60a10-142">.NET Core 3.0</span></span>

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

## <a name="see-also"></a><span data-ttu-id="60a10-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="60a10-143">See also</span></span>

- [<span data-ttu-id="60a10-144">API que siempre producen excepciones en .NET Core</span><span class="sxs-lookup"><span data-stu-id="60a10-144">APIs that always throw exceptions on .NET Core</span></span>](unsupported-apis.md)
- [<span data-ttu-id="60a10-145">Tecnologías de .NET Framework no disponibles en .NET Core</span><span class="sxs-lookup"><span data-stu-id="60a10-145">.NET Framework technologies unavailable on .NET Core</span></span>](../porting/net-framework-tech-unavailable.md)
