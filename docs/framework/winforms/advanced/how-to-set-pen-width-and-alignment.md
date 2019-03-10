---
title: Filtrar Establecer el ancho de lápiz y la alineación
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pens [Windows Forms], setting width
- pens [Windows Forms], setting alignment
ms.assetid: a202af36-4d31-4401-a126-b232f51db581
ms.openlocfilehash: e82f406b4fdca93df7a811eea5506846d56fda28
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57703054"
---
# <a name="how-to-set-pen-width-and-alignment"></a><span data-ttu-id="a5fa8-102">Filtrar Establecer el ancho de lápiz y la alineación</span><span class="sxs-lookup"><span data-stu-id="a5fa8-102">How to: Set Pen Width and Alignment</span></span>
<span data-ttu-id="a5fa8-103">Cuando creas un <xref:System.Drawing.Pen>, puede proporcionar el ancho del lápiz como uno de los argumentos al constructor.</span><span class="sxs-lookup"><span data-stu-id="a5fa8-103">When you create a <xref:System.Drawing.Pen>, you can supply the pen width as one of the arguments to the constructor.</span></span> <span data-ttu-id="a5fa8-104">También puede cambiar el ancho del lápiz con el <xref:System.Drawing.Pen.Width%2A> propiedad de la <xref:System.Drawing.Pen> clase.</span><span class="sxs-lookup"><span data-stu-id="a5fa8-104">You can also change the pen width with the <xref:System.Drawing.Pen.Width%2A> property of the <xref:System.Drawing.Pen> class.</span></span>  
  
 <span data-ttu-id="a5fa8-105">Una línea teórica tiene un ancho de 0.</span><span class="sxs-lookup"><span data-stu-id="a5fa8-105">A theoretical line has a width of 0.</span></span> <span data-ttu-id="a5fa8-106">Cuando se dibuja una línea de 1 píxel de ancho, los píxeles se centran en la línea teórica.</span><span class="sxs-lookup"><span data-stu-id="a5fa8-106">When you draw a line that is 1 pixel wide, the pixels are centered on the theoretical line.</span></span> <span data-ttu-id="a5fa8-107">Si dibuja una línea que tiene más de un píxel de ancho, los píxeles están centrados en la línea teórica o aparecen al lado de la línea teórica.</span><span class="sxs-lookup"><span data-stu-id="a5fa8-107">If you draw a line that is more than one pixel wide, the pixels are either centered on the theoretical line or appear to one side of the theoretical line.</span></span> <span data-ttu-id="a5fa8-108">Puede establecer la propiedad de alineación de un <xref:System.Drawing.Pen> para determinar cómo se ubicarán los píxeles dibujados con ese lápiz en relación con las líneas teóricas.</span><span class="sxs-lookup"><span data-stu-id="a5fa8-108">You can set the pen alignment property of a <xref:System.Drawing.Pen> to determine how the pixels drawn with that pen will be positioned relative to theoretical lines.</span></span>  
  
 <span data-ttu-id="a5fa8-109">Los valores <xref:System.Drawing.Drawing2D.PenAlignment.Center>, <xref:System.Drawing.Drawing2D.PenAlignment.Outset>, y <xref:System.Drawing.Drawing2D.PenAlignment.Inset> que aparecen en los siguientes ejemplos de código son miembros de la <xref:System.Drawing.Drawing2D.PenAlignment> enumeración.</span><span class="sxs-lookup"><span data-stu-id="a5fa8-109">The values <xref:System.Drawing.Drawing2D.PenAlignment.Center>, <xref:System.Drawing.Drawing2D.PenAlignment.Outset>, and <xref:System.Drawing.Drawing2D.PenAlignment.Inset> that appear in the following code examples are members of the <xref:System.Drawing.Drawing2D.PenAlignment> enumeration.</span></span>  
  
 <span data-ttu-id="a5fa8-110">En el ejemplo de código siguiente se dibuja una línea dos veces: una vez con un lápiz negro de ancho 1 y otra vez con un lápiz verde de ancho 10.</span><span class="sxs-lookup"><span data-stu-id="a5fa8-110">The following code example draws a line twice: once with a black pen of width 1 and once with a green pen of width 10.</span></span>  
  
### <a name="to-vary-the-width-of-a-pen"></a><span data-ttu-id="a5fa8-111">Para variar el ancho de un lápiz</span><span class="sxs-lookup"><span data-stu-id="a5fa8-111">To vary the width of a pen</span></span>  
  
