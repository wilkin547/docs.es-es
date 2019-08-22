---
title: Filtrar para agregar botones a un control de la barra de herramientas mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms], adding buttons
- ToolBar control [Windows Forms], adding buttons
- ToolBar control [Windows Forms], adding separators
- examples [Windows Forms], toolbars
- ToolBar control [Windows Forms], adding drop-down menus
ms.assetid: d9ce3040-3e21-4e2d-80ae-b430982b2db8
ms.openlocfilehash: 4d7a49633599aabc96153e4793e50c1a4d6d092d
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69666216"
---
# <a name="how-to-add-buttons-to-a-toolbar-control-using-the-designer"></a>Filtrar para agregar botones a un control de la barra de herramientas mediante el diseñador

> [!NOTE]
> El control <xref:System.Windows.Forms.ToolStrip> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.ToolBar>; sin embargo, el control <xref:System.Windows.Forms.ToolBar> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso.

Una parte integral del <xref:System.Windows.Forms.ToolBar> control son los botones que se agregan a él. Se pueden usar para facilitar el acceso a los comandos de menú o, como alternativa, se pueden colocar en otra área de la interfaz de usuario de la aplicación para exponer comandos a los usuarios que no están disponibles en la estructura de menús.

El procedimiento siguiente requiere un proyecto de **aplicación Windows** con un formulario que <xref:System.Windows.Forms.ToolBar> contenga un control. Para obtener información acerca de cómo configurar este tipo de [proyecto, consulte Cómo: Cree un proyecto](/visualstudio/ide/step-1-create-a-windows-forms-application-project) de aplicación de [Windows Forms y cómo: Agregue controles a Windows Forms](how-to-add-controls-to-windows-forms.md).

### <a name="to-add-buttons-at-design-time"></a>Para agregar botones en tiempo de diseño

1. Seleccione el control <xref:System.Windows.Forms.ToolBar>.

2. En la **ventana Propiedades** , haga clic <xref:System.Windows.Forms.ToolBar.Buttons%2A> en la propiedad para seleccionarla y haga clic![en los **puntos suspensivos** (el botón de puntos suspensivos (...)](./media/visual-studio-ellipsis-button.png)en el botón ventana Propiedades de Visual Studio.) para abrir la **ToolBarButton Editor de colecciones**.

3. Use los botones **Agregar** y **quitar** para agregar y quitar <xref:System.Windows.Forms.ToolBar> botones del control.

4. Configure las propiedades de los botones individuales en la ventana **propiedades** que aparece en el panel del lado derecho del editor. En la tabla siguiente se muestran algunas propiedades importantes que se deben tener en cuenta.

    |Propiedad|DESCRIPCIÓN|
    |--------------|-----------------|
    |<xref:System.Windows.Forms.ToolBarButton.DropDownMenu%2A>|Establece el menú que se va a mostrar en el botón de la barra de herramientas desplegable. La propiedad del botón <xref:System.Windows.Forms.ToolBarButton.Style%2A> de la barra de herramientas <xref:System.Windows.Forms.ToolBarButtonStyle.DropDownButton>debe establecerse en. Esta propiedad toma una instancia de la <xref:System.Windows.Forms.ContextMenu> clase como referencia.|
    |<xref:System.Windows.Forms.ToolBarButton.PartialPush%2A>|Establece si se inserta parcialmente un botón de barra de herramientas de estilo de alternancia. La propiedad del botón <xref:System.Windows.Forms.ToolBarButton.Style%2A> de la barra de herramientas <xref:System.Windows.Forms.ToolBarButtonStyle.ToggleButton>debe establecerse en.|
    |<xref:System.Windows.Forms.ToolBarButton.Pushed%2A>|Establece si un botón de la barra de herramientas de estilo de alternancia está actualmente en estado presionado. La propiedad del botón <xref:System.Windows.Forms.ToolBarButton.Style%2A> de la barra de herramientas <xref:System.Windows.Forms.ToolBarButtonStyle.ToggleButton> se <xref:System.Windows.Forms.ToolBarButtonStyle.PushButton>debe establecer en o.|
    |<xref:System.Windows.Forms.ToolBarButton.Style%2A>|Establece el estilo del botón de la barra de herramientas. Debe ser uno de los valores de la <xref:System.Windows.Forms.ToolBarButtonStyle> enumeración.|
    |<xref:System.Windows.Forms.ToolBarButton.Text%2A>|Cadena de texto que se muestra en el botón.|
    |<xref:System.Windows.Forms.ToolBarButton.ToolTipText%2A>|Texto que aparece como información sobre herramientas para el botón.|

5. Haga clic en **Aceptar** para cerrar el cuadro de diálogo y crear los paneles especificados.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.ToolBar>
- [Cómo: Definir un icono para un botón de la barra de herramientas](how-to-define-an-icon-for-a-toolbar-button.md)
- [Cómo: Desencadenar eventos de menú para botones de barra de herramientas](how-to-trigger-menu-events-for-toolbar-buttons.md)
- [Información general del control ToolBar](toolbar-control-overview-windows-forms.md)
- [ToolBar (control)](toolbar-control-windows-forms.md)
