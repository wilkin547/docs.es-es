---
title: Filtrar para mover un elemento ToolStrip de un control ToolStripContainer a un formulario
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStrip control [Windows Forms], parenting to forms
- Windows Forms, parenting ToolStrip controls
ms.assetid: a1c94a7f-6fc5-4e4c-84cf-ff11dc573d33
ms.openlocfilehash: 100e744e6e49fbf214488e9bbb796b5b6fb9591a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59142368"
---
# <a name="how-to-move-a-toolstrip-out-of-a-toolstripcontainer-onto-a-form"></a>Filtrar para mover un elemento ToolStrip de un control ToolStripContainer a un formulario
Utilice el siguiente procedimiento para mover un <xref:System.Windows.Forms.ToolStrip> fuera de un <xref:System.Windows.Forms.ToolStripContainer> a un formulario.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-move-a-toolstrip-out-of-a-toolstripcontainer-onto-a-form"></a>Para mover un objeto ToolStrip de un contenedor ToolStripContainer a un formulario  
  
1.  Seleccione el control <xref:System.Windows.Forms.ToolStrip>.  
  
2.  Cortar la <xref:System.Windows.Forms.ToolStrip> por presionando CTRL + X o haga clic en el <xref:System.Windows.Forms.ToolStrip> y elija **cortar** en el menú contextual.  
  
3.  Seleccione el formulario.  
  
4.  Pegar la <xref:System.Windows.Forms.ToolStrip> presione CTRL+V o elija **pegar** desde el **editar** menú.  
  
5.  Establecer el <xref:System.Windows.Forms.ToolStrip.Dock%2A> propiedad de la <xref:System.Windows.Forms.ToolStrip> a **superior**.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripContainer>
- [Información sobre el control ToolStrip](toolstrip-control-overview-windows-forms.md)
