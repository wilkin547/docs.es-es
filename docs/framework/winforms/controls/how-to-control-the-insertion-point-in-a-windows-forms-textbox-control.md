---
title: Procedimiento para controlar el punto de inserción en un control TextBox de formularios Windows Forms
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
ms.openlocfilehash: a9d8c02a05723814d074ff91c847471287588618
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64642972"
---
# <a name="how-to-control-the-insertion-point-in-a-windows-forms-textbox-control"></a><span data-ttu-id="7c8c4-102">Procedimiento para controlar el punto de inserción en un control TextBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7c8c4-102">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>
<span data-ttu-id="7c8c4-103">Cuando un formulario Windows Forms <xref:System.Windows.Forms.TextBox> control recibe el foco por primera vez, es el punto de inserción predeterminado del cuadro de texto a la izquierda del texto existente.</span><span class="sxs-lookup"><span data-stu-id="7c8c4-103">When a Windows Forms <xref:System.Windows.Forms.TextBox> control first receives the focus, the default insertion within the text box is to the left of any existing text.</span></span> <span data-ttu-id="7c8c4-104">El usuario puede mover el punto de inserción con el teclado o el mouse.</span><span class="sxs-lookup"><span data-stu-id="7c8c4-104">The user can move the insertion point with the keyboard or the mouse.</span></span> <span data-ttu-id="7c8c4-105">Si el cuadro de texto pierde y, a continuación, vuelva a obtener el foco, el punto de inserción será siempre que el usuario dejó.</span><span class="sxs-lookup"><span data-stu-id="7c8c4-105">If the text box loses and then regains the focus, the insertion point will be wherever the user last placed it.</span></span>  
  
 <span data-ttu-id="7c8c4-106">En algunos casos, este comportamiento puede resultar desconcertante para el usuario.</span><span class="sxs-lookup"><span data-stu-id="7c8c4-106">In some cases, this behavior can be disconcerting to the user.</span></span> <span data-ttu-id="7c8c4-107">Aplicación de procesamiento de una palabra, el usuario podría esperar que los caracteres aparecen después del texto existente.</span><span class="sxs-lookup"><span data-stu-id="7c8c4-107">In a word processing application, the user might expect new characters to appear after any existing text.</span></span> <span data-ttu-id="7c8c4-108">En una aplicación de entrada de datos, el usuario podría esperar que los caracteres para reemplazar cualquier entrada existente.</span><span class="sxs-lookup"><span data-stu-id="7c8c4-108">In a data entry application, the user might expect new characters to replace any existing entry.</span></span> <span data-ttu-id="7c8c4-109">El <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> y <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> propiedades le permiten modificar el comportamiento para adaptarlo a su propósito.</span><span class="sxs-lookup"><span data-stu-id="7c8c4-109">The <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> and <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> properties enable you to modify the behavior to suit your purpose.</span></span>  
  
### <a name="to-control-the-insertion-point-in-a-textbox-control"></a><span data-ttu-id="7c8c4-110">Para controlar el punto de inserción en un control TextBox</span><span class="sxs-lookup"><span data-stu-id="7c8c4-110">To control the insertion point in a TextBox control</span></span>  
  
1. <span data-ttu-id="7c8c4-111">Establezca la propiedad <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> en un valor apropiado.</span><span class="sxs-lookup"><span data-stu-id="7c8c4-111">Set the <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> property to an appropriate value.</span></span> <span data-ttu-id="7c8c4-112">Cero, coloca el punto de inserción inmediatamente a la izquierda del primer carácter.</span><span class="sxs-lookup"><span data-stu-id="7c8c4-112">Zero places the insertion point immediately to the left of the first character.</span></span>  
  
