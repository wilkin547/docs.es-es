---
title: Procedimiento para mostrar vínculos de estilo web con el control RichTextBox de formularios Windows Forms
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
ms.openlocfilehash: ce71981f7b233d3e168689c766128646eed3e981
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046184"
---
# <a name="how-to-display-web-style-links-with-the-windows-forms-richtextbox-control"></a>Procedimiento para mostrar vínculos de estilo web con el control RichTextBox de formularios Windows Forms

El control <xref:System.Windows.Forms.RichTextBox> Windows Forms puede mostrar vínculos Web en color y subrayado. Puede escribir código que abre una ventana del explorador que muestra el sitio Web especificado en el texto del vínculo cuando se hace clic en el vínculo.

### <a name="to-link-to-a-web-page-with-the-richtextbox-control"></a>Para vincular a una página web con el control RichTextBox

1. Establezca la <xref:System.Windows.Forms.RichTextBox.Text%2A> propiedad en una cadena que incluya una dirección URL válida (por ejemplo,"http://www.microsoft.com/").

2. Asegúrese de que <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A> la propiedad está establecida `true` en (el valor predeterminado).

3. Cree una nueva instancia global del <xref:System.Diagnostics.Process> objeto.

4. Escriba un controlador de eventos para <xref:System.Windows.Forms.RichTextBox.LinkClicked> el evento que envía al explorador el texto deseado.

    En el ejemplo siguiente, el <xref:System.Windows.Forms.RichTextBox.LinkClicked> evento abre una instancia de Internet Explorer en la dirección URL especificada en <xref:System.Windows.Forms.RichTextBox.Text%2A> la propiedad del <xref:System.Windows.Forms.RichTextBox> control. En este ejemplo se da por supuesto <xref:System.Windows.Forms.RichTextBox> un formulario con un control.

    > [!IMPORTANT]
    > Al llamar al <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> método, se producirá una <xref:System.Security.SecurityException> excepción si está ejecutando el código en un contexto de confianza parcial porque no tiene privilegios suficientes. Para obtener más información, vea [Code Access Security Basics](../../misc/code-access-security-basics.md) (Aspectos básicos de seguridad de acceso del código).

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

    (Visual C++) Debe inicializar el `p`proceso, que puede hacer incluyendo la siguiente instrucción en el constructor del formulario:

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
- [Controles que se utilizan en formularios Windows Forms](controls-to-use-on-windows-forms.md)
