---
title: Información general sobre documentos dinámicos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 'documents [WPF], flow documents [WPF], , '
- ', '
- flow documents [WPF]
ms.assetid: ef236a50-d44f-43c8-ba7c-82b0c733c0b7
ms.openlocfilehash: 082f5bf9f8cdd8e5f44aa74e7b34e03637b5c579
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64663365"
---
# <a name="flow-document-overview"></a>Información general sobre documentos dinámicos
Los documentos dinámicos están diseñados para optimizar su visualización y legibilidad. En lugar de establecer un diseño predefinido, los documentos dinámicos ajustan y redistribuyen dinámicamente su contenido basándose en variables en tiempo de ejecución, como el tamaño de la ventana, la resolución del dispositivo y las preferencias opcionales del usuario. Además, los documentos dinámicos ofrecen características de documento avanzadas, como paginación y columnas. En este tema se proporciona información general sobre los documentos dinámicos y cómo crearlos.  

<a name="what_is_a_flow_document"></a>   
## <a name="what-is-a-flow-document"></a>Qué es un documento dinámico  
 Un documento dinámico está diseñado para "redistribuir el contenido" según el tamaño de la ventana, la resolución del dispositivo y otras variables del entorno. Además, los documentos dinámicos tienen varias características integradas, como la búsqueda, los modos de visualización que optimizan la legibilidad, y la capacidad de cambiar el tamaño y el aspecto de las fuentes. Los documentos dinámicos se utilizan mejor cuando la facilidad de lectura es el escenario principal de consumo del documento. En cambio, los documentos fijos están diseñados para tener una presentación estática. Los documentos fijos son útiles cuando la fidelidad del contenido de origen es esencial. Consulte [documentos en WPF](documents-in-wpf.md) para obtener más información sobre los distintos tipos de documentos.  
  
 En la ilustración siguiente se muestra un ejemplo de documento dinámico visualizado en varias ventanas de tamaños diferentes. A medida que cambia el área de visualización, el contenido se redistribuye para aprovechar mejor el espacio disponible.  
  
 ![Redistribución del contenido de un documento dinámico](./media/edocs-flowdocument.png "eDocs_FlowDocument")  
  
 Tal como se muestra en la imagen anterior, el contenido dinámico puede incluir muchos componentes, como párrafos, listas, imágenes, etc. Estos componentes corresponden a elementos de marcado y objetos en el código de procedimiento. Analizaremos estas clases detalladamente más adelante en el [flujo clases relacionadas](#flow_related_classes) sección de esta introducción. Por ahora, este es un ejemplo de código simple que crea un documento dinámico que consta de un párrafo con texto en negrita y una lista.
  
 [!code-xaml[FlowOvwSnippets_snip#SimpleFlowExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SimpleFlowExample.xaml#simpleflowexamplewholepage)]  
  
 [!code-csharp[FlowOvwSnippets_procedural_snip#SimpleFlowCodeOnlyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/SimpleFlowExample.cs#simpleflowcodeonlyexamplewholepage)]
 [!code-vb[FlowOvwSnippets_procedural_snip#SimpleFlowCodeOnlyExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/SimpleFlowExample.vb#simpleflowcodeonlyexamplewholepage)]  
  
 En la ilustración siguiente se muestra el aspecto de este fragmento de código.  
  
 ![Captura de pantalla: Ejemplo de FlowDocument representado](./media/flow-ovw-first-example.png "Flow_Ovw_First_Example")  
  
 En este ejemplo, el <xref:System.Windows.Controls.FlowDocumentReader> control se usa para hospedar el contenido dinámico. Consulte [tipos de documentos dinámicos](#flow_document_types) para obtener más información sobre los controles que hospedan contenido dinámico. <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.List>, <xref:System.Windows.Documents.ListItem>, y <xref:System.Windows.Documents.Bold> elementos se utilizan para controlar el formato del contenido, según su orden en el marcado. Por ejemplo, el <xref:System.Windows.Documents.Bold> elemento abarca solo parte del texto del párrafo; como resultado, solo esa parte del texto está en negrita. Si ha utilizado HTML, esto le resultará familiar.  
  
 Tal como se muestra en la ilustración anterior, hay varias características integradas en documentos dinámicos:
  
- Buscar: Permite al usuario realizar una búsqueda de texto completo de todo el documento.  
  
- Modo de visualización: El usuario puede seleccionar su modo de visualización preferido como un modo de vista de página única (una página a la vez), dos página a la vez (formato de lectura de libro) modo y un modo de desplazamiento continuo (sin límite) de visualización.  Para obtener más información acerca de estos modos de visualización, consulte <xref:System.Windows.Controls.FlowDocumentReaderViewingMode>.  
  
- Controles de navegación de página: Si el modo de vista del documento utiliza páginas, los controles de navegación de páginas incluyen un botón para ir a la página siguiente (la flecha abajo) o la página anterior (flecha arriba), así como los indicadores para el número de página actual y el número total de páginas. Las páginas también pueden voltearse mediante las teclas de flecha del teclado.  
  
- Zoom: Los controles de zoom permiten al usuario aumentar o disminuir el nivel de zoom haciendo clic en el signo más o menos botones, respectivamente. Los controles de zoom incluyen también un control deslizante para ajustar el nivel de zoom. Para obtener más información, consulta <xref:System.Windows.Controls.FlowDocumentReader.Zoom%2A>.  
  
 Estas características pueden modificarse según el control utilizado para hospedar el contenido dinámico. En la siguiente sección se describen los distintos controles.  
  
<a name="flow_document_types"></a>   
## <a name="flow-document-types"></a>Tipos de documentos dinámicos  
 La visualización del contenido de los documentos dinámicos y cómo aparece depende de qué objeto se utilice para hospedar el contenido dinámico. Hay cuatro controles que admiten la visualización de contenido dinámico: <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, <xref:System.Windows.Controls.RichTextBox>, y <xref:System.Windows.Controls.FlowDocumentScrollViewer>. Estos controles se describen brevemente a continuación.  
  
 **Nota:** <xref:System.Windows.Documents.FlowDocument> es necesario hospedar directamente contenido dinámico, por lo que todos los controles de visualización consumen un <xref:System.Windows.Documents.FlowDocument> para habilitar el hospedaje de contenido dinámico.
  
### <a name="flowdocumentreader"></a>FlowDocumentReader  
 <xref:System.Windows.Controls.FlowDocumentReader> incluye características que permiten al usuario elegir dinámicamente entre distintos modos de visualización, incluido un modo de vista de página única (una página a la vez), dos página a la vez (formato de lectura de libro) modo y un modo de desplazamiento continuo (sin límite) de visualización. Para obtener más información acerca de estos modos de visualización, consulte <xref:System.Windows.Controls.FlowDocumentReaderViewingMode>. Si no tiene la capacidad de cambiar dinámicamente entre distintos modos de visualización, <xref:System.Windows.Controls.FlowDocumentPageViewer> y <xref:System.Windows.Controls.FlowDocumentScrollViewer> proporcionan dinámico más ligeros visores de contenido que se han corregido en un modo de visualización concreto.  
  
### <a name="flowdocumentpageviewer-and-flowdocumentscrollviewer"></a>FlowDocumentPageViewer y FlowDocumentScrollViewer  
 <xref:System.Windows.Controls.FlowDocumentPageViewer> Muestra el contenido en la página en tiempo de modo de vista, mientras <xref:System.Windows.Controls.FlowDocumentScrollViewer> muestra el contenido en modo de desplazamiento continuo. Ambos <xref:System.Windows.Controls.FlowDocumentPageViewer> y <xref:System.Windows.Controls.FlowDocumentScrollViewer> son fijos para un modo de visualización concreto. Comparar con <xref:System.Windows.Controls.FlowDocumentReader>, que incluye características que permiten al usuario elegir dinámicamente entre distintos modos de visualización (tal como lo proporciona el <xref:System.Windows.Controls.FlowDocumentReaderViewingMode> enumeración), a costa de recursos más intensiva que <xref:System.Windows.Controls.FlowDocumentPageViewer> o <xref:System.Windows.Controls.FlowDocumentScrollViewer>.  
  
 De manera predeterminada, siempre se muestra una barra de desplazamiento vertical y una barra de desplazamiento horizontal se vuelve visible cuando es necesario. El valor predeterminado para la interfaz de usuario <xref:System.Windows.Controls.FlowDocumentScrollViewer> no incluye una barra de herramientas; sin embargo, el <xref:System.Windows.Controls.FlowDocumentScrollViewer.IsToolBarVisible%2A> propiedad puede utilizarse para habilitar una barra de herramientas integrada.  
  
### <a name="richtextbox"></a>RichTextBox  
 Usa un <xref:System.Windows.Controls.RichTextBox> cuando desee permitir al usuario editar el contenido dinámico. Por ejemplo, si quisiera crear un editor que le permita al usuario manipular las cosas, como tablas, cursiva y formato, etcetera en negrita, usaría un <xref:System.Windows.Controls.RichTextBox>. Consulte [RichTextBox Overview](../controls/richtextbox-overview.md) para obtener más información.  
  
 **Nota:** El flujo del contenido dentro de un <xref:System.Windows.Controls.RichTextBox> no se comporta exactamente igual que contenido dinámico incluido en otros controles. Por ejemplo, no hay ninguna columna en un <xref:System.Windows.Controls.RichTextBox> y, por tanto, no automático cambiar el tamaño de comportamiento. Además, las características normalmente integradas de contenido dinámico, como búsqueda, zoom, navegación de páginas y el modo de visualización no están disponibles en un <xref:System.Windows.Controls.RichTextBox>.  
  
<a name="creating_flow_content"></a>   
## <a name="creating-flow-content"></a>Crear contenido dinámico  
 Contenido dinámico puede ser complejo, que consta de varios elementos, como texto, imágenes, tablas e incluso <xref:System.Windows.UIElement> derivadas de clases como controles. Para entender cómo crear contenido dinámico complejo, los puntos siguientes son fundamentales:  
  
- **Las clases relacionadas con el flujo**: Cada clase que se usa en el contenido dinámico tiene un propósito específico. Además, la relación jerárquica entre las clases dinámicas le ayuda a comprender cómo se utilizan. Por ejemplo, las clases derivadas de la <xref:System.Windows.Documents.Block> la clase se utilizan para contener otros objetos, mientras que las clases derivadas de <xref:System.Windows.Documents.Inline> contienen objetos que se muestran.  
  
- **Esquema de contenido**: Un documento dinámico puede requerir un número importante de elementos anidados. El esquema de contenido especifica las relaciones posibles entre elementos primarios y secundarios.  
  
 En las secciones siguientes se repasará cada una de estas áreas con más detalle.  
  
<a name="flow_related_classes"></a>   
## <a name="flow-related-classes"></a>Clases relacionadas con el flujo  
 En el diagrama siguiente se muestran los objetos más utilizados con el contenido dinámico:  
  
 ![Diagrama: Flujo de jerarquía de clases de elemento de contenido](./media/flow-class-hierarchy.png "Flow_Class_Hierarchy")  
  
 A los efectos del contenido dinámico, hay dos categorías importantes:  
  
1. **Las clases derivadas de Block**: También se denomina "Elementos de contenido de bloque" o simplemente "elementos Block". Los elementos que heredan de <xref:System.Windows.Documents.Block> puede utilizarse para agrupar elementos bajo un elemento primario común o para aplicar atributos comunes a un grupo.  
  
2. **Clases derivadas de inline**: También se denomina "Elementos de contenido en línea" o simplemente "elementos de Inline". Los elementos que heredan de <xref:System.Windows.Documents.Inline> se encuentran dentro de un elemento de bloque o de otro elemento Inline. Los elementos Inline se utilizan a menudo como contenedor directo del contenido que se representa en la pantalla. Por ejemplo, un <xref:System.Windows.Documents.Paragraph> (elemento Block) puede contener un <xref:System.Windows.Documents.Run> (elemento Inline), pero el <xref:System.Windows.Documents.Run> realmente contiene el texto que se representa en la pantalla.  
  
 Cada clase de estas dos categorías se describe brevemente a continuación.  
  
### <a name="block-derived-classes"></a>Clases derivadas de Block  
 **Paragraph**  
  
 <xref:System.Windows.Documents.Paragraph> se utiliza normalmente para agrupar el contenido en un párrafo. El uso más sencillo y común de Paragraph es crear un párrafo de texto.  
  
 [!code-xaml[FlowOvwSnippets_snip#ParagraphExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/ParagraphExample.xaml#paragraphexamplewholepage)]  
  
 [!code-csharp[FlowOvwSnippets_procedural_snip#ParagraphCodeOnlyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/ParagraphExample.cs#paragraphcodeonlyexamplewholepage)]
 [!code-vb[FlowOvwSnippets_procedural_snip#ParagraphCodeOnlyExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/ParagraphExample.vb#paragraphcodeonlyexamplewholepage)]  
  
 Sin embargo, también puede contener otros elementos derivados de inline, como verá a continuación. 
  
 **Sección**  
  
 <xref:System.Windows.Documents.Section> solo se usa para contener otros <xref:System.Windows.Documents.Block>-elementos derivados. No aplica ningún formato predeterminado a los elementos que contiene. Sin embargo, cualquier propiedad valores establecidos en un <xref:System.Windows.Documents.Section> se aplica a sus elementos secundarios. Una sección permite iterar mediante programación en su colección secundaria. <xref:System.Windows.Documents.Section> se utiliza de forma similar a la \<DIV > etiquetas en HTML.  
  
 En el ejemplo siguiente, se definen tres párrafos bajo una <xref:System.Windows.Documents.Section>. La sección tiene un <xref:System.Windows.Documents.TextElement.Background%2A> valor de propiedad de color rojo, por lo tanto, el color de fondo de los párrafos también será rojo.  
  
 [!code-xaml[FlowOvwSnippets_snip#SectionExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SectionExample.xaml#sectionexamplewholepage)]  
  
 [!code-csharp[FlowOvwSnippets_procedural_snip#SectionCodeOnlyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/SectionExample.cs#sectioncodeonlyexamplewholepage)]
 [!code-vb[FlowOvwSnippets_procedural_snip#SectionCodeOnlyExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/SectionExample.vb#sectioncodeonlyexamplewholepage)]  
  
 **BlockUIContainer**  
  
 <xref:System.Windows.Documents.BlockUIContainer> permite <xref:System.Windows.UIElement> elementos (es decir, un <xref:System.Windows.Controls.Button>) incrustado en contenido dinámico derivado de bloque. <xref:System.Windows.Documents.InlineUIContainer> (ver abajo) se utiliza para incrustar <xref:System.Windows.UIElement> elementos de contenido dinámico derivado de inline. <xref:System.Windows.Documents.BlockUIContainer> y <xref:System.Windows.Documents.InlineUIContainer> son importantes porque no hay ninguna otra manera de usar un <xref:System.Windows.UIElement> en flujo de contenido, salvo que está contenida dentro de uno de estos dos elementos.  
  
 El ejemplo siguiente muestra cómo usar el <xref:System.Windows.Documents.BlockUIContainer> elemento host <xref:System.Windows.UIElement> objetos dentro del contenido dinámico.  
  
 [!code-xaml[SpanSnippets#_BlockUIXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml#_blockuixaml)]  
  
 En la siguiente ilustración se muestra cómo se representa este ejemplo:  
  
 ![Captura de pantalla que muestra un control UIElement incrustado en contenido dinámico.](./media/flow-document-overview/embedded-blockuicontainer.png)  
  
 **List**  
  
 <xref:System.Windows.Documents.List> se utiliza para crear una lista con viñeta o numérica. Establecer el <xref:System.Windows.Documents.List.MarkerStyle%2A> propiedad a un <xref:System.Windows.TextMarkerStyle> valor de enumeración para determinar el estilo de la lista. En el ejemplo siguiente se muestra cómo crear una lista sencilla.  
  
 [!code-xaml[FlowOvwSnippets_snip#ListExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/ListExample.xaml#listexamplewholepage)]  
  
 [!code-csharp[FlowOvwSnippets_procedural_snip#ListCodeOnlyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/ListExample.cs#listcodeonlyexamplewholepage)]
 [!code-vb[FlowOvwSnippets_procedural_snip#ListCodeOnlyExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/ListExample.vb#listcodeonlyexamplewholepage)]  
  
 **Nota:** <xref:System.Windows.Documents.List> es el único elemento de flujo que usa el <xref:System.Windows.Documents.ListItemCollection> para administrar los elementos secundarios.  
  
 **Table**  
  
 <xref:System.Windows.Documents.Table> se usa para crear una tabla. <xref:System.Windows.Documents.Table> es similar a la <xref:System.Windows.Controls.Grid> elemento pero tiene más funciones y, por lo tanto, requiere mayor consumo de recursos. Dado que <xref:System.Windows.Controls.Grid> es un <xref:System.Windows.UIElement>, no puede usarse en el contenido dinámico, a menos que se encuentra en un <xref:System.Windows.Documents.BlockUIContainer> o <xref:System.Windows.Documents.InlineUIContainer>. Para obtener más información sobre <xref:System.Windows.Documents.Table>, consulte [información general sobre tablas](table-overview.md).  
  
### <a name="inline-derived-classes"></a>Clases derivadas de Inline  
 **Run**  
  
 <xref:System.Windows.Documents.Run> se usa para contener texto sin formato. Es de esperar <xref:System.Windows.Documents.Run> objetos que se usan ampliamente en el flujo del contenido. Sin embargo, en el marcado, <xref:System.Windows.Documents.Run> elementos no son necesarios para utilizar explícitamente. <xref:System.Windows.Documents.Run> se requiere que se utilizará al crear o manipular los documentos dinámicos mediante código. Por ejemplo, en el marcado siguiente, la primera <xref:System.Windows.Documents.Paragraph> especifica la <xref:System.Windows.Documents.Run> elemento explícitamente mientras que la segunda no. Ambos párrafos generan el mismo resultado.  
  
 [!code-xaml[FlowOvwSnippets_snip#RunExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/RunSnippetsExample.xaml#runexample1)]  
  
 **Nota:**  A partir de la [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)], <xref:System.Windows.Documents.Run.Text%2A> propiedad de la <xref:System.Windows.Documents.Run> objeto es una propiedad de dependencia. Puede enlazar el <xref:System.Windows.Documents.Run.Text%2A> propiedad a datos de origen, como un <xref:System.Windows.Controls.TextBlock>. El <xref:System.Windows.Documents.Run.Text%2A> propiedad totalmente compatible con el enlace unidireccional. El <xref:System.Windows.Documents.Run.Text%2A> propiedad también es compatible con un enlace bidireccional, excepto <xref:System.Windows.Controls.RichTextBox>. Para obtener un ejemplo, consulte <xref:System.Windows.Documents.Run.Text%2A?displayProperty=nameWithType>.  
  
 **Span**  
  
 <xref:System.Windows.Documents.Span> Agrupa otros elementos de contenido en línea. No se aplica ninguna representación inherente al contenido dentro de un <xref:System.Windows.Documents.Span> elemento. Sin embargo, los elementos que heredan de <xref:System.Windows.Documents.Span> incluidos <xref:System.Windows.Documents.Hyperlink>, <xref:System.Windows.Documents.Bold>, <xref:System.Windows.Documents.Italic> y <xref:System.Windows.Documents.Underline> aplicar formato al texto.  
  
 A continuación es un ejemplo de un <xref:System.Windows.Documents.Span> que se usa para incluir contenido inline, incluido el texto, un <xref:System.Windows.Documents.Bold> elemento y un <xref:System.Windows.Controls.Button>.  
  
 [!code-xaml[FlowOvwSnippets_snip#SpanExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SpanExample.xaml#spanexamplewholepage)]  
  
 En la captura de pantalla siguiente se muestra cómo se representa este ejemplo.  
  
 ![Captura de pantalla: Ejemplo de Span representado](./media/flow-spanexample.gif "Flow_SpanExample")  
  
 **InlineUIContainer**  
  
 <xref:System.Windows.Documents.InlineUIContainer> permite <xref:System.Windows.UIElement> elementos (es decir, como un control <xref:System.Windows.Controls.Button>) incrustado en un <xref:System.Windows.Documents.Inline> elemento de contenido. Este elemento es el equivalente inline al <xref:System.Windows.Documents.BlockUIContainer> se ha descrito anteriormente. A continuación se presenta un ejemplo que usa <xref:System.Windows.Documents.InlineUIContainer> para insertar un <xref:System.Windows.Controls.Button> en línea en un <xref:System.Windows.Documents.Paragraph>.  
  
 [!code-xaml[FlowOvwSnippets_snip#InlineUIContainerExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/InlineUIContainerExample.xaml#inlineuicontainerexamplewholepage)]  
  
 [!code-csharp[FlowOvwSnippets_procedural_snip#InlineUIContainerCodeOnlyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/InlineUIContainerExample.cs#inlineuicontainercodeonlyexamplewholepage)]
 [!code-vb[FlowOvwSnippets_procedural_snip#InlineUIContainerCodeOnlyExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/InlineUIContainerExample.vb#inlineuicontainercodeonlyexamplewholepage)]  
  
 **Nota:** <xref:System.Windows.Documents.InlineUIContainer> no tienen que usarse explícitamente en el marcado. Si se omite, un <xref:System.Windows.Documents.InlineUIContainer> se creará de todos modos cuando se compila el código.  
  
 **Figure y Floater**  
  
 <xref:System.Windows.Documents.Figure> y <xref:System.Windows.Documents.Floater> se utilizan para insertar contenido en documentos dinámicos con propiedades de colocación que pueden personalizarse independientemente del flujo principal de contenido. <xref:System.Windows.Documents.Figure> o <xref:System.Windows.Documents.Floater> elementos se utilizan a menudo para resaltar o recalcar partes de contenido, para hospedar imágenes auxiliares u otro contenido dentro del flujo de contenido principal, o insertar escasamente relacionados con contenido como anuncios.  
  
 El ejemplo siguiente muestra cómo insertar un <xref:System.Windows.Documents.Figure> en un párrafo de texto.  
  
 [!code-xaml[FlowOvwSnippets_snip#FigureExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/FigureExample.xaml#figureexamplewholepage)]  
  
 [!code-csharp[FlowOvwSnippets_procedural_snip#FigureCodeOnlyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/FigureExample.cs#figurecodeonlyexamplewholepage)]
 [!code-vb[FlowOvwSnippets_procedural_snip#FigureCodeOnlyExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/FigureExample.vb#figurecodeonlyexamplewholepage)]  
  
 En la ilustración siguiente se muestra cómo se representa este ejemplo.  
  
 ![Captura de pantalla: Ejemplo de figura](./media/flow-ovw-figure-example.png "Flow_Ovw_Figure_Example")  
  
 <xref:System.Windows.Documents.Figure> y <xref:System.Windows.Documents.Floater> difieren de varias maneras y se utilizan para diferentes escenarios.  
  
 **Figure:**  
  
- Se pueden colocar: Puede establecer sus delimitadores horizontal y vertical para acoplarlo con respecto a la página, el contenido, la columna o el párrafo. También puede usar su <xref:System.Windows.Documents.Figure.HorizontalOffset%2A> y <xref:System.Windows.Documents.Figure.VerticalOffset%2A> propiedades para especificar desplazamientos arbitrarios.  
  
- Es ajustable a más de una columna: Puede establecer <xref:System.Windows.Documents.Figure> alto y ancho en múltiplos de página, contenido o la columna alto o ancho. Tenga en cuenta que, en el caso de la página y el contenido, no se permiten múltiplos mayores que 1. Por ejemplo, puede establecer el ancho de un <xref:System.Windows.Documents.Figure> sea "0.5 page" o "0.25 content" o "2 Column". También puede establecer el alto y ancho en valores absolutos de píxeles.  
  
- No se pagina: Si el contenido dentro de un <xref:System.Windows.Documents.Figure> no cabe en el <xref:System.Windows.Documents.Figure>, se representará el contenido que quepa y se pierde el resto del contenido  
  
 **Floater:**  
  
- No se puede establecer su posición y se representará en cualquier espacio que pueda estar a su disposición. No se puede establecer el desplazamiento ni el delimitador un <xref:System.Windows.Documents.Floater>.  
  
- No puede cambiarse el tamaño a más de una columna: De forma predeterminada, <xref:System.Windows.Documents.Floater> tamaños de al menos una columna. Tiene un <xref:System.Windows.Documents.Floater.Width%2A> propiedad que se puede establecer en un valor de píxel absolutas, pero si este valor es mayor que el ancho de una columna, se pasa por alto y el elemento floater tiene un tamaño de una columna. Tamaño en menos de una columna, establezca el ancho en píxeles correcto, pero el ajuste de tamaño no es relativo a la columna, por lo que "0.5Column" no es una expresión válida para <xref:System.Windows.Documents.Floater> ancho. <xref:System.Windows.Documents.Floater> no tiene ninguna propiedad de alto y es alto no se puede establecer, su alto depende del contenido  
  
- <xref:System.Windows.Documents.Floater> pagina: Si su contenido en el ancho especificado se extiende a más de 1 columna alto, floater se parte y salta a la columna siguiente, la página siguiente, etcetera.  
  
 <xref:System.Windows.Documents.Figure> es un buen lugar para colocar contenido independiente donde desee controlar el tamaño y posición y esté seguro de que el contenido se ajustará al tamaño especificado. <xref:System.Windows.Documents.Floater> es un buen lugar para colocar el contenido más libremente y de manera que fluye similar al contenido de la página principal, pero es independiente de este.  
  
 **LineBreak**  
  
 <xref:System.Windows.Documents.LineBreak> provoca un salto de línea que se produzca en el contenido dinámico. El siguiente ejemplo muestra el uso de <xref:System.Windows.Documents.LineBreak>.  
  
 [!code-xaml[FlowOvwSnippets_snip#LineBreakExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/LineBreakExample.xaml#linebreakexamplewholepage)]  
  
 En la captura de pantalla siguiente se muestra cómo se representa este ejemplo.  
  
 ![Captura de pantalla: Ejemplo de LineBreak](./media/flow-ovw-linebreakexample.png "Flow_Ovw_LineBreakExample")  
  
### <a name="flow-collection-elements"></a>Elementos de colección dinámica  
 En muchos de los ejemplos anteriores, el <xref:System.Windows.Documents.BlockCollection> y <xref:System.Windows.Documents.InlineCollection> se usan para crear contenido dinámico mediante programación. Por ejemplo, para agregar elementos a un <xref:System.Windows.Documents.Paragraph>, puede usar la sintaxis:  
  
 `…`  
  
 `myParagraph.Inlines.Add(new Run("Some text"));`  
  
 `…`  
  
 Esto agrega un <xref:System.Windows.Documents.Run> a la <xref:System.Windows.Documents.InlineCollection> de la <xref:System.Windows.Documents.Paragraph>.  Esto equivale a implícito <xref:System.Windows.Documents.Run> se encuentra dentro de un <xref:System.Windows.Documents.Paragraph> en el marcado:  
  
 `…`  
  
 `<Paragraph>`  
  
 `Some Text`  
  
 `</Paragraph>`  
  
 `…`  
  
 Como un ejemplo del uso de la <xref:System.Windows.Documents.BlockCollection>, en el ejemplo siguiente se crea un nuevo <xref:System.Windows.Documents.Section> y, a continuación, usa el **agregar** método para agregar un nuevo <xref:System.Windows.Documents.Paragraph> a la <xref:System.Windows.Documents.Section> contenido.  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksAdd](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksadd)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksAdd](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksadd)]  
  
 Además de agregar elementos a una colección dinámica, también puede quitar elementos.  En el ejemplo siguiente se elimina la última <xref:System.Windows.Documents.Inline> elemento en el <xref:System.Windows.Documents.Span>.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesremovelast)]
 [!code-vb[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesremovelast)]  
  
 El siguiente ejemplo borra todo el contenido (<xref:System.Windows.Documents.Inline> elementos) desde el <xref:System.Windows.Documents.Span>.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesClear](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesclear)]
 [!code-vb[SpanSnippets#_SpanInlinesClear](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesclear)]  
  
 Cuando trabaje con contenido dinámico mediante programación, probablemente utilizará mucho estas colecciones.  
  
 Si un elemento dinámico utilice un <xref:System.Windows.Documents.InlineCollection> (inline) o <xref:System.Windows.Documents.BlockCollection> (bloques) para que contenga su elemento secundario elementos depende del tipo de elementos secundarios (<xref:System.Windows.Documents.Block> o <xref:System.Windows.Documents.Inline>) puede estar contenido en el elemento primario. Las reglas de contención para los elementos de contenido dinámico se resumen en el esquema de contenido en la sección siguiente.  
  
 **Nota:** Hay un tercer tipo de colección que se usa con contenido dinámico, el <xref:System.Windows.Documents.ListItemCollection>, pero esta colección solo se usa con un <xref:System.Windows.Documents.List>. Además, hay varias colecciones que se utiliza con <xref:System.Windows.Documents.Table>. Consulte [información general sobre tablas](table-overview.md) para obtener más información.  
  
<a name="content_schema"></a>   
## <a name="content-schema"></a>Esquema de contenido  
 Dado el número de los distintos elementos de contenido dinámico, puede resultar abrumador mantener un seguimiento de qué tipo de elementos secundarios puede contener un elemento. En el diagrama siguiente se resumen las reglas de contención para los elementos dinámicos. Las flechas representan las relaciones posibles entre elementos primarios y secundarios.  
  
 ![Diagrama: Esquema de contención de contenido dinámico](./media/flow-content-schema.png "Flow_Content_Schema")  
  
 Como puede verse en el diagrama anterior, los elementos secundarios de un elemento no se vienen determinados necesariamente por si es un <xref:System.Windows.Documents.Block> elemento o un <xref:System.Windows.Documents.Inline> elemento. Por ejemplo, un <xref:System.Windows.Documents.Span> (un <xref:System.Windows.Documents.Inline> elemento) solo puede tener <xref:System.Windows.Documents.Inline> elementos secundarios mientras un <xref:System.Windows.Documents.Figure> (también una <xref:System.Windows.Documents.Inline> elemento) solo puede tener <xref:System.Windows.Documents.Block> elementos secundarios. Por tanto, un diagrama es útil para determinar rápidamente qué elemento puede incluirse en otro. Por ejemplo, vamos a usar el diagrama para determinar cómo construir el contenido dinámico de un <xref:System.Windows.Controls.RichTextBox>.  
  
 **1.** Un <xref:System.Windows.Controls.RichTextBox> debe contener un <xref:System.Windows.Documents.FlowDocument> que a su vez debe contener un <xref:System.Windows.Documents.Block>-objeto derivado. A continuación, se muestra el segmento correspondiente del diagrama anterior.  
  
 ![Diagrama: Las reglas de contención de RichTextBox](./media/flow-ovw-schemawalkthrough1.png "Flow_Ovw_SchemaWalkThrough1")  
  
 Llegados a este punto, esta es la apariencia que podría tener el marcado.  
  
 [!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough1](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough1)]  
  
 **2.** Según el diagrama, hay varios <xref:System.Windows.Documents.Block> elementos para elegir, que incluyen <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.Table>, <xref:System.Windows.Documents.List>, y <xref:System.Windows.Documents.BlockUIContainer> (vea las clases derivadas de Block anteriores). Supongamos que queremos un <xref:System.Windows.Documents.Table>. Según el diagrama anterior, un <xref:System.Windows.Documents.Table> contiene un <xref:System.Windows.Documents.TableRowGroup> que contiene <xref:System.Windows.Documents.TableRow> elementos, que contienen <xref:System.Windows.Documents.TableCell> elementos que contienen un <xref:System.Windows.Documents.Block>-objeto derivado. A continuación se encuentra el segmento correspondiente para <xref:System.Windows.Documents.Table> tomado del diagrama anterior.  
  
 ![Diagrama: Elemento primario&#47;esquema secundario para tabla](./media/flow-ovw-schemawalkthrough2.png "Flow_Ovw_SchemaWalkThrough2")  
  
 A continuación, se muestra el marcado correspondiente.  
  
 [!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough2](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough2)]  
  
 **3.** Nuevamente, uno o varios <xref:System.Windows.Documents.Block> se requieren los elementos debajo de un <xref:System.Windows.Documents.TableCell>. Para facilitar el proceso, vamos a colocar texto dentro de la celda. Esto se logra mediante un <xref:System.Windows.Documents.Paragraph> con un <xref:System.Windows.Documents.Run> elemento. A continuación encontrará los segmentos correspondientes del diagrama que demuestran que un <xref:System.Windows.Documents.Paragraph> puede tardar un <xref:System.Windows.Documents.Inline> elemento y que un <xref:System.Windows.Documents.Run> (un <xref:System.Windows.Documents.Inline> elemento) sólo puede aceptar texto sin formato.  
  
 ![Diagrama: Elemento primario&#47;esquema secundario para párrafo](./media/flow-ovw-schemawalkthrough3.png "Flow_Ovw_SchemaWalkThrough3")  
  
 ![Diagrama: Elemento primario&#47;esquema secundario para ejecución](./media/flow-ovw-schemawalkthrough4.png "Flow_Ovw_SchemaWalkThrough4")  
  
 A continuación se muestra el ejemplo completo en el marcado.  
  
 [!code-xaml[FlowOvwSnippets_snip#SchemaExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SchemaExample.xaml#schemaexamplewholepage)]  
  
<a name="customizing_text"></a>   
## <a name="customizing-text"></a>Personalizar texto  
 En general, el texto es el tipo de contenido más frecuente de un documento dinámico. Aunque los objetos descritos anteriormente pueden utilizarse para controlar la mayoría de los aspectos de cómo se representa el texto, hay otros métodos para personalizar el texto, según se describen en esta sección.  
  
### <a name="text-decorations"></a>Decoraciones de texto  
 Las decoraciones de texto le permiten aplicar efectos de subrayado, línea alta, línea base y tachado al texto (consulte las imágenes siguientes). Estas decoraciones se agregan utilizando la <xref:System.Windows.Documents.Inline.TextDecorations%2A> propiedad que se expone mediante un número de objetos incluidos <xref:System.Windows.Documents.Inline>, <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Controls.TextBlock>, y <xref:System.Windows.Controls.TextBox>.  
  
 En el ejemplo siguiente se muestra cómo se establece la propiedad <xref:System.Windows.Documents.Paragraph.TextDecorations%2A> de <xref:System.Windows.Documents.Paragraph>.  
  
 [!code-xaml[InlineSnippets#_Paragraph_TextDecXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/InlineSnippets/CSharp/Window1.xaml#_paragraph_textdecxaml)]  
  
 [!code-csharp[InlineSnippets#_Paragraph_TextDec](~/samples/snippets/csharp/VS_Snippets_Wpf/InlineSnippets/CSharp/Window1.xaml.cs#_paragraph_textdec)]
 [!code-vb[InlineSnippets#_Paragraph_TextDec](~/samples/snippets/visualbasic/VS_Snippets_Wpf/InlineSnippets/visualbasic/window1.xaml.vb#_paragraph_textdec)]  
  
 En la ilustración siguiente, se muestra cómo se representa este ejemplo.  
  
 ![Captura de pantalla: Texto con efecto de tachado predeterminado](./media/inline-textdec-strike.png "Inline_TextDec_Strike")  
  
 Las ilustraciones siguientes muestran cómo el **suprarrayado**, **Baseline**, y **subrayado** decoraciones representan, respectivamente.  
  
 ![Captura de pantalla: TextDecorator de línea alta](./media/inline-textdec-over.png "Inline_TextDec_Over")  
  
 ![Captura de pantalla: Predeterminado de efecto de línea base en texto](./media/inline-textdec-base.png "Inline_TextDec_Base")  
  
 ![Captura de pantalla: Texto con efecto de subrayado predeterminado](./media/inline-textdec-under.png "Inline_TextDec_Under")  
  
### <a name="typography"></a>Tipografía  
 El <xref:System.Windows.Documents.TextElement.Typography%2A> propiedad se expone mediante la mayoría relacionadas con el flujo de contenido incluido <xref:System.Windows.Documents.TextElement>, <xref:System.Windows.Documents.FlowDocument>, <xref:System.Windows.Controls.TextBlock>, y <xref:System.Windows.Controls.TextBox>. Esta propiedad se utiliza para controlar características/variaciones tipográficas del texto (es decir, versalitas o mayúsculas, superíndices y subíndices, etc.).  
  
 El ejemplo siguiente muestra cómo establecer el <xref:System.Windows.Documents.TextElement.Typography%2A> atributo, mediante <xref:System.Windows.Documents.Paragraph> como elemento de ejemplo.  
  
 [!code-xaml[TextElementSnippets#_TextElement_TypogXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextElementSnippets/CSharp/Window1.xaml#_textelement_typogxaml)]  
  
 En la ilustración siguiente, se muestra cómo se representa este ejemplo.  
  
 ![Captura de pantalla: Texto con tipografía modificada](./media/textelement-typog.png "TextElement_Typog")  
  
 En cambio, en la siguiente ilustración se muestra cómo se representa un ejemplo similar con propiedades tipográficas predeterminadas.  
  
 ![Captura de pantalla: Texto con tipografía modificada](./media/textelement-typog-default.png "TextElement_Typog_Default")  
  
 El ejemplo siguiente muestra cómo establecer el <xref:System.Windows.Controls.TextBox.Typography%2A> propiedad mediante programación.  
  
 [!code-csharp[TextElementSnippets#_TextElement_Typog](~/samples/snippets/csharp/VS_Snippets_Wpf/TextElementSnippets/CSharp/Window1.xaml.cs#_textelement_typog)]
 [!code-vb[TextElementSnippets#_TextElement_Typog](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextElementSnippets/visualbasic/window1.xaml.vb#_textelement_typog)]  
  
 Consulte [tipografía en WPF](typography-in-wpf.md) para obtener más información sobre la tipografía.  
  
## <a name="see-also"></a>Vea también

- [Texto](optimizing-performance-text.md)
- [Tipografía en WPF](typography-in-wpf.md)
- [Temas "Cómo..."](flow-content-elements-how-to-topics.md)
- [Información general sobre el modelo de contenido de TextElement](textelement-content-model-overview.md)
- [RichTextBox Overview](../controls/richtextbox-overview.md) (Introducción a RichTextBox)
- [Documentos en WPF](documents-in-wpf.md)
- [Información general sobre tablas](table-overview.md)
- [Información general sobre anotaciones](annotations-overview.md)
