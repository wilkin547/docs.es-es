---
title: 'Cómo: Alinear texto dibujado'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], aligning
- Windows Forms, aligning drawn text
ms.assetid: 83c10a81-1a90-4b5c-98aa-2c6c4b280079
ms.openlocfilehash: 96e14ef510a08ed0c387733e37b6acae6cbd31cd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33522762"
---
# <a name="how-to-align-drawn-text"></a><span data-ttu-id="a7618-102">Cómo: Alinear texto dibujado</span><span class="sxs-lookup"><span data-stu-id="a7618-102">How to: Align Drawn Text</span></span>
<span data-ttu-id="a7618-103">Al realizar un dibujo personalizado, a menudo puede Centrar el texto dibujado en un formulario o control.</span><span class="sxs-lookup"><span data-stu-id="a7618-103">When you perform custom drawing, you may often want to center drawn text on a form or control.</span></span> <span data-ttu-id="a7618-104">Puede alinear texto dibujado con facilidad el <xref:System.Drawing.Graphics.DrawString%2A> o <xref:System.Windows.Forms.TextRenderer.DrawText%2A> métodos al crear el objeto de formato correcto y establecer las marcas de formato adecuado.</span><span class="sxs-lookup"><span data-stu-id="a7618-104">You can easily align text drawn with the <xref:System.Drawing.Graphics.DrawString%2A> or <xref:System.Windows.Forms.TextRenderer.DrawText%2A> methods by creating the correct formatting object and setting the appropriate format flags.</span></span>  
  
### <a name="to-draw-centered-text-with-gdi-drawstring"></a><span data-ttu-id="a7618-105">Para dibujar texto centrado con GDI + (DrawString)</span><span class="sxs-lookup"><span data-stu-id="a7618-105">To draw centered text with GDI+ (DrawString)</span></span>  
  
1.  <span data-ttu-id="a7618-106">Use un <xref:System.Drawing.StringFormat> con el adecuado <xref:System.Drawing.Graphics.DrawString%2A> método para especificar el texto centrado.</span><span class="sxs-lookup"><span data-stu-id="a7618-106">Use a <xref:System.Drawing.StringFormat> with the appropriate <xref:System.Drawing.Graphics.DrawString%2A> method to specify centered text.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#10)]
     [!code-vb[System.Drawing.AlignDrawnText#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#10)]  
  
### <a name="to-draw-centered-text-with-gdi-drawtext"></a><span data-ttu-id="a7618-107">Para dibujar texto centrado con GDI (DrawText)</span><span class="sxs-lookup"><span data-stu-id="a7618-107">To draw centered text with GDI (DrawText)</span></span>  
  
1.  <span data-ttu-id="a7618-108">Use la <xref:System.Windows.Forms.TextFormatFlags> enumeración para el ajuste, así como verticalmente y horizontalmente centrar el texto con el adecuado <xref:System.Windows.Forms.TextRenderer.DrawText%2A> método.</span><span class="sxs-lookup"><span data-stu-id="a7618-108">Use the <xref:System.Windows.Forms.TextFormatFlags> enumeration for wrapping as well as vertically and horizontally centering text with the appropriate <xref:System.Windows.Forms.TextRenderer.DrawText%2A> method.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#20)]
     [!code-vb[System.Drawing.AlignDrawnText#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#20)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a7618-109">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="a7618-109">Compiling the Code</span></span>  
 <span data-ttu-id="a7618-110">Los ejemplos de código anteriores están diseñados para su uso con Windows Forms y requieren <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="a7618-110">The preceding code examples are designed for use with Windows Forms, and they require <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7618-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="a7618-111">See Also</span></span>  
 [<span data-ttu-id="a7618-112">Dibujar texto con GDI</span><span class="sxs-lookup"><span data-stu-id="a7618-112">How to: Draw Text with GDI</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)  
 [<span data-ttu-id="a7618-113">Utilizar fuentes y texto</span><span class="sxs-lookup"><span data-stu-id="a7618-113">Using Fonts and Text</span></span>](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)  
 [<span data-ttu-id="a7618-114">Construir fuentes y familias de fuentes</span><span class="sxs-lookup"><span data-stu-id="a7618-114">How to: Construct Font Families and Fonts</span></span>](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md)
