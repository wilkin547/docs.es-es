---
title: Filtrar Crear figuras a partir de líneas, curvas y formas
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- figures [Windows Forms], creating from shapes
- figures [Windows Forms], creating from lines
ms.assetid: 82fd56c7-b443-4765-9b7c-62ce030656ec
ms.openlocfilehash: 1977f1c9efe2c379ef6039870aade300efca2bdd
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57709502"
---
# <a name="how-to-create-figures-from-lines-curves-and-shapes"></a><span data-ttu-id="8c5e2-102">Filtrar Crear figuras a partir de líneas, curvas y formas</span><span class="sxs-lookup"><span data-stu-id="8c5e2-102">How to: Create Figures from Lines, Curves, and Shapes</span></span>
<span data-ttu-id="8c5e2-103">Para crear una figura, construya un <xref:System.Drawing.Drawing2D.GraphicsPath>y, a continuación, llamar a métodos, como <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> y <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A>, para agregar tipos primitivos para la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="8c5e2-103">To create a figure, construct a <xref:System.Drawing.Drawing2D.GraphicsPath>, and then call methods, such as <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> and <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A>, to add primitives to the path.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8c5e2-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8c5e2-104">Example</span></span>  
 <span data-ttu-id="8c5e2-105">Los siguientes ejemplos de código crean rutas de acceso que tienen las cifras:</span><span class="sxs-lookup"><span data-stu-id="8c5e2-105">The following code examples create paths that have figures:</span></span>  
  
-   <span data-ttu-id="8c5e2-106">El primer ejemplo crea una ruta de acceso que tiene una sola figura.</span><span class="sxs-lookup"><span data-stu-id="8c5e2-106">The first example creates a path that has a single figure.</span></span> <span data-ttu-id="8c5e2-107">La figura consta de un único arco. El arco tiene un ángulo de barrido de-180 grados, que está a la izquierda en el sistema de coordenadas predeterminado.</span><span class="sxs-lookup"><span data-stu-id="8c5e2-107">The figure consists of a single arc. The arc has a sweep angle of –180 degrees, which is counterclockwise in the default coordinate system.</span></span>  
  
-   <span data-ttu-id="8c5e2-108">El segundo ejemplo crea una ruta de acceso que tiene dos figuras.</span><span class="sxs-lookup"><span data-stu-id="8c5e2-108">The second example creates a path that has two figures.</span></span> <span data-ttu-id="8c5e2-109">La primera figura es un arco seguido por una línea.</span><span class="sxs-lookup"><span data-stu-id="8c5e2-109">The first figure is an arc followed by a line.</span></span> <span data-ttu-id="8c5e2-110">La segunda figura es una línea seguida de una curva seguida de una línea.</span><span class="sxs-lookup"><span data-stu-id="8c5e2-110">The second figure is a line followed by a curve followed by a line.</span></span> <span data-ttu-id="8c5e2-111">La primera figura está abierta, y la segunda figura está cerrada.</span><span class="sxs-lookup"><span data-stu-id="8c5e2-111">The first figure is left open, and the second figure is closed.</span></span>  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#21)]  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#22)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8c5e2-112">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="8c5e2-112">Compiling the Code</span></span>  
 <span data-ttu-id="8c5e2-113">Los ejemplos anteriores están diseñados para su uso con Windows Forms y necesitan <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de la <xref:System.Windows.Forms.Control.Paint> controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="8c5e2-113">The previous examples are designed for use with Windows Forms, and they require <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c5e2-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="8c5e2-114">See also</span></span>
- <xref:System.Drawing.Drawing2D.GraphicsPath>
- [<span data-ttu-id="8c5e2-115">Crear y dibujar trazados</span><span class="sxs-lookup"><span data-stu-id="8c5e2-115">Constructing and Drawing Paths</span></span>](constructing-and-drawing-paths.md)
- [<span data-ttu-id="8c5e2-116">Utilizar lápiz para dibujar líneas y formas</span><span class="sxs-lookup"><span data-stu-id="8c5e2-116">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
