---
title: "Cómo: Obtener medidas de fuentes"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- fonts [Windows Forms], obtaining metrics
- font metrics [Windows Forms], obtaining
ms.assetid: ff7c0616-67f7-4fa2-84ee-b8d642f2b09b
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5b45f3f903c02d056fc457b652b01fb7b59413a8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-obtain-font-metrics"></a><span data-ttu-id="db6f7-102">Cómo: Obtener medidas de fuentes</span><span class="sxs-lookup"><span data-stu-id="db6f7-102">How to: Obtain Font Metrics</span></span>
<span data-ttu-id="db6f7-103">La <xref:System.Drawing.FontFamily> clase proporciona los métodos siguientes que recuperan diversas métricas para una combinación de familia y estilo concreta:</span><span class="sxs-lookup"><span data-stu-id="db6f7-103">The <xref:System.Drawing.FontFamily> class provides the following methods that retrieve various metrics for a particular family/style combination:</span></span>  
  
-   <span data-ttu-id="db6f7-104"><xref:System.Drawing.FontFamily.GetEmHeight%2A>(FontStyle)</span><span class="sxs-lookup"><span data-stu-id="db6f7-104"><xref:System.Drawing.FontFamily.GetEmHeight%2A>(FontStyle)</span></span>  
  
-   <span data-ttu-id="db6f7-105"><xref:System.Drawing.FontFamily.GetCellAscent%2A>(FontStyle)</span><span class="sxs-lookup"><span data-stu-id="db6f7-105"><xref:System.Drawing.FontFamily.GetCellAscent%2A>(FontStyle)</span></span>  
  
-   <span data-ttu-id="db6f7-106"><xref:System.Drawing.FontFamily.GetCellDescent%2A>(FontStyle)</span><span class="sxs-lookup"><span data-stu-id="db6f7-106"><xref:System.Drawing.FontFamily.GetCellDescent%2A>(FontStyle)</span></span>  
  
-   <span data-ttu-id="db6f7-107"><xref:System.Drawing.FontFamily.GetLineSpacing%2A>(FontStyle)</span><span class="sxs-lookup"><span data-stu-id="db6f7-107"><xref:System.Drawing.FontFamily.GetLineSpacing%2A>(FontStyle)</span></span>  
  
 <span data-ttu-id="db6f7-108">Los números devueltos por estos métodos están en unidades de diseño de fuente, por lo que son independientes del tamaño y unidades de un determinado <xref:System.Drawing.Font> objeto.</span><span class="sxs-lookup"><span data-stu-id="db6f7-108">The numbers returned by these methods are in font design units, so they are independent of the size and units of a particular <xref:System.Drawing.Font> object.</span></span>  
  
 <span data-ttu-id="db6f7-109">La ilustración siguiente muestra las distintas métricas.</span><span class="sxs-lookup"><span data-stu-id="db6f7-109">The following illustration shows the various metrics.</span></span>  
  
 <span data-ttu-id="db6f7-110">![Texto de las fuentes](../../../../docs/framework/winforms/advanced/media/fontstext7a.png "fontstext7A")</span><span class="sxs-lookup"><span data-stu-id="db6f7-110">![Fonts Text](../../../../docs/framework/winforms/advanced/media/fontstext7a.png "fontstext7A")</span></span>  
  
