---
title: Procedimiento para ajustar un control de formularios Windows Forms con ToolStripControlHost
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ToolStrip control [Windows Forms], wrapping controls
- toolbars [Windows Forms], wrapping controls
- ToolStrip control [Windows Forms], hosting controls
ms.assetid: e2ce4990-661d-4882-a116-8a9eb575dc84
ms.openlocfilehash: 4f1bac24d7742066d2b472f52b7d85c84c243670
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2019
ms.locfileid: "65589033"
---
# <a name="how-to-wrap-a-windows-forms-control-with-toolstripcontrolhost"></a><span data-ttu-id="9f8dd-102">Procedimiento para ajustar un control de formularios Windows Forms con ToolStripControlHost</span><span class="sxs-lookup"><span data-stu-id="9f8dd-102">How to: Wrap a Windows Forms Control with ToolStripControlHost</span></span>
<span data-ttu-id="9f8dd-103"><xref:System.Windows.Forms.ToolStripControlHost> está diseñado para habilitar el hospedaje de controles de Windows Forms arbitrarios mediante el constructor <xref:System.Windows.Forms.ToolStripControlHost> o extendiendo el propio <xref:System.Windows.Forms.ToolStripControlHost>.</span><span class="sxs-lookup"><span data-stu-id="9f8dd-103"><xref:System.Windows.Forms.ToolStripControlHost> is designed to enable hosting of arbitrary Windows Forms controls by using the <xref:System.Windows.Forms.ToolStripControlHost> constructor or by extending <xref:System.Windows.Forms.ToolStripControlHost> itself.</span></span> <span data-ttu-id="9f8dd-104">Es más sencillo ajustar el control extendiendo <xref:System.Windows.Forms.ToolStripControlHost> e implementando las propiedades y los métodos que exponen las propiedades y los métodos del control que se usan con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="9f8dd-104">It is easier to wrap the control by extending <xref:System.Windows.Forms.ToolStripControlHost> and implementing properties and methods that expose frequently used properties and methods of the control.</span></span> <span data-ttu-id="9f8dd-105">También puede exponer los eventos del control en el nivel de <xref:System.Windows.Forms.ToolStripControlHost>.</span><span class="sxs-lookup"><span data-stu-id="9f8dd-105">You can also expose events for the control at the <xref:System.Windows.Forms.ToolStripControlHost> level.</span></span>  
  
### <a name="to-host-a-control-in-a-toolstripcontrolhost-by-derivation"></a><span data-ttu-id="9f8dd-106">Para hospedar un control en un ToolStripControlHost por derivación</span><span class="sxs-lookup"><span data-stu-id="9f8dd-106">To host a control in a ToolStripControlHost by derivation</span></span>  
  
