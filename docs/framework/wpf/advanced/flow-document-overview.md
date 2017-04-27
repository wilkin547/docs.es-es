---
title: "Informaci&#243;n general sobre documentos din&#225;micos | Microsoft Docs"
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
  - "esquema de contenido"
  - "documentos, documentos de flujo"
  - "elementos de contenido dinámico [WPF], documentos de flujo"
  - "documentos de flujo"
ms.assetid: ef236a50-d44f-43c8-ba7c-82b0c733c0b7
caps.latest.revision: 39
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 29
---
# Informaci&#243;n general sobre documentos din&#225;micos
Los documentos dinámicos se han diseñado para optimizar su presentación y legibilidad.  En lugar de establecerse en un diseño predefinido, este tipo de documentos ajusta y recoloca dinámicamente su contenido basándose en variables de tiempo de ejecución, tales como el tamaño de la ventana, la resolución del dispositivo y las preferencias opcionales del usuario.  Además, ofrecen características de documentos avanzadas, como la paginación y las columnas.  En este tema se ofrece información general sobre los documentos dinámicos y sobre cómo crearlos.  
  
   
  
<a name="what_is_a_flow_document"></a>   
## Qué es un documento dinámico  
 Un documento dinámico está diseñado para "recolocar el contenido" dependiendo del tamaño de la ventana, la resolución del dispositivo y otras variables de entorno.  Además, los documentos dinámicos tienen varias características integradas que incluyen la búsqueda, modos de presentación que optimizan la legibilidad y la capacidad de cambiar el tamaño y la apariencia de las fuentes.  Este tipo de documentos son óptimos para su uso cuando la facilidad de lectura constituye el principal escenario de consumo del documento.  En cambio, los documentos fijos están diseñados para tener una presentación estática.  Los documentos fijos son útiles cuando la fidelidad del contenido de origen resulta esencial.  Vea [Documentos en WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md) para obtener más información sobre los distintos tipos de documentos.  
  
 La ilustración siguiente muestra un documento dinámico de ejemplo visualizado en varias ventanas de tamaños diferentes.  A medida que el área de presentación cambia, el contenido se recoloca para utilizar el espacio disponible del mejor modo posible.  
  
 ![Cambio de flujo del contenido de documentos de flujo](../../../../docs/framework/wpf/advanced/media/edocs-flowdocument.png "eDocs\_FlowDocument")  
  
 Tal y como se muestra en la imagen anterior, el contenido dinámico puede incluir muchos componentes, entre los que se incluyen párrafos, listas, imágenes, etc.  Estos componentes corresponden a elementos de marcado y a objetos del código de procedimientos.  Analizaremos estas clases detalladamente más adelante en la sección [Clases relacionadas con el flujo](#flow_related_classes) de esta introducción.  De momento, aquí tiene un ejemplo de código simple que crea un documento dinámico compuesto por un párrafo con texto en negrita y una lista.  
  
 [!code-xml[FlowOvwSnippets_snip#SimpleFlowExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SimpleFlowExample.xaml#simpleflowexamplewholepage)]  
  
 [!code-csharp[FlowOvwSnippets_procedural_snip#SimpleFlowCodeOnlyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/SimpleFlowExample.cs#simpleflowcodeonlyexamplewholepage)]
 [!code-vb[FlowOvwSnippets_procedural_snip#SimpleFlowCodeOnlyExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/SimpleFlowExample.vb#simpleflowcodeonlyexamplewholepage)]  
  
 La ilustración siguiente muestra la apariencia de este fragmento de código.  
  
 ![Captura de pantalla: Ejemplo de FlowDocument representado](../../../../docs/framework/wpf/advanced/media/flow-ovw-first-example.png "Flow\_Ovw\_First\_Example")  
  
 En este ejemplo, el control <xref:System.Windows.Controls.FlowDocumentReader> se utiliza para hospedar el contenido dinámico.  Vea [Tipos de documentos dinámicos](#flow_document_types) para obtener más información sobre los controles que hospedan contenido dinámico.  Los elementos <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.List>, <xref:System.Windows.Documents.ListItem> y <xref:System.Windows.Documents.Bold> se utilizan para controlar el formato del contenido, basándose en su orden en el marcado.  Por ejemplo, el elemento <xref:System.Windows.Documents.Bold> abarca sólo una parte del texto del párrafo; como resultado, sólo ese fragmento de texto está en negrita.  Si ha utilizado HTML, esto le resultará familiar.  
  
 Tal y como se muestra en la ilustración anterior, los documentos dinámicos tienen varias características integradas:  
  
-   Búsqueda: permite al usuario realizar una búsqueda de texto completo en un documento.  
  
-   Modo de visualización: el usuario puede elegir su modo de visualización preferido, incluyendo el modo de visualización de una sola página \(una página a la vez\), de dos páginas a la vez \(formato de lectura de libro\) y de desplazamiento continuo \(sin límite\).  Para obtener más información sobre estos modos de visualización, consulte <xref:System.Windows.Controls.FlowDocumentReaderViewingMode>.  
  
-   Controles de navegación de páginas: si el modo de visualización del documento utiliza páginas, los controles de navegación de páginas incluyen un botón que permite saltar a la página siguiente \(flecha abajo\) o a la página anterior \(flecha arriba\), así como indicadores del número de página actual y el número total de páginas.  También es posible pasar las páginas utilizando las teclas de dirección del teclado.  
  
-   Zoom: los controles de zoom permiten al usuario aumentar o reducir el nivel de zoom haciendo clic en los botones con el signo más y el signo menos, respectivamente.  Los controles de zoom incluyen también un control deslizante para ajustar el nivel de zoom.  Para obtener más información, vea <xref:System.Windows.Controls.FlowDocumentReader.Zoom%2A>.  
  
 Estas características se pueden modificar dependiendo del control utilizado para hospedar el contenido dinámico.  En la sección siguiente se describen los distintos controles.  
  
<a name="flow_document_types"></a>   
## Tipos de documentos dinámicos  
 La presentación y la apariencia del contenido en los documentos dinámicos dependerán del objeto utilizado para hospedar el contenido dinámico.  Hay cuatro controles que permiten la visualización del contenido dinámico: <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, <xref:System.Windows.Controls.RichTextBox> y <xref:System.Windows.Controls.FlowDocumentScrollViewer>.  Estos controles se describen brevemente a continuación.  
  
 **Nota: es necesario que**  <xref:System.Windows.Documents.FlowDocument> hospede directamente el contenido dinámico, por lo que todos estos controles utilizan un objeto <xref:System.Windows.Documents.FlowDocument> para habilitar el hospedaje de dicho contenido.  
  
### FlowDocumentReader  
 <xref:System.Windows.Controls.FlowDocumentReader> dispone de características que permiten al usuario seleccionar dinámicamente distintos modos de visualización, incluido el modo de visualización de una sola página \(una página a la vez\), dos páginas a la vez \(formato de lectura de libro\) y desplazamiento continuo \(sin límite\).  Para obtener más información sobre estos modos de visualización, consulte <xref:System.Windows.Controls.FlowDocumentReaderViewingMode>.  Si no necesita la capacidad de cambiar dinámicamente entre distintos modos de visualización, <xref:System.Windows.Controls.FlowDocumentPageViewer> y <xref:System.Windows.Controls.FlowDocumentScrollViewer> proporcionan visores de contenido dinámico más ligeros que son fijos para un modo de visualización concreto.  
  
### FlowDocumentPageViewer y FlowDocumentScrollViewer  
 <xref:System.Windows.Controls.FlowDocumentPageViewer> muestra el contenido en el modo de visualización de una sola página, mientras que <xref:System.Windows.Controls.FlowDocumentScrollViewer> muestra el contenido en modo de desplazamiento continuo.  Tanto <xref:System.Windows.Controls.FlowDocumentPageViewer> como <xref:System.Windows.Controls.FlowDocumentScrollViewer> son fijos para un modo de visualización concreto.  Puede compararlos con <xref:System.Windows.Controls.FlowDocumentReader>, que incluye características que permiten al usuario elegir dinámicamente entre varios modos de visualización \(suministrados por la enumeración <xref:System.Windows.Controls.FlowDocumentReaderViewingMode>\), a costa de exigir un uso más intensivo de recursos que <xref:System.Windows.Controls.FlowDocumentPageViewer> o <xref:System.Windows.Controls.FlowDocumentScrollViewer>.  
  
 De manera predeterminada, se muestra siempre una barra de desplazamiento vertical y la barra de desplazamiento horizontal se vuelve visible cuando es necesario.  La interfaz de usuario predeterminada para <xref:System.Windows.Controls.FlowDocumentScrollViewer> no incluye barra de herramientas; sin embargo, se puede utilizar la propiedad <xref:System.Windows.Controls.FlowDocumentScrollViewer.IsToolBarVisible%2A> para habilitar una barra de herramientas integrada.  
  
### RichTextBox  
 Utilice un control <xref:System.Windows.Controls.RichTextBox> si desea que el usuario pueda editar el contenido dinámico.  Por ejemplo, si desea crear un editor que le permita al usuario manipular elementos como tablas, formatos de cursiva y negrita, etc., utilice <xref:System.Windows.Controls.RichTextBox>.  Vea [Información general sobre el control RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md) para obtener más información.  
  
 **Nota:** el contenido dinámico existente dentro de un control <xref:System.Windows.Controls.RichTextBox> no se comporta exactamente como el contenido dinámico incluido en otros controles.  Por ejemplo, en <xref:System.Windows.Controls.RichTextBox> no hay ninguna columna, por lo que no existe un comportamiento de cambio de tamaño automático.  Además, las características normalmente integradas de contenido dinámico como la búsqueda, el modo de visualización, la navegación de páginas y el zoom no están disponibles dentro de un elemento <xref:System.Windows.Controls.RichTextBox>.  
  
<a name="creating_flow_content"></a>   
## Crear contenido dinámico  
 El contenido dinámico puede ser complejo, estando compuesto por varios elementos como texto, imágenes, tablas e incluso clases derivadas de <xref:System.Windows.UIElement> como los controles.  Los puntos siguientes resultan esenciales para entender cómo se crea el contenido de flujo dinámico:  
  
-   **Clases relacionadas con el flujo:** cada una de las clases utilizadas en el contenido dinámico tiene un propósito concreto.  Además, la relación jerárquica entre las clases dinámicas le ayuda a entender cómo se utilizan.  Por ejemplo, las clases derivadas de la clase <xref:System.Windows.Documents.Block> se utilizan para contener otros objetos, mientras que las clases derivadas de <xref:System.Windows.Documents.Inline> contienen objetos que se muestran.  
  
-   **Esquema de contenido:** un documento dinámico puede requerir un número sustancial de elementos anidados.  El esquema de contenido especifica las posibles relaciones de elemento primario\/secundario entre los elementos.  
  
 Las secciones siguientes analizarán con más detalle cada una de estas áreas.  
  
<a name="flow_related_classes"></a>   
## Clases relacionadas con el contenido dinámico  
 El diagrama siguiente muestra los objetos más utilizados con el contenido dinámico:  
  
 ![Diagrama: Jerarquía de clases de elementos de contenido dinámico](../../../../docs/framework/wpf/advanced/media/flow-class-hierarchy.png "Flow\_Class\_Hierarchy")  
  
 En lo que al contenido dinámico se refiere, hay dos categorías importantes:  
  
1.  **Clases derivadas de bloque:** también denominadas "elementos de contenido de bloque" o simplemente "elementos de bloque".  Los elementos que heredan de la clase <xref:System.Windows.Documents.Block> se pueden utilizar para agrupar elementos bajo un elemento primario común o para aplicar atributos comunes a un grupo.  
  
2.  **Clases derivadas inline:** también denominadas "elementos de contenido inline " o simplemente "elementos inline".  Los elementos que heredan de <xref:System.Windows.Documents.Inline> están incluidos dentro de un elemento de bloque o de otro elemento inline.  Los elementos inline se utilizan a menudo como contenedor directo del contenido que se representa en la pantalla.  Por ejemplo, un elemento <xref:System.Windows.Documents.Paragraph> \(elemento de bloque\) puede contener un elemento <xref:System.Windows.Documents.Run> \(elemento inline\), pero es <xref:System.Windows.Documents.Run> el que contiene en realidad el texto que se representa en la pantalla.  
  
 A continuación se describe brevemente cada una de las clases de estas dos categorías.  
  
### Clases derivadas de bloque  
 **Paragraph**  
  
 <xref:System.Windows.Documents.Paragraph> se utiliza normalmente para agrupar el contenido en un párrafo.  El uso más sencillo y común de Paragraph es crear un párrafo de texto.  
  
 [!code-xml[FlowOvwSnippets_snip#ParagraphExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/ParagraphExample.xaml#paragraphexamplewholepage)]  
  
 [!code-csharp[FlowOvwSnippets_procedural_snip#ParagraphCodeOnlyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/ParagraphExample.cs#paragraphcodeonlyexamplewholepage)]
 [!code-vb[FlowOvwSnippets_procedural_snip#ParagraphCodeOnlyExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/ParagraphExample.vb#paragraphcodeonlyexamplewholepage)]  
  
 Sin embargo, también puede contener otros elementos inline derivados, como comprobará a continuación.  
  
 **Sección**  
  
 <xref:System.Windows.Documents.Section> sólo se utiliza para contener otros elementos derivados de <xref:System.Windows.Documents.Block>.  No aplica ningún formato predeterminado a los elementos que contiene.  Sin embargo, cualquier conjunto de valores de propiedad establecidos en un elemento <xref:System.Windows.Documents.Section> se aplica a sus elementos secundarios.  Asimismo, una sección le permite recorrer en iteración mediante programación su colección secundaria.  <xref:System.Windows.Documents.Section> se utiliza de una manera similar a la etiqueta \<DIV\> en HTML.  
  
 En el ejemplo siguiente, se definen tres párrafos debajo de un elemento <xref:System.Windows.Documents.Section>.  La sección tiene un valor de propiedad <xref:System.Windows.Documents.TextElement.Background%2A> de Rojo, por lo que el color de fondo del párrafo también es rojo.  
  
 [!code-xml[FlowOvwSnippets_snip#SectionExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SectionExample.xaml#sectionexamplewholepage)]  
  
 [!code-csharp[FlowOvwSnippets_procedural_snip#SectionCodeOnlyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/SectionExample.cs#sectioncodeonlyexamplewholepage)]
 [!code-vb[FlowOvwSnippets_procedural_snip#SectionCodeOnlyExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/SectionExample.vb#sectioncodeonlyexamplewholepage)]  
  
 **BlockUIContainer**  
  
 <xref:System.Windows.Documents.BlockUIContainer> permite incrustar elementos <xref:System.Windows.UIElement> \(por ejemplo,  un control <xref:System.Windows.Controls.Button>\) en contenido dinámico derivado de bloque.  <xref:System.Windows.Documents.InlineUIContainer> \(vea a continuación\) se utiliza para incrustar elementos <xref:System.Windows.UIElement> en contenido dinámico derivado insertado.  <xref:System.Windows.Documents.BlockUIContainer> y <xref:System.Windows.Documents.InlineUIContainer> son importantes porque no hay ninguna otra manera de utilizar un elemento <xref:System.Windows.UIElement> en el contenido dinámico a menos que esté incluido en uno de estos dos elementos.  
  
 El ejemplo siguiente muestra cómo utilizar el elemento <xref:System.Windows.Documents.BlockUIContainer> para hospedar los objetos <xref:System.Windows.UIElement> dentro del contenido dinámico.  
  
 [!code-xml[SpanSnippets#_BlockUIXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml#_blockuixaml)]  
  
 En la ilustración siguiente se muestra cómo se representa este ejemplo.  
  
 ![Captura de pantalla: UIElement incrustado en contenido dinámico](../../../../docs/framework/wpf/advanced/media/blockuicontainer.png "BlockUIContainer")  
  
 **List**  
  
 <xref:System.Windows.Documents.List> se utiliza para crear una lista con viñetas o numérica.  Establezca la propiedad <xref:System.Windows.Documents.List.MarkerStyle%2A> en un valor de enumeración <xref:System.Windows.TextMarkerStyle> para determinar el estilo de la lista.  En el siguiente ejemplo se muestra cómo crear una lista sencilla.  
  
 [!code-xml[FlowOvwSnippets_snip#ListExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/ListExample.xaml#listexamplewholepage)]  
  
 [!code-csharp[FlowOvwSnippets_procedural_snip#ListCodeOnlyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/ListExample.cs#listcodeonlyexamplewholepage)]
 [!code-vb[FlowOvwSnippets_procedural_snip#ListCodeOnlyExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/ListExample.vb#listcodeonlyexamplewholepage)]  
  
 **Nota:** <xref:System.Windows.Documents.List> es el único elemento dinámico que utiliza <xref:System.Windows.Documents.ListItemCollection> para administrar los elementos secundarios.  
  
 **Tabla**  
  
 <xref:System.Windows.Documents.Table> se utiliza para crear una tabla.  <xref:System.Windows.Documents.Table> es similar al elemento <xref:System.Windows.Controls.Grid> pero tiene más funciones y, por consiguiente, requiere mayor consumo de recursos.  Dado que <xref:System.Windows.Controls.Grid> es un elemento <xref:System.Windows.UIElement>, no se puede utilizar en el contenido dinámico a menos que esté incluido en un elemento <xref:System.Windows.Documents.BlockUIContainer> o <xref:System.Windows.Documents.InlineUIContainer>.  Para obtener más información sobre <xref:System.Windows.Documents.Table>, vea [Información general sobre tablas](../../../../docs/framework/wpf/advanced/table-overview.md).  
  
### Clases derivadas inline  
 **Run**  
  
 <xref:System.Windows.Documents.Run> se utiliza para contener texto sin formato.  Los objetos <xref:System.Windows.Documents.Run> se usarán ampliamente en contenido de flujo.  Sin embargo, en marcado, no es obligatorio usar los elementos <xref:System.Windows.Documents.Run> explícitamente.  El uso de <xref:System.Windows.Documents.Run> es obligatorio cuando se crean o manipulan documentos dinámicos mediante código.  Por ejemplo, en el marcado siguiente, el primer elemento <xref:System.Windows.Documents.Paragraph> especifica explícitamente el elemento <xref:System.Windows.Documents.Run>, mientras que el segundo no lo hace.  Ambos párrafos generan el mismo resultado.  
  
 [!code-xml[FlowOvwSnippets_snip#RunExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/RunSnippetsExample.xaml#runexample1)]  
  
 **Nota:** A partir de [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)], la propiedad <xref:System.Windows.Documents.Run.Text%2A> del objeto <xref:System.Windows.Documents.Run> es una propiedad de dependencia.  Puede enlazar la propiedad <xref:System.Windows.Documents.Run.Text%2A> a un origen de datos como <xref:System.Windows.Controls.TextBlock>.  La propiedad <xref:System.Windows.Documents.Run.Text%2A> admite el enlace unidireccional totalmente.  La propiedad <xref:System.Windows.Documents.Run.Text%2A> también admite el enlace bidireccional, salvo para <xref:System.Windows.Controls.RichTextBox>.  Para obtener un ejemplo, vea <xref:System.Windows.Documents.Run.Text%2A?displayProperty=fullName>.  
  
 **Span**  
  
 <xref:System.Windows.Documents.Span> agrupa otros elementos de contenido alineados.  No se aplica ninguna representación inherente al contenido dentro de un elemento <xref:System.Windows.Documents.Span>.  Sin embargo, los elementos que heredan de <xref:System.Windows.Documents.Span>, incluyendo <xref:System.Windows.Documents.Hyperlink>, <xref:System.Windows.Documents.Bold>, <xref:System.Windows.Documents.Italic> y <xref:System.Windows.Documents.Underline>, aplican formato al texto.  
  
 A continuación se muestra un ejemplo de un objeto <xref:System.Windows.Documents.Span> utilizado para incluir contenido inline, incluyendo texto, un elemento <xref:System.Windows.Documents.Bold> y un elemento <xref:System.Windows.Controls.Button>.  
  
 [!code-xml[FlowOvwSnippets_snip#SpanExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SpanExample.xaml#spanexamplewholepage)]  
  
 La captura de pantalla siguiente muestra cómo se representa este ejemplo.  
  
 ![Captura de pantalla: Ejemplo de Span representado](../../../../docs/framework/wpf/advanced/media/flow-spanexample.png "Flow\_SpanExample")  
  
 **InlineUIContainer**  
  
 <xref:System.Windows.Documents.InlineUIContainer> permite incrustar elementos <xref:System.Windows.UIElement> \(por ejemplo,  un control como <xref:System.Windows.Controls.Button>\) en un elemento de contenido <xref:System.Windows.Documents.Inline>.  Este elemento es el equivalente inline al elemento <xref:System.Windows.Documents.BlockUIContainer> descrito anteriormente.  A continuación se muestra un ejemplo que utiliza <xref:System.Windows.Documents.InlineUIContainer> para insertar un control <xref:System.Windows.Controls.Button> inline en un elemento <xref:System.Windows.Documents.Paragraph>.  
  
 [!code-xml[FlowOvwSnippets_snip#InlineUIContainerExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/InlineUIContainerExample.xaml#inlineuicontainerexamplewholepage)]  
  
 [!code-csharp[FlowOvwSnippets_procedural_snip#InlineUIContainerCodeOnlyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/InlineUIContainerExample.cs#inlineuicontainercodeonlyexamplewholepage)]
 [!code-vb[FlowOvwSnippets_procedural_snip#InlineUIContainerCodeOnlyExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/InlineUIContainerExample.vb#inlineuicontainercodeonlyexamplewholepage)]  
  
 **Nota:** no es necesario utilizar <xref:System.Windows.Documents.InlineUIContainer> explícitamente en el marcado.  Si lo omite, se creará de todas formas un elemento <xref:System.Windows.Documents.InlineUIContainer> al compilar el código.  
  
 **Figure y Floater**  
  
 <xref:System.Windows.Documents.Figure> y <xref:System.Windows.Documents.Floater> se utilizan para incrustar contenido en documentos dinámicos con propiedades de posición que se pueden personalizar de forma independiente del flujo de contenido primario.  Los elementos <xref:System.Windows.Documents.Figure> o <xref:System.Windows.Documents.Floater> se utilizan a menudo para resaltar o recalcar partes de contenido, hospedar imágenes auxiliares u otro contenido dentro del flujo principal de contenido, o bien, para insertar contenido de relación indirecta como los anuncios.  
  
 El ejemplo siguiente muestra cómo incrustar un elemento <xref:System.Windows.Documents.Figure> en un párrafo de texto.  
  
 [!code-xml[FlowOvwSnippets_snip#FigureExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/FigureExample.xaml#figureexamplewholepage)]  
  
 [!code-csharp[FlowOvwSnippets_procedural_snip#FigureCodeOnlyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/FigureExample.cs#figurecodeonlyexamplewholepage)]
 [!code-vb[FlowOvwSnippets_procedural_snip#FigureCodeOnlyExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/FigureExample.vb#figurecodeonlyexamplewholepage)]  
  
 En la ilustración siguiente se muestra cómo se representa este ejemplo.  
  
 ![Captura de pantalla: Ejemplo de figura](../../../../docs/framework/wpf/advanced/media/flow-ovw-figure-example.png "Flow\_Ovw\_Figure\_Example")  
  
 Los elementos <xref:System.Windows.Documents.Figure> y <xref:System.Windows.Documents.Floater> son distintos y se utilizan en situaciones diferentes.  
  
 **Elemento Figure:**  
  
-   Se puede determinar su posición: puede establecer sus puntos de anclaje horizontales y verticales para acoplarlo con respecto a la página, el contenido, la columna o el párrafo.  También puede utilizar sus propiedades <xref:System.Windows.Documents.Figure.HorizontalOffset%2A> y <xref:System.Windows.Documents.Figure.VerticalOffset%2A> para especificar desplazamientos arbitrarios.  
  
-   Se puede ajustar su tamaño a varias columnas: puede establecer el alto y el ancho del elemento <xref:System.Windows.Documents.Figure> en múltiplos de los valores de alto o ancho de la página, el contenido o la columna.  Observe que en el caso de la página y del contenido, no se permiten múltiplos mayores que 1.  Por ejemplo, puede establecer el ancho de <xref:System.Windows.Documents.Figure> en "0,5 page", "0,25 content" o "2 Column".  También puede establecer el alto y el ancho en valores absolutos de píxel.  
  
-   No pagina: si el contenido de un elemento <xref:System.Windows.Documents.Figure> no cabe en <xref:System.Windows.Documents.Figure>, se representará el contenido que quepa y se perderá el contenido restante.  
  
 **Elemento Floater:**  
  
-   No se puede determinar su posición y se representará en cualquier espacio que esté disponible.  No se puede establecer el desplazamiento ni los puntos de anclaje de un elemento <xref:System.Windows.Documents.Floater>.  
  
-   No se puede ajustar su tamaño a más de una columna: de forma predeterminada, <xref:System.Windows.Documents.Floater> ajusta su tamaño a una columna.  Su propiedad <xref:System.Windows.Documents.Floater.Width%2A> puede establecerse en un valor absoluto de píxel, pero si este valor es mayor que el ancho de una columna, se omite y el tamaño del elemento Floater se ajusta a una columna.  Su tamaño puede establecerse en menos de una columna configurando el ancho en píxeles correcto, pero el tamaño no es relativo a la columna, por lo que "0,5Column" no es una expresión válida para el ancho de <xref:System.Windows.Documents.Floater>.  <xref:System.Windows.Documents.Floater> no tiene una propiedad que especifique el alto: su alto no puede establecerse ya que depende del contenido.  
  
-   <xref:System.Windows.Documents.Floater> pagina: si su contenido en el ancho especificado se extiende más allá del alto de una columna, el elemento Floater se parte y salta a la siguiente columna, la siguiente página, etc.  
  
 <xref:System.Windows.Documents.Figure> se presta especialmente para contenido independiente cuyo tamaño y posición desea controlar, ya que le da la seguridad de que el contenido se ajustará al tamaño especificado.  <xref:System.Windows.Documents.Floater> se presta especialmente para contenido que fluye más libremente y de manera similar al contenido de la página principal, pero que es independiente de este último.  
  
 **LineBreak**  
  
 <xref:System.Windows.Documents.LineBreak> origina un salto de línea en el contenido dinámico.   El siguiente ejemplo muestra el uso de <xref:System.Windows.Documents.LineBreak>.  
  
 [!code-xml[FlowOvwSnippets_snip#LineBreakExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/LineBreakExample.xaml#linebreakexamplewholepage)]  
  
 La captura de pantalla siguiente muestra cómo se representa este ejemplo.  
  
 ![Captura de pantalla: Ejemplo de LineBreak](../../../../docs/framework/wpf/advanced/media/flow-ovw-linebreakexample.png "Flow\_Ovw\_LineBreakExample")  
  
### Elementos de colección dinámica  
 En muchos de los ejemplos anteriores, los elementos <xref:System.Windows.Documents.BlockCollection> y <xref:System.Windows.Documents.InlineCollection> se utilizan para generar contenido dinámico mediante programación.  Por ejemplo, para agregar elementos a un objeto <xref:System.Windows.Documents.Paragraph>, puede utilizar la sintaxis siguiente:  
  
 `…`  
  
 `myParagraph.Inlines.Add(new Run("Some text"));`  
  
 `…`  
  
 Esto agrega un elemento <xref:System.Windows.Documents.Run> al elemento <xref:System.Windows.Documents.InlineCollection> del objeto <xref:System.Windows.Documents.Paragraph>.  Esto es lo mismo que el elemento <xref:System.Windows.Documents.Run> implícito incluido en un objeto <xref:System.Windows.Documents.Paragraph> en el marcado:  
  
 `…`  
  
 `<Paragraph>`  
  
 `Some Text`  
  
 `</Paragraph>`  
  
 `…`  
  
 Como ejemplo de uso del elemento <xref:System.Windows.Documents.BlockCollection>, el ejemplo siguiente crea un nuevo elemento <xref:System.Windows.Documents.Section> y, a continuación, utiliza el método **Add** para agregar un nuevo elemento <xref:System.Windows.Documents.Paragraph> al contenido de <xref:System.Windows.Documents.Section>.  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksAdd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksadd)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksAdd](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksadd)]  
  
 Además de agregar elementos a una colección dinámica, también se pueden quitar.  En el siguiente ejemplo se elimina el último elemento <xref:System.Windows.Documents.Inline> de <xref:System.Windows.Documents.Span>.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesRemoveLast](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesremovelast)]
 [!code-vb[SpanSnippets#_SpanInlinesRemoveLast](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesremovelast)]  
  
 En el siguiente ejemplo se borra todo el contenido \(los elementos <xref:System.Windows.Documents.Inline>\) de <xref:System.Windows.Documents.Span>.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesClear](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesclear)]
 [!code-vb[SpanSnippets#_SpanInlinesClear](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesclear)]  
  
 Al trabajar con contenido dinámico mediante programación, probablemente realizará un uso extensivo de estas colecciones.  
  
 Que un elemento dinámico utilice un elemento <xref:System.Windows.Documents.InlineCollection> \(Inlines\) o un elemento <xref:System.Windows.Documents.BlockCollection> \(Blocks\) para contener sus elementos secundarios dependerá de qué tipo de elementos secundarios \(<xref:System.Windows.Documents.Block> o <xref:System.Windows.Documents.Inline>\) puedan ser incluidos en el elemento primario.  Las reglas de contención para los elementos de contenido dinámico se resumen en el esquema de contenido de la sección siguiente.  
  
 **Nota:** existe un tercer tipo de colección utilizado con el contenido dinámico, <xref:System.Windows.Documents.ListItemCollection>, pero esta colección sólo se usa con un elemento <xref:System.Windows.Documents.List>.  Además, hay varias colecciones que se utilizan con <xref:System.Windows.Documents.Table>.  Vea [Información general sobre tablas](../../../../docs/framework/wpf/advanced/table-overview.md) para obtener más información.  
  
<a name="content_schema"></a>   
## Esquema de contenido  
 Dado el número de elementos de contenido dinámico diferentes que existen, puede resultar muy complicado efectuar un seguimiento del tipo de elementos secundarios que puede contener un elemento.  El diagrama siguiente resume las reglas de contención para los elementos dinámicos.  Las flechas representan las posibles relaciones entre elementos primarios\/secundarios.  
  
 ![Diagrama: Esquema de contención de contenido dinámico](../../../../docs/framework/wpf/advanced/media/flow-content-schema.png "Flow\_Content\_Schema")  
  
 Como se puede ver en el diagrama anterior, los elementos secundarios permitidos para un elemento no están determinados necesariamente por el hecho de que éste sea un elemento <xref:System.Windows.Documents.Block> o <xref:System.Windows.Documents.Inline>.  Por ejemplo, un objeto <xref:System.Windows.Documents.Span> \(un elemento <xref:System.Windows.Documents.Inline>\) sólo puede tener elementos secundarios <xref:System.Windows.Documents.Inline>, mientras que un objeto <xref:System.Windows.Documents.Figure> \(también un elemento <xref:System.Windows.Documents.Inline>\) sólo puede tener elementos secundarios <xref:System.Windows.Documents.Block>.  Por consiguiente, un diagrama es útil para determinar rápidamente qué elemento puede incluirse en otro.  Como ejemplo, utilicemos el diagrama para determinar cómo construir el contenido dinámico de un elemento <xref:System.Windows.Controls.RichTextBox>.  
  
 **1.** Un objeto <xref:System.Windows.Controls.RichTextBox> debe contener un elemento <xref:System.Windows.Documents.FlowDocument>, que a su vez debe contener un objeto derivado de <xref:System.Windows.Documents.Block>.  A continuación se muestra el segmento correspondiente del diagrama anterior.  
  
 ![Diagrama: Reglas de contención de RichTextBox](../../../../docs/framework/wpf/advanced/media/flow-ovw-schemawalkthrough1.png "Flow\_Ovw\_SchemaWalkThrough1")  
  
 Llegados a este punto, esta es la apariencia que podría tener el marcado.  
  
 [!code-xml[FlowOvwSnippets_snip#SchemaWalkThrough1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough1)]  
  
 **2.** Según el diagrama, hay varios elementos <xref:System.Windows.Documents.Block> entre los que elegir, incluyendo <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.Table>, <xref:System.Windows.Documents.List> y <xref:System.Windows.Documents.BlockUIContainer> \(vea Clases derivadas de bloque más arriba\).  Supongamos que deseamos un elemento <xref:System.Windows.Documents.Table>.  Según el diagrama anterior, un objeto <xref:System.Windows.Documents.Table> incluye un elemento <xref:System.Windows.Documents.TableRowGroup> que contiene elementos <xref:System.Windows.Documents.TableRow>, que a su vez contienen elementos <xref:System.Windows.Documents.TableCell> que incluyen un objeto derivado de <xref:System.Windows.Documents.Block>.  A continuación se muestra el segmento correspondiente para el elemento <xref:System.Windows.Documents.Table> tomado del diagrama anterior.  
  
 ![Diagrama: Esquema primario&#47;secundario para tabla](../../../../docs/framework/wpf/advanced/media/flow-ovw-schemawalkthrough2.png "Flow\_Ovw\_SchemaWalkThrough2")  
  
 A continuación se muestra el marcado correspondiente.  
  
 [!code-xml[FlowOvwSnippets_snip#SchemaWalkThrough2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough2)]  
  
 **3.** De nuevo, se requieren uno o varios elementos <xref:System.Windows.Documents.Block> debajo de un elemento <xref:System.Windows.Documents.TableCell>.  Para facilitar el proceso, coloquemos texto dentro de la celda.  Podemos hacerlo utilizando un objeto <xref:System.Windows.Documents.Paragraph> con un elemento <xref:System.Windows.Documents.Run>.  A continuación se muestran los segmentos correspondientes del diagrama que demuestran que un objeto <xref:System.Windows.Documents.Paragraph> puede aceptar un elemento <xref:System.Windows.Documents.Inline> y que un objeto <xref:System.Windows.Documents.Run> \(un elemento <xref:System.Windows.Documents.Inline>\) sólo puede aceptar texto sin formato.  
  
 ![Diagrama: Esquema primario&#47;secundario para párrafo](../../../../docs/framework/wpf/advanced/media/flow-ovw-schemawalkthrough3.png "Flow\_Ovw\_SchemaWalkThrough3")  
  
 ![Diagrama: Esquema primario&#47;secundario para ejecución](../../../../docs/framework/wpf/advanced/media/flow-ovw-schemawalkthrough4.png "Flow\_Ovw\_SchemaWalkThrough4")  
  
 A continuación se muestra el ejemplo completo en el marcado.  
  
 [!code-xml[FlowOvwSnippets_snip#SchemaExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SchemaExample.xaml#schemaexamplewholepage)]  
  
<a name="customizing_text"></a>   
## Personalizar el texto  
 Normalmente, el tipo de contenido más abundante en un documento dinámico es el texto.  Aunque los objetos descritos anteriormente se pueden utilizar para controlar la mayoría de los aspectos de la representación del texto, hay otros métodos para personalizar el texto que se describen en esta sección.  
  
### Decoraciones de texto  
 Las decoraciones de texto le permiten aplicar efectos de subrayado, de línea alta, de línea base y de tachado al texto \(vea las imágenes siguientes\).  Estas decoraciones se agregan utilizando la propiedad <xref:System.Windows.Documents.Inline.TextDecorations%2A> expuesta por varios objetos, como <xref:System.Windows.Documents.Inline>, <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Controls.TextBlock> y <xref:System.Windows.Controls.TextBox>.  
  
 En el ejemplo siguiente se muestra cómo establecer la propiedad <xref:System.Windows.Documents.Paragraph.TextDecorations%2A> de un objeto <xref:System.Windows.Documents.Paragraph>.  
  
 [!code-xml[InlineSnippets#_Paragraph_TextDecXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InlineSnippets/CSharp/Window1.xaml#_paragraph_textdecxaml)]  
  
 [!code-csharp[InlineSnippets#_Paragraph_TextDec](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InlineSnippets/CSharp/Window1.xaml.cs#_paragraph_textdec)]
 [!code-vb[InlineSnippets#_Paragraph_TextDec](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InlineSnippets/visualbasic/window1.xaml.vb#_paragraph_textdec)]  
  
 En la ilustración siguiente se muestra cómo se representa este ejemplo.  
  
 ![Captura de pantalla: Texto con efecto de tachado predeterminado](../../../../docs/framework/wpf/advanced/media/inline-textdec-strike.png "Inline\_TextDec\_Strike")  
  
 Las ilustraciones siguientes muestran cómo se representan las decoraciones **Línea alta**, **Línea base** y **Subrayado**, respectivamente.  
  
 ![Captura de pantalla: TextDecorator de línea alta](../../../../docs/framework/wpf/advanced/media/inline-textdec-over.png "Inline\_TextDec\_Over")  
  
 ![Captura de pantalla: Efecto de línea base predeterminada en texto](../../../../docs/framework/wpf/advanced/media/inline-textdec-base.png "Inline\_TextDec\_Base")  
  
 ![Captura de pantalla: Texto con efecto de subrayado predeterminado](../../../../docs/framework/wpf/advanced/media/inline-textdec-under.png "Inline\_TextDec\_Under")  
  
### Tipografía  
 La propiedad <xref:System.Windows.Documents.TextElement.Typography%2A> la expone la mayoría del contenido relacionado con el flujo, como <xref:System.Windows.Documents.TextElement>, <xref:System.Windows.Documents.FlowDocument>, <xref:System.Windows.Controls.TextBlock> y <xref:System.Windows.Controls.TextBox>.  Esta propiedad se utiliza para controlar características\/variaciones tipográficas del texto \(por ejemplo,  mayúsculas pequeñas o grandes, generación de superíndices y subíndices, etc.\).  
  
 En el ejemplo siguiente se muestra cómo establecer el atributo <xref:System.Windows.Documents.TextElement.Typography%2A> usando <xref:System.Windows.Documents.Paragraph> como elemento de ejemplo.  
  
 [!code-xml[TextElementSnippets#_TextElement_TypogXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextElementSnippets/CSharp/Window1.xaml#_textelement_typogxaml)]  
  
 En la ilustración siguiente se muestra cómo se representa este ejemplo.  
  
 ![Captura de pantalla: Texto con tipografía modificada](../../../../docs/framework/wpf/advanced/media/textelement-typog.png "TextElement\_Typog")  
  
 En contraste, en la ilustración siguiente se muestra cómo se representa un ejemplo similar con propiedades tipográficas predeterminadas.  
  
 ![Captura de pantalla: Texto con tipografía modificada](../../../../docs/framework/wpf/advanced/media/textelement-typog-default.png "TextElement\_Typog\_Default")  
  
 En el ejemplo siguiente se muestra cómo establecer la propiedad <xref:System.Windows.Controls.TextBox.Typography%2A> mediante programación.  
  
 [!code-csharp[TextElementSnippets#_TextElement_Typog](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextElementSnippets/CSharp/Window1.xaml.cs#_textelement_typog)]
 [!code-vb[TextElementSnippets#_TextElement_Typog](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextElementSnippets/visualbasic/window1.xaml.vb#_textelement_typog)]  
  
 Vea [Tipografía en WPF](../../../../docs/framework/wpf/advanced/typography-in-wpf.md) para obtener más información sobre tipografía.  
  
## Vea también  
 [Text](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)   
 [Tipografía en WPF](../../../../docs/framework/wpf/advanced/typography-in-wpf.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/advanced/flow-content-elements-how-to-topics.md)   
 [Información general sobre el modelo de contenido de TextElement](../../../../docs/framework/wpf/advanced/textelement-content-model-overview.md)   
 [Información general sobre el control RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)   
 [Documentos en WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)   
 [Información general sobre tablas](../../../../docs/framework/wpf/advanced/table-overview.md)   
 [Información general sobre anotaciones](../../../../docs/framework/wpf/advanced/annotations-overview.md)