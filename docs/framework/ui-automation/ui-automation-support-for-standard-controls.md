---
title: Compatibilidad de UI Automation con controles estándar
ms.date: 03/30/2017
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
ms.openlocfilehash: c59352f908c5f4a1fd2ca6dd631d26bb5d69f09a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74441223"
---
# <a name="ui-automation-support-for-standard-controls"></a>Compatibilidad de UI Automation con controles estándar
> [!NOTE]
> Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).  
  
 En este tema se incluye información sobre la compatibilidad de [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] con controles estándar en las aplicaciones desarrolladas para los marcos de trabajo [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]y [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] .  
  
<a name="Windows_Presentation_Foundation_Controls"></a>   
## <a name="windows-presentation-foundation-controls"></a>Controles de Windows Presentation Foundation  
 Todos los elementos de control [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] que ofrecen información o compatibilidad para la interacción del usuario tienen compatibilidad nativa completa con [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]. Otros elementos, como paneles, no son visibles para [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].  
  
<a name="Win32_Controls"></a>   
## <a name="win32-controls"></a>Controles de Win32  
 La mayoría de los controles [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] se exponen a [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] a través de los proveedores del cliente en UIAutomationClientsideProviders.dll. Este ensamblado se registra automáticamente para su uso con aplicaciones de cliente de automatización de la interfaz de usuario.  
  
 Solo se proporciona compatibilidad completa para controles desde la versión 6 de ComCtrl32.dll (disponibles con [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] y versiones posteriores).  
  
 Se admiten los siguientes controles.  
  
|Nombre de la clase|Tipo de control|  
|----------------|------------------|  
|Botón|Botón|  
|Botón|RadioButton|  
|Botón|Agrupar|  
|Botón|CheckBox|  
|Botón|Hipervínculo|  
|Botón|SplitButton|  
|Botón|CheckBox|  
|ComboBoxEx32|ComboBox|  
|ComboBox|ComboBox|  
|Editar|Documento|  
|Editar|Editar|  
|SysLink|Hipervínculo|  
|Estático|Text|  
|Estático|Imagen|  
|SysIPAddress32|Personalizados|  
|SysHeader32|Header/HeaderItem|  
|SysListView32|DataGrid|  
|SysListView32|Lista|  
|ListBox|Lista|  
|ListBox|ListItem|  
|#32768|Menú|  
|#32768|MenuItem|  
|msctls_progress32|ProgressBar|  
|RichEdit|Documento. Vea la nota.|  
|RichEdit20A|Documento|  
|RichEdit20W|Documento|  
|RichEdit50W|Documento|  
|ScrollBar|Slider|  
|msctls_trackbar32|Slider|  
|msctls_updown32|Spinner|  
|msctls_statusbar32|StatusBar|  
|SysTabControl32|Tab|  
|SysTabControl32|TabItem|  
|ToolbarWindow32|ToolBar|  
|ToolbarWindow32|MenuItem|  
|ToolbarWindow32|Botón|  
|ToolbarWindow32|CheckBox|  
|ToolbarWindow32|RadioButton|  
|ToolbarWindow32|Separador|  
|tooltips_class32|Información sobre herramientas|  
|#32774|Información sobre herramientas|  
|ReBarWindow32|ToolBar|  
|SysTreeView32|Árbol|  
|SysTreeView32|TreeItem|  
  
 **Note** The RichEdit control is supported only for versions shipped with Windows Vista (in RichEd20.dll version 3.1 and later, and MsftEdit.dll version 4.1 and later).  
  
 No se admiten los siguientes controles.  
  
|Nombre de la clase|Tipo de control|  
|----------------|------------------|  
|SysAnimate32|Imagen|  
|SysPager|Spinner|  
|SysDateTimePick32|Personalizados|  
|SysMonthCal32|Calendario|  
|MS_WINNOTE|Información sobre herramientas|  
|VBBubble|Información sobre herramientas|  
|ScrollBar (cuando se usa como control independiente)|Slider|  
|SuperGrid|Personalizados|  
  
<a name="Windows_Forms_Controls"></a>   
## <a name="windows-forms-controls"></a>Controles de Windows Forms  
 Windows Forms controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll. Este ensamblado se registra automáticamente para su uso con aplicaciones de cliente de automatización de la interfaz de usuario.  
  
 Typically, Windows Forms controls that are managed wrappers for [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] common controls are supported by [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]. Se admiten los siguientes controles.  
  
|Nombre de la clase|  
|----------------|  
|Botón|  
|CheckBox|  
|CheckedListBox|  
|ColorDialog|  
|ComboBox|  
|FolderBrowser|  
|FontDialog|  
|GroupBox|  
|HScrollBar|  
|ImageList|  
|Etiqueta|  
|ListBox|  
|ListView|  
|MainMenu/ContextMenu|  
|MonthCalendar|  
|NotifyIcon|  
|OpenFileDialog|  
|PageSetupDialog|  
|PrintDialog|  
|ProgressBar|  
|RadioButton|  
|RichTextBox|  
|SaveFileDialog|  
|ScrollableControl|  
|SoundPlayer|  
|StatusBar|  
|TabControl/TabPage|  
|TextBox|  
|Temporizador|  
|ToolBar|  
|Información sobre herramientas|  
|Trackbar|  
|TreeView|  
|VscrollBar|  
|ExploradorWeb|  
  
 The following controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] only through their support for Microsoft Active Accessibility. Es posible que algunas funciones no estén disponibles.  
  
|Nombre del control|  
|------------------|  
|BindingSource|  
|DataGrid|  
|DataGridView|  
|DataNavigator|  
|DomainUpDown|  
|ErrorProvider|  
|FlowLayoutPanel|  
|Form|  
|LinkLabel|  
|HelpProvider|  
|MaskedTextBox|  
|MenuStrip/ContextMenuStrip|  
|NumericUpDown|  
|Panel|  
|PictureBox|  
|PrintDocument|  
|PrintPreview-Control|  
|PrintPreview-Dialog|  
|PropertyGrid|  
|Control de usuario|  
|ToolStrip|  
|TableLayoutPanel|  
|SplitContainer/SplitterPanel|  
|Divisor|  
|RaftingContainer|  
|StatusStrip|  
  
## <a name="see-also"></a>Vea también

- [Tipos de control de Automatización de la interfaz de usuario](ui-automation-control-types.md)