1. <span data-ttu-id="9f8dd-107">Extienda <xref:System.Windows.Forms.ToolStripControlHost>.</span><span class="sxs-lookup"><span data-stu-id="9f8dd-107">Extend <xref:System.Windows.Forms.ToolStripControlHost>.</span></span> <span data-ttu-id="9f8dd-108">Implemente un constructor predeterminado que llame al constructor de clase base pasando el control deseado.</span><span class="sxs-lookup"><span data-stu-id="9f8dd-108">Implement a default constructor that calls the base class constructor passing in the desired control.</span></span>  
  
     [!code-cpp[System.Windows.Forms.ToolStripControlHost#10](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CPP/form1.cpp#10)]
     [!code-csharp[System.Windows.Forms.ToolStripControlHost#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CS/form1.cs#10)]
     [!code-vb[System.Windows.Forms.ToolStripControlHost#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/VB/form1.vb#10)]  
  
2. <span data-ttu-id="9f8dd-109">Declare una propiedad del mismo tipo que el control ajustado y devuelva `Control` como el tipo de control correcto en el descriptor de acceso de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="9f8dd-109">Declare a property of the same type as the wrapped control and return `Control` as the correct type of control in the property's accessor.</span></span>  
  
     [!code-cpp[System.Windows.Forms.ToolStripControlHost#11](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CPP/form1.cpp#11)]
     [!code-csharp[System.Windows.Forms.ToolStripControlHost#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CS/form1.cs#11)]
     [!code-vb[System.Windows.Forms.ToolStripControlHost#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/VB/form1.vb#11)]  
  
3. <span data-ttu-id="9f8dd-110">Exponga otras propiedades y métodos del control ajustado que se usen con frecuencia con las propiedades y los métodos de la clase extendida.</span><span class="sxs-lookup"><span data-stu-id="9f8dd-110">Expose other frequently used properties and methods of the wrapped control with properties and methods in the extended class.</span></span>  
  
     [!code-cpp[System.Windows.Forms.ToolStripControlHost#12](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CPP/form1.cpp#12)]
     [!code-csharp[System.Windows.Forms.ToolStripControlHost#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CS/form1.cs#12)]
     [!code-vb[System.Windows.Forms.ToolStripControlHost#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/VB/form1.vb#12)]  
  
4. <span data-ttu-id="9f8dd-111">Opcionalmente, invalide los métodos <xref:System.Windows.Forms.ToolStripControlHost.OnSubscribeControlEvents%2A> y <xref:System.Windows.Forms.ToolStripControlHost.OnUnsubscribeControlEvents%2A> y agregue los eventos de control que desea exponer.</span><span class="sxs-lookup"><span data-stu-id="9f8dd-111">Optionally, override the <xref:System.Windows.Forms.ToolStripControlHost.OnSubscribeControlEvents%2A>, and <xref:System.Windows.Forms.ToolStripControlHost.OnUnsubscribeControlEvents%2A> methods and add the control events you want to expose.</span></span>  
  
     [!code-cpp[System.Windows.Forms.ToolStripControlHost#16](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CPP/form1.cpp#16)]
     [!code-csharp[System.Windows.Forms.ToolStripControlHost#16](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CS/form1.cs#16)]
     [!code-vb[System.Windows.Forms.ToolStripControlHost#16](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/VB/form1.vb#16)]  
  
5. <span data-ttu-id="9f8dd-112">Proporcione el ajuste necesario para los eventos que desea exponer.</span><span class="sxs-lookup"><span data-stu-id="9f8dd-112">Provide the necessary wrapping for the events you want to expose.</span></span>  
  
     [!code-cpp[System.Windows.Forms.ToolStripControlHost#17](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CPP/form1.cpp#17)]
     [!code-csharp[System.Windows.Forms.ToolStripControlHost#17](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CS/form1.cs#17)]
     [!code-vb[System.Windows.Forms.ToolStripControlHost#17](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/VB/form1.vb#17)]  
  
## <a name="example"></a><span data-ttu-id="9f8dd-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9f8dd-113">Example</span></span>  
 [!code-cpp[System.Windows.Forms.ToolStripControlHost#13](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CPP/form1.cpp#13)]
 [!code-csharp[System.Windows.Forms.ToolStripControlHost#13](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CS/form1.cs#13)]
 [!code-vb[System.Windows.Forms.ToolStripControlHost#13](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/VB/form1.vb#13)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9f8dd-114">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="9f8dd-114">Compiling the Code</span></span>  
  
<span data-ttu-id="9f8dd-115">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="9f8dd-115">This example requires:</span></span>
  
- <span data-ttu-id="9f8dd-116">Referencias a los ensamblados System y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="9f8dd-116">References to the System and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f8dd-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="9f8dd-117">See also</span></span>

- <xref:System.Windows.Forms.ToolStripControlHost>
- [<span data-ttu-id="9f8dd-118">Información sobre el control ToolStrip</span><span class="sxs-lookup"><span data-stu-id="9f8dd-118">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="9f8dd-119">Arquitectura del control ToolStrip</span><span class="sxs-lookup"><span data-stu-id="9f8dd-119">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="9f8dd-120">Resumen de la tecnología ToolStrip</span><span class="sxs-lookup"><span data-stu-id="9f8dd-120">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)
