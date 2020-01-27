---
title: Establecer atributos de fuente para el control RichTextBox
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
ms.openlocfilehash: f27256c155223df576ee3c42e6bf65270c870b0f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744851"
---
# <a name="how-to-set-font-attributes-for-the-windows-forms-richtextbox-control"></a>Cómo: Establecer atributos de fuente para el control RichTextBox de formularios Windows Forms
El control <xref:System.Windows.Forms.RichTextBox> de Windows Forms tiene numerosas opciones para dar formato al texto que muestra. Puede poner los caracteres seleccionados en negrita, subrayados o cursiva, con la propiedad <xref:System.Windows.Forms.RichTextBox.SelectionFont%2A>. También puede usar esta propiedad para cambiar el tamaño y el tipo de letra de los caracteres seleccionados. La propiedad <xref:System.Windows.Forms.RichTextBox.SelectionColor%2A> permite cambiar el color de los caracteres seleccionados.  
  
### <a name="to-change-the-appearance-of-characters"></a>Para cambiar la apariencia de los caracteres  
  
1. Establezca la propiedad <xref:System.Windows.Forms.RichTextBox.SelectionFont%2A> en una fuente adecuada.  
  
     Para permitir que los usuarios establezcan la familia de fuentes, el tamaño y el tipo de letra en una aplicación, normalmente usaría el componente <xref:System.Windows.Forms.FontDialog>. Para obtener información general al respecto, consulte [Información general sobre el componente FontDialog](fontdialog-component-overview-windows-forms.md).  
  
2. Establezca la propiedad <xref:System.Windows.Forms.RichTextBox.SelectionColor%2A> en un color adecuado.  
  
     Para permitir que los usuarios establezcan el color en una aplicación, normalmente usaría el componente <xref:System.Windows.Forms.ColorDialog>. Para obtener información general al respecto, consulte [Información general sobre el componente ColorDialog](colordialog-component-overview-windows-forms.md).  
  
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
    > Estas propiedades solo afectan al texto seleccionado o, si no hay texto seleccionado, al texto que se escriba en la posición actual del punto de inserción. Para obtener información sobre cómo seleccionar texto mediante programación, vea <xref:System.Windows.Forms.TextBoxBase.Select%2A>.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.RichTextBox>
- [RichTextBox (control)](richtextbox-control-windows-forms.md)
- [Controles que se utilizan en Windows Forms](controls-to-use-on-windows-forms.md)
