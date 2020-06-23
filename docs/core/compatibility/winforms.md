---
title: Cambios importantes en Windows Forms
description: Enumera los cambios importantes en Windows Forms para .NET Core.
ms.date: 01/08/2020
ms.openlocfilehash: bd87e438ecf9930bfcd5377f9a3799d5f3693f49
ms.sourcegitcommit: 1cbd77da54405ea7dba343ac0334fb03237d25d2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2020
ms.locfileid: "84702473"
---
# <a name="breaking-changes-in-windows-forms"></a>Cambios importantes en Windows Forms

Se ha agregado compatibilidad con Windows Forms a .NET Core, versión 3.0. En este artículo se enumeran los cambios importantes de Windows Forms por versión de .NET Core en la que se han incorporado. Si está actualizando una aplicación de Windows Forms desde .NET Framework o una versión anterior de .NET Core (3.0 o posterior), este artículo se aplica a su caso.

En esta página se documentan los siguientes cambios importantes:

| Cambio importante | Versión introducida |
| - | :-: |
| [Controles de la barra de estado quitados](#removed-status-bar-controls) | 5.0 |
| [Los métodos de WinForms inician ahora la excepción ArgumentException](#winforms-methods-now-throw-argumentexception) | 5.0 |
| [Los métodos de WinForms inician ahora la excepción ArgumentNullException](#winforms-methods-now-throw-argumentnullexception) | 5.0 |
| [Ahora, las propiedades de WinForms producen ArgumentOutOfRangeException](#winforms-properties-now-throw-argumentoutofrangeexception) | 5.0 |
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
| [Se ha cambiado el acceso para AccessibleObject.RuntimeIDFirstItem](#change-of-access-for-accessibleobjectruntimeidfirstitem) | 3.0 |
| [Se han quitado las API duplicadas de Windows Forms](#duplicated-apis-removed-from-windows-forms) | 3.0 |

## <a name="net-50"></a>.NET 5.0

[!INCLUDE [winforms-deprecated-controls](../../../includes/core-changes/windowsforms/5.0/winforms-deprecated-controls.md)]

***

[!INCLUDE [invalid-args-cause-argumentexception](../../../includes/core-changes/windowsforms/5.0/invalid-args-cause-argumentexception.md)]

***

[!INCLUDE [null-args-cause-argumentnullexception](../../../includes/core-changes/windowsforms/5.0/null-args-cause-argumentnullexception.md)]

***

[!INCLUDE [invalid-args-cause-argumentoutofrangeexception](../../../includes/core-changes/windowsforms/5.0/invalid-args-cause-argumentoutofrangeexception.md)]

***

## <a name="net-core-31"></a>.NET Core 3.1

[!INCLUDE[Removed controls](~/includes/core-changes/windowsforms/3.1/remove-controls-3.1.md)]

***

[!INCLUDE[CellFormatting event](~/includes/core-changes/windowsforms/3.1/cellformatting-event-not-raised.md)]

***

## <a name="net-core-30"></a>.NET Core 3.0

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

## <a name="see-also"></a>Vea también

- [Migración de una aplicación de Windows Forms a .NET Core](../porting/winforms.md)
