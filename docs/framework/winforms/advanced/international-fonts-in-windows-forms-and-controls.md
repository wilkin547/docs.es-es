---
title: Fuentes internacionales en formularios y controles
ms.date: 03/30/2017
helpviewer_keywords:
- fonts [Windows Forms], international
- international applications [Windows Forms], character display
- fonts [Windows Forms], globalization considerations
- localization [Windows Forms], fonts
- Windows Forms controls, labels
- font fallback in Windows Forms
- globalization [Windows Forms], character sets
dev_langs:
- csharp
- vb
ms.assetid: 2c3066df-9bac-479a-82b2-79e484b346a3
ms.openlocfilehash: 59dde6bb384d644321a8ff5674d735f8e6d36fd0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743523"
---
# <a name="international-fonts-in-windows-forms-and-controls"></a>Fuentes internacionales en Windows Forms y controles

En aplicaciones internacionales, el método recomendado para seleccionar fuentes es usar la reserva de fuentes siempre que sea posible. La reserva de fuentes significa que el sistema determina el script al que pertenece el carácter.

## <a name="using-font-fallback"></a>Usar la reserva de fuentes

Para aprovechar esta característica, no establezca la propiedad <xref:System.Drawing.Font> del formulario o de cualquier otro elemento. La aplicación usará automáticamente la fuente predeterminada del sistema, que difiere de un idioma localizado del sistema operativo a otro. Cuando se ejecuta la aplicación, el sistema proporcionará automáticamente la fuente correcta para la referencia cultural seleccionada en el sistema operativo.

Existe una excepción a la regla de no establecer la fuente, que es para cambiar el estilo de fuente. Esto puede ser importante para una aplicación en la que el usuario hace clic en un botón para que el texto de un cuadro de texto aparezca en negrita. Para ello, debe escribir una función para cambiar el estilo de fuente del cuadro de texto a negrita, en función de la fuente del formulario. Es importante llamar a esta función en dos lugares: en el controlador de eventos <xref:System.Windows.Forms.Control.Click> del botón y en el controlador de eventos <xref:System.Windows.Forms.Control.FontChanged>. Si solo se llama a la función en el controlador de eventos <xref:System.Windows.Forms.Control.Click> y algún otro fragmento de código cambia la familia de fuentes del formulario completo, el cuadro de texto no cambia con el resto del formulario.

```vb
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
```

```csharp
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

Sin embargo, al localizar la aplicación, la fuente en negrita puede mostrarse mal para determinados idiomas. Si esto supone un problema, querrá que los localizadores tengan la opción de cambiar la fuente de negrita a texto normal. Dado que los localizadores no suelen ser desarrolladores y no tienen acceso al código fuente, solo a los archivos de recursos, esta opción debe establecerse en los archivos de recursos. Para ello, debe establecer la propiedad <xref:System.Drawing.Font.Bold%2A> en `true`. Esto hace que la configuración de fuente se escriba en los archivos de recursos, donde los localizadores pueden modificarla. Después, escriba el código después del método `InitializeComponent` para restablecer la fuente en función de la fuente del formulario, pero con el estilo de fuente especificado en el archivo de recursos.

```vb
TextBox1.Font = New System.Drawing.Font(Me.Font, TextBox1.Font.Style)
```

```csharp
textBox1.Font = new System.Drawing.Font(this.Font, textBox1.Font.Style);
```
  
## <a name="see-also"></a>Consulte también

- [Utilizar fuentes y texto](using-fonts-and-text.md)
