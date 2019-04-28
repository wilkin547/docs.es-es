---
title: Procedimiento para asociar un objeto ContextMenuStrip con un control
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- context menus [Windows Forms], relating
- ContextMenuStrips [Windows Forms], associating with controls
- context menus [Windows Forms], associating with controls
- ContextMenuStrips [Windows Forms], relating
ms.assetid: 6fc40a42-5d69-427f-aa30-0a146193226b
ms.openlocfilehash: 5fe880a44afdbd79116541809972d1456aefb9c6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62010994"
---
# <a name="how-to-associate-a-contextmenustrip-with-a-control"></a><span data-ttu-id="8874e-102">Procedimiento para asociar un objeto ContextMenuStrip con un control</span><span class="sxs-lookup"><span data-stu-id="8874e-102">How to: Associate a ContextMenuStrip with a Control</span></span>
<span data-ttu-id="8874e-103">Después de crear los controles y menús contextuales, utilice los procedimientos siguientes para mostrar un menú contextual determinado cuando el usuario hace clic con el botón secundario del mouse en el control.</span><span class="sxs-lookup"><span data-stu-id="8874e-103">After creating your controls and shortcut menus, use the following procedures to display a given shortcut menu when the user right-clicks the control.</span></span> <span data-ttu-id="8874e-104">Estos procedimientos asocian un <xref:System.Windows.Forms.ContextMenuStrip> a un Windows Forms y a un control <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="8874e-104">These procedures associate a <xref:System.Windows.Forms.ContextMenuStrip> with a Windows Form and with a <xref:System.Windows.Forms.ToolStrip> control.</span></span>  
  
### <a name="to-associate-a-contextmenustrip-with-a-windows-form"></a><span data-ttu-id="8874e-105">Para asociar un objeto ContextMenuStrip a Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8874e-105">To associate a ContextMenuStrip with a Windows Form</span></span>  
  
1. <span data-ttu-id="8874e-106">Establezca la propiedad <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> al nombre del <xref:System.Windows.Forms.ContextMenuStrip> asociado.</span><span class="sxs-lookup"><span data-stu-id="8874e-106">Set the <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> property to the name of the associated <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>  
  
### <a name="to-associate-a-contextmenustrip-with-a-toolstrip-control"></a><span data-ttu-id="8874e-107">Para asociar un objeto ContextMenuStrip a un control ToolStrip</span><span class="sxs-lookup"><span data-stu-id="8874e-107">To associate a ContextMenuStrip with a ToolStrip control</span></span>  
  
1. <span data-ttu-id="8874e-108">Establezca la propiedad <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> del control en el nombre del <xref:System.Windows.Forms.ContextMenuStrip> asociado.</span><span class="sxs-lookup"><span data-stu-id="8874e-108">Set the control's <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> property to the name of the associated <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8874e-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8874e-109">Example</span></span>  
 <span data-ttu-id="8874e-110">En el ejemplo de código siguiente, se crea un Windows Forms y un control <xref:System.Windows.Forms.ToolStrip>, y se asocia un control <xref:System.Windows.Forms.ContextMenuStrip> diferente a cada uno de ellos.</span><span class="sxs-lookup"><span data-stu-id="8874e-110">The following code example creates a Windows Form and a <xref:System.Windows.Forms.ToolStrip>, and associates a different <xref:System.Windows.Forms.ContextMenuStrip> control with each of them.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ContextMenuStrip#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ContextMenuStrip/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ContextMenuStrip#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ContextMenuStrip/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8874e-111">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="8874e-111">Compiling the Code</span></span>  
 <span data-ttu-id="8874e-112">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="8874e-112">This example requires:</span></span>  
  
- <span data-ttu-id="8874e-113">Referencias a los ensamblados System, System.Data, System.Drawing y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="8874e-113">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="8874e-114">Para obtener información sobre cómo compilar este ejemplo desde la línea de comandos para Visual Basic o Visual C#, vea [compilar desde la línea de comandos](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [de línea de comandos con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="8874e-114">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="8874e-115">También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="8874e-115">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8874e-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="8874e-116">See also</span></span>

- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.Control.ContextMenuStrip%2A>
- <xref:System.Windows.Forms.ToolStrip>
- [<span data-ttu-id="8874e-117">Cómo: Agregar elementos de menú a ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="8874e-117">How to: Add Menu Items to a ContextMenuStrip</span></span>](how-to-add-menu-items-to-a-contextmenustrip.md)
- [<span data-ttu-id="8874e-118">ContextMenuStrip (Control)</span><span class="sxs-lookup"><span data-stu-id="8874e-118">ContextMenuStrip Control</span></span>](contextmenustrip-control.md)
