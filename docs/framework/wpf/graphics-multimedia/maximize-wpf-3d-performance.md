---
title: "Maximizar el rendimiento de representaci&#243;n 3D en WPF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "gráficos 3D [WPF]"
ms.assetid: 4bcf949d-d92f-4d8d-8a9b-1e4c61b25bf6
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Maximizar el rendimiento de representaci&#243;n 3D en WPF
Cuando se utiliza [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] para compilar controles 3D e incluir escenas 3D en las aplicaciones, es importante tener en cuenta la optimización del rendimiento. En este tema se proporciona una lista de clases y propiedades 3D que afectan al rendimiento de la aplicación, junto con las recomendaciones para optimizar el rendimiento al utilizarlas.  
  
 En este tema se da por hecho que el lector tiene una comprensión avanzada de las características 3D de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  Las sugerencias de este documento se aplican al "nivel de presentación 2", que se define a grandes rasgos como el hardware que admite la versión 2.0 del sombreador de píxeles y la versión 2.0 del sombreador de vértices.  Para obtener información más detallada, vea [Niveles de representación de gráficos](../../../../docs/framework/wpf/advanced/graphics-rendering-tiers.md).  
  
## Impacto en el rendimiento: alto  
  
|||  
|-|-|  
|Propiedad.|Recomendación|  
|<xref:System.Windows.Media.Brush>|Velocidad del pincel \(de más rápida a más lenta\):<br /><br /> <xref:System.Windows.Media.SolidColorBrush><br /><br /> <xref:System.Windows.Media.LinearGradientBrush><br /><br /> <xref:System.Windows.Media.ImageBrush><br /><br /> <xref:System.Windows.Media.DrawingBrush> \(almacenado en caché\)<br /><br /> <xref:System.Windows.Media.VisualBrush> \(almacenado en memoria caché\)<br /><br /> <xref:System.Windows.Media.RadialGradientBrush><br /><br /> <xref:System.Windows.Media.DrawingBrush> \(no almacenado en memoria caché\)<br /><br /> <xref:System.Windows.Media.VisualBrush> \(no almacenado en memoria caché\)|  
|<xref:System.Windows.UIElement.ClipToBoundsProperty>|Establezca `Viewport3D.ClipToBounds` en false siempre que no necesite que [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] recorte explícitamente el contenido de <xref:System.Windows.Controls.Viewport3D> al rectángulo de Viewport3D. El recorte con suavizado de contorno de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] puede ser muy lento y `ClipToBounds` está habilitado \(lento\) de manera predeterminada en <xref:System.Windows.Controls.Viewport3D>.|  
|<xref:System.Windows.UIElement.IsHitTestVisible%2A>|Establezca `Viewport3D.IsHitTestVisible` en false siempre que no haga falta que [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] tenga en cuenta el contenido de <xref:System.Windows.Controls.Viewport3D> al realizar las pruebas de posicionamiento del mouse. Las pruebas de posicionamiento del contenido 3D se efectúan en el software y pueden resultar lentas con mallas grandes. <xref:System.Windows.UIElement.IsHitTestVisible%2A> está habilitado \(lento\) de manera predeterminada en <xref:System.Windows.Controls.Viewport3D>.|  
|<xref:System.Windows.Media.Media3D.GeometryModel3D>|Cree modelos diferentes únicamente cuando requieran materiales o transformaciones diferentes.  De lo contrario, intente combinar varias instancias <xref:System.Windows.Media.Media3D.GeometryModel3D> que tengan el mismo material y las mismas transformaciones en unas pocas instancias de <xref:System.Windows.Media.Media3D.GeometryModel3D> y <xref:System.Windows.Media.Media3D.MeshGeometry3D> mayores.|  
|<xref:System.Windows.Media.Media3D.MeshGeometry3D>|Animación de mallas: cambiar los vértices individuales de una malla fotograma a fotograma no siempre es eficaz en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. Para minimizar el impacto en el rendimiento de las notificaciones de cambios cuando se modifica cada vértice, desasocie la malla del árbol visual antes de realizar la modificación por vértices. Una vez modificada la malla, vuelva a adjuntarla al árbol visual. Además, intente minimizar el tamaño de las mallas que se animarán de esta manera.|  
|Suavizado de contorno 3D|Para aumentar la velocidad de representación, deshabilite el muestreo múltiple en <xref:System.Windows.Controls.Viewport3D> estableciendo la propiedad <xref:System.Windows.Media.RenderOptions.EdgeMode%2A> adjunta en `Aliased`.  De manera predeterminada, el suavizado de contorno 3D está deshabilitado en [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)] y habilitado en [!INCLUDE[TLA#tla_longhorn](../../../../includes/tlasharptla-longhorn-md.md)] con 4 muestras por píxel.|  
|Text|El texto activo en una escena 3D \(activo porque está en un <xref:System.Windows.Media.DrawingBrush> o <xref:System.Windows.Media.VisualBrush>\) puede ser lento.  Intente utilizar imágenes del texto en su lugar \(mediante <xref:System.Windows.Media.Imaging.RenderTargetBitmap>\), a menos que se trate de texto que vaya a cambiar.|  
|<xref:System.Windows.Media.TileBrush>|Si debe utilizar <xref:System.Windows.Media.VisualBrush> o <xref:System.Windows.Media.DrawingBrush> en una escena 3D porque el contenido del pincel no es estático, intente almacenar el pincel en la memoria caché \(estableciendo la propiedad <xref:System.Windows.Media.RenderOptions.CachingHint%2A> adjunta en `Cache`\).  Establezca umbrales de invalidación de escala mínimos \(con las propiedades adjuntas <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMinimum%2A> y <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMaximum%2A>\) y máximos para que no se regeneren los pinceles almacenados en memoria caché con demasiada frecuencia, pero se mantenga el nivel de calidad deseado.  De manera predeterminada, <xref:System.Windows.Media.DrawingBrush> y <xref:System.Windows.Media.VisualBrush> no se almacenan en memoria caché, lo que significa que cada vez que hay que representar de nuevo algún elemento pintado con el pincel, el contenido completo del pincel se tiene que representar de nuevo antes en una superficie intermedia.|  
|<xref:System.Windows.Media.Effects.BitmapEffect>|<xref:System.Windows.Media.Effects.BitmapEffect> obliga a representar todo el contenido afectado sin aceleración de hardware.  Para obtener el máximo rendimiento, no utilice <xref:System.Windows.Media.Effects.BitmapEffect>.|  
  
## Impacto en el rendimiento: medio  
  
|||  
|-|-|  
|Propiedad.|Recomendación|  
|<xref:System.Windows.Media.Media3D.MeshGeometry3D>|Cuando una malla se define como triángulos colindantes con vértices compartidos y esos vértices tienen las mismas posición, normal y coordenadas de textura, defina cada vértice compartido una sola vez y, a continuación, defina los triángulos por índices mediante <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A>.|  
|<xref:System.Windows.Media.ImageBrush>|Intente minimizar el tamaño de las texturas cuando tenga el control explícito del tamaño \(cuando utilice <xref:System.Windows.Media.Imaging.RenderTargetBitmap> o <xref:System.Windows.Media.ImageBrush>\).  Tenga en cuenta que las texturas de resolución más baja pueden disminuir la calidad visual, así que intente hallar el equilibrio apropiado entre calidad y rendimiento.|  
|Opacidad|Al representar contenido 3D translúcido \(como las reflexiones\), utilice las propiedades de opacidad en pinceles o materiales \(mediante <xref:System.Windows.Media.Brush.Opacity%2A> o <xref:System.Windows.Media.Media3D.DiffuseMaterial.Color%2A>\) en lugar de crear un <xref:System.Windows.Controls.Viewport3D> translúcido independiente estableciendo `Viewport3D.Opacity` en un valor menor que 1.|  
|<xref:System.Windows.Controls.Viewport3D>|Minimice el número de objetos <xref:System.Windows.Controls.Viewport3D> que utiliza en una escena.  Coloque varios modelos 3D en la misma Viewport3D, en lugar de crear instancias de Viewport3D independientes para cada modelo.|  
|<xref:System.Windows.Freezable>|Normalmente, es beneficioso reutilizar los <xref:System.Windows.Media.Media3D.MeshGeometry3D>, los <xref:System.Windows.Media.Media3D.GeometryModel3D>, los pinceles y los materiales.  Todos pueden tener varios elementos primarios, puesto que se derivan de `Freezable`.|  
|<xref:System.Windows.Freezable>|Llame al método <xref:System.Windows.Freezable.Freeze%2A> en Freezables cuando sus propiedades vayan a permanecer sin cambios en la aplicación.  La inmovilización puede disminuir espacio de trabajo y aumentar la velocidad.|  
|<xref:System.Windows.Media.Brush>|Utilice <xref:System.Windows.Media.ImageBrush> en lugar de <xref:System.Windows.Media.VisualBrush> o <xref:System.Windows.Media.DrawingBrush> cuando el contenido del pincel no vaya a cambiar.  El contenido 2D se puede convertir en una <xref:System.Windows.Controls.Image> mediante <xref:System.Windows.Media.Imaging.RenderTargetBitmap> y, a continuación, se puede utilizar en un <xref:System.Windows.Media.ImageBrush>.|  
|<xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A>|No utilice <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> a menos que realmente necesite ver las caras posteriores del <xref:System.Windows.Media.Media3D.GeometryModel3D>.|  
|<xref:System.Windows.Media.Media3D.Light>|Velocidad de la luz \(de mayor a menor\):<br /><br /> <xref:System.Windows.Media.Media3D.AmbientLight><br /><br /> <xref:System.Windows.Media.Media3D.DirectionalLight><br /><br /> <xref:System.Windows.Media.Media3D.PointLight><br /><br /> <xref:System.Windows.Media.Media3D.SpotLight>|  
|<xref:System.Windows.Media.Media3D.MeshGeometry3D>|Intente mantener los tamaños de las malla por debajo de estos límites:<br /><br /> <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A>: 20.001 instancias de <xref:System.Windows.Media.Media3D.Point3D><br /><br /> <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A>: 60.003 instancias de <xref:System.Int32>|  
|<xref:System.Windows.Media.Media3D.Material>|Velocidad de los materiales \(de mayor a menor\):<br /><br /> <xref:System.Windows.Media.Media3D.EmissiveMaterial><br /><br /> <xref:System.Windows.Media.Media3D.DiffuseMaterial><br /><br /> <xref:System.Windows.Media.Media3D.SpecularMaterial>|  
|<xref:System.Windows.Media.Brush>|[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 3D no cancela los pinceles no visibles \(pinceles de ambiente negros, pinceles claros, etc.\) de una manera coherente. Puede ser conveniente omitirlos de la escena.|  
|<xref:System.Windows.Media.Media3D.MaterialGroup>|Cada <xref:System.Windows.Media.Media3D.Material> de un <xref:System.Windows.Media.Media3D.MaterialGroup> provoca un paso más de representación; por este motivo, incluir muchos materiales, aunque sean simples, puede aumentar drásticamente las solicitudes de relleno sobre la GPU.  Minimice el número de materiales del <xref:System.Windows.Media.Media3D.MaterialGroup>.|  
  
## Impacto en el rendimiento: bajo  
  
|||  
|-|-|  
|Propiedad.|Recomendación|  
|<xref:System.Windows.Media.Media3D.Transform3DGroup>|Cuando no necesite la animación o el enlace de datos, en lugar de utilizar un grupo de transformaciones que contiene varias transformaciones, utilice una sola <xref:System.Windows.Media.Media3D.MatrixTransform3D>, y establézcala de modo que sea el producto de todas las transformaciones que, en otro caso, existirían independientemente en el grupo de transformaciones.|  
|<xref:System.Windows.Media.Media3D.Light>|Minimice el número de luces de la escena.  Demasiadas luces en una escena obligarán a [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] a recurrir a la representación de software. Los límites son aproximadamente 110 objetos <xref:System.Windows.Media.Media3D.DirectionalLight>, 70 objetos <xref:System.Windows.Media.Media3D.PointLight> o 40 objetos <xref:System.Windows.Media.Media3D.SpotLight>.|  
|<xref:System.Windows.Media.Media3D.ModelVisual3D>|Separe los objetos móviles de los estáticos colocándolos en instancias de <xref:System.Windows.Media.Media3D.ModelVisual3D> independientes.  ModelVisual3D es más "pesado" que <xref:System.Windows.Media.Media3D.GeometryModel3D>, porque almacena en memoria caché los límites transformados.  GeometryModel3D está optimizado para ser un modelo; ModelVisual3D lo está para ser nodo de escena.  Utilice ModelVisual3D para colocar instancias compartidas de GeometryModel3D en la escena.|  
|<xref:System.Windows.Media.Media3D.Light>|Minimice el número de veces que cambia al número de luces de la escena.  Cada cambio del número de luces fuerza una regeneración del sombreador y una recompilación, a menos que esa configuración haya existido previamente \(y, por tanto, su sombreador esté almacenado en memoria caché\).|  
|Luz|Las luces negras no son visibles, pero agregan tiempo de representación; puede ser conveniente omitirlas.|  
|<xref:System.Windows.Media.Media3D.MeshGeometry3D>|Para minimizar el tiempo de construcción de las colecciones grandes en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], tales como <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A>de MeshGeometry3D, <xref:System.Windows.Media.Media3D.MeshGeometry3D.Normals%2A>, <xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A> y <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A>, ajuste previamente el tamaño de las colecciones antes de rellenar los valores.  Si es posible, pase estructuras de datos previamente rellenadas, como matrices o listas, a los constructores de las colecciones.|  
  
## Vea también  
 [Información general sobre gráficos 3D](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)