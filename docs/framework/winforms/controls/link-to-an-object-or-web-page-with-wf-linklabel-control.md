---
title: "C&#243;mo: Establecer v&#237;nculos con un objeto o p&#225;gina Web mediante el control LinkLabel de formularios Windows Forms | Microsoft Docs"
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
  - "ejemplos [Windows Forms], LinkLabel (control)"
  - "vincular, a otros formularios"
  - "LinkLabel (control) [Windows Forms], ejemplos"
  - "LinkLabel (control) [Windows Forms], vincular a un objeto o una página Web"
  - "vínculos, a otros formularios"
  - "control de vínculos de páginas Web"
  - "Windows Forms, enlazar a objetos"
  - "Windows Forms, vincular a páginas Web"
ms.assetid: 6c91c975-3cb7-4504-82f0-fc6255f8fb85
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# C&#243;mo: Establecer v&#237;nculos con un objeto o p&#225;gina Web mediante el control LinkLabel de formularios Windows Forms
El control <xref:System.Windows.Forms.LinkLabel> de formularios Windows Forms permite crear vínculos de tipo Web en los formularios.  Puede configurarlo de forma que cuando se haga clic en él, cambie su color para indicar que se visitó el vínculo.  Para obtener más información sobre el cambio de color, vea [Cómo: Cambiar la apariencia del control LinkLabel de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md).  
  
## Vincular a otro formulario  
  
#### Para establecer un vínculo a otro formulario con un control LinkLabel  
  
1.  Establezca la leyenda adecuada en la propiedad <xref:System.Windows.Forms.LinkLabel.Text%2A>.  
  
2.  Establezca la propiedad <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> para determinar qué parte de la leyenda se indicará como vínculo.  La forma en que se indica depende de las propiedades relacionadas con la apariencia de la etiqueta del vínculo.  El valor de <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> se representa con un objeto <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> que contiene dos números: la posición del carácter inicial y el número de caracteres.  La propiedad <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> se puede establecer en la ventana Propiedades o en código de la siguiente manera:  
  
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
  
3.  En el controlador de eventos <xref:System.Windows.Forms.LinkLabel.LinkClicked>, invoque el método <xref:System.Windows.Forms.Form.Show%2A> para abrir otro formulario en el proyecto y establezca la propiedad <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> en `true`.  
  
    > [!NOTE]
    >  Una instancia de la clase <xref:System.Windows.Forms.LinkLabelLinkClickedEventArgs> lleva una referencia al control <xref:System.Windows.Forms.LinkLabel> en el que se hizo clic, por lo que no hay necesidad de convertir el objeto `sender` .  
  
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
  
## Vincular a una página Web  
 El control <xref:System.Windows.Forms.LinkLabel> puede utilizarse también para mostrar una página Web con el explorador predeterminado.  
  
#### Para iniciar Internet Explorer y establecer un vínculo a una página Web mediante un control LinkLabel  
  
1.  Establezca la leyenda adecuada en la propiedad <xref:System.Windows.Forms.LinkLabel.Text%2A>.  
  
2.  Establezca la propiedad <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> para determinar qué parte de la leyenda se indicará como vínculo.  
  
3.  En el controlador de eventos <xref:System.Windows.Forms.LinkLabel.LinkClicked>, en medio de un bloque de control de excepciones, llame a un segundo procedimiento que establezca la propiedad <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> en `true` y utilice el método <xref:System.Diagnostics.Process.Start%2A> para iniciar el explorador predeterminado con una dirección URL.  Para utilizar el método <xref:System.Diagnostics.Process.Start%2A>, tiene que agregar una referencia al espacio de nombres <xref:System.Diagnostics?displayProperty=fullName>.  
  
    > [!IMPORTANT]
    >  Si el código siguiente se ejecuta en un entorno parcialmente confiable \(como una unidad compartida\), el compilador JIT falla cuando se llama al método `VisitLink`.  La instrucción`System.Diagnostics.Process.Start` produce una solicitud de un vínculo que falla.  Al capturar la excepción cuando se llama al método `VisitLink`, el código siguiente garantiza que, si el compilador JIT falla, el error se controla correctamente.  
  
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
  
## Vea también  
 <xref:System.Diagnostics.Process.Start%2A?displayProperty=fullName>   
 [Información general sobre el control LinkLabel](../../../../docs/framework/winforms/controls/linklabel-control-overview-windows-forms.md)   
 [Cómo: Cambiar la apariencia del control LinkLabel de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md)   
 [LinkLabel \(Control\)](../../../../docs/framework/winforms/controls/linklabel-control-windows-forms.md)