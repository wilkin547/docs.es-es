---
title: 'Cómo: Utilizar las propiedades asociadas de Canvas para situar elementos secundarios'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- attached properties [WPF Designer]
- Canvas control [WPF], attached properties
ms.assetid: 48f1d25d-3820-4107-a4cc-d6c1e5664a44
ms.openlocfilehash: 89327b834dfd71c0a7420eb42a598b98cdb5e9d8
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44208498"
---
# <a name="how-to-use-the-attached-properties-of-canvas-to-position-child-elements"></a><span data-ttu-id="26d31-102">Cómo: Utilizar las propiedades asociadas de Canvas para situar elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="26d31-102">How to: Use the Attached Properties of Canvas to Position Child Elements</span></span>
<span data-ttu-id="26d31-103">En este ejemplo se muestra cómo usar las propiedades asociadas de <xref:System.Windows.Controls.Canvas> para situar elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="26d31-103">This example shows how to use the attached properties of <xref:System.Windows.Controls.Canvas> to position child elements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="26d31-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="26d31-104">Example</span></span>  
 <span data-ttu-id="26d31-105">El ejemplo siguiente agrega cuatro <xref:System.Windows.Controls.Button> elementos como elementos secundarios de un elemento primario <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="26d31-105">The following example adds four <xref:System.Windows.Controls.Button> elements as child elements of a parent <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="26d31-106">Cada elemento se representa mediante un <xref:System.Windows.Controls.Canvas.Bottom%2A>, <xref:System.Windows.Controls.Canvas.Left%2A>, <xref:System.Windows.Controls.Canvas.Right%2A>, y <xref:System.Windows.Controls.Canvas.Top%2A>.</span><span class="sxs-lookup"><span data-stu-id="26d31-106">Each element is represented by a <xref:System.Windows.Controls.Canvas.Bottom%2A>, <xref:System.Windows.Controls.Canvas.Left%2A>, <xref:System.Windows.Controls.Canvas.Right%2A>, and <xref:System.Windows.Controls.Canvas.Top%2A>.</span></span>
<span data-ttu-id="26d31-107">Cada <xref:System.Windows.Controls.Button> se sitúa en relación con el elemento primario <xref:System.Windows.Controls.Canvas> y según su valor de propiedad asignado.</span><span class="sxs-lookup"><span data-stu-id="26d31-107">Each <xref:System.Windows.Controls.Button> is positioned relative to the parent <xref:System.Windows.Controls.Canvas> and according to its assigned property value.</span></span>  
  
 [!code-cpp[CanvasAttachedProperties#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/CanvasAttachedProperties/CPP/CanvasAttachedProps.cpp#1)]
 [!code-csharp[CanvasAttachedProperties#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CanvasAttachedProperties/CSharp/CanvasAttachedProps.cs#1)]
 [!code-vb[CanvasAttachedProperties#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasAttachedProperties/VisualBasic/CanvasAttachedProps.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="26d31-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="26d31-108">See Also</span></span>  
 <xref:System.Windows.Controls.Canvas>  
 <xref:System.Windows.Controls.Canvas.Bottom%2A>  
 <xref:System.Windows.Controls.Canvas.Left%2A>  
 <xref:System.Windows.Controls.Canvas.Right%2A>  
 <xref:System.Windows.Controls.Canvas.Top%2A>  
 <xref:System.Windows.Controls.Button>  
 [<span data-ttu-id="26d31-109">Información general sobre elementos Panel</span><span class="sxs-lookup"><span data-stu-id="26d31-109">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [<span data-ttu-id="26d31-110">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="26d31-110">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/canvas-how-to-topics.md)  
 [<span data-ttu-id="26d31-111">Información general sobre propiedades asociadas</span><span class="sxs-lookup"><span data-stu-id="26d31-111">Attached Properties Overview</span></span>](../../../../docs/framework/wpf/advanced/attached-properties-overview.md)
