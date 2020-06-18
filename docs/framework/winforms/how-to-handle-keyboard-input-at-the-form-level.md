---
title: Procedimiento para controlar la entrada de teclado en el formulario
description: Obtenga información sobre cómo controlar la entrada del teclado para su Windows Forms en el nivel de formulario, antes de que los mensajes lleguen a un control.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- keyboard input [Windows Forms], at form level
- Windows Forms, handling keyboard input
- keyboards [Windows Forms], form-level input
ms.assetid: d7f8b390-dc91-42d2-ae0f-2ffa388127ad
ms.openlocfilehash: 6f0695b6f665a613e0e4e001a4f9bbfc09dd45ed
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904161"
---
# <a name="how-to-handle-keyboard-input-at-the-form-level"></a><span data-ttu-id="92bba-103">Procedimiento para controlar la entrada de teclado en el formulario</span><span class="sxs-lookup"><span data-stu-id="92bba-103">How to: Handle Keyboard Input at the Form Level</span></span>
<span data-ttu-id="92bba-104">Windows Forms permite controlar los mensajes del teclado en el nivel de formulario, antes de que los mensajes lleguen a un control.</span><span class="sxs-lookup"><span data-stu-id="92bba-104">Windows Forms provides the ability to handle keyboard messages at the form level, before the messages reach a control.</span></span> <span data-ttu-id="92bba-105">En este tema se muestra cómo realizar esta tarea.</span><span class="sxs-lookup"><span data-stu-id="92bba-105">This topic shows how to accomplish this task.</span></span>  
  
### <a name="to-handle-a-keyboard-message-at-the-form-level"></a><span data-ttu-id="92bba-106">Para controlar un mensaje de teclado en el nivel de formulario</span><span class="sxs-lookup"><span data-stu-id="92bba-106">To handle a keyboard message at the form level</span></span>  
  
- <span data-ttu-id="92bba-107">Controle los eventos <xref:System.Windows.Forms.Control.KeyPress> o <xref:System.Windows.Forms.Control.KeyDown> del formulario de inicio y establezca la propiedad <xref:System.Windows.Forms.Form.KeyPreview%2A> del formulario en `true` para que el formulario reciba los mensajes del teclado antes de que lleguen a los controles del formulario.</span><span class="sxs-lookup"><span data-stu-id="92bba-107">Handle the <xref:System.Windows.Forms.Control.KeyPress> or <xref:System.Windows.Forms.Control.KeyDown> event of the startup form, and set the <xref:System.Windows.Forms.Form.KeyPreview%2A> property of the form to `true` so that keyboard messages are received by the form before they reach any controls on the form.</span></span> <span data-ttu-id="92bba-108">Para controlar el evento <xref:System.Windows.Forms.Control.KeyPress>, el siguiente código de ejemplo detecta todas las teclas numéricas y consume las teclas '1', '4' y '7'.</span><span class="sxs-lookup"><span data-stu-id="92bba-108">The following code example handles the <xref:System.Windows.Forms.Control.KeyPress> event by detecting all of the number keys and consuming '1', '4', and '7'.</span></span>  
  
     [!code-cpp[System.Windows.Forms.KeyboardInputForm#10](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/cpp/form1.cpp#10)]
     [!code-csharp[System.Windows.Forms.KeyboardInputForm#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/CS/form1.cs#10)]
     [!code-vb[System.Windows.Forms.KeyboardInputForm#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/VB/form1.vb#10)]  
  
## <a name="example"></a><span data-ttu-id="92bba-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="92bba-109">Example</span></span>  
 <span data-ttu-id="92bba-110">El siguiente ejemplo de código es toda la aplicación del ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="92bba-110">The following code example is the entire application for the above example.</span></span> <span data-ttu-id="92bba-111">La aplicación incluye un <xref:System.Windows.Forms.TextBox> además de otros controles que permiten mover el foco desde el <xref:System.Windows.Forms.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="92bba-111">The application includes a <xref:System.Windows.Forms.TextBox> along with several other controls that allow you to move focus from the <xref:System.Windows.Forms.TextBox>.</span></span> <span data-ttu-id="92bba-112">El evento <xref:System.Windows.Forms.Control.KeyPress> del <xref:System.Windows.Forms.Form> principal consume '1', '4' y '7' y el evento <xref:System.Windows.Forms.Control.KeyPress> del <xref:System.Windows.Forms.TextBox> consume '2', '5' y '8' mientras muestra las teclas restantes.</span><span class="sxs-lookup"><span data-stu-id="92bba-112">The <xref:System.Windows.Forms.Control.KeyPress> event of the main <xref:System.Windows.Forms.Form> consumes '1', '4', and '7', and the <xref:System.Windows.Forms.Control.KeyPress> event of the <xref:System.Windows.Forms.TextBox> consumes '2', '5', and '8' while displaying the remaining keys.</span></span> <span data-ttu-id="92bba-113">Compare el resultado de <xref:System.Windows.Forms.MessageBox> cuando se presiona una tecla de número mientras el <xref:System.Windows.Forms.TextBox> tiene el foco con el resultado de <xref:System.Windows.Forms.MessageBox> cuando se presiona una tecla numérica mientras el foco está en otro de los controles.</span><span class="sxs-lookup"><span data-stu-id="92bba-113">Compare the <xref:System.Windows.Forms.MessageBox> output when you press a number key while the <xref:System.Windows.Forms.TextBox> has focus with the <xref:System.Windows.Forms.MessageBox> output when you press a number key while focus is on one of the other controls.</span></span>  
  
 [!code-cpp[System.Windows.Forms.KeyBoardInputForm#0](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/cpp/form1.cpp#0)]
 [!code-csharp[System.Windows.Forms.KeyBoardInputForm#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.KeyBoardInputForm#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/VB/form1.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="92bba-114">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="92bba-114">Compiling the Code</span></span>  
 <span data-ttu-id="92bba-115">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="92bba-115">This example requires:</span></span>  
  
- <span data-ttu-id="92bba-116">Referencias a los ensamblados System, System.Drawing y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="92bba-116">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92bba-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="92bba-117">See also</span></span>

- [<span data-ttu-id="92bba-118">Entradas mediante teclado en una aplicación de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="92bba-118">Keyboard Input in a Windows Forms Application</span></span>](keyboard-input-in-a-windows-forms-application.md)
