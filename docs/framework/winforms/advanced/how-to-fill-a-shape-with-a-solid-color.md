---
title: Procedimiento para rellenar una forma con un color sólido
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], adding to shapes
- shapes [Windows Forms], filling
ms.assetid: 06088b31-bac9-4ef3-9ebe-06c2c764d6df
ms.openlocfilehash: d6fe7a252029ff80f21d99f7342fabb1d29fbe24
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781295"
---
# <a name="how-to-fill-a-shape-with-a-solid-color"></a><span data-ttu-id="13ffb-102">Procedimiento para rellenar una forma con un color sólido</span><span class="sxs-lookup"><span data-stu-id="13ffb-102">How to: Fill a Shape with a Solid Color</span></span>
<span data-ttu-id="13ffb-103">Para rellenar una forma con un color sólido, cree un <xref:System.Drawing.SolidBrush> objeto y, a continuación, pasar ese <xref:System.Drawing.SolidBrush> objeto como argumento para uno de los métodos de relleno de la <xref:System.Drawing.Graphics> clase.</span><span class="sxs-lookup"><span data-stu-id="13ffb-103">To fill a shape with a solid color, create a <xref:System.Drawing.SolidBrush> object, and then pass that <xref:System.Drawing.SolidBrush> object as an argument to one of the fill methods of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="13ffb-104">El ejemplo siguiente muestra cómo rellenar una elipse con el color rojo.</span><span class="sxs-lookup"><span data-stu-id="13ffb-104">The following example shows how to fill an ellipse with the color red.</span></span>  
  
## <a name="example"></a><span data-ttu-id="13ffb-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="13ffb-105">Example</span></span>  
 <span data-ttu-id="13ffb-106">En el código siguiente, la <xref:System.Drawing.SolidBrush.%23ctor%2A> constructor toma un <xref:System.Drawing.Color> objeto como su único argumento.</span><span class="sxs-lookup"><span data-stu-id="13ffb-106">In the following code, the <xref:System.Drawing.SolidBrush.%23ctor%2A> constructor takes a <xref:System.Drawing.Color> object as its only argument.</span></span> <span data-ttu-id="13ffb-107">Los valores utilizados por el <xref:System.Drawing.Color.FromArgb%2A> método representan los componentes alfabéticos, rojos, verde y azules del color.</span><span class="sxs-lookup"><span data-stu-id="13ffb-107">The values used by the <xref:System.Drawing.Color.FromArgb%2A> method represent the alpha, red, green, and blue components of the color.</span></span> <span data-ttu-id="13ffb-108">Cada uno de estos valores debe estar en el intervalo de 0 a 255.</span><span class="sxs-lookup"><span data-stu-id="13ffb-108">Each of these values must be in the range 0 through 255.</span></span> <span data-ttu-id="13ffb-109">El primer 255 indica que el color es completamente opaco y el segundo 255 indica que el componente rojo es intensidad máxima.</span><span class="sxs-lookup"><span data-stu-id="13ffb-109">The first 255 indicates that the color is fully opaque, and the second 255 indicates that the red component is at full intensity.</span></span> <span data-ttu-id="13ffb-110">Los dos ceros indican que los componentes verde y azul tienen una intensidad de 0.</span><span class="sxs-lookup"><span data-stu-id="13ffb-110">The two zeros indicate that the green and blue components both have an intensity of 0.</span></span>  
  
 <span data-ttu-id="13ffb-111">Los cuatro números (0, 0, 100, 60) pasan a la <xref:System.Drawing.Graphics.FillEllipse%2A> método especificar la ubicación y tamaño del rectángulo delimitador de la elipse.</span><span class="sxs-lookup"><span data-stu-id="13ffb-111">The four numbers (0, 0, 100, 60) passed to the <xref:System.Drawing.Graphics.FillEllipse%2A> method specify the location and size of the bounding rectangle for the ellipse.</span></span> <span data-ttu-id="13ffb-112">El rectángulo tiene una esquina superior izquierda de (0, 0), un ancho de 100 y un alto de 60.</span><span class="sxs-lookup"><span data-stu-id="13ffb-112">The rectangle has an upper-left corner of (0, 0), a width of 100, and a height of 60.</span></span>  
  
 [!code-csharp[System.Drawing.UsingABrush#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingABrush#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="13ffb-113">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="13ffb-113">Compiling the Code</span></span>  
 <span data-ttu-id="13ffb-114">El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de la <xref:System.Windows.Forms.Control.Paint> controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="13ffb-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13ffb-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="13ffb-115">See also</span></span>

- [<span data-ttu-id="13ffb-116">Utilizar un pincel para rellenar formas</span><span class="sxs-lookup"><span data-stu-id="13ffb-116">Using a Brush to Fill Shapes</span></span>](using-a-brush-to-fill-shapes.md)
