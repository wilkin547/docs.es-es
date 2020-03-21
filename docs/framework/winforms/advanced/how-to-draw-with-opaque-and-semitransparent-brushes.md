---
title: 'Cómo: Dibujar con pinceles opacos y semitransparentes'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- semi-transparent shapes [Windows Forms], drawing
- transparency [Windows Forms], semi-transparent shapes
- alpha blending [Windows Forms], brush
- brushes [Windows Forms], using semi-transparent
ms.assetid: a4f6f6b8-3bc8-440a-84af-d62ef0f8ff40
ms.openlocfilehash: 1e48bbd563f6377380848949325962b568fa432c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142412"
---
# <a name="how-to-draw-with-opaque-and-semitransparent-brushes"></a><span data-ttu-id="2a1df-102">Cómo: Dibujar con pinceles opacos y semitransparentes</span><span class="sxs-lookup"><span data-stu-id="2a1df-102">How to: Draw with Opaque and Semitransparent Brushes</span></span>
<span data-ttu-id="2a1df-103">Cuando se rellena una forma, se debe pasar un objeto <xref:System.Drawing.Brush> en uno de los métodos de relleno de la clase <xref:System.Drawing.Graphics>.</span><span class="sxs-lookup"><span data-stu-id="2a1df-103">When you fill a shape, you must pass a <xref:System.Drawing.Brush> object to one of the fill methods of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="2a1df-104">El único parámetro del constructor <xref:System.Drawing.SolidBrush.%23ctor%2A> es un objeto <xref:System.Drawing.Color>.</span><span class="sxs-lookup"><span data-stu-id="2a1df-104">The one parameter of the <xref:System.Drawing.SolidBrush.%23ctor%2A> constructor is a <xref:System.Drawing.Color> object.</span></span> <span data-ttu-id="2a1df-105">Para rellenar una forma opaca, establezca el componente alfa del color en 255.</span><span class="sxs-lookup"><span data-stu-id="2a1df-105">To fill an opaque shape, set the alpha component of the color to 255.</span></span> <span data-ttu-id="2a1df-106">Para rellenar una forma semitransparente, establezca el componente alfa en cualquier valor entre 1 y 254.</span><span class="sxs-lookup"><span data-stu-id="2a1df-106">To fill a semitransparent shape, set the alpha component to any value from 1 through 254.</span></span>  
  
 <span data-ttu-id="2a1df-107">Cuando se rellena una forma semitransparente, el color de la forma se mezcla con los colores del fondo.</span><span class="sxs-lookup"><span data-stu-id="2a1df-107">When you fill a semitransparent shape, the color of the shape is blended with the colors of the background.</span></span> <span data-ttu-id="2a1df-108">El componente alfa especifica cómo se mezclan los colores de la forma y del fondo; los valores alfa cercanos a 0 dan más importancia a los colores de fondo y los cercanos a 255 dan más importancia al color de la forma.</span><span class="sxs-lookup"><span data-stu-id="2a1df-108">The alpha component specifies how the shape and background colors are mixed; alpha values near 0 place more weight on the background colors, and alpha values near 255 place more weight on the shape color.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2a1df-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2a1df-109">Example</span></span>  
 <span data-ttu-id="2a1df-110">En el ejemplo siguiente se dibuja un mapa de bits y después se rellenan tres elipses que se superponen al mapa de bits.</span><span class="sxs-lookup"><span data-stu-id="2a1df-110">The following example draws a bitmap and then fills three ellipses that overlap the bitmap.</span></span> <span data-ttu-id="2a1df-111">La primera elipse usa un componente alfa de 255, por lo que es opaca.</span><span class="sxs-lookup"><span data-stu-id="2a1df-111">The first ellipse uses an alpha component of 255, so it is opaque.</span></span> <span data-ttu-id="2a1df-112">La segunda y tercera elipses usan un componente alfa de 128, por lo que son semitransparentes; puede ver la imagen de fondo a través de las elipses.</span><span class="sxs-lookup"><span data-stu-id="2a1df-112">The second and third ellipses use an alpha component of 128, so they are semitransparent; you can see the background image through the ellipses.</span></span> <span data-ttu-id="2a1df-113">La instrucción que establece la propiedad <xref:System.Drawing.Graphics.CompositingQuality%2A> hace que la mezcla de la tercera elipse se realice conjuntamente con la corrección gamma.</span><span class="sxs-lookup"><span data-stu-id="2a1df-113">The call that sets the <xref:System.Drawing.Graphics.CompositingQuality%2A> property causes the blending for the third ellipse to be done in conjunction with gamma correction.</span></span>  

 [!code-csharp[System.Drawing.AlphaBlending#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.AlphaBlending#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#31)]  

 <span data-ttu-id="2a1df-114">La siguiente ilustración muestra la salida del código siguiente:</span><span class="sxs-lookup"><span data-stu-id="2a1df-114">The following illustration shows the output of the following code:</span></span>
  
 ![Ilustración que muestra salida opaca y semitransparente.](./media/how-to-draw-with-opaque-and-semitransparent-brushes/compositingquality-ellipse-semitransparent.png)  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2a1df-116">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="2a1df-116">Compiling the Code</span></span>  
 <span data-ttu-id="2a1df-117">El ejemplo anterior está diseñado para su uso <xref:System.Windows.Forms.PaintEventArgs> `e`con formularios Windows <xref:System.Windows.Forms.PaintEventHandler>Forms y requiere , que es un parámetro de .</span><span class="sxs-lookup"><span data-stu-id="2a1df-117">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a1df-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2a1df-118">See also</span></span>

- [<span data-ttu-id="2a1df-119">Gráficos y dibujos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2a1df-119">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="2a1df-120">Líneas y rellenos con mezcla alfa</span><span class="sxs-lookup"><span data-stu-id="2a1df-120">Alpha Blending Lines and Fills</span></span>](alpha-blending-lines-and-fills.md)
- [<span data-ttu-id="2a1df-121">Cómo: Proporcionar un fondo transparente a un control</span><span class="sxs-lookup"><span data-stu-id="2a1df-121">How to: Give Your Control a Transparent Background</span></span>](../controls/how-to-give-your-control-a-transparent-background.md)
- [<span data-ttu-id="2a1df-122">Cómo: Dibujar líneas opacas y semitransparentes</span><span class="sxs-lookup"><span data-stu-id="2a1df-122">How to: Draw Opaque and Semitransparent Lines</span></span>](how-to-draw-opaque-and-semitransparent-lines.md)
