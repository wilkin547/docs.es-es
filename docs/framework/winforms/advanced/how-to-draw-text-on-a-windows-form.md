---
title: 'Cómo: Dibujar texto en Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- forms [Windows Forms], drawing text
- text [Windows Forms], drawing
ms.assetid: 5d2447a9-21a1-4adc-b954-5516f2bb9b2c
ms.openlocfilehash: 9369a4ed26107bdc395d455ba6fb8420fd895d6f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33524789"
---
# <a name="how-to-draw-text-on-a-windows-form"></a><span data-ttu-id="ee4d6-102">Cómo: Dibujar texto en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ee4d6-102">How to: Draw Text on a Windows Form</span></span>
<span data-ttu-id="ee4d6-103">En el ejemplo de código siguiente se muestra cómo utilizar el <xref:System.Drawing.Graphics.DrawString%2A> método de la <xref:System.Drawing.Graphics> para dibujar texto en un formulario.</span><span class="sxs-lookup"><span data-stu-id="ee4d6-103">The following code example shows how to use the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> to draw text on a form.</span></span> <span data-ttu-id="ee4d6-104">Como alternativa, puede usar <xref:System.Windows.Forms.TextRenderer> para dibujar texto en un formulario.</span><span class="sxs-lookup"><span data-stu-id="ee4d6-104">Alternatively, you can use <xref:System.Windows.Forms.TextRenderer> for drawing text on a form.</span></span> <span data-ttu-id="ee4d6-105">Para obtener más información, consulte [Cómo: dibujar texto con GDI](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md).</span><span class="sxs-lookup"><span data-stu-id="ee4d6-105">For more information, see [How to: Draw Text with GDI](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ee4d6-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ee4d6-106">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#7](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#7)]
 [!code-csharp[System.Drawing.ConceptualHowTos#7](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#7)]
 [!code-vb[System.Drawing.ConceptualHowTos#7](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#7)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ee4d6-107">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="ee4d6-107">Compiling the Code</span></span>  
 <span data-ttu-id="ee4d6-108">No se puede llamar el <xref:System.Drawing.Graphics.DrawString%2A> método en el <xref:System.Windows.Forms.Form.Load> controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="ee4d6-108">You cannot call the <xref:System.Drawing.Graphics.DrawString%2A> method in the <xref:System.Windows.Forms.Form.Load> event handler.</span></span> <span data-ttu-id="ee4d6-109">No se volverá a dibujar el contenido dibujado si el formulario cambia de tamaño o lo ocultan con otra forma.</span><span class="sxs-lookup"><span data-stu-id="ee4d6-109">The drawn content will not be redrawn if the form is resized or obscured by another form.</span></span> <span data-ttu-id="ee4d6-110">Para que el contenido automáticamente volver a dibujar, debe invalidar el <xref:System.Windows.Forms.Control.OnPaint%2A> método.</span><span class="sxs-lookup"><span data-stu-id="ee4d6-110">To make your content automatically repaint, you should override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="ee4d6-111">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="ee4d6-111">Robust Programming</span></span>  
 <span data-ttu-id="ee4d6-112">Las condiciones siguientes pueden provocar una excepción:</span><span class="sxs-lookup"><span data-stu-id="ee4d6-112">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="ee4d6-113">La fuente Arial no está instalada.</span><span class="sxs-lookup"><span data-stu-id="ee4d6-113">The Arial font is not installed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee4d6-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="ee4d6-114">See Also</span></span>  
 <xref:System.Drawing.Graphics.DrawString%2A>  
 <xref:System.Windows.Forms.TextRenderer.DrawText%2A>  
 <xref:System.Drawing.StringFormat.FormatFlags%2A>  
 <xref:System.Drawing.StringFormatFlags>  
 <xref:System.Windows.Forms.TextFormatFlags>  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 [<span data-ttu-id="ee4d6-115">Introducción a la programación de gráficos</span><span class="sxs-lookup"><span data-stu-id="ee4d6-115">Getting Started with Graphics Programming</span></span>](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)  
 [<span data-ttu-id="ee4d6-116">Dibujar texto con GDI</span><span class="sxs-lookup"><span data-stu-id="ee4d6-116">How to: Draw Text with GDI</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)
