---
title: Procedimiento Vincular a un objeto o página con el Control LinkLabel de formularios Windows Forms Web
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], LinkLabel control
- Windows Forms, linking to objects
- Web page link control
- linking [Windows Forms], to other forms
- Windows Forms, linking to Web pages
- links [Windows Forms], to other forms
- LinkLabel control [Windows Forms], linking to object or Web page
- LinkLabel control [Windows Forms], examples
ms.assetid: 6c91c975-3cb7-4504-82f0-fc6255f8fb85
ms.openlocfilehash: fd397f9a6462ad9da06b1cc258a51b3cccf5d21c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54628453"
---
# <a name="how-to-link-to-an-object-or-web-page-with-the-windows-forms-linklabel-control"></a>Procedimiento Vincular a un objeto o página con el Control LinkLabel de formularios Windows Forms Web
Los formularios de Windows <xref:System.Windows.Forms.LinkLabel> control le permite crear vínculos de estilo Web en el formulario. Cuando se hace clic en el vínculo, puede cambiar su color para indicar que se ha visitado el vínculo. Para obtener más información acerca de cómo cambiar el color, vea [Cómo: Cambiar la apariencia del Control LinkLabel de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md).  
  
## <a name="linking-to-another-form"></a>Vincular a otro formulario  
  
#### <a name="to-link-to-another-form-with-a-linklabel-control"></a>Para vincular a otro formulario con un control LinkLabel  
  
1.  Establecer el <xref:System.Windows.Forms.LinkLabel.Text%2A> propiedad título apropiado.  
  
2.  Establecer el <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> propiedad para determinar qué parte de la leyenda se indicará como un vínculo. ¿Cómo se indica depende de las propiedades relacionadas con la apariencia de la etiqueta del vínculo. El <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> valor está representado por un <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> objeto que contiene dos números, la posición del carácter inicial y el número de caracteres. El <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> propiedad puede establecerse en la ventana Propiedades o en el código de forma similar al siguiente:  
  
    ```vb  
    ' In this code example, the link area has been set to begin  
    ' at the first character and extend for eight characters.  
    ' You may need to modify this based on the text entered in Step 1.  
    LinkLabel1.LinkArea = New LinkArea(0, 8)  
    ```  
  
    ```csharp  
    // In this code example, the link area has been set to begin  
    // at the first character and extend for eight characters.  
    // You may need to modify this based on the text entered in Step 1.  
    linkLabel1.LinkArea = new LinkArea(0,8);  
    ```  
  
    ```cpp  
    // In this code example, the link area has been set to begin  
    // at the first character and extend for eight characters.  
    // You may need to modify this based on the text entered in Step 1.  
    linkLabel1->LinkArea = LinkArea(0,8);  
    ```  
  
3.  En el <xref:System.Windows.Forms.LinkLabel.LinkClicked> controlador de eventos, invocar el <xref:System.Windows.Forms.Form.Show%2A> método para abrir otro formulario en el proyecto y establecer el <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> propiedad `true`.  
  
    > [!NOTE]
    >  Una instancia de la <xref:System.Windows.Forms.LinkLabelLinkClickedEventArgs> clase lleva una referencia a la <xref:System.Windows.Forms.LinkLabel> control que se hizo clic, por lo que no es necesario convertir el `sender` objeto.  
  
    ```vb  
    Protected Sub LinkLabel1_LinkClicked(ByVal Sender As System.Object, _  
       ByVal e As System.Windows.Forms.LinkLabelLinkClickedEventArgs) _  
       Handles LinkLabel1.LinkClicked  
       ' Show another form.  
       Dim f2 As New Form()  
       f2.Show  
       LinkLabel1.LinkVisited = True  
    End Sub  
    ```  
  
    ```csharp  
    protected void linkLabel1_LinkClicked(object sender, System. Windows.Forms.LinkLabelLinkClickedEventArgs e)  
    {  
       // Show another form.  
       Form f2 = new Form();  
       f2.Show();  
       linkLabel1.LinkVisited = true;  
    }  
    ```  
  
    ```cpp  
    private:  
       void linkLabel1_LinkClicked(System::Object ^  sender,  
          System::Windows::Forms::LinkLabelLinkClickedEventArgs ^  e)  
       {  
          // Show another form.  
          Form ^ f2 = new Form();  
          f2->Show();  
          linkLabel1->LinkVisited = true;  
       }  
    ```  
  
