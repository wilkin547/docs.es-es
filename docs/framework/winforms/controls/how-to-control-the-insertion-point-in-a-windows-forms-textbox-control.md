---
title: Controlar el punto de inserción en el control de cuadro de texto
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TextBox control [Windows Forms], insertion point
- insertion points [Windows Forms], TextBox controls
- text boxes [Windows Forms], controlling insertion point
ms.assetid: 5bee7d34-5121-429e-ab1f-d8ff67bc74c1
ms.openlocfilehash: fd4803820921f0c922a4ce885f809abee8fd4c6c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742205"
---
# <a name="how-to-control-the-insertion-point-in-a-windows-forms-textbox-control"></a><span data-ttu-id="e17b0-102">Cómo: Controlar el punto de inserción en un control TextBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e17b0-102">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>
<span data-ttu-id="e17b0-103">Cuando un Windows Forms control de <xref:System.Windows.Forms.TextBox> recibe el foco por primera vez, la inserción predeterminada en el cuadro de texto se encuentra a la izquierda de cualquier texto existente.</span><span class="sxs-lookup"><span data-stu-id="e17b0-103">When a Windows Forms <xref:System.Windows.Forms.TextBox> control first receives the focus, the default insertion within the text box is to the left of any existing text.</span></span> <span data-ttu-id="e17b0-104">El usuario puede desplace el punto de inserción con el teclado o el mouse.</span><span class="sxs-lookup"><span data-stu-id="e17b0-104">The user can move the insertion point with the keyboard or the mouse.</span></span> <span data-ttu-id="e17b0-105">Si el cuadro de texto pierde y vuelve a obtener el foco, el punto de inserción será donde el usuario lo haya colocado por última vez.</span><span class="sxs-lookup"><span data-stu-id="e17b0-105">If the text box loses and then regains the focus, the insertion point will be wherever the user last placed it.</span></span>  
  
 <span data-ttu-id="e17b0-106">En algunos casos, este comportamiento puede ser desconcertado para el usuario.</span><span class="sxs-lookup"><span data-stu-id="e17b0-106">In some cases, this behavior can be disconcerting to the user.</span></span> <span data-ttu-id="e17b0-107">En una aplicación de procesamiento de texto, el usuario podría esperar que aparezcan nuevos caracteres después de cualquier texto existente.</span><span class="sxs-lookup"><span data-stu-id="e17b0-107">In a word processing application, the user might expect new characters to appear after any existing text.</span></span> <span data-ttu-id="e17b0-108">En una aplicación de entrada de datos, el usuario podría esperar que los nuevos caracteres reemplazaran cualquier entrada existente.</span><span class="sxs-lookup"><span data-stu-id="e17b0-108">In a data entry application, the user might expect new characters to replace any existing entry.</span></span> <span data-ttu-id="e17b0-109">Las propiedades <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> y <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> permiten modificar el comportamiento para adaptarlo a su propósito.</span><span class="sxs-lookup"><span data-stu-id="e17b0-109">The <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> and <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> properties enable you to modify the behavior to suit your purpose.</span></span>  
  
### <a name="to-control-the-insertion-point-in-a-textbox-control"></a><span data-ttu-id="e17b0-110">Para controlar el punto de inserción en un control TextBox</span><span class="sxs-lookup"><span data-stu-id="e17b0-110">To control the insertion point in a TextBox control</span></span>  
  
1. <span data-ttu-id="e17b0-111">Establezca la propiedad <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> en un valor apropiado.</span><span class="sxs-lookup"><span data-stu-id="e17b0-111">Set the <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> property to an appropriate value.</span></span> <span data-ttu-id="e17b0-112">Cero coloca el punto de inserción inmediatamente a la izquierda del primer carácter.</span><span class="sxs-lookup"><span data-stu-id="e17b0-112">Zero places the insertion point immediately to the left of the first character.</span></span>  
  
