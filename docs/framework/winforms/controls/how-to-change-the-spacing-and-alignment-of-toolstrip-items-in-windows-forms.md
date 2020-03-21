---
title: 'Cómo: Cambiar el espaciado y la alineación de los elementos ToolStrip'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], aligning items
- examples [Windows Forms], toolbars
- toolbars [Windows Forms], aligning items
ms.assetid: cd483466-0f49-43df-addf-e2b5fcd64027
ms.openlocfilehash: 550ac1660a077e8d766a01bfa8d102c07f0fbfeb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182232"
---
# <a name="how-to-change-the-spacing-and-alignment-of-toolstrip-items-in-windows-forms"></a>Cómo: Cambiar el espaciado y la alineación de los elementos ToolStrip en formularios Windows Forms
El <xref:System.Windows.Forms.ToolStrip> control admite completamente las características de <xref:System.Windows.Forms.ToolStripItem> diseño, como el tamaño, el <xref:System.Windows.Forms.ToolStrip>espaciado de los controles en <xref:System.Windows.Forms.ToolStrip>relación entre sí, la disposición de los controles en el , y el espaciado de los controles en relación con el archivo .  
  
 Dado que el <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> valor `true`predeterminado de la propiedad es <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> , `false`los controles se dimensionan automáticamente a menos que establezca la propiedad en .  
  
### <a name="to-manually-size-a-toolstripitem"></a>Para cambiar manualmente el tamaño de un ToolStripItem  
  
1. Establezca <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> la `false` propiedad en para el control asociado.  
  
    ```vb  
    ToolStripButton1.AutoSize = False  
    ```  
  
    ```csharp  
    toolStripButton1.AutoSize = false;  
    ```  
  
2. Establezca <xref:System.Windows.Forms.ToolStripItem.Size%2A> la propiedad de la <xref:System.Windows.Forms.ToolStripItem>manera que desee para el archivo .  
  
### <a name="to-set-the-spacing-of-a-toolstripitem"></a>Para establecer el espaciado de un ToolStripItem  
  
1. Inserte los valores deseados, <xref:System.Windows.Forms.ToolStripItem.Margin%2A> en píxeles, en la propiedad del control asociado.  
  
     Los valores <xref:System.Windows.Forms.ToolStripItem.Margin%2A> de la propiedad especifican el espaciado entre el elemento y los elementos adyacentes en este orden: Izquierda, Superior, Derecha e Inferior.  
  
    ```vb  
    ToolStripTextBox1.Margin = New System.Windows.Forms.Padding _  
        (3, 0, 3, 0)  
    ```  
  
    ```csharp  
    toolStripTextBox1.Margin = new System.Windows.Forms.Padding
        (3, 0, 3, 0);  
    ```  
  
### <a name="to-align-a-toolstripitem-to-the-right-side-of-the-toolstrip"></a>Para alinear un ToolStripItem al lado derecho de la ToolStrip  
  
1. Establezca <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> la <xref:System.Windows.Forms.ToolStripItemAlignment.Right> propiedad en para el control asociado. De forma <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> predeterminada, <xref:System.Windows.Forms.ToolStripItemAlignment.Left>se establece en , que <xref:System.Windows.Forms.ToolStrip>alinea los controles al lado izquierdo del archivo .  
  
    ```vb  
    ToolStripSplitButton1.Alignment = _  
        System.Windows.Forms.ToolStripItemAlignment.Right  
    ```  
  
    ```csharp  
    toolStripSplitButton1.Alignment =
        System.Windows.Forms.ToolStripItemAlignment.Right;  
    ```  
  
### <a name="to-arrange-toolstrip-items-on-the-toolstrip"></a>Para organizar los elementos ToolStrip en El ToolStrip  
  
- Establezca <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> la propiedad en <xref:System.Windows.Forms.ToolStripLayoutStyle> el valor que desee.  
  
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
