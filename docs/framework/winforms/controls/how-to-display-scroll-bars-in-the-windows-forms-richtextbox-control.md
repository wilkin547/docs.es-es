---
title: 'Cómo: Mostrar barras de desplazamiento en el control RichTextBox de formularios Windows Forms'
ms.date: 03/30/2017
helpviewer_keywords:
- text boxes [Windows Forms], displaying scroll bars
- scroll bars [Windows Forms], displaying in controls
- RichTextBox control [Windows Forms], displaying scroll bars
ms.assetid: cdeb42e1-86e8-410c-ba46-18aec264ef5f
ms.openlocfilehash: 5588aad5b2e38716c628947c6e06365e7053eb5f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33532748"
---
# <a name="how-to-display-scroll-bars-in-the-windows-forms-richtextbox-control"></a>Cómo: Mostrar barras de desplazamiento en el control RichTextBox de formularios Windows Forms
De forma predeterminada, los formularios Windows Forms <xref:System.Windows.Forms.RichTextBox> control muestra las barras de desplazamiento horizontal y vertical según sea necesario. Hay siete valores posibles para la <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> propiedad de la <xref:System.Windows.Forms.RichTextBox> control, que se describen en la tabla siguiente.  
  
### <a name="to-display-scroll-bars-in-a-richtextbox-control"></a>Para mostrar las barras de desplazamiento en el control RichTextBox  
  
1.  Establezca la propiedad <xref:System.Windows.Forms.RichTextBox.Multiline%2A> en `true`. Se mostrará ningún tipo de barra, incluidos los de desplazamiento horizontal, si la <xref:System.Windows.Forms.RichTextBox.Multiline%2A> propiedad está establecida en `false`.  
  
2.  Establecer el <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> propiedad en un valor apropiado de la <xref:System.Windows.Forms.RichTextBoxScrollBars> enumeración.  
  
    |Valor|Descripción|  
    |-----------|-----------------|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.Both> (valor predeterminado)|Muestra las barras de desplazamiento horizontal o vertical, o ambas, sólo cuando el texto supera el ancho o el alto del control.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.None>|Nunca muestra ningún tipo de barra de desplazamiento.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.Horizontal>|Muestra una barra solo cuando el texto supera el ancho del control de desplazamiento horizontal. (Esto sucede, el <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> propiedad debe establecerse en `false`.)|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.Vertical>|Muestra una barra solo cuando el texto supera el alto del control de desplazamiento vertical.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedHorizontal>|Muestra si la barra de desplazamiento horizontal del <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> propiedad está establecida en `false`. La barra de desplazamiento aparece atenuada cuando el texto no supera el ancho del control.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedVertical>|Siempre muestra una barra de desplazamiento vertical. La barra de desplazamiento aparece atenuada cuando el texto no supera la longitud del control.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedBoth>|Siempre muestra una barra de desplazamiento vertical. Muestra si la barra de desplazamiento horizontal del <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> propiedad está establecida en `false`. Las barras de desplazamiento aparecen en gris cuando el texto no supera el ancho o el alto del control.|  
  
3.  Establezca la propiedad <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> en un valor apropiado.  
  
    |Valor|Descripción|  
    |-----------|-----------------|  
    |`false`|Texto en el control no se ajusta automáticamente para ajustarse al ancho del control, por lo que se desplazará a la derecha hasta que se alcance un salto de línea. Utilice este valor si eligió barras de desplazamiento horizontal o ambas cosas, por encima.|  
    |`true` (valor predeterminado)|Texto en el control se ajusta automáticamente para ajustarse al ancho del control. No se mostrará la barra de desplazamiento horizontal. Utilice este valor si eligió barras de desplazamiento vertical o ninguno, anteriormente, para mostrar uno o varios párrafos.|  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.RichTextBoxScrollBars>  
 <xref:System.Windows.Forms.RichTextBox>  
 [RichTextBox (control)](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)  
 [Controles que se utilizan en formularios Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
