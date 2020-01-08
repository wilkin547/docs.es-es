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
ms.openlocfilehash: d509de02cd1b3f645ee439c0b0eb33fd1ddbdb07
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636112"
---
# <a name="advanced-text-formatting"></a>Formato de texto avanzado
Windows Presentation Foundation (WPF) proporciona un sólido conjunto de API para incluir texto en la aplicación. Las API de diseño y [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)], como <xref:System.Windows.Controls.TextBlock>, proporcionan los elementos más comunes y de uso general para la presentación de texto. Las API de dibujo, como <xref:System.Windows.Media.GlyphRunDrawing> y <xref:System.Windows.Media.FormattedText>, proporcionan un medio para incluir texto con formato en los dibujos. En el nivel más avanzado, WPF proporciona un motor de formato de texto extensible para controlar todos los aspectos de la presentación de texto, como la administración del almacén de texto, la administración del formato de ejecución de texto y la administración de objetos incrustados.  
  
 En este tema se proporciona una introducción al formato de texto de WPF. Se centra en la implementación del cliente y el uso del motor de formato de texto de WPF.  
  
> [!NOTE]
> Todos los ejemplos de código de este documento se pueden encontrar en el [ejemplo de formato de texto avanzado](https://go.microsoft.com/fwlink/?LinkID=159965).  

<a name="prereq"></a>   
## <a name="prerequisites"></a>Requisitos previos  
 En este tema se da por supuesto que está familiarizado con las API de nivel superior usadas para la presentación de texto. La mayoría de los escenarios de usuario no requerirán las API de formato de texto avanzadas que se describen en este tema. Para ver una introducción a las distintas API de texto, consulte [documentos en WPF](documents-in-wpf.md).  
  
<a name="section1"></a>   
## <a name="advanced-text-formatting"></a>Formato de texto avanzado  
 Los controles de diseño de texto y [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] en WPF proporcionan propiedades de formato que permiten incluir fácilmente texto con formato en la aplicación. Estos controles exponen varias propiedades para controlar la presentación de texto, como las de tipo de letra, tamaño y color. En circunstancias normales, estos controles pueden controlar la mayoría de las características de presentación de texto en la aplicación. Sin embargo, algunos escenarios avanzados requieren el control del almacenamiento de texto, así como su presentación. WPF proporciona un motor de formato de texto extensible para este fin.  
  
 Las características de formato de texto avanzadas que se encuentran en WPF constan de un motor de formato de texto, un almacén de texto, ejecuciones de texto y propiedades de formato. El motor de formato de texto, <xref:System.Windows.Media.TextFormatting.TextFormatter>, crea líneas de texto que se usarán para la presentación. Esto se consigue iniciando el proceso de formato de línea y llamando al <xref:System.Windows.Media.TextFormatting.TextFormatter.FormatLine%2A>del formateador de texto. El formateador de texto recupera las ejecuciones de texto del almacén de texto llamando al método <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A> del almacén. A continuación, el formateador de texto forma los objetos <xref:System.Windows.Media.TextFormatting.TextRun> en <xref:System.Windows.Media.TextFormatting.TextLine> objetos y se les asigna a la aplicación para su inspección o visualización.  
  
<a name="section2"></a>   
## <a name="using-the-text-formatter"></a>Uso del formateador de texto  
 <xref:System.Windows.Media.TextFormatting.TextFormatter> es el motor de formato de texto de WPF y proporciona servicios para dar formato y dividir las líneas de texto. El formateador de texto puede controlar los distintos formatos de caracteres de texto y estilos de párrafo, e incluye compatibilidad para el diseño de texto internacional.  
  
 A diferencia de una API de texto tradicional, el <xref:System.Windows.Media.TextFormatting.TextFormatter> interactúa con un cliente de diseño de texto a través de un conjunto de métodos de devolución de llamada. Requiere que el cliente proporcione estos métodos en una implementación de la clase <xref:System.Windows.Media.TextFormatting.TextSource>. En el diagrama siguiente se muestra la interacción del diseño de texto entre la aplicación cliente y <xref:System.Windows.Media.TextFormatting.TextFormatter>.  
  
 ![Diagrama de TextFormatter y cliente de diseño de texto](./media/advanced-text-formatting/text-layout-textformatter-interaction.png)  
  
 El formateador de texto se usa para recuperar las líneas de texto con formato del almacén de texto, que es una implementación de <xref:System.Windows.Media.TextFormatting.TextSource>. Esto se hace creando primero una instancia del formateador de texto mediante el método <xref:System.Windows.Media.TextFormatting.TextFormatter.Create%2A>. Este método crea una instancia del formateador de texto y establece los valores máximos de alto y ancho de línea. En cuanto se crea una instancia del formateador de texto, el proceso de creación de líneas se inicia llamando al método <xref:System.Windows.Media.TextFormatting.TextFormatter.FormatLine%2A>. <xref:System.Windows.Media.TextFormatting.TextFormatter> devuelve llamadas al origen de texto para recuperar el texto y los parámetros de formato de las ejecuciones de texto que forman una línea.  
  
 En el ejemplo siguiente, se muestra el proceso para formatear un almacén de texto. El objeto <xref:System.Windows.Media.TextFormatting.TextFormatter> se usa para recuperar las líneas de texto del almacén de texto y, a continuación, dar formato a la línea de texto para dibujar en el <xref:System.Windows.Media.DrawingContext>.  
  
 [!code-csharp[TextFormatterExample#100](~/samples/snippets/csharp/VS_Snippets_Wpf/TextFormatterExample/CSharp/Window1.xaml.cs#100)]
 [!code-vb[TextFormatterExample#100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextFormatterExample/VisualBasic/Window1.xaml.vb#100)]  
  
<a name="section3"></a>   
## <a name="implementing-the-client-text-store"></a>Implementación del almacén de texto de cliente  
 Al ampliar el motor de formato de texto, es necesario que implemente y administre todos los aspectos del almacén de texto. Esta no es una tarea trivial. El almacén de texto es responsable del seguimiento de las propiedades de las ejecuciones de texto, las propiedades de párrafo, los objetos incrustados y otro contenido similar. También proporciona el formateador de texto con objetos <xref:System.Windows.Media.TextFormatting.TextRun> individuales que utiliza el formateador de texto para crear objetos <xref:System.Windows.Media.TextFormatting.TextLine>.  
  
 Para controlar la virtualización del almacén de texto, el almacén de texto se debe derivar de <xref:System.Windows.Media.TextFormatting.TextSource>. <xref:System.Windows.Media.TextFormatting.TextSource> define el método que el formateador de texto usa para recuperar las ejecuciones de texto del almacén de texto. <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A> es el método que usa el formateador de texto para recuperar las ejecuciones de texto usadas en el formato de línea. El formateador de texto realiza repetidamente la llamada a <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A> hasta que se produce una de las siguientes condiciones:  
  
- Se devuelve una <xref:System.Windows.Media.TextFormatting.TextEndOfLine> o una subclase.  
  
- El ancho acumulado de las ejecuciones de texto supera el ancho de línea máximo especificado en la llamada para crear el formateador de texto o la llamada al método <xref:System.Windows.Media.TextFormatting.TextFormatter.FormatLine%2A> del formateador de texto.  
  
- Se devuelve una secuencia de nueva línea Unicode, como "CF", "LF" o "CRLF".  
  
<a name="section4"></a>   
## <a name="providing-text-runs"></a>Abastecimiento de ejecuciones de texto  
 La esencia del proceso de formato de texto es la interacción entre el formateador de texto y el almacén de texto. La implementación de <xref:System.Windows.Media.TextFormatting.TextSource> proporciona el formateador de texto con los objetos <xref:System.Windows.Media.TextFormatting.TextRun> y las propiedades con las que se va a dar formato a las ejecuciones de texto. Esta interacción se controla mediante el método <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A>, al que llama el formateador de texto.  
  
 En la tabla siguiente se muestran algunos de los objetos <xref:System.Windows.Media.TextFormatting.TextRun> predefinidos.  
  
|Tipo TextRun|Usage|  
|------------------|-----------|  
|<xref:System.Windows.Media.TextFormatting.TextCharacters>|Ejecución de texto especializada que se usa para devolver una representación de glifos de caracteres al formateador de texto.|  
|<xref:System.Windows.Media.TextFormatting.TextEmbeddedObject>|Ejecución de texto especializada que se usa para proporcionar contenido donde la medida, la prueba de posicionamiento y el dibujo se ejecutan de forma global, como un botón o una imagen dentro del texto.|  
|<xref:System.Windows.Media.TextFormatting.TextEndOfLine>|Ejecución de texto especializada que se usa para marcar el final de una línea.|  
|<xref:System.Windows.Media.TextFormatting.TextEndOfParagraph>|Ejecución de texto especializada que se usa para marcar el final de un párrafo.|  
|<xref:System.Windows.Media.TextFormatting.TextEndOfSegment>|La ejecución de texto especializada que se usa para marcar el final de un segmento, por ejemplo, para finalizar el ámbito afectado por una ejecución de <xref:System.Windows.Media.TextFormatting.TextModifier> anterior.|  
|<xref:System.Windows.Media.TextFormatting.TextHidden>|Ejecución de texto especializada que se usa para marcar un intervalo de caracteres ocultos.|  
|<xref:System.Windows.Media.TextFormatting.TextModifier>|Ejecución de texto especializada que se usa para modificar las propiedades de las ejecuciones de texto en su ámbito. El ámbito se extiende a la siguiente <xref:System.Windows.Media.TextFormatting.TextEndOfSegment> de la ejecución de texto coincidente, o al <xref:System.Windows.Media.TextFormatting.TextEndOfParagraph>siguiente.|  
  
 Se pueden crear subclases de cualquiera de los objetos <xref:System.Windows.Media.TextFormatting.TextRun> predefinidos. Esto permite que el origen del texto proporcione al formateador de texto ejecuciones de texto que incluyan datos personalizados.  
  
 En el ejemplo siguiente se muestra un método <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A>. Este almacén de texto devuelve <xref:System.Windows.Media.TextFormatting.TextRun> objetos al formateador de texto para su procesamiento.  
  
 [!code-csharp[TextFormatterExample#101](~/samples/snippets/csharp/VS_Snippets_Wpf/TextFormatterExample/CSharp/CustomTextSource.cs#101)]
 [!code-vb[TextFormatterExample#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextFormatterExample/VisualBasic/CustomTextSource.vb#101)]  
  
> [!NOTE]
> En este ejemplo, el almacén de texto proporciona las mismas propiedades de texto para todo el texto. Los almacenes de texto avanzados tendrían que implementar su propia administración de intervalos para permitir que caracteres individuales tengan propiedades diferentes.  
  
<a name="section5"></a>   
## <a name="specifying-formatting-properties"></a>Especificación de las propiedades de formato  
 <xref:System.Windows.Media.TextFormatting.TextRun> se da formato a los objetos mediante las propiedades proporcionadas por el almacén de texto. Estas propiedades tienen dos tipos, <xref:System.Windows.Media.TextFormatting.TextParagraphProperties> y <xref:System.Windows.Media.TextFormatting.TextRunProperties>. <xref:System.Windows.Media.TextFormatting.TextParagraphProperties> administrar propiedades de párrafo inclusivas, como <xref:System.Windows.TextAlignment> y <xref:System.Windows.FlowDirection>. <xref:System.Windows.Media.TextFormatting.TextRunProperties> son propiedades que pueden ser diferentes para cada ejecución de texto dentro de un párrafo, como el pincel de primer plano, el <xref:System.Windows.Media.Typeface>y el tamaño de fuente. Para implementar tipos de propiedades de ejecución de texto personalizado y de párrafo personalizado, la aplicación debe crear clases que deriven de <xref:System.Windows.Media.TextFormatting.TextParagraphProperties> y <xref:System.Windows.Media.TextFormatting.TextRunProperties> respectivamente.  
  
## <a name="see-also"></a>Vea también

- [Tipografía en WPF](typography-in-wpf.md)
- [Documentos en WPF](documents-in-wpf.md)
