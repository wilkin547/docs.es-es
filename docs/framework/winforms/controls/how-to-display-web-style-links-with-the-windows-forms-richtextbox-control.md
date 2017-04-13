---
title: "C&#243;mo: Mostrar v&#237;nculos de estilo Web con el control RichTextBox de formularios Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "ejemplos [Windows Forms], cuadros de texto"
  - "RichTextBox (control) [Windows Forms], vincular a páginas Web"
  - "cuadros de texto, mostrar vínculos Web"
ms.assetid: 95089a37-a202-4f7a-94ee-6ee312908851
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# C&#243;mo: Mostrar v&#237;nculos de estilo Web con el control RichTextBox de formularios Windows Forms
El control <xref:System.Windows.Forms.RichTextBox> de formularios Windows Forms puede mostrar vínculos Web en color y subrayados.  Puede escribir código que abra una ventana de explorador que muestre el sitio web especificado en el texto del vínculo, al hacer clic en el vínculo.  
  
### Para vincular una página Web con el control RichTextBox  
  
1.  Establezca la propiedad <xref:System.Windows.Forms.RichTextBox.Text%2A> en una cadena que incluya una dirección URL válida \(por ejemplo, "http:\/\/www.microsoft.com\/spanish"\).  
  
2.  Asegúrese de que la propiedad <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A> está establecida en `true` \(el valor predeterminado\).  
  
3.  Cree una nueva instancia global del objeto <xref:System.Diagnostics.Process>.  
  
4.  Escriba un controlador de eventos para el evento <xref:System.Windows.Forms.RichTextBox.LinkClicked> que envíe al explorador el texto deseado.  
  
     En el ejemplo siguiente, el evento <xref:System.Windows.Forms.RichTextBox.LinkClicked> abre una instancia de Internet Explorer con una dirección URL especificada en la propiedad <xref:System.Windows.Forms.RichTextBox.Text%2A> del control <xref:System.Windows.Forms.RichTextBox>.  Este ejemplo supone un formulario con un control <xref:System.Windows.Forms.RichTextBox>.  
  
    > [!IMPORTANT]
    >  Al llamar al método <xref:System.Diagnostics.Process.Start%2A?displayProperty=fullName> encontrará una excepción <xref:System.Security.SecurityException> por falta de privilegios si ejecuta el código en un contexto de confianza parcial.  Para obtener más información, vea [Code Access Security Basics](../../../../docs/framework/misc/code-access-security-basics.md).  
  
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
  
     \([!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\) Debe inicializar el proceso`p`. Puede hacerlo incluyendo la siguiente instrucción en el constructor del formulario:  
  
    ```cpp  
    p = gcnew System::Diagnostics::Process();  
    ```  
  
     \([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\) Coloque el código siguiente en el constructor del formulario para registrar el controlador de eventos.  
  
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
  
     Es importante detener inmediatamente el proceso que ha creado una vez que termine de trabajar con él.  Tomando como referencia el código anterior, el código para detener el proceso sería similar al siguiente:  
  
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
  
## Vea también  
 <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A>   
 <xref:System.Windows.Forms.RichTextBox.LinkClicked>   
 <xref:System.Windows.Forms.RichTextBox>   
 [RichTextBox \(Control\)](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)   
 [Controles que se utilizan en formularios Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)