-   <span data-ttu-id="a5fa8-112">Establezca el valor de la <xref:System.Drawing.Pen.Alignment%2A> propiedad <xref:System.Drawing.Drawing2D.PenAlignment.Center> (predeterminado) para especificar que los píxeles que se dibuja con el lápiz verde se centrará en la línea teórica.</span><span class="sxs-lookup"><span data-stu-id="a5fa8-112">Set the value of the <xref:System.Drawing.Pen.Alignment%2A> property to <xref:System.Drawing.Drawing2D.PenAlignment.Center> (the default) to specify that pixels drawn with the green pen will be centered on the theoretical line.</span></span> <span data-ttu-id="a5fa8-113">La siguiente ilustración muestra la línea resultante.</span><span class="sxs-lookup"><span data-stu-id="a5fa8-113">The following illustration shows the resulting line.</span></span>  
  
     <span data-ttu-id="a5fa8-114">![Lápices](./media/pens1a.gif "pens1A")</span><span class="sxs-lookup"><span data-stu-id="a5fa8-114">![Pens](./media/pens1a.gif "pens1A")</span></span>  
  
     <span data-ttu-id="a5fa8-115">En el ejemplo de código siguiente se dibuja un rectángulo dos veces: una vez con un lápiz negro de ancho 1 y otra vez con un lápiz verde de ancho 10.</span><span class="sxs-lookup"><span data-stu-id="a5fa8-115">The following code example draws a rectangle twice: once with a black pen of width 1 and once with a green pen of width 10.</span></span>  
  
     [!code-csharp[System.Drawing.UsingAPen#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#41)]
     [!code-vb[System.Drawing.UsingAPen#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#41)]  
  
### <a name="to-change-the-alignment-of-a-pen"></a><span data-ttu-id="a5fa8-116">Para cambiar la alineación de un lápiz</span><span class="sxs-lookup"><span data-stu-id="a5fa8-116">To change the alignment of a pen</span></span>  
  
-   <span data-ttu-id="a5fa8-117">Establezca el valor de la <xref:System.Drawing.Pen.Alignment%2A> propiedad <xref:System.Drawing.Drawing2D.PenAlignment.Center> para especificar que los píxeles que se dibuja con el lápiz verde se centrará en los límites del rectángulo.</span><span class="sxs-lookup"><span data-stu-id="a5fa8-117">Set the value of the <xref:System.Drawing.Pen.Alignment%2A> property to <xref:System.Drawing.Drawing2D.PenAlignment.Center> to specify that the pixels drawn with the green pen will be centered on the boundary of the rectangle.</span></span>  
  
     <span data-ttu-id="a5fa8-118">La siguiente ilustración muestra el rectángulo resultante.</span><span class="sxs-lookup"><span data-stu-id="a5fa8-118">The following illustration shows the resulting rectangle.</span></span>  
  
     <span data-ttu-id="a5fa8-119">![Lápices](./media/pens2.gif "pens2")</span><span class="sxs-lookup"><span data-stu-id="a5fa8-119">![Pens](./media/pens2.gif "pens2")</span></span>  
  
     [!code-csharp[System.Drawing.UsingAPen#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#42)]
     [!code-vb[System.Drawing.UsingAPen#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#42)]  
  
### <a name="to-create-an-inset-pen"></a><span data-ttu-id="a5fa8-120">Para crear un lápiz de bajorrelieve</span><span class="sxs-lookup"><span data-stu-id="a5fa8-120">To create an inset pen</span></span>  
  
-   <span data-ttu-id="a5fa8-121">Cambiar la alineación del lápiz verde modificando la tercera instrucción en el ejemplo de código anterior como sigue:</span><span class="sxs-lookup"><span data-stu-id="a5fa8-121">Change the green pen's alignment by modifying the third statement in the preceding code example as follows:</span></span>  
  
     [!code-csharp[System.Drawing.UsingAPen#43](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#43)]
     [!code-vb[System.Drawing.UsingAPen#43](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#43)]  
  
     <span data-ttu-id="a5fa8-122">Los píxeles en la línea verde ancha aparecen ahora en el interior del rectángulo tal como se muestra en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="a5fa8-122">Now the pixels in the wide green line appear on the inside of the rectangle as shown in the following illustration.</span></span>  
  
     <span data-ttu-id="a5fa8-123">![Lápices](./media/pens3.gif "pens3")</span><span class="sxs-lookup"><span data-stu-id="a5fa8-123">![Pens](./media/pens3.gif "pens3")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5fa8-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="a5fa8-124">See also</span></span>
- [<span data-ttu-id="a5fa8-125">Utilizar lápiz para dibujar líneas y formas</span><span class="sxs-lookup"><span data-stu-id="a5fa8-125">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
- [<span data-ttu-id="a5fa8-126">Gráficos y dibujos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a5fa8-126">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
