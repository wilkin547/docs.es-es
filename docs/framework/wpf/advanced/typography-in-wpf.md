---
title: "Tipograf&#237;a en WPF | Microsoft Docs"
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
  - "tipografía, acerca de tipografía"
ms.assetid: 06cbf17b-6eff-4fe5-949d-2dd533e4e1f4
caps.latest.revision: 27
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 26
---
# Tipograf&#237;a en WPF
En este tema se introducen las características tipográficas principales de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Estas características incluyen mejoras en la calidad y el rendimiento de la representación de texto, compatibilidad con la tipografía de [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)], texto internacional mejorado, compatibilidad de fuentes mejorada y nuevas interfaces de programación de aplicaciones \(API\) de texto.  
  
   
  
<a name="Improved_Quality_and_Performance_of_Text"></a>   
## Mejora de la calidad y el rendimiento del texto  
 En [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], se presenta el texto utilizando [!INCLUDE[TLA#tla_ct](../../../../includes/tlasharptla-ct-md.md)], que mejora su claridad y legibilidad.  [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] es una tecnología de software desarrollada por [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)] que mejora la legibilidad del texto en las pantallas de cristal líquido \(LCD\) existentes, tales como las de los equipos portátiles, los Pocket PC o los monitores de pantalla plana.  [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] utiliza una presentación con unidades menores que los píxeles, que permite mostrar la forma real del texto con mayor fidelidad y alinear los caracteres con respecto a una parte fraccionaria de un píxel.  Esta resolución adicional aumenta la nitidez de los detalles diminutos en la presentación del texto, lo que facilita mucho su lectura durante espacios de tiempo prolongados.  Otra mejora de [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] es el suavizado de contorno en la dirección del eje y, que suaviza las partes superior e inferior de las curvas superficiales de los caracteres de texto.  Para obtener más detalles sobre las características de [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)], vea [Información general sobre ClearType](../../../../docs/framework/wpf/advanced/cleartype-overview.md).  
  
 ![Texto con función de suavizado de contorno de ClearType en la dirección del eje y](../../../../docs/framework/wpf/advanced/media/typographyinwpf02.png "TypographyInWPF02")  
Texto con suavizado de contorno de ClearType en la dirección del eje y  
  
 La canalización de representación de texto completa puede acelerarse mediante hardware en el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], siempre que el equipo cumpla los requisitos mínimos de hardware necesarios.  La representación que no se puede llevar a cabo mediante hardware se realiza mediante software.  La aceleración de hardware afecta a todas las fases de la canalización de representación de texto, desde el almacenamiento de glifos individuales hasta la aplicación del algoritmo de mezcla de [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] a la salida final mostrada, pasando por la composición de glifos en ejecuciones de glifos y la aplicación de efectos.  Para obtener más información sobre la aceleración de hardware, vea [Niveles de representación de gráficos](../../../../docs/framework/wpf/advanced/graphics-rendering-tiers.md).  
  
 ![Diagrama de la canalización de representación de texto](../../../../docs/framework/wpf/advanced/media/typographyinwpf01.png "TypographyInWPF01")  
Diagrama de la canalización de representación de texto  
  
 Además, el texto animado, ya sea mediante caracteres o glifos, aprovecha al máximo la capacidad de hardware de gráficos del [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  De este modo se suaviza la animación de texto.  
  
<a name="Rich_Typography"></a>   
## Tipografía enriquecida  
 El formato de fuente [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] es una extensión del formato de fuente [!INCLUDE[TLA#tla_truetype](../../../../includes/tlasharptla-truetype-md.md)].  [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)] y Adobe desarrollaron conjuntamente el formato de fuente [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)], que proporciona una completa selección de características tipográficas avanzadas.  El objeto <xref:System.Windows.Documents.Typography> expone muchas de las características avanzadas de las fuentes [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)], tales como alternativas estilísticas y letras floreadas.  [!INCLUDE[TLA2#tla_lhsdk](../../../../includes/tla2sharptla-lhsdk-md.md)] proporciona un conjunto de fuentes [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] de ejemplo diseñadas con características enriquecidas, tales como las fuentes Pericles y Pescadero.  Para obtener más información, vea [Paquete de fuentes OpenType de ejemplo](../../../../docs/framework/wpf/advanced/sample-opentype-font-pack.md).  
  
 La fuente [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] Pericles contiene glifos adicionales que proporcionan alternativas estilísticas al conjunto estándar de glifos.  En el texto siguiente se muestran glifos de alternativas estilísticas.  
  
 ![Texto que usa glifos alternativos de estilo OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont02.png "opentypefont02")  
Texto que utiliza alternativas estilísticas de glifos OpenType  
  
 Las letras floreadas son glifos decorativos en los que se utilizan adornos detallados que suelen asociarse a la caligrafía.  El texto siguiente muestra glifos normales y floreados de la fuente Pescadero.  
  
 ![Texto que usa glifos OpenType estándar y floreados](../../../../docs/framework/wpf/advanced/media/opentypefont08.png "opentypefont08")  
Texto que utiliza glifos OpenType normales y floreados  
  
 Para obtener más detalles sobre las características de [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)], vea [Características de las fuentes OpenType](../../../../docs/framework/wpf/advanced/opentype-font-features.md).  
  
<a name="Enhanced_International_Text_Support"></a>   
## Compatibilidad mejorada con el texto internacional  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona compatibilidad mejorada con el texto internacional mediante las características siguientes:  
  
-   Interlineado automático en todos los sistemas de escritura, mediante la medición adaptable.  
  
-   Compatibilidad general con el texto internacional.  Para obtener más información, vea [Globalización de WPF](../../../../docs/framework/wpf/advanced/globalization-for-wpf.md).  
  
-   Saltos de línea, guiones y justificación basados en el idioma.  
  
<a name="Enhanced_Font_Support"></a>   
## Compatibilidad mejorada de fuentes  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona compatibilidad mejorada con las fuentes mediante las características siguientes:  
  
-   Unicode para todo el texto.  Ya no se requiere un juego de caracteres ni una página de códigos para regir el comportamiento y la selección de fuentes.  
  
-   El comportamiento de las fuentes es independiente de la configuración global, como la configuración regional del sistema.  
  
-   Tipos <xref:System.Windows.FontWeight>, <xref:System.Windows.FontStretch>, y <xref:System.Windows.FontStyle> independientes para definir una clase <xref:System.Windows.Media.FontFamily>.  De este modo se proporciona mayor flexibilidad que en la programación de [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)], donde se utilizan combinaciones booleanas de cursiva y negrita para definir una familia de fuentes.  
  
-   El control de la dirección de escritura \(horizontal o vertical\) es independiente del nombre de la fuente.  
  
-   Los vínculos y el retroceso de fuente se incluyen en un archivo [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] portátil, mediante la tecnología de fuentes compuestas.  Las fuentes compuestas permiten la construcción de fuentes multilingües de intervalo completo.  Las fuentes compuestas también proporcionan un mecanismo que evita la presentación de glifos ausentes.  Para obtener más información, vea los comentarios de la clase <xref:System.Windows.Media.FontFamily>.  
  
-   Las fuentes internacionales se compilan a partir de fuentes compuestas, mediante un grupo de fuentes de un solo idioma.  De este modo se ahorran costos de recursos al desarrollar fuentes para varios idiomas.  
  
-   Las fuentes compuestas se incrustan en el documento para proporcionar portabilidad de los documentos.  Para obtener más información, vea los comentarios de la clase <xref:System.Windows.Media.FontFamily>.  
  
<a name="New_Text_APIs"></a>   
## Nuevas interfaces de programación de aplicaciones \(API\) de texto  
 El [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona varias [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] de texto que los programadores pueden usar al incluir texto en sus aplicaciones.  Estas [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] se agrupan en tres categorías:  
  
-   **Diseño e interfaz de usuario**.  Controles de texto comunes de la [!INCLUDE[TLA#tla_gui](../../../../includes/tlasharptla-gui-md.md)].  
  
-   **Dibujo de texto ligero**.  Permite dibujar texto directamente en los objetos.  
  
-   **Formato de texto avanzado**.  Permite implementar un motor de texto personalizado.  
  
### Diseño e interfaz de usuario  
 En el nivel superior de funcionalidad, las [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] de texto proporcionan controles comunes de la [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)], tales como <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.TextBlock> y <xref:System.Windows.Controls.TextBox>.  Estos controles proporcionan los elementos básicos de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] en una aplicación, además de constituir una manera fácil de presentar el texto e interactuar con él.  Los controles como <xref:System.Windows.Controls.RichTextBox> y <xref:System.Windows.Controls.PasswordBox> permiten un control más avanzado o especializado del texto.  Por su parte, las clases como <xref:System.Windows.Documents.TextRange>, <xref:System.Windows.Documents.TextSelection> y <xref:System.Windows.Documents.TextPointer> resultan de gran utilidad para manipular el texto.  Estos controles de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] proporcionan propiedades como <xref:System.Windows.Controls.Control.FontFamily%2A>, <xref:System.Windows.Controls.Control.FontSize%2A> y <xref:System.Windows.Controls.Control.FontStyle%2A>, que permiten controlar la fuente que se utiliza para representar el texto.  
  
#### Utilizar efectos de imagen, transformaciones y efectos de texto  
 El [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] permite crear usos visualmente interesantes de texto mediante características tales como efectos de imagen, transformaciones y efectos de texto.  En el ejemplo siguiente se muestra un tipo típico de efecto de sombra paralela aplicado al texto.  
  
 ![Sombra de texto con Suavidad &#61; 0.25](../../../../docs/framework/wpf/advanced/media/shadowtext01.png "ShadowText01")  
Texto con sombra paralela  
  
 En el ejemplo siguiente se muestra un efecto de sombra paralela y ruido aplicado al texto.  
  
 ![Sombra de texto con ruido](../../../../docs/framework/wpf/advanced/media/shadowtext04.png "ShadowText04")  
Texto con sombra paralela y ruido  
  
 En el ejemplo siguiente se muestra un efecto de resplandor exterior aplicado al texto.  
  
 ![Sombra de texto usando OuterGlowBitmapEffect](../../../../docs/framework/wpf/advanced/media/shadowtext05.png "ShadowText05")  
Texto con efecto de resplandor exterior  
  
 En el ejemplo siguiente se muestra un efecto de desenfoque aplicado al texto.  
  
 ![Sombra de texto usando BlurBitmapEffect](../../../../docs/framework/wpf/advanced/media/shadowtext06.png "ShadowText06")  
Texto con efecto de desenfoque  
  
 En el ejemplo siguiente se muestra la segunda línea de texto ajustada a una escala del 150% a lo largo del eje X y la tercera línea de texto ajustada a una escala del 150% a lo largo del eje Y.  
  
 ![Texto con escala ajustada usando ScaleTransform](../../../../docs/framework/wpf/advanced/media/transformedtext02.png "TransformedText02")  
Texto al que se ha aplicado ScaleTransform  
  
 En el ejemplo siguiente se muestra el texto sesgado a lo largo del eje X.  
  
 ![Texto sesgado usando SkewTransform](../../../../docs/framework/wpf/advanced/media/transformedtext03.png "TransformedText03")  
Texto al que se ha aplicado SkewTransform  
  
 <xref:System.Windows.Media.TextEffect> es un objeto auxiliar que permite tratar el texto como uno o más grupos de caracteres en una cadena de texto.  En el ejemplo siguiente se muestra un carácter individual al que se aplica una rotación.  Cada carácter gira de manera independiente a intervalos de 1 segundo.  
  
 ![Captura de pantalla de efecto de texto girando texto](../../../../docs/framework/wpf/advanced/media/texteffect01.png "TextEffect01")  
Ejemplo de animación de efecto de texto giratorio  
  
#### Utilizar documentos dinámicos  
 Además de los controles comunes de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona un control de diseño para la presentación de texto, el elemento <xref:System.Windows.Documents.FlowDocument>.  El elemento <xref:System.Windows.Documents.FlowDocument>, junto con el elemento <xref:System.Windows.Controls.DocumentViewer>, proporciona un control para grandes cantidades de texto con requisitos de diseño variables.  Los controles de diseño proporcionan acceso a la tipografía avanzada por medio del objeto <xref:System.Windows.Documents.Typography> y de las propiedades relacionadas con fuentes de otros controles de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
 En el ejemplo siguiente se muestra el contenido de texto hospedado en <xref:System.Windows.Controls.FlowDocumentReader>, que admite búsquedas, navegación, paginación y ajuste de contenidos.  
  
 ![Captura de pantalla del ejemplo Using OpenType Fonts](../../../../docs/framework/wpf/advanced/media/typographyinwpf-03.png "TypographyInWPF\_03")  
Texto hospedado en un objeto FlowDocumentReader  
  
 Para obtener más información, vea [Documentos en WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md).  
  
### Dibujo de texto ligero  
 Puede dibujar texto directamente en objetos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] mediante el método <xref:System.Windows.Media.DrawingContext.DrawText%2A> del objeto <xref:System.Windows.Media.DrawingContext>.  Para utilizar este método, cree un objeto <xref:System.Windows.Media.FormattedText>.  Este objeto permite dibujar texto de varias líneas, en el que se puede dar formato a cada carácter individualmente.  La funcionalidad del objeto <xref:System.Windows.Media.FormattedText> contiene gran parte de la funcionalidad de los marcadores de DrawText de la API de Win32.  Además, el objeto <xref:System.Windows.Media.FormattedText> contiene funcionalidades tales como la compatibilidad con los puntos suspensivos, que permite mostrar puntos suspensivos cuando el texto supera los límites establecidos.  En el ejemplo siguiente se muestra texto al que se han aplicado varios formatos, incluido un degradado lineal en las palabras segunda y tercera.  
  
 ![Texto mostrado mediante un objeto FormattedText](../../../../docs/framework/wpf/advanced/media/formattedtext01.png "FormattedText01")  
Texto mostrado mediante el objeto FormattedText  
  
 Puede convertir el texto con formato en objetos <xref:System.Windows.Media.Geometry>, lo que permite crear otros tipos de texto visualmente interesante.  Por ejemplo, podría crear un objeto <xref:System.Windows.Media.Geometry> basado en el contorno de una cadena de texto.  
  
 ![Esquema de texto que usa un pincel de degradado lineal](../../../../docs/framework/wpf/advanced/media/outlinedtext02.png "OutlinedText02")  
Aplicación de un contorno al texto mediante un pincel de degradado lineal  
  
 En los ejemplos siguientes se muestran varias maneras de crear efectos visuales interesantes modificando el trazo, el relleno y el resaltado del texto convertido.  
  
 ![Texto con colores diferentes para relleno y trazo](../../../../docs/framework/wpf/advanced/media/outlinedtext03.png "OutlinedText03")  
Ejemplo de cómo establecer el trazo y el relleno en diferentes colores  
  
 ![Texto con pincel de imagen aplicado a trazo](../../../../docs/framework/wpf/advanced/media/outlinedtext04.png "OutlinedText04")  
Ejemplo de un pincel de imagen aplicado al trazo  
  
 ![Texto con pincel de imagen aplicado a trazo](../../../../docs/framework/wpf/advanced/media/outlinedtext05.png "OutlinedText05")  
Ejemplo de un pincel de imagen aplicado al trazo y al resaltado  
  
 Para obtener más información sobre el objeto <xref:System.Windows.Media.FormattedText>, vea [Dibujar texto con formato](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md).  
  
### Formato de texto avanzado  
 En el nivel más avanzado de las [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] de texto, el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ofrece la capacidad de crear un diseño de texto personalizado mediante el objeto <xref:System.Windows.Media.TextFormatting.TextFormatter> y otros tipos en el espacio de nombres <xref:System.Windows.Media.TextFormatting>.  El objeto <xref:System.Windows.Media.TextFormatting.TextFormatter> y las clases asociadas permiten implementar un diseño de texto personalizado que admite su propia definición de formatos de caracteres, estilos de párrafo, reglas de salto de línea y otras características de diseño para el texto internacional.  Hay muy pocos casos en los que es conveniente invalidar la implementación predeterminada de la compatibilidad de diseño de texto del [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Sin embargo, si va a crear un control o aplicación de edición de texto, quizás necesite una implementación diferente que la predeterminada del [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 A diferencia de la [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] de texto tradicional, <xref:System.Windows.Media.TextFormatting.TextFormatter> interactúa con un cliente de diseño de texto a través de un conjunto de métodos de devolución de llamada.  Necesita que el cliente proporcione estos métodos en una implementación de la clase <xref:System.Windows.Media.TextFormatting.TextSource>.  En el diagrama siguiente se muestra la interacción de diseño de texto entre la aplicación cliente y <xref:System.Windows.Media.TextFormatting.TextFormatter>.  
  
 ![Diagrama de TextFormatter y cliente de diseño de texto](../../../../docs/framework/wpf/advanced/media/textformatter01.png "TextFormatter01")  
Interacción entre la aplicación y TextFormatter  
  
 Para obtener información más detallada sobre cómo crear el diseño de texto personalizado, vea [Formato de texto avanzado](../../../../docs/framework/wpf/advanced/advanced-text-formatting.md).  
  
## Vea también  
 <xref:System.Windows.Media.FormattedText>   
 <xref:System.Windows.Media.TextFormatting.TextFormatter>   
 [Información general sobre ClearType](../../../../docs/framework/wpf/advanced/cleartype-overview.md)   
 [Características de las fuentes OpenType](../../../../docs/framework/wpf/advanced/opentype-font-features.md)   
 [Dibujar texto con formato](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md)   
 [Formato de texto avanzado](../../../../docs/framework/wpf/advanced/advanced-text-formatting.md)   
 [Text](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)   
 [Microsoft Typography](http://www.microsoft.com/typography/default.mspx)