---
title: Filtrar para mostrar vínculos de estilo web con el control RichTextBox de formularios Windows Forms
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
ms.openlocfilehash: faaa48051c80b6dfd330f15f72a38297ff2d1b9f
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59301885"
---
# <a name="how-to-display-web-style-links-with-the-windows-forms-richtextbox-control"></a>Filtrar para mostrar vínculos de estilo web con el control RichTextBox de formularios Windows Forms
Los formularios de Windows <xref:System.Windows.Forms.RichTextBox> control puede mostrar vínculos Web en color y subrayados. Puede escribir código que se abre una ventana del explorador que muestra el sitio Web especificado en el texto del vínculo cuando se hace clic en el vínculo.  
  
### <a name="to-link-to-a-web-page-with-the-richtextbox-control"></a>Para vincular a una página Web con el control RichTextBox  
  
1. Establecer el <xref:System.Windows.Forms.RichTextBox.Text%2A> propiedad en una cadena que incluye una dirección URL válida (por ejemplo, "http://www.microsoft.com/").  
  
2. Asegúrese de que el <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A> propiedad está establecida en `true` (valor predeterminado).  
  
3. Crear una nueva instancia global de la <xref:System.Diagnostics.Process> objeto.  
  
4. Escribir un controlador de eventos para el <xref:System.Windows.Forms.RichTextBox.LinkClicked> eventos que envía al explorador el texto deseado.  
  
     En el ejemplo siguiente, la <xref:System.Windows.Forms.RichTextBox.LinkClicked> evento abre una instancia de Internet Explorer a la dirección URL especificada en el <xref:System.Windows.Forms.RichTextBox.Text%2A> propiedad de la <xref:System.Windows.Forms.RichTextBox> control. En este ejemplo se supone un formulario con un <xref:System.Windows.Forms.RichTextBox> control.  
  
    > [!IMPORTANT]
    >  Que realiza la llamada la <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> método, se producirá un <xref:System.Security.SecurityException> excepción si está ejecutando el código en un contexto de confianza parcial por falta de privilegios. Para obtener más información, vea [Code Access Security Basics](../../misc/code-access-security-basics.md) (Aspectos básicos de seguridad de acceso del código).  
  
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
  
     ([!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Debe inicializar el proceso `p`, lo que puede hacer mediante la inclusión de la siguiente instrucción en el constructor del formulario:  
  
    ```cpp  
    p = gcnew System::Diagnostics::Process();  
    ```  
  
     (Visual C#, [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) coloque el código siguiente en el constructor del formulario para registrar el controlador de eventos.  
  
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
  
     Es importante detener inmediatamente el proceso que ha creado una vez que haya terminado de trabajar con él. Tomando como referencia el código presentado anteriormente, el código para detener el proceso podría ser similar al siguiente:  
  
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
- [Control RichTextBox](richtextbox-control-windows-forms.md)
- [Controles que se utilizan en formularios Windows Forms](controls-to-use-on-windows-forms.md)
