---
title: 'Cómo: Mostrar vínculos de estilo Web con el control RichTextBox de formularios Windows Forms'
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
ms.openlocfilehash: bd813d479cd4dfb61a08d9a8c4a4e7612084e878
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33532612"
---
# <a name="how-to-display-web-style-links-with-the-windows-forms-richtextbox-control"></a>Cómo: Mostrar vínculos de estilo Web con el control RichTextBox de formularios Windows Forms
Los formularios Windows Forms <xref:System.Windows.Forms.RichTextBox> control puede mostrar vínculos Web en color y subrayados. Puede escribir código que se abre una ventana del explorador que muestra el sitio Web especificado en el texto del vínculo cuando se hace clic en el vínculo.  
  
### <a name="to-link-to-a-web-page-with-the-richtextbox-control"></a>Para vincular a una página Web con el control RichTextBox  
  
1.  Establecer el <xref:System.Windows.Forms.RichTextBox.Text%2A> propiedad a una cadena que incluye una dirección URL válida (por ejemplo, "http://www.microsoft.com/").  
  
2.  Asegúrese de que el <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A> propiedad está establecida en `true` (valor predeterminado).  
  
3.  Crear una nueva instancia global de la <xref:System.Diagnostics.Process> objeto.  
  
4.  Escribir un controlador de eventos para el <xref:System.Windows.Forms.RichTextBox.LinkClicked> eventos que envía al explorador el texto que desee.  
  
     En el ejemplo siguiente, la <xref:System.Windows.Forms.RichTextBox.LinkClicked> evento abre una instancia de Internet Explorer para la dirección URL especificada en el <xref:System.Windows.Forms.RichTextBox.Text%2A> propiedad de la <xref:System.Windows.Forms.RichTextBox> control. En este ejemplo se da por supuesto un formulario con un <xref:System.Windows.Forms.RichTextBox> control.  
  
    > [!IMPORTANT]
    >  Que realiza la llamada la <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> método, se producirá un <xref:System.Security.SecurityException> excepción si está ejecutando el código en un contexto de confianza parcial debido a privilegios suficientes. Para obtener más información, vea [Code Access Security Basics](../../../../docs/framework/misc/code-access-security-basics.md) (Aspectos básicos de seguridad de acceso del código).  
  
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
  
     Es importante detener inmediatamente el proceso que se ha creado una vez que haya terminado de trabajar con él. Consultar el código presentado anteriormente, el código para detener el proceso podría ser similar al siguiente:  
  
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
 <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A>  
 <xref:System.Windows.Forms.RichTextBox.LinkClicked>  
 <xref:System.Windows.Forms.RichTextBox>  
 [RichTextBox (control)](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)  
 [Controles que se utilizan en formularios Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