## <a name="example"></a><span data-ttu-id="db6f7-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="db6f7-111">Example</span></span>  
 <span data-ttu-id="db6f7-112">En el ejemplo siguiente se muestra las métricas para el estilo normal de la familia de fuentes Arial.</span><span class="sxs-lookup"><span data-stu-id="db6f7-112">The following example displays the metrics for the regular style of the Arial font family.</span></span> <span data-ttu-id="db6f7-113">El código también crea un <xref:System.Drawing.Font> objeto (basado en la familia Arial) con el tamaño de 16 píxeles y muestra las métricas (en píxeles) de ese <xref:System.Drawing.Font> objeto.</span><span class="sxs-lookup"><span data-stu-id="db6f7-113">The code also creates a <xref:System.Drawing.Font> object (based on the Arial family) with size 16 pixels and displays the metrics (in pixels) for that particular <xref:System.Drawing.Font> object.</span></span>  
  
 <span data-ttu-id="db6f7-114">En la siguiente ilustración muestra el resultado del código de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="db6f7-114">The following illustration shows the output of the example code.</span></span>  
  
 <span data-ttu-id="db6f7-115">![Texto de las fuentes](../../../../docs/framework/winforms/advanced/media/csfontstext8.png "csFontsText8")</span><span class="sxs-lookup"><span data-stu-id="db6f7-115">![Fonts Text](../../../../docs/framework/winforms/advanced/media/csfontstext8.png "csFontsText8")</span></span>  
  
 <span data-ttu-id="db6f7-116">Tenga en cuenta las dos primeras líneas de salida en la ilustración anterior.</span><span class="sxs-lookup"><span data-stu-id="db6f7-116">Note the first two lines of output in the preceding illustration.</span></span> <span data-ttu-id="db6f7-117">El <xref:System.Drawing.Font> objeto devuelve un tamaño de 16 y la <xref:System.Drawing.FontFamily> objeto devuelve un alto de em de 2.048.</span><span class="sxs-lookup"><span data-stu-id="db6f7-117">The <xref:System.Drawing.Font> object returns a size of 16, and the <xref:System.Drawing.FontFamily> object returns an em height of 2,048.</span></span> <span data-ttu-id="db6f7-118">Estos dos números (16 y 2.048) son la clave para convertir entre las unidades de diseño de fuente y las unidades (en este caso, píxeles) de la <xref:System.Drawing.Font> objeto.</span><span class="sxs-lookup"><span data-stu-id="db6f7-118">These two numbers (16 and 2,048) are the key to converting between font design units and the units (in this case pixels) of the <xref:System.Drawing.Font> object.</span></span>  
  
 <span data-ttu-id="db6f7-119">Por ejemplo, puede convertir el ascenso de unidades de diseño con los píxeles como sigue:</span><span class="sxs-lookup"><span data-stu-id="db6f7-119">For example, you can convert the ascent from design units to pixels as follows:</span></span>  
  
 <span data-ttu-id="db6f7-120">![Texto de las fuentes](../../../../docs/framework/winforms/advanced/media/fontstext9.png "FontsText9")</span><span class="sxs-lookup"><span data-stu-id="db6f7-120">![Fonts Text](../../../../docs/framework/winforms/advanced/media/fontstext9.png "FontsText9")</span></span>  
  
 <span data-ttu-id="db6f7-121">El código siguiente sitúa el texto verticalmente estableciendo el <xref:System.Drawing.PointF.Y%2A> miembro de datos de un <xref:System.Drawing.PointF> objeto.</span><span class="sxs-lookup"><span data-stu-id="db6f7-121">The following code positions text vertically by setting the <xref:System.Drawing.PointF.Y%2A> data member of a <xref:System.Drawing.PointF> object.</span></span> <span data-ttu-id="db6f7-122">La coordenada y se incrementa en `font.Height` para cada nueva línea de texto.</span><span class="sxs-lookup"><span data-stu-id="db6f7-122">The y-coordinate is increased by `font.Height` for each new line of text.</span></span> <span data-ttu-id="db6f7-123">El <xref:System.Drawing.Font.Height%2A> propiedad de un <xref:System.Drawing.Font> objeto devuelve el interlineado (en píxeles) para ese <xref:System.Drawing.Font> objeto.</span><span class="sxs-lookup"><span data-stu-id="db6f7-123">The <xref:System.Drawing.Font.Height%2A> property of a <xref:System.Drawing.Font> object returns the line spacing (in pixels) for that particular <xref:System.Drawing.Font> object.</span></span> <span data-ttu-id="db6f7-124">En este ejemplo, el número devuelto por <xref:System.Drawing.Font.Height%2A> es 19.</span><span class="sxs-lookup"><span data-stu-id="db6f7-124">In this example, the number returned by <xref:System.Drawing.Font.Height%2A> is 19.</span></span> <span data-ttu-id="db6f7-125">Tenga en cuenta que es el mismo que el número (redondeado a un entero) obtenido mediante la conversión de la métrica de espaciado de línea en píxeles.</span><span class="sxs-lookup"><span data-stu-id="db6f7-125">Note that this is the same as the number (rounded up to an integer) obtained by converting the line-spacing metric to pixels.</span></span>  
  
 <span data-ttu-id="db6f7-126">Tenga en cuenta que el alto de Em. (también llamado tamaño o tamaño em) no es la suma del ascenso y del descenso.</span><span class="sxs-lookup"><span data-stu-id="db6f7-126">Note that the em height (also called size or em size) is not the sum of the ascent and the descent.</span></span> <span data-ttu-id="db6f7-127">La suma del ascenso y del descenso se denomina el alto de celda.</span><span class="sxs-lookup"><span data-stu-id="db6f7-127">The sum of the ascent and the descent is called the cell height.</span></span> <span data-ttu-id="db6f7-128">El alto de celda menos el espacio interno es igual que el alto de Em.</span><span class="sxs-lookup"><span data-stu-id="db6f7-128">The cell height minus the internal leading is equal to the em height.</span></span> <span data-ttu-id="db6f7-129">El alto de celda más el interlineado externo es igual que el espaciado de línea.</span><span class="sxs-lookup"><span data-stu-id="db6f7-129">The cell height plus the external leading is equal to the line spacing.</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#71](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.FontsAndText#71](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="db6f7-130">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="db6f7-130">Compiling the Code</span></span>  
 <span data-ttu-id="db6f7-131">El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="db6f7-131">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db6f7-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="db6f7-132">See Also</span></span>  
 [<span data-ttu-id="db6f7-133">Gráficos y dibujos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="db6f7-133">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [<span data-ttu-id="db6f7-134">Utilizar fuentes y texto</span><span class="sxs-lookup"><span data-stu-id="db6f7-134">Using Fonts and Text</span></span>](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
