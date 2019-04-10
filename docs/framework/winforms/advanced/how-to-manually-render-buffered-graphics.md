---
title: Filtrar para representar manualmente gráficos almacenados en búfer
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flicker [Windows Forms], reducing by manually rendering graphics
- graphics [Windows Forms], rendering
ms.assetid: 5192295e-bd8e-45f7-8bd6-5c4f6bd21e61
ms.openlocfilehash: 48dd1d76a42661df6ba642c032c991be4d6a2900
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59339936"
---
# <a name="how-to-manually-render-buffered-graphics"></a><span data-ttu-id="f9f1f-102">Filtrar para representar manualmente gráficos almacenados en búfer</span><span class="sxs-lookup"><span data-stu-id="f9f1f-102">How to: Manually Render Buffered Graphics</span></span>
<span data-ttu-id="f9f1f-103">Si administra sus propios gráficos almacenados en búfer, deberá poder crear y representar búferes de gráficos.</span><span class="sxs-lookup"><span data-stu-id="f9f1f-103">If you are managing your own buffered graphics, you will need to be able to create and render graphics buffers.</span></span> <span data-ttu-id="f9f1f-104">Puede crear instancias de la clase <xref:System.Drawing.BufferedGraphics> que está asociada con las superficies de dibujo en pantalla mediante llamadas al método <xref:System.Drawing.BufferedGraphicsContext.Allocate%2A>.</span><span class="sxs-lookup"><span data-stu-id="f9f1f-104">You can create instances of the <xref:System.Drawing.BufferedGraphics> class that is associated with drawing surfaces on your screen by calling the <xref:System.Drawing.BufferedGraphicsContext.Allocate%2A> method.</span></span> <span data-ttu-id="f9f1f-105">Este método crea una instancia <xref:System.Drawing.BufferedGraphics> que está asociada a una superficie de representación determinada, como un formulario o un control.</span><span class="sxs-lookup"><span data-stu-id="f9f1f-105">This method creates a <xref:System.Drawing.BufferedGraphics> instance that is associated with a particular rendering surface, such as a form or control.</span></span> <span data-ttu-id="f9f1f-106">Después de crear una instancia de <xref:System.Drawing.BufferedGraphics>, puede dibujar gráficos en el búfer que se representan mediante la propiedad <xref:System.Drawing.BufferedGraphics.Graphics%2A>.</span><span class="sxs-lookup"><span data-stu-id="f9f1f-106">After you have created a <xref:System.Drawing.BufferedGraphics> instance, you can draw graphics to the buffer it represents through the <xref:System.Drawing.BufferedGraphics.Graphics%2A> property.</span></span> <span data-ttu-id="f9f1f-107">Después de haber realizado todas las operaciones de gráficos, puede copiar el contenido del búfer en la pantalla llamando al método <xref:System.Drawing.BufferedGraphics.Render%2A>.</span><span class="sxs-lookup"><span data-stu-id="f9f1f-107">After you have performed all graphics operations, you can copy the contents of the buffer to the screen by calling the <xref:System.Drawing.BufferedGraphics.Render%2A> method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f9f1f-108">Si realiza su propia representación, aumentará el consumo de memoria, aunque este aumento puede ser ligero.</span><span class="sxs-lookup"><span data-stu-id="f9f1f-108">If you perform your own rendering, memory consumption will increase, though the increase may only be slight.</span></span>  
  
### <a name="to-manually-display-buffered-graphics"></a><span data-ttu-id="f9f1f-109">Para mostrar manualmente los gráficos almacenados en búfer</span><span class="sxs-lookup"><span data-stu-id="f9f1f-109">To manually display buffered graphics</span></span>  
  
1. <span data-ttu-id="f9f1f-110">Obtenga una referencia a una instancia de la clase <xref:System.Drawing.BufferedGraphicsContext>.</span><span class="sxs-lookup"><span data-stu-id="f9f1f-110">Obtain a reference to an instance of the <xref:System.Drawing.BufferedGraphicsContext> class.</span></span> <span data-ttu-id="f9f1f-111">Para obtener más información, vea [Cómo: Administrar manualmente gráficos almacenados en búfer](how-to-manually-manage-buffered-graphics.md).</span><span class="sxs-lookup"><span data-stu-id="f9f1f-111">For more information, see [How to: Manually Manage Buffered Graphics](how-to-manually-manage-buffered-graphics.md).</span></span>  
  
2. <span data-ttu-id="f9f1f-112">Cree una instancia de la clase <xref:System.Drawing.BufferedGraphics> llamando al método <xref:System.Drawing.BufferedGraphicsContext.Allocate%2A>, tal y como se muestra en el ejemplo de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="f9f1f-112">Create an instance of the <xref:System.Drawing.BufferedGraphics> class by calling the <xref:System.Drawing.BufferedGraphicsContext.Allocate%2A> method, as shown in the following code example.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#21)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#21)]  
  
3. <span data-ttu-id="f9f1f-113">Dibuje los gráficos en el búfer de gráficos estableciendo la propiedad <xref:System.Drawing.BufferedGraphics.Graphics%2A>.</span><span class="sxs-lookup"><span data-stu-id="f9f1f-113">Draw graphics to the graphics buffer by setting the <xref:System.Drawing.BufferedGraphics.Graphics%2A> property.</span></span> <span data-ttu-id="f9f1f-114">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f9f1f-114">For example:</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#22)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#22)]  
  
4. <span data-ttu-id="f9f1f-115">Cuando haya completado todas las operaciones de dibujo en el búfer de gráficos, llame al método <xref:System.Drawing.BufferedGraphics.Render%2A> para representar el búfer, bien en la superficie de dibujo asociada con dicho búfer, o en una superficie de dibujo que especifique, tal y como se muestra en el ejemplo de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="f9f1f-115">When you have completed all of your drawing operations to the graphics buffer, call the <xref:System.Drawing.BufferedGraphics.Render%2A> method to render the buffer, either to the drawing surface associated with that buffer, or to a specified drawing surface, as shown in the following code example.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#23)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#23)]  
  
5. <span data-ttu-id="f9f1f-116">Cuando haya terminado de representar los gráficos, llame al método `Dispose` en la instancia <xref:System.Drawing.BufferedGraphics> para liberar recursos del sistema.</span><span class="sxs-lookup"><span data-stu-id="f9f1f-116">After you are finished rendering graphics, call the `Dispose` method on the <xref:System.Drawing.BufferedGraphics> instance to free system resources.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#24](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#24)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#24](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#24)]  
  
## <a name="see-also"></a><span data-ttu-id="f9f1f-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="f9f1f-117">See also</span></span>

- <xref:System.Drawing.BufferedGraphicsContext>
- <xref:System.Drawing.BufferedGraphics>
- [<span data-ttu-id="f9f1f-118">Gráficos de doble búfer</span><span class="sxs-lookup"><span data-stu-id="f9f1f-118">Double Buffered Graphics</span></span>](double-buffered-graphics.md)
- [<span data-ttu-id="f9f1f-119">Filtrar para administrar manualmente gráficos almacenados en búfer</span><span class="sxs-lookup"><span data-stu-id="f9f1f-119">How to: Manually Manage Buffered Graphics</span></span>](how-to-manually-manage-buffered-graphics.md)
