---
title: Descripción general de los gráficos 3D
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 3D graphics [WPF]
- graphics [WPF], 3D
ms.assetid: 67f31ed4-e36b-4b02-9889-dcce245d7afc
ms.openlocfilehash: e4918f7737bbe57a4f29c6c5cff1099f4f21674b
ms.sourcegitcommit: e48a54ebe62e874500a7043f6ee0b77a744d55b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2020
ms.locfileid: "80291817"
---
# <a name="3d-graphics-overview"></a>Descripción general de los gráficos 3D
<a name="introduction"></a>La funcionalidad 3D [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] en permite a los desarrolladores dibujar, transformar y animar gráficos 3D en código de marcado y de procedimiento. Los desarrolladores pueden combinar gráficos 2D y 3D para crear controles enriquecidos, proporcionar ilustraciones complejas de datos o mejorar la experiencia del usuario de la interfaz de una aplicación. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] El soporte 3D no está diseñado para proporcionar una plataforma de desarrollo de juegos con todas las funciones. En este tema se proporciona información [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] general sobre la funcionalidad 3D en el sistema de gráficos.  

<a name="threed_in_2d"></a>
## <a name="3d-in-a-2d-container"></a>3D en un contenedor 2D  
 El contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] gráficos 3D <xref:System.Windows.Controls.Viewport3D>en se encapsula en un elemento, que puede participar en la estructura de elementos bidimensionales. El sistema de <xref:System.Windows.Controls.Viewport3D> gráficos trata como un elemento [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]visual bidimensional como muchos otros en . <xref:System.Windows.Controls.Viewport3D>funciona como una ventana (una ventana gráfica) en una escena tridimensional. Más exactamente, es una superficie en la que se proyecta una escena 3D.  
  
 En una aplicación 2D <xref:System.Windows.Controls.Viewport3D> convencional, utilice como lo haría con otro elemento contenedor como Grid o Canvas.  Aunque se <xref:System.Windows.Controls.Viewport3D> puede utilizar con otros objetos de dibujo 2D en el mismo <xref:System.Windows.Controls.Viewport3D>gráfico de escena, no se pueden interpenetrar objetos 2D y 3D dentro de un archivo .  Este tema se centrará en cómo dibujar <xref:System.Windows.Controls.Viewport3D>gráficos 3D dentro del archivo .  
  
