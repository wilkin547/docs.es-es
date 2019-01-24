---
title: Procedimiento Usar el modo de composición para controlar la mezcla alfa
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- alpha blending [Windows Forms], compositing
- colors [Windows Forms], blending
- colors [Windows Forms], controlling transparency
ms.assetid: f331df2d-b395-4b0a-95be-24fec8c9bbb5
ms.openlocfilehash: 2e00b0b9b22bc8dcdd1c63494f1bc5854bc4f033
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54632015"
---
# <a name="how-to-use-compositing-mode-to-control-alpha-blending"></a><span data-ttu-id="055c2-102">Procedimiento Usar el modo de composición para controlar la mezcla alfa</span><span class="sxs-lookup"><span data-stu-id="055c2-102">How to: Use Compositing Mode to Control Alpha Blending</span></span>
<span data-ttu-id="055c2-103">Puede haber ocasiones en que desee crear un mapa de bits fuera de la pantalla que tiene las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="055c2-103">There may be times when you want to create an off-screen bitmap that has the following characteristics:</span></span>  
  
-   <span data-ttu-id="055c2-104">Colores tienen valores alfabéticos que son menos de 255.</span><span class="sxs-lookup"><span data-stu-id="055c2-104">Colors have alpha values that are less than 255.</span></span>  
  
-   <span data-ttu-id="055c2-105">Colores no son alfabéticos mezclan entre sí al crear el mapa de bits.</span><span class="sxs-lookup"><span data-stu-id="055c2-105">Colors are not alpha blended with each other as you create the bitmap.</span></span>  
  
