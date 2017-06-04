---
title: "C&#243;mo: Crear un cuadro de texto de contrase&#241;a con el control TextBox de formularios Windows Forms | Microsoft Docs"
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
  - "cuadros de contraseña, crear"
  - "PasswordChar (propiedad de cuadros de texto)"
  - "contraseñas, máscara de entrada"
  - "contraseñas, cuadro de texto de contraseña"
  - "TextBox (control) [Windows Forms], escribir contraseñas"
ms.assetid: d105d6b9-3d50-44cd-80d8-2c0e2f486727
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# C&#243;mo: Crear un cuadro de texto de contrase&#241;a con el control TextBox de formularios Windows Forms
Un cuadro de contraseña es un cuadro de texto de formularios Windows Forms que muestra caracteres marcadores mientras el usuario escribe una cadena.  
  
### Para crear un cuadro de texto de contraseña  
  
1.  Establezca la propiedad <xref:System.Windows.Forms.TextBox.PasswordChar%2A> del control <xref:System.Windows.Forms.TextBox> en un carácter específico.  
  
     La propiedad <xref:System.Windows.Forms.TextBox.PasswordChar%2A> especifica el carácter que se muestra en el cuadro de texto.  Por ejemplo, si desea que se muestren asteriscos en el cuadro de contraseña, especifique \* como valor de la propiedad <xref:System.Windows.Forms.TextBox.PasswordChar%2A> en la ventana Propiedades.  Independientemente del carácter que escriba el usuario en el cuadro de texto, se mostrarán asteriscos.  
  
2.  \(Opcional\) Establezca la propiedad <xref:System.Windows.Forms.TextBoxBase.MaxLength%2A>.  La propiedad determina cuántos caracteres se pueden escribir en el cuadro de texto.  Si se supera la longitud máxima, el sistema emite un sonido y el cuadro de texto deja de admitir caracteres.  Sin embargo, puede que no desee hacer esto, ya que la longitud máxima de una contraseña podría resultar útil a los piratas informáticos que intenten adivinar la contraseña.  
  
     El ejemplo de código siguiente muestra cómo se inicializa un cuadro de texto que aceptará una cadena de 14 caracteres de longitud como máximo y mostrará asteriscos en lugar de la cadena.  El procedimiento `InitializeMyControl`  no se ejecutará automáticamente; es necesario llamarlo.  
  
    > [!IMPORTANT]
    >  El uso de la propiedad <xref:System.Windows.Forms.TextBox.PasswordChar%2A> en un cuadro de texto puede ayudar a asegurarse de que otras personas no podrán determinar la contraseña de un usuario si ven al usuario cuando la escribe.  Esta medida de seguridad no cubre cualquier tipo de almacenamiento o transmisión de la contraseña que pueda tener lugar por la lógica de la aplicación.  Puesto que el texto escrito no está cifrado de ningún modo, debe tratarlo como información confidencial.  Incluso si no aparece como tal, la contraseña se sigue tratando como una cadena de texto sin formato \(a menos que haya implementado alguna medida de seguridad adicional\).  
  
    ```vb  
    Private Sub InitializeMyControl()  
       ' Set to no text.  
       TextBox1.Text = ""  
       ' The password character is an asterisk.  
       TextBox1.PasswordChar = "*"  
       ' The control will allow no more than 14 characters.  
       TextBox1.MaxLength = 14  
    End Sub  
  
    ```  
  
    ```csharp  
    private void InitializeMyControl()  
    {  
       // Set to no text.  
       textBox1.Text = "";  
       // The password character is an asterisk.  
       textBox1.PasswordChar = '*';  
       // The control will allow no more than 14 characters.  
       textBox1.MaxLength = 14;  
    }  
  
    ```  
  
    ```cpp  
    private:  
       void InitializeMyControl()  
       {  
          // Set to no text.  
          textBox1->Text = "";  
          // The password character is an asterisk.  
          textBox1->PasswordChar = '*';  
          // The control will allow no more than 14 characters.  
          textBox1->MaxLength = 14;  
       }  
    ```  
  
## Vea también  
 <xref:System.Windows.Forms.TextBox>   
 [Información general sobre el control TextBox](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)   
 [Cómo: Controlar el punto de inserción en un control TextBox de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)   
 [Cómo: Crear un cuadro de texto de sólo lectura](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)   
 [Cómo: Insertar comillas en una cadena](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)   
 [Cómo: Seleccionar texto en el control TextBox de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)   
 [Cómo: Ver múltiples líneas en el control TextBox de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)   
 [TextBox \(Control\)](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)