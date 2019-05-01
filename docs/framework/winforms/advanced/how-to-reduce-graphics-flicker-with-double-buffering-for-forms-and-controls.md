---
title: Procedimiento para reducir el parpadeo de los gráficos con un búfer doble en formularios y controles
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flicker [Windows Forms], reducing in Windows Forms
- graphics [Windows Forms], reducing double-buffered flicker
ms.assetid: 91083d3a-653f-4f15-a467-0f37b2aa39d6
ms.openlocfilehash: ef05b72b33d3f28d1811389dfae65554a1567d43
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61967133"
---
# <a name="how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls"></a><span data-ttu-id="39cef-102">Procedimiento para reducir el parpadeo de los gráficos con un búfer doble en formularios y controles</span><span class="sxs-lookup"><span data-stu-id="39cef-102">How to: Reduce Graphics Flicker with Double Buffering for Forms and Controls</span></span>
<span data-ttu-id="39cef-103">El almacenamiento en doble búfer usa un búfer de memoria para solucionar los problemas de parpadeo asociados a varias operaciones de pintura.</span><span class="sxs-lookup"><span data-stu-id="39cef-103">Double buffering uses a memory buffer to address the flicker problems associated with multiple paint operations.</span></span> <span data-ttu-id="39cef-104">Cuando se habilita el almacenamiento en doble búfer, todas las operaciones de pintura se representan primero en un búfer de memoria en lugar de la superficie de dibujo en la pantalla.</span><span class="sxs-lookup"><span data-stu-id="39cef-104">When double buffering is enabled, all paint operations are first rendered to a memory buffer instead of the drawing surface on the screen.</span></span> <span data-ttu-id="39cef-105">Una vez completadas todas las operaciones de pintura, el búfer de memoria se copia directamente en la superficie de dibujo asociada a él.</span><span class="sxs-lookup"><span data-stu-id="39cef-105">After all paint operations are completed, the memory buffer is copied directly to the drawing surface associated with it.</span></span> <span data-ttu-id="39cef-106">Dado que se realiza solo una única operación gráfica en la pantalla, se elimina, el parpadeo de las imágenes asociadas a operaciones de pintura complejas. Para la mayoría de las aplicaciones, el búfer doble predeterminado proporcionado por el [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] proporcionará los mejores resultados.</span><span class="sxs-lookup"><span data-stu-id="39cef-106">Because only one graphics operation is performed on the screen, the image flickering associated with complex painting operations is eliminated.For most applications, the default double buffering provided by the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] will provide the best results.</span></span> <span data-ttu-id="39cef-107">Controles estándar de Windows Forms tienen dobles búfer de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="39cef-107">Standard Windows Forms controls are double buffered by default.</span></span> <span data-ttu-id="39cef-108">Se puede habilitar de forma predeterminada en doble búfer en los formularios y controles creados de dos maneras.</span><span class="sxs-lookup"><span data-stu-id="39cef-108">You can enable default double buffering in your forms and authored controls in two ways.</span></span> <span data-ttu-id="39cef-109">Puede establecer el <xref:System.Windows.Forms.Control.DoubleBuffered%2A> propiedad `true`, o bien puede llamar el <xref:System.Windows.Forms.Control.SetStyle%2A> método para establecer el <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> marca a `true`.</span><span class="sxs-lookup"><span data-stu-id="39cef-109">You can either set the <xref:System.Windows.Forms.Control.DoubleBuffered%2A> property to `true`, or you can call the <xref:System.Windows.Forms.Control.SetStyle%2A> method to set the <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> flag to `true`.</span></span> <span data-ttu-id="39cef-110">Ambos métodos habilitará de forma predeterminada un búfer doble en formularios y controles y proporcionar la representación de gráficos sin parpadeo.</span><span class="sxs-lookup"><span data-stu-id="39cef-110">Both methods will enable default double buffering for your form or control and provide flicker-free graphics rendering.</span></span> <span data-ttu-id="39cef-111">Una llamada a la <xref:System.Windows.Forms.Control.SetStyle%2A> método solo se recomienda para los controles personalizados para el que ha escrito todo el código de representación.</span><span class="sxs-lookup"><span data-stu-id="39cef-111">Calling the <xref:System.Windows.Forms.Control.SetStyle%2A> method is recommended only for custom controls for which you have written all the rendering code.</span></span>  
  
 <span data-ttu-id="39cef-112">Para más avanzados escenarios de almacenamiento en búfer doble, como animación o administración avanzada de memoria, puede implementar su propia lógica de almacenamiento en búfer doble.</span><span class="sxs-lookup"><span data-stu-id="39cef-112">For more advanced double buffering scenarios, such as animation or advanced memory management, you can implement your own double buffering logic.</span></span> <span data-ttu-id="39cef-113">Para obtener más información, vea [Cómo: Administrar manualmente gráficos almacenados en búfer](how-to-manually-manage-buffered-graphics.md).</span><span class="sxs-lookup"><span data-stu-id="39cef-113">For more information, see [How to: Manually Manage Buffered Graphics](how-to-manually-manage-buffered-graphics.md).</span></span>  
  
### <a name="to-reduce-flicker"></a><span data-ttu-id="39cef-114">Para reducir el parpadeo</span><span class="sxs-lookup"><span data-stu-id="39cef-114">To reduce flicker</span></span>  
  
- <span data-ttu-id="39cef-115">Establezca la propiedad <xref:System.Windows.Forms.Control.DoubleBuffered%2A> en `true`.</span><span class="sxs-lookup"><span data-stu-id="39cef-115">Set the <xref:System.Windows.Forms.Control.DoubleBuffered%2A> property to `true`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#31)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#31)]  
  
 <span data-ttu-id="39cef-116">\- o -</span><span class="sxs-lookup"><span data-stu-id="39cef-116">\- or -</span></span>  
  
- <span data-ttu-id="39cef-117">Llame a la <xref:System.Windows.Forms.Control.SetStyle%2A> método para establecer el <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> marca `true`.</span><span class="sxs-lookup"><span data-stu-id="39cef-117">Call the <xref:System.Windows.Forms.Control.SetStyle%2A> method to set the <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> flag to `true`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#32](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#32)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#32](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#32)]  
  
## <a name="see-also"></a><span data-ttu-id="39cef-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="39cef-118">See also</span></span>

- <xref:System.Windows.Forms.Control.DoubleBuffered%2A>
- <xref:System.Windows.Forms.Control.SetStyle%2A>
- [<span data-ttu-id="39cef-119">Gráficos de doble búfer</span><span class="sxs-lookup"><span data-stu-id="39cef-119">Double Buffered Graphics</span></span>](double-buffered-graphics.md)
- [<span data-ttu-id="39cef-120">Gráficos y dibujos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="39cef-120">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
