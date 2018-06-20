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
dev_langs:
- csharp
- vb
ms.assetid: 2c3066df-9bac-479a-82b2-79e484b346a3
ms.openlocfilehash: b2738f174c9837a2ba83c1306f4617f39ce17de1
ms.sourcegitcommit: 6bc4efca63e526ce6f2d257fa870f01f8c459ae4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "36208604"
---
# <a name="international-fonts-in-windows-forms-and-controls"></a><span data-ttu-id="635a8-102">Fuentes internacionales en formularios Windows Forms y controles</span><span class="sxs-lookup"><span data-stu-id="635a8-102">International fonts in Windows Forms and controls</span></span>

<span data-ttu-id="635a8-103">En aplicaciones internacionales, el método recomendado para seleccionar fuentes es usar la reserva de fuentes siempre que sea posible.</span><span class="sxs-lookup"><span data-stu-id="635a8-103">In International applications, the recommended method of selecting fonts is to use font fallback wherever possible.</span></span> <span data-ttu-id="635a8-104">Reserva de fuentes significa que el sistema determina a qué script el carácter pertenece.</span><span class="sxs-lookup"><span data-stu-id="635a8-104">Font fallback means that the system determines what script the character belongs to.</span></span>

## <a name="using-font-fallback"></a><span data-ttu-id="635a8-105">Uso de reserva de fuentes</span><span class="sxs-lookup"><span data-stu-id="635a8-105">Using font fallback</span></span>

<span data-ttu-id="635a8-106">Para aprovechar las ventajas de esta característica, no establece la <xref:System.Drawing.Font> propiedad para el formulario o cualquier otro elemento.</span><span class="sxs-lookup"><span data-stu-id="635a8-106">To take advantage of this feature, don't set the <xref:System.Drawing.Font> property for your form or any other element.</span></span> <span data-ttu-id="635a8-107">La aplicación usará automáticamente la fuente predeterminada del sistema, que es diferente del idioma del sistema operativo a otro.</span><span class="sxs-lookup"><span data-stu-id="635a8-107">The application will automatically use the default system font, which differs from one localized language of the operating system to another.</span></span> <span data-ttu-id="635a8-108">Cuando se ejecuta la aplicación, el sistema proporciona automáticamente la fuente correcta para la referencia cultural seleccionada en el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="635a8-108">When the application runs, the system will automatically provide the correct font for the culture selected in the operating system.</span></span>

<span data-ttu-id="635a8-109">Hay una excepción a la regla de no establecer la fuente, que es para cambiar el estilo de fuente.</span><span class="sxs-lookup"><span data-stu-id="635a8-109">There's an exception to the rule of not setting the font, which is for changing the font style.</span></span> <span data-ttu-id="635a8-110">Esto podría ser importante para una aplicación en el que el usuario hace clic en un botón para que el texto en un cuadro de texto aparecen en negrita.</span><span class="sxs-lookup"><span data-stu-id="635a8-110">This might be important for an application in which the user clicks a button to make text in a text box appear in boldface.</span></span> <span data-ttu-id="635a8-111">Para ello, escribiría una función para cambiar el estilo de fuente del cuadro de texto en negrita, en función de la fuente del formulario es.</span><span class="sxs-lookup"><span data-stu-id="635a8-111">To do that, you would write a function to change the text box's font style to bold, based on whatever the form's font is.</span></span> <span data-ttu-id="635a8-112">Es importante llamar a esta función en dos lugares: en el botón <xref:System.Windows.Forms.Control.Click> controlador de eventos y en el <xref:System.Windows.Forms.Control.FontChanged> controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="635a8-112">It's important to call this function in two places: in the button's <xref:System.Windows.Forms.Control.Click> event handler and in the <xref:System.Windows.Forms.Control.FontChanged> event handler.</span></span> <span data-ttu-id="635a8-113">Si se llama a la función solo en el <xref:System.Windows.Forms.Control.Click> controlador de eventos y alguna otra parte de código cambia la familia de fuentes de todo el formulario, el cuadro de texto no cambia con el resto del formulario.</span><span class="sxs-lookup"><span data-stu-id="635a8-113">If the function is called only in the <xref:System.Windows.Forms.Control.Click> event handler and some other piece of code changes the font family of the entire form, the text box doesn't change with the rest of the form.</span></span>

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

<span data-ttu-id="635a8-114">Sin embargo, al localizar la aplicación, la fuente en negrita puede mostrarse incorrectamente en algunos idiomas.</span><span class="sxs-lookup"><span data-stu-id="635a8-114">However, when you localize your application, the bold font may display poorly for certain languages.</span></span> <span data-ttu-id="635a8-115">Si se trata de un problema, desea que los localizadores tengan la posibilidad de cambiar la fuente de negrita a texto normal.</span><span class="sxs-lookup"><span data-stu-id="635a8-115">If this is a concern, you want the localizers to have the option of switching the font from bold to regular text.</span></span> <span data-ttu-id="635a8-116">Dado que los localizadores normalmente no son programadores y no tienen acceso al código fuente, solo a los archivos de recursos, esta opción debe establecerse en los archivos de recursos.</span><span class="sxs-lookup"><span data-stu-id="635a8-116">Since localizers are typically not developers and don't have access to source code, only to resource files, this option needs to be set in the resource files.</span></span> <span data-ttu-id="635a8-117">Para ello, debe establecer el <xref:System.Drawing.Font.Bold%2A> propiedad `true`.</span><span class="sxs-lookup"><span data-stu-id="635a8-117">To do this, you would set the <xref:System.Drawing.Font.Bold%2A> property to `true`.</span></span> <span data-ttu-id="635a8-118">Esto da como resultado el valor de fuente que se escribe en los archivos de recursos, donde pueden editar los localizadores.</span><span class="sxs-lookup"><span data-stu-id="635a8-118">This results in the font setting being written out to the resource files, where localizers can edit it.</span></span> <span data-ttu-id="635a8-119">A continuación, escribir código después de la `InitializeComponent` método para restablecer la fuente basada en la fuente del formulario, pero usando el estilo de fuente especificado en el archivo de recursos.</span><span class="sxs-lookup"><span data-stu-id="635a8-119">You then write code after the `InitializeComponent` method to reset the font based on whatever the form's font is, but using the font style specified in the resource file.</span></span>

```vb
TextBox1.Font = New System.Drawing.Font(Me.Font, TextBox1.Font.Style)
```

```csharp
textBox1.Font = new System.Drawing.Font(this.Font, textBox1.Font.Style);
```
  
## <a name="see-also"></a><span data-ttu-id="635a8-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="635a8-120">See also</span></span>

[<span data-ttu-id="635a8-121">Globalizar aplicaciones de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="635a8-121">Globalizing Windows Forms applications</span></span>](globalizing-windows-forms.md)  
[<span data-ttu-id="635a8-122">Utilizar fuentes y texto</span><span class="sxs-lookup"><span data-stu-id="635a8-122">Using Fonts and Text</span></span>](using-fonts-and-text.md)