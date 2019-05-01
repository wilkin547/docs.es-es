---
title: Procedimiento para dibujar líneas opacas y semitransparentes
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drawing [Windows Forms], lines
- transparency [Windows Forms], lines
- lines [Windows Forms], drawing alpha blended
- alpha blending [Windows Forms], drawing lines
ms.assetid: 8f2508af-f495-4223-b5cc-646cbbb520eb
ms.openlocfilehash: 7408722dc13e83828cfca3f0615a2730e3c53461
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62004034"
---
# <a name="how-to-draw-opaque-and-semitransparent-lines"></a><span data-ttu-id="d192e-102">Procedimiento para dibujar líneas opacas y semitransparentes</span><span class="sxs-lookup"><span data-stu-id="d192e-102">How to: Draw Opaque and Semitransparent Lines</span></span>
<span data-ttu-id="d192e-103">Al dibujar una línea, debe pasar un objeto <xref:System.Drawing.Pen> al método <xref:System.Drawing.Graphics.DrawLine%2A> de la clase <xref:System.Drawing.Graphics>.</span><span class="sxs-lookup"><span data-stu-id="d192e-103">When you draw a line, you must pass a <xref:System.Drawing.Pen> object to the <xref:System.Drawing.Graphics.DrawLine%2A> method of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="d192e-104">Uno de los parámetros del constructor <xref:System.Drawing.Pen.%23ctor%2A> es un objeto <xref:System.Drawing.Color>.</span><span class="sxs-lookup"><span data-stu-id="d192e-104">One of the parameters of the <xref:System.Drawing.Pen.%23ctor%2A> constructor is a <xref:System.Drawing.Color> object.</span></span> <span data-ttu-id="d192e-105">Para dibujar una línea opaca, establezca el componente alfa del color en 255.</span><span class="sxs-lookup"><span data-stu-id="d192e-105">To draw an opaque line, set the alpha component of the color to 255.</span></span> <span data-ttu-id="d192e-106">Para dibujar una línea semitransparente, establezca el componente alfa en cualquier valor entre 1 y 254.</span><span class="sxs-lookup"><span data-stu-id="d192e-106">To draw a semitransparent line, set the alpha component to any value from 1 through 254.</span></span>  
  
 <span data-ttu-id="d192e-107">Cuando se dibuja una línea semitransparente sobre un fondo, el color de la línea se mezcla con los colores del fondo.</span><span class="sxs-lookup"><span data-stu-id="d192e-107">When you draw a semitransparent line over a background, the color of the line is blended with the colors of the background.</span></span> <span data-ttu-id="d192e-108">El componente alfa especifica cómo se mezclan los colores de la línea y del fondo; los valores alfa cercanos a 0 dan más importancia a los colores de fondo y los cercanos a 255 dan más importancia al color de la línea.</span><span class="sxs-lookup"><span data-stu-id="d192e-108">The alpha component specifies how the line and background colors are mixed; alpha values near 0 place more weight on the background colors, and alpha values near 255 place more weight on the line color.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d192e-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d192e-109">Example</span></span>  
 <span data-ttu-id="d192e-110">En el ejemplo siguiente se dibuja un mapa de bits y, después, se dibujan tres líneas que usan el mapa de bits como fondo.</span><span class="sxs-lookup"><span data-stu-id="d192e-110">The following example draws a bitmap and then draws three lines that use the bitmap as a background.</span></span> <span data-ttu-id="d192e-111">La primera línea usa un componente alfa de 255, por lo que es opaca.</span><span class="sxs-lookup"><span data-stu-id="d192e-111">The first line uses an alpha component of 255, so it is opaque.</span></span> <span data-ttu-id="d192e-112">La segunda y tercera líneas usan un componente alfa de 128, por lo que son semitransparentes; puede ver la imagen de fondo a través de las líneas.</span><span class="sxs-lookup"><span data-stu-id="d192e-112">The second and third lines use an alpha component of 128, so they are semitransparent; you can see the background image through the lines.</span></span> <span data-ttu-id="d192e-113">La instrucción que establece la propiedad <xref:System.Drawing.Graphics.CompositingQuality%2A> hace que la mezcla de la tercera línea se realice conjuntamente con la corrección gamma.</span><span class="sxs-lookup"><span data-stu-id="d192e-113">The statement that sets the <xref:System.Drawing.Graphics.CompositingQuality%2A> property causes the blending for the third line to be done in conjunction with gamma correction.</span></span>  
  
 [!code-csharp[System.Drawing.AlphaBlending#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.AlphaBlending#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#11)]  
  
 <span data-ttu-id="d192e-114">La siguiente ilustración muestra la salida del código siguiente:</span><span class="sxs-lookup"><span data-stu-id="d192e-114">The following illustration shows the output of the following code:</span></span>  
  
 ![Ilustración que muestra la salida opaca y semitransparente](./media/how-to-draw-opaque-and-semitransparent-lines/opaque-semitransparent-lines.png)  

## <a name="compiling-the-code"></a><span data-ttu-id="d192e-116">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="d192e-116">Compiling the Code</span></span>  
 <span data-ttu-id="d192e-117">El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs>`e`, que es un parámetro del controlador de eventos <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="d192e-117">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d192e-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="d192e-118">See also</span></span>

- [<span data-ttu-id="d192e-119">Líneas y rellenos con combinación alfa</span><span class="sxs-lookup"><span data-stu-id="d192e-119">Alpha Blending Lines and Fills</span></span>](alpha-blending-lines-and-fills.md)
- [<span data-ttu-id="d192e-120">Cómo: Proporcionar un fondo transparente a un Control</span><span class="sxs-lookup"><span data-stu-id="d192e-120">How to: Give Your Control a Transparent Background</span></span>](../controls/how-to-give-your-control-a-transparent-background.md)
- [<span data-ttu-id="d192e-121">Cómo: Dibujar con pinceles opacos y semitransparentes</span><span class="sxs-lookup"><span data-stu-id="d192e-121">How to: Draw with Opaque and Semitransparent Brushes</span></span>](how-to-draw-with-opaque-and-semitransparent-brushes.md)
