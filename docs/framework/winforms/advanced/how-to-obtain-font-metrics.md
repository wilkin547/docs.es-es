---
title: Procedimiento para obtener métricas de fuentes
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- fonts [Windows Forms], obtaining metrics
- font metrics [Windows Forms], obtaining
ms.assetid: ff7c0616-67f7-4fa2-84ee-b8d642f2b09b
ms.openlocfilehash: 24cada3962339cae0608bbe01e070a0b8e256e73
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59119059"
---
# <a name="how-to-obtain-font-metrics"></a><span data-ttu-id="9eec6-102">Procedimiento para obtener métricas de fuentes</span><span class="sxs-lookup"><span data-stu-id="9eec6-102">How to: Obtain Font Metrics</span></span>
<span data-ttu-id="9eec6-103">La <xref:System.Drawing.FontFamily> clase proporciona los siguientes métodos que recuperan diversas métricas para una combinación de familia y estilo concreta:</span><span class="sxs-lookup"><span data-stu-id="9eec6-103">The <xref:System.Drawing.FontFamily> class provides the following methods that retrieve various metrics for a particular family/style combination:</span></span>  
  
-   <span data-ttu-id="9eec6-104"><xref:System.Drawing.FontFamily.GetEmHeight%2A>(FontStyle)</span><span class="sxs-lookup"><span data-stu-id="9eec6-104"><xref:System.Drawing.FontFamily.GetEmHeight%2A>(FontStyle)</span></span>  
  
-   <span data-ttu-id="9eec6-105"><xref:System.Drawing.FontFamily.GetCellAscent%2A>(FontStyle)</span><span class="sxs-lookup"><span data-stu-id="9eec6-105"><xref:System.Drawing.FontFamily.GetCellAscent%2A>(FontStyle)</span></span>  
  
-   <span data-ttu-id="9eec6-106"><xref:System.Drawing.FontFamily.GetCellDescent%2A>(FontStyle)</span><span class="sxs-lookup"><span data-stu-id="9eec6-106"><xref:System.Drawing.FontFamily.GetCellDescent%2A>(FontStyle)</span></span>  
  
-   <span data-ttu-id="9eec6-107"><xref:System.Drawing.FontFamily.GetLineSpacing%2A>(FontStyle)</span><span class="sxs-lookup"><span data-stu-id="9eec6-107"><xref:System.Drawing.FontFamily.GetLineSpacing%2A>(FontStyle)</span></span>  
  
 <span data-ttu-id="9eec6-108">Los números devueltos por estos métodos están en unidades de diseño de fuente, por lo que son independientes del tamaño y las unidades de una determinada <xref:System.Drawing.Font> objeto.</span><span class="sxs-lookup"><span data-stu-id="9eec6-108">The numbers returned by these methods are in font design units, so they are independent of the size and units of a particular <xref:System.Drawing.Font> object.</span></span>  
  
 <span data-ttu-id="9eec6-109">La siguiente ilustración muestra las distintas métricas.</span><span class="sxs-lookup"><span data-stu-id="9eec6-109">The following illustration shows the various metrics.</span></span>  
  
 <span data-ttu-id="9eec6-110">![Texto de las fuentes](./media/fontstext7a.png "fontstext7A")</span><span class="sxs-lookup"><span data-stu-id="9eec6-110">![Fonts Text](./media/fontstext7a.png "fontstext7A")</span></span>  
  
