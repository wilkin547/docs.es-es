---
title: 'Cómo: Agregar botones a un control ToolBar mediante el Diseñador'
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms], adding buttons
- ToolBar control [Windows Forms], adding buttons
- ToolBar control [Windows Forms], adding separators
- examples [Windows Forms], toolbars
- ToolBar control [Windows Forms], adding drop-down menus
ms.assetid: d9ce3040-3e21-4e2d-80ae-b430982b2db8
ms.openlocfilehash: b96f112c83d2296356e3eb566a24315bcefeff1f
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/09/2018
ms.locfileid: "44253174"
---
# <a name="how-to-add-buttons-to-a-toolbar-control-using-the-designer"></a>Cómo: Agregar botones a un control ToolBar mediante el Diseñador
> [!NOTE]
>  El control <xref:System.Windows.Forms.ToolStrip> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.ToolBar>; sin embargo, el control <xref:System.Windows.Forms.ToolBar> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso.  
  
 Una parte integral de la <xref:System.Windows.Forms.ToolBar> control es los botones que agregue a él. Se pueden usar para facilitar el acceso a comandos de menú o, como alternativa, puede colocarse en otra área de la interfaz de usuario de la aplicación para exponer comandos a los usuarios que no están disponibles en la estructura de menú.  
  
 El procedimiento siguiente requiere una **aplicación Windows** proyecto con un formulario que contenga un <xref:System.Windows.Forms.ToolBar> control. Para obtener información acerca de cómo configurar un proyecto de este tipo, consulte [Cómo: crear un proyecto de aplicación Windows](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) y [Cómo: agregar controles a Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-add-buttons-at-design-time"></a>Para agregar botones en tiempo de diseño  
  
1.  Seleccione el control <xref:System.Windows.Forms.ToolBar>.  
  
2.  En el **propiedades** ventana, haga clic en el <xref:System.Windows.Forms.ToolBar.Buttons%2A> propiedad para seleccionarlo y haga clic en el **puntos suspensivos** (![de pantalla de VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png " vbEllipsesButton")) para abrir el **Editor de colecciones ToolBarButton**.  
  
3.  Use la **agregar** y **quitar** botones para agregar y quitar botones desde la <xref:System.Windows.Forms.ToolBar> control.  
  
4.  Configurar las propiedades de los botones individuales en el **propiedades** ventana que aparece en el panel en el lado derecho del editor. La siguiente tabla muestra algunas propiedades importantes a tener en cuenta.  
  
    |Property|Descripción|  
    |--------------|-----------------|  
    |<xref:System.Windows.Forms.ToolBarButton.DropDownMenu%2A>|Establece el menú que se mostrará en el botón de barra de herramientas desplegable. El botón de barra de herramientas <xref:System.Windows.Forms.ToolBarButton.Style%2A> propiedad debe establecerse en <xref:System.Windows.Forms.ToolBarButtonStyle.DropDownButton>. Esta propiedad toma una instancia de la <xref:System.Windows.Forms.ContextMenu> clase como referencia.|  
    |<xref:System.Windows.Forms.ToolBarButton.PartialPush%2A>|Establece si un botón de barra de herramientas de alternar está parcialmente presionado. El botón de barra de herramientas <xref:System.Windows.Forms.ToolBarButton.Style%2A> propiedad debe establecerse en <xref:System.Windows.Forms.ToolBarButtonStyle.ToggleButton>.|  
    |<xref:System.Windows.Forms.ToolBarButton.Pushed%2A>|Establece si un botón de Alternar barra de herramientas está actualmente en estado presionado. El botón de barra de herramientas <xref:System.Windows.Forms.ToolBarButton.Style%2A> propiedad debe establecerse en <xref:System.Windows.Forms.ToolBarButtonStyle.ToggleButton> o <xref:System.Windows.Forms.ToolBarButtonStyle.PushButton>.|  
    |<xref:System.Windows.Forms.ToolBarButton.Style%2A>|Establece el estilo del botón de barra de herramientas. Debe ser uno de los valores de la <xref:System.Windows.Forms.ToolBarButtonStyle> enumeración.|  
    |<xref:System.Windows.Forms.ToolBarButton.Text%2A>|La cadena de texto que se muestra en el botón.|  
    |<xref:System.Windows.Forms.ToolBarButton.ToolTipText%2A>|El texto que aparece como una información sobre herramientas para el botón.|  
  
5.  Haga clic en **Aceptar** para cerrar el cuadro de diálogo y crear los paneles especificados.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.ToolBar>  
 [Definir un icono para un botón ToolBar](../../../../docs/framework/winforms/controls/how-to-define-an-icon-for-a-toolbar-button.md)  
 [Cómo: Desencadenar eventos de menú para los botones de la barra de herramientas](../../../../docs/framework/winforms/controls/how-to-trigger-menu-events-for-toolbar-buttons.md)  
 [Información general del control ToolBar](../../../../docs/framework/winforms/controls/toolbar-control-overview-windows-forms.md)  
 [ToolBar (control)](../../../../docs/framework/winforms/controls/toolbar-control-windows-forms.md)
