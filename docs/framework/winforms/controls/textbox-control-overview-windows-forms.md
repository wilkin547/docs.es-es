---
title: Información general sobre el control TextBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- TextBox
helpviewer_keywords:
- TextBox control [Windows Forms], about TextBox controls
- text boxes [Windows Forms], adding
ms.assetid: d1a9c7f5-fa53-480a-a75c-158f8649ea2f
ms.openlocfilehash: 06ab460d720d17331881b5ba653263160eaf3cb3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742805"
---
# <a name="textbox-control-overview-windows-forms"></a><span data-ttu-id="fe8ea-102">Información general sobre el control TextBox (formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="fe8ea-102">TextBox Control Overview (Windows Forms)</span></span>
<span data-ttu-id="fe8ea-103">Windows Forms cuadros de texto se utilizan para obtener la entrada del usuario o para mostrar texto.</span><span class="sxs-lookup"><span data-stu-id="fe8ea-103">Windows Forms text boxes are used to get input from the user or to display text.</span></span> <span data-ttu-id="fe8ea-104">Normalmente, el control <xref:System.Windows.Forms.TextBox> se utiliza para texto editable, aunque también se puede convertir en de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="fe8ea-104">The <xref:System.Windows.Forms.TextBox> control is generally used for editable text, although it can also be made read-only.</span></span> <span data-ttu-id="fe8ea-105">Los cuadros de texto pueden mostrar varias líneas, ajustar el texto al tamaño del control y agregar formato básico.</span><span class="sxs-lookup"><span data-stu-id="fe8ea-105">Text boxes can display multiple lines, wrap text to the size of the control, and add basic formatting.</span></span> <span data-ttu-id="fe8ea-106">El control <xref:System.Windows.Forms.TextBox> proporciona un estilo de formato único para el texto que se muestra o se escribe en el control.</span><span class="sxs-lookup"><span data-stu-id="fe8ea-106">The <xref:System.Windows.Forms.TextBox> control provides a single format style for text displayed or entered into the control.</span></span> <span data-ttu-id="fe8ea-107">Para mostrar varios tipos de texto con formato, utilice el control <xref:System.Windows.Forms.RichTextBox>.</span><span class="sxs-lookup"><span data-stu-id="fe8ea-107">To display multiple types of formatted text, use the <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="fe8ea-108">Para obtener más información, vea [información general sobre el control RichTextBox](richtextbox-control-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="fe8ea-108">For more information, see [RichTextBox Control Overview](richtextbox-control-overview-windows-forms.md).</span></span>  
  
## <a name="working-with-the-textbox-control"></a><span data-ttu-id="fe8ea-109">Trabajar con el control TextBox</span><span class="sxs-lookup"><span data-stu-id="fe8ea-109">Working with the TextBox Control</span></span>  
 <span data-ttu-id="fe8ea-110">El texto que muestra el control está contenido en la propiedad <xref:System.Windows.Forms.TextBox.Text%2A>.</span><span class="sxs-lookup"><span data-stu-id="fe8ea-110">The text displayed by the control is contained in the <xref:System.Windows.Forms.TextBox.Text%2A> property.</span></span> <span data-ttu-id="fe8ea-111">De forma predeterminada, puede escribir hasta 2048 caracteres en un cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="fe8ea-111">By default, you can enter up to 2048 characters in a text box.</span></span> <span data-ttu-id="fe8ea-112">Si establece la propiedad <xref:System.Windows.Forms.TextBox.Multiline%2A> en `true`, puede escribir hasta 32 KB de texto.</span><span class="sxs-lookup"><span data-stu-id="fe8ea-112">If you set the <xref:System.Windows.Forms.TextBox.Multiline%2A> property to `true`, you can enter up to 32 KB of text.</span></span> <span data-ttu-id="fe8ea-113">La propiedad <xref:System.Windows.Forms.TextBox.Text%2A> se puede establecer en tiempo de diseño con la ventana Propiedades, en tiempo de ejecución en el código o mediante la entrada del usuario en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="fe8ea-113">The <xref:System.Windows.Forms.TextBox.Text%2A> property can be set at design time with the Properties Window, at run time in code, or by user input at run time.</span></span> <span data-ttu-id="fe8ea-114">El contenido actual de un cuadro de texto se puede recuperar en tiempo de ejecución mediante la lectura de la propiedad <xref:System.Windows.Forms.TextBox.Text%2A>.</span><span class="sxs-lookup"><span data-stu-id="fe8ea-114">The current contents of a text box can be retrieved at run time by reading the <xref:System.Windows.Forms.TextBox.Text%2A> property.</span></span>  
  
 <span data-ttu-id="fe8ea-115">En el ejemplo de código siguiente se establece el texto del control en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="fe8ea-115">The following code example sets text in the control at run time.</span></span> <span data-ttu-id="fe8ea-116">El procedimiento `InitializeMyControl` no se ejecutará automáticamente; se debe llamar a.</span><span class="sxs-lookup"><span data-stu-id="fe8ea-116">The `InitializeMyControl` procedure will not execute automatically; it must be called.</span></span>  
  
```vb  
Private Sub InitializeMyControl()  
   ' Put some text into the control first.  
   TextBox1.Text = "This is a TextBox control."  
End Sub  
```  
  
```csharp  
private void InitializeMyControl() {  
   // Put some text into the control first.  
   textBox1.Text = "This is a TextBox control.";  
}  
```  
  
```cpp  
private:  
   void InitializeMyControl()  
   {  
      // Put some text into the control first.  
      textBox1->Text = "This is a TextBox control.";  
   }  
```  
  
## <a name="see-also"></a><span data-ttu-id="fe8ea-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="fe8ea-117">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="fe8ea-118">Controlar el punto de inserción en un control TextBox de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fe8ea-118">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [<span data-ttu-id="fe8ea-119">Crear un cuadro de texto de contraseña con el control TextBox de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fe8ea-119">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="fe8ea-120">Crear un cuadro de texto de sólo lectura</span><span class="sxs-lookup"><span data-stu-id="fe8ea-120">How to: Create a Read-Only Text Box</span></span>](how-to-create-a-read-only-text-box-windows-forms.md)
- [<span data-ttu-id="fe8ea-121">Insertar comillas en una cadena</span><span class="sxs-lookup"><span data-stu-id="fe8ea-121">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="fe8ea-122">Seleccionar texto en el control TextBox de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fe8ea-122">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="fe8ea-123">Ver múltiples líneas en el control TextBox de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fe8ea-123">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="fe8ea-124">Control TextBox</span><span class="sxs-lookup"><span data-stu-id="fe8ea-124">TextBox Control</span></span>](textbox-control-windows-forms.md)
