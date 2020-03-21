---
title: Formato de texto avanzado
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- formatting [WPF]
- text [WPF]
- typography [WPF], text formatting
ms.assetid: f0a7986e-f5b2-485c-a27d-f8e922022212
ms.openlocfilehash: 745d20e0bd4f877f9d4559f9fc7829b56689d35c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185944"
---
# <a name="advanced-text-formatting"></a>Formato de texto avanzado
Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF) proporciona un sólido conjunto de API para incluir texto en la aplicación. El [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] diseño y las <xref:System.Windows.Controls.TextBlock>API, como , proporcionan los elementos más comunes y de uso general para la presentación de texto. Las API de <xref:System.Windows.Media.GlyphRunDrawing> dibujo, como y <xref:System.Windows.Media.FormattedText>, proporcionan un medio para incluir texto con formato en dibujos. En el nivel más avanzado, WPFWPF proporciona un motor de formato de texto extensible para controlar todos los aspectos de la presentación de texto, como la administración de almacenes de texto, la administración de formato de ejecución de texto y la administración de objetos incrustados.  
  
 En este tema se proporciona una introducción al formato de texto WPFWPF. Se centra en la implementación del cliente y el uso del motor de formato de texto WPFWPF.  
  
> [!NOTE]
> Todos los ejemplos de código de este documento se pueden encontrar en el ejemplo de formato de [texto avanzado](https://github.com/Microsoft/WPF-Samples/tree/master/PerMonitorDPI/TextFormatting).  

<a name="prereq"></a>
## <a name="prerequisites"></a>Requisitos previos  
 En este tema se supone que está familiarizado con las API de nivel superior utilizadas para la presentación de texto. La mayoría de los escenarios de usuario no requerirán las API de formato de texto avanzadas que se describen en este tema. Para obtener una introducción a las diferentes API de texto, vea [Documentos en WPF .](documents-in-wpf.md)  
  
<a name="section1"></a>
## <a name="advanced-text-formatting"></a>Formato de texto avanzado  
 El diseño [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de texto y los controles de WPFWPF proporcionan propiedades de formato que permiten incluir fácilmente texto con formato en la aplicación. Estos controles exponen varias propiedades para controlar la presentación de texto, como las de tipo de letra, tamaño y color. En circunstancias normales, estos controles pueden controlar la mayoría de las características de presentación de texto en la aplicación. Sin embargo, algunos escenarios avanzados requieren el control del almacenamiento de texto, así como su presentación. WPFWPF proporciona un motor de formato de texto extensible para este propósito.  
  
 Las características avanzadas de formato de texto que se encuentran en WPFWPF constan de un motor de formato de texto, un almacén de texto, ejecuciones de texto y propiedades de formato. El motor de <xref:System.Windows.Media.TextFormatting.TextFormatter>formato de texto, , crea líneas de texto que se utilizarán para la presentación. Esto se logra iniciando el proceso de formato de <xref:System.Windows.Media.TextFormatting.TextFormatter.FormatLine%2A>línea y llamando al formateador de texto . El formateador de texto recupera las ejecuciones de <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A> texto del almacén de texto llamando al método de la tienda. A <xref:System.Windows.Media.TextFormatting.TextRun> continuación, el <xref:System.Windows.Media.TextFormatting.TextLine> formateador de texto forma los objetos se forman en objetos y se asignan a la aplicación para su inspección o visualización.  
  
<a name="section2"></a>
## <a name="using-the-text-formatter"></a>Uso del formateador de texto  
 <xref:System.Windows.Media.TextFormatting.TextFormatter>es el motor de formato de texto WPFWPF y proporciona servicios para dar formato y romper líneas de texto. El formateador de texto puede controlar los distintos formatos de caracteres de texto y estilos de párrafo, e incluye compatibilidad para el diseño de texto internacional.  
  
 A diferencia de una <xref:System.Windows.Media.TextFormatting.TextFormatter> API de texto tradicional, interactúa con un cliente de diseño de texto a través de un conjunto de métodos de devolución de llamada. Requiere que el cliente proporcione estos métodos <xref:System.Windows.Media.TextFormatting.TextSource> en una implementación de la clase. En el diagrama siguiente se muestra la <xref:System.Windows.Media.TextFormatting.TextFormatter>interacción de diseño de texto entre la aplicación cliente y .  
  
 ![Diagrama de TextFormatter y cliente de diseño de texto](./media/advanced-text-formatting/text-layout-textformatter-interaction.png)  
  
 El formateador de texto se utiliza para recuperar líneas de <xref:System.Windows.Media.TextFormatting.TextSource>texto con formato del almacén de texto, que es una implementación de . Esto se hace creando primero una instancia del <xref:System.Windows.Media.TextFormatting.TextFormatter.Create%2A> formateador de texto mediante el método. Este método crea una instancia del formateador de texto y establece los valores máximos de alto y ancho de línea. Tan pronto como se crea una instancia del formateador de <xref:System.Windows.Media.TextFormatting.TextFormatter.FormatLine%2A> texto, el proceso de creación de líneas se inicia llamando al método. <xref:System.Windows.Media.TextFormatting.TextFormatter>vuelve a llamar al origen de texto para recuperar el texto y los parámetros de formato para las ejecuciones de texto que forman una línea.  
  
 En el ejemplo siguiente, se muestra el proceso para formatear un almacén de texto. El <xref:System.Windows.Media.TextFormatting.TextFormatter> objeto se utiliza para recuperar líneas de texto del almacén <xref:System.Windows.Media.DrawingContext>de texto y, a continuación, dar formato a la línea de texto para dibujar en el archivo .  
  
 [!code-csharp[TextFormatterExample#100](~/samples/snippets/csharp/VS_Snippets_Wpf/TextFormatterExample/CSharp/Window1.xaml.cs#100)]
 [!code-vb[TextFormatterExample#100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextFormatterExample/VisualBasic/Window1.xaml.vb#100)]  
  
<a name="section3"></a>
## <a name="implementing-the-client-text-store"></a>Implementación del almacén de texto de cliente  
 Al ampliar el motor de formato de texto, es necesario que implemente y administre todos los aspectos del almacén de texto. Esta no es una tarea trivial. El almacén de texto es responsable del seguimiento de las propiedades de las ejecuciones de texto, las propiedades de párrafo, los objetos incrustados y otro contenido similar. También proporciona el formateador <xref:System.Windows.Media.TextFormatting.TextRun> de texto con objetos <xref:System.Windows.Media.TextFormatting.TextLine> individuales que el formateador de texto utiliza para crear objetos.  
  
 Para controlar la virtualización del almacén de texto, <xref:System.Windows.Media.TextFormatting.TextSource>el almacén de texto debe derivarse de . <xref:System.Windows.Media.TextFormatting.TextSource>define el método que utiliza el formateador de texto para recuperar ejecuciones de texto del almacén de texto. <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A>es el método utilizado por el formateador de texto para recuperar las ejecuciones de texto utilizadas en el formato de línea. La llamada <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A> a se realiza repetidamente por el formateador de texto hasta que se produce una de las siguientes condiciones:  
  
- Se <xref:System.Windows.Media.TextFormatting.TextEndOfLine> devuelve una o una subclase.  
  
- El ancho acumulado de las ejecuciones de texto supera el ancho de línea máximo especificado en la <xref:System.Windows.Media.TextFormatting.TextFormatter.FormatLine%2A> llamada para crear el formateador de texto o la llamada al método del formateador de texto.  
  
- Se devuelve una secuencia de nueva línea Unicode, como "CF", "LF" o "CRLF".  
  
<a name="section4"></a>
## <a name="providing-text-runs"></a>Abastecimiento de ejecuciones de texto  
 La esencia del proceso de formato de texto es la interacción entre el formateador de texto y el almacén de texto. La implementación de proporciona el formateador de <xref:System.Windows.Media.TextFormatting.TextSource> texto con los <xref:System.Windows.Media.TextFormatting.TextRun> objetos y las propiedades con las que se va a dar formato al texto. Esta interacción se <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A> controla mediante el método, al que llama el formateador de texto.  
  
 En la tabla siguiente se <xref:System.Windows.Media.TextFormatting.TextRun> muestran algunos de los objetos predefinidos.  
  
|Tipo TextRun|Uso|  
|------------------|-----------|  
|<xref:System.Windows.Media.TextFormatting.TextCharacters>|Ejecución de texto especializada que se usa para devolver una representación de glifos de caracteres al formateador de texto.|  
|<xref:System.Windows.Media.TextFormatting.TextEmbeddedObject>|Ejecución de texto especializada que se usa para proporcionar contenido donde la medida, la prueba de posicionamiento y el dibujo se ejecutan de forma global, como un botón o una imagen dentro del texto.|  
|<xref:System.Windows.Media.TextFormatting.TextEndOfLine>|Ejecución de texto especializada que se usa para marcar el final de una línea.|  
|<xref:System.Windows.Media.TextFormatting.TextEndOfParagraph>|Ejecución de texto especializada que se usa para marcar el final de un párrafo.|  
|<xref:System.Windows.Media.TextFormatting.TextEndOfSegment>|La ejecución de texto especializada utilizada para marcar el final de un <xref:System.Windows.Media.TextFormatting.TextModifier> segmento, por ejemplo, para finalizar el ámbito afectado por una ejecución anterior.|  
|<xref:System.Windows.Media.TextFormatting.TextHidden>|Ejecución de texto especializada que se usa para marcar un intervalo de caracteres ocultos.|  
|<xref:System.Windows.Media.TextFormatting.TextModifier>|Ejecución de texto especializada que se usa para modificar las propiedades de las ejecuciones de texto en su ámbito. El ámbito se extiende <xref:System.Windows.Media.TextFormatting.TextEndOfSegment> a la siguiente <xref:System.Windows.Media.TextFormatting.TextEndOfParagraph>ejecución de texto coincidente o a la siguiente.|  
  
 Cualquiera de los <xref:System.Windows.Media.TextFormatting.TextRun> objetos predefinidos se puede subclase. Esto permite que el origen del texto proporcione al formateador de texto ejecuciones de texto que incluyan datos personalizados.  
  
 En el ejemplo <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A> siguiente se muestra un método. Este almacén <xref:System.Windows.Media.TextFormatting.TextRun> de texto devuelve objetos al formateador de texto para su procesamiento.  
  
 [!code-csharp[TextFormatterExample#101](~/samples/snippets/csharp/VS_Snippets_Wpf/TextFormatterExample/CSharp/CustomTextSource.cs#101)]
 [!code-vb[TextFormatterExample#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextFormatterExample/VisualBasic/CustomTextSource.vb#101)]  
  
> [!NOTE]
> En este ejemplo, el almacén de texto proporciona las mismas propiedades de texto para todo el texto. Los almacenes de texto avanzados tendrían que implementar su propia administración de intervalos para permitir que caracteres individuales tengan propiedades diferentes.  
  
<a name="section5"></a>
## <a name="specifying-formatting-properties"></a>Especificación de las propiedades de formato  
 <xref:System.Windows.Media.TextFormatting.TextRun>los objetos se formatean mediante las propiedades proporcionadas por el almacén de texto. Estas propiedades vienen en <xref:System.Windows.Media.TextFormatting.TextParagraphProperties> <xref:System.Windows.Media.TextFormatting.TextRunProperties>dos tipos y . <xref:System.Windows.Media.TextFormatting.TextParagraphProperties>controlar las propiedades <xref:System.Windows.TextAlignment> inclusivas de párrafo, como y <xref:System.Windows.FlowDirection>. <xref:System.Windows.Media.TextFormatting.TextRunProperties>son propiedades que pueden ser diferentes para cada texto que <xref:System.Windows.Media.Typeface>se ejecuta dentro de un párrafo, como el pincel en primer plano, y el tamaño de fuente. Para implementar tipos de propiedad de ejecución de texto personalizado <xref:System.Windows.Media.TextFormatting.TextParagraphProperties> <xref:System.Windows.Media.TextFormatting.TextRunProperties> y párrafo personalizado, la aplicación debe crear clases que se deriven de y, respectivamente.  
  
## <a name="see-also"></a>Consulte también

- [Tipografía en WPF](typography-in-wpf.md)
- [Documentos en WPF](documents-in-wpf.md)
