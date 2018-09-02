---
title: 'Cómo: Definir un icono para un botón del control ToolBar mediante el Diseñador'
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms], adding icons to buttons
- examples [Windows Forms], toolbars
- images [Windows Forms], toolbar buttons
- buttons [Windows Forms], images
- icons [Windows Forms], toolbar buttons
- ToolBar control [Windows Forms], adding icons to buttons
ms.assetid: d848f38e-67f2-49d4-8e88-01c845c06c02
ms.openlocfilehash: f26e21d824420fc4ff0480de21f260309c5c2e11
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43456725"
---
# <a name="how-to-define-an-icon-for-a-toolbar-button-using-the-designer"></a>Cómo: Definir un icono para un botón del control ToolBar mediante el Diseñador
> [!NOTE]
>  El control <xref:System.Windows.Forms.ToolStrip> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.ToolBar>; sin embargo, el control <xref:System.Windows.Forms.ToolBar> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso.  
  
 <xref:System.Windows.Forms.ToolBar> los botones son capaz de mostrar iconos dentro de ellos para facilitar su identificación por los usuarios. Esto se logra mediante la adición de imágenes para la <xref:System.Windows.Forms.ImageList> componente y lo asocia a la <xref:System.Windows.Forms.ToolBar> control.  
  
 El procedimiento siguiente requiere una **aplicación Windows** proyecto con un formulario que contenga un <xref:System.Windows.Forms.ToolBar> control y un <xref:System.Windows.Forms.ImageList> componente. Para obtener información acerca de cómo configurar un proyecto de este tipo, consulte [Cómo: crear un proyecto de aplicación Windows](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) y [Cómo: agregar controles a Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-set-an-icon-for-a-toolbar-button-at-design-time"></a>Para establecer un icono para un botón de barra de herramientas en tiempo de diseño  
  
1.  Agregar imágenes a la <xref:System.Windows.Forms.ImageList> componente. Para obtener más información, consulte [Cómo: agregar o quitar imágenes del componente ImageList mediante el diseñador](../../../../docs/framework/winforms/controls/how-to-add-or-remove-imagelist-images-with-the-designer.md).  
  
2.  Seleccione el <xref:System.Windows.Forms.ToolBar> control en el formulario.  
  
3.  En el **propiedades** ventana, establezca el <xref:System.Windows.Forms.ToolBar> del control <xref:System.Windows.Forms.ToolBar.ImageList%2A> propiedad a la <xref:System.Windows.Forms.ImageList> componente.  
  
4.  Haga clic en el <xref:System.Windows.Forms.ToolBar> del control <xref:System.Windows.Forms.ToolBar.Buttons%2A> propiedad para seleccionarlo y haga clic en el botón de puntos suspensivos (![de pantalla de VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) para abrir el **Editor de colecciones ToolBarButton**.  
  
5.  Use la **agregar** para agregar botones a la <xref:System.Windows.Forms.ToolBar> control.  
  
6.  En el **propiedades** ventana que aparece en el panel en el lado derecho de la **Editor de colecciones ToolBarButton**, establezca el <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> propiedad de cada botón de barra de herramientas a uno de los valores en la lista, que se dibuja desde las imágenes que agregó a la <xref:System.Windows.Forms.ImageList> componente.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.ToolBar>  
 [Cómo: Desencadenar eventos de menú para los botones de la barra de herramientas](../../../../docs/framework/winforms/controls/how-to-trigger-menu-events-for-toolbar-buttons.md)  
 [ToolBar (control)](../../../../docs/framework/winforms/controls/toolbar-control-windows-forms.md)  
 [ImageList (componente)](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md)
