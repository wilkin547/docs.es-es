---
title: Filtrar para mostrar una paleta de colores con el componente ColorDialog
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
ms.openlocfilehash: fcaf5da9958cf66fb63bd753dc94cba9c10f62f6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59096041"
---
# <a name="how-to-show-a-color-palette-with-the-colordialog-component"></a>Filtrar para mostrar una paleta de colores con el componente ColorDialog
El [ColorDialog](colordialog-component-windows-forms.md) componente muestra una paleta de colores y devuelve una propiedad que contiene el color seleccionado por el usuario.  
  
### <a name="to-choose-a-color-using-the-colordialog-component"></a>Para elegir un color mediante el componente ColorDialog  
  
1.  Mostrar el cuadro de diálogo mediante la <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> método.  
  
2.  Use el <xref:System.Windows.Forms.DialogResult> propiedad para determinar cómo se cerró el cuadro de diálogo.  
  
3.  Use la <xref:System.Windows.Forms.ColorDialog.Color%2A> propiedad de la <xref:System.Windows.Forms.ColorDialog> componente para establecer el color elegido.  
  
     En el ejemplo siguiente, la <xref:System.Windows.Forms.Button> del control <xref:System.Windows.Forms.Control.Click> controlador de eventos abre un <xref:System.Windows.Forms.ColorDialog> componente. Cuando se es un color elegido y el usuario hace clic en **Aceptar**, <xref:System.Windows.Forms.Button> color de fondo del control se establece en el color elegido. En el ejemplo se da por supuesto que el formulario tiene un <xref:System.Windows.Forms.Button> control y un <xref:System.Windows.Forms.ColorDialog> componente.  
  
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
  
     (Visual C#, [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) coloque el código siguiente en el constructor del formulario para registrar el controlador de eventos.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click +=   
       gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.ColorDialog>
- [Componente ColorDialog](colordialog-component-windows-forms.md)
