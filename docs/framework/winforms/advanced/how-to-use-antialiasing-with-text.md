---
title: Procedimiento Usa suavizado de contorno con texto
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- strings [Windows Forms], smoothing drawn
- antialiasing [Windows Forms], using with text
- text [Windows Forms], smoothing
- text [Windows Forms], antialiasing
- strings [Windows Forms], antialiasing when drawing
ms.assetid: 48fc34f3-f236-4b01-a0cb-f0752e6d22ae
ms.openlocfilehash: 64b1c27b9e8b7d405dde5add105ff2e682f8ad87
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54534113"
---
# <a name="how-to-use-antialiasing-with-text"></a><span data-ttu-id="cdd29-102">Procedimiento Usa suavizado de contorno con texto</span><span class="sxs-lookup"><span data-stu-id="cdd29-102">How to: Use Antialiasing with Text</span></span>
<span data-ttu-id="cdd29-103">*Suavizado de contorno* hace referencia al suavizado de los bordes escalonados de dibujados gráficos y texto para mejorar su apariencia y legibilidad.</span><span class="sxs-lookup"><span data-stu-id="cdd29-103">*Antialiasing* refers to the smoothing of jagged edges of drawn graphics and text to improve their appearance or readability.</span></span> <span data-ttu-id="cdd29-104">Con el administrado [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] clases, puede representar texto con suavizado de contorno de alta calidad, así como texto de menor calidad.</span><span class="sxs-lookup"><span data-stu-id="cdd29-104">With the managed [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] classes, you can render high quality antialiased text, as well as lower quality text.</span></span> <span data-ttu-id="cdd29-105">Normalmente, una representación de mayor calidad toma más tiempo de procesamiento que una calidad inferior.</span><span class="sxs-lookup"><span data-stu-id="cdd29-105">Typically, higher quality rendering takes more processing time than lower quality rendering.</span></span> <span data-ttu-id="cdd29-106">Para establecer el nivel de calidad de texto, establezca el <xref:System.Drawing.Graphics.TextRenderingHint%2A> propiedad de un <xref:System.Drawing.Graphics> a uno de los elementos de la <xref:System.Drawing.Text.TextRenderingHint> (enumeración)</span><span class="sxs-lookup"><span data-stu-id="cdd29-106">To set the text quality level, set the <xref:System.Drawing.Graphics.TextRenderingHint%2A> property of a <xref:System.Drawing.Graphics> to one of the elements of the <xref:System.Drawing.Text.TextRenderingHint> enumeration</span></span>  
  
## <a name="example"></a><span data-ttu-id="cdd29-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cdd29-107">Example</span></span>  
 <span data-ttu-id="cdd29-108">En el ejemplo de código siguiente se dibuja texto con dos configuraciones de calidad diferente.</span><span class="sxs-lookup"><span data-stu-id="cdd29-108">The following code example draws text with two different quality settings.</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.FontsAndText#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#21)]  
 
 <span data-ttu-id="cdd29-109">La siguiente ilustración muestra la salida del código de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="cdd29-109">The following illustration shows the output of the example code:</span></span>  
  
 <span data-ttu-id="cdd29-110">![Fonts Text](../../../../docs/framework/winforms/advanced/media/fontstext10.png "FontsText10")</span><span class="sxs-lookup"><span data-stu-id="cdd29-110">![Fonts Text](../../../../docs/framework/winforms/advanced/media/fontstext10.png "FontsText10")</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="cdd29-111">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="cdd29-111">Compiling the Code</span></span>  
 <span data-ttu-id="cdd29-112">El ejemplo de código anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="cdd29-112">The preceding code example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdd29-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="cdd29-113">See also</span></span>
- [<span data-ttu-id="cdd29-114">Utilizar fuentes y texto</span><span class="sxs-lookup"><span data-stu-id="cdd29-114">Using Fonts and Text</span></span>](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
