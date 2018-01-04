---
title: "Cómo: Agregar botones a un control ToolBar mediante el Diseñador"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- toolbars [Windows Forms], adding buttons
- ToolBar control [Windows Forms], adding buttons
- ToolBar control [Windows Forms], adding separators
- examples [Windows Forms], toolbars
- ToolBar control [Windows Forms], adding drop-down menus
ms.assetid: d9ce3040-3e21-4e2d-80ae-b430982b2db8
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ccd63cb88661db7601b87eec6bdf3a959afb8bbf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-buttons-to-a-toolbar-control-using-the-designer"></a>Cómo: Agregar botones a un control ToolBar mediante el Diseñador
> [!NOTE]
>  El control <xref:System.Windows.Forms.ToolStrip> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.ToolBar>; sin embargo, el control <xref:System.Windows.Forms.ToolBar> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso.  
  
 Una parte integral de la <xref:System.Windows.Forms.ToolBar> control es los botones que agregue a ella. Se pueden usar para facilitar el acceso a comandos de menú, o bien, como alternativa, puede colocarse en otra área de la interfaz de usuario de la aplicación para exponer comandos a los usuarios que no están disponibles en la estructura de menús.  
  
 El procedimiento siguiente requiere un **aplicación de Windows** proyecto con un formulario que contenga un <xref:System.Windows.Forms.ToolBar> control. Para obtener información acerca de cómo configurar un proyecto de este tipo, consulte [Cómo: crear un proyecto de aplicación de Windows](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) y [Cómo: agregar controles a formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para obtener más información, consulte [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-add-buttons-at-design-time"></a>Para agregar botones en tiempo de diseño  
  
1.  Seleccione el control <xref:System.Windows.Forms.ToolBar>.  
  
2.  En el **propiedades** ventana, haga clic en el <xref:System.Windows.Forms.ToolBar.Buttons%2A> propiedad para seleccionarlo y haga clic en el **puntos suspensivos** (![de pantalla de VisualStudioEllipsesButton] (../../../../docs/framework/winforms/media/vbellipsesbutton.png " vbEllipsesButton")) para abrir el **Editor de colecciones ToolBarButton**.  
  
3.  Use la **agregar** y **quitar** botones para agregar y quitar botones, desde el <xref:System.Windows.Forms.ToolBar> control.  
  
4.  Configurar las propiedades de los botones individuales en la **propiedades** ventana que aparece en el panel del lado derecho del editor. La tabla siguiente muestran algunas propiedades importantes a tener en cuenta.  
  
    |Property|Descripción|  
    |--------------|-----------------|  
    |<xref:System.Windows.Forms.ToolBarButton.DropDownMenu%2A>|Establece el menú que se mostrará en el botón de barra de herramientas de lista desplegable. El botón de barra de herramientas <xref:System.Windows.Forms.ToolBarButton.Style%2A> propiedad debe establecerse en <xref:System.Windows.Forms.ToolBarButtonStyle.DropDownButton>. Esta propiedad toma una instancia de la <xref:System.Windows.Forms.ContextMenu> clase como una referencia.|  
    |<xref:System.Windows.Forms.ToolBarButton.PartialPush%2A>|Establece si un botón de barra de herramientas Alternar parcialmente presionado. El botón de barra de herramientas <xref:System.Windows.Forms.ToolBarButton.Style%2A> propiedad debe establecerse en <xref:System.Windows.Forms.ToolBarButtonStyle.ToggleButton>.|  
    |<xref:System.Windows.Forms.ToolBarButton.Pushed%2A>|Establece si un botón de Alternar barra de herramientas está actualmente en estado presionado. El botón de barra de herramientas <xref:System.Windows.Forms.ToolBarButton.Style%2A> propiedad debe establecerse en <xref:System.Windows.Forms.ToolBarButtonStyle.ToggleButton> o <xref:System.Windows.Forms.ToolBarButtonStyle.PushButton>.|  
    |<xref:System.Windows.Forms.ToolBarButton.Style%2A>|Establece el estilo del botón de barra de herramientas. Debe ser uno de los valores de la <xref:System.Windows.Forms.ToolBarButtonStyle> enumeración.|  
    |<xref:System.Windows.Forms.ToolBarButton.Text%2A>|La cadena de texto que se muestra el botón.|  
    |<xref:System.Windows.Forms.ToolBarButton.ToolTipText%2A>|El texto que aparece como una información sobre herramientas para el botón.|  
  
5.  Haga clic en **Aceptar** para cerrar el cuadro de diálogo y crear los paneles especificados.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.ToolBar>  
 [Definir un icono para un botón ToolBar](../../../../docs/framework/winforms/controls/how-to-define-an-icon-for-a-toolbar-button.md)  
 [Cómo: Desencadenar eventos de menú para los botones de la barra de herramientas](../../../../docs/framework/winforms/controls/how-to-trigger-menu-events-for-toolbar-buttons.md)  
 [Información general del control ToolBar](../../../../docs/framework/winforms/controls/toolbar-control-overview-windows-forms.md)  
 [ToolBar (control)](../../../../docs/framework/winforms/controls/toolbar-control-windows-forms.md)
