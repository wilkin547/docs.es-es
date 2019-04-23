---
title: Procedimiento para rellenar una forma con un patrón de sombreado
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- patterns [Windows Forms], adding to shapes
- shapes [Windows Forms], filling with patterns
- brushes [Windows Forms], using hatch brushes
ms.assetid: 9c8300ff-187b-404f-af1f-ebd499f5b16f
ms.openlocfilehash: f5399c4151b335090f4b93be041375b8c2781afa
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59118123"
---
# <a name="how-to-fill-a-shape-with-a-hatch-pattern"></a><span data-ttu-id="5d7ee-102">Procedimiento para rellenar una forma con un patrón de sombreado</span><span class="sxs-lookup"><span data-stu-id="5d7ee-102">How to: Fill a Shape with a Hatch Pattern</span></span>
<span data-ttu-id="5d7ee-103">Un patrón de trama está formado por dos colores: uno para el fondo y otro para las líneas que forman el modelo sobre el fondo.</span><span class="sxs-lookup"><span data-stu-id="5d7ee-103">A hatch pattern is made from two colors: one for the background and one for the lines that form the pattern over the background.</span></span> <span data-ttu-id="5d7ee-104">Para rellenar una forma cerrada con un patrón de trama, utilice un <xref:System.Drawing.Drawing2D.HatchBrush> objeto.</span><span class="sxs-lookup"><span data-stu-id="5d7ee-104">To fill a closed shape with a hatch pattern, use a <xref:System.Drawing.Drawing2D.HatchBrush> object.</span></span> <span data-ttu-id="5d7ee-105">El ejemplo siguiente muestra cómo rellenar una elipse con un patrón de trama:</span><span class="sxs-lookup"><span data-stu-id="5d7ee-105">The following example demonstrates how to fill an ellipse with a hatch pattern:</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d7ee-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5d7ee-106">Example</span></span>  
 <span data-ttu-id="5d7ee-107">El <xref:System.Drawing.Drawing2D.HatchBrush.%23ctor%2A> constructor toma tres argumentos: el estilo de sombreado, el color de la línea de trama y el color del fondo.</span><span class="sxs-lookup"><span data-stu-id="5d7ee-107">The <xref:System.Drawing.Drawing2D.HatchBrush.%23ctor%2A> constructor takes three arguments: the hatch style, the color of the hatch line, and the color of the background.</span></span> <span data-ttu-id="5d7ee-108">El argumento de estilo de trama puede ser cualquier valor de la <xref:System.Drawing.Drawing2D.HatchStyle> enumeración.</span><span class="sxs-lookup"><span data-stu-id="5d7ee-108">The hatch style argument can be any value from the <xref:System.Drawing.Drawing2D.HatchStyle> enumeration.</span></span> <span data-ttu-id="5d7ee-109">Hay más de cincuenta elementos en el <xref:System.Drawing.Drawing2D.HatchStyle> enumeración; algunos de estos elementos se muestran en la lista siguiente:</span><span class="sxs-lookup"><span data-stu-id="5d7ee-109">There are more than fifty elements in the <xref:System.Drawing.Drawing2D.HatchStyle> enumeration; a few of those elements are shown in the following list:</span></span>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.Horizontal>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.Vertical>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.BackwardDiagonal>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.Cross>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.DiagonalCross>  
  
 <span data-ttu-id="5d7ee-110">La siguiente ilustración muestra la elipse rellena.</span><span class="sxs-lookup"><span data-stu-id="5d7ee-110">The following illustration shows the filled ellipse.</span></span>  
  
 <span data-ttu-id="5d7ee-111">![El patrón de trama](./media/hatch1.png "hatch1")</span><span class="sxs-lookup"><span data-stu-id="5d7ee-111">![Hatch Pattern](./media/hatch1.png "hatch1")</span></span>  
  
 [!code-csharp[System.Drawing.UsingABrush#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.UsingABrush#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5d7ee-112">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="5d7ee-112">Compiling the Code</span></span>  
 <span data-ttu-id="5d7ee-113">El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs>`e`, que es un parámetro del controlador de eventos <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="5d7ee-113">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d7ee-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="5d7ee-114">See also</span></span>

- [<span data-ttu-id="5d7ee-115">Utilizar un pincel para rellenar formas</span><span class="sxs-lookup"><span data-stu-id="5d7ee-115">Using a Brush to Fill Shapes</span></span>](using-a-brush-to-fill-shapes.md)
