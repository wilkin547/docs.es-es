---
title: Información general sobre el control RichTextBox (formularios Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- RichTextBox
helpviewer_keywords:
- RichTextBox control [Windows Forms], about RichTextBox control
- text boxes [Windows Forms], about text boxes
ms.assetid: 95081194-3dd4-4b84-9545-dd373e491eca
ms.openlocfilehash: ded2c9bb0e5b3320de700ce6126710314ed9e4f2
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57720254"
---
# <a name="richtextbox-control-overview-windows-forms"></a>Información general sobre el control RichTextBox (formularios Windows Forms)
Los formularios de Windows <xref:System.Windows.Forms.RichTextBox> control se utiliza para mostrar, escribir y manipular texto con formato. El <xref:System.Windows.Forms.RichTextBox> hace lo mismo que el <xref:System.Windows.Forms.TextBox> hace control, pero también puede mostrar fuentes, colores y vínculos; Cargar texto e imágenes incrustadas desde un archivo; y buscar caracteres especificados. El <xref:System.Windows.Forms.RichTextBox> control normalmente se usa para manipular texto y proporcionar características de presentación similares a las aplicaciones de procesamiento de textos como Microsoft Word. Como el <xref:System.Windows.Forms.TextBox> (control), el <xref:System.Windows.Forms.RichTextBox> control puede mostrar barras de desplazamiento; pero a diferencia del <xref:System.Windows.Forms.TextBox> control, su valor predeterminado es mostrar las barras de desplazamiento horizontales y verticales según sea necesario, y tiene configuraciones adicionales.  
  
## <a name="working-with-the-richtextbox-control"></a>Trabajar con el control RichTextBox  
 Igual que con el <xref:System.Windows.Forms.TextBox> control, se establece el texto mostrado el <xref:System.Windows.Forms.RichTextBox.Text%2A> propiedad. El <xref:System.Windows.Forms.RichTextBox> control tiene numerosas propiedades para dar formato al texto. Para obtener más información acerca de estas propiedades, vea [Cómo: Establecer atributos de fuente para los Windows Forms Control RichTextBox](how-to-set-font-attributes-for-the-windows-forms-richtextbox-control.md) y [Cómo: Establecer sangrías, sangrías francesas y párrafos con viñetas con el Control RichTextBox de formularios de Windows](set-indents-hanging-indents-bulleted-paragraphs-with-wf-richtextbox.md). Para manipular archivos, el <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> y <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> métodos pueden mostrar y escribir varios formatos de archivo como texto sin formato, texto sin formato Unicode y formato de texto enriquecido (RTF). Se enumeran los formatos de archivo posibles en <xref:System.Windows.Forms.RichTextBoxStreamType>. Puede usar el <xref:System.Windows.Forms.RichTextBox.Find%2A> método para buscar cadenas de texto o caracteres específicos.  
  
 También puede usar un <xref:System.Windows.Forms.RichTextBox> control de vínculos de estilo Web estableciendo la <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A> propiedad `true` y escribir código para controlar la <xref:System.Windows.Forms.RichTextBox.LinkClicked> eventos. Para obtener más información, vea [Cómo: Mostrar vínculos de estilo Web con el Windows Forms Control RichTextBox](how-to-display-web-style-links-with-the-windows-forms-richtextbox-control.md). Puede impedir que el usuario manipule una parte o todo el texto en el control estableciendo la <xref:System.Windows.Forms.RichTextBox.SelectionProtected%2A> propiedad `true`.  
  
 Puede deshacer y rehacer la mayoría de las operaciones de edición en un <xref:System.Windows.Forms.RichTextBox> control mediante una llamada a la <xref:System.Windows.Forms.TextBoxBase.Undo%2A> y <xref:System.Windows.Forms.RichTextBox.Redo%2A> métodos. El <xref:System.Windows.Forms.RichTextBox.CanRedo%2A> método le permite determinar si la última operación que deshizo el usuario puede volver a aplicar al control.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.RichTextBox>
- [RichTextBox (control)](richtextbox-control-windows-forms.md)
- [Información general sobre el control TextBox](textbox-control-overview-windows-forms.md)
