---
title: "C&#243;mo: Determinar el formulario secundario MDI activo | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "formularios secundarios"
  - "Portapapeles, copiar datos"
  - "MDI, activar formularios"
  - "MDI, ventanas secundarias"
  - "MDI, buscar el foco"
ms.assetid: 33880ec3-0207-4c2b-a616-ff140443cc0f
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# C&#243;mo: Determinar el formulario secundario MDI activo
En determinadas ocasiones, deseará proporcionar un comando que actúe sobre el control que tiene el foco en el formulario secundario actualmente activo.  Por ejemplo, suponga que desea copiar texto seleccionado desde el cuadro de texto del formulario secundario al Portapapeles.  Deberá crear un procedimiento que copie el texto seleccionado al Portapapeles mediante el evento <xref:System.Windows.Forms.Control.Click> del elemento de menú Copiar del menú estándar Edición.  
  
 Dado que una aplicación MDI puede tener muchas instancias del mismo formulario secundario, el procedimiento necesita saber qué formulario debe utilizar.  Para especificar el formulario correcto, utilice la propiedad <xref:System.Windows.Forms.Form.ActiveMdiChild%2A>, que devuelve el formulario secundario que tiene el foco o el que estuvo activo más recientemente.  
  
 Cuando tenga varios controles en un formulario, deberá especificar también qué control está activo.  Al igual que la propiedad <xref:System.Windows.Forms.Form.ActiveMdiChild%2A>, la propiedad <xref:System.Windows.Forms.ContainerControl.ActiveControl%2A> devuelve el control que tiene el foco en el formulario secundario activo.  El procedimiento siguiente ilustra un procedimiento de copia, al que se puede llamar desde un menú de un formulario secundario, un menú del formulario MDI o un botón de la barra de herramientas.  
  
### Para determinar el formulario secundario MDI activo \(a fin de copiar el texto que contiene en el Portapapeles\)  
  
1.  Dentro de un método, copie en el Portapapeles el texto del control activo del formulario secundario activo.  
  
    > [!NOTE]
    >  En este ejemplo se supone que hay un formulario primario MDI \(`Form1`\) que tiene una o varias ventanas secundarias MDI que, a su vez, contienen un control <xref:System.Windows.Forms.RichTextBox>.  Para obtener más información, vea [Crear formularios primarios MDI](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md).  
  
    ```vb  
    Public Sub mniCopy_Click(ByVal sender As Object, _  
       ByVal e As System.EventArgs) Handles mniCopy.Click  
  
       ' Determine the active child form.  
       Dim activeChild As Form = Me.ActiveMDIChild  
  
       ' If there is an active child form, find the active control, which  
       ' in this example should be a RichTextBox.  
       If (Not activeChild Is Nothing) Then  
          Dim theBox As RichTextBox = _  
            TryCast(activeChild.ActiveControl, RichTextBox)  
  
          If (Not theBox Is Nothing) Then  
             'Put selected text on Clipboard.  
             Clipboard.SetDataObject(theBox.SelectedText)  
          Else  
             MessageBox.Show("You need to select a RichTextBox.")  
          End If  
       End If  
    End Sub  
  
    ```  
  
    ```csharp  
    protected void mniCopy_Click (object sender, System.EventArgs e)  
    {  
       // Determine the active child form.  
       Form activeChild = this.ActiveMdiChild;  
  
       // If there is an active child form, find the active control, which  
       // in this example should be a RichTextBox.  
       if (activeChild != null)  
       {    
          try  
          {  
             RichTextBox theBox = (RichTextBox)activeChild.ActiveControl;  
             if (theBox != null)  
             {  
                // Put the selected text on the Clipboard.  
                Clipboard.SetDataObject(theBox.SelectedText);  
  
             }  
          }  
          catch  
          {  
             MessageBox.Show("You need to select a RichTextBox.");  
          }  
       }  
    }  
  
    ```  
  
## Vea también  
 [Aplicaciones de interfaz de múltiples documentos \(MDI\)](../../../../docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md)   
 [Cómo: Crear formularios principales MDI](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)   
 [Cómo: Crear formularios MDI secundarios](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)   
 [Cómo: Enviar datos al formulario secundario MDI activo](../../../../docs/framework/winforms/advanced/how-to-send-data-to-the-active-mdi-child.md)   
 [Cómo: Organizar formularios MDI secundarios](../../../../docs/framework/winforms/advanced/how-to-arrange-mdi-child-forms.md)