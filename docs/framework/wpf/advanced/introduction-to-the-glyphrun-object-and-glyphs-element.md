---
title: Introducción al objeto GlyphRun y al elemento Glyphs
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], Glyphs element
- Glyphs elements [WPF]
- GlyphRun object [WPF]
- text [WPF], glyphs
- glyphs [WPF]
- typography [WPF], GlyphRun object
ms.assetid: 746ca769-a331-4435-9b95-f72a883b67c1
ms.openlocfilehash: 0e5ec2b89f015c7e061b59fea755eb368f1ac7a1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62031309"
---
# <a name="introduction-to-the-glyphrun-object-and-glyphs-element"></a><span data-ttu-id="03811-102">Introducción al objeto GlyphRun y al elemento Glyphs</span><span class="sxs-lookup"><span data-stu-id="03811-102">Introduction to the GlyphRun Object and Glyphs Element</span></span>
<span data-ttu-id="03811-103">Este tema se describe la <xref:System.Windows.Media.GlyphRun> objeto y el <xref:System.Windows.Documents.Glyphs> elemento.</span><span class="sxs-lookup"><span data-stu-id="03811-103">This topic describes the <xref:System.Windows.Media.GlyphRun> object and the <xref:System.Windows.Documents.Glyphs> element.</span></span>  

<a name="text_glyphrunovw_intro"></a>   
## <a name="introduction-to-glyphrun"></a><span data-ttu-id="03811-104">Introducción a GlyphRun</span><span class="sxs-lookup"><span data-stu-id="03811-104">Introduction to GlyphRun</span></span>  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="03811-105">proporciona compatibilidad con texto avanzado, incluido el marcado de nivel de glifos con acceso directo a <xref:System.Windows.Documents.Glyphs> para los clientes que quieran interceptar y conservar el texto después de darle formato.</span><span class="sxs-lookup"><span data-stu-id="03811-105">provides advanced text support including glyph-level markup with direct access to <xref:System.Windows.Documents.Glyphs> for customers who want to intercept and persist text after formatting.</span></span> <span data-ttu-id="03811-106">Estas características ofrecen una compatibilidad fundamental para los distintos requisitos de representación de texto en cada uno de los siguientes escenarios.</span><span class="sxs-lookup"><span data-stu-id="03811-106">These features provide critical support for the different text rendering requirements in each of the following scenarios.</span></span>  
  
1. <span data-ttu-id="03811-107">Presentación en pantalla de documentos de formato fijo.</span><span class="sxs-lookup"><span data-stu-id="03811-107">Screen display of fixed-format documents.</span></span>  
  
