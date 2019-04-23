---
title: Información general sobre gráficos 3D
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 3-D graphics [WPF]
- graphics [WPF], 3-D
ms.assetid: 67f31ed4-e36b-4b02-9889-dcce245d7afc
ms.openlocfilehash: 79dc7a3578c395ae8cdf5933e1249441f97071a2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59087994"
---
# <a name="3-d-graphics-overview"></a>Información general sobre gráficos 3D
<a name="introduction"></a> La funcionalidad [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] permite a los programadores dibujar, transformar y animar gráficos 3D tanto en el marcado y en el código de procedimiento. Los desarrolladores pueden combinar gráficos [!INCLUDE[TLA#tla_2d](../../../../includes/tlasharptla-2d-md.md)] y [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] para crear controles enriquecidos, proporcionar ilustraciones complejas de datos o mejorar la experiencia del usuario de la interfaz de una aplicación. La compatibilidad con [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] no se ha diseñado para proporcionar una plataforma completa de desarrollo de juegos. En este tema se proporciona información general sobre la funcionalidad de [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] en el sistema de gráficos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  

<a name="threed_in_2d"></a>   
## <a name="3-d-in-a-2-d-container"></a>3D en un contenedor 2D  
 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] contenido en gráficos [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se encapsula en un elemento, <xref:System.Windows.Controls.Viewport3D>, que puede participar en la estructura de elementos bidimensionales. El sistema de gráficos trata <xref:System.Windows.Controls.Viewport3D> como elementos visuales bidimensionales, como muchos otros elementos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. <xref:System.Windows.Controls.Viewport3D> funciona como una ventana, una ventanilla, en una escena tridimensional. Expresado de modo más preciso, es una superficie sobre la que se proyecta una escena [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)].  
  
 En un convencional [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] aplicación, use <xref:System.Windows.Controls.Viewport3D> como lo haría con cualquier otro elemento contenedor, como Grid o Canvas.  Aunque puede usar <xref:System.Windows.Controls.Viewport3D> Sí [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] dibujar objetos en el mismo gráfico de escena, no puede interpenetrar [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] y [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] objetos dentro de un <xref:System.Windows.Controls.Viewport3D>.  En este tema se centrará en cómo dibujar [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] gráficos dentro de la <xref:System.Windows.Controls.Viewport3D>.  
  
<a name="coord_space"></a>   
## <a name="3-d-coordinate-space"></a>Espacio de coordenadas 3D  
 El sistema de coordenadas de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] para gráficos [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] localiza el origen en la parte superior izquierda del área de representación (que suele ser la pantalla). En el sistema [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)], los valores positivos del eje X se extienden hacia la derecha, y los valores positivos del eje Y se extienden hacia abajo.  En el sistema de coordenadas [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)], sin embargo, el origen se encuentra en el centro del área de representación, de manera que los valores positivos del eje X se extienden hacia la derecha, los valores positivos del eje Y se extienden hacia arriba (no hacia abajo) y los valores positivos del eje Z se extienden hacia el exterior partiendo del origen, es decir, hacia el espectador.  
  
 ![Sistemas de coordenadas](./media/coordsystem-1.png "CoordSystem-1")  
