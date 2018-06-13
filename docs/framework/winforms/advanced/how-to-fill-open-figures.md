---
title: 'Cómo: Rellenar figuras abiertas'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- open figures [Windows Forms], filling
- figures [Windows Forms], filling
ms.assetid: 5a36b0e4-f1f4-46c0-a85a-22ae98491950
ms.openlocfilehash: b7422ae2a4dc4d59fd337ab2294caa0d65057bae
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33521165"
---
# <a name="how-to-fill-open-figures"></a><span data-ttu-id="81805-102">Cómo: Rellenar figuras abiertas</span><span class="sxs-lookup"><span data-stu-id="81805-102">How to: Fill Open Figures</span></span>
<span data-ttu-id="81805-103">Una ruta de acceso se puede rellenar pasando un <xref:System.Drawing.Drawing2D.GraphicsPath> el objeto a la <xref:System.Drawing.Graphics.FillPath%2A> método.</span><span class="sxs-lookup"><span data-stu-id="81805-103">You can fill a path by passing a <xref:System.Drawing.Drawing2D.GraphicsPath> object to the <xref:System.Drawing.Graphics.FillPath%2A> method.</span></span> <span data-ttu-id="81805-104">El <xref:System.Drawing.Graphics.FillPath%2A> método rellena el trazado según el modo de relleno (alternativo o generación) establecido actualmente para la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="81805-104">The <xref:System.Drawing.Graphics.FillPath%2A> method fills the path according to the fill mode (alternate or winding) currently set for the path.</span></span> <span data-ttu-id="81805-105">Si la ruta de acceso tiene figuras abiertas, la ruta de acceso se rellena como si esas figuras estuvieran cerradas.</span><span class="sxs-lookup"><span data-stu-id="81805-105">If the path has any open figures, the path is filled as if those figures were closed.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="81805-106"> cierra una figura dibujando una línea recta desde su punto final hasta su punto inicial.</span><span class="sxs-lookup"><span data-stu-id="81805-106"> closes a figure by drawing a straight line from its ending point to its starting point.</span></span>  
  
## <a name="example"></a><span data-ttu-id="81805-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="81805-107">Example</span></span>  
 <span data-ttu-id="81805-108">En el ejemplo siguiente se crea una ruta de acceso que tiene una figura abierta (un arco) y una figura cerrada (una elipse).</span><span class="sxs-lookup"><span data-stu-id="81805-108">The following example creates a path that has one open figure (an arc) and one closed figure (an ellipse).</span></span> <span data-ttu-id="81805-109">El <xref:System.Drawing.Graphics.FillPath%2A> método rellena el trazado según el modo de relleno predeterminado, que es <xref:System.Drawing.Drawing2D.FillMode.Alternate>.</span><span class="sxs-lookup"><span data-stu-id="81805-109">The <xref:System.Drawing.Graphics.FillPath%2A> method fills the path according to the default fill mode, which is <xref:System.Drawing.Drawing2D.FillMode.Alternate>.</span></span>  
  
 <span data-ttu-id="81805-110">En la siguiente ilustración muestra el resultado del código de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="81805-110">The following illustration shows the output of the example code.</span></span> <span data-ttu-id="81805-111">Tenga en cuenta que la ruta de acceso se rellena (según <xref:System.Drawing.Drawing2D.FillMode.Alternate>) como si la figura abierta estuviera cerrada con una línea recta desde su punto final hasta su punto inicial.</span><span class="sxs-lookup"><span data-stu-id="81805-111">Note that the path is filled (according to <xref:System.Drawing.Drawing2D.FillMode.Alternate>) as if the open figure were closed by a straight line from its ending point to its starting point.</span></span>  
  
 <span data-ttu-id="81805-112">![Rellenar trayecto abierto](../../../../docs/framework/winforms/advanced/media/fillopenpath.png "FillOpenPath")</span><span class="sxs-lookup"><span data-stu-id="81805-112">![Fill Open Path](../../../../docs/framework/winforms/advanced/media/fillopenpath.png "FillOpenPath")</span></span>  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="81805-113">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="81805-113">Compiling the Code</span></span>  
 <span data-ttu-id="81805-114">El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro del controlador de eventos <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="81805-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81805-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="81805-115">See Also</span></span>  
 <xref:System.Drawing.Drawing2D.GraphicsPath>  
 [<span data-ttu-id="81805-116">Trazados de gráficos en GDI+</span><span class="sxs-lookup"><span data-stu-id="81805-116">Graphics Paths in GDI+</span></span>](../../../../docs/framework/winforms/advanced/graphics-paths-in-gdi.md)
