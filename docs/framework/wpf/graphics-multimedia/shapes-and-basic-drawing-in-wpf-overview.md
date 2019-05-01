---
title: Información general sobre formas y dibujo básico en WPF
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- shapes [WPF], about shapes
- basic drawing [WPF]
- vector drawing [WPF], overview
- vectors [WPF], drawing
- Shape objects [WPF]
ms.assetid: 66d7a6d6-e3b6-47bc-8dfe-8a1b26f7d901
ms.openlocfilehash: 1ce0e661d88b7c4d5719c4f11ef0912c5bacb587
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62008363"
---
# <a name="shapes-and-basic-drawing-in-wpf-overview"></a><span data-ttu-id="ec98b-102">Información general sobre formas y dibujo básico en WPF</span><span class="sxs-lookup"><span data-stu-id="ec98b-102">Shapes and Basic Drawing in WPF Overview</span></span>
<span data-ttu-id="ec98b-103">En este tema proporciona información general sobre cómo dibujar con <xref:System.Windows.Shapes.Shape> objetos.</span><span class="sxs-lookup"><span data-stu-id="ec98b-103">This topic gives an overview of how to draw with <xref:System.Windows.Shapes.Shape> objects.</span></span> <span data-ttu-id="ec98b-104">Un <xref:System.Windows.Shapes.Shape> es un tipo de <xref:System.Windows.UIElement> que le permite dibujar una forma a la pantalla.</span><span class="sxs-lookup"><span data-stu-id="ec98b-104">A <xref:System.Windows.Shapes.Shape> is a type of <xref:System.Windows.UIElement> that enables you to draw a shape to the screen.</span></span> <span data-ttu-id="ec98b-105">Dado que son elementos de interfaz de usuario, <xref:System.Windows.Shapes.Shape> objetos pueden usarse dentro de <xref:System.Windows.Controls.Panel> elementos y la mayoría de los controles.</span><span class="sxs-lookup"><span data-stu-id="ec98b-105">Because they are UI elements, <xref:System.Windows.Shapes.Shape> objects can be used inside <xref:System.Windows.Controls.Panel> elements and most controls.</span></span>  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="ec98b-106">ofrece varias capas de acceso a gráficos y servicios de representación.</span><span class="sxs-lookup"><span data-stu-id="ec98b-106">offers several layers of access to graphics and rendering services.</span></span> <span data-ttu-id="ec98b-107">En la capa superior, <xref:System.Windows.Shapes.Shape> objetos son fáciles de usar y proporcionan numerosas características útiles, como el diseño y la participación en el [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] sistema de eventos.</span><span class="sxs-lookup"><span data-stu-id="ec98b-107">At the top layer, <xref:System.Windows.Shapes.Shape> objects are easy to use and provide many useful features, such as layout and participation in the [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] event system.</span></span>  

<a name="shapes"></a>   
## <a name="shape-objects"></a><span data-ttu-id="ec98b-108">Objetos Shape</span><span class="sxs-lookup"><span data-stu-id="ec98b-108">Shape Objects</span></span>  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="ec98b-109">Proporciona una serie de listas para usar <xref:System.Windows.Shapes.Shape> objetos.</span><span class="sxs-lookup"><span data-stu-id="ec98b-109">provides a number of ready-to-use <xref:System.Windows.Shapes.Shape> objects.</span></span>  <span data-ttu-id="ec98b-110">Todos los objetos de forma que se heredan de la <xref:System.Windows.Shapes.Shape> clase.</span><span class="sxs-lookup"><span data-stu-id="ec98b-110">All shape objects inherit from the <xref:System.Windows.Shapes.Shape> class.</span></span> <span data-ttu-id="ec98b-111">Objetos de forma disponibles incluyen <xref:System.Windows.Shapes.Ellipse>, <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon>, <xref:System.Windows.Shapes.Polyline>, y <xref:System.Windows.Shapes.Rectangle>.</span><span class="sxs-lookup"><span data-stu-id="ec98b-111">Available shape objects include <xref:System.Windows.Shapes.Ellipse>, <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon>, <xref:System.Windows.Shapes.Polyline>, and <xref:System.Windows.Shapes.Rectangle>.</span></span> <span data-ttu-id="ec98b-112"><xref:System.Windows.Shapes.Shape> los objetos comparten las siguientes propiedades comunes.</span><span class="sxs-lookup"><span data-stu-id="ec98b-112"><xref:System.Windows.Shapes.Shape> objects share the following common properties.</span></span>  
  
- <span data-ttu-id="ec98b-113"><xref:System.Windows.Shapes.Shape.Stroke%2A>: Describe cómo se pinta el contorno de la forma.</span><span class="sxs-lookup"><span data-stu-id="ec98b-113"><xref:System.Windows.Shapes.Shape.Stroke%2A>: Describes how the shape's outline is painted.</span></span>  
  
- <span data-ttu-id="ec98b-114"><xref:System.Windows.Shapes.Shape.StrokeThickness%2A>: Describe el grosor del contorno de la forma.</span><span class="sxs-lookup"><span data-stu-id="ec98b-114"><xref:System.Windows.Shapes.Shape.StrokeThickness%2A>: Describes the thickness of the shape's outline.</span></span>  
  
