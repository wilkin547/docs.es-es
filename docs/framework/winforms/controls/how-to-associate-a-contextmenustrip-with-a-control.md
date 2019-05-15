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
ms.openlocfilehash: e1b2a49196d6da66d478a3d44eab64298cebe969
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2019
ms.locfileid: "65586609"
---
# <a name="how-to-associate-a-contextmenustrip-with-a-control"></a><span data-ttu-id="83cd5-102">Procedimiento para asociar un objeto ContextMenuStrip con un control</span><span class="sxs-lookup"><span data-stu-id="83cd5-102">How to: Associate a ContextMenuStrip with a Control</span></span>
<span data-ttu-id="83cd5-103">Después de crear los controles y menús contextuales, utilice los procedimientos siguientes para mostrar un menú contextual determinado cuando el usuario hace clic con el botón secundario del mouse en el control.</span><span class="sxs-lookup"><span data-stu-id="83cd5-103">After creating your controls and shortcut menus, use the following procedures to display a given shortcut menu when the user right-clicks the control.</span></span> <span data-ttu-id="83cd5-104">Estos procedimientos asocian un <xref:System.Windows.Forms.ContextMenuStrip> a un Windows Forms y a un control <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="83cd5-104">These procedures associate a <xref:System.Windows.Forms.ContextMenuStrip> with a Windows Form and with a <xref:System.Windows.Forms.ToolStrip> control.</span></span>  
  
### <a name="to-associate-a-contextmenustrip-with-a-windows-form"></a><span data-ttu-id="83cd5-105">Para asociar un objeto ContextMenuStrip a Windows Forms</span><span class="sxs-lookup"><span data-stu-id="83cd5-105">To associate a ContextMenuStrip with a Windows Form</span></span>  
  
1. <span data-ttu-id="83cd5-106">Establezca la propiedad <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> al nombre del <xref:System.Windows.Forms.ContextMenuStrip> asociado.</span><span class="sxs-lookup"><span data-stu-id="83cd5-106">Set the <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> property to the name of the associated <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>  
  
### <a name="to-associate-a-contextmenustrip-with-a-toolstrip-control"></a><span data-ttu-id="83cd5-107">Para asociar un objeto ContextMenuStrip a un control ToolStrip</span><span class="sxs-lookup"><span data-stu-id="83cd5-107">To associate a ContextMenuStrip with a ToolStrip control</span></span>  
  
1. <span data-ttu-id="83cd5-108">Establezca la propiedad <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> del control en el nombre del <xref:System.Windows.Forms.ContextMenuStrip> asociado.</span><span class="sxs-lookup"><span data-stu-id="83cd5-108">Set the control's <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> property to the name of the associated <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="83cd5-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="83cd5-109">Example</span></span>  
 <span data-ttu-id="83cd5-110">En el ejemplo de código siguiente, se crea un Windows Forms y un control <xref:System.Windows.Forms.ToolStrip>, y se asocia un control <xref:System.Windows.Forms.ContextMenuStrip> diferente a cada uno de ellos.</span><span class="sxs-lookup"><span data-stu-id="83cd5-110">The following code example creates a Windows Form and a <xref:System.Windows.Forms.ToolStrip>, and associates a different <xref:System.Windows.Forms.ContextMenuStrip> control with each of them.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ContextMenuStrip#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ContextMenuStrip/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ContextMenuStrip#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ContextMenuStrip/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="83cd5-111">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="83cd5-111">Compiling the Code</span></span>  
 <span data-ttu-id="83cd5-112">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="83cd5-112">This example requires:</span></span>  
  
- <span data-ttu-id="83cd5-113">Referencias a los ensamblados System, System.Data, System.Drawing y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="83cd5-113">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83cd5-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="83cd5-114">See also</span></span>

- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.Control.ContextMenuStrip%2A>
- <xref:System.Windows.Forms.ToolStrip>
- [<span data-ttu-id="83cd5-115">Cómo: Agregar elementos de menú a ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="83cd5-115">How to: Add Menu Items to a ContextMenuStrip</span></span>](how-to-add-menu-items-to-a-contextmenustrip.md)
- [<span data-ttu-id="83cd5-116">ContextMenuStrip (Control)</span><span class="sxs-lookup"><span data-stu-id="83cd5-116">ContextMenuStrip Control</span></span>](contextmenustrip-control.md)
