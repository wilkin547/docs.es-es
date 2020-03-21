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
ms.openlocfilehash: 32e8ab7104b8ea2f985395065868ed154ca1e378
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181963"
---
# <a name="introduction-to-the-glyphrun-object-and-glyphs-element"></a>Introducción al objeto GlyphRun y al elemento Glyphs
En este tema <xref:System.Windows.Media.GlyphRun> se <xref:System.Windows.Documents.Glyphs> describe el objeto y el elemento.  

<a name="text_glyphrunovw_intro"></a>
## <a name="introduction-to-glyphrun"></a>Introducción a GlyphRun  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]proporciona compatibilidad avanzada con texto, incluido <xref:System.Windows.Documents.Glyphs> el marcado a nivel de glifo con acceso directo a los clientes que desean interceptar y conservar texto después de formatear. Estas características ofrecen una compatibilidad fundamental para los distintos requisitos de representación de texto en cada uno de los siguientes escenarios.  
  
1. Presentación en pantalla de documentos de formato fijo.  
  
2. Escenarios de impresión.  
  
    - [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] como un lenguaje de impresora del dispositivo.  
  
    - Escritor de documentos de Microsoft XPS.  
  
    - Controladores de impresora anteriores, salida de aplicaciones Win32 al formato fijo.  
  
    - Formato de cola de impresión.  
  
3. Representación de documentos de formato fijo, incluidos los clientes de versiones anteriores de Windows y otros dispositivos informáticos.  
  
> [!NOTE]
> <xref:System.Windows.Documents.Glyphs>y <xref:System.Windows.Media.GlyphRun> están diseñados para la presentación de documentos de formato fijo y escenarios de impresión. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]proporciona varios elementos [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] para el <xref:System.Windows.Controls.Label> diseño <xref:System.Windows.Controls.TextBlock>general y escenarios como y . Para obtener más [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] información sobre el diseño y los escenarios, vea [la tipografía en WPFWPF](typography-in-wpf.md).  
  
<a name="text_glyphrunovw_glyphrunobject"></a>
## <a name="the-glyphrun-object"></a>Objeto GlyphRun  
 El <xref:System.Windows.Media.GlyphRun> objeto representa una secuencia de glifos de una sola cara de una sola fuente con un solo tamaño y con un único estilo de representación.  
  
 <xref:System.Windows.Media.GlyphRun>incluye tanto detalles <xref:System.Windows.Documents.Glyphs.Indices%2A> de fuente como glifos y posiciones de glifo individuales. También incluye los puntos de código Unicode originales desde los que se generó la ejecución, información de desplazamiento de búfer de carácter a glifo y marcas de desplazamiento de búfer por carácter y por glifo.  
  
 <xref:System.Windows.Media.GlyphRun>tiene un correspondiente <xref:System.Windows.FrameworkElement>alto <xref:System.Windows.Documents.Glyphs>nivel, . <xref:System.Windows.Documents.Glyphs>se puede utilizar en el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] árbol <xref:System.Windows.Media.GlyphRun> de elementos y en el marcado para representar la salida.  
  
<a name="text_glyphrunovw_glyphselement"></a>
## <a name="the-glyphs-element"></a>Elemento Glyphs  
 El <xref:System.Windows.Documents.Glyphs> elemento representa la <xref:System.Windows.Media.GlyphRun> salida [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]de un in . La siguiente sintaxis de <xref:System.Windows.Documents.Glyphs> marcado se utiliza para describir el elemento.  
  
 [!code-xaml[GlyphsOvwSample1#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSample1/CS/default.xaml#1)]  
  
 Las definiciones de propiedad siguientes corresponden a los primeros cuatro atributos del marcado del ejemplo.  
  
|Propiedad|Descripción|  
|--------------|-----------------|  
|<xref:System.Windows.Documents.Glyphs.FontUri%2A>|Especifica un identificador de recurso: nombre de archivo, identificador de recursos uniforme web (URI) o referencia de recursos en la aplicación .exe o contenedor.|  
|<xref:System.Windows.Documents.Glyphs.FontRenderingEmSize%2A>|Especifica el tamaño de fuente en unidades de superficie de dibujo (el valor predeterminado es de 0,96 pulgadas) .|  
|<xref:System.Windows.Documents.Glyphs.StyleSimulations%2A>|Especifica marcas para los estilos de negrita y cursiva.|  
|<xref:System.Windows.Documents.Glyphs.BidiLevel%2A>|Especifica el nivel del diseño bidireccional. Los valores pares y cero implican un diseño de izquierda a derecha, mientras que los valores impares implican un diseño de derecha a izquierda.|  
  
<a name="text_glyphrunovw_indicesproperty"></a>
### <a name="indices-property"></a>Propiedad Indices  
 La <xref:System.Windows.Documents.Glyphs.Indices%2A> propiedad es una cadena de especificaciones de glifo. Si una secuencia de glifos forma un clúster único, la especificación del primer glifo del clúster está precedida por una especificación de la cantidad de glifos y puntos de código que se combinan para formar el clúster. La <xref:System.Windows.Documents.Glyphs.Indices%2A> propiedad recopila en una cadena las siguientes propiedades.  
  
- Índices de glifo  
  
- Anchos de avance de glifo  
  
- Combinación de vectores de fijación de glifos  
  
- Asignación de clústeres de puntos de código a pictogramas  
  
- Banderas de glifo  
  
 Cada especificación de glifo tiene la forma siguiente.  
  
 `[GlyphIndex][,[Advance][,[uOffset][,[vOffset][,[Flags]]]]]`  
  
<a name="text_glyphrunovw_glyphmetrics"></a>
## <a name="glyph-metrics"></a>Métricas de glifo  
 Cada glifo define métricas que especifican <xref:System.Windows.Documents.Glyphs>cómo se alinea con otros archivos . En el gráfico siguiente se definen las distintas calidades tipográficas de dos caracteres de glifo diferentes.  
  
 ![Diagrama gráfico de medidas de glifo](./media/glyph-example.png "glyph_example")  
  
<a name="text_glyphrunovw_glyphsmarkup"></a>
## <a name="glyphs-markup"></a>Marcado de glifos  
 En el ejemplo de código siguiente <xref:System.Windows.Documents.Glyphs> se [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]muestra cómo utilizar varias propiedades del elemento en .  
  
 [!code-xaml[GlyphsOvwSamp2#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSamp2/CS/default.xaml#1)]  
  
## <a name="see-also"></a>Consulte también

- [Tipografía en WPF](typography-in-wpf.md)
- [Documentos en WPF](documents-in-wpf.md)
- [Texto](optimizing-performance-text.md)
