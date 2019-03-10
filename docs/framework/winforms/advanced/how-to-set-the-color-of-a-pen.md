---
title: Filtrar Establecer el Color de un lápiz
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- pens [Windows Forms], setting color
- colored pens
ms.assetid: a9df06f9-a6d5-4d9b-a2d1-583943540775
ms.openlocfilehash: a2645112950be88cbc569e0be7889c0f1019223d
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57710395"
---
# <a name="how-to-set-the-color-of-a-pen"></a><span data-ttu-id="a5e13-102">Procedimiento Establecer el Color de un lápiz</span><span class="sxs-lookup"><span data-stu-id="a5e13-102">How to: Set the Color of a Pen</span></span>
<span data-ttu-id="a5e13-103">En este ejemplo se cambia el color de preexistente <xref:System.Drawing.Pen> objeto</span><span class="sxs-lookup"><span data-stu-id="a5e13-103">This example changes the color of a pre-existing <xref:System.Drawing.Pen> object</span></span>  
  
## <a name="example"></a><span data-ttu-id="a5e13-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a5e13-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#9](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#9)]
 [!code-csharp[System.Drawing.ConceptualHowTos#9](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#9)]
 [!code-vb[System.Drawing.ConceptualHowTos#9](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#9)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a5e13-105">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="a5e13-105">Compiling the Code</span></span>  
 <span data-ttu-id="a5e13-106">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="a5e13-106">This example requires:</span></span>  
  
-   <span data-ttu-id="a5e13-107">Un <xref:System.Drawing.Pen> objeto denominado `myPen`.</span><span class="sxs-lookup"><span data-stu-id="a5e13-107">A <xref:System.Drawing.Pen> object named `myPen`.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="a5e13-108">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="a5e13-108">Robust Programming</span></span>  
 <span data-ttu-id="a5e13-109">Debe llamar a <xref:System.Drawing.Pen.Dispose%2A> en los objetos que consumen recursos del sistema (como <xref:System.Drawing.Pen> objetos) cuando haya terminado con ellos.</span><span class="sxs-lookup"><span data-stu-id="a5e13-109">You should call <xref:System.Drawing.Pen.Dispose%2A> on objects that consume system resources (such as <xref:System.Drawing.Pen> objects) after you are finished using them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5e13-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="a5e13-110">See also</span></span>
- <xref:System.Drawing.Pen>
- [<span data-ttu-id="a5e13-111">Introducción a la programación de gráficos</span><span class="sxs-lookup"><span data-stu-id="a5e13-111">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="a5e13-112">Cómo: Crear un lápiz</span><span class="sxs-lookup"><span data-stu-id="a5e13-112">How to: Create a Pen</span></span>](how-to-create-a-pen.md)
- [<span data-ttu-id="a5e13-113">Utilizar lápiz para dibujar líneas y formas</span><span class="sxs-lookup"><span data-stu-id="a5e13-113">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
- [<span data-ttu-id="a5e13-114">Lápices, líneas y rectángulos en GDI+</span><span class="sxs-lookup"><span data-stu-id="a5e13-114">Pens, Lines, and Rectangles in GDI+</span></span>](pens-lines-and-rectangles-in-gdi.md)
