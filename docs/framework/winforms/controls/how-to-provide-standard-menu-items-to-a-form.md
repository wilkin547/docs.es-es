---
title: Procedimiento para proporcionar elementos de menú estándar a un formulario
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- menu items [Windows Forms], standard
- ToolStrip control [Windows Forms]
ms.assetid: 75db9126-e70c-4e81-921d-b83c0a4a9f50
ms.openlocfilehash: bb101c57cfb453e0419357741c5cf42dc29221b9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59086720"
---
# <a name="how-to-provide-standard-menu-items-to-a-form"></a><span data-ttu-id="34ec7-102">Procedimiento para proporcionar elementos de menú estándar a un formulario</span><span class="sxs-lookup"><span data-stu-id="34ec7-102">How to: Provide Standard Menu Items to a Form</span></span>
<span data-ttu-id="34ec7-103">Puede proporcionar un menú estándar para los formularios con el control <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="34ec7-103">You can provide a standard menu for your forms with the <xref:System.Windows.Forms.MenuStrip> control.</span></span>  
  
 <span data-ttu-id="34ec7-104">Hay una amplia compatibilidad para esta característica en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="34ec7-104">There is extensive support for this feature in Visual Studio.</span></span>  
  
 <span data-ttu-id="34ec7-105">Consulte también [Tutorial: Proporcionar elementos de menú estándar a un formulario](walkthrough-providing-standard-menu-items-to-a-form.md).</span><span class="sxs-lookup"><span data-stu-id="34ec7-105">Also see [Walkthrough: Providing Standard Menu Items to a Form](walkthrough-providing-standard-menu-items-to-a-form.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="34ec7-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="34ec7-106">Example</span></span>  
 <span data-ttu-id="34ec7-107">En el ejemplo de código siguiente, se muestra cómo usar un control <xref:System.Windows.Forms.MenuStrip> para crear un formulario con un menú estándar.</span><span class="sxs-lookup"><span data-stu-id="34ec7-107">The following code example demonstrates how to use a <xref:System.Windows.Forms.MenuStrip> control to create a form with a standard menu.</span></span> <span data-ttu-id="34ec7-108">Las selecciones de elementos de menú se muestran en un control <xref:System.Windows.Forms.StatusStrip>.</span><span class="sxs-lookup"><span data-stu-id="34ec7-108">Menu item selections are displayed in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="34ec7-109">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="34ec7-109">Compiling the Code</span></span>  
 <span data-ttu-id="34ec7-110">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="34ec7-110">This example requires:</span></span>  
  
-   <span data-ttu-id="34ec7-111">Referencias a los ensamblados System, System.Drawing y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="34ec7-111">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="34ec7-112">Para obtener información sobre cómo compilar este ejemplo desde la línea de comandos para Visual Basic o Visual C#, vea [compilar desde la línea de comandos](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [de línea de comandos con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="34ec7-112">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="34ec7-113">También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="34ec7-113">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34ec7-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="34ec7-114">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="34ec7-115">Control MenuStrip</span><span class="sxs-lookup"><span data-stu-id="34ec7-115">MenuStrip Control</span></span>](menustrip-control-windows-forms.md)
