---
title: "Cómo: Ocultar ToolStripMenuItems mediante el Diseñador"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], hiding menu items in designer
- MenuStrip control [Windows Forms], hiding menu items in designer
- menu items [Windows Forms], hiding
ms.assetid: 8f1b057e-3d8a-4f11-88df-935f7b29a836
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9549fa11b3f019dce3cc77d5f6d1d08a8485f0cf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-hide-toolstripmenuitems-using-the-designer"></a>Cómo: Ocultar ToolStripMenuItems mediante el Diseñador
Ocultar elementos de menú es una manera de controlar la interfaz de usuario (UI) de la aplicación y restringir los comandos de usuario. A menudo, deseará ocultar un menú completo cuando todos los elementos de menú en el no están disponibles. Esto supone menos distracciones para el usuario. Además, puede ocultar y deshabilitar el menú o el elemento de menú, como si sólo se oculta no impide que el usuario obtener acceso a un comando de menú mediante una tecla de método abreviado. Para obtener más información acerca de cómo deshabilitar elementos de menú, vea [Cómo: Deshabilitar ToolStripMenuItems mediante el diseñador](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems-using-the-designer.md).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para obtener más información, vea [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-hide-a-top-level-menu-and-its-submenu-items"></a>Para ocultar un menú de nivel superior y sus elementos de submenú  
  
1.  Seleccione el elemento de menú de nivel superior y establezca su <xref:System.Windows.Forms.ToolStripItem.Visible%2A> o <xref:System.Windows.Forms.ToolStripItem.Available%2A> propiedad `false`.  
  
     Cuando se oculta el elemento de menú de nivel superior, también se ocultan todos los elementos de menú dentro de ese menú. Si hace clic en otra parte que no sea de en el <xref:System.Windows.Forms.MenuStrip> después de establecer <xref:System.Windows.Forms.ToolStripItem.Visible%2A> a `false`, el elemento de menú de nivel superior completa y sus elementos de submenú desaparecen del formulario, lo que muestra el efecto de tiempo de ejecución de la acción. Para mostrar el elemento de menú de nivel superior en tiempo de diseño, haga clic en el <xref:System.Windows.Forms.MenuStrip> en el **Bandeja de componentes**, en **esquema del documento**, o en la parte superior de la cuadrícula de propiedades.  
  
> [!NOTE]
>  Raramente ocultará un menú completo salvo para los menús secundarios MDI (interfaz) de varios documentos en un escenario de combinación.  
  
### <a name="to-hide-a-submenu-item"></a>Para ocultar un elemento de submenú  
  
1.  Seleccione el elemento de submenú y establezca su <xref:System.Windows.Forms.ToolStripItem.Visible%2A> propiedad `false`.  
  
     Cuando se oculta un elemento de submenú, permanece visible en el formulario en tiempo de diseño para que se puedan seleccionar fácilmente para seguir trabajando. En realidad se ocultará en tiempo de ejecución.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.ToolStripItem.Visible%2A>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>  
 <xref:System.Windows.Forms.ToolStripItem.Available%2A>  
 <xref:System.Windows.Forms.ToolStripMenuItem.Overflow%2A>  
 [Información general sobre el control MenuStrip](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)  
 [Deshabilitar ToolStripMenuItems mediante el Diseñador](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems-using-the-designer.md)
