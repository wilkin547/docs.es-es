---
title: Mostrar barras de desplazamiento en el control RichTextBox
ms.date: 03/30/2017
helpviewer_keywords:
- text boxes [Windows Forms], displaying scroll bars
- scroll bars [Windows Forms], displaying in controls
- RichTextBox control [Windows Forms], displaying scroll bars
ms.assetid: cdeb42e1-86e8-410c-ba46-18aec264ef5f
ms.openlocfilehash: 2185b572ef20765043d3df3dbfd8bf5b21cfac28
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745556"
---
# <a name="how-to-display-scroll-bars-in-the-windows-forms-richtextbox-control"></a>Cómo: Mostrar barras de desplazamiento en el control RichTextBox de formularios Windows Forms
De forma predeterminada, el control Windows Forms <xref:System.Windows.Forms.RichTextBox> muestra barras de desplazamiento horizontal y vertical según sea necesario. Hay siete valores posibles para la propiedad <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> del control <xref:System.Windows.Forms.RichTextBox>, que se describen en la tabla siguiente.  
  
### <a name="to-display-scroll-bars-in-a-richtextbox-control"></a>Para mostrar las barras de desplazamiento en un control RichTextBox  
  
1. Establezca la propiedad <xref:System.Windows.Forms.RichTextBox.Multiline%2A> en `true`. No se mostrará ningún tipo de barra de desplazamiento, incluida la horizontal, si la propiedad <xref:System.Windows.Forms.RichTextBox.Multiline%2A> está establecida en `false`.  
  
2. Establezca la propiedad <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> en un valor adecuado de la enumeración <xref:System.Windows.Forms.RichTextBoxScrollBars>.  
  
    |{2&gt;Value&lt;2}|Descripción|  
    |-----------|-----------------|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.Both> (predeterminado)|Muestra barras de desplazamiento horizontal o vertical, o ambas, solo cuando el texto supera el ancho o la longitud del control.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.None>|Nunca muestra ningún tipo de barra de desplazamiento.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.Horizontal>|Muestra una barra de desplazamiento horizontal solo cuando el texto supera el ancho del control. (Para que esto suceda, la propiedad <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> debe establecerse en `false`).|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.Vertical>|Muestra una barra de desplazamiento vertical solo cuando el texto supera el alto del control.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedHorizontal>|Muestra una barra de desplazamiento horizontal cuando la propiedad <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> está establecida en `false`. La barra de desplazamiento aparece atenuada cuando el texto no supera el ancho del control.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedVertical>|Siempre muestra una barra de desplazamiento vertical. La barra de desplazamiento aparece atenuada cuando el texto no supera la longitud del control.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedBoth>|Siempre muestra una barra de desplazamiento vertical. Muestra una barra de desplazamiento horizontal cuando la propiedad <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> está establecida en `false`. Las barras de desplazamiento aparecen atenuadas cuando el texto no supera el ancho o la longitud del control.|  
  
3. Establezca la propiedad <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> en un valor apropiado.  
  
    |{2&gt;Value&lt;2}|Descripción|  
    |-----------|-----------------|  
    |`false`|El texto del control no se ajusta automáticamente para ajustarse al ancho del control, por lo que se desplazará hacia la derecha hasta que se alcance un salto de línea. Use este valor si ha elegido barras de desplazamiento horizontal o ambas, arriba.|  
    |`true` (predeterminado)|El texto del control se ajusta automáticamente para ajustarse al ancho del control. No aparecerá la barra de desplazamiento horizontal. Use este valor si ha elegido barras de desplazamiento verticales o ninguna, arriba, para mostrar uno o más párrafos.|  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.RichTextBoxScrollBars>
- <xref:System.Windows.Forms.RichTextBox>
- [RichTextBox (control)](richtextbox-control-windows-forms.md)
- [Controles que se utilizan en Windows Forms](controls-to-use-on-windows-forms.md)