-   <span data-ttu-id="055c2-106">Cuando se muestra el mapa de bits terminado, los colores del mapa de bits son una combinación con los colores de fondo de la pantalla alfa.</span><span class="sxs-lookup"><span data-stu-id="055c2-106">When you display the finished bitmap, colors in the bitmap are alpha blended with the background colors on the display device.</span></span>  
  
 <span data-ttu-id="055c2-107">Para crear un mapa de bits, construya un espacio en blanco <xref:System.Drawing.Bitmap> objeto y, a continuación, construya un <xref:System.Drawing.Graphics> objeto basado en ese mapa de bits.</span><span class="sxs-lookup"><span data-stu-id="055c2-107">To create such a bitmap, construct a blank <xref:System.Drawing.Bitmap> object, and then construct a <xref:System.Drawing.Graphics> object based on that bitmap.</span></span> <span data-ttu-id="055c2-108">Establezca el modo de composición de la <xref:System.Drawing.Graphics> objeto <xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="055c2-108">Set the compositing mode of the <xref:System.Drawing.Graphics> object to <xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy?displayProperty=nameWithType>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="055c2-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="055c2-109">Example</span></span>  
 <span data-ttu-id="055c2-110">En el ejemplo siguiente se crea un <xref:System.Drawing.Graphics> objeto según un <xref:System.Drawing.Bitmap> objeto.</span><span class="sxs-lookup"><span data-stu-id="055c2-110">The following example creates a <xref:System.Drawing.Graphics> object based on a <xref:System.Drawing.Bitmap> object.</span></span> <span data-ttu-id="055c2-111">El código usa el <xref:System.Drawing.Graphics> objeto junto con dos pinceles semitransparentes (alfa = 160) para pintar en el mapa de bits.</span><span class="sxs-lookup"><span data-stu-id="055c2-111">The code uses the <xref:System.Drawing.Graphics> object along with two semitransparent brushes (alpha = 160) to paint on the bitmap.</span></span> <span data-ttu-id="055c2-112">El código rellena una elipse roja y una elipse verde utilizando los pinceles semitransparentes.</span><span class="sxs-lookup"><span data-stu-id="055c2-112">The code fills a red ellipse and a green ellipse using the semitransparent brushes.</span></span> <span data-ttu-id="055c2-113">La elipse verde superpone el rojo, pero no se mezcla con el color rojo, verde porque el modo de composición de la <xref:System.Drawing.Graphics> objeto se establece en <xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy>.</span><span class="sxs-lookup"><span data-stu-id="055c2-113">The green ellipse overlaps the red ellipse, but the green is not blended with the red because the compositing mode of the <xref:System.Drawing.Graphics> object is set to <xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy>.</span></span>  
  
 <span data-ttu-id="055c2-114">El código dibuja el mapa de bits en la pantalla dos veces: una vez en un fondo blanco y una vez en un fondo de varios colores.</span><span class="sxs-lookup"><span data-stu-id="055c2-114">The code draws the bitmap on the screen twice: once on a white background and once on a multicolored background.</span></span> <span data-ttu-id="055c2-115">Los píxeles del mapa de bits que forman parte de las dos elipses tienen un componente alfa de 160, por lo que los puntos suspensivos se mezclan con los colores de fondo en la pantalla.</span><span class="sxs-lookup"><span data-stu-id="055c2-115">The pixels in the bitmap that are part of the two ellipses have an alpha component of 160, so the ellipses are blended with the background colors on the screen.</span></span>  
  
 <span data-ttu-id="055c2-116">La siguiente ilustración muestra el resultado del ejemplo de código.</span><span class="sxs-lookup"><span data-stu-id="055c2-116">The following illustration shows the output of the code example.</span></span> <span data-ttu-id="055c2-117">Tenga en cuenta que los puntos suspensivos se mezclan con el fondo, pero no se mezclan entre sí.</span><span class="sxs-lookup"><span data-stu-id="055c2-117">Note that the ellipses are blended with the background, but they are not blended with each other.</span></span>  
  
 <span data-ttu-id="055c2-118">![Copia de origen](../../../../docs/framework/winforms/advanced/media/sourcecopy.png "sourcecopy")</span><span class="sxs-lookup"><span data-stu-id="055c2-118">![Source Copy](../../../../docs/framework/winforms/advanced/media/sourcecopy.png "sourcecopy")</span></span>  
  
 <span data-ttu-id="055c2-119">El ejemplo de código contiene esta instrucción:</span><span class="sxs-lookup"><span data-stu-id="055c2-119">The code example contains this statement:</span></span>  
  
 [!code-csharp[System.Drawing.AlphaBlending#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.AlphaBlending#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#41)]  
  
 <span data-ttu-id="055c2-120">Si desea que los puntos suspensivos para que se mezclan entre sí, así como con el fondo, cambie esa instrucción a lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="055c2-120">If you want the ellipses to be blended with each other as well as with the background, change that statement to the following:</span></span>  
  
 [!code-csharp[System.Drawing.AlphaBlending#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#42)]
 [!code-vb[System.Drawing.AlphaBlending#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#42)]  
  
 <span data-ttu-id="055c2-121">La siguiente ilustración muestra el resultado del código revisado.</span><span class="sxs-lookup"><span data-stu-id="055c2-121">The following illustration shows the output of the revised code.</span></span>  
  
 <span data-ttu-id="055c2-122">![Origen a través de](../../../../docs/framework/winforms/advanced/media/sourceover.png "sourceover")</span><span class="sxs-lookup"><span data-stu-id="055c2-122">![Source Over](../../../../docs/framework/winforms/advanced/media/sourceover.png "sourceover")</span></span>  
  
 [!code-csharp[System.Drawing.AlphaBlending#43](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#43)]
 [!code-vb[System.Drawing.AlphaBlending#43](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#43)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="055c2-123">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="055c2-123">Compiling the Code</span></span>  
 <span data-ttu-id="055c2-124">El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="055c2-124">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="055c2-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="055c2-125">See also</span></span>
- <xref:System.Drawing.Color.FromArgb%2A>
- [<span data-ttu-id="055c2-126">Líneas y rellenos con combinación alfa</span><span class="sxs-lookup"><span data-stu-id="055c2-126">Alpha Blending Lines and Fills</span></span>](../../../../docs/framework/winforms/advanced/alpha-blending-lines-and-fills.md)