Representaciones convencionales de los sistemas de coordenadas 2D y 3D  
  
 El espacio definido por estos ejes es el marco estático de referencia para los objetos [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Cuando se generan modelos en este espacio y se crean luces y cámaras para verlos, es útil distinguir este marco estático de referencia, o "espacio universal", del marco de referencia local creado para cada modelo al aplicarle transformaciones. Recuerde también que los objetos del espacio universal podrían parecer completamente diferentes, o incluso no verse en absoluto, dependiendo de la configuración de las luces y la cámara, pero que la posición de la cámara no cambia la ubicación de los objetos en el espacio universal.  
  
<a name="cameras"></a>   
## <a name="cameras-and-projections"></a>Cámaras y proyecciones  
 Los programadores que trabajan en [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] están acostumbrados a colocar los elementos de dibujo primitivos en una pantalla bidimensional. Al crear una escena [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)], es importante recordar que, en realidad, se está creando una representación [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] de los objetos [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]. Dado que una escena [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] tiene un aspecto diferente dependiendo del punto de vista del espectador, debe especificar ese punto de vista. El <xref:System.Windows.Media.Media3D.Camera> clase le permite especificar este punto de vista para un [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] escena.  
  
 Otra manera de entender cómo se representa una escena [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] en una superficie [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] consiste en describir dicha escena como una proyección sobre la superficie de visualización. El <xref:System.Windows.Media.Media3D.ProjectionCamera> le permite especificar proyecciones diferentes y sus propiedades para cambiar cómo el espectador ve [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] modelos. Un <xref:System.Windows.Media.Media3D.PerspectiveCamera> especifica una proyección en escorzo de la escena.  En otras palabras, el <xref:System.Windows.Media.Media3D.PerspectiveCamera> proporciona una perspectiva de punto de fuga.  Puede especificar la posición de la cámara en el espacio de coordenadas de la escena, la dirección y el campo de visión de la cámara y un vector que define la dirección de "arriba" en la escena. El siguiente diagrama ilustra la <xref:System.Windows.Media.Media3D.PerspectiveCamera>de proyección.  
  
 El <xref:System.Windows.Media.Media3D.ProjectionCamera.NearPlaneDistance%2A> y <xref:System.Windows.Media.Media3D.ProjectionCamera.FarPlaneDistance%2A> propiedades de <xref:System.Windows.Media.Media3D.ProjectionCamera> limite el intervalo de proyección de la cámara. Dado que las cámaras se pueden ubicar en cualquier parte de la escena, es posible situarlas dentro de un modelo o muy cerca de él, con lo que resultaría difícil distinguir correctamente los objetos.  <xref:System.Windows.Media.Media3D.ProjectionCamera.NearPlaneDistance%2A> le permite especificar una distancia mínima de la cámara más allá del cual no se dibujarán objetos.  Por el contrario, <xref:System.Windows.Media.Media3D.ProjectionCamera.FarPlaneDistance%2A> le permite especificar una distancia desde la cámara más allá del cual no se dibujarán objetos, lo que garantiza que los objetos demasiado lejos para ser reconocibles no se incluirán en la escena.  
  
 ![El programa de instalación de la cámara](./media/coordsystem-6.png "CoordSystem 6")  
Posición de la cámara  
  
 <xref:System.Windows.Media.Media3D.OrthographicCamera> Especifica una proyección ortogonal de un [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] modelo a un [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] superficie visual. Al igual que otras cámaras, especifica una posición, dirección de visualización y dirección "hacia arriba". A diferencia de <xref:System.Windows.Media.Media3D.PerspectiveCamera>, sin embargo, <xref:System.Windows.Media.Media3D.OrthographicCamera> describe una proyección que no incluye la perspectiva en escorzo. En otras palabras, <xref:System.Windows.Media.Media3D.OrthographicCamera> describe un cuadro de vista cuyos lados son paralelos, en lugar de uno cuyos lados convergen en un punto de la cámara. La siguiente imagen muestra el mismo modelo visto con <xref:System.Windows.Media.Media3D.PerspectiveCamera> y <xref:System.Windows.Media.Media3D.OrthographicCamera>.  
  
 ![Proyección en perspectiva y ortográfica](./media/camera-projections4.png "Camera_projections4")  
