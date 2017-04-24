---
title: "Informaci&#243;n general sobre gr&#225;ficos 3D | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "gráficos 3D"
  - "gráficos [WPF], 3D"
ms.assetid: 67f31ed4-e36b-4b02-9889-dcce245d7afc
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 20
---
# Informaci&#243;n general sobre gr&#225;ficos 3D
<a name="introduction"></a> La funcionalidad de [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] permite a los desarrolladores dibujar, transformar y animar gráficos 3D en el marcado y en el código de procedimiento.  Los desarrolladores pueden combinar gráficos [!INCLUDE[TLA#tla_2d](../../../../includes/tlasharptla-2d-md.md)] y [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] para crear controles enriquecidos, proporcionar ilustraciones complejas de datos o mejorar la experiencia del usuario de la interfaz de una aplicación. La compatibilidad con [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] no se ha diseñado para proporcionar una plataforma completa de desarrollo de juegos. En este tema se proporciona información general sobre la funcionalidad de [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] en el sistema de gráficos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
   
  
<a name="threed_in_2d"></a>   
## 3D en un contenedor 2D  
 El contenido de los gráficos [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se encapsula en un elemento, <xref:System.Windows.Controls.Viewport3D>, que puede participar en la estructura de elementos bidimensionales.  El sistema de gráficos trata los objetos <xref:System.Windows.Controls.Viewport3D> como elementos visuales bidimensionales, al igual que ocurre con muchos otros elementos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  <xref:System.Windows.Controls.Viewport3D> funciona como una ventana \(una ventanilla\) de una escena tridimensional.  Expresado de modo más preciso, es la superficie sobre la que se proyecta una escena [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)].  
  
 En una aplicación [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] convencional, utilice <xref:System.Windows.Controls.Viewport3D> como cualquier otro elemento contenedor, como Grid o Canvas.  Aunque puede utilizar <xref:System.Windows.Controls.Viewport3D> con otros objetos de dibujo [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] en el mismo gráfico de escena, no puede interpenetrar objetos [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] y [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] dentro de <xref:System.Windows.Controls.Viewport3D>.  Este tema se centrará en cómo dibujar gráficos [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] dentro de <xref:System.Windows.Controls.Viewport3D>.  
  
<a name="coord_space"></a>   
## Espacio de coordenadas 3D  
 El sistema de coordenadas de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] para gráficos [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] localiza el origen en la parte superior izquierda del área de representación \(que suele ser la pantalla\).  En el sistema [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)], los valores positivos del eje X se extienden hacia la derecha, y los valores positivos del eje Y extienden hacia abajo.  En el sistema de coordenadas [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)], sin embargo, el origen se encuentra en el centro del área de representación, los valores positivos del eje X se extienden hacia la derecha, los valores positivos del eje Y se extienden hacia arriba \(no hacia abajo\) y los valores positivos del eje Z se extienden hacia el exterior partiendo del origen, es decir, hacia el espectador.  
  
 ![Sistemas de coordenadas](../../../../docs/framework/wpf/graphics-multimedia/media/coordsystem-1.png "CoordSystem\-1")  