## <a name="example"></a><span data-ttu-id="9eec6-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9eec6-111">Example</span></span>  
 <span data-ttu-id="9eec6-112">El ejemplo siguiente muestra las métricas para el estilo normal de la familia de fuentes Arial.</span><span class="sxs-lookup"><span data-stu-id="9eec6-112">The following example displays the metrics for the regular style of the Arial font family.</span></span> <span data-ttu-id="9eec6-113">El código también crea un <xref:System.Drawing.Font> objeto (basado en la familia Arial) con el tamaño de 16 píxeles y muestra las métricas (en píxeles) para ese <xref:System.Drawing.Font> objeto.</span><span class="sxs-lookup"><span data-stu-id="9eec6-113">The code also creates a <xref:System.Drawing.Font> object (based on the Arial family) with size 16 pixels and displays the metrics (in pixels) for that particular <xref:System.Drawing.Font> object.</span></span>  
  
 <span data-ttu-id="9eec6-114">La siguiente ilustración muestra el resultado del código de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="9eec6-114">The following illustration shows the output of the example code.</span></span>  
  
 <span data-ttu-id="9eec6-115">![Fonts Text](./media/csfontstext8.png "csFontsText8")</span><span class="sxs-lookup"><span data-stu-id="9eec6-115">![Fonts Text](./media/csfontstext8.png "csFontsText8")</span></span>  
  
 <span data-ttu-id="9eec6-116">Tenga en cuenta las dos primeras líneas de salida en la ilustración anterior.</span><span class="sxs-lookup"><span data-stu-id="9eec6-116">Note the first two lines of output in the preceding illustration.</span></span> <span data-ttu-id="9eec6-117">El <xref:System.Drawing.Font> objeto devuelve un tamaño de 16 y el <xref:System.Drawing.FontFamily> objeto devuelve un alto em de 2048.</span><span class="sxs-lookup"><span data-stu-id="9eec6-117">The <xref:System.Drawing.Font> object returns a size of 16, and the <xref:System.Drawing.FontFamily> object returns an em height of 2,048.</span></span> <span data-ttu-id="9eec6-118">Estos dos números (16 y 2.048) son la clave para la conversión entre unidades de diseño de fuente y las unidades (en este caso, píxeles) de la <xref:System.Drawing.Font> objeto.</span><span class="sxs-lookup"><span data-stu-id="9eec6-118">These two numbers (16 and 2,048) are the key to converting between font design units and the units (in this case pixels) of the <xref:System.Drawing.Font> object.</span></span>  
  
 <span data-ttu-id="9eec6-119">Por ejemplo, puede convertir el ascenso de unidades de diseño a píxeles como sigue:</span><span class="sxs-lookup"><span data-stu-id="9eec6-119">For example, you can convert the ascent from design units to pixels as follows:</span></span>  
  
 <span data-ttu-id="9eec6-120">![Fonts Text](./media/fontstext9.png "FontsText9")</span><span class="sxs-lookup"><span data-stu-id="9eec6-120">![Fonts Text](./media/fontstext9.png "FontsText9")</span></span>  
  
 <span data-ttu-id="9eec6-121">El siguiente código coloca el texto verticalmente estableciendo el <xref:System.Drawing.PointF.Y%2A> miembro de datos de un <xref:System.Drawing.PointF> objeto.</span><span class="sxs-lookup"><span data-stu-id="9eec6-121">The following code positions text vertically by setting the <xref:System.Drawing.PointF.Y%2A> data member of a <xref:System.Drawing.PointF> object.</span></span> <span data-ttu-id="9eec6-122">La coordenada y se incrementa en `font.Height` para cada nueva línea de texto.</span><span class="sxs-lookup"><span data-stu-id="9eec6-122">The y-coordinate is increased by `font.Height` for each new line of text.</span></span> <span data-ttu-id="9eec6-123">El <xref:System.Drawing.Font.Height%2A> propiedad de un <xref:System.Drawing.Font> objeto devuelve el interlineado (en píxeles) para ese <xref:System.Drawing.Font> objeto.</span><span class="sxs-lookup"><span data-stu-id="9eec6-123">The <xref:System.Drawing.Font.Height%2A> property of a <xref:System.Drawing.Font> object returns the line spacing (in pixels) for that particular <xref:System.Drawing.Font> object.</span></span> <span data-ttu-id="9eec6-124">En este ejemplo, el número devuelto por <xref:System.Drawing.Font.Height%2A> es 19.</span><span class="sxs-lookup"><span data-stu-id="9eec6-124">In this example, the number returned by <xref:System.Drawing.Font.Height%2A> is 19.</span></span> <span data-ttu-id="9eec6-125">Tenga en cuenta que es el mismo que el número (redondeado a un entero) obtenido mediante la conversión de la métrica de espaciado de línea en píxeles.</span><span class="sxs-lookup"><span data-stu-id="9eec6-125">Note that this is the same as the number (rounded up to an integer) obtained by converting the line-spacing metric to pixels.</span></span>  
  
 <span data-ttu-id="9eec6-126">Tenga en cuenta que el alto em (también llamado tamaño o tamaño em) no es la suma de ascenso y el descenso.</span><span class="sxs-lookup"><span data-stu-id="9eec6-126">Note that the em height (also called size or em size) is not the sum of the ascent and the descent.</span></span> <span data-ttu-id="9eec6-127">La suma de ascenso y el descenso se denomina el alto de celda.</span><span class="sxs-lookup"><span data-stu-id="9eec6-127">The sum of the ascent and the descent is called the cell height.</span></span> <span data-ttu-id="9eec6-128">El alto de celda menos el espacio interno es igual que el alto em.</span><span class="sxs-lookup"><span data-stu-id="9eec6-128">The cell height minus the internal leading is equal to the em height.</span></span> <span data-ttu-id="9eec6-129">El alto de celda más la inicial externa es igual que el espaciado de línea.</span><span class="sxs-lookup"><span data-stu-id="9eec6-129">The cell height plus the external leading is equal to the line spacing.</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#71](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.FontsAndText#71](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9eec6-130">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="9eec6-130">Compiling the Code</span></span>  
 <span data-ttu-id="9eec6-131">El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="9eec6-131">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9eec6-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="9eec6-132">See also</span></span>

- [<span data-ttu-id="9eec6-133">Gráficos y dibujos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9eec6-133">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="9eec6-134">Utilizar fuentes y texto</span><span class="sxs-lookup"><span data-stu-id="9eec6-134">Using Fonts and Text</span></span>](using-fonts-and-text.md)
