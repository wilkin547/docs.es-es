---
title: Información general sobre el control TextBox (formularios Windows Forms)
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
ms.openlocfilehash: a91b67df1071c79707bb20a68efb4d5e6f083ae0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59162142"
---
# <a name="textbox-control-overview-windows-forms"></a><span data-ttu-id="4a45b-102">Información general sobre el control TextBox (formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="4a45b-102">TextBox Control Overview (Windows Forms)</span></span>
<span data-ttu-id="4a45b-103">Los cuadros de texto de Windows Forms se utilizan para obtener datos proporcionados por el usuario o para mostrar texto.</span><span class="sxs-lookup"><span data-stu-id="4a45b-103">Windows Forms text boxes are used to get input from the user or to display text.</span></span> <span data-ttu-id="4a45b-104">El <xref:System.Windows.Forms.TextBox> control se utiliza generalmente para el texto editable, aunque también se pueden hacer de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="4a45b-104">The <xref:System.Windows.Forms.TextBox> control is generally used for editable text, although it can also be made read-only.</span></span> <span data-ttu-id="4a45b-105">Los cuadros de texto pueden mostrar varias líneas, ajustar el texto para el tamaño del control y agregar formato básico.</span><span class="sxs-lookup"><span data-stu-id="4a45b-105">Text boxes can display multiple lines, wrap text to the size of the control, and add basic formatting.</span></span> <span data-ttu-id="4a45b-106">El <xref:System.Windows.Forms.TextBox> control proporciona un único estilo de formato para mostrar o escribir en el control de texto.</span><span class="sxs-lookup"><span data-stu-id="4a45b-106">The <xref:System.Windows.Forms.TextBox> control provides a single format style for text displayed or entered into the control.</span></span> <span data-ttu-id="4a45b-107">Para mostrar varios tipos de texto con formato, use el <xref:System.Windows.Forms.RichTextBox> control.</span><span class="sxs-lookup"><span data-stu-id="4a45b-107">To display multiple types of formatted text, use the <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="4a45b-108">Para obtener más información, consulte [información general del Control RichTextBox](richtextbox-control-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="4a45b-108">For more information, see [RichTextBox Control Overview](richtextbox-control-overview-windows-forms.md).</span></span>  
  
## <a name="working-with-the-textbox-control"></a><span data-ttu-id="4a45b-109">Trabajar con el Control de cuadro de texto</span><span class="sxs-lookup"><span data-stu-id="4a45b-109">Working with the TextBox Control</span></span>  
 <span data-ttu-id="4a45b-110">El texto mostrado por el control está incluido en el <xref:System.Windows.Forms.TextBox.Text%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="4a45b-110">The text displayed by the control is contained in the <xref:System.Windows.Forms.TextBox.Text%2A> property.</span></span> <span data-ttu-id="4a45b-111">De forma predeterminada, puede especificar hasta 2048 caracteres en un cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="4a45b-111">By default, you can enter up to 2048 characters in a text box.</span></span> <span data-ttu-id="4a45b-112">Si establece la <xref:System.Windows.Forms.TextBox.Multiline%2A> propiedad `true`, puede escribir hasta 32 KB de texto.</span><span class="sxs-lookup"><span data-stu-id="4a45b-112">If you set the <xref:System.Windows.Forms.TextBox.Multiline%2A> property to `true`, you can enter up to 32 KB of text.</span></span> <span data-ttu-id="4a45b-113">El <xref:System.Windows.Forms.TextBox.Text%2A> propiedad puede establecerse en tiempo de diseño con la ventana Propiedades, en tiempo de ejecución en el código o mediante la entrada del usuario en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4a45b-113">The <xref:System.Windows.Forms.TextBox.Text%2A> property can be set at design time with the Properties Window, at run time in code, or by user input at run time.</span></span> <span data-ttu-id="4a45b-114">Se puede recuperar el contenido actual de un cuadro de texto en tiempo de ejecución, lea el <xref:System.Windows.Forms.TextBox.Text%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="4a45b-114">The current contents of a text box can be retrieved at run time by reading the <xref:System.Windows.Forms.TextBox.Text%2A> property.</span></span>  
  
 <span data-ttu-id="4a45b-115">El ejemplo de código siguiente establece el texto en el control en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4a45b-115">The following code example sets text in the control at run time.</span></span> <span data-ttu-id="4a45b-116">El `InitializeMyControl` procedimiento no se ejecutará automáticamente; debe llamarse.</span><span class="sxs-lookup"><span data-stu-id="4a45b-116">The `InitializeMyControl` procedure will not execute automatically; it must be called.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4a45b-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="4a45b-117">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="4a45b-118">Filtrar para controlar el punto de inserción en un control TextBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4a45b-118">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [<span data-ttu-id="4a45b-119">Filtrar para crear un cuadro de texto de contraseña con el control TextBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4a45b-119">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="4a45b-120">Filtrar para crear un cuadro de texto de solo lectura</span><span class="sxs-lookup"><span data-stu-id="4a45b-120">How to: Create a Read-Only Text Box</span></span>](how-to-create-a-read-only-text-box-windows-forms.md)
- [<span data-ttu-id="4a45b-121">Filtrar para insertar comillas en una cadena</span><span class="sxs-lookup"><span data-stu-id="4a45b-121">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="4a45b-122">Filtrar para seleccionar texto en el control TextBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4a45b-122">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="4a45b-123">Filtrar para ver varias líneas en el control TextBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4a45b-123">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="4a45b-124">Control TextBox</span><span class="sxs-lookup"><span data-stu-id="4a45b-124">TextBox Control</span></span>](textbox-control-windows-forms.md)
