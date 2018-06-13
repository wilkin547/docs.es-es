---
title: 'Cómo: Administrar el desbordamiento de ToolStrip en formularios Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], managing overflow
- toolbars [Windows Forms], managing overflow
- examples [Windows Forms], toolbars
- CanOverflow property
ms.assetid: fa10e0ad-4cbf-4c0d-9082-359c2f855d4e
ms.openlocfilehash: 32bbc06320f0dc7f096a4b9021bebfbefedaf8f7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33534897"
---
# <a name="how-to-manage-toolstrip-overflow-in-windows-forms"></a>Cómo: Administrar el desbordamiento de ToolStrip en formularios Windows Forms
Cuando todos los elementos en una <xref:System.Windows.Forms.ToolStrip> control no caben en el espacio asignado, puede habilitar la funcionalidad del desbordamiento en el <xref:System.Windows.Forms.ToolStrip> y determinar el comportamiento de desbordamiento específicas de <xref:System.Windows.Forms.ToolStripItem>s.  
  
 Cuando se agrega <xref:System.Windows.Forms.ToolStripItem>s que requieren más espacio que se asigna a la <xref:System.Windows.Forms.ToolStrip> dado el tamaño del formulario actual, un <xref:System.Windows.Forms.ToolStripOverflowButton> aparece automáticamente en el <xref:System.Windows.Forms.ToolStrip>. El <xref:System.Windows.Forms.ToolStripOverflowButton> aparece, y los elementos con desbordamiento habilitado se pasan al menú de desbordamiento de la lista desplegable. Esto le permite personalizar y dar prioridad a cómo el <xref:System.Windows.Forms.ToolStrip> elementos correctamente ajustarán a los tamaños de forma diferente. También puede cambiar la apariencia de los elementos cuando se encuentren en el desbordamiento mediante el uso de la <xref:System.Windows.Forms.ToolStripItem.Placement%2A> y <xref:System.Windows.Forms.ToolStripOverflow.DisplayedItems%2A?displayProperty=nameWithType> propiedades y <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> eventos. Si amplía el formulario en tiempo de diseño o en tiempo de ejecución, más <xref:System.Windows.Forms.ToolStripItem>s se pueden mostrar en el método main <xref:System.Windows.Forms.ToolStrip> y <xref:System.Windows.Forms.ToolStripOverflowButton> incluso puede que desaparezcan hasta que disminuya el tamaño del formulario.  
  
### <a name="to-enable-overflow-on-a-toolstrip-control"></a>Para habilitar el desbordamiento en un control ToolStrip  
  
-   Asegúrese de que el <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> propiedad no está establecida en `false` para el <xref:System.Windows.Forms.ToolStrip>. De manera predeterminada, es `True`.  
  
     Cuando <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> es `True` (valor predeterminado), un <xref:System.Windows.Forms.ToolStripItem> se envía al menú de desbordamiento de la lista desplegable cuando el contenido de la <xref:System.Windows.Forms.ToolStripItem> supera el ancho de un horizontal <xref:System.Windows.Forms.ToolStrip> o el alto de un vertical <xref:System.Windows.Forms.ToolStrip>.  
  
### <a name="to-specify-overflow-behavior-of-a-specific-toolstripitem"></a>Para especificar el comportamiento de desbordamiento de un ToolStripItem concreto  
  
-   Establecer el <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> propiedad de la <xref:System.Windows.Forms.ToolStripItem> en el valor deseado. Las posibilidades son `Always`, `Never`, y `AsNeeded`. El defaultis `AsNeeded`.  
  
    ```vb  
    toolStripTextBox1.Overflow = _  
    System.Windows.Forms.ToolStripItemOverflow.Never  
    ```  
  
    ```csharp  
    toolStripTextBox1.Overflow = _  
    System.Windows.Forms.ToolStripItemOverflow.Never;  
    ```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStripOverflowButton>  
 <xref:System.Windows.Forms.ToolStripItem.Overflow%2A>  
 <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>  
 [Información sobre el control ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)  
 [Arquitectura del control ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)  
 [Resumen de la tecnología ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)
