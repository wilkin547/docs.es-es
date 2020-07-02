---
title: Vincular a un objeto o una página web con el control LinkLabel
description: Obtenga información sobre cómo crear vínculos de estilo Web a un objeto o una página web con el Windows Forms control LinkLabel.
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
ms.openlocfilehash: a5fb1c03e9a8d82fe77f4133ba04c42114787d23
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618317"
---
# <a name="how-to-link-to-an-object-or-web-page-with-the-windows-forms-linklabel-control"></a>Procedimiento para establecer vínculos con un objeto o página web mediante el control LinkLabel de formularios Windows Forms

El <xref:System.Windows.Forms.LinkLabel> control Windows Forms permite crear vínculos de estilo Web en el formulario. Cuando se hace clic en el vínculo, puede cambiar su color para indicar que se ha visitado el vínculo. Para obtener más información sobre cómo cambiar el color, vea [Cómo: cambiar la apariencia del control LinkLabel Windows Forms](how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md).

## <a name="linking-to-another-form"></a>Vincular a otro formulario

#### <a name="to-link-to-another-form-with-a-linklabel-control"></a>Para vincular a otro formulario con un control LinkLabel

1. Establezca la <xref:System.Windows.Forms.LinkLabel.Text%2A> propiedad en un título adecuado.

2. Establezca la <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> propiedad para determinar qué parte del título se indicará como un vínculo. La forma en que se indique depende de las propiedades relacionadas con la apariencia de la etiqueta de vínculo. El <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> valor se representa mediante un <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> objeto que contiene dos números, la posición del carácter inicial y el número de caracteres. La <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> propiedad se puede establecer en el ventana Propiedades o en el código de una manera similar a la siguiente:

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

3. En el <xref:System.Windows.Forms.LinkLabel.LinkClicked> controlador de eventos, invoque el <xref:System.Windows.Forms.Form.Show%2A> método para abrir otro formulario en el proyecto y establezca la <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> propiedad en `true` .

    > [!NOTE]
    > Una instancia de la <xref:System.Windows.Forms.LinkLabelLinkClickedEventArgs> clase incluye una referencia al <xref:System.Windows.Forms.LinkLabel> control en el que se ha hecho clic, por lo que no es necesario convertir el `sender` objeto.

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

## <a name="linking-to-a-web-page"></a>Vincular a una página web

El <xref:System.Windows.Forms.LinkLabel> control también se puede usar para mostrar una página web con el explorador predeterminado.

#### <a name="to-start-internet-explorer-and-link-to-a-web-page-with-a-linklabel-control"></a>Para iniciar Internet Explorer y vincular a una página web con un control LinkLabel

1. Establezca la <xref:System.Windows.Forms.LinkLabel.Text%2A> propiedad en un título adecuado.

2. Establezca la <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> propiedad para determinar qué parte del título se indicará como un vínculo.

3. En el <xref:System.Windows.Forms.LinkLabel.LinkClicked> controlador de eventos, en medio de un bloque de control de excepciones, llame a un segundo procedimiento que establezca la <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> propiedad en `true` y use el <xref:System.Diagnostics.Process.Start%2A> método para iniciar el explorador predeterminado con una dirección URL. Para usar el <xref:System.Diagnostics.Process.Start%2A> método, debe agregar una referencia al espacio de <xref:System.Diagnostics?displayProperty=nameWithType> nombres.

    > [!IMPORTANT]
    > Si el código siguiente se ejecuta en un entorno de confianza parcial (por ejemplo, en una unidad compartida), se produce un error en el compilador JIT cuando `VisitLink` se llama al método. La `System.Diagnostics.Process.Start` instrucción produce una petición de vínculo que produce un error. Al detectar la excepción cuando `VisitLink` se llama al método, el código siguiente garantiza que, si se produce un error en el compilador JIT, el error se administra correctamente.

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
- [Información general sobre el control LinkLabel](linklabel-control-overview-windows-forms.md)
- [Procedimiento para cambiar el aspecto del control LinkLabel de formularios Windows Forms](how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md)
- [Control LinkLabel](linklabel-control-windows-forms.md)
