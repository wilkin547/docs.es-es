---
title: Procedimiento para aplicar corrección gamma a un degradado
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- gradient brushes [Windows Forms], gamma correction
- gradients [Windows Forms], gamma correction
ms.assetid: da4690e7-5fac-4fd2-b3f0-5cb35c165b92
ms.openlocfilehash: e812e441233c1d29a67dac639048e20a659549f0
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64753569"
---
# <a name="how-to-apply-gamma-correction-to-a-gradient"></a><span data-ttu-id="9d3e7-102">Procedimiento para aplicar corrección gamma a un degradado</span><span class="sxs-lookup"><span data-stu-id="9d3e7-102">How to: Apply Gamma Correction to a Gradient</span></span>
<span data-ttu-id="9d3e7-103">Puede habilitar la corrección gamma de un pincel de degradado lineal estableciendo el pincel <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> propiedad `true`.</span><span class="sxs-lookup"><span data-stu-id="9d3e7-103">You can enable gamma correction for a linear gradient brush by setting the brush's <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> property to `true`.</span></span> <span data-ttu-id="9d3e7-104">Corrección gamma se puede deshabilitar estableciendo la <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> propiedad `false`.</span><span class="sxs-lookup"><span data-stu-id="9d3e7-104">You can disable gamma correction by setting the <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> property to `false`.</span></span> <span data-ttu-id="9d3e7-105">La corrección gamma está deshabilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="9d3e7-105">Gamma correction is disabled by default.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9d3e7-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9d3e7-106">Example</span></span>  

<span data-ttu-id="9d3e7-107">El ejemplo siguiente es un método que se llama desde un control <xref:System.Windows.Forms.Control.Paint> controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="9d3e7-107">The following example is a method that is called from a control's <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="9d3e7-108">En el ejemplo se crea un pincel de degradado lineal y usa ese pincel para rellenar los dos rectángulos.</span><span class="sxs-lookup"><span data-stu-id="9d3e7-108">The example creates a linear gradient brush and uses that brush to fill two rectangles.</span></span> <span data-ttu-id="9d3e7-109">El primer rectángulo se rellena sin corrección gamma y el segundo rectángulo se rellena con la corrección gamma.</span><span class="sxs-lookup"><span data-stu-id="9d3e7-109">The first rectangle is filled without gamma correction, and the second rectangle is filled with gamma correction.</span></span>  
  
 <span data-ttu-id="9d3e7-110">La ilustración siguiente muestra los dos rectángulos rellenos.</span><span class="sxs-lookup"><span data-stu-id="9d3e7-110">The following illustration shows the two filled rectangles.</span></span> <span data-ttu-id="9d3e7-111">El rectángulo superior, que no tiene la corrección gamma, aparece oscuro en el medio.</span><span class="sxs-lookup"><span data-stu-id="9d3e7-111">The top rectangle, which does not have gamma correction, appears dark in the middle.</span></span> <span data-ttu-id="9d3e7-112">El rectángulo inferior, que tiene la corrección gamma, parece que tiene una intensidad más uniforme.</span><span class="sxs-lookup"><span data-stu-id="9d3e7-112">The bottom rectangle, which has gamma correction, appears to have more uniform intensity.</span></span>  
  
 ![Dos rellenos de degradado rectángulos, con y sin la corrección gamma.](./media/how-to-apply-gamma-correction-to-a-gradient/two-rectangles-gamma-gradient.png)  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingaGradientBrush#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9d3e7-114">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="9d3e7-114">Compiling the Code</span></span>  
 <span data-ttu-id="9d3e7-115">El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de la <xref:System.Windows.Forms.Control.Paint> controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="9d3e7-115">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d3e7-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="9d3e7-116">See also</span></span>

- <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=nameWithType>
- [<span data-ttu-id="9d3e7-117">Utilizar un pincel degradado para rellenar formas</span><span class="sxs-lookup"><span data-stu-id="9d3e7-117">Using a Gradient Brush to Fill Shapes</span></span>](using-a-gradient-brush-to-fill-shapes.md)
