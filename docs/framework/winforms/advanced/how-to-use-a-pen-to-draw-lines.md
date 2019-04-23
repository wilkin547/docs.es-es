---
title: Procedimiento para usar un lápiz para dibujar líneas
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lines [Windows Forms], drawing
- pens [Windows Forms], drawing lines
ms.assetid: 0828c331-a438-4bdd-a4d6-3ef1e59e8795
ms.openlocfilehash: 8b4eb7684e15ffd5b0b528771490ba66f3b7bb45
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59156525"
---
# <a name="how-to-use-a-pen-to-draw-lines"></a><span data-ttu-id="c149c-102">Procedimiento para usar un lápiz para dibujar líneas</span><span class="sxs-lookup"><span data-stu-id="c149c-102">How to: Use a Pen to Draw Lines</span></span>
<span data-ttu-id="c149c-103">Para dibujar líneas, necesita un <xref:System.Drawing.Graphics> objeto y un <xref:System.Drawing.Pen> objeto.</span><span class="sxs-lookup"><span data-stu-id="c149c-103">To draw lines, you need a <xref:System.Drawing.Graphics> object and a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="c149c-104">El <xref:System.Drawing.Graphics> objeto proporciona el <xref:System.Drawing.Graphics.DrawLine%2A> método y el <xref:System.Drawing.Pen> objeto almacena las características de la línea, como el color y ancho.</span><span class="sxs-lookup"><span data-stu-id="c149c-104">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.DrawLine%2A> method, and the <xref:System.Drawing.Pen> object stores features of the line, such as color and width.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c149c-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c149c-105">Example</span></span>  
 <span data-ttu-id="c149c-106">En el ejemplo siguiente se dibuja una línea de (20, 10) a (300, 100).</span><span class="sxs-lookup"><span data-stu-id="c149c-106">The following example draws a line from (20, 10) to (300, 100).</span></span> <span data-ttu-id="c149c-107">La primera instrucción usa la <xref:System.Drawing.Pen.%23ctor%2A> constructor de clase para crear un lápiz negro.</span><span class="sxs-lookup"><span data-stu-id="c149c-107">The first statement uses the <xref:System.Drawing.Pen.%23ctor%2A> class constructor to create a black pen.</span></span> <span data-ttu-id="c149c-108">El argumento que se pasa a la <xref:System.Drawing.Pen.%23ctor%2A> constructor es un <xref:System.Drawing.Color> objeto creado con el <xref:System.Drawing.Color.FromArgb%2A> método.</span><span class="sxs-lookup"><span data-stu-id="c149c-108">The one argument passed to the <xref:System.Drawing.Pen.%23ctor%2A> constructor is a <xref:System.Drawing.Color> object created with the <xref:System.Drawing.Color.FromArgb%2A> method.</span></span> <span data-ttu-id="c149c-109">Los valores utilizados para crear el <xref:System.Drawing.Color> objetos: (255, 0, 0, 0), corresponden a los componentes alfabéticos, rojos, verde y azules del color.</span><span class="sxs-lookup"><span data-stu-id="c149c-109">The values used to create the <xref:System.Drawing.Color> object — (255, 0, 0, 0) — correspond to the alpha, red, green, and blue components of the color.</span></span> <span data-ttu-id="c149c-110">Estos valores definen una pluma de color negro opaco.</span><span class="sxs-lookup"><span data-stu-id="c149c-110">These values define an opaque black pen.</span></span>  
  
 [!code-csharp[System.Drawing.UsingAPen#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingAPen#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c149c-111">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="c149c-111">Compiling the Code</span></span>  
 <span data-ttu-id="c149c-112">El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs>`e`, que es un parámetro del controlador de eventos <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="c149c-112">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c149c-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="c149c-113">See also</span></span>

- <xref:System.Drawing.Pen>
- [<span data-ttu-id="c149c-114">Utilizar lápiz para dibujar líneas y formas</span><span class="sxs-lookup"><span data-stu-id="c149c-114">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
- [<span data-ttu-id="c149c-115">Lápices, líneas y rectángulos en GDI+</span><span class="sxs-lookup"><span data-stu-id="c149c-115">Pens, Lines, and Rectangles in GDI+</span></span>](pens-lines-and-rectangles-in-gdi.md)
