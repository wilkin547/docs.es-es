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
ms.openlocfilehash: 7290b7901714e9b71bda3f85f930f5331b8fd4ab
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59077334"
---
# <a name="how-to-apply-gamma-correction-to-a-gradient"></a><span data-ttu-id="88989-102">Procedimiento para aplicar corrección gamma a un degradado</span><span class="sxs-lookup"><span data-stu-id="88989-102">How to: Apply Gamma Correction to a Gradient</span></span>
<span data-ttu-id="88989-103">Puede habilitar la corrección gamma de un pincel de degradado lineal estableciendo el pincel <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> propiedad `true`.</span><span class="sxs-lookup"><span data-stu-id="88989-103">You can enable gamma correction for a linear gradient brush by setting the brush's <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> property to `true`.</span></span> <span data-ttu-id="88989-104">Corrección gamma se puede deshabilitar estableciendo la <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> propiedad `false`.</span><span class="sxs-lookup"><span data-stu-id="88989-104">You can disable gamma correction by setting the <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> property to `false`.</span></span> <span data-ttu-id="88989-105">La corrección gamma está deshabilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="88989-105">Gamma correction is disabled by default.</span></span>  
  
## <a name="example"></a><span data-ttu-id="88989-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="88989-106">Example</span></span>  
 <span data-ttu-id="88989-107">En el ejemplo se crea un pincel de degradado lineal y usa ese pincel para rellenar los dos rectángulos.</span><span class="sxs-lookup"><span data-stu-id="88989-107">The example creates a linear gradient brush and uses that brush to fill two rectangles.</span></span> <span data-ttu-id="88989-108">El primer rectángulo se rellena sin corrección gamma y el segundo rectángulo se rellena con la corrección gamma.</span><span class="sxs-lookup"><span data-stu-id="88989-108">The first rectangle is filled without gamma correction, and the second rectangle is filled with gamma correction.</span></span>  
  
 <span data-ttu-id="88989-109">La ilustración siguiente muestra los dos rectángulos rellenos.</span><span class="sxs-lookup"><span data-stu-id="88989-109">The following illustration shows the two filled rectangles.</span></span> <span data-ttu-id="88989-110">El rectángulo superior, que no tiene la corrección gamma, aparece oscuro en el medio.</span><span class="sxs-lookup"><span data-stu-id="88989-110">The top rectangle, which does not have gamma correction, appears dark in the middle.</span></span> <span data-ttu-id="88989-111">El rectángulo inferior, que tiene la corrección gamma, parece que tiene una intensidad más uniforme.</span><span class="sxs-lookup"><span data-stu-id="88989-111">The bottom rectangle, which has gamma correction, appears to have more uniform intensity.</span></span>  
  
 <span data-ttu-id="88989-112">![Degradado](./media/gammagradient1.png "gammagradient1")</span><span class="sxs-lookup"><span data-stu-id="88989-112">![Gradient](./media/gammagradient1.png "gammagradient1")</span></span>  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingaGradientBrush#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="88989-113">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="88989-113">Compiling the Code</span></span>  
 <span data-ttu-id="88989-114">El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de la <xref:System.Windows.Forms.Control.Paint> controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="88989-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88989-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="88989-115">See also</span></span>

- <xref:System.Drawing.Drawing2D.LinearGradientBrush>
- [<span data-ttu-id="88989-116">Utilizar un pincel degradado para rellenar formas</span><span class="sxs-lookup"><span data-stu-id="88989-116">Using a Gradient Brush to Fill Shapes</span></span>](using-a-gradient-brush-to-fill-shapes.md)
