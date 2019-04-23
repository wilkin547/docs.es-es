---
title: Procedimiento Usar las propiedades asociadas de Canvas para situar elementos secundarios
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- attached properties [WPF Designer]
- Canvas control [WPF], attached properties
ms.assetid: 48f1d25d-3820-4107-a4cc-d6c1e5664a44
ms.openlocfilehash: 347c8502bd4c5fafcde7a142327f85bfb75b9954
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59159632"
---
# <a name="how-to-use-the-attached-properties-of-canvas-to-position-child-elements"></a><span data-ttu-id="a1d26-102">Procedimiento Usar las propiedades asociadas de Canvas para situar elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a1d26-102">How to: Use the Attached Properties of Canvas to Position Child Elements</span></span>
<span data-ttu-id="a1d26-103">En este ejemplo se muestra cómo usar las propiedades asociadas de <xref:System.Windows.Controls.Canvas> para situar elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="a1d26-103">This example shows how to use the attached properties of <xref:System.Windows.Controls.Canvas> to position child elements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a1d26-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a1d26-104">Example</span></span>  
 <span data-ttu-id="a1d26-105">El ejemplo siguiente agrega cuatro <xref:System.Windows.Controls.Button> elementos como elementos secundarios de un elemento primario <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="a1d26-105">The following example adds four <xref:System.Windows.Controls.Button> elements as child elements of a parent <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="a1d26-106">Cada elemento se representa mediante un <xref:System.Windows.Controls.Canvas.Bottom%2A>, <xref:System.Windows.Controls.Canvas.Left%2A>, <xref:System.Windows.Controls.Canvas.Right%2A>, y <xref:System.Windows.Controls.Canvas.Top%2A>.</span><span class="sxs-lookup"><span data-stu-id="a1d26-106">Each element is represented by a <xref:System.Windows.Controls.Canvas.Bottom%2A>, <xref:System.Windows.Controls.Canvas.Left%2A>, <xref:System.Windows.Controls.Canvas.Right%2A>, and <xref:System.Windows.Controls.Canvas.Top%2A>.</span></span>
<span data-ttu-id="a1d26-107">Cada <xref:System.Windows.Controls.Button> se sitúa en relación con el elemento primario <xref:System.Windows.Controls.Canvas> y según su valor de propiedad asignado.</span><span class="sxs-lookup"><span data-stu-id="a1d26-107">Each <xref:System.Windows.Controls.Button> is positioned relative to the parent <xref:System.Windows.Controls.Canvas> and according to its assigned property value.</span></span>  
  
 [!code-cpp[CanvasAttachedProperties#1](~/samples/snippets/cpp/VS_Snippets_Wpf/CanvasAttachedProperties/CPP/CanvasAttachedProps.cpp#1)]
 [!code-csharp[CanvasAttachedProperties#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CanvasAttachedProperties/CSharp/CanvasAttachedProps.cs#1)]
 [!code-vb[CanvasAttachedProperties#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasAttachedProperties/VisualBasic/CanvasAttachedProps.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="a1d26-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="a1d26-108">See also</span></span>

- <xref:System.Windows.Controls.Canvas>
- <xref:System.Windows.Controls.Canvas.Bottom%2A>
- <xref:System.Windows.Controls.Canvas.Left%2A>
- <xref:System.Windows.Controls.Canvas.Right%2A>
- <xref:System.Windows.Controls.Canvas.Top%2A>
- <xref:System.Windows.Controls.Button>
- [<span data-ttu-id="a1d26-109">Información general sobre elementos Panel</span><span class="sxs-lookup"><span data-stu-id="a1d26-109">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="a1d26-110">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="a1d26-110">How-to Topics</span></span>](canvas-how-to-topics.md)
- [<span data-ttu-id="a1d26-111">Información general sobre propiedades asociadas</span><span class="sxs-lookup"><span data-stu-id="a1d26-111">Attached Properties Overview</span></span>](../advanced/attached-properties-overview.md)
