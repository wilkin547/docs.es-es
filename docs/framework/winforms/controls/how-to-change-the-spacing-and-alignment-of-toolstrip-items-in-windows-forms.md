---
title: 'Cómo: cambiar el espaciado y la alineación de los elementos ToolStrip'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], aligning items
- examples [Windows Forms], toolbars
- toolbars [Windows Forms], aligning items
ms.assetid: cd483466-0f49-43df-addf-e2b5fcd64027
ms.openlocfilehash: 805fbac5fe33071006f29692d503e5c57eacd765
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746566"
---
# <a name="how-to-change-the-spacing-and-alignment-of-toolstrip-items-in-windows-forms"></a>Cómo: Cambiar el espaciado y la alineación de los elementos ToolStrip en Windows Forms
El control <xref:System.Windows.Forms.ToolStrip> admite por completo características de diseño como el ajuste de tamaño, el espaciado de los controles <xref:System.Windows.Forms.ToolStripItem> entre sí, la disposición de los controles en el <xref:System.Windows.Forms.ToolStrip>y el espaciado de los controles en relación con el <xref:System.Windows.Forms.ToolStrip>.  
  
 Dado que el valor predeterminado de la propiedad <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> es `true`, el tamaño de los controles se ajusta automáticamente a menos que se establezca la propiedad <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> en `false`.  
  
### <a name="to-manually-size-a-toolstripitem"></a>Para cambiar manualmente el tamaño de un ToolStripItem  
  
1. Establezca la propiedad <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> en `false` para el control asociado.  
  
    ```vb  
    ToolStripButton1.AutoSize = False  
    ```  
  
    ```csharp  
    toolStripButton1.AutoSize = false;  
    ```  
  
2. Establezca la propiedad <xref:System.Windows.Forms.ToolStripItem.Size%2A> como desee para la <xref:System.Windows.Forms.ToolStripItem>asociada.  
  
### <a name="to-set-the-spacing-of-a-toolstripitem"></a>Para establecer el espaciado de un ToolStripItem  
  
1. Inserte los valores deseados, en píxeles, en la <xref:System.Windows.Forms.ToolStripItem.Margin%2A> propiedad del control asociado.  
  
     Los valores de la propiedad <xref:System.Windows.Forms.ToolStripItem.Margin%2A> especifican el espaciado entre el elemento y los elementos adyacentes en este orden: izquierda, superior, derecha e inferior.  
  
    ```vb  
    ToolStripTextBox1.Margin = New System.Windows.Forms.Padding _  
        (3, 0, 3, 0)  
    ```  
  
    ```csharp  
    toolStripTextBox1.Margin = new System.Windows.Forms.Padding   
        (3, 0, 3, 0);  
    ```  
  
### <a name="to-align-a-toolstripitem-to-the-right-side-of-the-toolstrip"></a>Para alinear un control ToolStripItem en el lado derecho de ToolStrip  
  
1. Establezca la propiedad <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> en <xref:System.Windows.Forms.ToolStripItemAlignment.Right> para el control asociado. De forma predeterminada, <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> se establece en <xref:System.Windows.Forms.ToolStripItemAlignment.Left>, que alinea los controles en el lado izquierdo de la <xref:System.Windows.Forms.ToolStrip>.  
  
    ```vb  
    ToolStripSplitButton1.Alignment = _  
        System.Windows.Forms.ToolStripItemAlignment.Right  
    ```  
  
    ```csharp  
    toolStripSplitButton1.Alignment =   
        System.Windows.Forms.ToolStripItemAlignment.Right;  
    ```  
  
### <a name="to-arrange-toolstrip-items-on-the-toolstrip"></a>Para organizar los elementos ToolStrip en ToolStrip  
  
- Establezca la propiedad <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> en el valor de <xref:System.Windows.Forms.ToolStripLayoutStyle> que desee.  
  
    ```vb  
    ToolStripDropDown1.LayoutStyle = _  
        System.Windows.Forms.ToolStripLayoutStyle.Flow  
    ```  
  
    ```csharp  
    toolStripDropDown1.LayoutStyle =   
        System.Windows.Forms.ToolStripLayoutStyle.Flow;  
    ```  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.Control.Layout>
- <xref:System.Windows.Forms.ToolStrip.LayoutCompleted>
- <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A>
- <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A>
- <xref:System.Windows.Forms.ToolStripItem.Placement%2A>
- <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>
- [Información sobre el control ToolStrip](toolstrip-control-overview-windows-forms.md)
- [Arquitectura del control ToolStrip](toolstrip-control-architecture.md)
- [Resumen de la tecnología ToolStrip](toolstrip-technology-summary.md)
