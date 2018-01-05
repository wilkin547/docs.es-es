---
title: "Maximizar el rendimiento de representación 3D en WPF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: 3-D graphics [WPF]
ms.assetid: 4bcf949d-d92f-4d8d-8a9b-1e4c61b25bf6
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 45053762a4782544531a09c92531b26f99663016
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="maximize-wpf-3d-performance"></a>Maximizar el rendimiento de representación 3D en WPF
Cuando use el [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] para crear controles 3D e incluir escenas 3D en las aplicaciones, es importante tener en cuenta la optimización del rendimiento. En este tema se proporciona una lista de clases 3D y propiedades que tienen implicaciones de rendimiento para la aplicación, junto con recomendaciones para optimizar el rendimiento cuando se usan.  
  
 En este tema se presupone una comprensión avanzada de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] características 3D. Las sugerencias en este documento se aplican al "nivel de representación 2", define a grandes rasgos como el hardware que admite la versión 2.0 del sombreador de píxeles y la versión 2.0 del sombreador de vértices. Para obtener más información, consulte [Graphics Rendering Tiers](../../../../docs/framework/wpf/advanced/graphics-rendering-tiers.md).  
  
## <a name="performance-impact-high"></a>Impacto en el rendimiento: alta  
  
|Property|Recomendación|  
|-|-|  
|<xref:System.Windows.Media.Brush>|Velocidad de pincel (de mayor a menor):<br /><br /> <xref:System.Windows.Media.SolidColorBrush><br /><br /> <xref:System.Windows.Media.LinearGradientBrush><br /><br /> <xref:System.Windows.Media.ImageBrush><br /><br /> <xref:System.Windows.Media.DrawingBrush>(en caché)<br /><br /> <xref:System.Windows.Media.VisualBrush>(en caché)<br /><br /> <xref:System.Windows.Media.RadialGradientBrush><br /><br /> <xref:System.Windows.Media.DrawingBrush>(sin almacenar en caché)<br /><br /> <xref:System.Windows.Media.VisualBrush>(sin almacenar en caché)|  
|<xref:System.Windows.UIElement.ClipToBoundsProperty>|Establecer `Viewport3D.ClipToBounds` en false siempre que no es necesario tener [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] explícitamente recortar el contenido de un <xref:System.Windows.Controls.Viewport3D> al rectángulo de Viewport3D. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]recorte de AntiAlias puede ser muy lento, y `ClipToBounds` está habilitado (lento) de forma predeterminada en <xref:System.Windows.Controls.Viewport3D>.|  
|<xref:System.Windows.UIElement.IsHitTestVisible%2A>|Establecer `Viewport3D.IsHitTestVisible` en false cuando no necesite [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] a tener en cuenta el contenido de un <xref:System.Windows.Controls.Viewport3D> al mouse realizar la prueba de posicionamiento.  Contenido 3D prueba de posicionamiento se realiza en el software y puede resultar lenta con mallas grandes. <xref:System.Windows.UIElement.IsHitTestVisible%2A>está habilitado (lento) de forma predeterminada en <xref:System.Windows.Controls.Viewport3D>.|  
|<xref:System.Windows.Media.Media3D.GeometryModel3D>|Cree modelos diferentes únicamente cuando requieran materiales o transformaciones diferentes.  En caso contrario, intenta fusionar muchos <xref:System.Windows.Media.Media3D.GeometryModel3D> instancias con el mismo material y transformaciones en unas pocas mayor <xref:System.Windows.Media.Media3D.GeometryModel3D> y <xref:System.Windows.Media.Media3D.MeshGeometry3D> instancias.|  
|<xref:System.Windows.Media.Media3D.MeshGeometry3D>|Animación de mallas: cambiar los vértices individuales de una malla de forma por fotograma, no siempre es eficaz en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  Para minimizar el impacto en el rendimiento de las notificaciones de cambio cuando se modifica cada vértice, desasocie la malla del árbol visual antes de realizar la modificación por vértices.  Una vez que se ha modificado la malla, vuelve a adjuntarla al árbol visual.  Además, intente minimizar el tamaño de las mallas que se animará de esta manera.|  
|Suavizado de contorno 3D|Para aumentar la velocidad de representación, deshabilite el muestreo múltiple en un <xref:System.Windows.Controls.Viewport3D> estableciendo la propiedad adjunta <xref:System.Windows.Media.RenderOptions.EdgeMode%2A> a `Aliased`.  De forma predeterminada, el suavizado de contorno 3D está deshabilitado en [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)] y está habilitada en [!INCLUDE[TLA#tla_longhorn](../../../../includes/tlasharptla-longhorn-md.md)] con 4 muestras por píxel.|  
|Texto|Live texto en una escena 3D (live porque está en un <xref:System.Windows.Media.DrawingBrush> o <xref:System.Windows.Media.VisualBrush>) puede ser lento. Pruebe a utilizar imágenes del texto en su lugar (a través de <xref:System.Windows.Media.Imaging.RenderTargetBitmap>) a menos que el texto cambiará.|  
|<xref:System.Windows.Media.TileBrush>|Si tiene que utilizar un <xref:System.Windows.Media.VisualBrush> o un <xref:System.Windows.Media.DrawingBrush> en una escena 3D porque el contenido del pincel no es estático, pruebe el pincel para el almacenamiento en caché (estableciendo la propiedad adjunta <xref:System.Windows.Media.RenderOptions.CachingHint%2A> a `Cache`).  Establecer umbrales de invalidación de la escala mínima y máxima (con las propiedades adjuntas <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMinimum%2A> y <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMaximum%2A>) para que los pinceles almacenados en caché no volverá a generar con demasiada frecuencia, mientras sigue manteniendo el nivel deseado de calidad.  De forma predeterminada, <xref:System.Windows.Media.DrawingBrush> y <xref:System.Windows.Media.VisualBrush> no se almacenan, lo que significa que cada vez que algo pintado con el pincel tiene que se vuelven a representar, todo el contenido del pincel debe primero volver a representar en una superficie intermedia.|  
|<xref:System.Windows.Media.Effects.BitmapEffect>|<xref:System.Windows.Media.Effects.BitmapEffect>obliga a todo el contenido afectado se representen sin aceleración de hardware.  Para obtener el mejor rendimiento, no use <xref:System.Windows.Media.Effects.BitmapEffect>.|  
  
## <a name="performance-impact-medium"></a>Impacto en el rendimiento: medio  
  
|Property|Recomendación|  
|-|-|  
|<xref:System.Windows.Media.Media3D.MeshGeometry3D>|Cuando una malla se define como triángulos colindantes con vértices compartidos y esos vértices tienen la misma posición, normal y coordenadas de textura, defina cada vértice compartido una sola vez y, a continuación, defina los triángulos por un índice con <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A>.|  
|<xref:System.Windows.Media.ImageBrush>|Intente reducir el tamaño de las texturas cuando tenga un control explícito sobre el tamaño (cuando se usa un <xref:System.Windows.Media.Imaging.RenderTargetBitmap> o un <xref:System.Windows.Media.ImageBrush>).  Tenga en cuenta que las texturas de resolución inferior puede disminuir la calidad visual, por lo que intenta encontrar el equilibrio adecuado entre la calidad y el rendimiento.|  
|Opacidad|Al representar 3D translúcido contenido (por ejemplo, reflexiones), utilice las propiedades de opacidad en pinceles o materiales (a través de <xref:System.Windows.Media.Brush.Opacity%2A> o <xref:System.Windows.Media.Media3D.DiffuseMaterial.Color%2A>) en lugar de crear otro translúcido <xref:System.Windows.Controls.Viewport3D> estableciendo `Viewport3D.Opacity` en un valor menor que 1.|  
|<xref:System.Windows.Controls.Viewport3D>|Minimizar el número de <xref:System.Windows.Controls.Viewport3D> objetos que usa en una escena.  Coloque varios modelos 3D en la misma Viewport3D, en lugar de crear instancias de Viewport3D independientes para cada modelo.|  
|<xref:System.Windows.Freezable>|Normalmente, es beneficioso reutilizar <xref:System.Windows.Media.Media3D.MeshGeometry3D>, <xref:System.Windows.Media.Media3D.GeometryModel3D>, pinceles y materiales.  Todos son multiparentable, puesto que se derivan de `Freezable`.|  
|<xref:System.Windows.Freezable>|Llame a la <xref:System.Windows.Freezable.Freeze%2A> método en Freezables cuando sus propiedades permanecerá sin cambios en la aplicación.  Congelación puede reducir el espacio de trabajo y aumentar la velocidad.|  
|<xref:System.Windows.Media.Brush>|Use <xref:System.Windows.Media.ImageBrush> en lugar de <xref:System.Windows.Media.VisualBrush> o <xref:System.Windows.Media.DrawingBrush> cuando no se cambiará el contenido del pincel.  Contenido 2D se puede convertir a un <xref:System.Windows.Controls.Image> a través de <xref:System.Windows.Media.Imaging.RenderTargetBitmap> y, a continuación, se utiliza en un <xref:System.Windows.Media.ImageBrush>.|  
|<xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A>|No utilice <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> a menos que necesite ver las caras posteriores de su <xref:System.Windows.Media.Media3D.GeometryModel3D>.|  
|<xref:System.Windows.Media.Media3D.Light>|Velocidad de la luz (de mayor a menor):<br /><br /> <xref:System.Windows.Media.Media3D.AmbientLight><br /><br /> <xref:System.Windows.Media.Media3D.DirectionalLight><br /><br /> <xref:System.Windows.Media.Media3D.PointLight><br /><br /> <xref:System.Windows.Media.Media3D.SpotLight>|  
|<xref:System.Windows.Media.Media3D.MeshGeometry3D>|Intente mantener mallas debajo de estos límites:<br /><br /> <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A>: 20.001 <xref:System.Windows.Media.Media3D.Point3D> instancias<br /><br /> <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A>: 60,003 <xref:System.Int32> instancias|  
|<xref:System.Windows.Media.Media3D.Material>|Velocidad del material (de mayor a menor):<br /><br /> <xref:System.Windows.Media.Media3D.EmissiveMaterial><br /><br /> <xref:System.Windows.Media.Media3D.DiffuseMaterial><br /><br /> <xref:System.Windows.Media.Media3D.SpecularMaterial>|  
|<xref:System.Windows.Media.Brush>|[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]3D no cancela los pinceles no visibles (pinceles de ambiente negros, pinceles claros, etc.) de una manera coherente.  Puede ser conveniente omitirlos de la escena.|  
|<xref:System.Windows.Media.Media3D.MaterialGroup>|Cada <xref:System.Windows.Media.Media3D.Material> en un <xref:System.Windows.Media.Media3D.MaterialGroup> hace otro paso de representación, incluidos por lo que muchos de los materiales, incluso los materiales simples, puede aumentar drásticamente las demandas de relleno en la GPU.  Minimizar el número de materiales en su <xref:System.Windows.Media.Media3D.MaterialGroup>.|  
  
## <a name="performance-impact-low"></a>Impacto en el rendimiento: baja  
  
|Property|Recomendación|  
|-|-|  
|<xref:System.Windows.Media.Media3D.Transform3DGroup>|Cuando no necesite animación o enlace de datos, en lugar de usar un grupo de transformaciones que contiene varias transformaciones, utilice una sola <xref:System.Windows.Media.Media3D.MatrixTransform3D>, si se establece en el producto de todas las transformaciones que en caso contrario, podría existir de forma independiente en el grupo de transformación.|  
|<xref:System.Windows.Media.Media3D.Light>|Minimizar el número de luces de la escena. Demasiadas luces en una escena forzará [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] se retrocede a la representación de software.  Los límites son aproximadamente 110 <xref:System.Windows.Media.Media3D.DirectionalLight> objetos, 70 <xref:System.Windows.Media.Media3D.PointLight> objetos o 40 <xref:System.Windows.Media.Media3D.SpotLight> objetos.|  
|<xref:System.Windows.Media.Media3D.ModelVisual3D>|Separar mover objetos de objetos estáticos colocándolos en independiente <xref:System.Windows.Media.Media3D.ModelVisual3D> instancias.  ModelVisual3D es más "pesado" que <xref:System.Windows.Media.Media3D.GeometryModel3D> porque almacena en caché los límites transformados.  GeometryModel3D se optimiza para ser un modelo; ModelVisual3D se optimiza para ser un nodo de la escena.  Use ModelVisual3D para colocar instancias compartidas de GeometryModel3D en la escena.|  
|<xref:System.Windows.Media.Media3D.Light>|Minimice el número de veces que se cambia el número de luces de la escena.  Cada cambio del número de luces fuerza una regeneración del sombreador y una recompilación, a menos que la configuración ha existido previamente (y, por tanto, tenía su sombreador almacenado en caché).|  
|Claro|Las luces negras no será visibles, pero agregará para representar la hora; Considere la posibilidad de omitirlas.|  
|<xref:System.Windows.Media.Media3D.MeshGeometry3D>|Para minimizar el tiempo de construcción de las colecciones grandes en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], por ejemplo, un MeshGeometry3D <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A>, <xref:System.Windows.Media.Media3D.MeshGeometry3D.Normals%2A>, <xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A>, y <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A>, ajustar previamente el tamaño de las colecciones antes del rellenado de valor. Si es posible, pase estructuras de datos previamente rellenadas constructores de las colecciones, como matrices o listas.|  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre gráficos 3D](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
