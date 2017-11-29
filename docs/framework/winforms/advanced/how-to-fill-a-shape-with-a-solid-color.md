---
title: "Cómo: Rellenar una forma con un color sólido"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], adding to shapes
- shapes [Windows Forms], filling
ms.assetid: 06088b31-bac9-4ef3-9ebe-06c2c764d6df
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: eb3e160392a903083386d9942f8e2cfe31ee89a4
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-fill-a-shape-with-a-solid-color"></a><span data-ttu-id="22998-102">Cómo: Rellenar una forma con un color sólido</span><span class="sxs-lookup"><span data-stu-id="22998-102">How to: Fill a Shape with a Solid Color</span></span>
<span data-ttu-id="22998-103">Para rellenar una forma con un color sólido, cree un <xref:System.Drawing.SolidBrush> objeto y, a continuación, pasar ese <xref:System.Drawing.SolidBrush> objeto como argumento a uno de los métodos de relleno de la <xref:System.Drawing.Graphics> clase.</span><span class="sxs-lookup"><span data-stu-id="22998-103">To fill a shape with a solid color, create a <xref:System.Drawing.SolidBrush> object, and then pass that <xref:System.Drawing.SolidBrush> object as an argument to one of the fill methods of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="22998-104">En el ejemplo siguiente se muestra cómo rellenar una elipse con el color rojo.</span><span class="sxs-lookup"><span data-stu-id="22998-104">The following example shows how to fill an ellipse with the color red.</span></span>  
  
## <a name="example"></a><span data-ttu-id="22998-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="22998-105">Example</span></span>  
 <span data-ttu-id="22998-106">En el código siguiente, la <xref:System.Drawing.SolidBrush.%23ctor%2A> constructor toma un <xref:System.Drawing.Color> objeto como su único argumento.</span><span class="sxs-lookup"><span data-stu-id="22998-106">In the following code, the <xref:System.Drawing.SolidBrush.%23ctor%2A> constructor takes a <xref:System.Drawing.Color> object as its only argument.</span></span> <span data-ttu-id="22998-107">Los valores utilizados por la <xref:System.Drawing.Color.FromArgb%2A> método representan los componentes alfabéticos, rojos, verde y azules del color.</span><span class="sxs-lookup"><span data-stu-id="22998-107">The values used by the <xref:System.Drawing.Color.FromArgb%2A> method represent the alpha, red, green, and blue components of the color.</span></span> <span data-ttu-id="22998-108">Cada uno de estos valores debe estar en el intervalo comprendido entre 0 y 255.</span><span class="sxs-lookup"><span data-stu-id="22998-108">Each of these values must be in the range 0 through 255.</span></span> <span data-ttu-id="22998-109">El primer 255 indica que el color es completamente opaco y el segundo 255 indica que el componente rojo tiene intensidad máxima.</span><span class="sxs-lookup"><span data-stu-id="22998-109">The first 255 indicates that the color is fully opaque, and the second 255 indicates that the red component is at full intensity.</span></span> <span data-ttu-id="22998-110">Los dos ceros indican que los componentes verde y azules tienen una intensidad de 0.</span><span class="sxs-lookup"><span data-stu-id="22998-110">The two zeros indicate that the green and blue components both have an intensity of 0.</span></span>  
  
 <span data-ttu-id="22998-111">Los cuatro números (0, 0, 100, 60) que se pasan a la <xref:System.Drawing.Graphics.FillEllipse%2A> método especificar la ubicación y el tamaño del rectángulo delimitador de la elipse.</span><span class="sxs-lookup"><span data-stu-id="22998-111">The four numbers (0, 0, 100, 60) passed to the <xref:System.Drawing.Graphics.FillEllipse%2A> method specify the location and size of the bounding rectangle for the ellipse.</span></span> <span data-ttu-id="22998-112">El rectángulo tiene una esquina superior izquierda de (0, 0), un ancho de 100 y un alto de 60.</span><span class="sxs-lookup"><span data-stu-id="22998-112">The rectangle has an upper-left corner of (0, 0), a width of 100, and a height of 60.</span></span>  
  
 [!code-csharp[System.Drawing.UsingABrush#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingABrush#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="22998-113">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="22998-113">Compiling the Code</span></span>  
 <span data-ttu-id="22998-114">El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro del controlador de eventos <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="22998-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22998-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="22998-115">See Also</span></span>  
 [<span data-ttu-id="22998-116">Utilizar un pincel para rellenar formas</span><span class="sxs-lookup"><span data-stu-id="22998-116">Using a Brush to Fill Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)
