---
title: 'Cómo: Detectar cuándo está el puntero del mouse (ratón) en un elemento ToolStripItem'
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms], detecting mouse movement
- ToolStrip control [Windows Forms], detecting mouse movement
- ToolStripItem class [Windows Forms], detecting mouse movement
- mouse [Windows Forms], detecting movement on toolbars
ms.assetid: d38b5082-aba7-4f6c-841b-bd9714e307fd
ms.openlocfilehash: 15a7562efd9a86a029754610ffd9e77c372d1ac2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33530502"
---
# <a name="how-to-detect-when-the-mouse-pointer-is-over-a-toolstripitem"></a>Cómo: Detectar cuándo está el puntero del mouse (ratón) en un elemento ToolStripItem
Utilice el procedimiento siguiente para detectar cuando el puntero del mouse está sobre un <xref:System.Windows.Forms.ToolStripItem>.  
  
### <a name="to-detect-when-the-pointer-is-over-a-toolstripitem"></a>Detectar cuando el puntero está sobre un elemento ToolStripItem  
  
-   Use la <xref:System.Windows.Forms.ToolStripItem.Selected%2A> propiedad para los elementos en el que <xref:System.Windows.Forms.ToolStripItem.CanSelect%2A> es `true`.  
  
     Esto evitará tener que sincronizar el <xref:System.Windows.Forms.ToolStripItem.MouseEnter> y <xref:System.Windows.Forms.ToolStripItem.MouseLeave> eventos.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.ToolStripItem>  
 <xref:System.Windows.Forms.ToolStripItem.Selected%2A>  
 [Información sobre el control ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)
