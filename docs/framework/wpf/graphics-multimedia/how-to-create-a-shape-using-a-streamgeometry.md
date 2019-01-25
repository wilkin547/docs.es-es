---
title: Procedimiento Crear una forma utilizando StreamGeometry
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], shapes
- shapes [WPF], creating with StreamGeometry class
ms.assetid: 08f7c8ce-074b-49cd-9aba-cc9592d4ee51
ms.openlocfilehash: 94e7683d22b685c95f9f70612bc0aacef06e23bd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54554211"
---
# <a name="how-to-create-a-shape-using-a-streamgeometry"></a><span data-ttu-id="b8919-102">Procedimiento Crear una forma utilizando StreamGeometry</span><span class="sxs-lookup"><span data-stu-id="b8919-102">How to: Create a Shape Using a StreamGeometry</span></span>
<span data-ttu-id="b8919-103"><xref:System.Windows.Media.StreamGeometry> es la alternativa ligera a <xref:System.Windows.Media.PathGeometry> para crear formas geométricas.</span><span class="sxs-lookup"><span data-stu-id="b8919-103"><xref:System.Windows.Media.StreamGeometry> is light-weight alternative to <xref:System.Windows.Media.PathGeometry> for creating geometric shapes.</span></span> <span data-ttu-id="b8919-104">Use un <xref:System.Windows.Media.StreamGeometry> cuando necesite describir una geometría compleja pero no desea la sobrecarga de admitir el enlace de datos, animaciones ni modificaciones.</span><span class="sxs-lookup"><span data-stu-id="b8919-104">Use a <xref:System.Windows.Media.StreamGeometry> when you need to describe a complex geometry but do not want the overhead of supporting data binding, animation, or modification.</span></span> <span data-ttu-id="b8919-105">Por ejemplo, debido a su eficacia, la <xref:System.Windows.Media.StreamGeometry> clase es una buena elección para describir adornos.</span><span class="sxs-lookup"><span data-stu-id="b8919-105">For example, because of its efficiency, the <xref:System.Windows.Media.StreamGeometry> class is a good choice for describing adorners.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8919-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b8919-106">Example</span></span>  
 <span data-ttu-id="b8919-107">En el ejemplo siguiente se usa la sintaxis de atributo para crear un triangular <xref:System.Windows.Media.StreamGeometry> en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b8919-107">The following example uses attribute syntax to create a triangular <xref:System.Windows.Media.StreamGeometry> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
 [!code-xaml[GeometriesMiscSnippets_snip#StreamGeometryTriangleExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/StreamGeometryExample.xaml#streamgeometrytriangleexamplewholepage)]  
  
 <span data-ttu-id="b8919-108">Para obtener más información acerca de <xref:System.Windows.Media.StreamGeometry> sintaxis de atributo, vea el [sintaxis de marcado de trazados](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) página.</span><span class="sxs-lookup"><span data-stu-id="b8919-108">For more information about <xref:System.Windows.Media.StreamGeometry> attribute syntax, see the [Path Markup Syntax](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) page.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8919-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b8919-109">Example</span></span>  
 <span data-ttu-id="b8919-110">El ejemplo siguiente se usa un <xref:System.Windows.Media.StreamGeometry> para definir un triángulo en el código.</span><span class="sxs-lookup"><span data-stu-id="b8919-110">The next example uses a <xref:System.Windows.Media.StreamGeometry> to define a triangle in code.</span></span> <span data-ttu-id="b8919-111">En primer lugar, el ejemplo se crea un <xref:System.Windows.Media.StreamGeometry>, a continuación, obtiene un <xref:System.Windows.Media.StreamGeometryContext> y lo usa para describir el triángulo.</span><span class="sxs-lookup"><span data-stu-id="b8919-111">First, the example creates a <xref:System.Windows.Media.StreamGeometry>, then obtains a <xref:System.Windows.Media.StreamGeometryContext> and uses it to describe the triangle.</span></span>  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#StreamGeometryTriangleExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/StreamGeometryTriangleExample.cs#streamgeometrytriangleexamplewholepage)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#StreamGeometryTriangleExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/streamgeometrytriangleexample.vb#streamgeometrytriangleexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="b8919-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b8919-112">Example</span></span>  
 <span data-ttu-id="b8919-113">En el ejemplo siguiente se crea un método que utiliza un <xref:System.Windows.Media.StreamGeometry> y <xref:System.Windows.Media.StreamGeometryContext> para definir una forma geométrica según los parámetros especificados.</span><span class="sxs-lookup"><span data-stu-id="b8919-113">The next example creates a method that uses a <xref:System.Windows.Media.StreamGeometry> and <xref:System.Windows.Media.StreamGeometryContext> to define a geometric shape based on specified parameters.</span></span>  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#StreamGeometryExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/StreamGeometryExample.cs#streamgeometryexamplewholepage)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#StreamGeometryExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/streamgeometryexample.vb#streamgeometryexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="b8919-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="b8919-114">See also</span></span>
- <xref:System.Windows.Media.PathGeometry>
- <xref:System.Windows.Media.StreamGeometry>
- <xref:System.Windows.Media.StreamGeometryContext>
- [<span data-ttu-id="b8919-115">Crear una forma mediante una clase PathGeometry</span><span class="sxs-lookup"><span data-stu-id="b8919-115">Create a Shape by Using a PathGeometry</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)
- [<span data-ttu-id="b8919-116">Información general sobre geometría</span><span class="sxs-lookup"><span data-stu-id="b8919-116">Geometry Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)
