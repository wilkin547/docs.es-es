---
title: "International Fonts in Windows Forms and Controls | Microsoft Docs"
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
  - "fonts, international"
  - "international applications [Windows Forms], character display"
  - "fonts, globalization considerations"
  - "localization [Windows Forms], fonts"
  - "Windows Forms controls, labels"
  - "font fallback in Windows Forms"
  - "globalization [Windows Forms], character sets"
ms.assetid: 2c3066df-9bac-479a-82b2-79e484b346a3
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# International Fonts in Windows Forms and Controls
En aplicaciones internacionales el método recomendado para seleccionar fuentes es usar la reserva de fuentes siempre que sea posible.  La reserva de fuentes significa que el sistema determina a qué script pertenece el carácter.  
  
## Utilizar la reserva de fuentes  
 Para aprovechar esta característica, no establezca la propiedad <xref:System.Drawing.Font> del formulario ni de ningún otro elemento  y la aplicación usará automáticamente la fuente predeterminada del sistema, que es distinta dependiendo del idioma del sistema operativo.  Cuando la aplicación se ejecuta, el sistema proporciona automáticamente la fuente adecuada para la referencia cultural seleccionada en el sistema operativo.  
  
 Hay una excepción a esta regla de no establecer la fuente, que es cuando se desea cambiar el estilo de la fuente.  Esto puede resultar importante en una aplicación en la que el usuario hace clic en un botón con el fin de que el texto de un cuadro de texto aparezca en negrita.  Para hacer esto, se ha de escribir una función que cambie el estilo de fuente del cuadro de texto a negrita, a partir de la fuente del formulario.  Es importante llamar a esta función en dos lugares: en el controlador del evento <xref:System.Windows.Forms.Control.Click> del botón y en el controlador del evento <xref:System.Windows.Forms.Control.FontChanged>.  Si se llama a la función sólo en el controlador del evento <xref:System.Windows.Forms.Control.Click> y alguna otra parte de código cambia la familia de la fuente de todo el formulario, el cuadro de texto no cambiará con el resto del formulario.  
  
```  
' Visual Basic  
Private Sub MakeBold()  
   ' Change the TextBox to a bold version of the form font  
   TextBox1.Font = New Font(Me.Font, FontStyle.Bold)  
End Sub  
  
Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
   ' Clicking this button makes the TextBox bold  
   MakeBold()  
End Sub  
  
Private Sub Form1_FontChanged(ByVal sender As Object, ByVal e As System.EventArgs) Handles MyBase.FontChanged  
   ' If the TextBox is already bold and the form's font changes,  
   ' change the TextBox to a bold version of the new form font  
   If (TextBox1.Font.Style = FontStyle.Bold) Then  
      MakeBold()  
   End If  
End Sub  
  
// C#  
private void button1_Click(object sender, System.EventArgs e)  
{  
   // Clicking this button makes the TextBox bold  
   MakeBold();  
}  
  
private void MakeBold()   
{  
   // Change the TextBox to a bold version of the form's font  
   textBox1.Font = new Font(this.Font, FontStyle.Bold);  
}  
  
private void Form1_FontChanged(object sender, System.EventArgs e)  
{  
   // If the TextBox is already bold and the form's font changes,  
   // change the TextBox to a bold version of the new form font  
   if (textBox1.Font.Style == FontStyle.Bold)   
   {  
      MakeBold();  
   }  
}  
```  
  
 Sin embargo, cuando se traduzca y adapte la aplicación, la fuente negrita puede mostrarse incorrectamente en algunos idiomas.  Si esto supone un problema, lo deseable es que los localizadores tengan la opción de cambiar la fuente de negrita a texto normal.  Sin embargo, como los localizadores normalmente no son programadores y no tienen acceso al código fuente, sólo a los archivos de recursos, esta opción tiene que establecerse en los archivos de recursos.  Para ello, establezca la propiedad <xref:System.Drawing.Font.Bold%2A> en `true`.  Esto hace que la configuración de fuente se escriba en los archivos de recursos, donde los localizadores pueden editarla.  Si lo desea, puede escribir código después del método `InitializeComponent`  para restablecer la fuente basada en la del formulario, pero usando el estilo de fuente especificado en el archivo de recursos.  
  
```  
' Visual Basic  
TextBox1.Font = New System.Drawing.Font(Me.Font, TextBox1.Font.Style)  
  
// C#  
textBox1.Font = new System.Drawing.Font(this.Font, textBox1.Font.Style);  
```  
  
## Vea también  
 [Globalizing Windows Forms](../../../../docs/framework/winforms/advanced/globalizing-windows-forms.md)   
 [Utilizar fuentes y texto](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)