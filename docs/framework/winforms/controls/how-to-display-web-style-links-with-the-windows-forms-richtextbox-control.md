---
title: Mostrar vínculos de estilo Web con el control RichTextBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- text boxes [Windows Forms], displaying Web links
- examples [Windows Forms], text boxes
- RichTextBox control [Windows Forms], linking to Web pages
ms.assetid: 95089a37-a202-4f7a-94ee-6ee312908851
ms.openlocfilehash: 78a07a250744018f121b03f2973b1661ed6bf764
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745531"
---
# <a name="how-to-display-web-style-links-with-the-windows-forms-richtextbox-control"></a>Cómo: Mostrar vínculos de estilo Web con el control RichTextBox de formularios Windows Forms

El control Windows Forms <xref:System.Windows.Forms.RichTextBox> puede mostrar vínculos Web en color y subrayado. Puede escribir código que abre una ventana del explorador que muestra el sitio Web especificado en el texto del vínculo cuando se hace clic en el vínculo.

### <a name="to-link-to-a-web-page-with-the-richtextbox-control"></a>Para vincular a una página web con el control RichTextBox

1. Establezca la <xref:System.Windows.Forms.RichTextBox.Text%2A> propiedad en una cadena que incluya una dirección URL válida (por ejemplo,"http://www.microsoft.com/").

2. Asegúrese de que la propiedad <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A> está establecida en `true` (valor predeterminado).

3. Cree una nueva instancia global del objeto <xref:System.Diagnostics.Process>.

4. Escriba un controlador de eventos para el evento <xref:System.Windows.Forms.RichTextBox.LinkClicked> que envía el texto deseado al explorador.

    En el ejemplo siguiente, el evento <xref:System.Windows.Forms.RichTextBox.LinkClicked> abre una instancia de Internet Explorer en la dirección URL especificada en la propiedad <xref:System.Windows.Forms.RichTextBox.Text%2A> del control <xref:System.Windows.Forms.RichTextBox>. En este ejemplo se da por supuesto un formulario con un control <xref:System.Windows.Forms.RichTextBox>.

    > [!IMPORTANT]
    > Al llamar al método <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType>, se producirá una excepción <xref:System.Security.SecurityException> si se ejecuta el código en un contexto de confianza parcial debido a privilegios insuficientes. Para obtener más información, vea [Code Access Security Basics](../../misc/code-access-security-basics.md) (Aspectos básicos de seguridad de acceso del código).

    ```vb
    Public p As New System.Diagnostics.Process
    Private Sub RichTextBox1_LinkClicked _
       (ByVal sender As Object, ByVal e As _
       System.Windows.Forms.LinkClickedEventArgs) _
       Handles RichTextBox1.LinkClicked
          ' Call Process.Start method to open a browser
          ' with link text as URL.
          p = System.Diagnostics.Process.Start("IExplore.exe", e.LinkText)
    End Sub
    ```

    ```csharp
    public System.Diagnostics.Process p = new System.Diagnostics.Process();

    private void richTextBox1_LinkClicked(object sender,
    System.Windows.Forms.LinkClickedEventArgs e)
    {
       // Call Process.Start method to open a browser
       // with link text as URL.
       p = System.Diagnostics.Process.Start("IExplore.exe", e.LinkText);
    }
    ```

    ```cpp
    public:
       System::Diagnostics::Process ^ p;

    private:
       void richTextBox1_LinkClicked(System::Object ^  sender,
          System::Windows::Forms::LinkClickedEventArgs ^  e)
       {
          // Call Process.Start method to open a browser
          // with link text as URL.
          p = System::Diagnostics::Process::Start("IExplore.exe",
             e->LinkText);
       }
    ```

    (Visual C++) Debe inicializar el proceso `p`, lo que puede hacer si incluye la siguiente instrucción en el constructor del formulario:

    ```cpp
    p = gcnew System::Diagnostics::Process();
    ```

    (Visual C#, visual C++) Coloque el siguiente código en el constructor del formulario para registrar el controlador de eventos.

    ```csharp
    this.richTextBox1.LinkClicked += new
       System.Windows.Forms.LinkClickedEventHandler
       (this.richTextBox1_LinkClicked);
    ```

    ```cpp
    this->richTextBox1->LinkClicked += gcnew
       System::Windows::Forms::LinkClickedEventHandler
       (this, &Form1::richTextBox1_LinkClicked);
    ```

    Es importante detener inmediatamente el proceso que ha creado una vez que haya terminado de trabajar con él. Al hacer referencia al código presentado anteriormente, el código para detener el proceso podría ser similar al siguiente:

    ```vb
    Public Sub StopWebProcess()
       p.Kill()
    End Sub
    ```

    ```csharp
    public void StopWebProcess()
    {
       p.Kill();
    }
    ```

    ```cpp
    public: void StopWebProcess()
    {
       p->Kill();
    }
    ```

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A>
- <xref:System.Windows.Forms.RichTextBox.LinkClicked>
- <xref:System.Windows.Forms.RichTextBox>
- [RichTextBox (control)](richtextbox-control-windows-forms.md)
- [Controles que se utilizan en Windows Forms](controls-to-use-on-windows-forms.md)
