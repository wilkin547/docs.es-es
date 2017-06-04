---
title: "C&#243;mo: Mostrar una lista de fuentes con el componente FontDialog | Microsoft Docs"
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
  - "Fuente (cuadro de diálogo), mostrar"
  - "Font (propiedad), establecer mediante el componente FontDialog"
  - "FontDialog (componente) [Windows Forms]"
  - "fuentes, atributos"
  - "fuentes, seleccionar"
  - "fuentes, mostrar lista"
ms.assetid: 35692c1b-0937-4b7a-9207-1ae6bdc244a0
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# C&#243;mo: Mostrar una lista de fuentes con el componente FontDialog
El componente [FontDialog](../../../../docs/framework/winforms/controls/fontdialog-component-windows-forms.md) permite a los usuarios seleccionar una fuente y cambiar sus características de presentación, como el grosor y el tamaño.  
  
 La fuente seleccionada en el cuadro de diálogo se devuelve en la propiedad <xref:System.Windows.Forms.FontDialog.Font%2A>.  Por tanto, aprovechar la fuente seleccionada por el usuario es tan fácil como leer una propiedad.  
  
### Para seleccionar propiedades de fuente utilizando el componente FontDialog  
  
1.  Muestre el cuadro de diálogo mediante el método <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>.  
  
2.  Utilice la propiedad <xref:System.Windows.Forms.DialogResult> para determinar cómo se cerró el cuadro de diálogo.  
  
3.  Utilice la propiedad <xref:System.Windows.Forms.FontDialog.Font%2A> para definir la fuente deseada.  
  
     En el ejemplo siguiente, el controlador de eventos <xref:System.Windows.Forms.Control.Click> del control <xref:System.Windows.Forms.Button> abre un componente <xref:System.Windows.Forms.FontDialog>.  Cuando se elige una fuente y el usuario hace clic en **Aceptar**, la propiedad <xref:System.Windows.Forms.FontDialog.Font%2A> de un control <xref:System.Windows.Forms.TextBox> que está en el formulario se establece en la fuente seleccionada.  En el ejemplo se supone que el formulario tiene un control <xref:System.Windows.Forms.Button>, un control <xref:System.Windows.Forms.TextBox> y un componente <xref:System.Windows.Forms.FontDialog>.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles Button1.Click  
       If FontDialog1.ShowDialog() = DialogResult.OK Then  
          TextBox1.Font = FontDialog1.Font  
       End If  
    End Sub  
  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       if(fontDialog1.ShowDialog() == DialogResult.OK)  
       {  
          textBox1.Font = fontDialog1.Font;  
       }  
    }  
  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          if(fontDialog1->ShowDialog() == DialogResult::OK)  
          {  
             textBox1->Font = fontDialog1->Font;  
          }  
       }  
    ```  
  
     \([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] y [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\) Coloque el código siguiente en el constructor del formulario para registrar el controlador de eventos.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
  
    ```  
  
    ```cpp  
    button1->Click += gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## Vea también  
 <xref:System.Windows.Forms.FontDialog>   
 [FontDialog](../../../../docs/framework/winforms/controls/fontdialog-component-windows-forms.md)