2. <span data-ttu-id="03811-108">Escenarios de impresión.</span><span class="sxs-lookup"><span data-stu-id="03811-108">Print scenarios.</span></span>  
  
    - [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] <span data-ttu-id="03811-109">como un lenguaje de impresora del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="03811-109">as a device printer language.</span></span>  
  
    - [!INCLUDE[TLA#tla_mxdw](../../../../includes/tlasharptla-mxdw-md.md)]<span data-ttu-id="03811-110">.</span><span class="sxs-lookup"><span data-stu-id="03811-110">.</span></span>  
  
    - <span data-ttu-id="03811-111">Controladores de impresora anteriores: salida de aplicaciones [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] al formato fijo.</span><span class="sxs-lookup"><span data-stu-id="03811-111">Previous printer drivers, output from [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] applications to the fixed format.</span></span>  
  
    - <span data-ttu-id="03811-112">Formato de cola de impresión.</span><span class="sxs-lookup"><span data-stu-id="03811-112">Print spool format.</span></span>  
  
3. <span data-ttu-id="03811-113">Representación de documentos de formato fijo, incluidos clientes de versiones anteriores de [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] y otros dispositivos informáticos.</span><span class="sxs-lookup"><span data-stu-id="03811-113">Fixed-format document representation, including clients for previous versions of [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] and other computing devices.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="03811-114"><xref:System.Windows.Documents.Glyphs> y <xref:System.Windows.Media.GlyphRun> están diseñados para escenarios de impresión y presentación de documentos de formato fijo.</span><span class="sxs-lookup"><span data-stu-id="03811-114"><xref:System.Windows.Documents.Glyphs> and <xref:System.Windows.Media.GlyphRun> are designed for fixed-format document presentation and print scenarios.</span></span> [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="03811-115">proporciona varios elementos para el diseño general y [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] escenarios, como <xref:System.Windows.Controls.Label> y <xref:System.Windows.Controls.TextBlock>.</span><span class="sxs-lookup"><span data-stu-id="03811-115">provides several elements for general layout and [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] scenarios such as <xref:System.Windows.Controls.Label> and <xref:System.Windows.Controls.TextBlock>.</span></span> <span data-ttu-id="03811-116">Para obtener más información sobre los escenarios de diseño y [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], consulte [Tipografía en WPF](typography-in-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="03811-116">For more information on layout and [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] scenarios, see the [Typography in WPF](typography-in-wpf.md).</span></span>  
  
<a name="text_glyphrunovw_glyphrunobject"></a>   
## <a name="the-glyphrun-object"></a><span data-ttu-id="03811-117">Objeto GlyphRun</span><span class="sxs-lookup"><span data-stu-id="03811-117">The GlyphRun Object</span></span>  
 <span data-ttu-id="03811-118">La <xref:System.Windows.Media.GlyphRun> objeto representa una secuencia de glifos de una sola cara de una única fuente en un solo tamaño y con un único estilo de representación.</span><span class="sxs-lookup"><span data-stu-id="03811-118">The <xref:System.Windows.Media.GlyphRun> object represents a sequence of glyphs from a single face of a single font at a single size, and with a single rendering style.</span></span>  
  
 <span data-ttu-id="03811-119"><xref:System.Windows.Media.GlyphRun> incluye ambos detalles de la fuente, como la propiedad <xref:System.Windows.Documents.Glyphs.Indices%2A> y posiciones de glifo individuales.</span><span class="sxs-lookup"><span data-stu-id="03811-119"><xref:System.Windows.Media.GlyphRun> includes both font details such as glyph <xref:System.Windows.Documents.Glyphs.Indices%2A> and individual glyph positions.</span></span> <span data-ttu-id="03811-120">También incluye el original [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] se generó la ejecución de información de asignación de desplazamiento de búfer de carácter a glifo y marcadores por glifo y por carácter de puntos de código.</span><span class="sxs-lookup"><span data-stu-id="03811-120">It also includes the original [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] code points the run was generated from, character-to-glyph buffer offset mapping information, and per-character and per-glyph flags.</span></span>  
  
 <span data-ttu-id="03811-121"><xref:System.Windows.Media.GlyphRun> le corresponde un alto nivel <xref:System.Windows.FrameworkElement>, <xref:System.Windows.Documents.Glyphs>.</span><span class="sxs-lookup"><span data-stu-id="03811-121"><xref:System.Windows.Media.GlyphRun> has a corresponding high-level <xref:System.Windows.FrameworkElement>, <xref:System.Windows.Documents.Glyphs>.</span></span> <span data-ttu-id="03811-122"><xref:System.Windows.Documents.Glyphs> se puede usar en el árbol de elementos y en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] marcado para representar <xref:System.Windows.Media.GlyphRun> salida.</span><span class="sxs-lookup"><span data-stu-id="03811-122"><xref:System.Windows.Documents.Glyphs> can be used in the element tree and in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup to represent <xref:System.Windows.Media.GlyphRun> output.</span></span>  
  
<a name="text_glyphrunovw_glyphselement"></a>   
## <a name="the-glyphs-element"></a><span data-ttu-id="03811-123">Elemento Glyphs</span><span class="sxs-lookup"><span data-stu-id="03811-123">The Glyphs Element</span></span>  
 <span data-ttu-id="03811-124">El <xref:System.Windows.Documents.Glyphs> elemento representa la salida de un <xref:System.Windows.Media.GlyphRun> en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="03811-124">The <xref:System.Windows.Documents.Glyphs> element represents the output of a <xref:System.Windows.Media.GlyphRun> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span> <span data-ttu-id="03811-125">La sintaxis de marcado siguiente se utiliza para describir el <xref:System.Windows.Documents.Glyphs> elemento.</span><span class="sxs-lookup"><span data-stu-id="03811-125">The following markup syntax is used to describe the <xref:System.Windows.Documents.Glyphs> element.</span></span>  
  
 [!code-xaml[GlyphsOvwSample1#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSample1/CS/default.xaml#1)]  
  
 <span data-ttu-id="03811-126">Las definiciones de propiedad siguientes corresponden a los primeros cuatro atributos del marcado del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="03811-126">The following property definitions correspond to the first four attributes in the sample markup.</span></span>  
  
|<span data-ttu-id="03811-127">Propiedad</span><span class="sxs-lookup"><span data-stu-id="03811-127">Property</span></span>|<span data-ttu-id="03811-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="03811-128">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.Windows.Documents.Glyphs.FontUri%2A>|<span data-ttu-id="03811-129">Especifica un identificador de recurso: nombre de archivo, Web [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)], o referencia de recurso en la aplicación .exe o contenedor.</span><span class="sxs-lookup"><span data-stu-id="03811-129">Specifies a resource identifier: file name, Web [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)], or resource reference in the application .exe or container.</span></span>|  
|<xref:System.Windows.Documents.Glyphs.FontRenderingEmSize%2A>|<span data-ttu-id="03811-130">Especifica el tamaño de fuente en unidades de superficie de dibujo (el valor predeterminado es de 0,96 pulgadas) .</span><span class="sxs-lookup"><span data-stu-id="03811-130">Specifies the font size in drawing surface units (default is .96 inches).</span></span>|  
|<xref:System.Windows.Documents.Glyphs.StyleSimulations%2A>|<span data-ttu-id="03811-131">Especifica marcas para los estilos de negrita y cursiva.</span><span class="sxs-lookup"><span data-stu-id="03811-131">Specifies flags for bold and Italic styles.</span></span>|  
|<xref:System.Windows.Documents.Glyphs.BidiLevel%2A>|<span data-ttu-id="03811-132">Especifica el nivel del diseño bidireccional.</span><span class="sxs-lookup"><span data-stu-id="03811-132">Specifies the bidirectional layout level.</span></span> <span data-ttu-id="03811-133">Los valores pares y cero implican un diseño de izquierda a derecha, mientras que los valores impares implican un diseño de derecha a izquierda.</span><span class="sxs-lookup"><span data-stu-id="03811-133">Even-numbered and zero values imply left-to-right layout; odd-numbered values imply right-to-left layout.</span></span>|  
  
<a name="text_glyphrunovw_indicesproperty"></a>   
### <a name="indices-property"></a><span data-ttu-id="03811-134">Propiedad Indices</span><span class="sxs-lookup"><span data-stu-id="03811-134">Indices property</span></span>  
 <span data-ttu-id="03811-135">El <xref:System.Windows.Documents.Glyphs.Indices%2A> propiedad es una cadena de especificaciones del glifo.</span><span class="sxs-lookup"><span data-stu-id="03811-135">The <xref:System.Windows.Documents.Glyphs.Indices%2A> property is a string of glyph specifications.</span></span> <span data-ttu-id="03811-136">Si una secuencia de glifos forma un clúster único, la especificación del primer glifo del clúster está precedida por una especificación de la cantidad de glifos y puntos de código que se combinan para formar el clúster.</span><span class="sxs-lookup"><span data-stu-id="03811-136">Where a sequence of glyphs forms a single cluster, the specification of the first glyph in the cluster is preceded by a specification of how many glyphs and how many code points combine to form the cluster.</span></span> <span data-ttu-id="03811-137">El <xref:System.Windows.Documents.Glyphs.Indices%2A> propiedad recopila en una cadena las siguientes propiedades.</span><span class="sxs-lookup"><span data-stu-id="03811-137">The <xref:System.Windows.Documents.Glyphs.Indices%2A> property collects in one string the following properties.</span></span>  
  
- <span data-ttu-id="03811-138">Índices de glifo</span><span class="sxs-lookup"><span data-stu-id="03811-138">Glyph indices</span></span>  
  
- <span data-ttu-id="03811-139">Anchos de avance de glifo</span><span class="sxs-lookup"><span data-stu-id="03811-139">Glyph advance widths</span></span>  
  
- <span data-ttu-id="03811-140">Combinación de vectores de los datos adjuntos de glifo</span><span class="sxs-lookup"><span data-stu-id="03811-140">Combining glyph attachment vectors</span></span>  
  
- <span data-ttu-id="03811-141">Asignación del clúster para los glifos de puntos de código</span><span class="sxs-lookup"><span data-stu-id="03811-141">Cluster mapping from code points to glyphs</span></span>  
  
- <span data-ttu-id="03811-142">Marcadores de glifo</span><span class="sxs-lookup"><span data-stu-id="03811-142">Glyph flags</span></span>  
  
 <span data-ttu-id="03811-143">Cada especificación de glifo tiene la forma siguiente.</span><span class="sxs-lookup"><span data-stu-id="03811-143">Each glyph specification has the following form.</span></span>  
  
 `[GlyphIndex][,[Advance][,[uOffset][,[vOffset][,[Flags]]]]]`  
  
<a name="text_glyphrunovw_glyphmetrics"></a>   
## <a name="glyph-metrics"></a><span data-ttu-id="03811-144">Métricas de glifo</span><span class="sxs-lookup"><span data-stu-id="03811-144">Glyph Metrics</span></span>  
 <span data-ttu-id="03811-145">Cada glifo define métricas que especifican cómo se alinea con otros <xref:System.Windows.Documents.Glyphs>.</span><span class="sxs-lookup"><span data-stu-id="03811-145">Each glyph defines metrics that specify how it aligns with other <xref:System.Windows.Documents.Glyphs>.</span></span> <span data-ttu-id="03811-146">En el gráfico siguiente se definen las distintas calidades tipográficas de dos caracteres de glifo diferentes.</span><span class="sxs-lookup"><span data-stu-id="03811-146">The following graphic defines the various typographic qualities of two different glyph characters.</span></span>  
  
 <span data-ttu-id="03811-147">![Diagrama de medidas de glifo](./media/glyph-example.png "glyph_example")</span><span class="sxs-lookup"><span data-stu-id="03811-147">![Diagraph of glyph measurements](./media/glyph-example.png "glyph_example")</span></span>  
  
<a name="text_glyphrunovw_glyphsmarkup"></a>   
## <a name="glyphs-markup"></a><span data-ttu-id="03811-148">Marcado de glifos</span><span class="sxs-lookup"><span data-stu-id="03811-148">Glyphs Markup</span></span>  
 <span data-ttu-id="03811-149">El ejemplo de código siguiente muestra cómo usar las distintas propiedades de la <xref:System.Windows.Documents.Glyphs> elemento [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="03811-149">The following code example shows how to use various properties of the <xref:System.Windows.Documents.Glyphs> element in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
 [!code-xaml[GlyphsOvwSamp2#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSamp2/CS/default.xaml#1)]  
  
## <a name="see-also"></a><span data-ttu-id="03811-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="03811-150">See also</span></span>

- [<span data-ttu-id="03811-151">Tipografía en WPF</span><span class="sxs-lookup"><span data-stu-id="03811-151">Typography in WPF</span></span>](typography-in-wpf.md)
- [<span data-ttu-id="03811-152">Documentos en WPF</span><span class="sxs-lookup"><span data-stu-id="03811-152">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="03811-153">Texto</span><span class="sxs-lookup"><span data-stu-id="03811-153">Text</span></span>](optimizing-performance-text.md)
