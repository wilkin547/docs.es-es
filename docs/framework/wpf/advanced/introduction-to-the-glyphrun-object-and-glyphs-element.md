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
ms.openlocfilehash: 9e40a9656bd1d89203b167860ef6951d5e30377c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918394"
---
# <a name="introduction-to-the-glyphrun-object-and-glyphs-element"></a>Introducción al objeto GlyphRun y al elemento Glyphs
En este tema se <xref:System.Windows.Media.GlyphRun> describe el objeto <xref:System.Windows.Documents.Glyphs> y el elemento.  

<a name="text_glyphrunovw_intro"></a>   
## <a name="introduction-to-glyphrun"></a>Introducción a GlyphRun  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]proporciona compatibilidad con texto avanzado, incluido el marcado de nivel de glifos con acceso directo a <xref:System.Windows.Documents.Glyphs> para los clientes que quieren interceptar y conservar el texto después de darle formato. Estas características ofrecen una compatibilidad fundamental para los distintos requisitos de representación de texto en cada uno de los siguientes escenarios.  
  
1. Presentación en pantalla de documentos de formato fijo.  
  
2. Escenarios de impresión.  
  
    - [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] como un lenguaje de impresora del dispositivo.  
  
    - Escritor de documentos XPS de Microsoft.  
  
    - Controladores de impresora anteriores: salida de aplicaciones [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] al formato fijo.  
  
    - Formato de cola de impresión.  
  
3. Representación de documentos de formato fijo, incluidos clientes de versiones anteriores de Windows y otros dispositivos informáticos.  
  
> [!NOTE]
> <xref:System.Windows.Documents.Glyphs>y <xref:System.Windows.Media.GlyphRun> están diseñados para escenarios de impresión y presentación de documentos de formato fijo. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]proporciona varios elementos para el diseño general [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] y escenarios <xref:System.Windows.Controls.Label> como y <xref:System.Windows.Controls.TextBlock>. Para obtener más información sobre los escenarios de diseño y [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], consulte [Tipografía en WPF](typography-in-wpf.md).  
  
<a name="text_glyphrunovw_glyphrunobject"></a>   
## <a name="the-glyphrun-object"></a>Objeto GlyphRun  
 El <xref:System.Windows.Media.GlyphRun> objeto representa una secuencia de glifos de un solo aspecto de una sola fuente con un solo tamaño y con un único estilo de representación.  
  
 <xref:System.Windows.Media.GlyphRun>incluye detalles de fuente como glifo <xref:System.Windows.Documents.Glyphs.Indices%2A> y posiciones de glifo individuales. También incluye los puntos de [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] código originales desde los que se generó la ejecución, la información de asignación de desplazamiento de búfer de carácter a glifo y las marcas por carácter y por glifo.  
  
 <xref:System.Windows.Media.GlyphRun>tiene un de alto nivel <xref:System.Windows.FrameworkElement>correspondiente,. <xref:System.Windows.Documents.Glyphs> <xref:System.Windows.Documents.Glyphs>se puede usar en el árbol de elementos y [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] en el marcado <xref:System.Windows.Media.GlyphRun> para representar la salida.  
  
<a name="text_glyphrunovw_glyphselement"></a>   
## <a name="the-glyphs-element"></a>Elemento Glyphs  
 El <xref:System.Windows.Documents.Glyphs> elemento representa la salida de un <xref:System.Windows.Media.GlyphRun> en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. La sintaxis de marcado siguiente se utiliza para describir <xref:System.Windows.Documents.Glyphs> el elemento.  
  
 [!code-xaml[GlyphsOvwSample1#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSample1/CS/default.xaml#1)]  
  
 Las definiciones de propiedad siguientes corresponden a los primeros cuatro atributos del marcado del ejemplo.  
  
|Propiedad|DESCRIPCIÓN|  
|--------------|-----------------|  
|<xref:System.Windows.Documents.Glyphs.FontUri%2A>|Especifica un identificador de recurso: nombre de archivo, [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)]web o referencia de recurso en el contenedor Application. exe o.|  
|<xref:System.Windows.Documents.Glyphs.FontRenderingEmSize%2A>|Especifica el tamaño de fuente en unidades de superficie de dibujo (el valor predeterminado es de 0,96 pulgadas) .|  
|<xref:System.Windows.Documents.Glyphs.StyleSimulations%2A>|Especifica marcas para los estilos de negrita y cursiva.|  
|<xref:System.Windows.Documents.Glyphs.BidiLevel%2A>|Especifica el nivel del diseño bidireccional. Los valores pares y cero implican un diseño de izquierda a derecha, mientras que los valores impares implican un diseño de derecha a izquierda.|  
  
<a name="text_glyphrunovw_indicesproperty"></a>   
### <a name="indices-property"></a>Propiedad Indices  
 La <xref:System.Windows.Documents.Glyphs.Indices%2A> propiedad es una cadena de especificaciones de glifo. Si una secuencia de glifos forma un clúster único, la especificación del primer glifo del clúster está precedida por una especificación de la cantidad de glifos y puntos de código que se combinan para formar el clúster. La <xref:System.Windows.Documents.Glyphs.Indices%2A> propiedad recopila en una cadena las siguientes propiedades.  
  
- Índices de glifo  
  
- Anchos de avance de glifo  
  
- Combinación de vectores de datos adjuntos de glifo  
  
- Asignación de clústeres desde puntos de código a glifos  
  
- Marcas de glifo  
  
 Cada especificación de glifo tiene la forma siguiente.  
  
 `[GlyphIndex][,[Advance][,[uOffset][,[vOffset][,[Flags]]]]]`  
  
<a name="text_glyphrunovw_glyphmetrics"></a>   
## <a name="glyph-metrics"></a>Métricas de glifo  
 Cada glifo define métricas que especifican cómo se alinea con otros <xref:System.Windows.Documents.Glyphs>. En el gráfico siguiente se definen las distintas calidades tipográficas de dos caracteres de glifo diferentes.  
  
 ![Diagrama de medidas de glifo](./media/glyph-example.png "glyph_example")  
  
<a name="text_glyphrunovw_glyphsmarkup"></a>   
## <a name="glyphs-markup"></a>Marcado de glifos  
 En el ejemplo de código siguiente se muestra cómo utilizar varias propiedades <xref:System.Windows.Documents.Glyphs> del elemento [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]en.  
  
 [!code-xaml[GlyphsOvwSamp2#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSamp2/CS/default.xaml#1)]  
  
## <a name="see-also"></a>Vea también

- [Tipografía en WPF](typography-in-wpf.md)
- [Documentos en WPF](documents-in-wpf.md)
- [Texto](optimizing-performance-text.md)
