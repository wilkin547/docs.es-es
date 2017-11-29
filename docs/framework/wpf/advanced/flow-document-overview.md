---
title: "Información general sobre documentos dinámicos"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 'documents [WPF], flow documents [WPF], , '
- ', '
- flow documents [WPF]
ms.assetid: ef236a50-d44f-43c8-ba7c-82b0c733c0b7
caps.latest.revision: "39"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 10f7eda2b6761a825dcb2b24ae9f11b2e1262d7e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="flow-document-overview"></a>Información general sobre documentos dinámicos
Los documentos dinámicos están diseñados para optimizar su visualización y legibilidad. En lugar de establecer un diseño predefinido, los documentos dinámicos ajustan y redistribuyen dinámicamente su contenido basándose en variables en tiempo de ejecución, como el tamaño de la ventana, la resolución del dispositivo y las preferencias opcionales del usuario. Además, los documentos dinámicos ofrecen características de documento avanzadas, como paginación y columnas. En este tema se proporciona información general sobre los documentos dinámicos y cómo crearlos.  
  

  
<a name="what_is_a_flow_document"></a>   
## <a name="what-is-a-flow-document"></a>Qué es un documento dinámico  
 Un documento dinámico está diseñado para "redistribuir el contenido" según el tamaño de la ventana, la resolución del dispositivo y otras variables del entorno. Además, los documentos dinámicos tienen varias características integradas, como la búsqueda, los modos de visualización que optimizan la legibilidad, y la capacidad de cambiar el tamaño y el aspecto de las fuentes. Los documentos dinámicos se utilizan mejor cuando la facilidad de lectura es el escenario principal de consumo del documento. En cambio, los documentos fijos están diseñados para tener una presentación estática. Los documentos fijos son útiles cuando la fidelidad del contenido de origen es esencial. Vea [documentos en WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md) para obtener más información acerca de diferentes tipos de documentos.  
  
 En la ilustración siguiente se muestra un ejemplo de documento dinámico visualizado en varias ventanas de tamaños diferentes. A medida que cambia el área de visualización, el contenido se redistribuye para aprovechar mejor el espacio disponible.  
  
 ![Redistribución del contenido de un documento dinámico](../../../../docs/framework/wpf/advanced/media/edocs-flowdocument.png "eDocs_FlowDocument")  
  
 Tal como se muestra en la imagen anterior, el contenido dinámico puede incluir muchos componentes, como párrafos, listas, imágenes, etc. Estos componentes corresponden a elementos de marcado y objetos en el código de procedimiento. Se pasa a través de estas clases detalladamente más adelante en el [flujo clases relacionadas](#flow_related_classes) sección de esta información general. Por ahora, este es un ejemplo de código simple que crea un documento dinámico que consta de un párrafo con texto en negrita y una lista.
  
 [!code-xaml[FlowOvwSnippets_snip#SimpleFlowExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SimpleFlowExample.xaml#simpleflowexamplewholepage)]  
  
 [!code-csharp[FlowOvwSnippets_procedural_snip#SimpleFlowCodeOnlyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/SimpleFlowExample.cs#simpleflowcodeonlyexamplewholepage)]
 [!code-vb[FlowOvwSnippets_procedural_snip#SimpleFlowCodeOnlyExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/SimpleFlowExample.vb#simpleflowcodeonlyexamplewholepage)]  
  
 En la ilustración siguiente se muestra el aspecto de este fragmento de código.  
  
 ![Captura de pantalla: Ejemplo de FlowDocument representado](../../../../docs/framework/wpf/advanced/media/flow-ovw-first-example.png "Flow_Ovw_First_Example")  
  
 En este ejemplo, el <xref:System.Windows.Controls.FlowDocumentReader> control se usa para hospedar el contenido dinámico. Vea [tipos de documentos dinámicos](#flow_document_types) para obtener más información sobre los controles que hospedan contenido dinámico. <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.List>, <xref:System.Windows.Documents.ListItem>, y <xref:System.Windows.Documents.Bold> elementos se utilizan para controlar el formato del contenido, según su orden en el marcado. Por ejemplo, el <xref:System.Windows.Documents.Bold> elemento abarca solo una parte del texto en el párrafo; por tanto, solamente esa parte del texto está en negrita. Si ha utilizado HTML, esto le resultará familiar.  
  
 Como se resalta en la ilustración anterior, hay varias características integradas en documentos dinámicos:
  
-   Buscar: permite al usuario realizar una búsqueda de texto completo en todo un documento.  
  
-   Modo de visualización: el usuario puede seleccionar su modo de visualización preferido, incluido el modo de visualización de una sola página (una página a la vez), el modo de visualización de dos página a la vez (formato de lectura de libro) y un modo de desplazamiento continuo (sin límite).  Para obtener más información acerca de estos modos de visualización, consulte <xref:System.Windows.Controls.FlowDocumentReaderViewingMode>.  
  
-   Controles de navegación de página: si el modo de visualización del documento utiliza páginas, los controles de navegación de páginas incluyen un botón para ir a la página siguiente (flecha abajo) o la página anterior (flecha arriba), así como indicadores para el número de página actual y el número total de páginas. Las páginas también pueden voltearse mediante las teclas de flecha del teclado.  
  
-   Zoom: los controles de zoom permiten al usuario aumentar o disminuir el nivel de zoom haciendo clic en los botones de más o menos, respectivamente. Los controles de zoom incluyen también un control deslizante para ajustar el nivel de zoom. Para obtener más información, consulta <xref:System.Windows.Controls.FlowDocumentReader.Zoom%2A>.  
  
 Estas características pueden modificarse según el control utilizado para hospedar el contenido dinámico. En la siguiente sección se describen los distintos controles.  
  
<a name="flow_document_types"></a>   
## <a name="flow-document-types"></a>Tipos de documentos dinámicos  
 La visualización del contenido de los documentos dinámicos y cómo aparece depende de qué objeto se utilice para hospedar el contenido dinámico. Hay cuatro controles que admiten la visualización de contenido dinámico: <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, <xref:System.Windows.Controls.RichTextBox>, y <xref:System.Windows.Controls.FlowDocumentScrollViewer>. Estos controles se describen brevemente a continuación.  
  
 **Nota:** <xref:System.Windows.Documents.FlowDocument> es necesario para directamente el contenido del flujo host, por lo que todos estos controles de vista utilizan un <xref:System.Windows.Documents.FlowDocument> para habilitar el hospedaje de contenido de flujo.  
  
### <a name="flowdocumentreader"></a>FlowDocumentReader  
 <xref:System.Windows.Controls.FlowDocumentReader>incluye características que permiten al usuario elegir dinámicamente entre distintos modos de visualización, incluido un modo de visualización de página (una página a la vez), dos página a la vez (formato de lectura de libro) modo y un modo desplazamiento continuo de visualización (sin límite). Para obtener más información acerca de estos modos de visualización, consulte <xref:System.Windows.Controls.FlowDocumentReaderViewingMode>. Si no necesita la capacidad de cambiar dinámicamente entre distintos modos de visualización, <xref:System.Windows.Controls.FlowDocumentPageViewer> y <xref:System.Windows.Controls.FlowDocumentScrollViewer> proporcionar dinámico más ligeros los visores de contenido que se corrigen en un modo de visualización concreto.  
  
### <a name="flowdocumentpageviewer-and-flowdocumentscrollviewer"></a>FlowDocumentPageViewer y FlowDocumentScrollViewer  
 <xref:System.Windows.Controls.FlowDocumentPageViewer>Muestra el contenido de página en tiempo modo de visualización, mientras <xref:System.Windows.Controls.FlowDocumentScrollViewer> muestra el contenido en el modo de desplazamiento continuo. Ambos <xref:System.Windows.Controls.FlowDocumentPageViewer> y <xref:System.Windows.Controls.FlowDocumentScrollViewer> son fijos para un modo de visualización concreto. Comparar con <xref:System.Windows.Controls.FlowDocumentReader>, que incluye características que permiten al usuario elegir dinámicamente entre distintos modos de visualización (proporcionados por el <xref:System.Windows.Controls.FlowDocumentReaderViewingMode> enumeración), pero a costa de que se va a más recursos de forma intensiva que <xref:System.Windows.Controls.FlowDocumentPageViewer> o <xref:System.Windows.Controls.FlowDocumentScrollViewer>.  
  
 De manera predeterminada, siempre se muestra una barra de desplazamiento vertical y una barra de desplazamiento horizontal se vuelve visible cuando es necesario. El valor predeterminado interfaz de usuario para <xref:System.Windows.Controls.FlowDocumentScrollViewer> no incluye una barra de herramientas; sin embargo, la <xref:System.Windows.Controls.FlowDocumentScrollViewer.IsToolBarVisible%2A> propiedad puede utilizarse para habilitar una barra de herramientas integrada.  
  
### <a name="richtextbox"></a>RichTextBox  
 Usa un <xref:System.Windows.Controls.RichTextBox> cuando desee permitir al usuario editar el contenido del flujo. Por ejemplo, si desea crear un editor que permite a los usuarios manipular cosas como tablas, cursiva y negrita formato, etcetera, usaría un <xref:System.Windows.Controls.RichTextBox>. Vea [RichTextBox Overview](../../../../docs/framework/wpf/controls/richtextbox-overview.md) para obtener más información.  
  
 **Nota:** de flujo de contenido dentro de un <xref:System.Windows.Controls.RichTextBox> no se comportan exactamente igual que el contenido del flujo contenido en otros controles. Por ejemplo, no hay ninguna columna en un <xref:System.Windows.Controls.RichTextBox> y, por tanto, no automático cambiar el tamaño de comportamiento. Asimismo, las características normalmente integradas de contenido dinámico como la búsqueda, ver modo, la navegación en páginas y el zoom no están disponibles dentro de un <xref:System.Windows.Controls.RichTextBox>.  
  
<a name="creating_flow_content"></a>   
## <a name="creating-flow-content"></a>Crear contenido dinámico  
 El contenido del flujo puede ser complejo, estando compuesto por varios elementos como texto, imágenes, tablas e incluso <xref:System.Windows.UIElement> deriva clases como controles. Para entender cómo crear contenido dinámico complejo, los puntos siguientes son fundamentales:  
  
-   **Clases relacionadas con el flujo**: cada clase que se utiliza en el contenido dinámico tiene un propósito específico. Además, la relación jerárquica entre las clases dinámicas le ayuda a comprender cómo se utilizan. Por ejemplo, las clases derivadas de la <xref:System.Windows.Documents.Block> clase se utilizan para contener otros objetos, mientras que las clases derivadas de <xref:System.Windows.Documents.Inline> contienen objetos que se muestran.  
  
-   **Esquema de contenido**: un documento dinámico puede requerir un número importante de elementos anidados. El esquema de contenido especifica las relaciones posibles entre elementos primarios y secundarios.  
  
 En las secciones siguientes se repasará cada una de estas áreas con más detalle.  
  
<a name="flow_related_classes"></a>   
## <a name="flow-related-classes"></a>Clases relacionadas con el flujo  
 En el diagrama siguiente se muestran los objetos más utilizados con el contenido dinámico:  
  
 ![Diagrama: Jerarquía de clases de elementos de contenido dinámico](../../../../docs/framework/wpf/advanced/media/flow-class-hierarchy.png "Flow_Class_Hierarchy")  
  
 A los efectos del contenido dinámico, hay dos categorías importantes:  
  
1.  **Clases derivadas de Block**: también denominadas "elementos de contenido de Block" o simplemente "elementos Block". Elementos que se heredan de <xref:System.Windows.Documents.Block> puede utilizarse para agrupar elementos bajo un elemento primario común o para aplicar atributos comunes a un grupo.  
  
2.  **Clases derivadas de Inline**: también denominadas "elementos de contenido de Inline" o simplemente "elementos de Inline". Elementos que se heredan de <xref:System.Windows.Documents.Inline> se encuentran dentro de un elemento de bloque o de otro elemento en línea. Los elementos Inline se utilizan a menudo como contenedor directo del contenido que se representa en la pantalla. Por ejemplo, un <xref:System.Windows.Documents.Paragraph> (elemento de bloque) puede contener una <xref:System.Windows.Documents.Run> (elemento Inline), pero la <xref:System.Windows.Documents.Run> realmente contiene el texto que se presenta en la pantalla.  
  
 Cada clase de estas dos categorías se describe brevemente a continuación.  
  
### <a name="block-derived-classes"></a>Clases derivadas de Block  
 **Paragraph**  
  
 <xref:System.Windows.Documents.Paragraph>se utiliza normalmente para agrupar el contenido en un párrafo. El uso más sencillo y común de Paragraph es crear un párrafo de texto.  
  
 [!code-xaml[FlowOvwSnippets_snip#ParagraphExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/ParagraphExample.xaml#paragraphexamplewholepage)]  
  
 [!code-csharp[FlowOvwSnippets_procedural_snip#ParagraphCodeOnlyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/ParagraphExample.cs#paragraphcodeonlyexamplewholepage)]
 [!code-vb[FlowOvwSnippets_procedural_snip#ParagraphCodeOnlyExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/ParagraphExample.vb#paragraphcodeonlyexamplewholepage)]  
  
 Sin embargo, también puede contener otros elementos inline derivados, como verá a continuación. 
  
 **Sección**  
  
 <xref:System.Windows.Documents.Section>solo se usa para contener otros <xref:System.Windows.Documents.Block>-elementos derivados. No aplica ningún formato predeterminado a los elementos que contiene. Sin embargo, cualquier propiedad valores establecidos en un <xref:System.Windows.Documents.Section> se aplica a sus elementos secundarios. Una sección permite iterar mediante programación en su colección secundaria. <xref:System.Windows.Documents.Section>se utiliza de forma similar a la \<DIV > etiqueta en HTML.  
  
 En el ejemplo siguiente, se definen tres párrafos bajo una <xref:System.Windows.Documents.Section>. La sección tiene un <xref:System.Windows.Documents.TextElement.Background%2A> valor de la propiedad de color rojo, por lo tanto, el color de fondo de los párrafos también está en rojo.  
  
 [!code-xaml[FlowOvwSnippets_snip#SectionExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SectionExample.xaml#sectionexamplewholepage)]  
  
 [!code-csharp[FlowOvwSnippets_procedural_snip#SectionCodeOnlyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/SectionExample.cs#sectioncodeonlyexamplewholepage)]
 [!code-vb[FlowOvwSnippets_procedural_snip#SectionCodeOnlyExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/SectionExample.vb#sectioncodeonlyexamplewholepage)]  
  
 **BlockUIContainer**  
  
 <xref:System.Windows.Documents.BlockUIContainer>permite <xref:System.Windows.UIElement> elementos (es decir, un <xref:System.Windows.Controls.Button>) incrustado en contenido dinámico derivado de bloque. <xref:System.Windows.Documents.InlineUIContainer>(ver abajo) se utiliza para incrustar <xref:System.Windows.UIElement> elementos de contenido dinámico derivado insertado. <xref:System.Windows.Documents.BlockUIContainer>y <xref:System.Windows.Documents.InlineUIContainer> son importantes porque no hay ninguna otra manera de usar un <xref:System.Windows.UIElement> en flujo de contenido a menos que se encuentra dentro de uno de estos dos elementos.  
  
 En el ejemplo siguiente se muestra cómo utilizar el <xref:System.Windows.Documents.BlockUIContainer> elemento para hospedar <xref:System.Windows.UIElement> objetos dentro del contenido dinámico.  
  
 [!code-xaml[SpanSnippets#_BlockUIXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml#_blockuixaml)]  
  
 En la ilustración siguiente, se muestra cómo se representa este ejemplo.  
  
 ![Captura de pantalla: UIElement insertado en contenido dinámico](../../../../docs/framework/wpf/advanced/media/blockuicontainer.png "BlockUIContainer")  
  
 **List**  
  
 <xref:System.Windows.Documents.List>se utiliza para crear una lista con viñeta o numérica. Establecer el <xref:System.Windows.Documents.List.MarkerStyle%2A> propiedad a un <xref:System.Windows.TextMarkerStyle> valor de enumeración para determinar el estilo de la lista. En el ejemplo siguiente se muestra cómo crear una lista sencilla.  
  
 [!code-xaml[FlowOvwSnippets_snip#ListExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/ListExample.xaml#listexamplewholepage)]  
  
 [!code-csharp[FlowOvwSnippets_procedural_snip#ListCodeOnlyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/ListExample.cs#listcodeonlyexamplewholepage)]
 [!code-vb[FlowOvwSnippets_procedural_snip#ListCodeOnlyExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/ListExample.vb#listcodeonlyexamplewholepage)]  
  
 **Nota:** <xref:System.Windows.Documents.List> es el único elemento de flujo que usa el <xref:System.Windows.Documents.ListItemCollection> para administrar los elementos secundarios.  
  
 **Table**  
  
 <xref:System.Windows.Documents.Table>se utiliza para crear una tabla. <xref:System.Windows.Documents.Table>es similar a la <xref:System.Windows.Controls.Grid> elemento pero tiene más capacidades y, por lo tanto, requiere mayor consumo de recursos. Dado que <xref:System.Windows.Controls.Grid> es un <xref:System.Windows.UIElement>, no se puede usar en el contenido dinámico a menos que se encuentra en un <xref:System.Windows.Documents.BlockUIContainer> o <xref:System.Windows.Documents.InlineUIContainer>. Para obtener más información sobre <xref:System.Windows.Documents.Table>, consulte [información general de la tabla](../../../../docs/framework/wpf/advanced/table-overview.md).  
  
### <a name="inline-derived-classes"></a>Clases derivadas de Inline  
 **Run**  
  
 <xref:System.Windows.Documents.Run>se usa para contener texto sin formato. Podría pensarse que <xref:System.Windows.Documents.Run> objetos que se usan ampliamente en contenido dinámico. Sin embargo, en el marcado, <xref:System.Windows.Documents.Run> elementos no se debe usar explícitamente. <xref:System.Windows.Documents.Run>es necesario que se utilizará al crear o manipular documentos dinámicos mediante código. Por ejemplo, en el marcado debajo de la primera <xref:System.Windows.Documents.Paragraph> especifica la <xref:System.Windows.Documents.Run> elemento explícitamente mientras que la segunda no. Ambos párrafos generan el mismo resultado.  
  
 [!code-xaml[FlowOvwSnippets_snip#RunExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/RunSnippetsExample.xaml#runexample1)]  
  
 **Nota:** a partir de la [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)], <xref:System.Windows.Documents.Run.Text%2A> propiedad de la <xref:System.Windows.Documents.Run> objeto es una propiedad de dependencia. Puede enlazar la <xref:System.Windows.Documents.Run.Text%2A> propiedad a datos de origen, como un <xref:System.Windows.Controls.TextBlock>. El <xref:System.Windows.Documents.Run.Text%2A> propiedad es totalmente compatible con enlace unidireccional. El <xref:System.Windows.Documents.Run.Text%2A> propiedad también es compatible con un enlace bidireccional, salvo por <xref:System.Windows.Controls.RichTextBox>. Para obtener un ejemplo, consulta <xref:System.Windows.Documents.Run.Text%2A?displayProperty=nameWithType>.  
  
 **Span**  
  
 <xref:System.Windows.Documents.Span>Agrupa otros elementos de contenido en línea. No se aplica ninguna representación inherente al contenido dentro de un <xref:System.Windows.Documents.Span> elemento. Sin embargo, los elementos que heredan de <xref:System.Windows.Documents.Span> incluidos <xref:System.Windows.Documents.Hyperlink>, <xref:System.Windows.Documents.Bold>, <xref:System.Windows.Documents.Italic> y <xref:System.Windows.Documents.Underline> aplicar formato al texto.  
  
 A continuación se muestra un ejemplo de un <xref:System.Windows.Documents.Span> que se usa para incluir contenido inline, incluyendo el texto, un <xref:System.Windows.Documents.Bold> elemento y un <xref:System.Windows.Controls.Button>.  
  
 [!code-xaml[FlowOvwSnippets_snip#SpanExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SpanExample.xaml#spanexamplewholepage)]  
  
 En la captura de pantalla siguiente se muestra cómo se representa este ejemplo.  
  
 ![Captura de pantalla: Ejemplo de Span representado](../../../../docs/framework/wpf/advanced/media/flow-spanexample.gif "Flow_SpanExample")  
  
 **InlineUIContainer**  
  
 <xref:System.Windows.Documents.InlineUIContainer>permite <xref:System.Windows.UIElement> elementos (es decir, al igual que un control <xref:System.Windows.Controls.Button>) para incrustar en un <xref:System.Windows.Documents.Inline> elemento de contenido. Este elemento es el equivalente inline al <xref:System.Windows.Documents.BlockUIContainer> se ha descrito anteriormente. A continuación se muestra un ejemplo que utiliza <xref:System.Windows.Documents.InlineUIContainer> para insertar un <xref:System.Windows.Controls.Button> en línea en un <xref:System.Windows.Documents.Paragraph>.  
  
 [!code-xaml[FlowOvwSnippets_snip#InlineUIContainerExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/InlineUIContainerExample.xaml#inlineuicontainerexamplewholepage)]  
  
 [!code-csharp[FlowOvwSnippets_procedural_snip#InlineUIContainerCodeOnlyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/InlineUIContainerExample.cs#inlineuicontainercodeonlyexamplewholepage)]
 [!code-vb[FlowOvwSnippets_procedural_snip#InlineUIContainerCodeOnlyExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/InlineUIContainerExample.vb#inlineuicontainercodeonlyexamplewholepage)]  
  
 **Nota:** <xref:System.Windows.Documents.InlineUIContainer> no tienen que usarse explícitamente en el marcado. Si se omite, un <xref:System.Windows.Documents.InlineUIContainer> se creará de todos modos cuando se compila el código.  
  
 **Figure y Floater**  
  
 <xref:System.Windows.Documents.Figure>y <xref:System.Windows.Documents.Floater> se utilizan para insertar contenido en documentos dinámicos con las propiedades de ubicación que pueden personalizar de forma independiente del flujo de contenido principal. <xref:System.Windows.Documents.Figure>o <xref:System.Windows.Documents.Floater> elementos a menudo se usan para resaltar o recalcar partes de contenido, hospedar imágenes auxiliares u otro tipo de contenido dentro del flujo de contenido principal, o flexible insertar contenido como anuncios relacionado.  
  
 En el ejemplo siguiente se muestra cómo incrustar un <xref:System.Windows.Documents.Figure> en un párrafo de texto.  
  
 [!code-xaml[FlowOvwSnippets_snip#FigureExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/FigureExample.xaml#figureexamplewholepage)]  
  
 [!code-csharp[FlowOvwSnippets_procedural_snip#FigureCodeOnlyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/FigureExample.cs#figurecodeonlyexamplewholepage)]
 [!code-vb[FlowOvwSnippets_procedural_snip#FigureCodeOnlyExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/FigureExample.vb#figurecodeonlyexamplewholepage)]  
  
 En la ilustración siguiente se muestra cómo se representa este ejemplo.  
  
 ![Captura de pantalla: Ejemplo de Figure](../../../../docs/framework/wpf/advanced/media/flow-ovw-figure-example.png "Flow_Ovw_Figure_Example")  
  
 <xref:System.Windows.Documents.Figure>y <xref:System.Windows.Documents.Floater> difieren de varias maneras y se utilizan para escenarios diferentes.  
  
 **Figure:**  
  
-   Se pueden determinar su posición: puede establecer sus delimitadores horizontal y vertical para acoplarlo con respecto a la página, el contenido, la columna o el párrafo. También puede usar su <xref:System.Windows.Documents.Figure.HorizontalOffset%2A> y <xref:System.Windows.Documents.Figure.VerticalOffset%2A> propiedades para especificar desplazamientos arbitrarios.  
  
-   Es ajustable a más de una columna: puede establecer <xref:System.Windows.Documents.Figure> alto y ancho en múltiplos de página, el contenido o la columna alto o el ancho. Tenga en cuenta que, en el caso de la página y el contenido, no se permiten múltiplos mayores que 1. Por ejemplo, puede establecer el ancho de un <xref:System.Windows.Documents.Figure> a ser "0,5 page" o "0,25 content" o "columna 2". También puede establecer el alto y ancho en valores absolutos de píxeles.  
  
-   No se paginan: si el contenido dentro de un <xref:System.Windows.Documents.Figure> no cabe en el <xref:System.Windows.Documents.Figure>, se representará el contenido se ajusta y se pierde el contenido restante  
  
 **Floater:**  
  
-   No se puede establecer su posición y se representará en cualquier espacio que pueda estar a su disposición. No se puede establecer el desplazamiento o el anclaje de un <xref:System.Windows.Documents.Floater>.  
  
-   No se deben preverse para más de una columna: de forma predeterminada, <xref:System.Windows.Documents.Floater> tamaños de al menos una columna. Tiene un <xref:System.Windows.Documents.Floater.Width%2A> propiedad que se puede establecer en un valor de píxel absolutas, pero si este valor es mayor que el ancho de una columna, se pasa por alto y el elemento floater tiene un tamaño de una columna. Tamaño a menos de una sola columna estableciendo el ancho en píxeles correcto, pero el tamaño no es relativo a la columna, por lo que "0.5Column" no es una expresión válida para <xref:System.Windows.Documents.Floater> ancho. <xref:System.Windows.Documents.Floater>no tiene ninguna propiedad de alto y es alto no se puede establecer, su alto depende del contenido  
  
-   <xref:System.Windows.Documents.Floater>pagina: si su contenido en el ancho especificado se extiende a más de 1 alto de columna, floater se parte y salta a la columna siguiente, la página siguiente, etcetera.  
  
 <xref:System.Windows.Documents.Figure>es un buen lugar para colocar el contenido independiente en la que desea controlar el tamaño y colocar y esté seguro de que el contenido se ajusta al tamaño especificado. <xref:System.Windows.Documents.Floater>es un buen lugar para incluir más contenido que fluye libre que fluye similar al contenido de la página principal, pero se separa de él.  
  
 **LineBreak**  
  
 <xref:System.Windows.Documents.LineBreak>hace que un salto de línea para que se produzca en el contenido del flujo. El siguiente ejemplo muestra el uso de <xref:System.Windows.Documents.LineBreak>.  
  
 [!code-xaml[FlowOvwSnippets_snip#LineBreakExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/LineBreakExample.xaml#linebreakexamplewholepage)]  
  
 En la captura de pantalla siguiente se muestra cómo se representa este ejemplo.  
  
 ![Captura de pantalla: Ejemplo de LineBreak](../../../../docs/framework/wpf/advanced/media/flow-ovw-linebreakexample.png "Flow_Ovw_LineBreakExample")  
  
### <a name="flow-collection-elements"></a>Elementos de colección dinámica  
 En muchos de los ejemplos anteriores, la <xref:System.Windows.Documents.BlockCollection> y <xref:System.Windows.Documents.InlineCollection> se utilizan para construir mediante programación el contenido del flujo. Por ejemplo, para agregar elementos a un <xref:System.Windows.Documents.Paragraph>, puede utilizar la sintaxis:  
  
 `…`  
  
 `myParagraph.Inlines.Add(new Run("Some text"));`  
  
 `…`  
  
 Esto agrega un <xref:System.Windows.Documents.Run> a la <xref:System.Windows.Documents.InlineCollection> de la <xref:System.Windows.Documents.Paragraph>.  Este es el mismo que la parte implícita <xref:System.Windows.Documents.Run> encontrados en un <xref:System.Windows.Documents.Paragraph> en el marcado:  
  
 `…`  
  
 `<Paragraph>`  
  
 `Some Text`  
  
 `</Paragraph>`  
  
 `…`  
  
 Como un ejemplo del uso de la <xref:System.Windows.Documents.BlockCollection>, en el ejemplo siguiente se crea un nuevo <xref:System.Windows.Documents.Section> y, a continuación, usa el **agregar** método para agregar un nuevo <xref:System.Windows.Documents.Paragraph> a la <xref:System.Windows.Documents.Section> contenido.  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksAdd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksadd)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksAdd](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksadd)]  
  
 Además de agregar elementos a una colección dinámica, también puede quitar elementos.  En el ejemplo siguiente se elimina el último <xref:System.Windows.Documents.Inline> elemento en el <xref:System.Windows.Documents.Span>.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesRemoveLast](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesremovelast)]
 [!code-vb[SpanSnippets#_SpanInlinesRemoveLast](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesremovelast)]  
  
 En el ejemplo siguiente se borra todo el contenido (<xref:System.Windows.Documents.Inline> elementos) de la <xref:System.Windows.Documents.Span>.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesClear](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesclear)]
 [!code-vb[SpanSnippets#_SpanInlinesClear](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesclear)]  
  
 Cuando trabaje con contenido dinámico mediante programación, probablemente utilizará mucho estas colecciones.  
  
 Si un elemento de flujo utiliza un <xref:System.Windows.Documents.InlineCollection> (elementos incorporados) o <xref:System.Windows.Documents.BlockCollection> (bloques) para que contenga su elemento secundario elementos depende del tipo de elementos secundarios (<xref:System.Windows.Documents.Block> o <xref:System.Windows.Documents.Inline>) puede estar contenido en el elemento primario. Las reglas de contención para los elementos de contenido dinámico se resumen en el esquema de contenido en la sección siguiente.  
  
 **Nota:** hay un tercer tipo de colección que se usa con el contenido del flujo, el <xref:System.Windows.Documents.ListItemCollection>, pero esta colección solo se usa con un <xref:System.Windows.Documents.List>. Además, hay varias colecciones que se utilizan con <xref:System.Windows.Documents.Table>. Vea [información general de la tabla](../../../../docs/framework/wpf/advanced/table-overview.md) para obtener más información.  
  
<a name="content_schema"></a>   
## <a name="content-schema"></a>Esquema de contenido  
 Dado el número de los distintos elementos de contenido dinámico, puede resultar abrumador mantener un seguimiento de qué tipo de elementos secundarios puede contener un elemento. En el diagrama siguiente se resumen las reglas de contención para los elementos dinámicos. Las flechas representan las relaciones posibles entre elementos primarios y secundarios.  
  
 ![Diagrama: Esquema de contención de contenido dinámico](../../../../docs/framework/wpf/advanced/media/flow-content-schema.png "Flow_Content_Schema")  
  
 Como puede verse en el diagrama anterior, los elementos secundarios permitidos para un elemento no necesariamente dependen de si se trata de un <xref:System.Windows.Documents.Block> elemento o un <xref:System.Windows.Documents.Inline> elemento. Por ejemplo, un <xref:System.Windows.Documents.Span> (un <xref:System.Windows.Documents.Inline> elemento) solo puede tener <xref:System.Windows.Documents.Inline> los elementos secundarios a un <xref:System.Windows.Documents.Figure> (también una <xref:System.Windows.Documents.Inline> elemento) solo puede tener <xref:System.Windows.Documents.Block> los elementos secundarios. Por tanto, un diagrama es útil para determinar rápidamente qué elemento puede incluirse en otro. Por ejemplo, vamos a usar el diagrama para determinar cómo construir el contenido del flujo de un <xref:System.Windows.Controls.RichTextBox>.  
  
 **1.** A <xref:System.Windows.Controls.RichTextBox> debe contener una <xref:System.Windows.Documents.FlowDocument> que a su vez debe contener un <xref:System.Windows.Documents.Block>-objeto derivado. A continuación, se muestra el segmento correspondiente del diagrama anterior.  
  
 ![Diagrama: reglas de contención de RichTextBox](../../../../docs/framework/wpf/advanced/media/flow-ovw-schemawalkthrough1.png "Flow_Ovw_SchemaWalkThrough1")  
  
 Llegados a este punto, esta es la apariencia que podría tener el marcado.  
  
 [!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough1)]  
  
 **2.** Según el diagrama, hay varios <xref:System.Windows.Documents.Block> elementos que puede elegir incluidos <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.Table>, <xref:System.Windows.Documents.List>, y <xref:System.Windows.Documents.BlockUIContainer> (vea clases derivadas de bloque anteriores). Supongamos que queremos un <xref:System.Windows.Documents.Table>. Según el diagrama anterior, un <xref:System.Windows.Documents.Table> contiene un <xref:System.Windows.Documents.TableRowGroup> que contiene <xref:System.Windows.Documents.TableRow> elementos, que contienen <xref:System.Windows.Documents.TableCell> elementos que contienen un <xref:System.Windows.Documents.Block>-objeto derivado. A continuación se muestra el segmento correspondiente para <xref:System.Windows.Documents.Table> tomado del diagrama anterior.  
  
 ![Diagrama: Esquema de elemento primario&#47;secundario para Table](../../../../docs/framework/wpf/advanced/media/flow-ovw-schemawalkthrough2.png "Flow_Ovw_SchemaWalkThrough2")  
  
 A continuación, se muestra el marcado correspondiente.  
  
 [!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough2)]  
  
 **3.** Una vez más, uno o varios <xref:System.Windows.Documents.Block> requieren debajo de los elementos de un <xref:System.Windows.Documents.TableCell>. Para facilitar el proceso, vamos a colocar texto dentro de la celda. Podemos hacer esto con un <xref:System.Windows.Documents.Paragraph> con un <xref:System.Windows.Documents.Run> elemento. A continuación se muestra los segmentos correspondientes del diagrama que muestra que un <xref:System.Windows.Documents.Paragraph> puede tardar un <xref:System.Windows.Documents.Inline> elemento y que un <xref:System.Windows.Documents.Run> (un <xref:System.Windows.Documents.Inline> elemento) solo se puede tomar el texto sin formato.  
  
 ![Diagrama: Esquema de elemento primario&#47;secundario para Paragraph](../../../../docs/framework/wpf/advanced/media/flow-ovw-schemawalkthrough3.png "Flow_Ovw_SchemaWalkThrough3")  
  
 ![Diagrama: Esquema de elementos primarios/secundarios para Run](../../../../docs/framework/wpf/advanced/media/flow-ovw-schemawalkthrough4.png "Flow_Ovw_SchemaWalkThrough4")  
  
 A continuación se muestra el ejemplo completo en el marcado.  
  
 [!code-xaml[FlowOvwSnippets_snip#SchemaExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SchemaExample.xaml#schemaexamplewholepage)]  
  
<a name="customizing_text"></a>   
## <a name="customizing-text"></a>Personalizar texto  
 En general, el texto es el tipo de contenido más frecuente de un documento dinámico. Aunque los objetos descritos anteriormente pueden utilizarse para controlar la mayoría de los aspectos de cómo se representa el texto, hay otros métodos para personalizar el texto, según se describen en esta sección.  
  
### <a name="text-decorations"></a>Decoraciones de texto  
 Las decoraciones de texto le permiten aplicar efectos de subrayado, línea alta, línea base y tachado al texto (consulte las imágenes siguientes). Estas decoraciones se agregan utilizando la <xref:System.Windows.Documents.Inline.TextDecorations%2A> propiedad expuesto por un número de objetos incluidos <xref:System.Windows.Documents.Inline>, <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Controls.TextBlock>, y <xref:System.Windows.Controls.TextBox>.  
  
 En el ejemplo siguiente se muestra cómo se establece la propiedad <xref:System.Windows.Documents.Paragraph.TextDecorations%2A> de <xref:System.Windows.Documents.Paragraph>.  
  
 [!code-xaml[InlineSnippets#_Paragraph_TextDecXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InlineSnippets/CSharp/Window1.xaml#_paragraph_textdecxaml)]  
  
 [!code-csharp[InlineSnippets#_Paragraph_TextDec](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InlineSnippets/CSharp/Window1.xaml.cs#_paragraph_textdec)]
 [!code-vb[InlineSnippets#_Paragraph_TextDec](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InlineSnippets/visualbasic/window1.xaml.vb#_paragraph_textdec)]  
  
 En la ilustración siguiente, se muestra cómo se representa este ejemplo.  
  
 ![Captura de pantalla: texto con efecto de tachado predeterminado](../../../../docs/framework/wpf/advanced/media/inline-textdec-strike.png "Inline_TextDec_Strike")  
  
 Las ilustraciones siguientes muestran cómo el **suprarrayado**, **previsto**, y **subrayado** decoraciones se representan, respectivamente.  
  
 ![Captura de pantalla: TextDecorator de línea alta](../../../../docs/framework/wpf/advanced/media/inline-textdec-over.png "Inline_TextDec_Over")  
  
 ![Captura de pantalla: Efecto de línea base predeterminada en texto](../../../../docs/framework/wpf/advanced/media/inline-textdec-base.png "Inline_TextDec_Base")  
  
 ![Captura de pantalla: Texto con efecto de subrayado predeterminado](../../../../docs/framework/wpf/advanced/media/inline-textdec-under.png "Inline_TextDec_Under")  
  
### <a name="typography"></a>Tipografía  
 El <xref:System.Windows.Documents.TextElement.Typography%2A> propiedad se expone mediante la mayoría relacionadas con el flujo de contenido inclusión <xref:System.Windows.Documents.TextElement>, <xref:System.Windows.Documents.FlowDocument>, <xref:System.Windows.Controls.TextBlock>, y <xref:System.Windows.Controls.TextBox>. Esta propiedad se utiliza para controlar características/variaciones tipográficas del texto (es decir, versalitas o mayúsculas, superíndices y subíndices, etc.).  
  
 En el ejemplo siguiente se muestra cómo establecer el <xref:System.Windows.Documents.TextElement.Typography%2A> atributo, mediante <xref:System.Windows.Documents.Paragraph> como elemento de ejemplo.  
  
 [!code-xaml[TextElementSnippets#_TextElement_TypogXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextElementSnippets/CSharp/Window1.xaml#_textelement_typogxaml)]  
  
 En la ilustración siguiente, se muestra cómo se representa este ejemplo.  
  
 ![Captura de pantalla: texto con tipografía modificada](../../../../docs/framework/wpf/advanced/media/textelement-typog.png "TextElement_Typog")  
  
 En cambio, en la siguiente ilustración se muestra cómo se representa un ejemplo similar con propiedades tipográficas predeterminadas.  
  
 ![Captura de pantalla: texto con tipografía modificada](../../../../docs/framework/wpf/advanced/media/textelement-typog-default.png "TextElement_Typog_Default")  
  
 En el ejemplo siguiente se muestra cómo establecer el <xref:System.Windows.Controls.TextBox.Typography%2A> propiedad mediante programación.  
  
 [!code-csharp[TextElementSnippets#_TextElement_Typog](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextElementSnippets/CSharp/Window1.xaml.cs#_textelement_typog)]
 [!code-vb[TextElementSnippets#_TextElement_Typog](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextElementSnippets/visualbasic/window1.xaml.vb#_textelement_typog)]  
  
 Vea [tipografía en WPF](../../../../docs/framework/wpf/advanced/typography-in-wpf.md) para obtener más información sobre tipografía.  
  
## <a name="see-also"></a>Vea también  
 [Texto](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)  
 [Tipografía en WPF](../../../../docs/framework/wpf/advanced/typography-in-wpf.md)  
 [Temas de procedimientos](../../../../docs/framework/wpf/advanced/flow-content-elements-how-to-topics.md)  
 [Información general sobre el modelo de contenido de TextElement](../../../../docs/framework/wpf/advanced/textelement-content-model-overview.md)  
 [RichTextBox Overview](../../../../docs/framework/wpf/controls/richtextbox-overview.md) (Introducción a RichTextBox)  
 [Documentos en WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [Información general sobre tablas](../../../../docs/framework/wpf/advanced/table-overview.md)  
 [Información general sobre anotaciones](../../../../docs/framework/wpf/advanced/annotations-overview.md)