Proyecciones ortográfica y en perspectiva  
  
 En el código siguiente se muestran algunas configuraciones de cámara típicas.  
  
 [!code-csharp[3dgallery_procedural_snip#Basic3DShapeCodeExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Basic3DShapeExample.cs#basic3dshapecodeexampleinline1)]
 [!code-vb[3dgallery_procedural_snip#Basic3DShapeCodeExampleInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/basic3dshapeexample.vb#basic3dshapecodeexampleinline1)]  
  
<a name="models_meshes"></a>   
## <a name="model-and-mesh-primitives"></a>Elementos primitivos de modelo y de malla  
  
 <xref:System.Windows.Media.Media3D.Model3D> es la clase base abstracta que representa un tipo genérico [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] objeto. Para crear un [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] escena, necesita algunos objetos para ver y los objetos que componen el gráfico de escena se derivan de <xref:System.Windows.Media.Media3D.Model3D>. Actualmente, el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] admite geometrías de modelado con <xref:System.Windows.Media.Media3D.GeometryModel3D>. El <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A> propiedad de este modelo toma una malla primitivo.  
  
 Para crear un modelo, comience por crear un elemento primitivo, o malla. Un elemento [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] primitivo es una colección de vértices que constituyen una entidad [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] única. La mayoría de los sistemas [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] proporcionan elementos primitivos modelados a partir de la figura cerrada más simple: un triángulo definido por tres vértices.  Dado que los tres puntos de un triángulo son coplanares, puede seguir agregando triángulos para modelar formas más complejas, denominadas mallas.  
  
 El [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] sistema actualmente proporciona la <xref:System.Windows.Media.Media3D.MeshGeometry3D> (clase), que le permite especificar cualquier geometría; no admite actualmente predefinidos [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] primitivas como esferas y formas cúbicas. Empezar a crear un <xref:System.Windows.Media.Media3D.MeshGeometry3D> especificando una lista de vértices de triángulos como su <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> propiedad. Cada vértice se especifica como un <xref:System.Windows.Media.Media3D.Point3D>.  (En Lenguaje [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], especifique esta propiedad como una lista de números agrupados en ternas, que representan las coordenadas de cada vértice). Según cuál sea la geometría, la malla puede estar compuesta de muchos triángulos, algunos de los cuales compartirán las mismas esquinas (vértices). [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] necesita información sobre qué triángulos comparten qué vértices para dibujar la malla correctamente. Esta información se proporciona especificando una lista de índices de triángulos con la <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A> propiedad. Esta lista especifica el orden en que se especifican los puntos en el <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> lista determinarán un triángulo.  
  
 [!code-xaml[basic3d#Basic3DXAML3DN3](~/samples/snippets/xaml/VS_Snippets_Wpf/Basic3D/XAML/Window1.xaml#basic3dxaml3dn3)]  
  
 En el ejemplo anterior, el <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> lista especifica ocho vértices para definir una malla en forma de cubo. El <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A> propiedad especifica una lista de doce grupos de tres índices.  Cada número en la lista hace referencia a un desplazamiento en el <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> lista.  Por ejemplo, los tres primeros vértices especificados por el <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> lista son (1,1,0), (0,1,0) y (0,0,0). Los tres primeros índices especificados por el <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A> lista son 0, 2 y 1, que corresponden a la primera, en tercer lugar y segundo puntos en el <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> lista. Como resultado, el primer triángulo que constituye el modelo del cubo se creará de (1,1,0) a (0,1,0) y a (0,0,0), y los once triángulos restantes se determinarán de igual forma.  
  
 Puede seguir definiendo el modelo especificando valores para el <xref:System.Windows.Media.Media3D.MeshGeometry3D.Normals%2A> y <xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A> propiedades.  Para representar la superficie del modelo, el sistema de gráficos necesita información sobre en qué dirección mira la superficie de cualquier triángulo dado. Utiliza esta información para realizar los cálculos de iluminación del modelo: las superficies que miran directamente hacia una fuente de luz parecen más luminosas que las que tienen un ángulo que las oculta de la luz. Aunque [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] puede determinar los vectores normales predeterminados utilizando las coordenadas de posición, también es posible especificar vectores normales diferentes para crear un aspecto más aproximado de las superficies curvas.  
  
 El <xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A> propiedad especifica una colección de <xref:System.Windows.Point>que indica el sistema de gráficos cómo asignar las coordenadas que determinan cómo trazar una textura en los vértices de la malla. <xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A> se especifican como un valor comprendido entre 0 y 1, ambos incluidos.  Igual que con el <xref:System.Windows.Media.Media3D.MeshGeometry3D.Normals%2A> propiedad, el sistema de gráficos puede calcular las coordenadas de textura de predeterminado, pero decide establecer coordenadas de textura diferentes para controlar la asignación de una textura que incluya parte de un patrón repetitivo, por ejemplo. Encontrará más información sobre coordenadas de textura en los temas siguientes o en el SDK de Managed Direct3D.  
  
 En el ejemplo siguiente se muestra cómo crear una cara del modelo del cubo en código de procedimiento. Observe que puede dibujar el cubo completo como un solo objeto GeometryModel3D; en este ejemplo se dibuja la cara del cubo como un modelo distinto a fin de aplicar después texturas independientes a cada cara.  
  
 [!code-csharp[3doverview#3DOverview3DN6](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn6)]
 [!code-vb[3doverview#3DOverview3DN6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn6)]  
  
 [!code-csharp[3doverview#3DOverview3DN7](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn7)]
 [!code-vb[3doverview#3DOverview3DN7](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn7)]  
  
<a name="materials"></a>   
## <a name="applying-materials-to-the-model"></a>Aplicación de materiales al modelo  
  
 Para que una malla parezca un objeto tridimensional, debe tener una textura aplicada que cubra la superficie definida por sus vértices y triángulos, de manera que se pueda iluminar y proyectar por la cámara. En [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)], usa el <xref:System.Windows.Media.Brush> clase para aplicar colores, patrones, degradados u otro contenido visual a las áreas de la pantalla.  El aspecto de los objetos [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)], sin embargo, depende del modelo de iluminación, no solo del color o del patrón que se les aplica. Los objetos reales reflejan la luz de manera distinta según la calidad de su superficie: las superficies satinadas y brillantes no tienen el mismo aspecto que las superficies ásperas o mates, y algunos objetos parecen absorber la luz, mientras que otros la emiten. Puede aplicar a los objetos [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] los mismos pinceles que a los objetos [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)], pero no directamente.  
  
 Para definir las características de la superficie de un modelo, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] usa el <xref:System.Windows.Media.Media3D.Material> clase abstracta. Las subclases concretas de Material determinan algunas de las características del aspecto de la superficie del modelo y, además, cada una de ellas proporciona una propiedad Brush a la que puede pasar SolidColorBrush, TileBrush o VisualBrush.  
  
-   <xref:System.Windows.Media.Media3D.DiffuseMaterial> Especifica que el pincel se aplicará al modelo como si estuviera iluminado con una luz difusa. Utilizar DiffuseMaterial es lo que más se parece al uso directo de pinceles en los modelos [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)]; las superficies del modelo no reflejan la luz como si brillasen.  
  
-   <xref:System.Windows.Media.Media3D.SpecularMaterial> Especifica que el pincel se aplicará al modelo como si fuera de la superficie del modelo dura o brillante, capaz de reflejar la iluminación. Puede establecer el grado al que la textura sugerirá esta cualidad, o "brillo", especificando un valor para el <xref:System.Windows.Media.Media3D.SpecularMaterial.SpecularPower%2A> propiedad.  
  
-   <xref:System.Windows.Media.Media3D.EmissiveMaterial> le permite especificar que la textura se aplicará como si el modelo estuviera emitiendo luz igual al color del pincel. Esto no convierte el modelo en una luz; sin embargo, participará de manera diferente en el sombreado que si se aplica textura con DiffuseMaterial o SpecularMaterial.  
  
 Para mejorar el rendimiento, la ocultas de un <xref:System.Windows.Media.Media3D.GeometryModel3D> (esas caras que están fuera de la vista porque están en el lado opuesto del modelo de la cámara) se seleccionan de la escena.  Para especificar un <xref:System.Windows.Media.Media3D.Material> para aplicar a la cara oculta de un modelo como un plano, establezca el modelo <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> propiedad.  
  
 Para lograr algunas cualidades de la superficie, como el brillo o los efectos de reflejo, puede ser conveniente aplicar sucesivamente varios pinceles diferentes a un modelo. Puede aplicar y reutilizar varios materiales mediante la <xref:System.Windows.Media.Media3D.MaterialGroup> clase. Los elementos secundarios de MaterialGroup se aplican del primero al último en varias pasadas de representación.  
  
 En los ejemplos de código siguientes se muestra cómo aplicar un color sólido y un dibujo como pinceles a los modelos [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)].  
  
 [!code-xaml[basic3d#Basic3DXAML3DN5](~/samples/snippets/xaml/VS_Snippets_Wpf/Basic3D/XAML/Window1.xaml#basic3dxaml3dn5)]  
  
 [!code-xaml[3doverview#3DOverview3DN9](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/app.xaml#3doverview3dn9)]  
  
 [!code-csharp[3doverview#3DOverview3DN8](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn8)]
 [!code-vb[3doverview#3DOverview3DN8](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn8)]  
  
<a name="lights"></a>   
## <a name="illuminating-the-scene"></a>Iluminación de la escena  
 Las luces de los gráficos [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] hacen lo mismo que las luces en el mundo real: permiten ver las superficies. Más concretamente, las luces determinan qué parte de una escena se incluye en la proyección. Los objetos de luz en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] crean gran variedad de efectos de luz y sombra y siguen el modelo de comportamiento de diversas luces del mundo real. Debe incluir por lo menos una luz en la escena, pues de lo contrario no habrá ningún modelo visible.  
  
 Las luces siguientes se derivan de la clase base <xref:System.Windows.Media.Media3D.Light>:  
  
-   <xref:System.Windows.Media.Media3D.AmbientLight>: Proporciona iluminación de ambiente que ilumina todos los objetos uniformemente, independientemente de su ubicación u orientación.  
  
-   <xref:System.Windows.Media.Media3D.DirectionalLight>: Ilumina como una fuente de luz distante.  Las luces direccionales tienen un <xref:System.Windows.Media.Media3D.DirectionalLight.Direction%2A> especificado como un Vector3D, pero ninguna ubicación concreta.  
  
-   <xref:System.Windows.Media.Media3D.PointLight>: Ilumina como una fuente de luz cercana. Las luces puntuales tienen posición y emiten la luz desde esa posición. Los objetos de la escena se iluminan dependiendo de su posición y distancia con respecto a la luz. <xref:System.Windows.Media.Media3D.PointLightBase> expone un <xref:System.Windows.Media.Media3D.PointLightBase.Range%2A> propiedad, que determina una distancia más allá del cual no se iluminará los modelos por la luz. PointLight también expone propiedades de atenuación que determinan cómo disminuye la intensidad de la luz con la distancia. Puede especificar interpolaciones constantes, lineales o cuadráticas para la atenuación de la luz.  
  
-   <xref:System.Windows.Media.Media3D.SpotLight>: Se hereda de <xref:System.Windows.Media.Media3D.PointLight>. Los focos de luz iluminan como las luces puntuales, y tienen posición y dirección. Proyectan la luz en un área cónica establecido por <xref:System.Windows.Media.Media3D.SpotLight.InnerConeAngle%2A> y <xref:System.Windows.Media.Media3D.SpotLight.OuterConeAngle%2A> propiedades, especificadas en grados.  
  
 Las luces son <xref:System.Windows.Media.Media3D.Model3D> objetos, por lo que puede transformar y animar propiedades de la luz, incluida la posición, color, dirección y rango.  
  
 [!code-xaml[hittest3d#HitTest3D3DN6](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTest3D/CSharp/Window1.xaml#hittest3d3dn6)]  
  
 [!code-csharp[basic3d#Basic3D3DN11](~/samples/snippets/csharp/VS_Snippets_Wpf/Basic3D/CSharp/Window1.xaml.cs#basic3d3dn11)]
 [!code-vb[basic3d#Basic3D3DN11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Basic3D/visualbasic/window1.xaml.vb#basic3d3dn11)]  
  
 [!code-csharp[basic3d#Basic3D3DN12](~/samples/snippets/csharp/VS_Snippets_Wpf/Basic3D/CSharp/Window1.xaml.cs#basic3d3dn12)]
 [!code-vb[basic3d#Basic3D3DN12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Basic3D/visualbasic/window1.xaml.vb#basic3d3dn12)]  
  
 [!code-csharp[basic3d#Basic3D3DN13](~/samples/snippets/csharp/VS_Snippets_Wpf/Basic3D/CSharp/Window1.xaml.cs#basic3d3dn13)]
 [!code-vb[basic3d#Basic3D3DN13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Basic3D/visualbasic/window1.xaml.vb#basic3d3dn13)]  
  
<a name="transforms"></a>   
## <a name="transforming-models"></a>Transformación de modelos  
 Al crear modelos, estos tienen una ubicación determinada en la escena. Para mover esos modelos por la escena, girarlos o cambiar su tamaño, no es práctico cambiar los vértices que definen los propios modelos.  En lugar de ello, al igual que en [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)], se aplican transformaciones a los modelos.  
  
 Cada objeto de modelo tiene un <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> propiedad con el que puede mover, reorientar o cambiar el tamaño del modelo.  Al aplicar una transformación, en realidad lo que se hace es desplazar todos los puntos del modelo según un vector o valor especificado por la transformación. Es decir, se transforma el espacio de coordenadas en el que se ha definido el modelo ("espacio del modelo"), pero no se cambian los valores que constituyen la geometría del modelo en el sistema de coordenadas de la escena completa ("espacio universal").  
  
 Para más información acerca de la transformación de modelos, consulte [Información general sobre transformaciones de modelos 3D](3-d-transformations-overview.md).  
  
<a name="animations"></a>   
## <a name="animating-models"></a>Animación de modelos  
 La implementación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] utiliza el mismo sistema de control de tiempo y animación que los gráficos [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)]. En otras palabras, para animar una escena 3D, se animan las propiedades de sus modelos. Es posible animar directamente las propiedades de los elementos primitivos, pero suele ser más fácil animar las transformaciones que cambian la posición o el aspecto de los modelos. Dado que se pueden aplicar transformaciones a <xref:System.Windows.Media.Media3D.Model3DGroup> objetos, así como los modelos individuales, es posible aplicar un conjunto de animaciones a un elemento secundario de un Model3DGroup y otro conjunto de animaciones a un grupo de objetos secundarios. También puede lograr gran variedad de efectos visuales animando las propiedades de iluminación de la escena. Finalmente, si lo desea, puede animar la propia proyección, animando la posición de la cámara o el campo de visión. Para información general sobre el sistema de control de tiempo y animación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], consulte los temas [Información general sobre animaciones](animation-overview.md), [Información general sobre objetos Storyboard](storyboards-overview.md) y [Información general sobre objetos Freezable](../advanced/freezable-objects-overview.md).  
  
 Para animar un objeto en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], se crea una escala de tiempo, se define una animación (que, en realidad, es un cambio de algún valor de propiedad a lo largo del tiempo) y se especifica la propiedad a la que aplicar la animación. Dado que todos los objetos en un [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] escena son elementos secundarios de <xref:System.Windows.Controls.Viewport3D>, las propiedades de destino de cualquier animación que desea aplicar a la escena son propiedades de las propiedades de Viewport3D.  
  
 Supongamos que desea hacer que un modelo parezca tambalearse en su lugar. Podría optar por aplicar un <xref:System.Windows.Media.Media3D.RotateTransform3D> al modelo y animar el eje de giro de un vector a otro. En el ejemplo de código siguiente se muestra cómo aplicar Vector3DAnimation a la propiedad Axis de la propiedad Rotation3D de la transformación, suponiendo que RotateTransform3D es una de las diversas transformaciones aplicadas al modelo con TransformGroup.  
  
 [!code-csharp[3doverview#3DOverview3DN1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn1)]
 [!code-vb[3doverview#3DOverview3DN1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn1)]  
  
 [!code-csharp[3doverview#3DOverview3DN3](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn3)]
 [!code-vb[3doverview#3DOverview3DN3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn3)]  
  
 [!code-csharp[3doverview#3DOverview3DN4](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn4)]
 [!code-vb[3doverview#3DOverview3DN4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn4)]  
  
 [!code-csharp[3doverview#3DOverview3DN5](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn5)]
 [!code-vb[3doverview#3DOverview3DN5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn5)]  
  
<a name="animations1"></a>   
## <a name="add-3-d-content-to-the-window"></a>Incorporación de contenido 3D a la ventana  
 Para representar la escena, agregue modelos y luces a un <xref:System.Windows.Media.Media3D.Model3DGroup>, a continuación, establezca el <xref:System.Windows.Media.Media3D.Model3DGroup> como el <xref:System.Windows.Media.Media3D.ModelVisual3D.Content%2A> de un <xref:System.Windows.Media.Media3D.ModelVisual3D>. Agregar el <xref:System.Windows.Media.Media3D.ModelVisual3D> a la <xref:System.Windows.Controls.Viewport3D.Children%2A> colección de la <xref:System.Windows.Controls.Viewport3D>. Agregue cámaras a la <xref:System.Windows.Controls.Viewport3D> estableciendo su <xref:System.Windows.Controls.Viewport3D.Camera%2A> propiedad.  
  
 Por último, agregue el <xref:System.Windows.Controls.Viewport3D> a la ventana. Cuando el <xref:System.Windows.Controls.Viewport3D> se incluye como el contenido de un elemento de diseño, como Canvas, especifique el tamaño de la Viewport3D estableciendo su <xref:System.Windows.FrameworkElement.Height%2A> y <xref:System.Windows.FrameworkElement.Width%2A> propiedades (se hereda de <xref:System.Windows.FrameworkElement>).  
  
 [!code-xaml[hostingwpfusercontrolinwf#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/HostingWpfUserControlInWf/ConeControl.xaml#1)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Controls.Viewport3D>
- <xref:System.Windows.Media.Media3D.PerspectiveCamera>
- <xref:System.Windows.Media.Media3D.DirectionalLight>
- <xref:System.Windows.Media.Media3D.Material>
- [Información general sobre transformaciones de modelos 3D](3-d-transformations-overview.md)
- [Maximizar el rendimiento de representación 3D en WPF](maximize-wpf-3d-performance.md)
- [Temas "Cómo..."](3-d-graphics-how-to-topics.md)
- [Información general sobre formas y dibujo básico en WPF](shapes-and-basic-drawing-in-wpf-overview.md)
- [Pintar con imágenes, dibujos y elementos visuales](painting-with-images-drawings-and-visuals.md)