Representaciones convencionales de los sistemas de coordenadas 2D y 3D  
  
 El espacio definido por estos ejes es el marco estático de referencia para los objetos [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Cuando se generan modelos en este espacio y se crean luces y cámaras para verlos, es útil distinguir este marco estático de referencia, o "espacio universal", del marco de referencia local creado para cada modelo al aplicarle transformaciones.  Recuerde también que los objetos del espacio universal podrían parecer completamente diferentes, o incluso no verse en absoluto, dependiendo de la configuración de las luces y la cámara, pero que la posición de la cámara no cambia la ubicación de los objetos en el espacio universal.  
  
<a name="cameras"></a>   
## Cámaras y proyecciones  
 Los programadores que trabajan en [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] están acostumbrado a colocar los elementos de dibujo primitivos en una pantalla bidimensional.  Al crear una escena [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)], es importante recordar que, en realidad, se está creando una representación [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] de los objetos [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)].  Dado que una escena [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] tiene un aspecto diferente dependiendo del punto de vista del espectador, debe especificar ese punto de vista.  La clase <xref:System.Windows.Media.Media3D.Camera> permite especificar este punto de vista para una escena [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)].  
  
 Otra manera de entender cómo se representa una escena [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] en una superficie [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] consiste en describir dicha escena como una proyección sobre la superficie de visualización.  <xref:System.Windows.Media.Media3D.ProjectionCamera> permite especificar proyecciones diferentes y sus propiedades para cambiar la manera en que el espectador ve los modelos [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)].  <xref:System.Windows.Media.Media3D.PerspectiveCamera> especifica una proyección en escorzo de la escena.  En otras palabras, <xref:System.Windows.Media.Media3D.PerspectiveCamera> proporciona una perspectiva de punto de fuga.  Puede especificar la posición de la cámara en el espacio de coordenadas de la escena, la dirección y el campo de visión de la cámara, y un vector que define la dirección "hacia arriba" en la escena.  En el diagrama siguiente se muestra la proyección de <xref:System.Windows.Media.Media3D.PerspectiveCamera>.  
  
 Las propiedades <xref:System.Windows.Media.Media3D.ProjectionCamera.NearPlaneDistance%2A> y <xref:System.Windows.Media.Media3D.ProjectionCamera.FarPlaneDistance%2A> de <xref:System.Windows.Media.Media3D.ProjectionCamera> limitan el intervalo de proyección de la cámara.  Dado que las cámaras se pueden ubicar en cualquier parte de la escena, es posible situarlas dentro de un modelo o muy cerca de él, con lo que resultaría difícil distinguir correctamente los objetos.  <xref:System.Windows.Media.Media3D.ProjectionCamera.NearPlaneDistance%2A> permite especificar una distancia mínima a la cámara a partir de la cual no se dibujarán objetos.  A la inversa, <xref:System.Windows.Media.Media3D.ProjectionCamera.FarPlaneDistance%2A> permite especificar una distancia máxima a la cámara, más allá de la que no se dibujarán objetos, lo que garantice que no se incluyan en la escena aquellos objetos que estén demasiado lejos para ser reconocibles.  
  
 ![Instalación de cámara](../../../../docs/framework/wpf/graphics-multimedia/media/coordsystem-6.png "CoordSystem\-6")  
Posición de la cámara  
  
 <xref:System.Windows.Media.Media3D.OrthographicCamera> especifica una proyección ortogonal de un modelo [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] sobre una superficie visual [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)].  Al igual que otras cámaras, especifica una posición, dirección de visualización y dirección "hacia arriba".  Sin embargo, a diferencia de <xref:System.Windows.Media.Media3D.PerspectiveCamera>, <xref:System.Windows.Media.Media3D.OrthographicCamera> describe una proyección que no incluye la perspectiva en escorzo.  Es decir, <xref:System.Windows.Media.Media3D.OrthographicCamera> describe un cuadro de vista cuyos lados son paralelos, en lugar de uno cuyos lados convergen en un punto de la cámara.  La imagen siguiente muestra el mismo modelo visto con <xref:System.Windows.Media.Media3D.PerspectiveCamera> y con <xref:System.Windows.Media.Media3D.OrthographicCamera>.  
  
 ![Proyección en perspectiva y ortográfica](../../../../docs/framework/wpf/graphics-multimedia/media/camera-projections4.png "Camera\_projections4")  
