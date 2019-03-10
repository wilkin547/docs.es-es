---
title: Filtrar Controlar eventos de entrada de usuario en controles de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms controls, user input
- user input [Windows Forms], Windows Forms controls
ms.assetid: 3de74dcf-fae3-42d0-92b5-bc04a61a6888
ms.openlocfilehash: 886558eb33ffbbec65917f15f4da16673518dce9
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57723964"
---
# <a name="how-to-handle-user-input-events-in-windows-forms-controls"></a><span data-ttu-id="b1527-102">Filtrar Controlar eventos de entrada de usuario en controles de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b1527-102">How to: Handle User Input Events in Windows Forms Controls</span></span>
<span data-ttu-id="b1527-103">En este ejemplo, se muestra cómo controlar la mayoría de los eventos de teclado, mouse, foco y validación que pueden producirse en un control de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="b1527-103">This example demonstrates how to handle most keyboard, mouse, focus, and validation events that can occur in a Windows Forms control.</span></span> <span data-ttu-id="b1527-104">El cuadro de texto denominado `TextBoxInput` recibe los eventos cuando tiene foco y la información sobre cada evento se escribe en el cuadro de texto denominado `TextBoxOutput` en el orden en que se producen los eventos.</span><span class="sxs-lookup"><span data-stu-id="b1527-104">The text box named `TextBoxInput` receives the events when it has focus, and information about each event is written in the text box named `TextBoxOutput` in the order in which the events are raised.</span></span> <span data-ttu-id="b1527-105">La aplicación también incluye un conjunto de casillas que puede utilizarse para filtrar los eventos de los que se quiere dar parte.</span><span class="sxs-lookup"><span data-stu-id="b1527-105">The application also includes a set of check boxes that can be used to filter which events to report.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b1527-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b1527-106">Example</span></span>  
 [!code-cpp[System.Windows.Forms.UserInputWalkthrough#0](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.UserInputWalkthrough/cpp/form1.cpp#0)]
 [!code-csharp[System.Windows.Forms.UserInputWalkthrough#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.UserInputWalkthrough/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.UserInputWalkthrough#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.UserInputWalkthrough/VB/form1.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b1527-107">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="b1527-107">Compiling the Code</span></span>  
 <span data-ttu-id="b1527-108">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="b1527-108">This example requires:</span></span>  
  
-   <span data-ttu-id="b1527-109">Referencias a los ensamblados System, System.Drawing y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="b1527-109">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="b1527-110">Para obtener información sobre cómo compilar este ejemplo desde la línea de comandos para Visual Basic o Visual C#, vea [compilar desde la línea de comandos](../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [de línea de comandos con csc.exe](../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="b1527-110">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="b1527-111">También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="b1527-111">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1527-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="b1527-112">See also</span></span>
- [<span data-ttu-id="b1527-113">Datos proporcionados por el usuario en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b1527-113">User Input in Windows Forms</span></span>](user-input-in-windows-forms.md)
