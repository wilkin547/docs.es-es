---
title: Procedimiento Proporcionar elementos de menú estándar a un formulario
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- menu items [Windows Forms], standard
- ToolStrip control [Windows Forms]
ms.assetid: 75db9126-e70c-4e81-921d-b83c0a4a9f50
ms.openlocfilehash: befff7b2eceb37b49c4d1263f46bf93775d432c5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54564021"
---
# <a name="how-to-provide-standard-menu-items-to-a-form"></a><span data-ttu-id="96546-102">Procedimiento Proporcionar elementos de menú estándar a un formulario</span><span class="sxs-lookup"><span data-stu-id="96546-102">How to: Provide Standard Menu Items to a Form</span></span>
<span data-ttu-id="96546-103">Puede proporcionar un menú estándar para los formularios con el control <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="96546-103">You can provide a standard menu for your forms with the <xref:System.Windows.Forms.MenuStrip> control.</span></span>  
  
 <span data-ttu-id="96546-104">Hay una amplia compatibilidad para esta característica en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="96546-104">There is extensive support for this feature in Visual Studio.</span></span>  
  
 <span data-ttu-id="96546-105">Consulte también [Tutorial: Proporcionar elementos de menú estándar a un formulario](walkthrough-providing-standard-menu-items-to-a-form.md).</span><span class="sxs-lookup"><span data-stu-id="96546-105">Also see [Walkthrough: Providing Standard Menu Items to a Form](walkthrough-providing-standard-menu-items-to-a-form.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="96546-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="96546-106">Example</span></span>  
 <span data-ttu-id="96546-107">En el ejemplo de código siguiente, se muestra cómo usar un control <xref:System.Windows.Forms.MenuStrip> para crear un formulario con un menú estándar.</span><span class="sxs-lookup"><span data-stu-id="96546-107">The following code example demonstrates how to use a <xref:System.Windows.Forms.MenuStrip> control to create a form with a standard menu.</span></span> <span data-ttu-id="96546-108">Las selecciones de elementos de menú se muestran en un control <xref:System.Windows.Forms.StatusStrip>.</span><span class="sxs-lookup"><span data-stu-id="96546-108">Menu item selections are displayed in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="96546-109">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="96546-109">Compiling the Code</span></span>  
 <span data-ttu-id="96546-110">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="96546-110">This example requires:</span></span>  
  
-   <span data-ttu-id="96546-111">Referencias a los ensamblados System, System.Drawing y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="96546-111">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="96546-112">Para obtener información sobre cómo compilar este ejemplo desde la línea de comandos para Visual Basic o Visual C#, vea [compilar desde la línea de comandos](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [de línea de comandos con csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="96546-112">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="96546-113">También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="96546-113">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="96546-114">Consulte también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms con Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="96546-114">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96546-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="96546-115">See also</span></span>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="96546-116">Control MenuStrip</span><span class="sxs-lookup"><span data-stu-id="96546-116">MenuStrip Control</span></span>](../../../../docs/framework/winforms/controls/menustrip-control-windows-forms.md)
