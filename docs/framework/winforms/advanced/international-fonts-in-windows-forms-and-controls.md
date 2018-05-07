---
title: Fuentes internacionales en formularios Windows Forms y controles
ms.date: 03/30/2017
helpviewer_keywords:
- fonts [Windows Forms], international
- international applications [Windows Forms], character display
- fonts [Windows Forms], globalization considerations
- localization [Windows Forms], fonts
- Windows Forms controls, labels
- font fallback in Windows Forms
- globalization [Windows Forms], character sets
ms.assetid: 2c3066df-9bac-479a-82b2-79e484b346a3
ms.openlocfilehash: 38a6928dfb548c6b514b598dbebe5bbc62d2e3f8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="international-fonts-in-windows-forms-and-controls"></a>Fuentes internacionales en formularios Windows Forms y controles
En aplicaciones internacionales el método recomendado para seleccionar fuentes es usar la reserva de fuentes siempre que sea posible. Reserva de fuentes significa que el sistema determina a qué script el carácter pertenece.  
  
## <a name="using-font-fallback"></a>Uso de reserva de fuentes  
 Para aprovechar las ventajas de esta característica, no establezca la <xref:System.Drawing.Font> propiedad para el formulario o cualquier otro elemento. La aplicación usará automáticamente la fuente predeterminada del sistema, que es diferente del idioma del sistema operativo a otro. Cuando se ejecuta la aplicación, el sistema proporciona automáticamente la fuente correcta para la referencia cultural seleccionada en el sistema operativo.  
  
 Hay una excepción a la regla de no establecer la fuente, que es para cambiar el estilo de fuente. Esto podría ser importante para una aplicación en el que el usuario hace clic en un botón para que el texto en un cuadro de texto aparecen en negrita. Para ello, escribiría una función para cambiar el estilo de fuente del cuadro de texto en negrita, en función de la fuente del formulario es. Es importante llamar a esta función en dos lugares: en el botón <xref:System.Windows.Forms.Control.Click> controlador de eventos y en el <xref:System.Windows.Forms.Control.FontChanged> controlador de eventos. Si se llama a la función solo en el <xref:System.Windows.Forms.Control.Click> controlador de eventos y alguna otra parte de código cambia la familia de fuentes de todo el formulario, el cuadro de texto no cambiará con el resto del formulario.  
  
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
  
 Sin embargo, al localizar la aplicación, la fuente en negrita puede mostrarse incorrectamente en algunos idiomas. Si se trata de un problema, desea que los localizadores tengan la posibilidad de cambiar la fuente de negrita a texto normal. Dado que los localizadores normalmente no son programadores y no tiene acceso al código fuente, solo a los archivos de recursos, esta opción debe establecerse en los archivos de recursos. Para ello, debe establecer el <xref:System.Drawing.Font.Bold%2A> propiedad `true`. Esto da como resultado el valor de fuente que se escribe en los archivos de recursos, donde pueden editar los localizadores. A continuación, escribir código después de la `InitializeComponent` método para restablecer la fuente basada en la fuente del formulario, pero usando el estilo de fuente especificado en el archivo de recursos.  
  
```  
' Visual Basic  
TextBox1.Font = New System.Drawing.Font(Me.Font, TextBox1.Font.Style)  
  
// C#  
textBox1.Font = new System.Drawing.Font(this.Font, textBox1.Font.Style);  
```  
  
## <a name="see-also"></a>Vea también  
 [Globalizar Windows Forms](../../../../docs/framework/winforms/advanced/globalizing-windows-forms.md)  
 [Utilizar fuentes y texto](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
