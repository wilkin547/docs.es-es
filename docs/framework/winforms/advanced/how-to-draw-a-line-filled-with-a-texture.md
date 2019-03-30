---
title: Filtrar Dibujar una línea rellenada con una textura
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drawing [Windows Forms], lines
- lines [Windows Forms], texture
- drawing lines [Windows Forms], texture
ms.assetid: dc9118cc-f3c2-42e5-8173-f46d41d18fd5
ms.openlocfilehash: 82fc553e2a2fc9d1e8161c0f0dfef9190668e48c
ms.sourcegitcommit: 15ab532fd5e1f8073a4b678922d93b68b521bfa0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/29/2019
ms.locfileid: "58653761"
---
# <a name="how-to-draw-a-line-filled-with-a-texture"></a><span data-ttu-id="326e1-102">Filtrar Dibujar una línea rellenada con una textura</span><span class="sxs-lookup"><span data-stu-id="326e1-102">How to: Draw a Line Filled with a Texture</span></span>
<span data-ttu-id="326e1-103">En lugar de dibujar una línea con un color sólido, puede dibujar una línea con una textura.</span><span class="sxs-lookup"><span data-stu-id="326e1-103">Instead of drawing a line with a solid color, you can draw a line with a texture.</span></span> <span data-ttu-id="326e1-104">Para dibujar líneas y curvas con una textura, cree un <xref:System.Drawing.TextureBrush> de objetos y pasar ese <xref:System.Drawing.TextureBrush> objeto a un <xref:System.Drawing.Pen.%23ctor%2A> constructor.</span><span class="sxs-lookup"><span data-stu-id="326e1-104">To draw lines and curves with a texture, create a <xref:System.Drawing.TextureBrush> object, and pass that <xref:System.Drawing.TextureBrush> object to a <xref:System.Drawing.Pen.%23ctor%2A> constructor.</span></span> <span data-ttu-id="326e1-105">El mapa de bits asociado con el pincel de textura se usa para el plano de mosaico (de manera invisible) y, cuando el lápiz dibuja una línea o curva, el trazo del lápiz revela ciertas píxeles de la textura en mosaico.</span><span class="sxs-lookup"><span data-stu-id="326e1-105">The bitmap associated with the texture brush is used to tile the plane (invisibly), and when the pen draws a line or curve, the stroke of the pen uncovers certain pixels of the tiled texture.</span></span>  
  
## <a name="example"></a><span data-ttu-id="326e1-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="326e1-106">Example</span></span>  
 <span data-ttu-id="326e1-107">En el ejemplo siguiente se crea un <xref:System.Drawing.Bitmap> objeto desde el archivo `Texture1.jpg`.</span><span class="sxs-lookup"><span data-stu-id="326e1-107">The following example creates a <xref:System.Drawing.Bitmap> object from the file `Texture1.jpg`.</span></span> <span data-ttu-id="326e1-108">Ese mapa de bits se usa para construir un <xref:System.Drawing.TextureBrush> objeto y el <xref:System.Drawing.TextureBrush> objeto se usa para construir un <xref:System.Drawing.Pen> objeto.</span><span class="sxs-lookup"><span data-stu-id="326e1-108">That bitmap is used to construct a <xref:System.Drawing.TextureBrush> object, and the <xref:System.Drawing.TextureBrush> object is used to construct a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="326e1-109">La llamada a <xref:System.Drawing.Graphics.DrawImage%2A> dibuja el mapa de bits con la esquina superior izquierda en (0, 0).</span><span class="sxs-lookup"><span data-stu-id="326e1-109">The call to <xref:System.Drawing.Graphics.DrawImage%2A> draws the bitmap with its upper-left corner at (0, 0).</span></span> <span data-ttu-id="326e1-110">La llamada a <xref:System.Drawing.Graphics.DrawEllipse%2A> usa el <xref:System.Drawing.Pen> objeto para dibujar una elipse con textura.</span><span class="sxs-lookup"><span data-stu-id="326e1-110">The call to <xref:System.Drawing.Graphics.DrawEllipse%2A> uses the <xref:System.Drawing.Pen> object to draw a textured ellipse.</span></span>  
  
 <span data-ttu-id="326e1-111">La siguiente ilustración muestra el mapa de bits y la elipse:</span><span class="sxs-lookup"><span data-stu-id="326e1-111">The following illustration shows the bitmap and the textured ellipse:</span></span>  
  
 ![Captura de pantalla que muestra el mapa de bits y la elipse.](./media/how-to-draw-a-line-filled-with-a-texture/bitmap-textured-ellipse.png)  
  
 [!code-csharp[System.Drawing.UsingAPen#61](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.UsingAPen#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="326e1-113">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="326e1-113">Compiling the Code</span></span>  
 <span data-ttu-id="326e1-114">Crear un formulario de Windows y controlar el formato <xref:System.Windows.Forms.Control.Paint> eventos.</span><span class="sxs-lookup"><span data-stu-id="326e1-114">Create a Windows Form and handle the form's <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="326e1-115">Pegue el código anterior en el <xref:System.Windows.Forms.Control.Paint> controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="326e1-115">Paste the preceding code into the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="326e1-116">Reemplace `Texture.jpg` con una imagen válida en su sistema.</span><span class="sxs-lookup"><span data-stu-id="326e1-116">Replace `Texture.jpg` with an image valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="326e1-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="326e1-117">See also</span></span>
- [<span data-ttu-id="326e1-118">Utilizar lápiz para dibujar líneas y formas</span><span class="sxs-lookup"><span data-stu-id="326e1-118">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
- [<span data-ttu-id="326e1-119">Gráficos y dibujos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="326e1-119">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
