---
title: "Cómo: Unir líneas"
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
- miter line join style
- bevel line join style
- line join
- drawing [Windows Forms], joining lines
- GraphicsPath object
- round line join style
- lines [Windows Forms], joining
- graphics [Windows Forms], joining lines
ms.assetid: 9fc480c2-3c75-4fd1-8ab5-296a99e820e2
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f02da181d66f7bb26a8414782e42eff2570e6918
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-join-lines"></a><span data-ttu-id="12874-102">Cómo: Unir líneas</span><span class="sxs-lookup"><span data-stu-id="12874-102">How to: Join Lines</span></span>
<span data-ttu-id="12874-103">Una unión de líneas es el área común que está formado por dos líneas cuyos extremos se encuentran o se superponen.</span><span class="sxs-lookup"><span data-stu-id="12874-103">A line join is the common area that is formed by two lines whose ends meet or overlap.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="12874-104">proporciona tres estilos de unión de línea: ángulo, bisel y redondo.</span><span class="sxs-lookup"><span data-stu-id="12874-104"> provides three line join styles: miter, bevel, and round.</span></span> <span data-ttu-id="12874-105">Estilo de unión de línea es una propiedad de la <xref:System.Drawing.Pen> clase.</span><span class="sxs-lookup"><span data-stu-id="12874-105">Line join style is a property of the <xref:System.Drawing.Pen> class.</span></span> <span data-ttu-id="12874-106">Cuando se especifica un estilo de unión de línea para un <xref:System.Drawing.Pen> objeto, que se aplicará a todas las líneas conectadas en cualquier estilo de unión <xref:System.Drawing.Drawing2D.GraphicsPath> objeto dibujado con ese lápiz.</span><span class="sxs-lookup"><span data-stu-id="12874-106">When you specify a line join style for a <xref:System.Drawing.Pen> object, that join style will be applied to all the connected lines in any <xref:System.Drawing.Drawing2D.GraphicsPath> object drawn using that pen.</span></span>  
  
 <span data-ttu-id="12874-107">La ilustración siguiente muestra los resultados del ejemplo de unión de línea biselada.</span><span class="sxs-lookup"><span data-stu-id="12874-107">The following illustration shows the results of the beveled line join example.</span></span>  
  
 <span data-ttu-id="12874-108">![Lápices](../../../../docs/framework/winforms/advanced/media/pens5.gif "pens5")</span><span class="sxs-lookup"><span data-stu-id="12874-108">![Pens](../../../../docs/framework/winforms/advanced/media/pens5.gif "pens5")</span></span>  
  
## <a name="example"></a><span data-ttu-id="12874-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="12874-109">Example</span></span>  
 <span data-ttu-id="12874-110">Puede especificar el estilo de unión de línea mediante la <xref:System.Drawing.Pen.LineJoin%2A> propiedad de la <xref:System.Drawing.Pen> clase.</span><span class="sxs-lookup"><span data-stu-id="12874-110">You can specify the line join style by using the <xref:System.Drawing.Pen.LineJoin%2A> property of the <xref:System.Drawing.Pen> class.</span></span> <span data-ttu-id="12874-111">En el ejemplo se muestra una unión de línea biselada entre una línea horizontal y una línea vertical.</span><span class="sxs-lookup"><span data-stu-id="12874-111">The example demonstrates a beveled line join between a horizontal line and a vertical line.</span></span> <span data-ttu-id="12874-112">En el código siguiente, el valor <xref:System.Drawing.Drawing2D.LineJoin.Bevel> asignado a la <xref:System.Drawing.Pen.LineJoin%2A> propiedad es un miembro de la <xref:System.Drawing.Drawing2D.LineJoin> enumeración.</span><span class="sxs-lookup"><span data-stu-id="12874-112">In the following code, the value <xref:System.Drawing.Drawing2D.LineJoin.Bevel> assigned to the <xref:System.Drawing.Pen.LineJoin%2A> property is a member of the <xref:System.Drawing.Drawing2D.LineJoin> enumeration.</span></span> <span data-ttu-id="12874-113">Los demás miembros de la <xref:System.Drawing.Drawing2D.LineJoin> enumeración son <xref:System.Drawing.Drawing2D.LineJoin.Miter> y <xref:System.Drawing.Drawing2D.LineJoin.Round>.</span><span class="sxs-lookup"><span data-stu-id="12874-113">The other members of the <xref:System.Drawing.Drawing2D.LineJoin> enumeration are <xref:System.Drawing.Drawing2D.LineJoin.Miter> and <xref:System.Drawing.Drawing2D.LineJoin.Round>.</span></span>  
  
 [!code-csharp[System.Drawing.UsingAPen#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingAPen#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="12874-114">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="12874-114">Compiling the Code</span></span>  
 <span data-ttu-id="12874-115">El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro del controlador de eventos <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="12874-115">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12874-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="12874-116">See Also</span></span>  
 [<span data-ttu-id="12874-117">Utilizar lápiz para dibujar líneas y formas</span><span class="sxs-lookup"><span data-stu-id="12874-117">Using a Pen to Draw Lines and Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