## <a name="linking-to-a-web-page"></a>Vincular a una página Web  
 El <xref:System.Windows.Forms.LinkLabel> control también puede usarse para mostrar una página Web con el explorador predeterminado.  
  
#### <a name="to-start-internet-explorer-and-link-to-a-web-page-with-a-linklabel-control"></a>Para iniciar Internet Explorer y vínculo a una página Web con un control LinkLabel  
  
1.  Establecer el <xref:System.Windows.Forms.LinkLabel.Text%2A> propiedad título apropiado.  
  
2.  Establecer el <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> propiedad para determinar qué parte de la leyenda se indicará como un vínculo.  
  
3.  En el <xref:System.Windows.Forms.LinkLabel.LinkClicked> controlador de eventos, en medio de un bloque de control de excepciones, llame a un segundo procedimiento que establece el <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> propiedad `true` y usa el <xref:System.Diagnostics.Process.Start%2A> método para iniciar el explorador predeterminado con una dirección URL. Para usar el <xref:System.Diagnostics.Process.Start%2A> método tiene que agregar una referencia a la <xref:System.Diagnostics?displayProperty=nameWithType> espacio de nombres.  
  
    > [!IMPORTANT]
    >  Si el código siguiente se ejecuta en un entorno de confianza parcial (como en una unidad compartida), el compilador JIT se produce un error cuando el `VisitLink` se llama al método. El `System.Diagnostics.Process.Start` instrucción provoca una petición de vínculo que se produce un error. Al capturar la excepción cuando el `VisitLink` se llama al método, el código siguiente asegura que si se produce un error en el compilador JIT, el error se controlen correctamente.  
  
    ```vb  
    Private Sub LinkLabel1_LinkClicked(ByVal sender As System.Object, _  
       ByVal e As System.Windows.Forms.LinkLabelLinkClickedEventArgs) _  
       Handles LinkLabel1.LinkClicked  
       Try  
          VisitLink()  
       Catch ex As Exception  
          ' The error message  
          MessageBox.Show("Unable to open link that was clicked.")  
       End Try  
    End Sub  
  
    Sub VisitLink()  
       ' Change the color of the link text by setting LinkVisited   
       ' to True.  
       LinkLabel1.LinkVisited = True  
       ' Call the Process.Start method to open the default browser   
       ' with a URL:  
       System.Diagnostics.Process.Start("http://www.microsoft.com")  
    End Sub  
    ```  
  
    ```csharp  
    private void linkLabel1_LinkClicked(object sender, System.Windows.Forms.LinkLabelLinkClickedEventArgs e)  
    {  
       try  
       {  
          VisitLink();  
       }  
       catch (Exception ex )  
       {  
          MessageBox.Show("Unable to open link that was clicked.");  
       }  
    }  
  
    private void VisitLink()  
    {  
       // Change the color of the link text by setting LinkVisited   
       // to true.  
       linkLabel1.LinkVisited = true;  
       //Call the Process.Start method to open the default browser   
       //with a URL:  
       System.Diagnostics.Process.Start("http://www.microsoft.com");  
    }  
    ```  
  
    ```cpp  
    private:  
       void linkLabel1_LinkClicked(System::Object ^  sender,  
          System::Windows::Forms::LinkLabelLinkClickedEventArgs ^  e)  
       {  
          try  
          {  
             VisitLink();  
          }  
          catch (Exception ^ ex)  
          {  
             MessageBox::Show("Unable to open link that was clicked.");  
          }  
       }  
    private:  
       void VisitLink()  
       {  
          // Change the color of the link text by setting LinkVisited   
          // to true.  
          linkLabel1->LinkVisited = true;  
          // Call the Process.Start method to open the default browser   
          // with a URL:  
          System::Diagnostics::Process::Start("http://www.microsoft.com");  
       }  
    ```  
  
## <a name="see-also"></a>Vea también
- <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType>
- [Información general sobre el control LinkLabel](../../../../docs/framework/winforms/controls/linklabel-control-overview-windows-forms.md)
- [Cómo: Cambiar la apariencia del Control LinkLabel de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md)
- [LinkLabel (control)](../../../../docs/framework/winforms/controls/linklabel-control-windows-forms.md)
