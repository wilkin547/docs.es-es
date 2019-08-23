---
title: Procedimiento para administrar manualmente gráficos almacenados en búfer
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flicker [Windows Forms], reducing by manually managing graphics
- graphics [Windows Forms], managing buffered
ms.assetid: 4c2a90ee-bbbe-4ff6-9170-1b06c195c918
ms.openlocfilehash: 6010d52750b20c07db51917621f8643e9d9b47d7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968597"
---
# <a name="how-to-manually-manage-buffered-graphics"></a><span data-ttu-id="c57df-102">Procedimiento para administrar manualmente gráficos almacenados en búfer</span><span class="sxs-lookup"><span data-stu-id="c57df-102">How to: Manually Manage Buffered Graphics</span></span>
<span data-ttu-id="c57df-103">Para escenarios de doble búfer más avanzados, puede usar las clases .NET Framework para implementar su propia lógica de doble búfer.</span><span class="sxs-lookup"><span data-stu-id="c57df-103">For more advanced double buffering scenarios, you can use the .NET Framework classes to implement your own double-buffering logic.</span></span> <span data-ttu-id="c57df-104">La clase responsable de la asignación y administración de búferes de gráficos <xref:System.Drawing.BufferedGraphicsContext> individuales es la clase.</span><span class="sxs-lookup"><span data-stu-id="c57df-104">The class responsible for allocating and managing individual graphics buffers is the <xref:System.Drawing.BufferedGraphicsContext> class.</span></span> <span data-ttu-id="c57df-105">Cada aplicación tiene su propio valor <xref:System.Drawing.BufferedGraphicsContext> predeterminado que administra todo el búfer doble predeterminado para esa aplicación.</span><span class="sxs-lookup"><span data-stu-id="c57df-105">Every application has its own default <xref:System.Drawing.BufferedGraphicsContext> that manages all of the default double buffering for that application.</span></span> <span data-ttu-id="c57df-106">Puede recuperar una referencia a esta instancia llamando <xref:System.Drawing.BufferedGraphicsManager.Current%2A>a.</span><span class="sxs-lookup"><span data-stu-id="c57df-106">You can retrieve a reference to this instance by calling the <xref:System.Drawing.BufferedGraphicsManager.Current%2A>.</span></span>  
  
### <a name="to-obtain-a-reference-to-the-default-bufferedgraphicscontext"></a><span data-ttu-id="c57df-107">Para obtener una referencia al BufferedGraphicsContext predeterminado</span><span class="sxs-lookup"><span data-stu-id="c57df-107">To obtain a reference to the default BufferedGraphicsContext</span></span>  
  
- <span data-ttu-id="c57df-108">Establezca la <xref:System.Drawing.BufferedGraphicsManager.Current%2A> propiedad, como se muestra en el ejemplo de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="c57df-108">Set the <xref:System.Drawing.BufferedGraphicsManager.Current%2A> property, as shown in the following code example.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#11)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#11)]  
  
    > [!NOTE]
    > <span data-ttu-id="c57df-109">No es necesario llamar al `Dispose` método en la <xref:System.Drawing.BufferedGraphicsContext> referencia que se recibe de la <xref:System.Drawing.BufferedGraphicsManager> clase.</span><span class="sxs-lookup"><span data-stu-id="c57df-109">You do not need to call the `Dispose` method on the <xref:System.Drawing.BufferedGraphicsContext> reference that you receive from the <xref:System.Drawing.BufferedGraphicsManager> class.</span></span> <span data-ttu-id="c57df-110">Controla toda la asignación de memoria y la distribución de las instancias predeterminadas <xref:System.Drawing.BufferedGraphicsContext>. <xref:System.Drawing.BufferedGraphicsManager></span><span class="sxs-lookup"><span data-stu-id="c57df-110">The <xref:System.Drawing.BufferedGraphicsManager> handles all of the memory allocation and distribution for default <xref:System.Drawing.BufferedGraphicsContext> instances.</span></span>  
  
     <span data-ttu-id="c57df-111">En el <xref:System.Drawing.BufferedGraphicsContext> <xref:System.Drawing.BufferedGraphicsContext> casodelasaplicacionesconunusointensivodegráficoscomolaanimación,enocasionespuedemejorarelrendimientomedianteundedicadoenlugardelos<xref:System.Drawing.BufferedGraphicsManager>proporcionados por.</span><span class="sxs-lookup"><span data-stu-id="c57df-111">For graphically intensive applications such as animation, you can sometimes improve performance by using a dedicated <xref:System.Drawing.BufferedGraphicsContext> instead of the <xref:System.Drawing.BufferedGraphicsContext> provided by the <xref:System.Drawing.BufferedGraphicsManager>.</span></span> <span data-ttu-id="c57df-112">Esto le permite crear y administrar búferes de gráficos individualmente, sin incurrir en la sobrecarga de rendimiento que supone administrar todos los demás gráficos almacenados en búfer asociados a la aplicación, aunque la memoria consumida por la aplicación será mayor.</span><span class="sxs-lookup"><span data-stu-id="c57df-112">This enables you to create and manage graphics buffers individually, without incurring the performance overhead of managing all the other buffered graphics associated with your application, though the memory consumed by the application will be greater.</span></span>  
  
### <a name="to-create-a-dedicated-bufferedgraphicscontext"></a><span data-ttu-id="c57df-113">Para crear un BufferedGraphicsContext dedicado</span><span class="sxs-lookup"><span data-stu-id="c57df-113">To create a dedicated BufferedGraphicsContext</span></span>  
  
- <span data-ttu-id="c57df-114">Declare y cree una instancia nueva de <xref:System.Drawing.BufferedGraphicsContext> la clase, como se muestra en el ejemplo de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="c57df-114">Declare and create a new instance of the <xref:System.Drawing.BufferedGraphicsContext> class, as shown in the following code example.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#12)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#12)]  
  
## <a name="see-also"></a><span data-ttu-id="c57df-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="c57df-115">See also</span></span>

- <xref:System.Drawing.BufferedGraphicsContext>
- [<span data-ttu-id="c57df-116">Gráficos de doble búfer</span><span class="sxs-lookup"><span data-stu-id="c57df-116">Double Buffered Graphics</span></span>](double-buffered-graphics.md)
- [<span data-ttu-id="c57df-117">Cómo: Representar manualmente gráficos almacenados en búfer</span><span class="sxs-lookup"><span data-stu-id="c57df-117">How to: Manually Render Buffered Graphics</span></span>](how-to-manually-render-buffered-graphics.md)