- <span data-ttu-id="ec98b-115"><xref:System.Windows.Shapes.Shape.Fill%2A>: Describe cómo se pinta el interior de la forma.</span><span class="sxs-lookup"><span data-stu-id="ec98b-115"><xref:System.Windows.Shapes.Shape.Fill%2A>: Describes how the interior of the shape is painted.</span></span>  
  
- <span data-ttu-id="ec98b-116">Propiedades de datos para especificar coordenadas y vértices, medidos en píxeles independientes del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ec98b-116">Data properties to specify coordinates and vertices, measured in device-independent pixels.</span></span>  
  
 <span data-ttu-id="ec98b-117">Dado que proceden de <xref:System.Windows.UIElement>, objetos de forma que pueden utilizarse dentro de paneles y la mayoría de los controles.</span><span class="sxs-lookup"><span data-stu-id="ec98b-117">Because they derive from <xref:System.Windows.UIElement>, shape objects can be used inside panels and most controls.</span></span> <span data-ttu-id="ec98b-118">El <xref:System.Windows.Controls.Canvas> panel es una opción particularmente apropiada para crear dibujos complejos, ya que admite el posicionamiento absoluto de sus objetos secundarios.</span><span class="sxs-lookup"><span data-stu-id="ec98b-118">The <xref:System.Windows.Controls.Canvas> panel is a particularly good choice for creating complex drawings because it supports absolute positioning of its child objects.</span></span>  
  
 <span data-ttu-id="ec98b-119">La <xref:System.Windows.Shapes.Line> clase le permite dibujar una línea entre dos puntos.</span><span class="sxs-lookup"><span data-stu-id="ec98b-119">The <xref:System.Windows.Shapes.Line> class enables you to draw a line between two points.</span></span> <span data-ttu-id="ec98b-120">En el ejemplo siguiente se muestran varias maneras de especificar coordenadas de línea y propiedades de trazo.</span><span class="sxs-lookup"><span data-stu-id="ec98b-120">The following example shows several ways to specify line coordinates and stroke properties.</span></span>  
  
 [!code-xaml[drawingwithshapeelements#LineExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 [!code-cpp[shapesprocedural#ShapesProceduralLine](~/samples/snippets/cpp/VS_Snippets_Wpf/ShapesProcedural/CPP/ShapesProcedural.cpp#shapesproceduralline)]
 [!code-csharp[shapesprocedural#ShapesProceduralLine](~/samples/snippets/csharp/VS_Snippets_Wpf/ShapesProcedural/Csharp/ShapesProcedural.cs#shapesproceduralline)]
 [!code-vb[shapesprocedural#ShapesProceduralLine](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ShapesProcedural/VisualBasic/ShapesProceduralVB.vb#shapesproceduralline)]  
  
 <span data-ttu-id="ec98b-121">La siguiente imagen muestra el texto representado <xref:System.Windows.Shapes.Line>.</span><span class="sxs-lookup"><span data-stu-id="ec98b-121">The following image shows the rendered <xref:System.Windows.Shapes.Line>.</span></span>  
  
 <span data-ttu-id="ec98b-122">![Ilustración de línea](./media/shape-ovw-line2.gif "shape_ovw_line2")</span><span class="sxs-lookup"><span data-stu-id="ec98b-122">![Line illustration](./media/shape-ovw-line2.gif "shape_ovw_line2")</span></span>  
  
 <span data-ttu-id="ec98b-123">Aunque el <xref:System.Windows.Shapes.Line> clase proporcionar un <xref:System.Windows.Shapes.Shape.Fill%2A> la propiedad, no tiene ningún efecto porque un <xref:System.Windows.Shapes.Line> no tiene ninguna área.</span><span class="sxs-lookup"><span data-stu-id="ec98b-123">Although the <xref:System.Windows.Shapes.Line> class does provide a <xref:System.Windows.Shapes.Shape.Fill%2A> property, setting it has no effect because a <xref:System.Windows.Shapes.Line> has no area.</span></span>  
  
 <span data-ttu-id="ec98b-124">Otra forma común es la <xref:System.Windows.Shapes.Ellipse>.</span><span class="sxs-lookup"><span data-stu-id="ec98b-124">Another common shape is the <xref:System.Windows.Shapes.Ellipse>.</span></span>  <span data-ttu-id="ec98b-125">Crear un <xref:System.Windows.Shapes.Ellipse> mediante la definición de la forma <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> propiedades.</span><span class="sxs-lookup"><span data-stu-id="ec98b-125">Create an <xref:System.Windows.Shapes.Ellipse> by defining the shape's <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties.</span></span> <span data-ttu-id="ec98b-126">Para dibujar un círculo, especifique un <xref:System.Windows.Shapes.Ellipse> cuyo <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> valores son iguales.</span><span class="sxs-lookup"><span data-stu-id="ec98b-126">To draw a circle, specify an <xref:System.Windows.Shapes.Ellipse> whose <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> values are equal.</span></span>  
  
 [!code-xaml[ShapeOverviews#ShapesOVW1](~/samples/snippets/csharp/VS_Snippets_Wpf/ShapeOverviews/CS/Window1.xaml#shapesovw1)]  
  
 [!code-csharp[brushesmiscsnippets_procedural_snip#SetBackgroundColorOfShapeCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesMiscSnippets_procedural_snip/CSharp/SetBackgroundColorOfShapeExample.cs#setbackgroundcolorofshapecodeexamplewholepage)]
 [!code-vb[brushesmiscsnippets_procedural_snip#SetBackgroundColorOfShapeCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesMiscSnippets_procedural_snip/visualbasic/setbackgroundcolorofshapeexample.vb#setbackgroundcolorofshapecodeexamplewholepage)]  
  
 <span data-ttu-id="ec98b-127">La siguiente imagen muestra un ejemplo de un representado <xref:System.Windows.Shapes.Ellipse>.</span><span class="sxs-lookup"><span data-stu-id="ec98b-127">The following image shows an example of a rendered <xref:System.Windows.Shapes.Ellipse>.</span></span>  
  
 <span data-ttu-id="ec98b-128">![Ilustración de elipse](./media/shape-ovw-ellipse2.png "shape_ovw_ellipse2")</span><span class="sxs-lookup"><span data-stu-id="ec98b-128">![Ellipse illustration](./media/shape-ovw-ellipse2.png "shape_ovw_ellipse2")</span></span>  
  
<a name="paths"></a>   
## <a name="using-paths-and-geometries"></a><span data-ttu-id="ec98b-129">Utilizar trazados y geometrías</span><span class="sxs-lookup"><span data-stu-id="ec98b-129">Using Paths and Geometries</span></span>  
 <span data-ttu-id="ec98b-130">La <xref:System.Windows.Shapes.Path> clase le permite dibujar curvas y formas complejas.</span><span class="sxs-lookup"><span data-stu-id="ec98b-130">The <xref:System.Windows.Shapes.Path> class enables you to draw curves and complex shapes.</span></span> <span data-ttu-id="ec98b-131">Estas curvas y formas se describen mediante <xref:System.Windows.Media.Geometry> objetos.</span><span class="sxs-lookup"><span data-stu-id="ec98b-131">These curves and shapes are described using <xref:System.Windows.Media.Geometry> objects.</span></span> <span data-ttu-id="ec98b-132">Para usar un <xref:System.Windows.Shapes.Path>, se crea un <xref:System.Windows.Media.Geometry> y usarlo para establecer el <xref:System.Windows.Shapes.Path> del objeto <xref:System.Windows.Shapes.Path.Data%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="ec98b-132">To use a <xref:System.Windows.Shapes.Path>, you create a <xref:System.Windows.Media.Geometry> and use it to set the <xref:System.Windows.Shapes.Path> object's <xref:System.Windows.Shapes.Path.Data%2A> property.</span></span>  
  
 <span data-ttu-id="ec98b-133">Hay una gran variedad de <xref:System.Windows.Media.Geometry> objetos que puede elegir.</span><span class="sxs-lookup"><span data-stu-id="ec98b-133">There are a variety of <xref:System.Windows.Media.Geometry> objects to choose from.</span></span> <span data-ttu-id="ec98b-134">El <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.RectangleGeometry>, y <xref:System.Windows.Media.EllipseGeometry> las clases describen formas relativamente simples.</span><span class="sxs-lookup"><span data-stu-id="ec98b-134">The <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.RectangleGeometry>, and <xref:System.Windows.Media.EllipseGeometry> classes describe relatively simple shapes.</span></span> <span data-ttu-id="ec98b-135">Para crear formas más complejas o crear curvas, utilice un <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="ec98b-135">To create more complex shapes or create curves, use a <xref:System.Windows.Media.PathGeometry>.</span></span>  
  
<a name="pathgeometry"></a>   
### <a name="pathgeometry-and-pathsegments"></a><span data-ttu-id="ec98b-136">PathGeometry y PathSegments</span><span class="sxs-lookup"><span data-stu-id="ec98b-136">PathGeometry and PathSegments</span></span>  
 <span data-ttu-id="ec98b-137"><xref:System.Windows.Media.PathGeometry> los objetos se componen de uno o varios <xref:System.Windows.Media.PathFigure> objetos; cada <xref:System.Windows.Media.PathFigure> representa una "figura" diferentes o forma.</span><span class="sxs-lookup"><span data-stu-id="ec98b-137"><xref:System.Windows.Media.PathGeometry> objects are comprised of one or more <xref:System.Windows.Media.PathFigure> objects; each <xref:System.Windows.Media.PathFigure> represents a different "figure" or shape.</span></span> <span data-ttu-id="ec98b-138">Cada <xref:System.Windows.Media.PathFigure> propio consta de uno o varios <xref:System.Windows.Media.PathSegment> objetos que representan una parte conectada de la figura o forma.</span><span class="sxs-lookup"><span data-stu-id="ec98b-138">Each <xref:System.Windows.Media.PathFigure> is itself comprised of one or more <xref:System.Windows.Media.PathSegment> objects, each representing a connected portion of the figure or shape.</span></span> <span data-ttu-id="ec98b-139">Tipos de segmentos incluyen lo siguiente: <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.BezierSegment>, y <xref:System.Windows.Media.ArcSegment>.</span><span class="sxs-lookup"><span data-stu-id="ec98b-139">Segment types include the following: <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.BezierSegment>, and <xref:System.Windows.Media.ArcSegment>.</span></span>  
  
 <span data-ttu-id="ec98b-140">En el ejemplo siguiente, un <xref:System.Windows.Shapes.Path> se usa para dibujar una curva Bézier cuadrática.</span><span class="sxs-lookup"><span data-stu-id="ec98b-140">In the following example, a <xref:System.Windows.Shapes.Path> is used to draw a quadratic Bezier curve.</span></span>  
  
 [!code-xaml[geometrysample#34](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#34)]  
  
 <span data-ttu-id="ec98b-141">La siguiente imagen muestra la forma representada.</span><span class="sxs-lookup"><span data-stu-id="ec98b-141">The following image shows the rendered shape.</span></span>  
  
 <span data-ttu-id="ec98b-142">![Ilustración de trayecto](./media/shape-ovw-path2.gif "shape_ovw_path2")</span><span class="sxs-lookup"><span data-stu-id="ec98b-142">![Path illustration](./media/shape-ovw-path2.gif "shape_ovw_path2")</span></span>  
  
 <span data-ttu-id="ec98b-143">Para obtener más información acerca de <xref:System.Windows.Media.PathGeometry> y el otro <xref:System.Windows.Media.Geometry> las clases, consulte el [información general sobre geometría](geometry-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ec98b-143">For more information about <xref:System.Windows.Media.PathGeometry> and the other <xref:System.Windows.Media.Geometry> classes, see the [Geometry Overview](geometry-overview.md).</span></span>  
  
<a name="pathdatastring"></a>   
### <a name="xaml-abbreviated-syntax"></a><span data-ttu-id="ec98b-144">Sintaxis abreviada de XAML</span><span class="sxs-lookup"><span data-stu-id="ec98b-144">XAML Abbreviated Syntax</span></span>  
 <span data-ttu-id="ec98b-145">En [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], también puede usar una sintaxis abreviada especial para describir un <xref:System.Windows.Shapes.Path>.</span><span class="sxs-lookup"><span data-stu-id="ec98b-145">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], you may also use a special abbreviated syntax to describe a <xref:System.Windows.Shapes.Path>.</span></span> <span data-ttu-id="ec98b-146">En el ejemplo siguiente, se utiliza la sintaxis abreviada para dibujar una forma compleja.</span><span class="sxs-lookup"><span data-stu-id="ec98b-146">In the following example, abbreviated syntax is used to draw a complex shape.</span></span>  
  
```xaml  
      <Path Stroke="DarkGoldenRod" StrokeThickness="3"   
Data="M 100,200 C 100,25 400,350 400,175 H 280" />  
```  
  
 <span data-ttu-id="ec98b-147">La siguiente imagen muestra un representado <xref:System.Windows.Shapes.Path>.</span><span class="sxs-lookup"><span data-stu-id="ec98b-147">The following image shows a rendered <xref:System.Windows.Shapes.Path>.</span></span>  
  
 <span data-ttu-id="ec98b-148">![Ilustración de trayecto](./media/shape-ovw-path.PNG "shape_ovw_path")</span><span class="sxs-lookup"><span data-stu-id="ec98b-148">![Path illustration](./media/shape-ovw-path.PNG "shape_ovw_path")</span></span>  
  
 <span data-ttu-id="ec98b-149">El <xref:System.Windows.Shapes.Path.Data%2A> comienza la cadena de atributo con el comando "moveto", indicado por M, que establece un punto de inicio para la ruta de acceso en el sistema de coordenadas de la <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="ec98b-149">The <xref:System.Windows.Shapes.Path.Data%2A> attribute string begins with the "moveto" command, indicated by M, which establishes a start point for the path in the coordinate system of the <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="ec98b-150"><xref:System.Windows.Shapes.Path> parámetros de datos distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="ec98b-150"><xref:System.Windows.Shapes.Path> data parameters are case-sensitive.</span></span> <span data-ttu-id="ec98b-151">La letra M mayúscula indica una ubicación absoluta para el nuevo punto activo.</span><span class="sxs-lookup"><span data-stu-id="ec98b-151">The capital M indicates an absolute location for the new current point.</span></span> <span data-ttu-id="ec98b-152">Una m minúscula indica coordenadas relativas.</span><span class="sxs-lookup"><span data-stu-id="ec98b-152">A lowercase m would indicate relative coordinates.</span></span> <span data-ttu-id="ec98b-153">El primer segmento es una curva de Bézier cúbica que comienza en (100,200) y termina en (400,175), trazado con los dos puntos de control (100,25) y (400,350).</span><span class="sxs-lookup"><span data-stu-id="ec98b-153">The first segment is a cubic Bezier curve beginning at (100,200) and ending at (400,175), drawn using the two control points (100,25) and (400,350).</span></span> <span data-ttu-id="ec98b-154">Este segmento se indica mediante el comando C en el <xref:System.Windows.Shapes.Path.Data%2A> cadena de atributo.</span><span class="sxs-lookup"><span data-stu-id="ec98b-154">This segment is indicated by the C command in the <xref:System.Windows.Shapes.Path.Data%2A> attribute string.</span></span> <span data-ttu-id="ec98b-155">De nuevo, la C mayúscula indica una ruta de acceso absoluta; la c minúscula indicaría una ruta de acceso relativa.</span><span class="sxs-lookup"><span data-stu-id="ec98b-155">Again, the capital C indicates an absolute path; the lowercase c would indicate a relative path.</span></span>  
  
 <span data-ttu-id="ec98b-156">El segundo segmento comienza con un comando H "lineto" horizontal absoluto, que especifica una línea trazada desde el punto de conexión del subtrazado anterior (400,175) hasta un nuevo punto de conexión (280,175).</span><span class="sxs-lookup"><span data-stu-id="ec98b-156">The second segment begins with an absolute horizontal "lineto" command H, which specifies a line drawn from the preceding subpath's endpoint (400,175) to a new endpoint (280,175).</span></span> <span data-ttu-id="ec98b-157">Dado que es un comando "lineto" horizontal, el valor especificado es un *x*-coordinar.</span><span class="sxs-lookup"><span data-stu-id="ec98b-157">Because it is a horizontal "lineto" command, the value specified is an *x*-coordinate.</span></span>  
  
 <span data-ttu-id="ec98b-158">Para obtener la sintaxis de ruta de acceso completa, consulte el <xref:System.Windows.Shapes.Path.Data%2A> referencia y [crear una forma mediante una clase PathGeometry](how-to-create-a-shape-by-using-a-pathgeometry.md).</span><span class="sxs-lookup"><span data-stu-id="ec98b-158">For the complete path syntax, see the <xref:System.Windows.Shapes.Path.Data%2A> reference and [Create a Shape by Using a PathGeometry](how-to-create-a-shape-by-using-a-pathgeometry.md).</span></span>  
  
<a name="fillpaint"></a>   
## <a name="painting-shapes"></a><span data-ttu-id="ec98b-159">Pintar formas</span><span class="sxs-lookup"><span data-stu-id="ec98b-159">Painting Shapes</span></span>  
 <span data-ttu-id="ec98b-160"><xref:System.Windows.Media.Brush> los objetos se utilizan para dibujar una forma <xref:System.Windows.Shapes.Shape.Stroke%2A> y <xref:System.Windows.Shapes.Shape.Fill%2A>.</span><span class="sxs-lookup"><span data-stu-id="ec98b-160"><xref:System.Windows.Media.Brush> objects are used to paint a shape's <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.Fill%2A>.</span></span> <span data-ttu-id="ec98b-161">En el ejemplo siguiente, el trazo y relleno de un <xref:System.Windows.Shapes.Ellipse> se especifican.</span><span class="sxs-lookup"><span data-stu-id="ec98b-161">In the following example, the stroke and fill of an <xref:System.Windows.Shapes.Ellipse> are specified.</span></span> <span data-ttu-id="ec98b-162">Tenga en cuenta que una entrada válida para las propiedades del pincel puede ser una palabra clave o el valor de color en formato hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="ec98b-162">Note that valid input for brush properties can be either a keyword or hexadecimal color value.</span></span> <span data-ttu-id="ec98b-163">Para obtener más información sobre las palabras clave de colores disponibles, vea las propiedades de la <xref:System.Windows.Media.Colors> clase en el <xref:System.Windows.Media> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="ec98b-163">For more information about available color keywords, see properties of the <xref:System.Windows.Media.Colors> class in the <xref:System.Windows.Media> namespace.</span></span>  
  
```xaml
<Canvas Background="LightGray">   
   <Ellipse  
      Canvas.Top="50"  
      Canvas.Left="50"  
      Fill="#FFFFFF00"  
      Height="75"  
      Width="75"  
      StrokeThickness="5"  
      Stroke="#FF0000FF"/>  
</Canvas>  
```  
  
 <span data-ttu-id="ec98b-164">La siguiente imagen muestra el texto representado <xref:System.Windows.Shapes.Ellipse>.</span><span class="sxs-lookup"><span data-stu-id="ec98b-164">The following image shows the rendered <xref:System.Windows.Shapes.Ellipse>.</span></span>  
  
 <span data-ttu-id="ec98b-165">![Una elipse](./media/shape-ovw-ellipsefill.PNG "shape_ovw_ellipsefill")</span><span class="sxs-lookup"><span data-stu-id="ec98b-165">![An ellipse](./media/shape-ovw-ellipsefill.PNG "shape_ovw_ellipsefill")</span></span>  
  
 <span data-ttu-id="ec98b-166">Como alternativa, puede usar la sintaxis de elemento de propiedad para crear explícitamente un <xref:System.Windows.Media.SolidColorBrush> objeto que se va a pintar la forma con un color sólido.</span><span class="sxs-lookup"><span data-stu-id="ec98b-166">Alternatively, you can use property element syntax to explicitly create a <xref:System.Windows.Media.SolidColorBrush> object to paint the shape with a solid color.</span></span>  
  
```xaml
<!-- This polygon shape uses pre-defined color values for its Stroke and  
     Fill properties.   
     The SolidColorBrush's Opacity property affects the fill color in   
     this case by making it slightly transparent (opacity of 0.4) so   
     that it blends with any underlying color. -->  
  
<Polygon  
    Points="300,200 400,125 400,275 300,200"  
    Stroke="Purple"   
    StrokeThickness="2">  
    <Polygon.Fill>  
       <SolidColorBrush Color="Blue" Opacity="0.4"/>  
    </Polygon.Fill>  
</Polygon>  
```  
  
 <span data-ttu-id="ec98b-167">En la ilustración siguiente se muestra la forma representada.</span><span class="sxs-lookup"><span data-stu-id="ec98b-167">The following illustration shows the rendered shape.</span></span>  
  
 <span data-ttu-id="ec98b-168">![Ilustración de SolidColorBrush](./media/shape-ovw-solidcolorbrush.PNG "shape_ovw_solidcolorbrush")</span><span class="sxs-lookup"><span data-stu-id="ec98b-168">![SolidColorBrush illustration](./media/shape-ovw-solidcolorbrush.PNG "shape_ovw_solidcolorbrush")</span></span>  
  
 <span data-ttu-id="ec98b-169">También puede pintar el trazo o relleno de una forma con degradados, imágenes, patrones y mucho más.</span><span class="sxs-lookup"><span data-stu-id="ec98b-169">You can also paint a shape's stroke or fill with gradients, images, patterns, and more.</span></span> <span data-ttu-id="ec98b-170">Para obtener más información, consulte el [el dibujo con colores sólidos y degradados](painting-with-solid-colors-and-gradients-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ec98b-170">For more information, see the [Painting with Solid Colors and Gradients Overview](painting-with-solid-colors-and-gradients-overview.md).</span></span>  
  
<a name="stretchableshapessection"></a>   
## <a name="stretchable-shapes"></a><span data-ttu-id="ec98b-171">Formas extensibles</span><span class="sxs-lookup"><span data-stu-id="ec98b-171">Stretchable Shapes</span></span>  
 <span data-ttu-id="ec98b-172">El <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon>, <xref:System.Windows.Shapes.Polyline>, y <xref:System.Windows.Shapes.Rectangle> clases tienen una <xref:System.Windows.Shapes.Shape.Stretch%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="ec98b-172">The <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon>, <xref:System.Windows.Shapes.Polyline>, and <xref:System.Windows.Shapes.Rectangle> classes all have a <xref:System.Windows.Shapes.Shape.Stretch%2A> property.</span></span> <span data-ttu-id="ec98b-173">Esta propiedad determina cómo un <xref:System.Windows.Shapes.Shape> contenido del objeto (es decir, la forma que va a dibujar) se ajusta para rellenar el <xref:System.Windows.Shapes.Shape> espacio de diseño del objeto.</span><span class="sxs-lookup"><span data-stu-id="ec98b-173">This property determines how a <xref:System.Windows.Shapes.Shape> object's contents (the shape to be drawn) is stretched to fill the <xref:System.Windows.Shapes.Shape> object's layout space.</span></span> <span data-ttu-id="ec98b-174">Un <xref:System.Windows.Shapes.Shape> espacio de diseño del objeto es la cantidad de espacio en el <xref:System.Windows.Shapes.Shape> está asignada por el sistema de diseño, debido a uno explícita <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> configuración o debido su <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> y <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> configuración.</span><span class="sxs-lookup"><span data-stu-id="ec98b-174">A <xref:System.Windows.Shapes.Shape> object's layout space is the amount of space the <xref:System.Windows.Shapes.Shape> is allocated by the layout system, because of either an explicit <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> setting or because of its <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> and <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> settings.</span></span> <span data-ttu-id="ec98b-175">Para obtener más información sobre el diseño en Windows Presentation Foundation, vea [diseño](../advanced/layout.md) información general.</span><span class="sxs-lookup"><span data-stu-id="ec98b-175">For additional information on layout in Windows Presentation Foundation, see [Layout](../advanced/layout.md) overview.</span></span>  
  
 <span data-ttu-id="ec98b-176">La propiedad Stretch puede tener uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="ec98b-176">The Stretch property takes one of the following values:</span></span>  
  
- <span data-ttu-id="ec98b-177"><xref:System.Windows.Media.Stretch.None>: El <xref:System.Windows.Shapes.Shape> no se ajusta el contenido del objeto.</span><span class="sxs-lookup"><span data-stu-id="ec98b-177"><xref:System.Windows.Media.Stretch.None>: The <xref:System.Windows.Shapes.Shape> object's contents are not stretched.</span></span>  
  
- <span data-ttu-id="ec98b-178"><xref:System.Windows.Media.Stretch.Fill>: El <xref:System.Windows.Shapes.Shape> contenido del objeto se ajusta para rellenar el espacio de diseño.</span><span class="sxs-lookup"><span data-stu-id="ec98b-178"><xref:System.Windows.Media.Stretch.Fill>: The <xref:System.Windows.Shapes.Shape> object's contents are stretched to fill its layout space.</span></span>  <span data-ttu-id="ec98b-179">No se mantiene la relación de aspecto.</span><span class="sxs-lookup"><span data-stu-id="ec98b-179">Aspect ratio is not preserved.</span></span>  
  
- <span data-ttu-id="ec98b-180"><xref:System.Windows.Media.Stretch.Uniform>: El <xref:System.Windows.Shapes.Shape> contenido del objeto se ajusta tanto como sea posible para rellenar el espacio de diseño mientras conserva su relación de aspecto original.</span><span class="sxs-lookup"><span data-stu-id="ec98b-180"><xref:System.Windows.Media.Stretch.Uniform>: The <xref:System.Windows.Shapes.Shape> object's contents are stretched as much as possible to fill its layout space while preserving its original aspect ratio.</span></span>  
  
- <span data-ttu-id="ec98b-181"><xref:System.Windows.Media.Stretch.UniformToFill>: El <xref:System.Windows.Shapes.Shape> contenido del objeto se ajusta para rellenar completamente el espacio de diseño mientras conserva su relación de aspecto original.</span><span class="sxs-lookup"><span data-stu-id="ec98b-181"><xref:System.Windows.Media.Stretch.UniformToFill>: The <xref:System.Windows.Shapes.Shape> object's contents are stretched to completely fill its layout space while preserving its original aspect ratio.</span></span>  
  
 <span data-ttu-id="ec98b-182">Tenga en cuenta que, cuando un <xref:System.Windows.Shapes.Shape> se ajusta el contenido del objeto, el <xref:System.Windows.Shapes.Shape> se pinta el contorno del objeto después del ajuste.</span><span class="sxs-lookup"><span data-stu-id="ec98b-182">Note that, when a <xref:System.Windows.Shapes.Shape> object's contents are stretched, the <xref:System.Windows.Shapes.Shape> object's outline is painted after the stretching.</span></span>  
  
 <span data-ttu-id="ec98b-183">En el ejemplo siguiente, un <xref:System.Windows.Shapes.Polygon> se usa para dibujar un triángulo muy pequeño de (0,0) a (0,1) a (1,1).</span><span class="sxs-lookup"><span data-stu-id="ec98b-183">In the following example, a <xref:System.Windows.Shapes.Polygon> is used to draw a very small triangle from (0,0) to (0,1) to (1,1).</span></span> <span data-ttu-id="ec98b-184">El <xref:System.Windows.Shapes.Polygon> del objeto <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> se establecen en 100, y su propiedad stretch se establece en Fill.</span><span class="sxs-lookup"><span data-stu-id="ec98b-184">The <xref:System.Windows.Shapes.Polygon> object's <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> are set to 100, and its stretch property is set to Fill.</span></span> <span data-ttu-id="ec98b-185">Como resultado, el <xref:System.Windows.Shapes.Polygon> el contenido del objeto (el triángulo) se ajusta para rellenar el espacio mayor.</span><span class="sxs-lookup"><span data-stu-id="ec98b-185">As a result, the <xref:System.Windows.Shapes.Polygon> object's contents (the triangle) are stretched to fill the larger space.</span></span>  
  
```xaml
<Polygon  
  Points="0,0 0,1 1,1"  
  Fill="Blue"  
  Width="100"  
  Height="100"  
  Stretch="Fill"  
  Stroke="Black"  
  StrokeThickness="2" />  
```

```csharp
PointCollection myPointCollection = new PointCollection();  
myPointCollection.Add(new Point(0,0));  
myPointCollection.Add(new Point(0,1));  
myPointCollection.Add(new Point(1,1));  
  
Polygon myPolygon = new Polygon();  
myPolygon.Points = myPointCollection;  
myPolygon.Fill = Brushes.Blue;  
myPolygon.Width = 100;  
myPolygon.Height = 100;  
myPolygon.Stretch = Stretch.Fill;  
myPolygon.Stroke = Brushes.Black;  
myPolygon.StrokeThickness = 2;  
```

<a name="transforms"></a>   
## <a name="transforming-shapes"></a><span data-ttu-id="ec98b-186">Transformar formas</span><span class="sxs-lookup"><span data-stu-id="ec98b-186">Transforming Shapes</span></span>  
 <span data-ttu-id="ec98b-187">La <xref:System.Windows.Media.Transform> clase proporciona los medios para transformar las formas en un plano bidimensional.</span><span class="sxs-lookup"><span data-stu-id="ec98b-187">The <xref:System.Windows.Media.Transform> class provides the means to transform shapes in a two-dimensional plane.</span></span>  <span data-ttu-id="ec98b-188">Los distintos tipos de transformación incluyen la rotación (<xref:System.Windows.Media.RotateTransform>), escala (<xref:System.Windows.Media.ScaleTransform>), el sesgado (<xref:System.Windows.Media.SkewTransform>) y traducción (<xref:System.Windows.Media.TranslateTransform>).</span><span class="sxs-lookup"><span data-stu-id="ec98b-188">The different types of transformation include rotation (<xref:System.Windows.Media.RotateTransform>), scale (<xref:System.Windows.Media.ScaleTransform>), skew (<xref:System.Windows.Media.SkewTransform>), and translation (<xref:System.Windows.Media.TranslateTransform>).</span></span>  
  
 <span data-ttu-id="ec98b-189">Una transformación común para aplicar a una forma es la rotación.</span><span class="sxs-lookup"><span data-stu-id="ec98b-189">A common transform to apply to a shape is a rotation.</span></span>  <span data-ttu-id="ec98b-190">Para girar una forma, crear un <xref:System.Windows.Media.RotateTransform> y especifique su <xref:System.Windows.Media.RotateTransform.Angle%2A>.</span><span class="sxs-lookup"><span data-stu-id="ec98b-190">To rotate a shape, create a <xref:System.Windows.Media.RotateTransform> and specify its <xref:System.Windows.Media.RotateTransform.Angle%2A>.</span></span> <span data-ttu-id="ec98b-191">Un <xref:System.Windows.Media.RotateTransform.Angle%2A> de 45 gira el elemento 45 grados a la derecha; un ángulo de 90 gira el elemento 90 grados a la derecha; y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="ec98b-191">An <xref:System.Windows.Media.RotateTransform.Angle%2A> of 45 rotates the element 45 degrees clockwise; an angle of 90 rotates the element 90 degrees clockwise; and so on.</span></span> <span data-ttu-id="ec98b-192">Establecer el <xref:System.Windows.Media.RotateTransform.CenterX%2A> y <xref:System.Windows.Media.RotateTransform.CenterY%2A> propiedades si desea controlar el punto sobre el que se gira el elemento.</span><span class="sxs-lookup"><span data-stu-id="ec98b-192">Set the <xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> properties if you want to control the point about which the element is rotated.</span></span> <span data-ttu-id="ec98b-193">Estos valores de propiedad se expresan en el espacio de coordenadas del elemento que se va a transformar.</span><span class="sxs-lookup"><span data-stu-id="ec98b-193">These property values are expressed in the coordinate space of the element being transformed.</span></span> <span data-ttu-id="ec98b-194"><xref:System.Windows.Media.RotateTransform.CenterX%2A> y <xref:System.Windows.Media.RotateTransform.CenterY%2A> tienen valores predeterminados de cero.</span><span class="sxs-lookup"><span data-stu-id="ec98b-194"><xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> have default values of zero.</span></span> <span data-ttu-id="ec98b-195">Por último, aplique el <xref:System.Windows.Media.RotateTransform> al elemento.</span><span class="sxs-lookup"><span data-stu-id="ec98b-195">Finally, apply the <xref:System.Windows.Media.RotateTransform> to the element.</span></span> <span data-ttu-id="ec98b-196">Si no desea que la transformación afecte al diseño, establezca la forma <xref:System.Windows.UIElement.RenderTransform%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="ec98b-196">If you don't want the transform to affect layout, set the shape's <xref:System.Windows.UIElement.RenderTransform%2A> property.</span></span>  
  
 <span data-ttu-id="ec98b-197">En el ejemplo siguiente, un <xref:System.Windows.Media.RotateTransform> se utiliza para girar una forma 45 grados sobre parte superior izquierda la forma en la (0,0).</span><span class="sxs-lookup"><span data-stu-id="ec98b-197">In the following example, a <xref:System.Windows.Media.RotateTransform> is used to rotate a shape 45 degrees about the shape's top left corner (0,0).</span></span>  
  
 [!code-xaml[transformssample#14](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/RotateTransformExample.xaml#14)]  
  
 <span data-ttu-id="ec98b-198">En el ejemplo siguiente, otra forma se gira 45 grados, pero esta vez se gira alrededor del punto (25,50).</span><span class="sxs-lookup"><span data-stu-id="ec98b-198">In the next example, another shape is rotated 45 degrees, but this time it's rotated about the point (25,50).</span></span>  
  
 [!code-xaml[transformssample#15](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/RotateTransformExample.xaml#15)]  
  
 <span data-ttu-id="ec98b-199">En la ilustración siguiente se muestran los resultados de aplicar las dos transformaciones.</span><span class="sxs-lookup"><span data-stu-id="ec98b-199">The following illustration shows the results of applying the two transforms.</span></span>  
  
 <span data-ttu-id="ec98b-200">![Rotaciones de 45 grados con diferentes puntos centrales](./media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")</span><span class="sxs-lookup"><span data-stu-id="ec98b-200">![45 degree rotations with different center points](./media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")</span></span>  
  
 <span data-ttu-id="ec98b-201">En los ejemplos anteriores, se aplicó una única transformación a cada objeto de forma.</span><span class="sxs-lookup"><span data-stu-id="ec98b-201">In the previous examples, a single transform was applied to each shape object.</span></span> <span data-ttu-id="ec98b-202">Para aplicar varias transformaciones a una forma (o cualquier otro elemento de interfaz de usuario), use un <xref:System.Windows.Media.TransformGroup>.</span><span class="sxs-lookup"><span data-stu-id="ec98b-202">To apply multiple transforms to a shape (or any other UI element), use a <xref:System.Windows.Media.TransformGroup>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec98b-203">Vea también</span><span class="sxs-lookup"><span data-stu-id="ec98b-203">See also</span></span>

- [<span data-ttu-id="ec98b-204">Imágenes y gráficos 2D</span><span class="sxs-lookup"><span data-stu-id="ec98b-204">2D Graphics and Imaging</span></span>](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [<span data-ttu-id="ec98b-205">Información general sobre el dibujo con colores sólidos y degradados</span><span class="sxs-lookup"><span data-stu-id="ec98b-205">Painting with Solid Colors and Gradients Overview</span></span>](painting-with-solid-colors-and-gradients-overview.md)
- [<span data-ttu-id="ec98b-206">Información general sobre geometría</span><span class="sxs-lookup"><span data-stu-id="ec98b-206">Geometry Overview</span></span>](geometry-overview.md)
- [<span data-ttu-id="ec98b-207">Tutorial: Mi primera aplicación de escritorio WPF</span><span class="sxs-lookup"><span data-stu-id="ec98b-207">Walkthrough: My first WPF desktop application</span></span>](../getting-started/walkthrough-my-first-wpf-desktop-application.md)
- [<span data-ttu-id="ec98b-208">Información general sobre animaciones</span><span class="sxs-lookup"><span data-stu-id="ec98b-208">Animation Overview</span></span>](animation-overview.md)
