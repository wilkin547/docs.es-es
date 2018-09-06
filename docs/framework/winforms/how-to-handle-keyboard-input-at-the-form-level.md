---
title: 'Cómo: Controlar los datos introducidos mediante el teclado en el formulario'
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
ms.openlocfilehash: a75c4f116b32499f9ba33dd863f2a5b6952a3e24
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2018
ms.locfileid: "43797887"
---
# <a name="how-to-handle-keyboard-input-at-the-form-level"></a><span data-ttu-id="9eabd-102">Cómo: Controlar los datos introducidos mediante el teclado en el formulario</span><span class="sxs-lookup"><span data-stu-id="9eabd-102">How to: Handle Keyboard Input at the Form Level</span></span>
<span data-ttu-id="9eabd-103">Windows Forms permite controlar los mensajes del teclado en el nivel de formulario, antes de que los mensajes lleguen a un control.</span><span class="sxs-lookup"><span data-stu-id="9eabd-103">Windows Forms provides the ability to handle keyboard messages at the form level, before the messages reach a control.</span></span> <span data-ttu-id="9eabd-104">En este tema se muestra cómo realizar esta tarea.</span><span class="sxs-lookup"><span data-stu-id="9eabd-104">This topic shows how to accomplish this task.</span></span>  
  
### <a name="to-handle-a-keyboard-message-at-the-form-level"></a><span data-ttu-id="9eabd-105">Para controlar un mensaje de teclado en el nivel de formulario</span><span class="sxs-lookup"><span data-stu-id="9eabd-105">To handle a keyboard message at the form level</span></span>  
  
-   <span data-ttu-id="9eabd-106">Controle los eventos <xref:System.Windows.Forms.Control.KeyPress> o <xref:System.Windows.Forms.Control.KeyDown> del formulario de inicio y establezca la propiedad <xref:System.Windows.Forms.Form.KeyPreview%2A> del formulario en `true` para que el formulario reciba los mensajes del teclado antes de que lleguen a los controles del formulario.</span><span class="sxs-lookup"><span data-stu-id="9eabd-106">Handle the <xref:System.Windows.Forms.Control.KeyPress> or <xref:System.Windows.Forms.Control.KeyDown> event of the startup form, and set the <xref:System.Windows.Forms.Form.KeyPreview%2A> property of the form to `true` so that keyboard messages are received by the form before they reach any controls on the form.</span></span> <span data-ttu-id="9eabd-107">Para controlar el evento <xref:System.Windows.Forms.Control.KeyPress>, el siguiente código de ejemplo detecta todas las teclas numéricas y consume las teclas '1', '4' y '7'.</span><span class="sxs-lookup"><span data-stu-id="9eabd-107">The following code example handles the <xref:System.Windows.Forms.Control.KeyPress> event by detecting all of the number keys and consuming '1', '4', and '7'.</span></span>  
  
     [!code-cpp[System.Windows.Forms.KeyboardInputForm#10](../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/cpp/form1.cpp#10)]
     [!code-csharp[System.Windows.Forms.KeyboardInputForm#10](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/CS/form1.cs#10)]
     [!code-vb[System.Windows.Forms.KeyboardInputForm#10](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/VB/form1.vb#10)]  
  
## <a name="example"></a><span data-ttu-id="9eabd-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9eabd-108">Example</span></span>  
 <span data-ttu-id="9eabd-109">El siguiente ejemplo de código es toda la aplicación del ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="9eabd-109">The following code example is the entire application for the above example.</span></span> <span data-ttu-id="9eabd-110">La aplicación incluye un <xref:System.Windows.Forms.TextBox> además de otros controles que permiten mover el foco desde el <xref:System.Windows.Forms.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="9eabd-110">The application includes a <xref:System.Windows.Forms.TextBox> along with several other controls that allow you to move focus from the <xref:System.Windows.Forms.TextBox>.</span></span> <span data-ttu-id="9eabd-111">El evento <xref:System.Windows.Forms.Control.KeyPress> del <xref:System.Windows.Forms.Form> principal consume '1', '4' y '7' y el evento <xref:System.Windows.Forms.Control.KeyPress> del <xref:System.Windows.Forms.TextBox> consume '2', '5' y '8' mientras muestra las teclas restantes.</span><span class="sxs-lookup"><span data-stu-id="9eabd-111">The <xref:System.Windows.Forms.Control.KeyPress> event of the main <xref:System.Windows.Forms.Form> consumes '1', '4', and '7', and the <xref:System.Windows.Forms.Control.KeyPress> event of the <xref:System.Windows.Forms.TextBox> consumes '2', '5', and '8' while displaying the remaining keys.</span></span> <span data-ttu-id="9eabd-112">Compare el resultado de <xref:System.Windows.Forms.MessageBox> cuando se presiona una tecla de número mientras el <xref:System.Windows.Forms.TextBox> tiene el foco con el resultado de <xref:System.Windows.Forms.MessageBox> cuando se presiona una tecla numérica mientras el foco está en otro de los controles.</span><span class="sxs-lookup"><span data-stu-id="9eabd-112">Compare the <xref:System.Windows.Forms.MessageBox> output when you press a number key while the <xref:System.Windows.Forms.TextBox> has focus with the <xref:System.Windows.Forms.MessageBox> output when you press a number key while focus is on one of the other controls.</span></span>  
  
 [!code-cpp[System.Windows.Forms.KeyBoardInputForm#0](../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/cpp/form1.cpp#0)]
 [!code-csharp[System.Windows.Forms.KeyBoardInputForm#0](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.KeyBoardInputForm#0](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/VB/form1.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9eabd-113">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="9eabd-113">Compiling the Code</span></span>  
 <span data-ttu-id="9eabd-114">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="9eabd-114">This example requires:</span></span>  
  
-   <span data-ttu-id="9eabd-115">Referencias a los ensamblados System, System.Drawing y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="9eabd-115">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="9eabd-116">Para obtener información sobre cómo compilar este ejemplo desde la línea de comandos para Visual Basic o Visual C#, vea [compilar desde la línea de comandos](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [de línea de comandos con csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="9eabd-116">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="9eabd-117">También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="9eabd-117">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="9eabd-118">Vea también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms en Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="9eabd-118">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9eabd-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="9eabd-119">See Also</span></span>  
 [<span data-ttu-id="9eabd-120">Entradas mediante teclado en una aplicación de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9eabd-120">Keyboard Input in a Windows Forms Application</span></span>](../../../docs/framework/winforms/keyboard-input-in-a-windows-forms-application.md)
