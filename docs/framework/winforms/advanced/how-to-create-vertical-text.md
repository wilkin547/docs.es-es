---
title: 'Cómo: Crear texto vertical'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], drawing vertical
- Windows Forms, drawing vertical text
- strings [Windows Forms], drawing vertical
- vertical text [Windows Forms], drawing
ms.assetid: 50c69046-4188-47d9-b949-cc2610ffd337
ms.openlocfilehash: 86401342625f593945b801f7619ef9ca9681317c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182562"
---
# <a name="how-to-create-vertical-text"></a><span data-ttu-id="9a6e8-102">Cómo: Crear texto vertical</span><span class="sxs-lookup"><span data-stu-id="9a6e8-102">How to: Create Vertical Text</span></span>
<span data-ttu-id="9a6e8-103">Puede utilizar <xref:System.Drawing.StringFormat> un objeto para especificar que el texto se dibuje verticalmente en lugar de horizontalmente.</span><span class="sxs-lookup"><span data-stu-id="9a6e8-103">You can use a <xref:System.Drawing.StringFormat> object to specify that text be drawn vertically rather than horizontally.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9a6e8-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9a6e8-104">Example</span></span>  
 <span data-ttu-id="9a6e8-105">En el ejemplo siguiente <xref:System.Drawing.StringFormatFlags.DirectionVertical> se <xref:System.Drawing.StringFormat.FormatFlags%2A> asigna <xref:System.Drawing.StringFormat> el valor a la propiedad de un objeto.</span><span class="sxs-lookup"><span data-stu-id="9a6e8-105">The following example assigns the value <xref:System.Drawing.StringFormatFlags.DirectionVertical> to the <xref:System.Drawing.StringFormat.FormatFlags%2A> property of a <xref:System.Drawing.StringFormat> object.</span></span> <span data-ttu-id="9a6e8-106">Ese <xref:System.Drawing.StringFormat> objeto se <xref:System.Drawing.Graphics.DrawString%2A> pasa al <xref:System.Drawing.Graphics> método de la clase.</span><span class="sxs-lookup"><span data-stu-id="9a6e8-106">That <xref:System.Drawing.StringFormat> object is passed to the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="9a6e8-107">El <xref:System.Drawing.StringFormatFlags.DirectionVertical> valor es un <xref:System.Drawing.StringFormatFlags> miembro de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="9a6e8-107">The value <xref:System.Drawing.StringFormatFlags.DirectionVertical> is a member of the <xref:System.Drawing.StringFormatFlags> enumeration.</span></span>  
  
 <span data-ttu-id="9a6e8-108">La siguiente ilustración muestra el texto vertical:</span><span class="sxs-lookup"><span data-stu-id="9a6e8-108">The following illustration shows the vertical text:</span></span>
  
 ![Gráfico que muestra el texto de fuente vertical.](./media/how-to-create-vertical-text/vertical-font-text-graphic.png)  
  
 [!code-csharp[System.Drawing.FontsAndText#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.FontsAndText#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9a6e8-110">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="9a6e8-110">Compiling the Code</span></span>  
  
- <span data-ttu-id="9a6e8-111">El ejemplo anterior está diseñado para su uso <xref:System.Windows.Forms.PaintEventArgs> `e` con formularios Windows <xref:System.Windows.Forms.PaintEventHandler>Forms y requiere , que es un parámetro de .</span><span class="sxs-lookup"><span data-stu-id="9a6e8-111">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e` , which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a6e8-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9a6e8-112">See also</span></span>

- [<span data-ttu-id="9a6e8-113">Cómo: Dibujar texto con GDI</span><span class="sxs-lookup"><span data-stu-id="9a6e8-113">How to: Draw Text with GDI</span></span>](how-to-draw-text-with-gdi.md)
