---
title: 'Cómo: Establecer el color de un lápiz'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- pens [Windows Forms], setting color
- colored pens
ms.assetid: a9df06f9-a6d5-4d9b-a2d1-583943540775
ms.openlocfilehash: 37bc289fa1eeb7ef5510474dff062ae76be5fc65
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33522387"
---
# <a name="how-to-set-the-color-of-a-pen"></a><span data-ttu-id="1cd8f-102">Cómo: Establecer el color de un lápiz</span><span class="sxs-lookup"><span data-stu-id="1cd8f-102">How to: Set the Color of a Pen</span></span>
<span data-ttu-id="1cd8f-103">Este ejemplo cambia el color de preexistente <xref:System.Drawing.Pen> objeto</span><span class="sxs-lookup"><span data-stu-id="1cd8f-103">This example changes the color of a pre-existing <xref:System.Drawing.Pen> object</span></span>  
  
## <a name="example"></a><span data-ttu-id="1cd8f-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1cd8f-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#9](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#9)]
 [!code-csharp[System.Drawing.ConceptualHowTos#9](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#9)]
 [!code-vb[System.Drawing.ConceptualHowTos#9](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#9)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="1cd8f-105">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="1cd8f-105">Compiling the Code</span></span>  
 <span data-ttu-id="1cd8f-106">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="1cd8f-106">This example requires:</span></span>  
  
-   <span data-ttu-id="1cd8f-107">A <xref:System.Drawing.Pen> objeto denominado `myPen`.</span><span class="sxs-lookup"><span data-stu-id="1cd8f-107">A <xref:System.Drawing.Pen> object named `myPen`.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="1cd8f-108">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="1cd8f-108">Robust Programming</span></span>  
 <span data-ttu-id="1cd8f-109">Debe llamar a <xref:System.Drawing.Pen.Dispose%2A> en los objetos que consumen recursos del sistema (como <xref:System.Drawing.Pen> objetos) cuando haya terminado de usarlos.</span><span class="sxs-lookup"><span data-stu-id="1cd8f-109">You should call <xref:System.Drawing.Pen.Dispose%2A> on objects that consume system resources (such as <xref:System.Drawing.Pen> objects) after you are finished using them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cd8f-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="1cd8f-110">See Also</span></span>  
 <xref:System.Drawing.Pen>  
 [<span data-ttu-id="1cd8f-111">Introducción a la programación de gráficos</span><span class="sxs-lookup"><span data-stu-id="1cd8f-111">Getting Started with Graphics Programming</span></span>](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)  
 [<span data-ttu-id="1cd8f-112">Crear un lápiz</span><span class="sxs-lookup"><span data-stu-id="1cd8f-112">How to: Create a Pen</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)  
 [<span data-ttu-id="1cd8f-113">Utilizar lápiz para dibujar líneas y formas</span><span class="sxs-lookup"><span data-stu-id="1cd8f-113">Using a Pen to Draw Lines and Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)  
 [<span data-ttu-id="1cd8f-114">Lápices, líneas y rectángulos en GDI+</span><span class="sxs-lookup"><span data-stu-id="1cd8f-114">Pens, Lines, and Rectangles in GDI+</span></span>](../../../../docs/framework/winforms/advanced/pens-lines-and-rectangles-in-gdi.md)
