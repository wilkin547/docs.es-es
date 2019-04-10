---
title: Filtrar para definir un icono para un botón de la barra de herramientas mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms], adding icons to buttons
- examples [Windows Forms], toolbars
- images [Windows Forms], toolbar buttons
- buttons [Windows Forms], images
- icons [Windows Forms], toolbar buttons
- ToolBar control [Windows Forms], adding icons to buttons
ms.assetid: d848f38e-67f2-49d4-8e88-01c845c06c02
ms.openlocfilehash: 19d0b284238ed662b25627d6077c1ebe6ecc6e86
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59323712"
---
# <a name="how-to-define-an-icon-for-a-toolbar-button-using-the-designer"></a>Filtrar para definir un icono para un botón de la barra de herramientas mediante el diseñador
> [!NOTE]
>  El control <xref:System.Windows.Forms.ToolStrip> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.ToolBar>; sin embargo, el control <xref:System.Windows.Forms.ToolBar> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso.  
  
 <xref:System.Windows.Forms.ToolBar> los botones son capaz de mostrar iconos dentro de ellos para facilitar su identificación por los usuarios. Esto se logra mediante la adición de imágenes para la <xref:System.Windows.Forms.ImageList> componente y lo asocia a la <xref:System.Windows.Forms.ToolBar> control.  
  
 El procedimiento siguiente requiere una **aplicación Windows** proyecto con un formulario que contenga un <xref:System.Windows.Forms.ToolBar> control y un <xref:System.Windows.Forms.ImageList> componente. Para obtener información acerca de cómo configurar un proyecto de este tipo, vea [Cómo: Cree un proyecto de aplicación de Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) y [Cómo: Agregar controles a Windows Forms](how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-set-an-icon-for-a-toolbar-button-at-design-time"></a>Para establecer un icono para un botón de barra de herramientas en tiempo de diseño  
  
1. Agregar imágenes a la <xref:System.Windows.Forms.ImageList> componente. Para obtener más información, vea [Cómo: Agregar o quitar imágenes del componente ImageList mediante el diseñador](how-to-add-or-remove-imagelist-images-with-the-designer.md).  
  
2. Seleccione el <xref:System.Windows.Forms.ToolBar> control en el formulario.  
  
3. En el **propiedades** ventana, establezca el <xref:System.Windows.Forms.ToolBar> del control <xref:System.Windows.Forms.ToolBar.ImageList%2A> propiedad a la <xref:System.Windows.Forms.ImageList> componente.  
  
4. Haga clic en el <xref:System.Windows.Forms.ToolBar> del control <xref:System.Windows.Forms.ToolBar.Buttons%2A> propiedad para seleccionarlo y haga clic en el botón de puntos suspensivos (![de pantalla de VisualStudioEllipsesButton](../media/vbellipsesbutton.png "vbEllipsesButton")) para abrir el **Editor de colecciones ToolBarButton**.  
  
5. Use la **agregar** para agregar botones a la <xref:System.Windows.Forms.ToolBar> control.  
  
6. En el **propiedades** ventana que aparece en el panel en el lado derecho de la **Editor de colecciones ToolBarButton**, establezca el <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> propiedad de cada botón de barra de herramientas a uno de los valores en la lista, que se dibuja desde las imágenes que agregó a la <xref:System.Windows.Forms.ImageList> componente.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.ToolBar>
- [Filtrar para desencadenar eventos de menú para los botones de la barra de herramientas](how-to-trigger-menu-events-for-toolbar-buttons.md)
- [Barra de herramientas (Control)](toolbar-control-windows-forms.md)
- [Componente ImageList](imagelist-component-windows-forms.md)
