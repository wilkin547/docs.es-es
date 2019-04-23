---
title: Procedimiento para detectar cuándo está el puntero del mouse en un elemento ToolStripItem
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms], detecting mouse movement
- ToolStrip control [Windows Forms], detecting mouse movement
- ToolStripItem class [Windows Forms], detecting mouse movement
- mouse [Windows Forms], detecting movement on toolbars
ms.assetid: d38b5082-aba7-4f6c-841b-bd9714e307fd
ms.openlocfilehash: 09fd9f2f9b8cc44b6c04b829bf2854bea4aa8cf7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59220051"
---
# <a name="how-to-detect-when-the-mouse-pointer-is-over-a-toolstripitem"></a>Procedimiento para detectar cuándo está el puntero del mouse en un elemento ToolStripItem
Utilice el procedimiento siguiente para detectar cuando el puntero del mouse se sitúa sobre un <xref:System.Windows.Forms.ToolStripItem>.  
  
### <a name="to-detect-when-the-pointer-is-over-a-toolstripitem"></a>Para detectar cuando el puntero está sobre un elemento ToolStripItem  
  
-   Use la <xref:System.Windows.Forms.ToolStripItem.Selected%2A> propiedad para los elementos en el que <xref:System.Windows.Forms.ToolStripItem.CanSelect%2A> es `true`.  
  
     Esto impedirá tener que sincronizar el <xref:System.Windows.Forms.ToolStripItem.MouseEnter> y <xref:System.Windows.Forms.ToolStripItem.MouseLeave> eventos.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripItem.Selected%2A>
- [Información sobre el control ToolStrip](toolstrip-control-overview-windows-forms.md)
