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
# <a name="breaking-changes-in-windows-forms-for-net-core-30-and-31"></a>Cambios importantes en Windows Forms para .NET Core 3.0 y 3.1

Se ha agregado compatibilidad con Windows Forms a .NET Core, versión 3.0. En este artículo se enumeran los cambios importantes de Windows Forms por versión de .NET en la que se han incorporado. Si está actualizando una aplicación de Windows Forms desde .NET Framework o una versión anterior de .NET Core (3.0 o posterior), este artículo se aplica a su caso.

En esta página se documentan los siguientes cambios importantes:

| Cambio importante | Versión introducida |
| - | :-: |
| [Controles eliminados](#removed-controls) | 3.1 |
| [El evento CellFormatting no se produce si se muestra información en pantalla](#cellformatting-event-not-raised-if-tooltip-is-shown) | 3.1 |
| [Se ha cambiado Control.DefaultFont a Segoe UI 9 pt](#default-control-font-changed-to-segoe-ui-9-pt) | 3.0 |
| [Se ha modernizado FolderBrowserDialog](#modernization-of-the-folderbrowserdialog) | 3.0 |
| [Se ha quitado SerializableAttribute de algunos tipos de Windows Forms](#serializableattribute-removed-from-some-windows-forms-types) | 3.0 |
| [No se admite el modificador de compatibilidad AllowUpdateChildControlIndexForTabControls](#allowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported) | 3.0 |
| [No se admite el modificador de compatibilidad DomainUpDown.UseLegacyScrolling](#domainupdownuselegacyscrolling-compatibility-switch-not-supported) | 3.0 |
| [No se admite el modificador de compatibilidad DoNotLoadLatestRichEditControl](#donotloadlatestricheditcontrol-compatibility-switch-not-supported) | 3.0 |
| [No se admite el modificador de compatibilidad DoNotSupportSelectAllShortcutInMultilineTextBox](#donotsupportselectallshortcutinmultilinetextbox-compatibility-switch-not-supported) | 3.0 |
| [No se admite el modificador de compatibilidad DontSupportReentrantFilterMessage](#dontsupportreentrantfiltermessage-compatibility-switch-not-supported) | 3.0 |
| [No se admite el modificador de compatibilidad EnableVisualStyleValidation](#enablevisualstylevalidation-compatibility-switch-not-supported) | 3.0 |
| [No se admite el modificador de compatibilidad UseLegacyContextMenuStripSourceControlValue](#uselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported) | 3.0 |
| [No se admite el modificador de compatibilidad UseLegacyImages](#uselegacyimages-compatibility-switch-not-supported) | 3.0 |

## <a name="net-core-31"></a>.NET Core 3.1

[!INCLUDE[Removed controls](~/includes/core-changes/windowsforms/3.1/remove-controls-3.1.md)]

***

[!INCLUDE[CellFormatting event](~/includes/core-changes/windowsforms/3.1/cellformatting-event-not-raised.md)]

**_

## <a name="net-core-30"></a>.NET Core 3.0

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

_**

## <a name="see-also"></a>Vea también

- [Migración de una aplicación de Windows Forms a .NET Core](/dotnet/desktop/winforms/migration/?view=netdesktop-5.0&preserve-view=true)
