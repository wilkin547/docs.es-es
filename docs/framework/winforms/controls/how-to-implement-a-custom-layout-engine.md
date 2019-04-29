---
title: Procedimiento para implementar un motor de diseño personalizado
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- layout engines [Windows Forms], custom
- TableLayoutPanel control [Windows Forms], layout engine
- layout engines [Windows Forms], implementing
- FlowLayoutPanel control [Windows Forms], layout engine
ms.assetid: f91aa91c-29f4-4089-95ca-5d48b774b00e
ms.openlocfilehash: 8e5043e2b42b1e7449c6dab51691b6d57e28cd53
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61941250"
---
# <a name="how-to-implement-a-custom-layout-engine"></a><span data-ttu-id="8dc26-102">Procedimiento para implementar un motor de diseño personalizado</span><span class="sxs-lookup"><span data-stu-id="8dc26-102">How to: Implement a Custom Layout Engine</span></span>
<span data-ttu-id="8dc26-103">En el ejemplo de código siguiente se muestra cómo crear un motor de diseño personalizado que realiza un diseño de flujo simple.</span><span class="sxs-lookup"><span data-stu-id="8dc26-103">The following code example demonstrates how to create a custom layout engine that performs a simple flow layout.</span></span> <span data-ttu-id="8dc26-104">Implementa un control de panel denominado `DemoFlowPanel`, lo que invalida el <xref:System.Windows.Forms.Control.LayoutEngine%2A> propiedad para proporcionar una instancia de la `DemoFlowLayout` clase.</span><span class="sxs-lookup"><span data-stu-id="8dc26-104">It implements a panel control named `DemoFlowPanel`, which overrides the <xref:System.Windows.Forms.Control.LayoutEngine%2A> property to provide an instance of the `DemoFlowLayout` class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8dc26-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8dc26-105">Example</span></span>  
 [!code-cpp[System.Windows.Forms.Layout.LayoutEngine#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.Layout.LayoutEngine/cpp/DemoFlowLayout.cpp#1)]
 [!code-csharp[System.Windows.Forms.Layout.LayoutEngine#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Layout.LayoutEngine/CS/DemoFlowLayout.cs#1)]
 [!code-vb[System.Windows.Forms.Layout.LayoutEngine#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Layout.LayoutEngine/VB/DemoFlowLayout.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="8dc26-106">Vea también</span><span class="sxs-lookup"><span data-stu-id="8dc26-106">See also</span></span>

- <xref:System.Windows.Forms.Layout.LayoutEngine>
- <xref:System.Windows.Forms.Control.LayoutEngine%2A?displayProperty=nameWithType>
