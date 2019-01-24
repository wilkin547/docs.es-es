---
title: Procedimiento Establecer el Color de un lápiz
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- pens [Windows Forms], setting color
- colored pens
ms.assetid: a9df06f9-a6d5-4d9b-a2d1-583943540775
ms.openlocfilehash: d0402a7d6bb641ef6d97eb41bc25f3c59b3b4250
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54569445"
---
# <a name="how-to-set-the-color-of-a-pen"></a><span data-ttu-id="b75b7-102">Procedimiento Establecer el Color de un lápiz</span><span class="sxs-lookup"><span data-stu-id="b75b7-102">How to: Set the Color of a Pen</span></span>
<span data-ttu-id="b75b7-103">En este ejemplo se cambia el color de preexistente <xref:System.Drawing.Pen> objeto</span><span class="sxs-lookup"><span data-stu-id="b75b7-103">This example changes the color of a pre-existing <xref:System.Drawing.Pen> object</span></span>  
  
## <a name="example"></a><span data-ttu-id="b75b7-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b75b7-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#9](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#9)]
 [!code-csharp[System.Drawing.ConceptualHowTos#9](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#9)]
 [!code-vb[System.Drawing.ConceptualHowTos#9](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#9)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b75b7-105">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="b75b7-105">Compiling the Code</span></span>  
 <span data-ttu-id="b75b7-106">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="b75b7-106">This example requires:</span></span>  
  
-   <span data-ttu-id="b75b7-107">Un <xref:System.Drawing.Pen> objeto denominado `myPen`.</span><span class="sxs-lookup"><span data-stu-id="b75b7-107">A <xref:System.Drawing.Pen> object named `myPen`.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="b75b7-108">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="b75b7-108">Robust Programming</span></span>  
 <span data-ttu-id="b75b7-109">Debe llamar a <xref:System.Drawing.Pen.Dispose%2A> en los objetos que consumen recursos del sistema (como <xref:System.Drawing.Pen> objetos) cuando haya terminado con ellos.</span><span class="sxs-lookup"><span data-stu-id="b75b7-109">You should call <xref:System.Drawing.Pen.Dispose%2A> on objects that consume system resources (such as <xref:System.Drawing.Pen> objects) after you are finished using them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b75b7-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="b75b7-110">See also</span></span>
- <xref:System.Drawing.Pen>
- [<span data-ttu-id="b75b7-111">Introducción a la programación de gráficos</span><span class="sxs-lookup"><span data-stu-id="b75b7-111">Getting Started with Graphics Programming</span></span>](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)
- [<span data-ttu-id="b75b7-112">Cómo: Crear un lápiz</span><span class="sxs-lookup"><span data-stu-id="b75b7-112">How to: Create a Pen</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)
- [<span data-ttu-id="b75b7-113">Utilizar lápiz para dibujar líneas y formas</span><span class="sxs-lookup"><span data-stu-id="b75b7-113">Using a Pen to Draw Lines and Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
- [<span data-ttu-id="b75b7-114">Lápices, líneas y rectángulos en GDI+</span><span class="sxs-lookup"><span data-stu-id="b75b7-114">Pens, Lines, and Rectangles in GDI+</span></span>](../../../../docs/framework/winforms/advanced/pens-lines-and-rectangles-in-gdi.md)
