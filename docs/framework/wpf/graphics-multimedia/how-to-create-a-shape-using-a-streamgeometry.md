---
title: Procedimiento Crear una forma mediante un objeto StreamGeometry
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], shapes
- shapes [WPF], creating with StreamGeometry class
ms.assetid: 08f7c8ce-074b-49cd-9aba-cc9592d4ee51
ms.openlocfilehash: fd191e4cfdfa33c144389d4871a9641e9c811ed3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62054580"
---
# <a name="how-to-create-a-shape-using-a-streamgeometry"></a>Procedimiento Crear una forma mediante un objeto StreamGeometry
<xref:System.Windows.Media.StreamGeometry> es la alternativa ligera a <xref:System.Windows.Media.PathGeometry> para crear formas geométricas. Use un <xref:System.Windows.Media.StreamGeometry> cuando necesite describir una geometría compleja pero no desea la sobrecarga de admitir el enlace de datos, animaciones ni modificaciones. Por ejemplo, debido a su eficacia, la <xref:System.Windows.Media.StreamGeometry> clase es una buena elección para describir adornos.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa la sintaxis de atributo para crear un triangular <xref:System.Windows.Media.StreamGeometry> en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-xaml[GeometriesMiscSnippets_snip#StreamGeometryTriangleExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/StreamGeometryExample.xaml#streamgeometrytriangleexamplewholepage)]  
  
 Para obtener más información acerca de <xref:System.Windows.Media.StreamGeometry> sintaxis de atributo, vea el [sintaxis de marcado de trazados](path-markup-syntax.md) página.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente se usa un <xref:System.Windows.Media.StreamGeometry> para definir un triángulo en el código. En primer lugar, el ejemplo se crea un <xref:System.Windows.Media.StreamGeometry>, a continuación, obtiene un <xref:System.Windows.Media.StreamGeometryContext> y lo usa para describir el triángulo.  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#StreamGeometryTriangleExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/StreamGeometryTriangleExample.cs#streamgeometrytriangleexamplewholepage)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#StreamGeometryTriangleExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/streamgeometrytriangleexample.vb#streamgeometrytriangleexamplewholepage)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crea un método que utiliza un <xref:System.Windows.Media.StreamGeometry> y <xref:System.Windows.Media.StreamGeometryContext> para definir una forma geométrica según los parámetros especificados.  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#StreamGeometryExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/StreamGeometryExample.cs#streamgeometryexamplewholepage)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#StreamGeometryExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/streamgeometryexample.vb#streamgeometryexamplewholepage)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Media.PathGeometry>
- <xref:System.Windows.Media.StreamGeometry>
- <xref:System.Windows.Media.StreamGeometryContext>
- [Crear una forma mediante una clase PathGeometry](how-to-create-a-shape-by-using-a-pathgeometry.md)
- [Información general sobre geometría](geometry-overview.md)
