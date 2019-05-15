---
title: Procedimiento para controlar eventos de entrada del usuario en controles de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms controls, user input
- user input [Windows Forms], Windows Forms controls
ms.assetid: 3de74dcf-fae3-42d0-92b5-bc04a61a6888
ms.openlocfilehash: ae230f22c929be39ea00eafe378c6910c4a9d35f
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2019
ms.locfileid: "65592080"
---
# <a name="how-to-handle-user-input-events-in-windows-forms-controls"></a><span data-ttu-id="2168c-102">Procedimiento para controlar eventos de entrada del usuario en controles de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2168c-102">How to: Handle User Input Events in Windows Forms Controls</span></span>
<span data-ttu-id="2168c-103">En este ejemplo, se muestra cómo controlar la mayoría de los eventos de teclado, mouse, foco y validación que pueden producirse en un control de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="2168c-103">This example demonstrates how to handle most keyboard, mouse, focus, and validation events that can occur in a Windows Forms control.</span></span> <span data-ttu-id="2168c-104">El cuadro de texto denominado `TextBoxInput` recibe los eventos cuando tiene foco y la información sobre cada evento se escribe en el cuadro de texto denominado `TextBoxOutput` en el orden en que se producen los eventos.</span><span class="sxs-lookup"><span data-stu-id="2168c-104">The text box named `TextBoxInput` receives the events when it has focus, and information about each event is written in the text box named `TextBoxOutput` in the order in which the events are raised.</span></span> <span data-ttu-id="2168c-105">La aplicación también incluye un conjunto de casillas que puede utilizarse para filtrar los eventos de los que se quiere dar parte.</span><span class="sxs-lookup"><span data-stu-id="2168c-105">The application also includes a set of check boxes that can be used to filter which events to report.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2168c-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2168c-106">Example</span></span>  
 [!code-cpp[System.Windows.Forms.UserInputWalkthrough#0](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.UserInputWalkthrough/cpp/form1.cpp#0)]
 [!code-csharp[System.Windows.Forms.UserInputWalkthrough#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.UserInputWalkthrough/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.UserInputWalkthrough#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.UserInputWalkthrough/VB/form1.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2168c-107">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="2168c-107">Compiling the Code</span></span>  
 <span data-ttu-id="2168c-108">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="2168c-108">This example requires:</span></span>  
  
- <span data-ttu-id="2168c-109">Referencias a los ensamblados System, System.Drawing y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="2168c-109">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2168c-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="2168c-110">See also</span></span>

- [<span data-ttu-id="2168c-111">Datos proporcionados por el usuario en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2168c-111">User Input in Windows Forms</span></span>](user-input-in-windows-forms.md)
