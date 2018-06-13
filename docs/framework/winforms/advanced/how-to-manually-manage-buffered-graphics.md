---
title: 'Cómo: Administrar manualmente gráficos almacenados en búfer'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flicker [Windows Forms], reducing by manually managing graphics
- graphics [Windows Forms], managing buffered
ms.assetid: 4c2a90ee-bbbe-4ff6-9170-1b06c195c918
ms.openlocfilehash: f8675582fe6bafefd94d6a740c3263e407dfd4e7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33523960"
---
# <a name="how-to-manually-manage-buffered-graphics"></a><span data-ttu-id="95556-102">Cómo: Administrar manualmente gráficos almacenados en búfer</span><span class="sxs-lookup"><span data-stu-id="95556-102">How to: Manually Manage Buffered Graphics</span></span>
<span data-ttu-id="95556-103">Para escenarios más avanzados de almacenamiento en búfer dobles, puede usar el [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] las clases para implementar su propia lógica de almacenamiento en búfer doble.</span><span class="sxs-lookup"><span data-stu-id="95556-103">For more advanced double buffering scenarios, you can use the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] classes to implement your own double-buffering logic.</span></span> <span data-ttu-id="95556-104">La clase responsable de asignar y administrar los búferes de gráficos individuales es la <xref:System.Drawing.BufferedGraphicsContext> clase.</span><span class="sxs-lookup"><span data-stu-id="95556-104">The class responsible for allocating and managing individual graphics buffers is the <xref:System.Drawing.BufferedGraphicsContext> class.</span></span> <span data-ttu-id="95556-105">Cada aplicación tiene su propio valor predeterminado <xref:System.Drawing.BufferedGraphicsContext> que administra todos de manera predeterminada el doble búfer para esa aplicación.</span><span class="sxs-lookup"><span data-stu-id="95556-105">Every application has its own default <xref:System.Drawing.BufferedGraphicsContext> that manages all of the default double buffering for that application.</span></span> <span data-ttu-id="95556-106">Puede recuperar una referencia a esta instancia mediante una llamada a la <xref:System.Drawing.BufferedGraphicsManager.Current%2A>.</span><span class="sxs-lookup"><span data-stu-id="95556-106">You can retrieve a reference to this instance by calling the <xref:System.Drawing.BufferedGraphicsManager.Current%2A>.</span></span>  
  
### <a name="to-obtain-a-reference-to-the-default-bufferedgraphicscontext"></a><span data-ttu-id="95556-107">Para obtener una referencia a la clase BufferedGraphicsContext predeterminada</span><span class="sxs-lookup"><span data-stu-id="95556-107">To obtain a reference to the default BufferedGraphicsContext</span></span>  
  
-   <span data-ttu-id="95556-108">Establecer el <xref:System.Drawing.BufferedGraphicsManager.Current%2A> propiedad, como se muestra en el ejemplo de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="95556-108">Set the <xref:System.Drawing.BufferedGraphicsManager.Current%2A> property, as shown in the following code example.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#11)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#11)]  
  
    > [!NOTE]
    >  <span data-ttu-id="95556-109">No es necesario llamar a la `Dispose` método en el <xref:System.Drawing.BufferedGraphicsContext> referencia que recibe la <xref:System.Drawing.BufferedGraphicsManager> clase.</span><span class="sxs-lookup"><span data-stu-id="95556-109">You do not need to call the `Dispose` method on the <xref:System.Drawing.BufferedGraphicsContext> reference that you receive from the <xref:System.Drawing.BufferedGraphicsManager> class.</span></span> <span data-ttu-id="95556-110">El <xref:System.Drawing.BufferedGraphicsManager> se encarga de toda la asignación de memoria de distribución predeterminada <xref:System.Drawing.BufferedGraphicsContext> instancias.</span><span class="sxs-lookup"><span data-stu-id="95556-110">The <xref:System.Drawing.BufferedGraphicsManager> handles all of the memory allocation and distribution for default <xref:System.Drawing.BufferedGraphicsContext> instances.</span></span>  
  
     <span data-ttu-id="95556-111">Para las aplicaciones gráficamente intensivas como las animaciones, a veces puede mejorar el rendimiento mediante el uso de una dedicado <xref:System.Drawing.BufferedGraphicsContext> en lugar de la <xref:System.Drawing.BufferedGraphicsContext> proporcionada por el <xref:System.Drawing.BufferedGraphicsManager>.</span><span class="sxs-lookup"><span data-stu-id="95556-111">For graphically intensive applications such as animation, you can sometimes improve performance by using a dedicated <xref:System.Drawing.BufferedGraphicsContext> instead of the <xref:System.Drawing.BufferedGraphicsContext> provided by the <xref:System.Drawing.BufferedGraphicsManager>.</span></span> <span data-ttu-id="95556-112">Esto le permite crear y administrar búferes de gráficos individualmente, sin incurrir en la sobrecarga de rendimiento de la administración de todos los otros gráficos almacenados en búfer asociados a la aplicación, aunque la memoria consumida por la aplicación será mayor.</span><span class="sxs-lookup"><span data-stu-id="95556-112">This enables you to create and manage graphics buffers individually, without incurring the performance overhead of managing all the other buffered graphics associated with your application, though the memory consumed by the application will be greater.</span></span>  
  
### <a name="to-create-a-dedicated-bufferedgraphicscontext"></a><span data-ttu-id="95556-113">Para crear una clase BufferedGraphicsContext dedicada</span><span class="sxs-lookup"><span data-stu-id="95556-113">To create a dedicated BufferedGraphicsContext</span></span>  
  
-   <span data-ttu-id="95556-114">Declarar y crear una nueva instancia de la <xref:System.Drawing.BufferedGraphicsContext> de la clase, como se muestra en el ejemplo de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="95556-114">Declare and create a new instance of the <xref:System.Drawing.BufferedGraphicsContext> class, as shown in the following code example.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#12)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#12)]  
  
## <a name="see-also"></a><span data-ttu-id="95556-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="95556-115">See Also</span></span>  
 <xref:System.Drawing.BufferedGraphicsContext>  
 [<span data-ttu-id="95556-116">Gráficos de doble búfer</span><span class="sxs-lookup"><span data-stu-id="95556-116">Double Buffered Graphics</span></span>](../../../../docs/framework/winforms/advanced/double-buffered-graphics.md)  
 [<span data-ttu-id="95556-117">Representar manualmente gráficos almacenados en búfer</span><span class="sxs-lookup"><span data-stu-id="95556-117">How to: Manually Render Buffered Graphics</span></span>](../../../../docs/framework/winforms/advanced/how-to-manually-render-buffered-graphics.md)
