---
title: Procedimiento para establecer el representador de ToolStrip para una aplicación
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Renderer property [Windows Forms]
- ToolStripProfessionalRenderer class [Windows Forms]
- ToolStrip control [Windows Forms]
- MenuStrip control [Windows Forms]
- toolbars [Windows Forms], customizing
ms.assetid: 46acef3e-9844-4ae8-9a2e-3006fe99cadf
ms.openlocfilehash: c9250b723e68ac97d1486a896392bf64c66cdfbc
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2019
ms.locfileid: "65591592"
---
# <a name="how-to-set-the-toolstrip-renderer-for-an-application"></a><span data-ttu-id="29ff2-102">Procedimiento para establecer el representador de ToolStrip para una aplicación</span><span class="sxs-lookup"><span data-stu-id="29ff2-102">How to: Set the ToolStrip Renderer for an Application</span></span>
<span data-ttu-id="29ff2-103">Puede personalizar la apariencia de sus controles <xref:System.Windows.Forms.ToolStrip> de forma individual o para todos los controles <xref:System.Windows.Forms.ToolStrip> de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="29ff2-103">You can customize the appearance of your <xref:System.Windows.Forms.ToolStrip> controls individually or for all the <xref:System.Windows.Forms.ToolStrip> controls in your application.</span></span>  
  
## <a name="example"></a><span data-ttu-id="29ff2-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="29ff2-104">Example</span></span>  
 <span data-ttu-id="29ff2-105">En el ejemplo de código siguiente, se muestra cómo aplicar de forma selectiva un representador personalizado a un control <xref:System.Windows.Forms.ToolStrip> y un control <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="29ff2-105">The following code example demonstrates how to selectively apply a custom renderer to a <xref:System.Windows.Forms.ToolStrip> control and a <xref:System.Windows.Forms.MenuStrip> control.</span></span>  
  
 <span data-ttu-id="29ff2-106">Para utilizar este ejemplo de código, compile y ejecute la aplicación y, a continuación, seleccione el ámbito de la representación personalizada desde el <xref:System.Windows.Forms.ComboBox> control.</span><span class="sxs-lookup"><span data-stu-id="29ff2-106">To use this code example, compile and run the application, and then select the scope of the custom rending from the <xref:System.Windows.Forms.ComboBox> control.</span></span> <span data-ttu-id="29ff2-107">Haga clic en **Aplicar** para establecer el representador.</span><span class="sxs-lookup"><span data-stu-id="29ff2-107">Click **Apply** to set the renderer.</span></span>  
  
 <span data-ttu-id="29ff2-108">Para ver la representación del elemento de menú personalizado, seleccione el <xref:System.Windows.Forms.MenuStrip> opción desde el <xref:System.Windows.Forms.ComboBox> de control, haga clic en **aplicar**y, a continuación, abra el **archivo** elemento de menú.</span><span class="sxs-lookup"><span data-stu-id="29ff2-108">To see custom menu item rendering, select the <xref:System.Windows.Forms.MenuStrip> option from the <xref:System.Windows.Forms.ComboBox> control, click **Apply**, and then open the **File** menu item.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#70](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#70)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#70](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#70)]  
  
 <span data-ttu-id="29ff2-109">Establezca la propiedad <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> para aplicar un representador personalizado a todos los controles <xref:System.Windows.Forms.ToolStrip> de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="29ff2-109">Set the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> property to apply a custom renderer to all the <xref:System.Windows.Forms.ToolStrip> controls in your application.</span></span>  
  
 <span data-ttu-id="29ff2-110">Establezca la propiedad <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> para aplicar un representador personalizado a un control <xref:System.Windows.Forms.ToolStrip> individual.</span><span class="sxs-lookup"><span data-stu-id="29ff2-110">Set the <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> property to apply a custom renderer to an individual <xref:System.Windows.Forms.ToolStrip> control.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="29ff2-111">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="29ff2-111">Compiling the Code</span></span>  
 <span data-ttu-id="29ff2-112">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="29ff2-112">This example requires:</span></span>  
  
- <span data-ttu-id="29ff2-113">Referencias a los ensamblados System.Design, System.Drawing y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="29ff2-113">References to the System.Design, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29ff2-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="29ff2-114">See also</span></span>

- <xref:System.Windows.Forms.ToolStripManager>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripProfessionalRenderer>
- [<span data-ttu-id="29ff2-115">Control ToolStrip</span><span class="sxs-lookup"><span data-stu-id="29ff2-115">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
