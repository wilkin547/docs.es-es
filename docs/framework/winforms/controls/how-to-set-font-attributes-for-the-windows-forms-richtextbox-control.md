---
title: Filtrar Establecer atributos de fuente para el Control RichTextBox de formularios de Windows
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- .rtf files [Windows Forms], formatting in RichTextBox control
- fonts [Windows Forms], changing attributes in RichTextBox control
- RTF files [Windows Forms], formatting in RichTextBox control
- RichTextBox control [Windows Forms], setting font attributes
- text [Windows Forms]
- text boxes [Windows Forms], formatting text
- formatting [Windows Forms]
ms.assetid: 2bc23ddb-0529-4489-a1a2-ad253cb43f9a
ms.openlocfilehash: 92578bd267230f5878bda9533bd117e8f98d8f13
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57714689"
---
# <a name="how-to-set-font-attributes-for-the-windows-forms-richtextbox-control"></a>Filtrar Establecer atributos de fuente para el Control RichTextBox de formularios de Windows
Los formularios de Windows <xref:System.Windows.Forms.RichTextBox> control tiene numerosas opciones para dar formato al texto que muestra. Puede realizar los caracteres seleccionados en negrita, subrayado o cursiva, utilizando el <xref:System.Windows.Forms.RichTextBox.SelectionFont%2A> propiedad. También puede usar esta propiedad para cambiar el tamaño y el tipo de letra de los caracteres seleccionados. El <xref:System.Windows.Forms.RichTextBox.SelectionColor%2A> propiedad le permite cambiar el color de los caracteres seleccionados.  
  
### <a name="to-change-the-appearance-of-characters"></a>Para cambiar la apariencia de los caracteres  
  
1.  Establecer el <xref:System.Windows.Forms.RichTextBox.SelectionFont%2A> propiedad en una fuente adecuada.  
  
     Para permitir que los usuarios establezcan la familia de fuentes, el tamaño y tipo de letra en una aplicación, normalmente usaría el <xref:System.Windows.Forms.FontDialog> componente. Para obtener información general al respecto, consulte [Información general sobre el componente FontDialog](fontdialog-component-overview-windows-forms.md).  
  
2.  Establecer el <xref:System.Windows.Forms.RichTextBox.SelectionColor%2A> propiedad en un color adecuado.  
  
     Para permitir que los usuarios establezcan el color en una aplicación, normalmente usaría el <xref:System.Windows.Forms.ColorDialog> componente. Para obtener información general al respecto, consulte [Información general sobre el componente ColorDialog](colordialog-component-overview-windows-forms.md).  
  
    ```vb  
    RichTextBox1.SelectionFont = New Font("Tahoma", 12, FontStyle.Bold)  
    RichTextBox1.SelectionColor = System.Drawing.Color.Red  
    ```  
  
    ```csharp  
    richTextBox1.SelectionFont = new Font("Tahoma", 12, FontStyle.Bold);  
    richTextBox1.SelectionColor = System.Drawing.Color.Red;  
    ```  
  
    ```cpp  
    richTextBox1->SelectionFont =  
       gcnew System::Drawing::Font("Tahoma", 12, FontStyle::Bold);  
    richTextBox1->SelectionColor = System::Drawing::Color::Red;  
    ```  
  
    > [!NOTE]
    >  Estas propiedades solo afectan al texto seleccionado o, si no hay texto seleccionado, al texto que se escriba en la posición actual del punto de inserción. Para obtener información sobre cómo seleccionar texto mediante programación, vea <xref:System.Windows.Forms.TextBoxBase.Select%2A>.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.RichTextBox>
- [RichTextBox (control)](richtextbox-control-windows-forms.md)
- [Controles que se utilizan en formularios Windows Forms](controls-to-use-on-windows-forms.md)
