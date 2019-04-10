---
title: Filtrar para crear un pincel sólido
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- solid color brushes
- brushes [Windows Forms], examples
- brushes [Windows Forms], creating solid
ms.assetid: 85c3fe7d-fb1d-4591-8a9f-d75b556b90af
ms.openlocfilehash: ed9ec1f52b41c83b3cc6e36dedf97f1c00db42e6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59213446"
---
# <a name="how-to-create-a-solid-brush"></a><span data-ttu-id="a4acd-102">Filtrar para crear un pincel sólido</span><span class="sxs-lookup"><span data-stu-id="a4acd-102">How to: Create a Solid Brush</span></span>
<span data-ttu-id="a4acd-103">Este ejemplo se crea un <xref:System.Drawing.SolidBrush> objeto que puede utilizarse por un <xref:System.Drawing.Graphics> objeto para rellenar formas.</span><span class="sxs-lookup"><span data-stu-id="a4acd-103">This example creates a <xref:System.Drawing.SolidBrush> object that can be used by a <xref:System.Drawing.Graphics> object for filling shapes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a4acd-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a4acd-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#1)]
 [!code-csharp[System.Drawing.ConceptualHowTos#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#1)]
 [!code-vb[System.Drawing.ConceptualHowTos#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#1)]  
  
## <a name="robust-programming"></a><span data-ttu-id="a4acd-105">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="a4acd-105">Robust Programming</span></span>  
 <span data-ttu-id="a4acd-106">Cuando haya terminado de usarlos, debe llamar a <xref:System.IDisposable.Dispose%2A> en objetos que consuman recursos del sistema, como los objetos de pincel.</span><span class="sxs-lookup"><span data-stu-id="a4acd-106">After you have finished using them, you should call <xref:System.IDisposable.Dispose%2A> on objects that consume system resources, such as brush objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4acd-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="a4acd-107">See also</span></span>

- <xref:System.Drawing.SolidBrush>
- <xref:System.Drawing.Brush>
- [<span data-ttu-id="a4acd-108">Introducción a la programación de gráficos</span><span class="sxs-lookup"><span data-stu-id="a4acd-108">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="a4acd-109">Pinceles y formas rellenas en GDI+</span><span class="sxs-lookup"><span data-stu-id="a4acd-109">Brushes and Filled Shapes in GDI+</span></span>](brushes-and-filled-shapes-in-gdi.md)
- [<span data-ttu-id="a4acd-110">Utilizar un pincel para rellenar formas</span><span class="sxs-lookup"><span data-stu-id="a4acd-110">Using a Brush to Fill Shapes</span></span>](using-a-brush-to-fill-shapes.md)
