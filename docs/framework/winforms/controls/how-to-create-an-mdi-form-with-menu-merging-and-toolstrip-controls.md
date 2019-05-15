---
title: Procedimiento para crear un formulario MDI con combinación de menús y controles ToolStrip
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStripPanel control [Windows Forms]
- ToolStrip control [Windows Forms]
- MenuStrip control [Windows Forms]
ms.assetid: 64992ed9-44af-4baf-b45f-863e6ab35711
ms.openlocfilehash: 0edcc27968c55908cda0e881ed66f83323316711
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2019
ms.locfileid: "65591304"
---
# <a name="how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls"></a><span data-ttu-id="38ac1-102">Procedimiento para crear un formulario MDI con combinación de menús y controles ToolStrip</span><span class="sxs-lookup"><span data-stu-id="38ac1-102">How to: Create an MDI Form with Menu Merging and ToolStrip Controls</span></span>
<span data-ttu-id="38ac1-103">El espacio de nombres <xref:System.Windows.Forms?displayProperty=nameWithType> es compatible con aplicaciones de interfaces de múltiples documentos (MDI) y el control <xref:System.Windows.Forms.MenuStrip> admite la combinación de menús.</span><span class="sxs-lookup"><span data-stu-id="38ac1-103">The <xref:System.Windows.Forms?displayProperty=nameWithType> namespace supports multiple document interface (MDI) applications, and the <xref:System.Windows.Forms.MenuStrip> control supports menu merging.</span></span> <span data-ttu-id="38ac1-104">Los formularios MDI también pueden ser compatibles con los controles <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="38ac1-104">MDI forms can also <xref:System.Windows.Forms.ToolStrip> controls.</span></span>  
  
 <span data-ttu-id="38ac1-105">Hay una amplia compatibilidad para esta característica en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="38ac1-105">There is extensive support for this feature in Visual Studio.</span></span>  
  
 <span data-ttu-id="38ac1-106">Consulte también [Tutorial: Crear un formulario MDI con combinación de menús y controles ToolStrip](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span><span class="sxs-lookup"><span data-stu-id="38ac1-106">Also see [Walkthrough: Creating an MDI Form with Menu Merging and ToolStrip Controls](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="38ac1-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="38ac1-107">Example</span></span>  
 <span data-ttu-id="38ac1-108">En el siguiente ejemplo de código, se muestra cómo utilizar los controles <xref:System.Windows.Forms.ToolStripPanel> con un formulario MDI.</span><span class="sxs-lookup"><span data-stu-id="38ac1-108">The following code example demonstrates how to use <xref:System.Windows.Forms.ToolStripPanel> controls with an MDI form.</span></span> <span data-ttu-id="38ac1-109">El formulario también admite la combinación de menús con menús secundarios.</span><span class="sxs-lookup"><span data-stu-id="38ac1-109">The form also supports menu merging with child menus.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.MdiForm#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.MdiForm#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="38ac1-110">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="38ac1-110">Compiling the Code</span></span>  
 <span data-ttu-id="38ac1-111">Para este ejemplo de código se necesita:</span><span class="sxs-lookup"><span data-stu-id="38ac1-111">This code example requires:</span></span>  
  
- <span data-ttu-id="38ac1-112">Referencias a los ensamblados System.Drawing y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="38ac1-112">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38ac1-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="38ac1-113">See also</span></span>

- [<span data-ttu-id="38ac1-114">Control ToolStrip</span><span class="sxs-lookup"><span data-stu-id="38ac1-114">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
