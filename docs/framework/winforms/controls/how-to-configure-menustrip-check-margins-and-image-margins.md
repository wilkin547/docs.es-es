---
title: Procedimiento para configurar los márgenes de comprobación y de imagen de MenuStrip
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- margins [Windows Forms], setting in MenuStrip controls
- menus [Windows Forms], setting margins
- MenuStrip control [Windows Forms], configuring check and image margins
ms.assetid: 45a9075d-4bea-4ce2-9b2c-7619aa39f8ce
ms.openlocfilehash: fa099012fa77daacd1f428e64abd662ee1738f84
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2019
ms.locfileid: "65586595"
---
# <a name="how-to-configure-menustrip-check-margins-and-image-margins"></a><span data-ttu-id="cc383-102">Procedimiento para configurar los márgenes de comprobación y de imagen de MenuStrip</span><span class="sxs-lookup"><span data-stu-id="cc383-102">How to: Configure MenuStrip Check Margins and Image Margins</span></span>
<span data-ttu-id="cc383-103">Puede personalizar un <xref:System.Windows.Forms.MenuStrip> estableciendo las propiedades <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowImageMargin%2A> y <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowCheckMargin%2A> en diversas combinaciones.</span><span class="sxs-lookup"><span data-stu-id="cc383-103">You can customize a <xref:System.Windows.Forms.MenuStrip> by setting the <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowImageMargin%2A> and <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowCheckMargin%2A> properties in various combinations.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cc383-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cc383-104">Example</span></span>  
 <span data-ttu-id="cc383-105">En el ejemplo de código siguiente, se muestra cómo establecer y personalizar los márgenes de comprobación y los márgenes de imagen <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="cc383-105">The following code example demonstrates how to set and customize the <xref:System.Windows.Forms.ContextMenuStrip> check margins and image margins.</span></span> <span data-ttu-id="cc383-106">El procedimiento es el mismo para <xref:System.Windows.Forms.ContextMenuStrip> o <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="cc383-106">The procedure is the same for a <xref:System.Windows.Forms.ContextMenuStrip> or a <xref:System.Windows.Forms.MenuStrip>.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#60](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#60)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#60](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#60)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="cc383-107">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="cc383-107">Compiling the Code</span></span>  
 <span data-ttu-id="cc383-108">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="cc383-108">This example requires:</span></span>  
  
- <span data-ttu-id="cc383-109">Referencias a los ensamblados System, System.Drawing y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="cc383-109">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc383-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="cc383-110">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.ToolStripDropDown>
- [<span data-ttu-id="cc383-111">Control ToolStrip</span><span class="sxs-lookup"><span data-stu-id="cc383-111">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
- [<span data-ttu-id="cc383-112">Cómo: Habilitar los márgenes de comprobación y de imagen en los controles ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="cc383-112">How to: Enable Check Margins and Image Margins in ContextMenuStrip Controls</span></span>](how-to-enable-check-margins-and-image-margins-in-contextmenustrip-controls.md)