<a name="coord_space"></a>
## <a name="3d-coordinate-space"></a>Espacio de coordenadas 3D  
 El [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sistema de coordenadas para gráficos 2D localiza el origen en la parte superior izquierda del área de renderizado (normalmente la pantalla). En el sistema 2D, los valores positivos del eje X proceden a la derecha y los valores positivos del eje Y proceden hacia abajo.  En el sistema de coordenadas 3D, sin embargo, el origen se encuentra en el centro del área de representación, con valores positivos del eje X procediendo hacia la derecha pero valores positivos del eje Y procediendo hacia arriba en su lugar, y valores positivos del eje z que avanzan hacia afuera desde el origen, hacia el espectador.  
  
 ![Sistemas de coordenadas](./media/coordsystem-1.png "CoordSystem-1")  
Representaciones convencionales del sistema de coordenadas 2D y 3D  
  
 El espacio definido por estos ejes es el marco [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]estacionario de referencia para objetos 3D en . Cuando se generan modelos en este espacio y se crean luces y cámaras para verlos, es útil distinguir este marco estático de referencia, o "espacio universal", del marco de referencia local creado para cada modelo al aplicarle transformaciones. Recuerde también que los objetos del espacio universal podrían parecer completamente diferentes, o incluso no verse en absoluto, dependiendo de la configuración de las luces y la cámara, pero que la posición de la cámara no cambia la ubicación de los objetos en el espacio universal.  
  
<a name="cameras"></a>
## <a name="cameras-and-projections"></a>Cámaras y proyecciones  
 Los desarrolladores que trabajan en 2D están acostumbrados a colocar primitivas de dibujo en una pantalla bidimensional. Al crear una escena 3D, es importante recordar que realmente está creando una representación 2D de objetos 3D. Dado que una escena 3D tiene un aspecto diferente en función del punto de vista del usuario, debe especificar ese punto de vista. La <xref:System.Windows.Media.Media3D.Camera> clase le permite especificar este punto de vista para una escena 3D.  
  
 Otra forma de entender cómo se representa una escena 3D en una superficie 2D es describiendo la escena como una proyección sobre la superficie de visualización. El <xref:System.Windows.Media.Media3D.ProjectionCamera> le permite especificar diferentes proyecciones y sus propiedades para cambiar la forma en que el onlooker ve los modelos 3D. A <xref:System.Windows.Media.Media3D.PerspectiveCamera> especifica una proyección que acorta la escena.  En otras palabras, la <xref:System.Windows.Media.Media3D.PerspectiveCamera> perspectiva proporciona punto de fuga.  Puede especificar la posición de la cámara en el espacio de coordenadas de la escena, la dirección y el campo de visión de la cámara y un vector que define la dirección de "arriba" en la escena. El diagrama siguiente <xref:System.Windows.Media.Media3D.PerspectiveCamera>ilustra la proyección de la .s.  
  
 Las <xref:System.Windows.Media.Media3D.ProjectionCamera.NearPlaneDistance%2A> <xref:System.Windows.Media.Media3D.ProjectionCamera.FarPlaneDistance%2A> propiedades <xref:System.Windows.Media.Media3D.ProjectionCamera> y las propiedades de limitan el rango de proyección de la cámara. Dado que las cámaras se pueden ubicar en cualquier parte de la escena, es posible situarlas dentro de un modelo o muy cerca de él, con lo que resultaría difícil distinguir correctamente los objetos.  <xref:System.Windows.Media.Media3D.ProjectionCamera.NearPlaneDistance%2A>le permite especificar una distancia mínima desde la cámara más allá de la cual no se dibujarán objetos.  Por el <xref:System.Windows.Media.Media3D.ProjectionCamera.FarPlaneDistance%2A> contrario, permite especificar una distancia desde la cámara más allá de la cual no se dibujarán objetos, lo que garantiza que los objetos demasiado alejados para ser reconocibles no se incluirán en la escena.  
  
 ![Colocación de la cámara](./media/coordsystem-6.png "CoordSystem-6")  
Posición de la cámara  
  
 <xref:System.Windows.Media.Media3D.OrthographicCamera>especifica una proyección ortogonal de un modelo 3D a una superficie visual 2D. Al igual que otras cámaras, especifica una posición, dirección de visualización y dirección "hacia arriba". A <xref:System.Windows.Media.Media3D.PerspectiveCamera>diferencia <xref:System.Windows.Media.Media3D.OrthographicCamera> de , sin embargo, describe una proyección que no incluye el escorzante de perspectiva. En otras <xref:System.Windows.Media.Media3D.OrthographicCamera> palabras, describe una caja de visualización cuyos lados son paralelos, en lugar de uno cuyos lados se encuentran en un punto de la cámara. La siguiente imagen muestra el mismo <xref:System.Windows.Media.Media3D.PerspectiveCamera> <xref:System.Windows.Media.Media3D.OrthographicCamera>modelo que se ha visto mediante y .  
  
 ![Proyección ortográfica y en perspectiva](./media/camera-projections4.png "Camera_projections4")  
Proyecciones ortográfica y en perspectiva  
  
 En el código siguiente se muestran algunas configuraciones de cámara típicas.  
  
 [!code-csharp[3dgallery_procedural_snip#Basic3DShapeCodeExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Basic3DShapeExample.cs#basic3dshapecodeexampleinline1)]
 [!code-vb[3dgallery_procedural_snip#Basic3DShapeCodeExampleInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/basic3dshapeexample.vb#basic3dshapecodeexampleinline1)]  
  
<a name="models_meshes"></a>
## <a name="model-and-mesh-primitives"></a>Elementos primitivos de modelo y de malla  
  
 <xref:System.Windows.Media.Media3D.Model3D>es la clase base abstracta que representa un objeto 3D genérico. Para crear una escena 3D, necesita algunos objetos para ver y <xref:System.Windows.Media.Media3D.Model3D>los objetos que componen el gráfico de escena derivan de . Actualmente, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] el soporta el <xref:System.Windows.Media.Media3D.GeometryModel3D>modelado de geometrías con . La <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A> propiedad de este modelo toma una primitiva de malla.  
  
 Para crear un modelo, comience por crear un elemento primitivo, o malla. Una primitiva 3D es una colección de vértices que forman una sola entidad 3D. La mayoría de los sistemas 3D proporcionan primitivas modeladas en la figura cerrada más simple: un triángulo definido por tres vértices.  Dado que los tres puntos de un triángulo son coplanares, puede seguir agregando triángulos para modelar formas más complejas, denominadas mallas.  
  
 El [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sistema 3D <xref:System.Windows.Media.Media3D.MeshGeometry3D> proporciona actualmente la clase, que le permite especificar cualquier geometría; actualmente no admite primitivas 3D predefinidas como esferas y formas cúbicas. Comience a <xref:System.Windows.Media.Media3D.MeshGeometry3D> crear un especificando una lista <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> de vértices de triángulo como su propiedad. Cada vértice se especifica <xref:System.Windows.Media.Media3D.Point3D>como un archivo .  (En [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], especifique esta propiedad como una lista de números agrupados en tres que representan las coordenadas de cada vértice.) Dependiendo de su geometría, la malla puede estar compuesta de muchos triángulos, algunos de los cuales comparten las mismas esquinas (vértices). [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] necesita información sobre qué triángulos comparten qué vértices para dibujar la malla correctamente. Esta información se proporciona especificando una lista <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A> de índices de triángulo con la propiedad. Esta lista especifica el orden en el <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> que los puntos especificados en la lista determinarán un triángulo.  
  
 [!code-xaml[basic3d#Basic3DXAML3DN3](~/samples/snippets/xaml/VS_Snippets_Wpf/Basic3D/XAML/Window1.xaml#basic3dxaml3dn3)]  
  
 En el ejemplo anterior, la <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> lista especifica ocho vértices para definir una malla con forma de cubo. La <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A> propiedad especifica una lista de doce grupos de tres índices.  Cada número de la lista hace <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> referencia a un desplazamiento en la lista.  Por ejemplo, los tres primeros vértices <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> especificados por la lista son (1,1,0), (0,1,0) y (0,0,0). Los tres primeros índices <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A> especificados por la lista son 0, 2 y 1, que <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> corresponden al primer, tercer y segundo punto de la lista. Como resultado, el primer triángulo que constituye el modelo del cubo se creará de (1,1,0) a (0,1,0) y a (0,0,0), y los once triángulos restantes se determinarán de igual forma.  
  
 Puede seguir definiendo el modelo especificando <xref:System.Windows.Media.Media3D.MeshGeometry3D.Normals%2A> <xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A> valores para las propiedades y.  Para representar la superficie del modelo, el sistema de gráficos necesita información sobre en qué dirección mira la superficie de cualquier triángulo dado. Utiliza esta información para realizar los cálculos de iluminación del modelo: las superficies que miran directamente hacia una fuente de luz parecen más luminosas que las que tienen un ángulo que las oculta de la luz. Aunque [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] puede determinar los vectores normales predeterminados utilizando las coordenadas de posición, también es posible especificar vectores normales diferentes para crear un aspecto más aproximado de las superficies curvas.  
  
 La <xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A> propiedad especifica una <xref:System.Windows.Point>colección de s que indican al sistema de gráficos cómo asignar las coordenadas que determinan cómo se dibuja una textura a los vértices de la malla. <xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A>se especifican como un valor entre cero y 1, ambos inclusive.  Al igual <xref:System.Windows.Media.Media3D.MeshGeometry3D.Normals%2A> que con la propiedad, el sistema de gráficos puede calcular las coordenadas de textura predeterminadas, pero puede elegir establecer diferentes coordenadas de textura para controlar la asignación de una textura que incluye parte de un patrón de repetición, por ejemplo. Encontrará más información sobre coordenadas de textura en los temas siguientes o en el SDK de Managed Direct3D.  
  
 En el ejemplo siguiente se muestra cómo crear una cara del modelo del cubo en código de procedimiento. Puede dibujar todo el cubo como un único GeometryModel3D; este ejemplo dibuja la cara del cubo como un modelo distinto para aplicar texturas separadas a cada cara más adelante.  
  
 [!code-csharp[3doverview#3DOverview3DN6](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn6)]
 [!code-vb[3doverview#3DOverview3DN6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn6)]  
  
 [!code-csharp[3doverview#3DOverview3DN7](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn7)]
 [!code-vb[3doverview#3DOverview3DN7](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn7)]  
  
<a name="materials"></a>'
## <a name="applying-materials-to-the-model"></a>Aplicación de materiales al modelo  
  
 Para que una malla parezca un objeto tridimensional, debe tener una textura aplicada que cubra la superficie definida por sus vértices y triángulos, de manera que se pueda iluminar y proyectar por la cámara. En 2D, utilice <xref:System.Windows.Media.Brush> la clase para aplicar colores, patrones, degradados u otro contenido visual a áreas de la pantalla.  La apariencia de los objetos 3D, sin embargo, es una función del modelo de iluminación, no sólo del color o patrón aplicado a ellos. Los objetos reales reflejan la luz de manera distinta según la calidad de su superficie: las superficies satinadas y brillantes no tienen el mismo aspecto que las superficies ásperas o mates, y algunos objetos parecen absorber la luz, mientras que otros la emiten. Puede aplicar todos los mismos pinceles a objetos 3D que puede aplicar a objetos 2D, pero no puede aplicarlos directamente.  
  
 Para definir las características de la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] superficie <xref:System.Windows.Media.Media3D.Material> de un modelo, utilice la clase abstracta. Las subclases concretas de Material determinan algunas de las características del aspecto de la superficie del modelo y, además, cada una de ellas proporciona una propiedad Brush a la que puede pasar SolidColorBrush, TileBrush o VisualBrush.  
  
- <xref:System.Windows.Media.Media3D.DiffuseMaterial>especifica que el pincel se aplicará al modelo como si ese modelo estuviera iluminado difusamente. El uso de DiffuseMaterial se asemeja más al uso de pinceles directamente en modelos 2D; las superficies del modelo no reflejan la luz como si fuera brillante.  
  
- <xref:System.Windows.Media.Media3D.SpecularMaterial>especifica que el pincel se aplicará al modelo como si la superficie del modelo fuera dura o brillante, capaz de reflejar los reflejos. Puede establecer el grado en que la textura sugerirá esta calidad reflectante, o <xref:System.Windows.Media.Media3D.SpecularMaterial.SpecularPower%2A> "brillo", especificando un valor para la propiedad.  
  
- <xref:System.Windows.Media.Media3D.EmissiveMaterial>le permite especificar que la textura se aplicará como si el modelo estuviera emitiendo luz igual al color del pincel. Esto no convierte el modelo en una luz; sin embargo, participará de manera diferente en el sombreado que si se aplica textura con DiffuseMaterial o SpecularMaterial.  
  
 Para un mejor rendimiento, <xref:System.Windows.Media.Media3D.GeometryModel3D> las caras posteriores de un (aquellas caras que están fuera de la vista porque están en el lado opuesto del modelo de la cámara) se eliminan de la escena.  Para especificar <xref:System.Windows.Media.Media3D.Material> una aplicación a la cara posterior de un modelo <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> como un plano, establezca la propiedad del modelo.  
  
 Para lograr algunas cualidades de la superficie, como el brillo o los efectos de reflejo, puede ser conveniente aplicar sucesivamente varios pinceles diferentes a un modelo. Puede aplicar y reutilizar varios <xref:System.Windows.Media.Media3D.MaterialGroup> materiales mediante la clase. Los elementos secundarios de MaterialGroup se aplican del primero al último en varias pasadas de representación.  
  
 En los ejemplos de código siguientes se muestra cómo aplicar un color sólido y un dibujo como pinceles a modelos 3D.  
  
 [!code-xaml[basic3d#Basic3DXAML3DN5](~/samples/snippets/xaml/VS_Snippets_Wpf/Basic3D/XAML/Window1.xaml#basic3dxaml3dn5)]  
  ' [!code-xaml[3doverview#3DOverview3DN9](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/app.xaml#3doverview3dn9)]  
 ' [!code-csharp[3doverview#3DOverview3DN8](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn8)]
  [!code-vb[3doverview#3DOverview3DN8](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn8)]  
  
<a name="lights"></a>
## <a name="illuminating-the-scene"></a>Iluminación de la escena  
 Las luces de los gráficos 3D hacen lo que las luces hacen en el mundo real: hacen que las superficies sean visibles. Más concretamente, las luces determinan qué parte de una escena se incluye en la proyección. Los objetos de luz en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] crean gran variedad de efectos de luz y sombra y siguen el modelo de comportamiento de diversas luces del mundo real. Incluya al menos una luz en la escena o no habrá modelos visibles.  
  
 Las siguientes luces derivan <xref:System.Windows.Media.Media3D.Light>de la clase base:  
  
- <xref:System.Windows.Media.Media3D.AmbientLight>: Proporciona iluminación ambiental que ilumina todos los objetos de forma uniforme independientemente de su ubicación u orientación.  
  
- <xref:System.Windows.Media.Media3D.DirectionalLight>: Se ilumina como una fuente de luz distante.  Las luces <xref:System.Windows.Media.Media3D.DirectionalLight.Direction%2A> direccionales tienen un Vector3D especificado, pero no una ubicación especificada.  
  
- <xref:System.Windows.Media.Media3D.PointLight>: Se ilumina como una fuente de luz cercana. Las luces puntuales tienen posición y emiten la luz desde esa posición. Los objetos de la escena se iluminan dependiendo de su posición y distancia con respecto a la luz. <xref:System.Windows.Media.Media3D.PointLightBase>expone una <xref:System.Windows.Media.Media3D.PointLightBase.Range%2A> propiedad, que determina una distancia más allá de la cual los modelos no serán iluminados por la luz. PointLight también expone propiedades de atenuación, que determinan cómo disminuye la intensidad de la luz a lo largo de la distancia. Puede especificar interpolaciones constantes, lineales o cuadráticas para la atenuación de la luz.  
  
- <xref:System.Windows.Media.Media3D.SpotLight>: Hereda <xref:System.Windows.Media.Media3D.PointLight>de . Los focos de luz iluminan como las luces puntuales, y tienen posición y dirección. Proyectan luz en un área en <xref:System.Windows.Media.Media3D.SpotLight.InnerConeAngle%2A> <xref:System.Windows.Media.Media3D.SpotLight.OuterConeAngle%2A> forma de cono establecida por y propiedades, especificadas en grados.  
  
 Las <xref:System.Windows.Media.Media3D.Model3D> luces son objetos, por lo que puede transformar y animar propiedades de luz, incluida la posición, el color, la dirección y el rango.  
  
 [!code-xaml[hittest3d#HitTest3D3DN6](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTest3D/CSharp/Window1.xaml#hittest3d3dn6)]  
  
 [!code-csharp[basic3d#Basic3D3DN11](~/samples/snippets/csharp/VS_Snippets_Wpf/Basic3D/CSharp/Window1.xaml.cs#basic3d3dn11)]
 [!code-vb[basic3d#Basic3D3DN11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Basic3D/visualbasic/window1.xaml.vb#basic3d3dn11)]  
  
 [!code-csharp[basic3d#Basic3D3DN12](~/samples/snippets/csharp/VS_Snippets_Wpf/Basic3D/CSharp/Window1.xaml.cs#basic3d3dn12)]
 [!code-vb[basic3d#Basic3D3DN12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Basic3D/visualbasic/window1.xaml.vb#basic3d3dn12)]  
  
 [!code-csharp[basic3d#Basic3D3DN13](~/samples/snippets/csharp/VS_Snippets_Wpf/Basic3D/CSharp/Window1.xaml.cs#basic3d3dn13)]
 [!code-vb[basic3d#Basic3D3DN13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Basic3D/visualbasic/window1.xaml.vb#basic3d3dn13)]  
  
<a name="transforms"></a>
## <a name="transforming-models"></a>Transformación de modelos  
 Al crear modelos, estos tienen una ubicación determinada en la escena. Para mover esos modelos por la escena, girarlos o cambiar su tamaño, no es práctico cambiar los vértices que definen los propios modelos.  En su lugar, al igual que en 2D, se aplican transformaciones a los modelos.  
  
 Cada objeto de <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> modelo tiene una propiedad con la que puede mover, reorientar o cambiar el tamaño del modelo.  Al aplicar una transformación, en realidad lo que se hace es desplazar todos los puntos del modelo según un vector o valor especificado por la transformación. Es decir, se transforma el espacio de coordenadas en el que se ha definido el modelo ("espacio del modelo"), pero no se cambian los valores que constituyen la geometría del modelo en el sistema de coordenadas de la escena completa ("espacio universal").  
  
 Para obtener más información sobre la transformación de modelos, consulte [Información general sobre transformaciones 3D](3-d-transformations-overview.md).  
  
<a name="animations"></a>
## <a name="animating-models"></a>Animación de modelos  
 La [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] implementación 3D participa en el mismo sistema de sincronización y animación que los gráficos 2D. En otras palabras, para animar una escena 3D, anime las propiedades de sus modelos. Es posible animar directamente las propiedades de los elementos primitivos, pero suele ser más fácil animar las transformaciones que cambian la posición o el aspecto de los modelos. Dado que las transformaciones se pueden aplicar a <xref:System.Windows.Media.Media3D.Model3DGroup> objetos, así como a modelos individuales, es posible aplicar un conjunto de animaciones a un elemento secundario de un Model3DGroup y otro conjunto de animaciones a un grupo de objetos secundarios. También puede lograr gran variedad de efectos visuales animando las propiedades de iluminación de la escena. Finalmente, si lo desea, puede animar la propia proyección, animando la posición de la cámara o el campo de visión. Para información general sobre el sistema de control de tiempo y animación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], consulte los temas [Información general sobre animaciones](animation-overview.md), [Información general sobre objetos Storyboard](storyboards-overview.md) y [Información general sobre objetos Freezable](../advanced/freezable-objects-overview.md).  
  
 Para animar un objeto en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], se crea una escala de tiempo, se define una animación (que, en realidad, es un cambio de algún valor de propiedad a lo largo del tiempo) y se especifica la propiedad a la que aplicar la animación. Dado que todos los objetos de <xref:System.Windows.Controls.Viewport3D>una escena 3D son elementos secundarios de , las propiedades a las que apunta cualquier animación que desee aplicar a la escena son propiedades de Viewport3D.  
  
 Supongamos que desea hacer que un modelo parezca tambalearse en su lugar. Puede optar por <xref:System.Windows.Media.Media3D.RotateTransform3D> aplicar a al modelo y animar el eje de su rotación de un vector a otro. En el ejemplo de código siguiente se muestra cómo aplicar Vector3DAnimation a la propiedad Axis de la propiedad Rotation3D de la transformación, suponiendo que RotateTransform3D es una de las diversas transformaciones aplicadas al modelo con TransformGroup.  
  
 [!code-csharp[3doverview#3DOverview3DN1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn1)]
 [!code-vb[3doverview#3DOverview3DN1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn1)]  
  
 [!code-csharp[3doverview#3DOverview3DN3](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn3)]
 [!code-vb[3doverview#3DOverview3DN3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn3)]  
  
 [!code-csharp[3doverview#3DOverview3DN4](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn4)]
 [!code-vb[3doverview#3DOverview3DN4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn4)]  
  
 [!code-csharp[3doverview#3DOverview3DN5](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn5)]
 [!code-vb[3doverview#3DOverview3DN5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn5)]  
  
<a name="animations1"></a>
## <a name="add-3d-content-to-the-window"></a>Añadir contenido 3D a la ventana  
 Para renderizar la escena, agregue <xref:System.Windows.Media.Media3D.Model3DGroup>modelos y <xref:System.Windows.Media.Media3D.Model3DGroup> luces <xref:System.Windows.Media.Media3D.ModelVisual3D.Content%2A> a <xref:System.Windows.Media.Media3D.ModelVisual3D>un , a continuación, establezca el como el de un archivo . Agregue <xref:System.Windows.Media.Media3D.ModelVisual3D> el <xref:System.Windows.Controls.Viewport3D.Children%2A> a la <xref:System.Windows.Controls.Viewport3D>colección de la . Agregue cámaras <xref:System.Windows.Controls.Viewport3D> a <xref:System.Windows.Controls.Viewport3D.Camera%2A> la configuración de su propiedad.  
  
 Por último, <xref:System.Windows.Controls.Viewport3D> agregue el a la ventana. Cuando <xref:System.Windows.Controls.Viewport3D> se incluye como el contenido de un elemento de diseño como Canvas, <xref:System.Windows.FrameworkElement.Width%2A> especifique el <xref:System.Windows.FrameworkElement>tamaño de Viewport3D estableciendo sus <xref:System.Windows.FrameworkElement.Height%2A> propiedades y (heredadas de ).  
  
 [!code-xaml[hostingwpfusercontrolinwf#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/HostingWpfUserControlInWf/ConeControl.xaml#1)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Controls.Viewport3D>
- <xref:System.Windows.Media.Media3D.PerspectiveCamera>
- <xref:System.Windows.Media.Media3D.DirectionalLight>
- <xref:System.Windows.Media.Media3D.Material>
- [Descripción general de las transformaciones 3D](3-d-transformations-overview.md)
- [Maximizar el rendimiento de representación 3D en WPF](maximize-wpf-3d-performance.md)
- [Temas "Cómo..."](3-d-graphics-how-to-topics.md)
- [Información general sobre formas y dibujo básico en WPF](shapes-and-basic-drawing-in-wpf-overview.md)
- [Pintar con imágenes, dibujos y elementos visuales](painting-with-images-drawings-and-visuals.md)
