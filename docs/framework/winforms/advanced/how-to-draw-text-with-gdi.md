---
title: 'Cómo: Dibujar texto con GDI'
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
ms.openlocfilehash: e18ff96ea97eb636de8ab73aaa094c07b10fd456
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33522920"
---
# <a name="how-to-draw-text-with-gdi"></a><span data-ttu-id="32602-102">Cómo: Dibujar texto con GDI</span><span class="sxs-lookup"><span data-stu-id="32602-102">How to: Draw Text with GDI</span></span>
<span data-ttu-id="32602-103">Con el <xref:System.Windows.Forms.TextRenderer.DrawText%2A> método en el <xref:System.Windows.Forms.TextRenderer> (clase), puede tener acceso a [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] funcionalidad para dibujar texto en un formulario o control.</span><span class="sxs-lookup"><span data-stu-id="32602-103">With the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> method in the <xref:System.Windows.Forms.TextRenderer> class, you can access [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] functionality for drawing text on a form or control.</span></span> [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]<span data-ttu-id="32602-104"> representación de texto normalmente ofrece un mejor rendimiento y una medida de texto más preciso [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span><span class="sxs-lookup"><span data-stu-id="32602-104"> text rendering typically offers better performance and more accurate text measuring than [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="32602-105">El <xref:System.Windows.Forms.TextRenderer.DrawText%2A> métodos de la <xref:System.Windows.Forms.TextRenderer> clase no se admiten para la impresión.</span><span class="sxs-lookup"><span data-stu-id="32602-105">The <xref:System.Windows.Forms.TextRenderer.DrawText%2A> methods of the <xref:System.Windows.Forms.TextRenderer> class are not supported for printing.</span></span> <span data-ttu-id="32602-106">Al imprimir, utilice siempre la <xref:System.Drawing.Graphics.DrawString%2A> métodos de la <xref:System.Drawing.Graphics> clase.</span><span class="sxs-lookup"><span data-stu-id="32602-106">When printing, always use the <xref:System.Drawing.Graphics.DrawString%2A> methods of the <xref:System.Drawing.Graphics> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="32602-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="32602-107">Example</span></span>  
 <span data-ttu-id="32602-108">En el ejemplo de código siguiente se muestra cómo dibujar texto en varias líneas dentro de un rectángulo utilizando el <xref:System.Windows.Forms.TextRenderer.DrawText%2A> método.</span><span class="sxs-lookup"><span data-stu-id="32602-108">The following code example demonstrates how to draw text on multiple lines within a rectangle using the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> method.</span></span>  
  
 [!code-csharp[System.Windows.Forms.TextRendererExamples#7](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TextRendererExamples/CS/Form1.cs#7)]
 [!code-vb[System.Windows.Forms.TextRendererExamples#7](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TextRendererExamples/VB/Form1.vb#7)]  
  
 <span data-ttu-id="32602-109">Para representar texto con la <xref:System.Windows.Forms.TextRenderer> (clase), necesita un <xref:System.Drawing.IDeviceContext>, como un <xref:System.Drawing.Graphics> y un <xref:System.Drawing.Font>, una ubicación para dibujar el texto y el color en el que se debe dibujar.</span><span class="sxs-lookup"><span data-stu-id="32602-109">To render text with the <xref:System.Windows.Forms.TextRenderer> class, you need an <xref:System.Drawing.IDeviceContext>, such as a <xref:System.Drawing.Graphics> and a <xref:System.Drawing.Font>, a location to draw the text, and the color in which it should be drawn.</span></span> <span data-ttu-id="32602-110">Si lo desea, puede especificar el texto con formato mediante el uso de la <xref:System.Windows.Forms.TextFormatFlags> enumeración.</span><span class="sxs-lookup"><span data-stu-id="32602-110">Optionally, you can specify the text formatting by using the <xref:System.Windows.Forms.TextFormatFlags> enumeration.</span></span>  
  
 <span data-ttu-id="32602-111">Para obtener más información acerca de cómo obtener un <xref:System.Drawing.Graphics>, consulte [Cómo: crear objetos Graphics para dibujar](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md).</span><span class="sxs-lookup"><span data-stu-id="32602-111">For more information about obtaining a <xref:System.Drawing.Graphics>, see [How to: Create Graphics Objects for Drawing](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md).</span></span> <span data-ttu-id="32602-112">Para obtener más información sobre cómo generar un <xref:System.Drawing.Font>, consulte [Cómo: construir fuentes y familias de fuentes](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md).</span><span class="sxs-lookup"><span data-stu-id="32602-112">For more information about constructing a <xref:System.Drawing.Font>, see [How to: Construct Font Families and Fonts](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="32602-113">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="32602-113">Compiling the Code</span></span>  
 <span data-ttu-id="32602-114">El ejemplo de código anterior está diseñado para su uso con Windows Forms y requiere el <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="32602-114">The preceding code example is designed for use with Windows Forms, and it requires the <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32602-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="32602-115">See Also</span></span>  
 <xref:System.Windows.Forms.TextRenderer>  
 <xref:System.Drawing.Font>  
 <xref:System.Drawing.Color>  
 <xref:System.Drawing.Color>  
 [<span data-ttu-id="32602-116">Utilizar fuentes y texto</span><span class="sxs-lookup"><span data-stu-id="32602-116">Using Fonts and Text</span></span>](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
