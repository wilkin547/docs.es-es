---
title: "Cómo: Crear una forma utilizando StreamGeometry"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], shapes
- shapes [WPF], creating with StreamGeometry class
ms.assetid: 08f7c8ce-074b-49cd-9aba-cc9592d4ee51
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a333fd6c1906eaea2c8eaf2c3b07502b5a9c4d40
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-shape-using-a-streamgeometry"></a>Cómo: Crear una forma utilizando StreamGeometry
<xref:System.Windows.Media.StreamGeometry>es la alternativa ligera a <xref:System.Windows.Media.PathGeometry> para crear formas geométricas. Use un <xref:System.Windows.Media.StreamGeometry> cuando necesite describir una geometría compleja pero no desea que la sobrecarga de admitir el enlace de datos, animaciones ni modificaciones. Por ejemplo, debido a su eficacia, la <xref:System.Windows.Media.StreamGeometry> clase es una buena opción para describir adornos.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se utiliza la sintaxis de atributo para crear una triangular <xref:System.Windows.Media.StreamGeometry> en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-xaml[GeometriesMiscSnippets_snip#StreamGeometryTriangleExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/StreamGeometryExample.xaml#streamgeometrytriangleexamplewholepage)]  
  
 Para obtener más información acerca de <xref:System.Windows.Media.StreamGeometry> sintaxis de atributo, vea la [sintaxis de ruta de acceso de marcado](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) página.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente se usa un <xref:System.Windows.Media.StreamGeometry> para definir un triángulo en el código. En primer lugar, el ejemplo se crea un <xref:System.Windows.Media.StreamGeometry>, a continuación, obtiene un <xref:System.Windows.Media.StreamGeometryContext> y lo utiliza para describir el triángulo.  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#StreamGeometryTriangleExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/StreamGeometryTriangleExample.cs#streamgeometrytriangleexamplewholepage)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#StreamGeometryTriangleExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/streamgeometrytriangleexample.vb#streamgeometrytriangleexamplewholepage)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crea un método que utiliza un <xref:System.Windows.Media.StreamGeometry> y <xref:System.Windows.Media.StreamGeometryContext> para definir una forma geométrica según los parámetros especificados.  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#StreamGeometryExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/StreamGeometryExample.cs#streamgeometryexamplewholepage)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#StreamGeometryExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/streamgeometryexample.vb#streamgeometryexamplewholepage)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Media.PathGeometry>  
 <xref:System.Windows.Media.StreamGeometry>  
 <xref:System.Windows.Media.StreamGeometryContext>  
 [Crear una forma mediante una clase PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)  
 [Información general sobre geometría](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)