2. <span data-ttu-id="7c8c4-113">(Opcional) Establecer el <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> propiedad a la longitud del texto que desea seleccionar.</span><span class="sxs-lookup"><span data-stu-id="7c8c4-113">(Optional) Set the <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> property to the length of the text you want to select.</span></span>  
  
     <span data-ttu-id="7c8c4-114">El código siguiente siempre devuelve el punto de inserción a 0.</span><span class="sxs-lookup"><span data-stu-id="7c8c4-114">The code below always returns the insertion point to 0.</span></span> <span data-ttu-id="7c8c4-115">El `TextBox1_Enter` controlador de eventos debe enlazarse al control; para obtener más información, consulte [crear controladores de eventos en Windows Forms](../creating-event-handlers-in-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="7c8c4-115">The `TextBox1_Enter` event handler must be bound to the control; for more information, see [Creating Event Handlers in Windows Forms](../creating-event-handlers-in-windows-forms.md).</span></span>  
  
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
  
## <a name="making-the-insertion-point-visible-by-default"></a><span data-ttu-id="7c8c4-116">Hacer Visible de forma predeterminada el punto de inserción</span><span class="sxs-lookup"><span data-stu-id="7c8c4-116">Making the Insertion Point Visible by Default</span></span>  
 <span data-ttu-id="7c8c4-117">El <xref:System.Windows.Forms.TextBox> es visible de forma predeterminada en un solo si formulario nuevo punto de inserción del <xref:System.Windows.Forms.TextBox> control es el primero en el orden de tabulación.</span><span class="sxs-lookup"><span data-stu-id="7c8c4-117">The <xref:System.Windows.Forms.TextBox> insertion point is visible by default in a new form only if the <xref:System.Windows.Forms.TextBox> control is first in the tab order.</span></span> <span data-ttu-id="7c8c4-118">En caso contrario, el punto de inserción aparece sólo si da el <xref:System.Windows.Forms.TextBox> el foco con el teclado o el mouse.</span><span class="sxs-lookup"><span data-stu-id="7c8c4-118">Otherwise, the insertion point appears only if you give the <xref:System.Windows.Forms.TextBox> the focus with either the keyboard or the mouse.</span></span>  
  
#### <a name="to-make-the-text-box-insertion-point-visible-by-default-on-a-new-form"></a><span data-ttu-id="7c8c4-119">Para realizar la inserción del cuadro de texto punto visible de forma predeterminada en un formulario nuevo</span><span class="sxs-lookup"><span data-stu-id="7c8c4-119">To make the text box insertion point visible by default on a new form</span></span>  
  
- <span data-ttu-id="7c8c4-120">Establecer el <xref:System.Windows.Forms.TextBox> del control <xref:System.Windows.Forms.Control.TabIndex%2A> propiedad `0`.</span><span class="sxs-lookup"><span data-stu-id="7c8c4-120">Set the <xref:System.Windows.Forms.TextBox> control's <xref:System.Windows.Forms.Control.TabIndex%2A> property to `0`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c8c4-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="7c8c4-121">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="7c8c4-122">Información general sobre el control TextBox</span><span class="sxs-lookup"><span data-stu-id="7c8c4-122">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="7c8c4-123">Cómo: Crear un cuadro de texto de contraseña con el Control TextBox de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7c8c4-123">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="7c8c4-124">Cómo: Crear un cuadro de texto de solo lectura</span><span class="sxs-lookup"><span data-stu-id="7c8c4-124">How to: Create a Read-Only Text Box</span></span>](how-to-create-a-read-only-text-box-windows-forms.md)
- [<span data-ttu-id="7c8c4-125">Cómo: Insertar comillas en una cadena</span><span class="sxs-lookup"><span data-stu-id="7c8c4-125">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="7c8c4-126">Cómo: Seleccionar texto en el Control TextBox de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7c8c4-126">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="7c8c4-127">Cómo: Ver múltiples líneas en el Control TextBox de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7c8c4-127">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="7c8c4-128">Control TextBox</span><span class="sxs-lookup"><span data-stu-id="7c8c4-128">TextBox Control</span></span>](textbox-control-windows-forms.md)
