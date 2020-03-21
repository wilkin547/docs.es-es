---
title: 'Cómo: Mostrar una paleta de colores con el componente ColorDialog'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- palettes [Windows Forms], showing color
- color dialog box [Windows Forms], showing color palettes
- colors [Windows Forms], allowing users to select
- color palettes [Windows Forms], dialog box
- ColorDialog component [Windows Forms], showing color palettes
- color palettes [Windows Forms], showing in ColorDialog component
- colors [Windows Forms], showing palettes
ms.assetid: ee050f61-dbc8-4436-ba22-51360981ab48
ms.openlocfilehash: 0406ef7a32678bd149c0024348a7adf1f0b72926
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141788"
---
# <a name="how-to-show-a-color-palette-with-the-colordialog-component"></a>Cómo: Mostrar una paleta de colores con el componente ColorDialog
El componente [ColorDialog](colordialog-component-windows-forms.md) muestra una paleta de colores y devuelve una propiedad que contiene el color que el usuario ha seleccionado.  
  
### <a name="to-choose-a-color-using-the-colordialog-component"></a>Para elegir un color mediante el componente ColorDialog  
  
1. Muestre el cuadro <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> de diálogo utilizando el método.  
  
2. Utilice <xref:System.Windows.Forms.DialogResult> la propiedad para determinar cómo se cerró el cuadro de diálogo.  
  
3. Utilice <xref:System.Windows.Forms.ColorDialog.Color%2A> la propiedad <xref:System.Windows.Forms.ColorDialog> del componente para establecer el color elegido.  
  
     En el ejemplo <xref:System.Windows.Forms.Button> siguiente, <xref:System.Windows.Forms.Control.Click> el controlador <xref:System.Windows.Forms.ColorDialog> de eventos del control abre un componente. Cuando se elige un color **OK**y el <xref:System.Windows.Forms.Button> usuario hace clic en Aceptar , el color de fondo del control se establece en el color elegido. En el ejemplo se <xref:System.Windows.Forms.Button> supone que <xref:System.Windows.Forms.ColorDialog> el formulario tiene un control y un componente.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
    ByVal e As System.EventArgs) Handles Button1.Click  
       If ColorDialog1.ShowDialog() = DialogResult.OK Then  
          Button1.BackColor = ColorDialog1.Color  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       if(colorDialog1.ShowDialog() == DialogResult.OK)  
       {  
          button1.BackColor = colorDialog1.Color;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,
          System::EventArgs ^ e)  
       {  
          if(colorDialog1->ShowDialog() == DialogResult::OK)  
          {  
             button1->BackColor = colorDialog1->Color;  
          }  
       }  
    ```  
  
     (Visual C, Visual C++) Coloque el código siguiente en el constructor del formulario para registrar el controlador de eventos.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click +=
       gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.ColorDialog>
- [Componente ColorDialog](colordialog-component-windows-forms.md)
