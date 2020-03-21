---
title: Compatibilidad de UI Automation con controles estándar
ms.date: 03/30/2017
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
ms.openlocfilehash: 36028d589e98177f6a0e83092edd656860b1a8d4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179850"
---
# <a name="ui-automation-support-for-standard-controls"></a>Compatibilidad de UI Automation con controles estándar
> [!NOTE]
> Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).  
  
 Este tema contiene [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] información sobre la compatibilidad [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]con controles estándar en aplicaciones desarrolladas para los marcos de trabajo , Win32 y Windows Forms.  
  
<a name="Windows_Presentation_Foundation_Controls"></a>
## <a name="windows-presentation-foundation-controls"></a>Controles de Windows Presentation Foundation  
 Todos los elementos de control [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] que ofrecen información o compatibilidad para la interacción del usuario tienen compatibilidad nativa completa con [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]. Otros elementos, como paneles, no son visibles para [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].  
  
<a name="Win32_Controls"></a>
## <a name="win32-controls"></a>Controles de Win32  
 La mayoría de los [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] controles Win32 se exponen a través de proveedores del lado cliente en UIAutomationClientsideProviders.dll. Este ensamblado se registra automáticamente para su uso con aplicaciones de cliente de automatización de la interfaz de usuario.  
  
 La compatibilidad completa solo se proporciona para los controles de la versión 6 de *ComCtrl32.dll*.  
  
 Se admiten los siguientes controles.  
  
|Nombre de la clase|Tipo de control|  
|----------------|------------------|  
|Botón|Botón|  
|Botón|RadioButton|  
|Botón|Grupo|  
|Botón|CheckBox|  
|Botón|Hyperlink|  
|Botón|SplitButton|  
|Botón|CheckBox|  
|ComboBoxEx32|ComboBox|  
|ComboBox|ComboBox|  
|Editar|Documento|  
|Editar|Editar|  
|SysLink|Hyperlink|  
|estática|Texto|  
|estática|Imagen|  
|SysIPAddress32|Personalizado|  
|SysHeader32|Header/HeaderItem|  
|SysListView32|DataGrid|  
|SysListView32|List|  
|ListBox|List|  
|ListBox|ListItem|  
|#32768|Menú|  
|#32768|MenuItem|  
|msctls_progress32|ProgressBar|  
|RichEdit|Documentar. Vea la nota.|  
|RichEdit20A|Documento|  
|RichEdit20W|Documento|  
|RichEdit50W|Documento|  
|ScrollBar|Control deslizante|  
|msctls_trackbar32|Control deslizante|  
|msctls_updown32|Spinner|  
|msctls_statusbar32|StatusBar|  
|SysTabControl32|Pestaña|  
|SysTabControl32|TabItem|  
|ToolbarWindow32|ToolBar|  
|ToolbarWindow32|MenuItem|  
|ToolbarWindow32|Botón|  
|ToolbarWindow32|CheckBox|  
|ToolbarWindow32|RadioButton|  
|ToolbarWindow32|Separador|  
|tooltips_class32|Información sobre herramientas|  
|#32774|Información sobre herramientas|  
|ReBarWindow32|Barra de herramientas|  
|SysTreeView32|Árbol|  
|SysTreeView32|TreeItem|  
  
 **Nota** El control RichEdit solo se admite para las versiones incluidas con Windows Vista (en RichEd20.dll versión 3.1 y posteriores, y MsftEdit.dll versión 4.1 y posteriores).  
  
 No se admiten los siguientes controles.  
  
|Nombre de la clase|Tipo de control|  
|----------------|------------------|  
|SysAnimate32|Imagen|  
|SysPager|Spinner|  
|SysDateTimePick32|Personalizado|  
|SysMonthCal32|Calendario|  
|MS_WINNOTE|Información sobre herramientas|  
|VBBubble|Información sobre herramientas|  
|ScrollBar (cuando se usa como control independiente)|Control deslizante|  
|SuperGrid|Personalizado|  
  
<a name="Windows_Forms_Controls"></a>
## <a name="windows-forms-controls"></a>Controles de Windows Forms  
 Los controles de [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] formularios Windows Forms se exponen a través de proveedores del lado cliente en UIAutomationClientsideProviders.dll. Este ensamblado se registra automáticamente para su uso con aplicaciones de cliente de automatización de la interfaz de usuario.  
  
 Normalmente, los controles de formularios Windows Forms que son [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]contenedores administrados para controles comunes de Win32 son compatibles con . Se admiten los siguientes controles.  
  
|Class Name (Nombre de clase)|  
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
|Timer|  
|Barra de herramientas|  
|Información sobre herramientas|  
|Trackbar|  
|TreeView|  
|VscrollBar|  
|ExploradorWeb|  
  
 Los siguientes controles [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] se exponen solo a través de su compatibilidad con Microsoft Active Accessibility. Es posible que algunas funciones no estén disponibles.  
  
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
  
## <a name="see-also"></a>Consulte también

- [Tipos de control de Automatización de la interfaz de usuario](ui-automation-control-types.md)
