---
title: Cambios importantes de .NET Framework a .NET Core
titleSuffix: ''
description: Enumera los cambios importantes de .NET Framework a .NET Core.
ms.date: 12/18/2019
ms.openlocfilehash: f712be14d7debc4b3008f8459e6ee925754b25f0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "77449415"
---
# <a name="breaking-changes-for-migration-from-net-framework-to-net-core"></a>Cambios importantes para la migración desde .NET Framework a .NET Core

Si va a migrar una aplicación desde .NET Framework a .NET Core, los cambios más importantes que se enumeran en este artículo pueden afectar a los usuarios. Los cambios importantes se agrupan por categoría y, dentro de esas categorías, por la versión de .NET Core en la que se realizaron.

> [!NOTE]
> Este artículo no es una lista completa de los cambios importantes entre .NET Framework y .NET Core. Aquí se agregan los principales cambios importantes a medida que se conocen.

## <a name="corefx"></a>CoreFX

- [Cambio del valor predeterminado de UseShellExecute](#change-in-default-value-of-useshellexecute)
- [UnauthorizedAccessException producida por FileSystemInfo.Attributes](#unauthorizedaccessexception-thrown-by-filesysteminfoattributes)

### <a name="net-core-21"></a>.NET Core 2.1

[!INCLUDE[Process.Start changes](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

***

### <a name="net-core-10"></a>.NET Core 1.0

[!INCLUDE [UnauthorizedAccessException thrown by FileSystemInfo.Attributes](~/includes/core-changes/corefx/1.0/filesysteminfo-attributes-exceptions.md)]

***

## <a name="cryptography"></a>Criptografía

- [Se respeta el parámetro booleano de SignedCms.ComputeSignature](#boolean-parameter-of-signedcmscomputesignature-is-respected)

### <a name="net-core-21"></a>.NET Core 2.1

[!INCLUDE [Boolean parameter of SignedCms.ComputeSignature is respected](~/includes/core-changes/cryptography/2.1/compute-signature-silent-parameter.md)]

***

## <a name="windows-forms"></a>Windows Forms

Se ha agregado compatibilidad con Windows Forms a .NET Core, versión 3.0. Si va a realizar la migración de una aplicación de Windows Forms desde .NET Framework a .NET Core, los cambios más importantes que se enumeran aquí pueden afectar a los usuarios de la aplicación.

- [Controles eliminados](#removed-controls)
- [El evento CellFormatting no se produce si se muestra información en pantalla](#cellformatting-event-not-raised-if-tooltip-is-shown)
- [Se ha cambiado Control.DefaultFont a Segoe UI 9 pt](#default-control-font-changed-to-segoe-ui-9-pt)
- [Se ha modernizado FolderBrowserDialog](#modernization-of-the-folderbrowserdialog)
- [Se ha quitado SerializableAttribute de algunos tipos de Windows Forms](#serializableattribute-removed-from-some-windows-forms-types)
- [No se admite el modificador de compatibilidad AllowUpdateChildControlIndexForTabControls](#allowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported)
- [No se admite el modificador de compatibilidad DomainUpDown.UseLegacyScrolling](#domainupdownuselegacyscrolling-compatibility-switch-not-supported)
- [No se admite el modificador de compatibilidad DoNotLoadLatestRichEditControl](#donotloadlatestricheditcontrol-compatibility-switch-not-supported)
- [No se admite el modificador de compatibilidad DoNotSupportSelectAllShortcutInMultilineTextBox](#donotsupportselectallshortcutinmultilinetextbox-compatibility-switch-not-supported)
- [No se admite el modificador de compatibilidad DontSupportReentrantFilterMessage](#dontsupportreentrantfiltermessage-compatibility-switch-not-supported)
- [No se admite el modificador de compatibilidad EnableVisualStyleValidation](#enablevisualstylevalidation-compatibility-switch-not-supported)
- [No se admite el modificador de compatibilidad UseLegacyContextMenuStripSourceControlValue](#uselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported)
- [No se admite el modificador de compatibilidad UseLegacyImages](#uselegacyimages-compatibility-switch-not-supported)
- [Se ha cambiado el acceso para AccessibleObject.RuntimeIDFirstItem](#change-of-access-for-accessibleobjectruntimeidfirstitem)
- [Se han quitado las API duplicadas de Windows Forms](#duplicated-apis-removed-from-windows-forms)

### <a name="net-core-31"></a>.NET Core 3.1

[!INCLUDE[Removed controls](~/includes/core-changes/windowsforms/3.1/remove-controls-3.1.md)]

***

[!INCLUDE[CellFormatting event](~/includes/core-changes/windowsforms/3.1/cellformatting-event-not-raised.md)]

***

### <a name="net-core-30"></a>.NET Core 3.0

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

## <a name="see-also"></a>Vea también

- [API que siempre producen excepciones en .NET Core](unsupported-apis.md)
- [Tecnologías de .NET Framework no disponibles en .NET Core](../porting/net-framework-tech-unavailable.md)
