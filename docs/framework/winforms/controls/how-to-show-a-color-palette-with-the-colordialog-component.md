---
title: "C&#243;mo: Mostrar una paleta de colores con el componente ColorDialog | Microsoft Docs"
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
  - "cuadro de diálogo de colores, mostrar paletas de colores"
  - "paletas de colores, cuadro de diálogo"
  - "paletas de colores, mostrar en el componente ColorDialog"
  - "Color (propiedad)"
  - "ColorDialog (componente), mostrar paletas de colores"
  - "colores, permitir selección a los usuarios"
  - "colores, mostrar paletas"
  - "paletas, mostrar color"
ms.assetid: ee050f61-dbc8-4436-ba22-51360981ab48
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# C&#243;mo: Mostrar una paleta de colores con el componente ColorDialog
El componente [ColorDialog](../../../../docs/framework/winforms/controls/colordialog-component-windows-forms.md) muestra una paleta de colores y devuelve una propiedad que contiene el color seleccionado por el usuario.  
  
### Para elegir un color utilizando el componente ColorDialog  
  
1.  Muestre el cuadro de diálogo mediante el método <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>.  
  
2.  Utilice la propiedad <xref:System.Windows.Forms.DialogResult> para determinar cómo se cerró el cuadro de diálogo.  
  
3.  Utilice la propiedad <xref:System.Windows.Forms.ColorDialog.Color%2A> del componente <xref:System.Windows.Forms.ColorDialog> para establecer el color elegido.  
  
     En el ejemplo siguiente, el controlador de eventos <xref:System.Windows.Forms.Control.Click> del control <xref:System.Windows.Forms.Button> abre un componente <xref:System.Windows.Forms.ColorDialog>.  Cuando se elige un color y el usuario hace clic en **Aceptar**, el color de fondo del control <xref:System.Windows.Forms.Button> se define como el color elegido.  En el ejemplo se supone que el formulario tiene un control <xref:System.Windows.Forms.Button> y un componente <xref:System.Windows.Forms.ColorDialog>.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
    ByVal e As System.EventArgs) Handles Button1.Click  
       If ColorDialog1.ShowDialog() = DialogResult.OK Then  
          Button1.BackColor = ColorDialog1.Color  
       End If  
    End Sub  
  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       if(colorDialog1.ShowDialog() == DialogResult.OK)  
       {  
          button1.BackColor = colorDialog1.Color;  
       }  
    }  
  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,   
          System::EventArgs ^ e)  
       {  
          if(colorDialog1->ShowDialog() == DialogResult::OK)  
          {  
             button1->BackColor = colorDialog1->Color;  
          }  
       }  
    ```  
  
     \([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\) Coloque el código siguiente en el constructor del formulario para registrar el controlador de eventos.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
  
    ```  
  
    ```cpp  
    this->button1->Click +=   
       gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## Vea también  
 <xref:System.Windows.Forms.ColorDialog>   
 [ColorDialog](../../../../docs/framework/winforms/controls/colordialog-component-windows-forms.md)