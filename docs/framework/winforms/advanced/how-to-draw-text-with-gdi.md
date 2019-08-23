---
title: Procedimiento para dibujar texto con GDI
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- GDI [Windows Forms], drawing text [Windows Forms]
- text [Windows Forms], drawing with TextRenderer
- drawing [Windows Forms], text
- Windows Forms, drawing text with GDI
ms.assetid: 2a19fe5d-2ace-451c-94db-01cb1118ef7b
ms.openlocfilehash: 3ed2b5c94e4a38a5873a34e61287c4038cab5cbb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956539"
---
# <a name="how-to-draw-text-with-gdi"></a><span data-ttu-id="a1240-102">Procedimiento para dibujar texto con GDI</span><span class="sxs-lookup"><span data-stu-id="a1240-102">How to: Draw Text with GDI</span></span>
<span data-ttu-id="a1240-103">Con el <xref:System.Windows.Forms.TextRenderer.DrawText%2A> método en la <xref:System.Windows.Forms.TextRenderer> clase, puede tener acceso a la funcionalidad de GDI para dibujar texto en un formulario o control.</span><span class="sxs-lookup"><span data-stu-id="a1240-103">With the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> method in the <xref:System.Windows.Forms.TextRenderer> class, you can access GDI functionality for drawing text on a form or control.</span></span> <span data-ttu-id="a1240-104">La representación de texto GDI suele ofrecer un mejor rendimiento y una medida de texto más precisa que GDI+.</span><span class="sxs-lookup"><span data-stu-id="a1240-104">GDI text rendering typically offers better performance and more accurate text measuring than GDI+.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a1240-105">No <xref:System.Windows.Forms.TextRenderer.DrawText%2A> se admiten <xref:System.Windows.Forms.TextRenderer> los métodos de la clase para imprimir.</span><span class="sxs-lookup"><span data-stu-id="a1240-105">The <xref:System.Windows.Forms.TextRenderer.DrawText%2A> methods of the <xref:System.Windows.Forms.TextRenderer> class are not supported for printing.</span></span> <span data-ttu-id="a1240-106">Al imprimir, use siempre los <xref:System.Drawing.Graphics.DrawString%2A> métodos de la <xref:System.Drawing.Graphics> clase.</span><span class="sxs-lookup"><span data-stu-id="a1240-106">When printing, always use the <xref:System.Drawing.Graphics.DrawString%2A> methods of the <xref:System.Drawing.Graphics> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a1240-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a1240-107">Example</span></span>  
 <span data-ttu-id="a1240-108">En el ejemplo de código siguiente se muestra cómo dibujar texto en varias líneas dentro de un <xref:System.Windows.Forms.TextRenderer.DrawText%2A> rectángulo mediante el método.</span><span class="sxs-lookup"><span data-stu-id="a1240-108">The following code example demonstrates how to draw text on multiple lines within a rectangle using the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> method.</span></span>  
  
 [!code-csharp[System.Windows.Forms.TextRendererExamples#7](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TextRendererExamples/CS/Form1.cs#7)]
 [!code-vb[System.Windows.Forms.TextRendererExamples#7](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TextRendererExamples/VB/Form1.vb#7)]  
  
 <span data-ttu-id="a1240-109">Para representar texto con la <xref:System.Windows.Forms.TextRenderer> clase, se necesita un <xref:System.Drawing.IDeviceContext>, <xref:System.Drawing.Font>como <xref:System.Drawing.Graphics> y, una ubicación para dibujar el texto y el color en el que se debe dibujar.</span><span class="sxs-lookup"><span data-stu-id="a1240-109">To render text with the <xref:System.Windows.Forms.TextRenderer> class, you need an <xref:System.Drawing.IDeviceContext>, such as a <xref:System.Drawing.Graphics> and a <xref:System.Drawing.Font>, a location to draw the text, and the color in which it should be drawn.</span></span> <span data-ttu-id="a1240-110">Opcionalmente, puede especificar el formato de texto mediante la <xref:System.Windows.Forms.TextFormatFlags> enumeración.</span><span class="sxs-lookup"><span data-stu-id="a1240-110">Optionally, you can specify the text formatting by using the <xref:System.Windows.Forms.TextFormatFlags> enumeration.</span></span>  
  
 <span data-ttu-id="a1240-111">Para obtener más información acerca de <xref:System.Drawing.Graphics>cómo obtener [una, consulte Cómo: Crear objetos gráficos para dibujar](how-to-create-graphics-objects-for-drawing.md).</span><span class="sxs-lookup"><span data-stu-id="a1240-111">For more information about obtaining a <xref:System.Drawing.Graphics>, see [How to: Create Graphics Objects for Drawing](how-to-create-graphics-objects-for-drawing.md).</span></span> <span data-ttu-id="a1240-112">Para obtener más información acerca de cómo <xref:System.Drawing.Font>crear un [, consulte Cómo: Construya familias y fuentes](how-to-construct-font-families-and-fonts.md)de fuentes.</span><span class="sxs-lookup"><span data-stu-id="a1240-112">For more information about constructing a <xref:System.Drawing.Font>, see [How to: Construct Font Families and Fonts](how-to-construct-font-families-and-fonts.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a1240-113">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="a1240-113">Compiling the Code</span></span>  
 <span data-ttu-id="a1240-114">El ejemplo de código anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="a1240-114">The preceding code example is designed for use with Windows Forms, and it requires the <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1240-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="a1240-115">See also</span></span>

- <xref:System.Windows.Forms.TextRenderer>
- <xref:System.Drawing.Font>
- <xref:System.Drawing.Color>
- [<span data-ttu-id="a1240-116">Utilizar fuentes y texto</span><span class="sxs-lookup"><span data-stu-id="a1240-116">Using Fonts and Text</span></span>](using-fonts-and-text.md)
