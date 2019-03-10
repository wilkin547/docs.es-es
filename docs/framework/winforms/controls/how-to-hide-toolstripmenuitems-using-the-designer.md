---
title: Filtrar Ocultar ToolStripMenuItems mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], hiding menu items in designer
- MenuStrip control [Windows Forms], hiding menu items in designer
- menu items [Windows Forms], hiding
ms.assetid: 8f1b057e-3d8a-4f11-88df-935f7b29a836
ms.openlocfilehash: 2af9f31360f667662d4d640b5e449ff6ee8ce381
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57721546"
---
# <a name="how-to-hide-toolstripmenuitems-using-the-designer"></a>Procedimiento Ocultar ToolStripMenuItems mediante el diseñador
Ocultar elementos de menú es una manera de controlar la interfaz de usuario (UI) de la aplicación y restringir los comandos de usuario. A menudo, deseará ocultar un menú completo cuando no están disponibles todos los elementos de menú en él. Esto supone menos distracciones para el usuario. Además, es posible que desea ocultar y deshabilitar el menú o elemento de menú, como ocultar por sí solo no impide que el usuario acceso a un comando de menú mediante una tecla de método abreviado. Para obtener más información acerca de cómo deshabilitar los elementos de menú, vea [Cómo: Deshabilitar ToolStripMenuItems mediante el diseñador](how-to-disable-toolstripmenuitems-using-the-designer.md).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-hide-a-top-level-menu-and-its-submenu-items"></a>Para ocultar un menú de nivel superior y sus elementos de submenú  
  
1.  Seleccione el elemento de menú de nivel superior y establezca su <xref:System.Windows.Forms.ToolStripItem.Visible%2A> o <xref:System.Windows.Forms.ToolStripItem.Available%2A> propiedad `false`.  
  
     Cuando se oculta el elemento de menú de nivel superior, también se ocultan todos los elementos de menú dentro de ese menú. Si hace clic en algún lugar que no sea en el <xref:System.Windows.Forms.MenuStrip> después de establecer <xref:System.Windows.Forms.ToolStripItem.Visible%2A> a `false`, el elemento de menú de nivel superior completa y sus elementos de submenú desaparecen del formulario, lo que muestra el efecto del tiempo de ejecución de la acción. Para mostrar el elemento de menú de nivel superior en tiempo de diseño, haga clic en el <xref:System.Windows.Forms.MenuStrip> en el **Bandeja de componentes**, en **esquema del documento**, o en la parte superior de la cuadrícula de propiedades.  
  
> [!NOTE]
>  Rara vez se oculte un menú todo excepto los menús secundarios MDI (interfaz) de varios documentos en un escenario de combinación.  
  
### <a name="to-hide-a-submenu-item"></a>Para ocultar un elemento de submenú  
  
1.  Seleccione el elemento de submenú y establezca su <xref:System.Windows.Forms.ToolStripItem.Visible%2A> propiedad `false`.  
  
     Cuando se oculta un elemento de submenú, permanece visible en el formulario en tiempo de diseño para que se puede seleccionar fácilmente para seguir trabajando. En realidad se ocultará en tiempo de ejecución.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.ToolStripItem.Visible%2A>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>
- <xref:System.Windows.Forms.ToolStripItem.Available%2A>
- <xref:System.Windows.Forms.ToolStripMenuItem.Overflow%2A>
- [Información general sobre el control MenuStrip](menustrip-control-overview-windows-forms.md)
- [Cómo: Deshabilitar ToolStripMenuItems mediante el diseñador](how-to-disable-toolstripmenuitems-using-the-designer.md)
