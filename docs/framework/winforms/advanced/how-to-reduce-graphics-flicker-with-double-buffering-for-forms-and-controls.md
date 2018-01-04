---
title: "Cómo: Reducir el parpadeo de los gráficos con un búfer doble en formularios y controles"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flicker [Windows Forms], reducing in Windows Forms
- graphics [Windows Forms], reducing double-buffered flicker
ms.assetid: 91083d3a-653f-4f15-a467-0f37b2aa39d6
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fc782ba262527a319cbb05cc6d36ca568afc55c0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls"></a><span data-ttu-id="06127-102">Cómo: Reducir el parpadeo de los gráficos con un búfer doble en formularios y controles</span><span class="sxs-lookup"><span data-stu-id="06127-102">How to: Reduce Graphics Flicker with Double Buffering for Forms and Controls</span></span>
<span data-ttu-id="06127-103">El almacenamiento en doble búfer usa un búfer de memoria para solucionar los problemas de parpadeo asociados a varias operaciones de pintura.</span><span class="sxs-lookup"><span data-stu-id="06127-103">Double buffering uses a memory buffer to address the flicker problems associated with multiple paint operations.</span></span> <span data-ttu-id="06127-104">Cuando se habilita el almacenamiento en doble búfer, todas las operaciones de pintura se representan primero en un búfer de memoria en lugar de la superficie de dibujo en la pantalla.</span><span class="sxs-lookup"><span data-stu-id="06127-104">When double buffering is enabled, all paint operations are first rendered to a memory buffer instead of the drawing surface on the screen.</span></span> <span data-ttu-id="06127-105">Una vez completadas todas las operaciones de pintura, el búfer de memoria se copia directamente en la superficie de dibujo asociada a él.</span><span class="sxs-lookup"><span data-stu-id="06127-105">After all paint operations are completed, the memory buffer is copied directly to the drawing surface associated with it.</span></span> <span data-ttu-id="06127-106">Dado que las operaciones de solo gráficos se realiza en la pantalla, se elimina el parpadeo de las imágenes asociadas a operaciones de dibujo complejas. Para la mayoría de las aplicaciones, el búfer doble predeterminado proporcionado por el [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] proporcionará los mejores resultados.</span><span class="sxs-lookup"><span data-stu-id="06127-106">Because only one graphics operation is performed on the screen, the image flickering associated with complex painting operations is eliminated.For most applications, the default double buffering provided by the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] will provide the best results.</span></span> <span data-ttu-id="06127-107">Controles de formularios Windows Forms estándar tienen dobles búfer de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="06127-107">Standard Windows Forms controls are double buffered by default.</span></span> <span data-ttu-id="06127-108">Puede habilitar de forma predeterminada el doble búfer en los formularios y controles creados de dos maneras.</span><span class="sxs-lookup"><span data-stu-id="06127-108">You can enable default double buffering in your forms and authored controls in two ways.</span></span> <span data-ttu-id="06127-109">Puede establecer la <xref:System.Windows.Forms.Control.DoubleBuffered%2A> propiedad `true`, o puede llamar a la <xref:System.Windows.Forms.Control.SetStyle%2A> método para establecer el <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> indicador en `true`.</span><span class="sxs-lookup"><span data-stu-id="06127-109">You can either set the <xref:System.Windows.Forms.Control.DoubleBuffered%2A> property to `true`, or you can call the <xref:System.Windows.Forms.Control.SetStyle%2A> method to set the <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> flag to `true`.</span></span> <span data-ttu-id="06127-110">Ambos métodos habilitará de forma predeterminada un búfer doble en el formulario o control y proporcionar la representación de gráficos sin parpadeo.</span><span class="sxs-lookup"><span data-stu-id="06127-110">Both methods will enable default double buffering for your form or control and provide flicker-free graphics rendering.</span></span> <span data-ttu-id="06127-111">Llamar a la <xref:System.Windows.Forms.Control.SetStyle%2A> método solo se recomienda para controles personalizados para el que ha escrito el código de representación.</span><span class="sxs-lookup"><span data-stu-id="06127-111">Calling the <xref:System.Windows.Forms.Control.SetStyle%2A> method is recommended only for custom controls for which you have written all the rendering code.</span></span>  
  
 <span data-ttu-id="06127-112">Para escenarios almacenamiento en búfer dobles y más avanzados, como animación o administración de memoria avanzados, puede implementar su propia lógica de almacenamiento en búfer doble.</span><span class="sxs-lookup"><span data-stu-id="06127-112">For more advanced double buffering scenarios, such as animation or advanced memory management, you can implement your own double buffering logic.</span></span> <span data-ttu-id="06127-113">Para obtener más información, consulte [Cómo: Manually Manage Buffered Graphics](../../../../docs/framework/winforms/advanced/how-to-manually-manage-buffered-graphics.md).</span><span class="sxs-lookup"><span data-stu-id="06127-113">For more information, see [How to: Manually Manage Buffered Graphics](../../../../docs/framework/winforms/advanced/how-to-manually-manage-buffered-graphics.md).</span></span>  
  
### <a name="to-reduce-flicker"></a><span data-ttu-id="06127-114">Para reducir el parpadeo</span><span class="sxs-lookup"><span data-stu-id="06127-114">To reduce flicker</span></span>  
  
-   <span data-ttu-id="06127-115">Establezca la propiedad <xref:System.Windows.Forms.Control.DoubleBuffered%2A> en `true`.</span><span class="sxs-lookup"><span data-stu-id="06127-115">Set the <xref:System.Windows.Forms.Control.DoubleBuffered%2A> property to `true`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#31)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#31)]  
  
 <span data-ttu-id="06127-116">\- o -</span><span class="sxs-lookup"><span data-stu-id="06127-116">\- or -</span></span>  
  
-   <span data-ttu-id="06127-117">Llame a la <xref:System.Windows.Forms.Control.SetStyle%2A> método para establecer el <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> indicador en `true`.</span><span class="sxs-lookup"><span data-stu-id="06127-117">Call the <xref:System.Windows.Forms.Control.SetStyle%2A> method to set the <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> flag to `true`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#32)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#32)]  
  
## <a name="see-also"></a><span data-ttu-id="06127-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="06127-118">See Also</span></span>  
 <xref:System.Windows.Forms.Control.DoubleBuffered%2A>  
 <xref:System.Windows.Forms.Control.SetStyle%2A>  
 [<span data-ttu-id="06127-119">Gráficos de doble búfer</span><span class="sxs-lookup"><span data-stu-id="06127-119">Double Buffered Graphics</span></span>](../../../../docs/framework/winforms/advanced/double-buffered-graphics.md)  
 [<span data-ttu-id="06127-120">Gráficos y dibujos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="06127-120">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