2. <span data-ttu-id="e17b0-113">Opta Establezca la propiedad <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> en la longitud del texto que desea seleccionar.</span><span class="sxs-lookup"><span data-stu-id="e17b0-113">(Optional) Set the <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> property to the length of the text you want to select.</span></span>  
  
     <span data-ttu-id="e17b0-114">El código siguiente siempre devuelve el punto de inserción a 0.</span><span class="sxs-lookup"><span data-stu-id="e17b0-114">The code below always returns the insertion point to 0.</span></span> <span data-ttu-id="e17b0-115">El controlador de eventos `TextBox1_Enter` debe estar enlazado al control; para obtener más información, vea [crear controladores de eventos en Windows Forms](../creating-event-handlers-in-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="e17b0-115">The `TextBox1_Enter` event handler must be bound to the control; for more information, see [Creating Event Handlers in Windows Forms](../creating-event-handlers-in-windows-forms.md).</span></span>  
  
    ```vb  
    Private Sub TextBox1_Enter(ByVal sender As Object, ByVal e As System.EventArgs) Handles TextBox1.Enter  
       TextBox1.SelectionStart = 0  
       TextBox1.SelectionLength = 0  
    End Sub  
    ```  
  
    ```csharp  
    private void textBox1_Enter(Object sender, System.EventArgs e) {  
       textBox1.SelectionStart = 0;  
       textBox1.SelectionLength = 0;  
    }  
    ```  
  
    ```cpp  
    private:  
       void textBox1_Enter(System::Object ^  sender,  
          System::EventArgs ^  e)  
       {  
          textBox1->SelectionStart = 0;  
          textBox1->SelectionLength = 0;  
       }  
    ```  
  
## <a name="making-the-insertion-point-visible-by-default"></a><span data-ttu-id="e17b0-116">Cómo es visible de forma predeterminada el punto de inserción</span><span class="sxs-lookup"><span data-stu-id="e17b0-116">Making the Insertion Point Visible by Default</span></span>  
 <span data-ttu-id="e17b0-117">El punto de inserción <xref:System.Windows.Forms.TextBox> es visible de forma predeterminada en un formulario nuevo solo si el control <xref:System.Windows.Forms.TextBox> es el primero en el orden de tabulación.</span><span class="sxs-lookup"><span data-stu-id="e17b0-117">The <xref:System.Windows.Forms.TextBox> insertion point is visible by default in a new form only if the <xref:System.Windows.Forms.TextBox> control is first in the tab order.</span></span> <span data-ttu-id="e17b0-118">De lo contrario, el punto de inserción solo aparece si se asigna al <xref:System.Windows.Forms.TextBox> el foco con el teclado o con el mouse.</span><span class="sxs-lookup"><span data-stu-id="e17b0-118">Otherwise, the insertion point appears only if you give the <xref:System.Windows.Forms.TextBox> the focus with either the keyboard or the mouse.</span></span>  
  
#### <a name="to-make-the-text-box-insertion-point-visible-by-default-on-a-new-form"></a><span data-ttu-id="e17b0-119">Para que el punto de inserción del cuadro de texto esté visible de forma predeterminada en un nuevo formulario</span><span class="sxs-lookup"><span data-stu-id="e17b0-119">To make the text box insertion point visible by default on a new form</span></span>  
  
- <span data-ttu-id="e17b0-120">Establezca la propiedad <xref:System.Windows.Forms.Control.TabIndex%2A> del control <xref:System.Windows.Forms.TextBox> en `0`.</span><span class="sxs-lookup"><span data-stu-id="e17b0-120">Set the <xref:System.Windows.Forms.TextBox> control's <xref:System.Windows.Forms.Control.TabIndex%2A> property to `0`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e17b0-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e17b0-121">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="e17b0-122">Información general sobre el control TextBox</span><span class="sxs-lookup"><span data-stu-id="e17b0-122">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="e17b0-123">Crear un cuadro de texto de contraseña con el control TextBox de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e17b0-123">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="e17b0-124">Crear un cuadro de texto de sólo lectura</span><span class="sxs-lookup"><span data-stu-id="e17b0-124">How to: Create a Read-Only Text Box</span></span>](how-to-create-a-read-only-text-box-windows-forms.md)
- [<span data-ttu-id="e17b0-125">Insertar comillas en una cadena</span><span class="sxs-lookup"><span data-stu-id="e17b0-125">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="e17b0-126">Seleccionar texto en el control TextBox de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e17b0-126">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="e17b0-127">Ver múltiples líneas en el control TextBox de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e17b0-127">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="e17b0-128">TextBox (control)</span><span class="sxs-lookup"><span data-stu-id="e17b0-128">TextBox Control</span></span>](textbox-control-windows-forms.md)
