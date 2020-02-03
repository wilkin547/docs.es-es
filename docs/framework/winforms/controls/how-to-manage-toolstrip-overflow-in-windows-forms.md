---
title: 'Cómo: Administrar el desbordamiento de ToolStrip'
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
ms.openlocfilehash: 52cc02e626bee2d2457355028ecddc17e462d8fa
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736146"
---
# <a name="how-to-manage-toolstrip-overflow-in-windows-forms"></a>Cómo: Administrar el desbordamiento de ToolStrip en formularios Windows Forms

Cuando todos los elementos de un control <xref:System.Windows.Forms.ToolStrip> no caben en el espacio asignado, puede habilitar la funcionalidad de desbordamiento en el <xref:System.Windows.Forms.ToolStrip> y determinar el comportamiento de desbordamiento de <xref:System.Windows.Forms.ToolStripItem>s específicos.

Cuando se agregan <xref:System.Windows.Forms.ToolStripItem>que requieren más espacio que el asignado al <xref:System.Windows.Forms.ToolStrip> dado el tamaño actual del formulario, aparece automáticamente una <xref:System.Windows.Forms.ToolStripOverflowButton> en el <xref:System.Windows.Forms.ToolStrip>. Aparece el <xref:System.Windows.Forms.ToolStripOverflowButton> y los elementos habilitados para el desbordamiento se mueven al menú desplegable de desbordamiento. Esto le permite personalizar y priorizar el modo en que los elementos de <xref:System.Windows.Forms.ToolStrip> se ajustan correctamente a distintos tamaños de formulario. También puede cambiar la apariencia de los elementos cuando entran en el desbordamiento mediante las propiedades <xref:System.Windows.Forms.ToolStripItem.Placement%2A> y <xref:System.Windows.Forms.ToolStripOverflow.DisplayedItems%2A?displayProperty=nameWithType> y el evento <xref:System.Windows.Forms.ToolStrip.LayoutCompleted>. Si aumenta el tamaño del formulario en tiempo de diseño o en tiempo de ejecución, es posible que se muestren más <xref:System.Windows.Forms.ToolStripItem>s en el <xref:System.Windows.Forms.ToolStrip> principal y el <xref:System.Windows.Forms.ToolStripOverflowButton> incluso desaparecerá hasta que se reduzca el tamaño del formulario.

## <a name="to-enable-overflow-on-a-toolstrip-control"></a>Para habilitar el desbordamiento en un control ToolStrip

- Asegúrese de que la propiedad <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> no esté establecida en `false` para el <xref:System.Windows.Forms.ToolStrip>. El valor predeterminado es `True`.

     Cuando <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> se `True` (valor predeterminado), se envía un <xref:System.Windows.Forms.ToolStripItem> al menú de desbordamiento desplegable cuando el contenido del <xref:System.Windows.Forms.ToolStripItem> supera el ancho de un <xref:System.Windows.Forms.ToolStrip> horizontal o el alto de un <xref:System.Windows.Forms.ToolStrip>vertical.

## <a name="to-specify-overflow-behavior-of-a-specific-toolstripitem"></a>Para especificar el comportamiento de desbordamiento de un ToolStripItem específico

- Establezca la propiedad <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> del <xref:System.Windows.Forms.ToolStripItem> en el valor deseado. Las posibilidades son `Always`, `Never`y `AsNeeded`. El valor predeterminado es `AsNeeded`.

    ```vb
    toolStripTextBox1.Overflow = _
    System.Windows.Forms.ToolStripItemOverflow.Never
    ```

    ```csharp
    toolStripTextBox1.Overflow = _
    System.Windows.Forms.ToolStripItemOverflow.Never;
    ```

## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripOverflowButton>
- <xref:System.Windows.Forms.ToolStripItem.Overflow%2A>
- <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>
- [Información sobre el control ToolStrip](toolstrip-control-overview-windows-forms.md)
- [Arquitectura del control ToolStrip](toolstrip-control-architecture.md)
- [Resumen de la tecnología ToolStrip](toolstrip-technology-summary.md)
