---
title: Información general sobre formas y dibujo básico
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
ms.openlocfilehash: dfdbf67d35cbb13e80d0c5184f165b0cc660e2ef
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731623"
---
# <a name="shapes-and-basic-drawing-in-wpf-overview"></a><span data-ttu-id="579bc-102">Información general sobre formas y dibujo básico en WPF</span><span class="sxs-lookup"><span data-stu-id="579bc-102">Shapes and Basic Drawing in WPF Overview</span></span>
<span data-ttu-id="579bc-103">En este tema se proporciona información general sobre cómo dibujar con objetos <xref:System.Windows.Shapes.Shape>.</span><span class="sxs-lookup"><span data-stu-id="579bc-103">This topic gives an overview of how to draw with <xref:System.Windows.Shapes.Shape> objects.</span></span> <span data-ttu-id="579bc-104">Un <xref:System.Windows.Shapes.Shape> es un tipo de <xref:System.Windows.UIElement> que permite dibujar una forma en la pantalla.</span><span class="sxs-lookup"><span data-stu-id="579bc-104">A <xref:System.Windows.Shapes.Shape> is a type of <xref:System.Windows.UIElement> that enables you to draw a shape to the screen.</span></span> <span data-ttu-id="579bc-105">Dado que son elementos de interfaz de usuario, se pueden usar <xref:System.Windows.Shapes.Shape> objetos dentro de <xref:System.Windows.Controls.Panel> elementos y la mayoría de los controles.</span><span class="sxs-lookup"><span data-stu-id="579bc-105">Because they are UI elements, <xref:System.Windows.Shapes.Shape> objects can be used inside <xref:System.Windows.Controls.Panel> elements and most controls.</span></span>  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="579bc-106">ofrece varias capas de acceso a gráficos y servicios de representación.</span><span class="sxs-lookup"><span data-stu-id="579bc-106">offers several layers of access to graphics and rendering services.</span></span> <span data-ttu-id="579bc-107">En la capa superior, los objetos <xref:System.Windows.Shapes.Shape> son fáciles de usar y proporcionan muchas características útiles, como el diseño y la participación en el sistema de eventos [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="579bc-107">At the top layer, <xref:System.Windows.Shapes.Shape> objects are easy to use and provide many useful features, such as layout and participation in the [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] event system.</span></span>  

<a name="shapes"></a>   
## <a name="shape-objects"></a><span data-ttu-id="579bc-108">Objetos Shape</span><span class="sxs-lookup"><span data-stu-id="579bc-108">Shape Objects</span></span>  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="579bc-109">proporciona varios objetos <xref:System.Windows.Shapes.Shape> listos para usar.</span><span class="sxs-lookup"><span data-stu-id="579bc-109">provides a number of ready-to-use <xref:System.Windows.Shapes.Shape> objects.</span></span>  <span data-ttu-id="579bc-110">Todos los objetos de forma se heredan de la clase <xref:System.Windows.Shapes.Shape>.</span><span class="sxs-lookup"><span data-stu-id="579bc-110">All shape objects inherit from the <xref:System.Windows.Shapes.Shape> class.</span></span> <span data-ttu-id="579bc-111">Los objetos de forma disponibles incluyen <xref:System.Windows.Shapes.Ellipse>, <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon>, <xref:System.Windows.Shapes.Polyline>y <xref:System.Windows.Shapes.Rectangle>.</span><span class="sxs-lookup"><span data-stu-id="579bc-111">Available shape objects include <xref:System.Windows.Shapes.Ellipse>, <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon>, <xref:System.Windows.Shapes.Polyline>, and <xref:System.Windows.Shapes.Rectangle>.</span></span> <span data-ttu-id="579bc-112"><xref:System.Windows.Shapes.Shape> objetos comparten las siguientes propiedades comunes.</span><span class="sxs-lookup"><span data-stu-id="579bc-112"><xref:System.Windows.Shapes.Shape> objects share the following common properties.</span></span>  
  
- <span data-ttu-id="579bc-113"><xref:System.Windows.Shapes.Shape.Stroke%2A>: describe cómo se pinta el contorno de la forma.</span><span class="sxs-lookup"><span data-stu-id="579bc-113"><xref:System.Windows.Shapes.Shape.Stroke%2A>: Describes how the shape's outline is painted.</span></span>  
  
- <span data-ttu-id="579bc-114"><xref:System.Windows.Shapes.Shape.StrokeThickness%2A>: describe el grosor del contorno de la forma.</span><span class="sxs-lookup"><span data-stu-id="579bc-114"><xref:System.Windows.Shapes.Shape.StrokeThickness%2A>: Describes the thickness of the shape's outline.</span></span>  
  
- <span data-ttu-id="579bc-115"><xref:System.Windows.Shapes.Shape.Fill%2A>: describe cómo se pinta el interior de la forma.</span><span class="sxs-lookup"><span data-stu-id="579bc-115"><xref:System.Windows.Shapes.Shape.Fill%2A>: Describes how the interior of the shape is painted.</span></span>  
  
- <span data-ttu-id="579bc-116">Propiedades de datos para especificar coordenadas y vértices, medidos en píxeles independientes del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="579bc-116">Data properties to specify coordinates and vertices, measured in device-independent pixels.</span></span>  
  
 <span data-ttu-id="579bc-117">Dado que se derivan de <xref:System.Windows.UIElement>, los objetos de forma se pueden usar dentro de los paneles y la mayoría de los controles.</span><span class="sxs-lookup"><span data-stu-id="579bc-117">Because they derive from <xref:System.Windows.UIElement>, shape objects can be used inside panels and most controls.</span></span> <span data-ttu-id="579bc-118">El panel de <xref:System.Windows.Controls.Canvas> es una opción especialmente adecuada para crear dibujos complejos porque admite el posicionamiento absoluto de sus objetos secundarios.</span><span class="sxs-lookup"><span data-stu-id="579bc-118">The <xref:System.Windows.Controls.Canvas> panel is a particularly good choice for creating complex drawings because it supports absolute positioning of its child objects.</span></span>  
  
 <span data-ttu-id="579bc-119">La clase <xref:System.Windows.Shapes.Line> permite dibujar una línea entre dos puntos.</span><span class="sxs-lookup"><span data-stu-id="579bc-119">The <xref:System.Windows.Shapes.Line> class enables you to draw a line between two points.</span></span> <span data-ttu-id="579bc-120">En el ejemplo siguiente se muestran varias maneras de especificar coordenadas de línea y propiedades de trazo.</span><span class="sxs-lookup"><span data-stu-id="579bc-120">The following example shows several ways to specify line coordinates and stroke properties.</span></span>  
  
 [!code-xaml[drawingwithshapeelements#LineExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 [!code-cpp[shapesprocedural#ShapesProceduralLine](~/samples/snippets/cpp/VS_Snippets_Wpf/ShapesProcedural/CPP/ShapesProcedural.cpp#shapesproceduralline)]
 [!code-csharp[shapesprocedural#ShapesProceduralLine](~/samples/snippets/csharp/VS_Snippets_Wpf/ShapesProcedural/Csharp/ShapesProcedural.cs#shapesproceduralline)]
 [!code-vb[shapesprocedural#ShapesProceduralLine](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ShapesProcedural/VisualBasic/ShapesProceduralVB.vb#shapesproceduralline)]  
  
 <span data-ttu-id="579bc-121">En la imagen siguiente se muestra el <xref:System.Windows.Shapes.Line>representado.</span><span class="sxs-lookup"><span data-stu-id="579bc-121">The following image shows the rendered <xref:System.Windows.Shapes.Line>.</span></span>  
  
 <span data-ttu-id="579bc-122">![Ilustración de línea](./media/shape-ovw-line2.gif "shape_ovw_line2")</span><span class="sxs-lookup"><span data-stu-id="579bc-122">![Line illustration](./media/shape-ovw-line2.gif "shape_ovw_line2")</span></span>  
  
 <span data-ttu-id="579bc-123">Aunque la clase <xref:System.Windows.Shapes.Line> proporciona una propiedad <xref:System.Windows.Shapes.Shape.Fill%2A>, establecerla no tiene ningún efecto porque un <xref:System.Windows.Shapes.Line> no tiene área.</span><span class="sxs-lookup"><span data-stu-id="579bc-123">Although the <xref:System.Windows.Shapes.Line> class does provide a <xref:System.Windows.Shapes.Shape.Fill%2A> property, setting it has no effect because a <xref:System.Windows.Shapes.Line> has no area.</span></span>  
  
 <span data-ttu-id="579bc-124">Otra forma común es la <xref:System.Windows.Shapes.Ellipse>.</span><span class="sxs-lookup"><span data-stu-id="579bc-124">Another common shape is the <xref:System.Windows.Shapes.Ellipse>.</span></span>  <span data-ttu-id="579bc-125">Cree una <xref:System.Windows.Shapes.Ellipse> definiendo las propiedades <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> de la forma.</span><span class="sxs-lookup"><span data-stu-id="579bc-125">Create an <xref:System.Windows.Shapes.Ellipse> by defining the shape's <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties.</span></span> <span data-ttu-id="579bc-126">Para dibujar un círculo, especifique una <xref:System.Windows.Shapes.Ellipse> cuyos valores de <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> sean iguales.</span><span class="sxs-lookup"><span data-stu-id="579bc-126">To draw a circle, specify an <xref:System.Windows.Shapes.Ellipse> whose <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> values are equal.</span></span>  
  
 [!code-xaml[ShapeOverviews#ShapesOVW1](~/samples/snippets/csharp/VS_Snippets_Wpf/ShapeOverviews/CS/Window1.xaml#shapesovw1)]  
  
 [!code-csharp[brushesmiscsnippets_procedural_snip#SetBackgroundColorOfShapeCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesMiscSnippets_procedural_snip/CSharp/SetBackgroundColorOfShapeExample.cs#setbackgroundcolorofshapecodeexamplewholepage)]
 [!code-vb[brushesmiscsnippets_procedural_snip#SetBackgroundColorOfShapeCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesMiscSnippets_procedural_snip/visualbasic/setbackgroundcolorofshapeexample.vb#setbackgroundcolorofshapecodeexamplewholepage)]  
  
 <span data-ttu-id="579bc-127">En la imagen siguiente se muestra un ejemplo de una <xref:System.Windows.Shapes.Ellipse>representada.</span><span class="sxs-lookup"><span data-stu-id="579bc-127">The following image shows an example of a rendered <xref:System.Windows.Shapes.Ellipse>.</span></span>  
  
 <span data-ttu-id="579bc-128">![Ilustración de elipse](./media/shape-ovw-ellipse2.png "shape_ovw_ellipse2")</span><span class="sxs-lookup"><span data-stu-id="579bc-128">![Ellipse illustration](./media/shape-ovw-ellipse2.png "shape_ovw_ellipse2")</span></span>  
  
<a name="paths"></a>   
## <a name="using-paths-and-geometries"></a><span data-ttu-id="579bc-129">Utilizar trazados y geometrías</span><span class="sxs-lookup"><span data-stu-id="579bc-129">Using Paths and Geometries</span></span>  
 <span data-ttu-id="579bc-130">La clase <xref:System.Windows.Shapes.Path> permite dibujar curvas y formas complejas.</span><span class="sxs-lookup"><span data-stu-id="579bc-130">The <xref:System.Windows.Shapes.Path> class enables you to draw curves and complex shapes.</span></span> <span data-ttu-id="579bc-131">Estas curvas y formas se describen mediante objetos <xref:System.Windows.Media.Geometry>.</span><span class="sxs-lookup"><span data-stu-id="579bc-131">These curves and shapes are described using <xref:System.Windows.Media.Geometry> objects.</span></span> <span data-ttu-id="579bc-132">Para usar un <xref:System.Windows.Shapes.Path>, cree un <xref:System.Windows.Media.Geometry> y úselo para establecer la propiedad <xref:System.Windows.Shapes.Path.Data%2A> del objeto <xref:System.Windows.Shapes.Path>.</span><span class="sxs-lookup"><span data-stu-id="579bc-132">To use a <xref:System.Windows.Shapes.Path>, you create a <xref:System.Windows.Media.Geometry> and use it to set the <xref:System.Windows.Shapes.Path> object's <xref:System.Windows.Shapes.Path.Data%2A> property.</span></span>  
  
 <span data-ttu-id="579bc-133">Hay una variedad de objetos de <xref:System.Windows.Media.Geometry> entre los que elegir.</span><span class="sxs-lookup"><span data-stu-id="579bc-133">There are a variety of <xref:System.Windows.Media.Geometry> objects to choose from.</span></span> <span data-ttu-id="579bc-134">Las clases <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.RectangleGeometry>y <xref:System.Windows.Media.EllipseGeometry> describen formas relativamente simples.</span><span class="sxs-lookup"><span data-stu-id="579bc-134">The <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.RectangleGeometry>, and <xref:System.Windows.Media.EllipseGeometry> classes describe relatively simple shapes.</span></span> <span data-ttu-id="579bc-135">Para crear formas más complejas o crear curvas, use una <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="579bc-135">To create more complex shapes or create curves, use a <xref:System.Windows.Media.PathGeometry>.</span></span>  
  
<a name="pathgeometry"></a>   
### <a name="pathgeometry-and-pathsegments"></a><span data-ttu-id="579bc-136">PathGeometry y PathSegments</span><span class="sxs-lookup"><span data-stu-id="579bc-136">PathGeometry and PathSegments</span></span>  
 <span data-ttu-id="579bc-137"><xref:System.Windows.Media.PathGeometry> objetos se componen de uno o varios objetos <xref:System.Windows.Media.PathFigure>; cada <xref:System.Windows.Media.PathFigure> representa una "figura" o forma diferente.</span><span class="sxs-lookup"><span data-stu-id="579bc-137"><xref:System.Windows.Media.PathGeometry> objects are comprised of one or more <xref:System.Windows.Media.PathFigure> objects; each <xref:System.Windows.Media.PathFigure> represents a different "figure" or shape.</span></span> <span data-ttu-id="579bc-138">Cada <xref:System.Windows.Media.PathFigure> se compone de uno o varios objetos <xref:System.Windows.Media.PathSegment>, cada uno de los cuales representa una parte conectada de la figura o forma.</span><span class="sxs-lookup"><span data-stu-id="579bc-138">Each <xref:System.Windows.Media.PathFigure> is itself comprised of one or more <xref:System.Windows.Media.PathSegment> objects, each representing a connected portion of the figure or shape.</span></span> <span data-ttu-id="579bc-139">Entre los tipos de segmentos se incluyen los siguientes: <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.BezierSegment>y <xref:System.Windows.Media.ArcSegment>.</span><span class="sxs-lookup"><span data-stu-id="579bc-139">Segment types include the following: <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.BezierSegment>, and <xref:System.Windows.Media.ArcSegment>.</span></span>  
  
 <span data-ttu-id="579bc-140">En el ejemplo siguiente, se usa un <xref:System.Windows.Shapes.Path> para dibujar una curva Bézier cuadrática.</span><span class="sxs-lookup"><span data-stu-id="579bc-140">In the following example, a <xref:System.Windows.Shapes.Path> is used to draw a quadratic Bezier curve.</span></span>  
  
 [!code-xaml[geometrysample#34](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#34)]  
  
 <span data-ttu-id="579bc-141">La siguiente imagen muestra la forma representada.</span><span class="sxs-lookup"><span data-stu-id="579bc-141">The following image shows the rendered shape.</span></span>  
  
 <span data-ttu-id="579bc-142">![Ilustración de trazado](./media/shape-ovw-path2.gif "shape_ovw_path2")</span><span class="sxs-lookup"><span data-stu-id="579bc-142">![Path illustration](./media/shape-ovw-path2.gif "shape_ovw_path2")</span></span>  
  
 <span data-ttu-id="579bc-143">Para obtener más información sobre <xref:System.Windows.Media.PathGeometry> y las demás clases de <xref:System.Windows.Media.Geometry>, consulte la [información general sobre geometría](geometry-overview.md).</span><span class="sxs-lookup"><span data-stu-id="579bc-143">For more information about <xref:System.Windows.Media.PathGeometry> and the other <xref:System.Windows.Media.Geometry> classes, see the [Geometry Overview](geometry-overview.md).</span></span>  
  
<a name="pathdatastring"></a>   
### <a name="xaml-abbreviated-syntax"></a><span data-ttu-id="579bc-144">Sintaxis abreviada de XAML</span><span class="sxs-lookup"><span data-stu-id="579bc-144">XAML Abbreviated Syntax</span></span>  
 <span data-ttu-id="579bc-145">En [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], también puede usar una sintaxis abreviada especial para describir un <xref:System.Windows.Shapes.Path>.</span><span class="sxs-lookup"><span data-stu-id="579bc-145">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], you may also use a special abbreviated syntax to describe a <xref:System.Windows.Shapes.Path>.</span></span> <span data-ttu-id="579bc-146">En el ejemplo siguiente, se utiliza la sintaxis abreviada para dibujar una forma compleja.</span><span class="sxs-lookup"><span data-stu-id="579bc-146">In the following example, abbreviated syntax is used to draw a complex shape.</span></span>  
  
```xaml  
      <Path Stroke="DarkGoldenRod" StrokeThickness="3"   
Data="M 100,200 C 100,25 400,350 400,175 H 280" />  
```  
  
 <span data-ttu-id="579bc-147">En la imagen siguiente se muestra una <xref:System.Windows.Shapes.Path>representada.</span><span class="sxs-lookup"><span data-stu-id="579bc-147">The following image shows a rendered <xref:System.Windows.Shapes.Path>.</span></span>  
  
 <span data-ttu-id="579bc-148">![Ilustración de trazado](./media/shape-ovw-path.PNG "shape_ovw_path")</span><span class="sxs-lookup"><span data-stu-id="579bc-148">![Path illustration](./media/shape-ovw-path.PNG "shape_ovw_path")</span></span>  
  
 <span data-ttu-id="579bc-149">La cadena de atributo de <xref:System.Windows.Shapes.Path.Data%2A> comienza con el comando "moveTo", indicado por M, que establece un punto de inicio para la ruta de acceso en el sistema de coordenadas del <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="579bc-149">The <xref:System.Windows.Shapes.Path.Data%2A> attribute string begins with the "moveto" command, indicated by M, which establishes a start point for the path in the coordinate system of the <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="579bc-150"><xref:System.Windows.Shapes.Path> parámetros de datos distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="579bc-150"><xref:System.Windows.Shapes.Path> data parameters are case-sensitive.</span></span> <span data-ttu-id="579bc-151">La letra M mayúscula indica una ubicación absoluta para el nuevo punto actual.</span><span class="sxs-lookup"><span data-stu-id="579bc-151">The capital M indicates an absolute location for the new current point.</span></span> <span data-ttu-id="579bc-152">Una m minúscula indica coordenadas relativas.</span><span class="sxs-lookup"><span data-stu-id="579bc-152">A lowercase m would indicate relative coordinates.</span></span> <span data-ttu-id="579bc-153">El primer segmento es una curva de Bézier cúbica que comienza en (100,200) y termina en (400,175), trazado con los dos puntos de control (100,25) y (400,350).</span><span class="sxs-lookup"><span data-stu-id="579bc-153">The first segment is a cubic Bezier curve beginning at (100,200) and ending at (400,175), drawn using the two control points (100,25) and (400,350).</span></span> <span data-ttu-id="579bc-154">Este segmento se indica mediante el comando C en la cadena de atributo <xref:System.Windows.Shapes.Path.Data%2A>.</span><span class="sxs-lookup"><span data-stu-id="579bc-154">This segment is indicated by the C command in the <xref:System.Windows.Shapes.Path.Data%2A> attribute string.</span></span> <span data-ttu-id="579bc-155">De nuevo, la C mayúscula indica una ruta de acceso absoluta; la c minúscula indicaría una ruta de acceso relativa.</span><span class="sxs-lookup"><span data-stu-id="579bc-155">Again, the capital C indicates an absolute path; the lowercase c would indicate a relative path.</span></span>  
  
 <span data-ttu-id="579bc-156">El segundo segmento comienza con un comando H "lineto" horizontal absoluto, que especifica una línea trazada desde el punto de conexión del subtrazado anterior (400,175) hasta un nuevo punto de conexión (280,175).</span><span class="sxs-lookup"><span data-stu-id="579bc-156">The second segment begins with an absolute horizontal "lineto" command H, which specifies a line drawn from the preceding subpath's endpoint (400,175) to a new endpoint (280,175).</span></span> <span data-ttu-id="579bc-157">Dado que es un comando "lineTo" horizontal, el valor especificado es una coordenada *x*.</span><span class="sxs-lookup"><span data-stu-id="579bc-157">Because it is a horizontal "lineto" command, the value specified is an *x*-coordinate.</span></span>  
  
 <span data-ttu-id="579bc-158">Para obtener la sintaxis de ruta de acceso completa, vea la referencia de <xref:System.Windows.Shapes.Path.Data%2A> y [crear una forma mediante PathGeometry](how-to-create-a-shape-by-using-a-pathgeometry.md).</span><span class="sxs-lookup"><span data-stu-id="579bc-158">For the complete path syntax, see the <xref:System.Windows.Shapes.Path.Data%2A> reference and [Create a Shape by Using a PathGeometry](how-to-create-a-shape-by-using-a-pathgeometry.md).</span></span>  
  
<a name="fillpaint"></a>   
## <a name="painting-shapes"></a><span data-ttu-id="579bc-159">Pintar formas</span><span class="sxs-lookup"><span data-stu-id="579bc-159">Painting Shapes</span></span>  
 <span data-ttu-id="579bc-160"><xref:System.Windows.Media.Brush> objetos se utilizan para pintar el <xref:System.Windows.Shapes.Shape.Stroke%2A> y el <xref:System.Windows.Shapes.Shape.Fill%2A>de una forma.</span><span class="sxs-lookup"><span data-stu-id="579bc-160"><xref:System.Windows.Media.Brush> objects are used to paint a shape's <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.Fill%2A>.</span></span> <span data-ttu-id="579bc-161">En el ejemplo siguiente, se especifican el trazo y el relleno de un <xref:System.Windows.Shapes.Ellipse>.</span><span class="sxs-lookup"><span data-stu-id="579bc-161">In the following example, the stroke and fill of an <xref:System.Windows.Shapes.Ellipse> are specified.</span></span> <span data-ttu-id="579bc-162">Tenga en cuenta que una entrada válida para las propiedades del pincel puede ser una palabra clave o el valor de color en formato hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="579bc-162">Note that valid input for brush properties can be either a keyword or hexadecimal color value.</span></span> <span data-ttu-id="579bc-163">Para obtener más información sobre las palabras clave de color disponibles, consulte propiedades de la clase <xref:System.Windows.Media.Colors> en el espacio de nombres <xref:System.Windows.Media>.</span><span class="sxs-lookup"><span data-stu-id="579bc-163">For more information about available color keywords, see properties of the <xref:System.Windows.Media.Colors> class in the <xref:System.Windows.Media> namespace.</span></span>  
  
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
  
 <span data-ttu-id="579bc-164">En la imagen siguiente se muestra el <xref:System.Windows.Shapes.Ellipse>representado.</span><span class="sxs-lookup"><span data-stu-id="579bc-164">The following image shows the rendered <xref:System.Windows.Shapes.Ellipse>.</span></span>  
  
 <span data-ttu-id="579bc-165">![Una elipse](./media/shape-ovw-ellipsefill.PNG "shape_ovw_ellipsefill")</span><span class="sxs-lookup"><span data-stu-id="579bc-165">![An ellipse](./media/shape-ovw-ellipsefill.PNG "shape_ovw_ellipsefill")</span></span>  
  
 <span data-ttu-id="579bc-166">Como alternativa, puede usar la sintaxis de elementos de propiedad para crear explícitamente un objeto <xref:System.Windows.Media.SolidColorBrush> para pintar la forma con un color sólido.</span><span class="sxs-lookup"><span data-stu-id="579bc-166">Alternatively, you can use property element syntax to explicitly create a <xref:System.Windows.Media.SolidColorBrush> object to paint the shape with a solid color.</span></span>  
  
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
  
 <span data-ttu-id="579bc-167">En la ilustración siguiente se muestra la forma representada.</span><span class="sxs-lookup"><span data-stu-id="579bc-167">The following illustration shows the rendered shape.</span></span>  
  
 <span data-ttu-id="579bc-168">![Ilustración de SolidColorBrush](./media/shape-ovw-solidcolorbrush.PNG "shape_ovw_solidcolorbrush")</span><span class="sxs-lookup"><span data-stu-id="579bc-168">![SolidColorBrush illustration](./media/shape-ovw-solidcolorbrush.PNG "shape_ovw_solidcolorbrush")</span></span>  
  
 <span data-ttu-id="579bc-169">También puede pintar el trazo o relleno de una forma con degradados, imágenes, patrones y mucho más.</span><span class="sxs-lookup"><span data-stu-id="579bc-169">You can also paint a shape's stroke or fill with gradients, images, patterns, and more.</span></span> <span data-ttu-id="579bc-170">Para obtener más información, consulte la información [General sobre el dibujo con colores sólidos y degradados](painting-with-solid-colors-and-gradients-overview.md).</span><span class="sxs-lookup"><span data-stu-id="579bc-170">For more information, see the [Painting with Solid Colors and Gradients Overview](painting-with-solid-colors-and-gradients-overview.md).</span></span>  
  
<a name="stretchableshapessection"></a>   
## <a name="stretchable-shapes"></a><span data-ttu-id="579bc-171">Formas extensibles</span><span class="sxs-lookup"><span data-stu-id="579bc-171">Stretchable Shapes</span></span>  
 <span data-ttu-id="579bc-172">Todas las clases <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon>, <xref:System.Windows.Shapes.Polyline>y <xref:System.Windows.Shapes.Rectangle> tienen una propiedad <xref:System.Windows.Shapes.Shape.Stretch%2A>.</span><span class="sxs-lookup"><span data-stu-id="579bc-172">The <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon>, <xref:System.Windows.Shapes.Polyline>, and <xref:System.Windows.Shapes.Rectangle> classes all have a <xref:System.Windows.Shapes.Shape.Stretch%2A> property.</span></span> <span data-ttu-id="579bc-173">Esta propiedad determina cómo se ajusta el contenido de un objeto <xref:System.Windows.Shapes.Shape> (la forma que se va a dibujar) para rellenar el espacio de diseño del objeto <xref:System.Windows.Shapes.Shape>.</span><span class="sxs-lookup"><span data-stu-id="579bc-173">This property determines how a <xref:System.Windows.Shapes.Shape> object's contents (the shape to be drawn) is stretched to fill the <xref:System.Windows.Shapes.Shape> object's layout space.</span></span> <span data-ttu-id="579bc-174">El espacio de diseño de un objeto <xref:System.Windows.Shapes.Shape> es la cantidad de espacio que el sistema de diseño asigna al <xref:System.Windows.Shapes.Shape>, debido a un valor de <xref:System.Windows.FrameworkElement.Width%2A> explícito y <xref:System.Windows.FrameworkElement.Height%2A>, o debido a su configuración <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> y <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>.</span><span class="sxs-lookup"><span data-stu-id="579bc-174">A <xref:System.Windows.Shapes.Shape> object's layout space is the amount of space the <xref:System.Windows.Shapes.Shape> is allocated by the layout system, because of either an explicit <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> setting or because of its <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> and <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> settings.</span></span> <span data-ttu-id="579bc-175">Para obtener información adicional sobre el diseño en Windows Presentation Foundation, consulte información general de [diseño](../advanced/layout.md) .</span><span class="sxs-lookup"><span data-stu-id="579bc-175">For additional information on layout in Windows Presentation Foundation, see [Layout](../advanced/layout.md) overview.</span></span>  
  
 <span data-ttu-id="579bc-176">La propiedad Stretch puede tener uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="579bc-176">The Stretch property takes one of the following values:</span></span>  
  
- <span data-ttu-id="579bc-177"><xref:System.Windows.Media.Stretch.None>: el contenido del objeto de <xref:System.Windows.Shapes.Shape> no se ajusta.</span><span class="sxs-lookup"><span data-stu-id="579bc-177"><xref:System.Windows.Media.Stretch.None>: The <xref:System.Windows.Shapes.Shape> object's contents are not stretched.</span></span>  
  
- <span data-ttu-id="579bc-178"><xref:System.Windows.Media.Stretch.Fill>: el contenido del objeto de <xref:System.Windows.Shapes.Shape> se ajusta para rellenar el espacio de diseño.</span><span class="sxs-lookup"><span data-stu-id="579bc-178"><xref:System.Windows.Media.Stretch.Fill>: The <xref:System.Windows.Shapes.Shape> object's contents are stretched to fill its layout space.</span></span>  <span data-ttu-id="579bc-179">No se mantiene la relación de aspecto.</span><span class="sxs-lookup"><span data-stu-id="579bc-179">Aspect ratio is not preserved.</span></span>  
  
- <span data-ttu-id="579bc-180"><xref:System.Windows.Media.Stretch.Uniform>: el contenido del objeto de <xref:System.Windows.Shapes.Shape> se ajusta tanto como sea posible para rellenar el espacio de diseño a la vez que conserva su relación de aspecto original.</span><span class="sxs-lookup"><span data-stu-id="579bc-180"><xref:System.Windows.Media.Stretch.Uniform>: The <xref:System.Windows.Shapes.Shape> object's contents are stretched as much as possible to fill its layout space while preserving its original aspect ratio.</span></span>  
  
- <span data-ttu-id="579bc-181"><xref:System.Windows.Media.Stretch.UniformToFill>: el contenido del objeto de la <xref:System.Windows.Shapes.Shape> se ajusta para rellenar completamente su espacio de diseño conservando la relación de aspecto original.</span><span class="sxs-lookup"><span data-stu-id="579bc-181"><xref:System.Windows.Media.Stretch.UniformToFill>: The <xref:System.Windows.Shapes.Shape> object's contents are stretched to completely fill its layout space while preserving its original aspect ratio.</span></span>  
  
 <span data-ttu-id="579bc-182">Tenga en cuenta que, cuando se ajusta el contenido de un objeto <xref:System.Windows.Shapes.Shape>, el contorno del objeto <xref:System.Windows.Shapes.Shape> se pinta después de la ampliación.</span><span class="sxs-lookup"><span data-stu-id="579bc-182">Note that, when a <xref:System.Windows.Shapes.Shape> object's contents are stretched, the <xref:System.Windows.Shapes.Shape> object's outline is painted after the stretching.</span></span>  
  
 <span data-ttu-id="579bc-183">En el ejemplo siguiente, se usa un <xref:System.Windows.Shapes.Polygon> para dibujar un triángulo muy pequeño de (0,0) a (0,1) a (1,1).</span><span class="sxs-lookup"><span data-stu-id="579bc-183">In the following example, a <xref:System.Windows.Shapes.Polygon> is used to draw a very small triangle from (0,0) to (0,1) to (1,1).</span></span> <span data-ttu-id="579bc-184">Los <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> del objeto de <xref:System.Windows.Shapes.Polygon> se establecen en 100 y su propiedad Stretch está establecida en Fill.</span><span class="sxs-lookup"><span data-stu-id="579bc-184">The <xref:System.Windows.Shapes.Polygon> object's <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> are set to 100, and its stretch property is set to Fill.</span></span> <span data-ttu-id="579bc-185">Como resultado, el contenido del objeto <xref:System.Windows.Shapes.Polygon> (el triángulo) se ajusta para rellenar el espacio mayor.</span><span class="sxs-lookup"><span data-stu-id="579bc-185">As a result, the <xref:System.Windows.Shapes.Polygon> object's contents (the triangle) are stretched to fill the larger space.</span></span>  
  
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
## <a name="transforming-shapes"></a><span data-ttu-id="579bc-186">Transformar formas</span><span class="sxs-lookup"><span data-stu-id="579bc-186">Transforming Shapes</span></span>  
 <span data-ttu-id="579bc-187">La clase <xref:System.Windows.Media.Transform> proporciona los medios para transformar las formas en un plano bidimensional.</span><span class="sxs-lookup"><span data-stu-id="579bc-187">The <xref:System.Windows.Media.Transform> class provides the means to transform shapes in a two-dimensional plane.</span></span>  <span data-ttu-id="579bc-188">Los distintos tipos de transformaciones incluyen la rotación (<xref:System.Windows.Media.RotateTransform>), la escala (<xref:System.Windows.Media.ScaleTransform>), el sesgo (<xref:System.Windows.Media.SkewTransform>) y la traslación (<xref:System.Windows.Media.TranslateTransform>).</span><span class="sxs-lookup"><span data-stu-id="579bc-188">The different types of transformation include rotation (<xref:System.Windows.Media.RotateTransform>), scale (<xref:System.Windows.Media.ScaleTransform>), skew (<xref:System.Windows.Media.SkewTransform>), and translation (<xref:System.Windows.Media.TranslateTransform>).</span></span>  
  
 <span data-ttu-id="579bc-189">Una transformación común para aplicar a una forma es la rotación.</span><span class="sxs-lookup"><span data-stu-id="579bc-189">A common transform to apply to a shape is a rotation.</span></span>  <span data-ttu-id="579bc-190">Para girar una forma, cree un <xref:System.Windows.Media.RotateTransform> y especifique su <xref:System.Windows.Media.RotateTransform.Angle%2A>.</span><span class="sxs-lookup"><span data-stu-id="579bc-190">To rotate a shape, create a <xref:System.Windows.Media.RotateTransform> and specify its <xref:System.Windows.Media.RotateTransform.Angle%2A>.</span></span> <span data-ttu-id="579bc-191">Un <xref:System.Windows.Media.RotateTransform.Angle%2A> de 45 gira el elemento 45 grados en el sentido de las agujas del reloj; un ángulo de 90 gira el elemento 90 grados en el sentido de las agujas del reloj; etc.</span><span class="sxs-lookup"><span data-stu-id="579bc-191">An <xref:System.Windows.Media.RotateTransform.Angle%2A> of 45 rotates the element 45 degrees clockwise; an angle of 90 rotates the element 90 degrees clockwise; and so on.</span></span> <span data-ttu-id="579bc-192">Establezca las propiedades <xref:System.Windows.Media.RotateTransform.CenterX%2A> y <xref:System.Windows.Media.RotateTransform.CenterY%2A> si desea controlar el punto sobre el que se gira el elemento.</span><span class="sxs-lookup"><span data-stu-id="579bc-192">Set the <xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> properties if you want to control the point about which the element is rotated.</span></span> <span data-ttu-id="579bc-193">Estos valores de propiedad se expresan en el espacio de coordenadas del elemento que se va a transformar.</span><span class="sxs-lookup"><span data-stu-id="579bc-193">These property values are expressed in the coordinate space of the element being transformed.</span></span> <span data-ttu-id="579bc-194"><xref:System.Windows.Media.RotateTransform.CenterX%2A> y <xref:System.Windows.Media.RotateTransform.CenterY%2A> tienen valores predeterminados de cero.</span><span class="sxs-lookup"><span data-stu-id="579bc-194"><xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> have default values of zero.</span></span> <span data-ttu-id="579bc-195">Por último, aplique el <xref:System.Windows.Media.RotateTransform> al elemento.</span><span class="sxs-lookup"><span data-stu-id="579bc-195">Finally, apply the <xref:System.Windows.Media.RotateTransform> to the element.</span></span> <span data-ttu-id="579bc-196">Si no desea que la transformación afecte al diseño, establezca la propiedad <xref:System.Windows.UIElement.RenderTransform%2A> de la forma.</span><span class="sxs-lookup"><span data-stu-id="579bc-196">If you don't want the transform to affect layout, set the shape's <xref:System.Windows.UIElement.RenderTransform%2A> property.</span></span>  
  
 <span data-ttu-id="579bc-197">En el ejemplo siguiente, se usa un <xref:System.Windows.Media.RotateTransform> para girar una forma 45 grados sobre la esquina superior izquierda de la forma (0,0).</span><span class="sxs-lookup"><span data-stu-id="579bc-197">In the following example, a <xref:System.Windows.Media.RotateTransform> is used to rotate a shape 45 degrees about the shape's top left corner (0,0).</span></span>  
  
 [!code-xaml[transformssample#14](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/RotateTransformExample.xaml#14)]  
  
 <span data-ttu-id="579bc-198">En el ejemplo siguiente, otra forma se gira 45 grados, pero esta vez se gira alrededor del punto (25,50).</span><span class="sxs-lookup"><span data-stu-id="579bc-198">In the next example, another shape is rotated 45 degrees, but this time it's rotated about the point (25,50).</span></span>  
  
 [!code-xaml[transformssample#15](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/RotateTransformExample.xaml#15)]  
  
 <span data-ttu-id="579bc-199">En la ilustración siguiente se muestran los resultados de aplicar las dos transformaciones.</span><span class="sxs-lookup"><span data-stu-id="579bc-199">The following illustration shows the results of applying the two transforms.</span></span>  
  
 <span data-ttu-id="579bc-200">![Rotaciones de 45 grados con diferentes centros](./media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")</span><span class="sxs-lookup"><span data-stu-id="579bc-200">![45 degree rotations with different center points](./media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")</span></span>  
  
 <span data-ttu-id="579bc-201">En los ejemplos anteriores, se aplicó una única transformación a cada objeto de forma.</span><span class="sxs-lookup"><span data-stu-id="579bc-201">In the previous examples, a single transform was applied to each shape object.</span></span> <span data-ttu-id="579bc-202">Para aplicar varias transformaciones a una forma (o cualquier otro elemento de la interfaz de usuario), use una <xref:System.Windows.Media.TransformGroup>.</span><span class="sxs-lookup"><span data-stu-id="579bc-202">To apply multiple transforms to a shape (or any other UI element), use a <xref:System.Windows.Media.TransformGroup>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="579bc-203">Consulte también</span><span class="sxs-lookup"><span data-stu-id="579bc-203">See also</span></span>

- [<span data-ttu-id="579bc-204">Imágenes y gráficos 2D</span><span class="sxs-lookup"><span data-stu-id="579bc-204">2D Graphics and Imaging</span></span>](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [<span data-ttu-id="579bc-205">Información general sobre el dibujo con colores sólidos y degradados</span><span class="sxs-lookup"><span data-stu-id="579bc-205">Painting with Solid Colors and Gradients Overview</span></span>](painting-with-solid-colors-and-gradients-overview.md)
- [<span data-ttu-id="579bc-206">Información general sobre geometría</span><span class="sxs-lookup"><span data-stu-id="579bc-206">Geometry Overview</span></span>](geometry-overview.md)
- [<span data-ttu-id="579bc-207">Tutorial: Mi primera aplicación de escritorio WPF</span><span class="sxs-lookup"><span data-stu-id="579bc-207">Walkthrough: My first WPF desktop application</span></span>](../getting-started/walkthrough-my-first-wpf-desktop-application.md)
- [<span data-ttu-id="579bc-208">Información general sobre animaciones</span><span class="sxs-lookup"><span data-stu-id="579bc-208">Animation Overview</span></span>](animation-overview.md)
