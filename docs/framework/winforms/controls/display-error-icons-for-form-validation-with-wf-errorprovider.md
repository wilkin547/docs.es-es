---
title: "C&#243;mo: Mostrar iconos de error para la validaci&#243;n de formularios con el componente ErrorProvider de formularios Windows Forms | Microsoft Docs"
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
  - "iconos de error"
  - "mensajes de error, mostrar iconos"
  - "ErrorProvider (componente) [Windows Forms], mostrar iconos de error"
  - "errores [Windows Forms], mostrar a usuarios"
ms.assetid: 3b681a32-9db4-497b-a34b-34980eabee46
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# C&#243;mo: Mostrar iconos de error para la validaci&#243;n de formularios con el componente ErrorProvider de formularios Windows Forms
Puede utilizar un componente <xref:System.Windows.Forms.ErrorProvider> de formularios Windows Forms para que se muestre un icono de error cuando el usuario escriba datos no válidos.  El formulario debe tener al menos dos controles para pasar de un control a otro mediante tabulación e invocar el código de validación.  
  
### Para mostrar un icono de error cuando el valor de un control no es válido  
  
1.  Agregue dos controles, por ejemplo, cuadros de texto, a un Windows Form.  
  
2.  Agregue un componente <xref:System.Windows.Forms.ErrorProvider> al formulario.  
  
3.  Seleccione el primer control y agregue código a su controlador de eventos <xref:System.Windows.Forms.Control.Validating>.  Para que este código se ejecute correctamente, el procedimiento debe estar conectado al evento.  Para obtener más información, vea [How to: Create Event Handlers at Run Time for Windows Forms](../../../../docs/framework/winforms/how-to-create-event-handlers-at-run-time-for-windows-forms.md).  
  
     En el código siguiente se comprueba la validez de los datos escritos por el usuario; si los datos no son válidos, se llama al método <xref:System.Windows.Forms.ErrorProvider.SetError%2A>.  El primer argumento del método <xref:System.Windows.Forms.ErrorProvider.SetError%2A> especifica junto a qué control se muestra el icono.  El segundo argumento es el texto de error que debe mostrarse.  
  
    ```vb  
    Private Sub TextBox1_Validating(ByVal Sender As Object, _  
       ByVal e As System.ComponentModel.CancelEventArgs) Handles _  
       TextBox1.Validating  
          If Not IsNumeric(TextBox1.Text) Then  
             ErrorProvider1.SetError(TextBox1, "Not a numeric value.")  
          Else  
             ' Clear the error.  
             ErrorProvider1.SetError(TextBox1, "")  
          End If  
    End Sub  
  
    ```  
  
    ```csharp  
    protected void textBox1_Validating (object sender,  
       System.ComponentModel.CancelEventArgs e)  
    {  
       try  
       {  
          int x = Int32.Parse(textBox1.Text);  
          errorProvider1.SetError(textBox1, "");  
       }  
       catch (Exception ex)  
       {  
          errorProvider1.SetError(textBox1, "Not an integer value.");  
       }  
    }  
  
    ```  
  
    ```cpp  
    private:  
       System::Void textBox1_Validating(System::Object ^  sender,  
          System::ComponentModel::CancelEventArgs ^  e)  
       {  
          try  
          {  
             int x = Int32::Parse(textBox1->Text);  
             errorProvider1->SetError(textBox1, "");  
          }  
          catch (System::Exception ^ ex)  
          {  
             errorProvider1->SetError(textBox1, "Not an integer value.");  
          }  
       }  
    ```  
  
     \([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\) Coloque el código siguiente en el constructor del formulario para registrar el controlador de eventos.  
  
    ```csharp  
    this.textBox1.Validating += new  
    System.ComponentModel.CancelEventHandler(this.textBox1_Validating);  
  
    ```  
  
    ```cpp  
    this->textBox1->Validating += gcnew  
       System::ComponentModel::CancelEventHandler  
       (this, &Form1::textBox1_Validating);  
    ```  
  
4.  Ejecute el proyecto.  Escriba datos no válidos \(en este ejemplo, no numéricos\) en el primer control y, a continuación, utilice el tabulador para pasar al segundo.  Cuando se muestre el icono de error, apunte al icono con el puntero del mouse para ver el texto de error.  
  
## Vea también  
 <xref:System.Windows.Forms.ErrorProvider.SetError%2A>   
 [Información general del componente ErrorProvider](../../../../docs/framework/winforms/controls/errorprovider-component-overview-windows-forms.md)   
 [Cómo: Ver errores de un conjunto de datos con el componente ErrorProvider de formularios Windows Forms](../../../../docs/framework/winforms/controls/view-errors-within-a-dataset-with-wf-errorprovider-component.md)