Perspectiva y proyecciones ortográficas  
  
 En el código siguiente se muestran algunos valores de cámara típicos.  
  
 [!code-csharp[3dgallery_procedural_snip#Basic3DShapeCodeExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Basic3DShapeExample.cs#basic3dshapecodeexampleinline1)]
 [!code-vb[3dgallery_procedural_snip#Basic3DShapeCodeExampleInline1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/basic3dshapeexample.vb#basic3dshapecodeexampleinline1)]  
  
<a name="models_meshes"></a>   
## Elementos primitivos de modelo y de malla  
 <xref:System.Windows.Media.Media3D.Model3D> es la clase base abstracta que representa un objeto [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] genérico.  Para compilar una escena [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)], necesita algunos objetos que ver; los objetos que componen el gráfico de escena se derivan de la clase <xref:System.Windows.Media.Media3D.Model3D>.  En la actualidad, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] permite geometrías de modelado con <xref:System.Windows.Media.Media3D.GeometryModel3D>.  La propiedad <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A> de este modelo acepta un elemento primitivo de malla.  
  
 Para crear un modelo, comience por crear un elemento primitivo, o malla.  Un elemento [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] primitivo es una colección de vértices que constituyen una entidad [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] única.  La mayoría de los sistemas [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] proporcionan elementos primitivos modelados a partir de la figura cerrada más simple: un triángulo definido por tres vértices.  Dado que los tres puntos de un triángulo son coplanares, puede seguir agregando triángulos para modelar formas más complejas, denominadas mallas.  
  
 El sistema [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona actualmente la clase <xref:System.Windows.Media.Media3D.MeshGeometry3D>, que permite especificar cualquier geometría; en este momento, no admite elementos [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] primitivos predefinidos, tales como esferas o formas cúbicas.  Empiece por crear <xref:System.Windows.Media.Media3D.MeshGeometry3D> especificando una lista de vértices de triángulos como su propiedad <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A>.  Cada vértice se especifica como un <xref:System.Windows.Media.Media3D.Point3D>.  \(En [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], especifique esta propiedad como una lista de números agrupados en ternas, que representan las coordenadas de cada vértice.\) Según cuál sea la geometría, la malla puede estar compuesta de muchos triángulos, algunos de los cuales compartirán las mismas esquinas \(vértices\).  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] necesita información sobre qué triángulos comparten qué vértices para dibujar la malla correctamente.  Esta información se proporciona especificando una lista de índices de triángulos con la propiedad <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A>.  Esta lista especifica el orden en el que los puntos especificados en la lista <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> determinarán un triángulo.  
  
 [!code-xml[basic3d#Basic3DXAML3DN3](../../../../samples/snippets/xaml/VS_Snippets_Wpf/Basic3D/XAML/Window1.xaml#basic3dxaml3dn3)]  
  
 En el ejemplo anterior, la lista <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> especifica ocho vértices para definir una malla en forma de cubo.  La propiedad <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A> especifica una lista de doce grupos de tres índices.  Cada número de la lista hace referencia a un desplazamiento en la lista <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A>.  Por ejemplo, los tres primeros vértices especificados por la lista <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> son \(1,1,0\), \(0,1,0\) y \(0,0,0\).  Los tres primeros índices especificados por la lista <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A> son 0, 2 y 1, que corresponden a los puntos primero, tercero y segundo de la lista <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A>.  Como resultado, el primer triángulo que constituye el modelo del cubo se creará de \(1,1,0\) a \(0,1,0\) y a \(0,0,0\), y los once triángulos restantes se determinarán de igual forma.  
  
 Puede seguir definiendo el modelo especificando valores para las propiedades <xref:System.Windows.Media.Media3D.MeshGeometry3D.Normals%2A> y <xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A>.  Para representar la superficie del modelo, el sistema de gráficos necesita información sobre en qué dirección mira la superficie de cualquier triángulo dado.  Utiliza esta información para realizar los cálculos de iluminación del modelo: las superficies que miran directamente hacia una fuente de luz parecen más luminosas que las que tienen un ángulo que las oculta de la luz.  Aunque [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] puede determinar los vectores normales predeterminados utilizando las coordenadas de posición, también es posible especificar vectores normales diferentes para crear un aspecto más aproximado de las superficies curvas.  
  
 La propiedad <xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A> especifica una colección de puntos \(<xref:System.Windows.Point>\) que indica al sistema de gráficos cómo asignar las coordenadas que determinan cómo trazar una textura en los vértices de la malla.  Las <xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A> se especifican como un valor comprendido entre cero y 1, incluidos.  Como sucede con la propiedad <xref:System.Windows.Media.Media3D.MeshGeometry3D.Normals%2A>, el sistema de gráficos puede calcular las coordenadas de textura predeterminadas, pero si lo desea puede establecer coordenadas de textura diferentes a fin de controlar la asignación de una textura que incluya parte de un patrón repetitivo, por ejemplo.  Encontrará más información sobre coordenadas de textura en los temas siguientes o en Managed Direct3D SDK.  
  
 En el ejemplo siguiente se muestra cómo crear una cara del modelo del cubo en código de procedimiento.  Observe que puede dibujar el cubo completo como un solo objeto GeometryModel3D; en este ejemplo se dibuja la cara del cubo como un modelo distinto a fin de aplicar después texturas independientes a cada cara.  
  
 [!code-csharp[3doverview#3DOverview3DN6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn6)]
 [!code-vb[3doverview#3DOverview3DN6](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn6)]  
  
 [!code-csharp[3doverview#3DOverview3DN7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn7)]
 [!code-vb[3doverview#3DOverview3DN7](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn7)]  
  
<a name="materials"></a>   
## Aplicar materiales al modelo  
 Para que una malla parezca un objeto tridimensional, debe tener una textura aplicada que cubra la superficie definida por sus vértices y triángulos, de manera que se pueda iluminar y proyectar por la cámara.  En [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)], se utiliza la clase <xref:System.Windows.Media.Brush> para aplicar colores, patrones, degradados y otro contenido visual a las áreas de la pantalla.  El aspecto de los objetos [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)], sin embargo, depende del modelo de iluminación, no sólo del color o del patrón que se les aplica.  Los objetos reales reflejan la luz de manera distinta según la calidad de su superficie: las superficies satinadas y brillantes no tienen el mismo aspecto que las superficies ásperas o mates, y algunos objetos parecen absorber la luz, mientras que otros la emiten.  Puede aplicar a los objetos [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] los mismos pinceles que a los objetos [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)], pero no directamente.  
  
 Para definir las características de la superficie de un modelo, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] utiliza la clase abstracta <xref:System.Windows.Media.Media3D.Material>.  Las subclases concretas de Material determinan algunas de las características del aspecto de la superficie del modelo y, además, cada una de ellas proporciona una propiedad Brush a la que puede pasar SolidColorBrush, TileBrush o VisualBrush.  
  
-   <xref:System.Windows.Media.Media3D.DiffuseMaterial> especifica que el pincel se aplicará al modelo como si estuviera iluminado con una luz difusa.  Utilizar DiffuseMaterial es lo que más se parece al uso directo de pinceles en los modelos [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)]; las superficies del modelo no reflejan la luz como si brillasen.  
  
-   <xref:System.Windows.Media.Media3D.SpecularMaterial> especifica que el pincel se aplicará al modelo como si la superficie del modelo fuese dura o brillante, capaz de reflejar la iluminación.  Puede establecer el grado en que la textura sugerirá esta cualidad de reflexión, o "brillo", especificando un valor para la propiedad <xref:System.Windows.Media.Media3D.SpecularMaterial.SpecularPower%2A>.  
  
-   <xref:System.Windows.Media.Media3D.EmissiveMaterial> permite especificar que la textura se aplicará como si el modelo estuviera emitiendo luz del mismo color que el pincel.  Esto no convierte el modelo en una luz; sin embargo, participará de manera diferente en el sombreado que si se aplica textura con DiffuseMaterial o SpecularMaterial.  
  
 Para mejorar rendimiento, las caras ocultas de <xref:System.Windows.Media.Media3D.GeometryModel3D> \(aquéllas que están fuera de la vista porque se encuentran en el lado del modelo opuesto a la cámara\) se seleccionan de la escena.  Para especificar el <xref:System.Windows.Media.Media3D.Material> que se aplicará a la cara oculta de un modelo, como un plano, establezca la propiedad <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> del modelo.  
  
 Para lograr algunas cualidades de la superficie, como el brillo o los efectos de reflejo, puede ser conveniente aplicar sucesivamente varios pinceles diferentes a un modelo.  Puede aplicar y reutilizar varios materiales mediante la clase <xref:System.Windows.Media.Media3D.MaterialGroup>.  Los elementos secundarios de MaterialGroup se aplican del primero al último en varias pasadas de representación.  
  
 En los ejemplos de código siguientes se muestra cómo aplicar un color sólido y un dibujo como pinceles a los modelos [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)].  
  
 [!code-xml[basic3d#Basic3DXAML3DN5](../../../../samples/snippets/xaml/VS_Snippets_Wpf/Basic3D/XAML/Window1.xaml#basic3dxaml3dn5)]  
  
 [!code-xml[3doverview#3DOverview3DN9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/app.xaml#3doverview3dn9)]  
  
 [!code-csharp[3doverview#3DOverview3DN8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn8)]
 [!code-vb[3doverview#3DOverview3DN8](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn8)]  
  
<a name="lights"></a>   
## Iluminar la escena  
 Las luces de los gráficos [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] hacen lo mismo que las luces en el mundo real: permiten ver las superficies.  Más concretamente, las luces determinan qué parte de una escena se incluye en la proyección.  Los objetos de luz en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] crean gran variedad de efectos de luz y sombra y siguen el modelo de comportamiento de diversas luces del mundo real.  Debe incluir por lo menos una luz en la escena, pues de lo contrario no habrá ningún modelo visible.  
  
 Las luces siguientes se derivan de la clase base <xref:System.Windows.Media.Media3D.Light>:  
  
-   <xref:System.Windows.Media.Media3D.AmbientLight>: proporciona iluminación de ambiente que ilumina uniformemente todos los objetos sin tener en cuenta su ubicación u orientación.  
  
-   <xref:System.Windows.Media.Media3D.DirectionalLight>: ilumina como una fuente de luz distante.  Las luces direccionales tienen <xref:System.Windows.Media.Media3D.DirectionalLight.Direction%2A>, que se especifica como Vector3D, pero ninguna ubicación concreta.  
  
-   <xref:System.Windows.Media.Media3D.PointLight>: ilumina como una fuente de luz cercana.  Las luces puntuales tienen posición y emiten la luz desde esa posición.  Los objetos de la escena se iluminan dependiendo de su posición y distancia con respecto a la luz.  <xref:System.Windows.Media.Media3D.PointLightBase> expone una propiedad <xref:System.Windows.Media.Media3D.PointLightBase.Range%2A>, que determina una distancia más allá de la cual la luz no iluminará los modelos.  PointLight también expone propiedades de atenuación que determinan cómo disminuye la intensidad de la luz con la distancia.  Puede especificar interpolaciones constantes, lineales o cuadráticas para la atenuación de la luz.  
  
-   <xref:System.Windows.Media.Media3D.SpotLight>: hereda de <xref:System.Windows.Media.Media3D.PointLight>.  Los focos de luz iluminan como las luces puntuales, y tienen posición y dirección.  Proyectan la luz en una área cónica establecida por las propiedades <xref:System.Windows.Media.Media3D.SpotLight.InnerConeAngle%2A> y <xref:System.Windows.Media.Media3D.SpotLight.OuterConeAngle%2A>, especificadas en grados.  
  
 Las luces son objetos <xref:System.Windows.Media.Media3D.Model3D>, por lo que puede transformar y animar las propiedades de la luz, incluidas su posición, posición, color, dirección y alcance.  
  
 [!code-xml[hittest3d#HitTest3D3DN6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTest3D/CSharp/Window1.xaml#hittest3d3dn6)]  
  
 [!code-csharp[basic3d#Basic3D3DN11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Basic3D/CSharp/Window1.xaml.cs#basic3d3dn11)]
 [!code-vb[basic3d#Basic3D3DN11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Basic3D/visualbasic/window1.xaml.vb#basic3d3dn11)]  
  
 [!code-csharp[basic3d#Basic3D3DN12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Basic3D/CSharp/Window1.xaml.cs#basic3d3dn12)]
 [!code-vb[basic3d#Basic3D3DN12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Basic3D/visualbasic/window1.xaml.vb#basic3d3dn12)]  
  
 [!code-csharp[basic3d#Basic3D3DN13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Basic3D/CSharp/Window1.xaml.cs#basic3d3dn13)]
 [!code-vb[basic3d#Basic3D3DN13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Basic3D/visualbasic/window1.xaml.vb#basic3d3dn13)]  
  
<a name="transforms"></a>   
## Transformar modelos  
 Al crear modelos, éstos tienen una ubicación determinada en la escena.  Para mover esos modelos por la escena, girarlos o cambiar su tamaño, no es práctico cambiar los vértices que definen los propios modelos.  En lugar de ello, al igual que en [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)], se aplican transformaciones a los modelos.  
  
 Cada objeto del modelo tiene una propiedad <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> con la que puede mover, reorientar o cambiar el tamaño del modelo.  Al aplicar una transformación, en realidad lo que se hace es desplazar todos los puntos del modelo según un vector o valor especificado por la transformación.  Es decir, se transforma el espacio de coordenadas en el que se ha definido el modelo \("espacio del modelo"\), pero no se cambian los valores que constituyen la geometría del modelo en el sistema de coordenadas de la escena completa \("espacio universal"\).  
  
 Para obtener más información acerca de la transformación de modelos, consulte [Información general sobre transformaciones de modelos 3D](../../../../docs/framework/wpf/graphics-multimedia/3-d-transformations-overview.md).  
  
<a name="animations"></a>   
## Animar modelos  
 La implementación de [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] utiliza el mismo sistema de control de tiempo y animación que los gráficos [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)].  En otras palabras, para animar una escena 3D, se animan las propiedades de sus modelos.  Es posible animar directamente las propiedades de los elementos primitivos, pero suele ser más fácil animar las transformaciones que cambian la posición o el aspecto de los modelos.  Dado que las transformaciones se pueden aplicar a los objetos <xref:System.Windows.Media.Media3D.Model3DGroup> así como a los modelos individuales, es posible de aplicar un conjunto de animaciones a un elemento secundario de Model3DGroup y otro conjunto de animaciones a un grupo de objetos secundarios.  También puede lograr gran variedad de efectos visuales animando las propiedades de iluminación de la escena.  Finalmente, si lo desea puede animar la propia proyección, animando la posición de la cámara o el campo de visión.  Para obtener información general sobre el sistema de control de tiempo y animación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], consulte los temas [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md), [Información general sobre objetos Storyboard](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md) y [Información general sobre objetos Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
 Para animar un objeto en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], se crea una escala de tiempo, se define una animación \(que, en realidad, es un cambio de algún valor de propiedad a lo largo del tiempo\) y se especifica la propiedad a la que aplicar la animación.  Dado que todos los objetos de una escena [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] son elementos secundarios de <xref:System.Windows.Controls.Viewport3D>, las propiedades de destino de cualquier animación que desea aplicar a la escena son propiedades de propiedades de Viewport3D.  
  
 Supongamos que desea hacer que un modelo parezca tambalearse en su lugar.  Podría aplicar <xref:System.Windows.Media.Media3D.RotateTransform3D> al modelo y animar el eje de giro de un vector a otro.  En el ejemplo de código siguiente se muestra cómo aplicar Vector3DAnimation a la propiedad Axis de la propiedad Rotation3D de la transformación, suponiendo que RotateTransform3D es una de las diversas transformaciones aplicadas al modelo con TransformGroup.  
  
 [!code-csharp[3doverview#3DOverview3DN1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn1)]
 [!code-vb[3doverview#3DOverview3DN1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn1)]  
  
 [!code-csharp[3doverview#3DOverview3DN3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn3)]
 [!code-vb[3doverview#3DOverview3DN3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn3)]  
  
 [!code-csharp[3doverview#3DOverview3DN4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn4)]
 [!code-vb[3doverview#3DOverview3DN4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn4)]  
  
 [!code-csharp[3doverview#3DOverview3DN5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn5)]
 [!code-vb[3doverview#3DOverview3DN5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn5)]  
  
<a name="animations1"></a>   
## Agregar contenido 3D a la ventana  
 Para representar la escena, agregue modelos y luces a <xref:System.Windows.Media.Media3D.Model3DGroup>, a continuación, establezca <xref:System.Windows.Media.Media3D.Model3DGroup> en el <xref:System.Windows.Media.Media3D.ModelVisual3D.Content%2A> de <xref:System.Windows.Media.Media3D.ModelVisual3D>.  Agregue <xref:System.Windows.Media.Media3D.ModelVisual3D> a la colección <xref:System.Windows.Controls.Viewport3D.Children%2A> de <xref:System.Windows.Controls.Viewport3D>.  Agregue cámaras a <xref:System.Windows.Controls.Viewport3D>, estableciendo su propiedad <xref:System.Windows.Controls.Viewport3D.Camera%2A>.  
  
 Finalmente, agregue <xref:System.Windows.Controls.Viewport3D> a la ventana.  Cuando se incluye <xref:System.Windows.Controls.Viewport3D> como contenido de un elemento de diseño, como Canvas, debe especificar el tamaño de Viewport3D estableciendo las propiedades <xref:System.Windows.FrameworkElement.Height%2A> y <xref:System.Windows.FrameworkElement.Width%2A> \(heredadas de <xref:System.Windows.FrameworkElement>\).  
  
 [!code-xml[hostingwpfusercontrolinwf#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/HostingWpfUserControlInWf/ConeControl.xaml#1)]  
  
## Vea también  
 <xref:System.Windows.Controls.Viewport3D>   
 <xref:System.Windows.Media.Media3D.PerspectiveCamera>   
 <xref:System.Windows.Media.Media3D.DirectionalLight>   
 <xref:System.Windows.Media.Media3D.Material>   
 [Información general sobre transformaciones de modelos 3D](../../../../docs/framework/wpf/graphics-multimedia/3-d-transformations-overview.md)   
 [Maximizar el rendimiento de representación 3D en WPF](../../../../docs/framework/wpf/graphics-multimedia/maximize-wpf-3d-performance.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-how-to-topics.md)   
 [Información general sobre formas y dibujo básico en WPF](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)   
 [Pintar con imágenes, dibujos y elementos visuales](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)