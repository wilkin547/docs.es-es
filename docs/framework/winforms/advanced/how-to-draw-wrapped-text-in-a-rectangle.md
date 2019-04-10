---
title: Filtrar para dibujar texto ajustado en un rectángulo
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, drawing text in a rectangle
- text [Windows Forms], drawing in a rectangle
- strings [Windows Forms], drawing in a rectangle
ms.assetid: e1fb432a-dc90-48b5-9b6b-acc14507133d
ms.openlocfilehash: 8e5c7cab1f977bef0570b2e540d7bf3a630aceb0
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59301934"
---
# <a name="how-to-draw-wrapped-text-in-a-rectangle"></a><span data-ttu-id="dedde-102">Filtrar para dibujar texto ajustado en un rectángulo</span><span class="sxs-lookup"><span data-stu-id="dedde-102">How to: Draw Wrapped Text in a Rectangle</span></span>
<span data-ttu-id="dedde-103">Puede dibujar texto ajustado en un rectángulo mediante el uso de la <xref:System.Drawing.Graphics.DrawString%2A> sobrecargar el método de la <xref:System.Drawing.Graphics> clases que toman un <xref:System.Drawing.Rectangle> o <xref:System.Drawing.RectangleF> parámetro.</span><span class="sxs-lookup"><span data-stu-id="dedde-103">You can draw wrapped text in a rectangle by using the <xref:System.Drawing.Graphics.DrawString%2A> overloaded method of the <xref:System.Drawing.Graphics> class that takes a <xref:System.Drawing.Rectangle> or <xref:System.Drawing.RectangleF> parameter.</span></span> <span data-ttu-id="dedde-104">También se puede utilizar un <xref:System.Drawing.Brush> y un <xref:System.Drawing.Font>.</span><span class="sxs-lookup"><span data-stu-id="dedde-104">You will also use a <xref:System.Drawing.Brush> and a <xref:System.Drawing.Font>.</span></span>  
  
 <span data-ttu-id="dedde-105">También puede dibujar texto ajustado en un rectángulo mediante el uso de la <xref:System.Windows.Forms.TextRenderer.DrawText%2A> sobrecargar el método de la <xref:System.Windows.Forms.TextRenderer> que toma un <xref:System.Drawing.Rectangle> y un <xref:System.Windows.Forms.TextFormatFlags> parámetro.</span><span class="sxs-lookup"><span data-stu-id="dedde-105">You can also draw wrapped text in a rectangle by using the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> overloaded method of the <xref:System.Windows.Forms.TextRenderer> that takes a <xref:System.Drawing.Rectangle> and a <xref:System.Windows.Forms.TextFormatFlags> parameter.</span></span> <span data-ttu-id="dedde-106">También se puede utilizar un <xref:System.Drawing.Color> y un <xref:System.Drawing.Font>.</span><span class="sxs-lookup"><span data-stu-id="dedde-106">You will also use a <xref:System.Drawing.Color> and a <xref:System.Drawing.Font>.</span></span>  
  
 <span data-ttu-id="dedde-107">La siguiente ilustración muestra el resultado del texto dibujado en el rectángulo, cuando se usa el <xref:System.Drawing.Graphics.DrawString%2A> método:</span><span class="sxs-lookup"><span data-stu-id="dedde-107">The following illustration shows the output of text drawn in the rectangle when you use the <xref:System.Drawing.Graphics.DrawString%2A> method:</span></span>
  
 ![Captura de pantalla que muestra el resultado cuando se usa el método DrawString.](./media/how-to-draw-wrapped-text-in-a-rectangle/drawstring-method-font-text.png)  
  
### <a name="to-draw-wrapped-text-in-a-rectangle-with-gdi"></a><span data-ttu-id="dedde-109">Para dibujar texto ajustado en un rectángulo con GDI +</span><span class="sxs-lookup"><span data-stu-id="dedde-109">To draw wrapped text in a rectangle with GDI+</span></span>  
  
1. <span data-ttu-id="dedde-110">Use la <xref:System.Drawing.Graphics.DrawString%2A> método sobrecargado, pasando el texto que desee, <xref:System.Drawing.Rectangle> o <xref:System.Drawing.RectangleF>, <xref:System.Drawing.Font> y <xref:System.Drawing.Brush>.</span><span class="sxs-lookup"><span data-stu-id="dedde-110">Use the <xref:System.Drawing.Graphics.DrawString%2A> overloaded method, passing the text you want, <xref:System.Drawing.Rectangle> or <xref:System.Drawing.RectangleF>, <xref:System.Drawing.Font> and <xref:System.Drawing.Brush>.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#50](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#50)]
     [!code-vb[System.Drawing.AlignDrawnText#50](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#50)]  
  
### <a name="to-draw-wrapped-text-in-a-rectangle-with-gdi"></a><span data-ttu-id="dedde-111">Para dibujar texto ajustado en un rectángulo con GDI</span><span class="sxs-lookup"><span data-stu-id="dedde-111">To draw wrapped text in a rectangle with GDI</span></span>  
  
1. <span data-ttu-id="dedde-112">Use la <xref:System.Windows.Forms.TextFormatFlags> se debe ajustar el valor de enumeración para especificar el texto con el <xref:System.Windows.Forms.TextRenderer.DrawText%2A> método sobrecargado, pasando el texto que desee, <xref:System.Drawing.Rectangle>, <xref:System.Drawing.Font> y <xref:System.Drawing.Color>.</span><span class="sxs-lookup"><span data-stu-id="dedde-112">Use the <xref:System.Windows.Forms.TextFormatFlags> enumeration value to specify the text should be wrapped with the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> overloaded method, passing the text you want, <xref:System.Drawing.Rectangle>, <xref:System.Drawing.Font> and <xref:System.Drawing.Color>.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#60](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#60)]
     [!code-vb[System.Drawing.AlignDrawnText#60](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#60)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="dedde-113">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="dedde-113">Compiling the Code</span></span>  
 <span data-ttu-id="dedde-114">Los ejemplos anteriores requieren:</span><span class="sxs-lookup"><span data-stu-id="dedde-114">The previous examples require:</span></span>  
  
-   <xref:System.Windows.Forms.PaintEventArgs> `e`<span data-ttu-id="dedde-115">, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="dedde-115">, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dedde-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="dedde-116">See also</span></span>

- [<span data-ttu-id="dedde-117">Filtrar para dibujar texto con GDI</span><span class="sxs-lookup"><span data-stu-id="dedde-117">How to: Draw Text with GDI</span></span>](how-to-draw-text-with-gdi.md)
- [<span data-ttu-id="dedde-118">Utilizar fuentes y texto</span><span class="sxs-lookup"><span data-stu-id="dedde-118">Using Fonts and Text</span></span>](using-fonts-and-text.md)
- [<span data-ttu-id="dedde-119">Filtrar para construir fuentes y familias de fuentes</span><span class="sxs-lookup"><span data-stu-id="dedde-119">How to: Construct Font Families and Fonts</span></span>](how-to-construct-font-families-and-fonts.md)
- [<span data-ttu-id="dedde-120">Filtrar para dibujar texto en una ubicación especificada</span><span class="sxs-lookup"><span data-stu-id="dedde-120">How to: Draw Text at a Specified Location</span></span>](how-to-draw-text-at-a-specified-location.md)
