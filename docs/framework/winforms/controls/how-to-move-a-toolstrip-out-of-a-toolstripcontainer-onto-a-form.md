---
title: 'Cómo: Mover un objeto ToolStrip de un contenedor ToolStripContainer a un formulario'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStrip control [Windows Forms], parenting to forms
- Windows Forms, parenting ToolStrip controls
ms.assetid: a1c94a7f-6fc5-4e4c-84cf-ff11dc573d33
ms.openlocfilehash: 6cc54264033eca541ce845b75d608087fee8a542
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-move-a-toolstrip-out-of-a-toolstripcontainer-onto-a-form"></a>Cómo: Mover un objeto ToolStrip de un contenedor ToolStripContainer a un formulario
Utilice el procedimiento siguiente para mover un <xref:System.Windows.Forms.ToolStrip> fuera de un <xref:System.Windows.Forms.ToolStripContainer> a un formulario.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para obtener más información, vea [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-move-a-toolstrip-out-of-a-toolstripcontainer-onto-a-form"></a>Para mover un objeto ToolStrip de un contenedor ToolStripContainer a un formulario  
  
1.  Seleccione el control <xref:System.Windows.Forms.ToolStrip>.  
  
2.  Cortar la <xref:System.Windows.Forms.ToolStrip> por presionando CTRL + X, o haga clic en el <xref:System.Windows.Forms.ToolStrip> y elija **cortar** en el menú contextual.  
  
3.  Seleccione el formulario.  
  
4.  Pegar la <xref:System.Windows.Forms.ToolStrip> al presionar CTRL+V o elija **pegar** desde el **editar** menú.  
  
5.  Establecer el <xref:System.Windows.Forms.ToolStrip.Dock%2A> propiedad de la <xref:System.Windows.Forms.ToolStrip> a **arriba**.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStripContainer>  
 [Información sobre el control ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)
