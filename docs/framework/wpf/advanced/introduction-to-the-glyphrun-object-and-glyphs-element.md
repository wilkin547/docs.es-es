---
title: "Introducci&#243;n al objeto GlyphRun y al elemento Glyphs | Microsoft Docs"
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
  - "tipografía, Glyphs (elemento)"
  - "Glyphs (elementos)"
  - "GlyphRun (objeto)"
  - "texto de glifos"
  - "glifos [WPF]"
  - "tipografía, GlyphRun (objeto)"
ms.assetid: 746ca769-a331-4435-9b95-f72a883b67c1
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 20
---
# Introducci&#243;n al objeto GlyphRun y al elemento Glyphs
Este tema se describe la <xref:System.Windows.Media.GlyphRun> objeto y el <xref:System.Windows.Documents.Glyphs> elemento.  
  
   
  
<a name="text_glyphrunovw_intro"></a>   
## <a name="introduction-to-glyphrun"></a>Introducción a GlyphRun  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]proporciona compatibilidad con texto avanzado incluido el marcado de nivel de glifos con acceso directo a <xref:System.Windows.Documents.Glyphs> para clientes que desean interceptar y conservar el texto después de darle formato. Estas características ofrecen compatibilidad fundamental para el texto diferentes requisitos de representación en cada uno de los siguientes escenarios.  
  
1.  Presentación en pantalla de documentos de formato fijo.  
  
2.  Escenarios de impresión.  
  
    -   [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]como un lenguaje de impresora del dispositivo.  
  
    -   [!INCLUDE[TLA#tla_mxdw](../../../../includes/tlasharptla-mxdw-md.md)]Operador  
  
    -   Controladores de impresora anteriores, salidos de [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] aplicaciones al formato fijo.  
  
    -   Formato de la cola de impresión.  
  
3.  Representación de documentos de formato fijo, incluidos clientes de versiones anteriores de [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] y otros dispositivos informáticos.  
  
> [!NOTE]
>  <xref:System.Windows.Documents.Glyphs> y <xref:System.Windows.Media.GlyphRun> están diseñadas para escenarios de impresión y presentación de documentos de formato fijo.                      [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]proporciona varios elementos para el diseño general y [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] escenarios como <xref:System.Windows.Controls.Label> y <xref:System.Windows.Controls.TextBlock>. Para obtener más información sobre el diseño y [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] escenarios, consulte el [tipografía en WPF](../../../../docs/framework/wpf/advanced/typography-in-wpf.md).  
  
<a name="text_glyphrunovw_glyphrunobject"></a>   
## <a name="the-glyphrun-object"></a>GlyphRun (objeto)  
 El <xref:System.Windows.Media.GlyphRun> objeto representa una secuencia de glifos de un solo tipo de letra de una única fuente en un solo tamaño y con un único estilo de representación.  
  
 <xref:System.Windows.Media.GlyphRun> incluye los detalles de la fuente, como la propiedad <xref:System.Windows.Documents.Glyphs.Indices%2A> y posiciones de glifo individuales. También incluye el original [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] se generó la ejecución de información de asignación de desplazamiento de búfer de carácter a glifo y marcadores por glifo y por carácter de puntos de código.  
  
 <xref:System.Windows.Media.GlyphRun> se corresponde con un alto nivel <xref:System.Windows.FrameworkElement>, <xref:System.Windows.Documents.Glyphs>.                  <xref:System.Windows.Documents.Glyphs> puede utilizarse en el árbol de elementos y en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] marcado para representar <xref:System.Windows.Media.GlyphRun> salida.  
  
<a name="text_glyphrunovw_glyphselement"></a>   
## <a name="the-glyphs-element"></a>Glyphs (elemento)  
 El <xref:System.Windows.Documents.Glyphs> elemento representa la salida de un <xref:System.Windows.Media.GlyphRun> en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. La sintaxis de marcado siguiente se utiliza para describir la <xref:System.Windows.Documents.Glyphs> elemento.  
  
 [!code-xml[GlyphsOvwSample1#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSample1/CS/default.xaml#1)]  
  
 Las definiciones de propiedad siguientes corresponden a los primeros cuatro atributos del marcado del ejemplo.  
  
|Propiedad|Descripción|  
|--------------|-----------------|  
|<xref:System.Windows.Documents.Glyphs.FontUri%2A>|Especifica un identificador de recurso: nombre de archivo Web [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)], o una referencia de recurso en la aplicación .exe o contenedor.|  
|<xref:System.Windows.Documents.Glyphs.FontRenderingEmSize%2A>|Especifica el tamaño de fuente en unidades (el valor predeterminado es.96 pulgadas) de la superficie de dibujo.|  
|<xref:System.Windows.Documents.Glyphs.StyleSimulations%2A>|Especifica los marcadores para los estilos de negrita y cursiva.|  
|<xref:System.Windows.Documents.Glyphs.BidiLevel%2A>|Especifica el nivel del diseño bidireccional. Pares y valores cero implican el diseño de izquierda a derecha; valores impares implican el diseño de derecha a izquierda.|  
  
<a name="text_glyphrunovw_indicesproperty"></a>   
### <a name="indices-property"></a>Propiedad Indices  
 El <xref:System.Windows.Documents.Glyphs.Indices%2A> propiedad es una cadena de especificaciones del glifo. Cuando una secuencia de glifos forma un clúster único, la especificación del primer glifo del clúster está precedida por una especificación del número de glifos y cuántos puntos de código se combinan para formar el clúster. El <xref:System.Windows.Documents.Glyphs.Indices%2A> propiedad recopila en una cadena, las siguientes propiedades.  
  
-   Índices de glifo  
  
-   Anchos de avance del glifo  
  
-   Combinación de vectores de datos adjuntos de glifo  
  
-   Asignación del clúster de puntos de código a los glifos  
  
-   Marcadores de glifo  
  
 Cada especificación del glifo tiene la forma siguiente.  
  
 `[GlyphIndex][,[Advance][,[uOffset][,[vOffset][,[Flags]]]]]`  
  
<a name="text_glyphrunovw_glyphmetrics"></a>   
## <a name="glyph-metrics"></a>Métricas de glifos  
 Cada glifo define métricas que especifican cómo se alinea con otros <xref:System.Windows.Documents.Glyphs>. El gráfico siguiente definen las distintas calidades tipográficas de dos caracteres de glifo diferentes.  
  
 ![Diagrama gráfico de medidas de glifo](../../../../docs/framework/wpf/advanced/media/glyph-example.png "glyph_example")  
  
<a name="text_glyphrunovw_glyphsmarkup"></a>   
## <a name="glyphs-markup"></a>Marcado de glifos  
 En el ejemplo de código siguiente se muestra cómo utilizar las distintas propiedades de la <xref:System.Windows.Documents.Glyphs> elemento [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-xml[GlyphsOvwSamp2#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSamp2/CS/default.xaml#1)]  
  
## <a name="see-also"></a>Vea también  
 [Tipografía en WPF](../../../../docs/framework/wpf/advanced/typography-in-wpf.md)   
 [Documentos en WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)   
 [Texto](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)