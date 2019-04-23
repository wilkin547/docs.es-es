---
title: Procedimiento para rellenar figuras abiertas
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- open figures [Windows Forms], filling
- figures [Windows Forms], filling
ms.assetid: 5a36b0e4-f1f4-46c0-a85a-22ae98491950
ms.openlocfilehash: addcf959e429974b9306353abb743bb2bb3114e4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59174569"
---
# <a name="how-to-fill-open-figures"></a><span data-ttu-id="faf4d-102">Procedimiento para rellenar figuras abiertas</span><span class="sxs-lookup"><span data-stu-id="faf4d-102">How to: Fill Open Figures</span></span>
<span data-ttu-id="faf4d-103">Puede rellenar una ruta de acceso pasando un <xref:System.Drawing.Drawing2D.GraphicsPath> de objeto para el <xref:System.Drawing.Graphics.FillPath%2A> método.</span><span class="sxs-lookup"><span data-stu-id="faf4d-103">You can fill a path by passing a <xref:System.Drawing.Drawing2D.GraphicsPath> object to the <xref:System.Drawing.Graphics.FillPath%2A> method.</span></span> <span data-ttu-id="faf4d-104">El <xref:System.Drawing.Graphics.FillPath%2A> método rellena la ruta de acceso según el modo de relleno (alternativo o de espirales) establecido para la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="faf4d-104">The <xref:System.Drawing.Graphics.FillPath%2A> method fills the path according to the fill mode (alternate or winding) currently set for the path.</span></span> <span data-ttu-id="faf4d-105">Si la ruta de acceso tiene figuras abiertas, se rellena la ruta de acceso como si se cerraron esas cifras.</span><span class="sxs-lookup"><span data-stu-id="faf4d-105">If the path has any open figures, the path is filled as if those figures were closed.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="faf4d-106">cierra una figura, dibuje una línea recta desde su punto final para el punto de partida.</span><span class="sxs-lookup"><span data-stu-id="faf4d-106">closes a figure by drawing a straight line from its ending point to its starting point.</span></span>  
  
## <a name="example"></a><span data-ttu-id="faf4d-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="faf4d-107">Example</span></span>  
 <span data-ttu-id="faf4d-108">El ejemplo siguiente crea una ruta de acceso que tiene una figura abierta (un arco) y una figura cerrada (una elipse).</span><span class="sxs-lookup"><span data-stu-id="faf4d-108">The following example creates a path that has one open figure (an arc) and one closed figure (an ellipse).</span></span> <span data-ttu-id="faf4d-109">El <xref:System.Drawing.Graphics.FillPath%2A> método rellena la ruta de acceso según el modo de relleno predeterminado, que es <xref:System.Drawing.Drawing2D.FillMode.Alternate>.</span><span class="sxs-lookup"><span data-stu-id="faf4d-109">The <xref:System.Drawing.Graphics.FillPath%2A> method fills the path according to the default fill mode, which is <xref:System.Drawing.Drawing2D.FillMode.Alternate>.</span></span>  
  
 <span data-ttu-id="faf4d-110">La siguiente ilustración muestra el resultado del código de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="faf4d-110">The following illustration shows the output of the example code.</span></span> <span data-ttu-id="faf4d-111">Tenga en cuenta que se rellena la ruta de acceso (según <xref:System.Drawing.Drawing2D.FillMode.Alternate>) como si se cerraron la figura abierta mediante una línea recta desde su punto final para el punto de partida.</span><span class="sxs-lookup"><span data-stu-id="faf4d-111">Note that the path is filled (according to <xref:System.Drawing.Drawing2D.FillMode.Alternate>) as if the open figure were closed by a straight line from its ending point to its starting point.</span></span>  
  
 ![Diagrama que muestra la salida del método FillPath](./media/how-to-fill-open-figures/fill-path-alternate-mode.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="faf4d-113">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="faf4d-113">Compiling the Code</span></span>  
 <span data-ttu-id="faf4d-114">El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de la <xref:System.Windows.Forms.Control.Paint> controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="faf4d-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="faf4d-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="faf4d-115">See also</span></span>

- <xref:System.Drawing.Drawing2D.GraphicsPath>
- [<span data-ttu-id="faf4d-116">Trazados de gráficos en GDI+</span><span class="sxs-lookup"><span data-stu-id="faf4d-116">Graphics Paths in GDI+</span></span>](graphics-paths-in-gdi.md)
