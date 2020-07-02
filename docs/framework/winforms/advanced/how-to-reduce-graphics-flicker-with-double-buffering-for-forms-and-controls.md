---
title: Procedimiento para reducir el parpadeo de los gráficos con un búfer doble en formularios y controles
description: Obtenga información acerca de cómo reducir el parpadeo de los gráficos con el almacenamiento en búfer doble para Windows Forms y usar controles para solucionar los problemas de parpadeo asociados a las operaciones de pintura.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flicker [Windows Forms], reducing in Windows Forms
- graphics [Windows Forms], reducing double-buffered flicker
ms.assetid: 91083d3a-653f-4f15-a467-0f37b2aa39d6
ms.openlocfilehash: f7c0425729f8a1a780124621788a1c49e06e0c4e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618134"
---
# <a name="how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls"></a><span data-ttu-id="90a86-103">Procedimiento para reducir el parpadeo de los gráficos con un búfer doble en formularios y controles</span><span class="sxs-lookup"><span data-stu-id="90a86-103">How to: Reduce Graphics Flicker with Double Buffering for Forms and Controls</span></span>
<span data-ttu-id="90a86-104">El almacenamiento en doble búfer usa un búfer de memoria para solucionar los problemas de parpadeo asociados a varias operaciones de pintura.</span><span class="sxs-lookup"><span data-stu-id="90a86-104">Double buffering uses a memory buffer to address the flicker problems associated with multiple paint operations.</span></span> <span data-ttu-id="90a86-105">Cuando se habilita el almacenamiento en doble búfer, todas las operaciones de pintura se representan primero en un búfer de memoria en lugar de la superficie de dibujo en la pantalla.</span><span class="sxs-lookup"><span data-stu-id="90a86-105">When double buffering is enabled, all paint operations are first rendered to a memory buffer instead of the drawing surface on the screen.</span></span> <span data-ttu-id="90a86-106">Una vez completadas todas las operaciones de pintura, el búfer de memoria se copia directamente en la superficie de dibujo asociada a él.</span><span class="sxs-lookup"><span data-stu-id="90a86-106">After all paint operations are completed, the memory buffer is copied directly to the drawing surface associated with it.</span></span> <span data-ttu-id="90a86-107">Dado que solo se realiza una operación de gráficos en la pantalla, se elimina el parpadeo de la imagen asociado a las operaciones de pintura complejas. Para la mayoría de las aplicaciones, el doble búfer predeterminado proporcionado por el .NET Framework proporcionará los mejores resultados.</span><span class="sxs-lookup"><span data-stu-id="90a86-107">Because only one graphics operation is performed on the screen, the image flickering associated with complex painting operations is eliminated.For most applications, the default double buffering provided by the .NET Framework will provide the best results.</span></span> <span data-ttu-id="90a86-108">Los controles de Windows Forms estándar se almacenan en búfer doble de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="90a86-108">Standard Windows Forms controls are double buffered by default.</span></span> <span data-ttu-id="90a86-109">Puede habilitar el doble búfer predeterminado en los formularios y los controles creados de dos maneras.</span><span class="sxs-lookup"><span data-stu-id="90a86-109">You can enable default double buffering in your forms and authored controls in two ways.</span></span> <span data-ttu-id="90a86-110">Puede establecer la <xref:System.Windows.Forms.Control.DoubleBuffered%2A> propiedad en o puede `true` llamar al <xref:System.Windows.Forms.Control.SetStyle%2A> método para establecer la <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> marca en `true` .</span><span class="sxs-lookup"><span data-stu-id="90a86-110">You can either set the <xref:System.Windows.Forms.Control.DoubleBuffered%2A> property to `true`, or you can call the <xref:System.Windows.Forms.Control.SetStyle%2A> method to set the <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> flag to `true`.</span></span> <span data-ttu-id="90a86-111">Ambos métodos habilitarán el doble búfer predeterminado para su formulario o control y proporcionarán una representación de gráficos sin parpadeos.</span><span class="sxs-lookup"><span data-stu-id="90a86-111">Both methods will enable default double buffering for your form or control and provide flicker-free graphics rendering.</span></span> <span data-ttu-id="90a86-112"><xref:System.Windows.Forms.Control.SetStyle%2A>Solo se recomienda llamar al método para los controles personalizados para los que se ha escrito todo el código de representación.</span><span class="sxs-lookup"><span data-stu-id="90a86-112">Calling the <xref:System.Windows.Forms.Control.SetStyle%2A> method is recommended only for custom controls for which you have written all the rendering code.</span></span>  
  
 <span data-ttu-id="90a86-113">Para escenarios de doble búfer más avanzados, como la animación o la administración avanzada de memoria, puede implementar su propia lógica de almacenamiento en búfer doble.</span><span class="sxs-lookup"><span data-stu-id="90a86-113">For more advanced double buffering scenarios, such as animation or advanced memory management, you can implement your own double buffering logic.</span></span> <span data-ttu-id="90a86-114">Para obtener más información, vea [Cómo: administrar manualmente gráficos almacenados en búfer](how-to-manually-manage-buffered-graphics.md).</span><span class="sxs-lookup"><span data-stu-id="90a86-114">For more information, see [How to: Manually Manage Buffered Graphics](how-to-manually-manage-buffered-graphics.md).</span></span>  
  
### <a name="to-reduce-flicker"></a><span data-ttu-id="90a86-115">Para reducir el parpadeo</span><span class="sxs-lookup"><span data-stu-id="90a86-115">To reduce flicker</span></span>  
  
- <span data-ttu-id="90a86-116">Establezca la propiedad <xref:System.Windows.Forms.Control.DoubleBuffered%2A> en `true`.</span><span class="sxs-lookup"><span data-stu-id="90a86-116">Set the <xref:System.Windows.Forms.Control.DoubleBuffered%2A> property to `true`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#31)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#31)]  
  
 <span data-ttu-id="90a86-117">\- o -</span><span class="sxs-lookup"><span data-stu-id="90a86-117">\- or -</span></span>  
  
- <span data-ttu-id="90a86-118">Llame al <xref:System.Windows.Forms.Control.SetStyle%2A> método para establecer la <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> marca en `true` .</span><span class="sxs-lookup"><span data-stu-id="90a86-118">Call the <xref:System.Windows.Forms.Control.SetStyle%2A> method to set the <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> flag to `true`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#32](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#32)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#32](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#32)]  
  
## <a name="see-also"></a><span data-ttu-id="90a86-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="90a86-119">See also</span></span>

- <xref:System.Windows.Forms.Control.DoubleBuffered%2A>
- <xref:System.Windows.Forms.Control.SetStyle%2A>
- [<span data-ttu-id="90a86-120">Gráficos de doble búfer</span><span class="sxs-lookup"><span data-stu-id="90a86-120">Double Buffered Graphics</span></span>](double-buffered-graphics.md)
- [<span data-ttu-id="90a86-121">Gráficos y dibujos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="90a86-121">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
