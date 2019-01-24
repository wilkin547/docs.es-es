---
title: Procedimiento Crear texto Vertical
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
ms.openlocfilehash: 513d59c61d5195665928f6bb28d1d091b425c103
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54573155"
---
# <a name="how-to-create-vertical-text"></a><span data-ttu-id="d11e3-102">Procedimiento Crear texto Vertical</span><span class="sxs-lookup"><span data-stu-id="d11e3-102">How to: Create Vertical Text</span></span>
<span data-ttu-id="d11e3-103">Puede usar un <xref:System.Drawing.StringFormat> objeto para especificar que se dibuja el texto verticalmente en lugar de horizontalmente.</span><span class="sxs-lookup"><span data-stu-id="d11e3-103">You can use a <xref:System.Drawing.StringFormat> object to specify that text be drawn vertically rather than horizontally.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d11e3-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d11e3-104">Example</span></span>  
 <span data-ttu-id="d11e3-105">En el ejemplo siguiente se asigna el valor <xref:System.Drawing.StringFormatFlags.DirectionVertical> a la <xref:System.Drawing.StringFormat.FormatFlags%2A> propiedad de un <xref:System.Drawing.StringFormat> objeto.</span><span class="sxs-lookup"><span data-stu-id="d11e3-105">The following example assigns the value <xref:System.Drawing.StringFormatFlags.DirectionVertical> to the <xref:System.Drawing.StringFormat.FormatFlags%2A> property of a <xref:System.Drawing.StringFormat> object.</span></span> <span data-ttu-id="d11e3-106">Que <xref:System.Drawing.StringFormat> objeto se pasa a la <xref:System.Drawing.Graphics.DrawString%2A> método de la <xref:System.Drawing.Graphics> clase.</span><span class="sxs-lookup"><span data-stu-id="d11e3-106">That <xref:System.Drawing.StringFormat> object is passed to the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="d11e3-107">El valor <xref:System.Drawing.StringFormatFlags.DirectionVertical> es un miembro de la <xref:System.Drawing.StringFormatFlags> enumeración.</span><span class="sxs-lookup"><span data-stu-id="d11e3-107">The value <xref:System.Drawing.StringFormatFlags.DirectionVertical> is a member of the <xref:System.Drawing.StringFormatFlags> enumeration.</span></span>  
  
 <span data-ttu-id="d11e3-108">La siguiente ilustración muestra el texto vertical.</span><span class="sxs-lookup"><span data-stu-id="d11e3-108">The following illustration shows the vertical text.</span></span>  
  
 <span data-ttu-id="d11e3-109">![Texto de las fuentes](../../../../docs/framework/winforms/advanced/media/csfontstext5.png "csfontstext5")</span><span class="sxs-lookup"><span data-stu-id="d11e3-109">![Fonts Text](../../../../docs/framework/winforms/advanced/media/csfontstext5.png "csfontstext5")</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.FontsAndText#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d11e3-110">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="d11e3-110">Compiling the Code</span></span>  
  
-   <span data-ttu-id="d11e3-111">El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e` , que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="d11e3-111">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e` , which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d11e3-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="d11e3-112">See also</span></span>
- [<span data-ttu-id="d11e3-113">Cómo: Dibujar texto con GDI</span><span class="sxs-lookup"><span data-stu-id="d11e3-113">How to: Draw Text with GDI</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)
