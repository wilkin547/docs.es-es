---
title: Filtrar Cambiar el espaciado y la alineación de los elementos ToolStrip en Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], aligning items
- examples [Windows Forms], toolbars
- toolbars [Windows Forms], aligning items
ms.assetid: cd483466-0f49-43df-addf-e2b5fcd64027
ms.openlocfilehash: 954087fa893baf3aa623c912efb081491304d3fb
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57719447"
---
# <a name="how-to-change-the-spacing-and-alignment-of-toolstrip-items-in-windows-forms"></a>Filtrar Cambiar el espaciado y la alineación de los elementos ToolStrip en Windows Forms
El <xref:System.Windows.Forms.ToolStrip> control es totalmente compatible con las características de diseño, como cambiar el tamaño, el espaciado de <xref:System.Windows.Forms.ToolStripItem> controles relacionados entre sí, la disposición de los controles en el <xref:System.Windows.Forms.ToolStrip>y el espaciado de los controles relativa a la <xref:System.Windows.Forms.ToolStrip>.  
  
 Dado que el valor predeterminado de la <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> propiedad es `true`, controles de tamaño se ajusta automáticamente a menos que establezca el <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> propiedad a `false`.  
  
### <a name="to-manually-size-a-toolstripitem"></a>Para cambiar manualmente el tamaño de un elemento ToolStripItem  
  
1.  Establecer el <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> propiedad `false` para el control asociado.  
  
    ```vb  
    ToolStripButton1.AutoSize = False  
    ```  
  
    ```csharp  
    toolStripButton1.AutoSize = false;  
    ```  
  
2.  Establecer el <xref:System.Windows.Forms.ToolStripItem.Size%2A> como quiera para el asociado de la propiedad <xref:System.Windows.Forms.ToolStripItem>.  
  
### <a name="to-set-the-spacing-of-a-toolstripitem"></a>Para establecer el espaciado de un elemento ToolStripItem  
  
1.  Inserte los valores deseados, en píxeles, en el <xref:System.Windows.Forms.ToolStripItem.Margin%2A> propiedad del control asociado.  
  
     Los valores de la <xref:System.Windows.Forms.ToolStripItem.Margin%2A> propiedad especifica el espaciado entre el elemento y los elementos adyacentes en este orden: Izquierda, superior, derecho e inferior.  
  
    ```vb  
    ToolStripTextBox1.Margin = New System.Windows.Forms.Padding _  
        (3, 0, 3, 0)  
    ```  
  
    ```csharp  
    toolStripTextBox1.Margin = new System.Windows.Forms.Padding   
        (3, 0, 3, 0);  
    ```  
  
### <a name="to-align-a-toolstripitem-to-the-right-side-of-the-toolstrip"></a>Para alinear un control ToolStripItem en el lado derecho de la franja de herramientas  
  
1.  Establecer el <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> propiedad <xref:System.Windows.Forms.ToolStripItemAlignment.Right> para el control asociado. De forma predeterminada, <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> está establecido en <xref:System.Windows.Forms.ToolStripItemAlignment.Left>, lo que alinea los controles en el lado izquierdo de la <xref:System.Windows.Forms.ToolStrip>.  
  
    ```vb  
    ToolStripSplitButton1.Alignment = _  
        System.Windows.Forms.ToolStripItemAlignment.Right  
    ```  
  
    ```csharp  
    toolStripSplitButton1.Alignment =   
        System.Windows.Forms.ToolStripItemAlignment.Right;  
    ```  
  
### <a name="to-arrange-toolstrip-items-on-the-toolstrip"></a>Para organizar los elementos ToolStrip en el control ToolStrip  
  
-   Establecer el <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> en el valor de <xref:System.Windows.Forms.ToolStripLayoutStyle> que desee.  
  
    ```vb  
    ToolStripDropDown1.LayoutStyle = _  
        System.Windows.Forms.ToolStripLayoutStyle.Flow  
    ```  
  
    ```csharp  
    toolStripDropDown1.LayoutStyle =   
        System.Windows.Forms.ToolStripLayoutStyle.Flow;  
    ```  
  
## <a name="see-also"></a>Vea también
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
