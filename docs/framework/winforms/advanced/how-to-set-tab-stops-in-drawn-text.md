---
title: Procedimiento para establecer posiciones de tabulación en texto dibujado
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], drawing with tab stops
- tabs [Windows Forms], drawn text
ms.assetid: 64878f98-39ba-4303-b63f-0859ab682eeb
ms.openlocfilehash: 8821f6170b8ba588e3197ef54eab14c2719a6cc3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947817"
---
# <a name="how-to-set-tab-stops-in-drawn-text"></a><span data-ttu-id="10353-102">Procedimiento para establecer posiciones de tabulación en texto dibujado</span><span class="sxs-lookup"><span data-stu-id="10353-102">How to: Set Tab Stops in Drawn Text</span></span>
<span data-ttu-id="10353-103">Puede establecer las tabulaciones para el texto llamando al <xref:System.Drawing.StringFormat.SetTabStops%2A> método de un <xref:System.Drawing.StringFormat> objeto y, a continuación <xref:System.Drawing.StringFormat> , <xref:System.Drawing.Graphics.DrawString%2A> pasando ese objeto al método <xref:System.Drawing.Graphics> de la clase.</span><span class="sxs-lookup"><span data-stu-id="10353-103">You can set tab stops for text by calling the <xref:System.Drawing.StringFormat.SetTabStops%2A> method of a <xref:System.Drawing.StringFormat> object and then passing that <xref:System.Drawing.StringFormat> object to the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> class.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="10353-104">No <xref:System.Windows.Forms.TextRenderer?displayProperty=nameWithType> admite la adición de tabulaciones al texto dibujado, aunque se pueden expandir las tabulaciones existentes mediante <xref:System.Windows.Forms.TextFormatFlags.ExpandTabs?displayProperty=nameWithType> la marca.</span><span class="sxs-lookup"><span data-stu-id="10353-104">The <xref:System.Windows.Forms.TextRenderer?displayProperty=nameWithType> does not support adding tab stops to drawn text, although you can expand existing tab stops using the <xref:System.Windows.Forms.TextFormatFlags.ExpandTabs?displayProperty=nameWithType> flag.</span></span>  
  
## <a name="example"></a><span data-ttu-id="10353-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="10353-105">Example</span></span>  
 <span data-ttu-id="10353-106">En el ejemplo siguiente se establecen tabulaciones en 150, 250 y 350.</span><span class="sxs-lookup"><span data-stu-id="10353-106">The following example sets tab stops at 150, 250, and 350.</span></span> <span data-ttu-id="10353-107">Después, el código muestra una lista con pestañas de nombres y puntuaciones de pruebas.</span><span class="sxs-lookup"><span data-stu-id="10353-107">Then, the code displays a tabbed list of names and test scores.</span></span>  
  
 <span data-ttu-id="10353-108">En la ilustración siguiente se muestra el texto con pestañas:</span><span class="sxs-lookup"><span data-stu-id="10353-108">The following illustration shows the tabbed text:</span></span>  
  
 ![Captura de pantalla que muestra una lista con pestañas de nombres y puntuaciones.](./media/how-to-set-tab-stops-in-drawn-text/tab-list-names-test-scores.png)  
  
 <span data-ttu-id="10353-110">En el código siguiente se pasan dos argumentos <xref:System.Drawing.StringFormat.SetTabStops%2A> al método.</span><span class="sxs-lookup"><span data-stu-id="10353-110">The following code passes two arguments to the <xref:System.Drawing.StringFormat.SetTabStops%2A> method.</span></span> <span data-ttu-id="10353-111">El segundo argumento es una matriz que contiene desplazamientos de tabulación.</span><span class="sxs-lookup"><span data-stu-id="10353-111">The second argument is an array that contains tab offsets.</span></span> <span data-ttu-id="10353-112">El primer argumento pasado a <xref:System.Drawing.StringFormat.SetTabStops%2A> es 0, que indica que el primer desplazamiento de la matriz se mide desde la posición 0, el borde izquierdo del rectángulo delimitador.</span><span class="sxs-lookup"><span data-stu-id="10353-112">The first argument passed to <xref:System.Drawing.StringFormat.SetTabStops%2A> is 0, which indicates that the first offset in the array is measured from position 0, the left edge of the bounding rectangle.</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.FontsAndText#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="10353-113">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="10353-113">Compiling the Code</span></span>  
  
- <span data-ttu-id="10353-114">El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="10353-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10353-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="10353-115">See also</span></span>

- [<span data-ttu-id="10353-116">Utilizar fuentes y texto</span><span class="sxs-lookup"><span data-stu-id="10353-116">Using Fonts and Text</span></span>](using-fonts-and-text.md)
- [<span data-ttu-id="10353-117">Cómo: Dibujar texto con GDI</span><span class="sxs-lookup"><span data-stu-id="10353-117">How to: Draw Text with GDI</span></span>](how-to-draw-text-with-gdi.md)
