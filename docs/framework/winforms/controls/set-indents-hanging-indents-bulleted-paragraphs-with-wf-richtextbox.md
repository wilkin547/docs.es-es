---
title: Procedimiento para establecer sangrías, sangrías francesas y párrafos con viñetas con el control RichTextBox de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- text boxes [Windows Forms], setting indents
- .rtf files [Windows Forms], formatting in RichTextBox control
- examples [Windows Forms], text boxes
- RTF files [Windows Forms], formatting in RichTextBox control
- RichTextBox control [Windows Forms], setting indents and bullets
- text boxes [Windows Forms], bullets
ms.assetid: abfb40e6-5642-4691-8ec1-9d9ae91688dc
ms.openlocfilehash: ef579923ac2b9ea9905a60000d93f6bfc90ed5b8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59342679"
---
# <a name="how-to-set-indents-hanging-indents-and-bulleted-paragraphs-with-the-windows-forms-richtextbox-control"></a>Procedimiento para establecer sangrías, sangrías francesas y párrafos con viñetas con el control RichTextBox de formularios Windows Forms
Los formularios de Windows <xref:System.Windows.Forms.RichTextBox> control tiene numerosas opciones para dar formato al texto que muestra. Puede dar formato a párrafos seleccionados como listas con viñetas estableciendo el <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> propiedad. También puede usar el <xref:System.Windows.Forms.RichTextBox.SelectionIndent%2A>, <xref:System.Windows.Forms.RichTextBox.SelectionRightIndent%2A>, y <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> propiedades para establecer la sangría de párrafos relativa a la izquierda y derecha bordes del control y el borde izquierdo de otras líneas de texto.  
  
### <a name="to-format-a-paragraph-as-a-bulleted-list"></a>Para aplicar formato a un párrafo como una lista con viñetas  
  
1. Establezca la propiedad <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> en `true`.  
  
    ```vb  
    RichTextBox1.SelectionBullet = True  
    ```  
  
    ```csharp  
    richTextBox1.SelectionBullet = true;  
    ```  
  
    ```cpp  
    richTextBox1->SelectionBullet = true;  
    ```  
  
### <a name="to-indent-a-paragraph"></a>Para aplicar sangría a un párrafo  
  
1. Establecer el <xref:System.Windows.Forms.RichTextBox.SelectionIndent%2A> propiedad en un entero que representa la distancia en píxeles entre el borde izquierdo del control y el borde izquierdo del texto.  
  
2. Establecer el <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> propiedad en un entero que representa la distancia en píxeles entre el borde izquierdo de la primera línea del texto del párrafo y el borde izquierdo de las líneas siguientes del mismo párrafo. El valor de la <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> propiedad solo se aplica a las líneas de un párrafo encapsuladas bajo la primera línea.  
  
3. Establecer el <xref:System.Windows.Forms.RichTextBox.SelectionRightIndent%2A> propiedad en un entero que representa la distancia en píxeles entre el borde derecho del control y el borde derecho del texto.  
  
    ```vb  
    RichTextBox1.SelectionIndent = 8  
    RichTextBox1.SelectionHangingIndent = 3  
    RichTextBox1.SelectionRightIndent = 12  
    ```  
  
    ```csharp  
    richTextBox1.SelectionIndent = 8;  
    richTextBox1.SelectionHangingIndent = 3;  
    richTextBox1.SelectionRightIndent = 12;  
    ```  
  
    ```cpp  
    richTextBox1->SelectionIndent = 8;  
    richTextBox1->SelectionHangingIndent = 3;  
    richTextBox1->SelectionRightIndent = 12;  
    ```  
  
    > [!NOTE]
    >  Todas estas propiedades afectan a todos los párrafos que contienen texto seleccionado y también al texto que se escribe después del punto de inserción actual. Por ejemplo, cuando un usuario selecciona una palabra dentro de un párrafo y, a continuación, ajusta la sangría, la nueva configuración se aplica a todo el párrafo que contiene la palabra y a los párrafos que se escriben después del párrafo seleccionado. Para obtener información acerca de cómo seleccionar texto mediante programación, vea <xref:System.Windows.Forms.TextBoxBase.Select%2A>.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.RichTextBox>
- [RichTextBox (control)](richtextbox-control-windows-forms.md)
- [Controles que se utilizan en formularios Windows Forms](controls-to-use-on-windows-forms.md)
