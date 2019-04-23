---
title: Procedimiento para mostrar barras de desplazamiento en el control RichTextBox de formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- text boxes [Windows Forms], displaying scroll bars
- scroll bars [Windows Forms], displaying in controls
- RichTextBox control [Windows Forms], displaying scroll bars
ms.assetid: cdeb42e1-86e8-410c-ba46-18aec264ef5f
ms.openlocfilehash: 152706cee511e4bca1dd324a652e8077b1f8548a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59312662"
---
# <a name="how-to-display-scroll-bars-in-the-windows-forms-richtextbox-control"></a>Procedimiento para mostrar barras de desplazamiento en el control RichTextBox de formularios Windows Forms
De forma predeterminada, los formularios de Windows <xref:System.Windows.Forms.RichTextBox> control muestra las barras de desplazamiento horizontales y verticales según sea necesario. Hay siete valores posibles para el <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> propiedad de la <xref:System.Windows.Forms.RichTextBox> control, que se describen en la tabla siguiente.  
  
### <a name="to-display-scroll-bars-in-a-richtextbox-control"></a>Para mostrar las barras de desplazamiento en un control RichTextBox  
  
1. Establezca la propiedad <xref:System.Windows.Forms.RichTextBox.Multiline%2A> en `true`. Se mostrará ningún tipo de barra de desplazamiento, como horizontal, si la <xref:System.Windows.Forms.RichTextBox.Multiline%2A> propiedad está establecida en `false`.  
  
2. Establecer el <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> propiedad en un valor adecuado de la <xref:System.Windows.Forms.RichTextBoxScrollBars> enumeración.  
  
    |Valor|Descripción|  
    |-----------|-----------------|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.Both> (valor predeterminado)|Muestra las barras de desplazamiento horizontal o vertical, o ambos, solo cuando el texto supera el ancho o la longitud del control.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.None>|Nunca se muestra ningún tipo de barra de desplazamiento.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.Horizontal>|Muestra una barra solo cuando el texto supera el ancho del control de desplazamiento horizontal. (Para ello, el <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> propiedad debe establecerse en `false`.)|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.Vertical>|Muestra una barra solo cuando el texto supera el alto del control de desplazamiento vertical.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedHorizontal>|Muestra cuándo la barra de desplazamiento horizontal del <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> propiedad está establecida en `false`. La barra de desplazamiento aparece atenuada cuando el texto no supera el ancho del control.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedVertical>|Muestra siempre una barra de desplazamiento vertical. La barra de desplazamiento aparece atenuada cuando el texto no supera la longitud del control.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedBoth>|Muestra siempre una barra de desplazamiento vertical. Muestra cuándo la barra de desplazamiento horizontal del <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> propiedad está establecida en `false`. Las barras de desplazamiento aparecen en gris cuando el texto no superar el ancho o la longitud del control.|  
  
3. Establezca la propiedad <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> en un valor apropiado.  
  
    |Valor|Descripción|  
    |-----------|-----------------|  
    |`false`|Texto del control no se ajusta automáticamente para ajustarse al ancho del control, por lo que se desplazará a la derecha hasta que se alcanza un salto de línea. Use este valor si anteriormente eligió las barras de desplazamiento horizontal o ambos.|  
    |`true` (valor predeterminado)|Texto del control se ajusta automáticamente para ajustarse al ancho del control. No aparecerá la barra de desplazamiento horizontal. Use este valor si anteriormente eligió los barras de desplazamiento vertical, o ninguno, para mostrar uno o varios párrafos.|  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.RichTextBoxScrollBars>
- <xref:System.Windows.Forms.RichTextBox>
- [RichTextBox (control)](richtextbox-control-windows-forms.md)
- [Controles que se utilizan en formularios Windows Forms](controls-to-use-on-windows-forms.md)
