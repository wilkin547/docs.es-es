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
ms.openlocfilehash: 8e8f1bf193a41530a19e1046e3907b4c926b779f
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64637032"
---
# <a name="how-to-set-tab-stops-in-drawn-text"></a><span data-ttu-id="94024-102">Procedimiento para establecer posiciones de tabulación en texto dibujado</span><span class="sxs-lookup"><span data-stu-id="94024-102">How to: Set Tab Stops in Drawn Text</span></span>
<span data-ttu-id="94024-103">Puede establecer posiciones de tabulación para el texto mediante una llamada a la <xref:System.Drawing.StringFormat.SetTabStops%2A> método de un <xref:System.Drawing.StringFormat> objeto y, a continuación, pasando que <xref:System.Drawing.StringFormat> de objeto para el <xref:System.Drawing.Graphics.DrawString%2A> método de la <xref:System.Drawing.Graphics> clase.</span><span class="sxs-lookup"><span data-stu-id="94024-103">You can set tab stops for text by calling the <xref:System.Drawing.StringFormat.SetTabStops%2A> method of a <xref:System.Drawing.StringFormat> object and then passing that <xref:System.Drawing.StringFormat> object to the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="94024-104">El <xref:System.Windows.Forms.TextRenderer?displayProperty=nameWithType> hace que no admiten la incorporación de posiciones de tabulación en texto dibujado, aunque puede expandir la pestaña existente dejará de utilizar el <xref:System.Windows.Forms.TextFormatFlags.ExpandTabs?displayProperty=nameWithType> marca.</span><span class="sxs-lookup"><span data-stu-id="94024-104">The <xref:System.Windows.Forms.TextRenderer?displayProperty=nameWithType> does not support adding tab stops to drawn text, although you can expand existing tab stops using the <xref:System.Windows.Forms.TextFormatFlags.ExpandTabs?displayProperty=nameWithType> flag.</span></span>  
  
## <a name="example"></a><span data-ttu-id="94024-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="94024-105">Example</span></span>  
 <span data-ttu-id="94024-106">El ejemplo siguiente establece las posiciones de tabulación en 150, 250 y 350.</span><span class="sxs-lookup"><span data-stu-id="94024-106">The following example sets tab stops at 150, 250, and 350.</span></span> <span data-ttu-id="94024-107">A continuación, el código muestra una lista de nombres y las puntuaciones de pruebas con pestañas.</span><span class="sxs-lookup"><span data-stu-id="94024-107">Then, the code displays a tabbed list of names and test scores.</span></span>  
  
 <span data-ttu-id="94024-108">La siguiente ilustración muestra el texto con pestañas:</span><span class="sxs-lookup"><span data-stu-id="94024-108">The following illustration shows the tabbed text:</span></span>  
  
 ![Captura de pantalla que muestra una lista de nombres y las puntuaciones con pestañas.](./media/how-to-set-tab-stops-in-drawn-text/tab-list-names-test-scores.png)  
  
 <span data-ttu-id="94024-110">El código siguiente pasa dos argumentos de la <xref:System.Drawing.StringFormat.SetTabStops%2A> método.</span><span class="sxs-lookup"><span data-stu-id="94024-110">The following code passes two arguments to the <xref:System.Drawing.StringFormat.SetTabStops%2A> method.</span></span> <span data-ttu-id="94024-111">El segundo argumento es una matriz que contiene los desplazamientos de ficha.</span><span class="sxs-lookup"><span data-stu-id="94024-111">The second argument is an array that contains tab offsets.</span></span> <span data-ttu-id="94024-112">El primer argumento pasado a <xref:System.Drawing.StringFormat.SetTabStops%2A> es 0, lo que indica que el primer desplazamiento de la matriz se mide desde la posición 0, el borde izquierdo del rectángulo delimitador.</span><span class="sxs-lookup"><span data-stu-id="94024-112">The first argument passed to <xref:System.Drawing.StringFormat.SetTabStops%2A> is 0, which indicates that the first offset in the array is measured from position 0, the left edge of the bounding rectangle.</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.FontsAndText#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="94024-113">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="94024-113">Compiling the Code</span></span>  
  
- <span data-ttu-id="94024-114">El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="94024-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94024-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="94024-115">See also</span></span>

- [<span data-ttu-id="94024-116">Utilizar fuentes y texto</span><span class="sxs-lookup"><span data-stu-id="94024-116">Using Fonts and Text</span></span>](using-fonts-and-text.md)
- [<span data-ttu-id="94024-117">Cómo: Dibujar texto con GDI</span><span class="sxs-lookup"><span data-stu-id="94024-117">How to: Draw Text with GDI</span></span>](how-to-draw-text-with-gdi.md)
