---
title: Información general sobre documentos dinámicos
description: Obtenga información sobre los documentos dinámicos en Windows Presentation Foundation, que ajustan dinámicamente el contenido en función del tamaño de la ventana, la resolución del dispositivo y las preferencias del usuario.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 'documents [WPF], flow documents [WPF], , '
- ', '
- flow documents [WPF]
ms.assetid: ef236a50-d44f-43c8-ba7c-82b0c733c0b7
ms.openlocfilehash: dac0cb91175a1398a0124020c048e14d7bcd1f76
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165238"
---
# <a name="flow-document-overview"></a>Información general sobre documentos dinámicos

Los documentos dinámicos están diseñados para optimizar su visualización y legibilidad. En lugar de establecer un diseño predefinido, los documentos dinámicos ajustan y redistribuyen dinámicamente su contenido basándose en variables en tiempo de ejecución, como el tamaño de la ventana, la resolución del dispositivo y las preferencias opcionales del usuario. Además, los documentos dinámicos ofrecen características de documento avanzadas, como paginación y columnas. En este tema se proporciona información general sobre los documentos dinámicos y cómo crearlos.

<a name="what_is_a_flow_document"></a>

## <a name="what-is-a-flow-document"></a>Qué es un documento dinámico

Un documento dinámico está diseñado para "redistribuir el contenido" según el tamaño de la ventana, la resolución del dispositivo y otras variables del entorno. Además, los documentos dinámicos tienen varias características integradas, como la búsqueda, los modos de visualización que optimizan la legibilidad, y la capacidad de cambiar el tamaño y el aspecto de las fuentes. Los documentos dinámicos se utilizan mejor cuando la facilidad de lectura es el escenario principal de consumo del documento. En cambio, los documentos fijos están diseñados para tener una presentación estática. Los documentos fijos son útiles cuando la fidelidad del contenido de origen es esencial. Consulte [documentos en WPF](documents-in-wpf.md) para obtener más información sobre los distintos tipos de documentos.

En la ilustración siguiente se muestra un ejemplo de documento dinámico visualizado en varias ventanas de tamaños diferentes. A medida que cambia el área de visualización, el contenido se redistribuye para aprovechar mejor el espacio disponible.

![Cambio de flujo del contenido de documentos de flujo](./media/edocs-flowdocument.png "eDocs_FlowDocument")

Tal como se muestra en la imagen anterior, el contenido dinámico puede incluir muchos componentes, como párrafos, listas, imágenes, etc. Estos componentes corresponden a elementos de marcado y objetos en el código de procedimiento. Veremos estas clases en detalle más adelante en la sección [clases relacionadas con el flujo](#flow_related_classes) de esta información general. Por ahora, este es un ejemplo de código simple que crea un documento dinámico que consta de un párrafo con algún texto en negrita y una lista.

[!code-xaml[FlowOvwSnippets_snip#SimpleFlowExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SimpleFlowExample.xaml#simpleflowexamplewholepage)]

[!code-csharp[FlowOvwSnippets_procedural_snip#SimpleFlowCodeOnlyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/SimpleFlowExample.cs#simpleflowcodeonlyexamplewholepage)]
[!code-vb[FlowOvwSnippets_procedural_snip#SimpleFlowCodeOnlyExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/SimpleFlowExample.vb#simpleflowcodeonlyexamplewholepage)]

En la ilustración siguiente se muestra el aspecto de este fragmento de código.

![Captura de pantalla: Ejemplo de FlowDocument representado](./media/flow-ovw-first-example.png "Flow_Ovw_First_Example")

En este ejemplo, el <xref:System.Windows.Controls.FlowDocumentReader> control se usa para hospedar el contenido dinámico. Vea [tipos de documentos dinámicos](#flow_document_types) para obtener más información sobre los controles de hospedaje de contenido dinámico. <xref:System.Windows.Documents.Paragraph><xref:System.Windows.Documents.List> <xref:System.Windows.Documents.ListItem> los elementos,, y <xref:System.Windows.Documents.Bold> se utilizan para controlar el formato del contenido, en función de su orden en el marcado. Por ejemplo, el <xref:System.Windows.Documents.Bold> elemento abarca solo parte del texto del párrafo; como resultado, solo esa parte del texto está en negrita. Si ha utilizado HTML, esto le resultará familiar.

Como se resalta en la ilustración anterior, hay varias características integradas en los documentos dinámicos:

- Buscar: permite al usuario realizar una búsqueda de texto completo en todo un documento.

- Modo de visualización: el usuario puede seleccionar su modo de visualización preferido, incluido el modo de visualización de una sola página (una página a la vez), el modo de visualización de dos página a la vez (formato de lectura de libro) y un modo de desplazamiento continuo (sin límite).  Para obtener más información acerca de estos modos de visualización, vea <xref:System.Windows.Controls.FlowDocumentReaderViewingMode> .

- Controles de navegación de página: si el modo de visualización del documento utiliza páginas, los controles de navegación de páginas incluyen un botón para ir a la página siguiente (flecha abajo) o la página anterior (flecha arriba), así como indicadores para el número de página actual y el número total de páginas. Las páginas también pueden voltearse mediante las teclas de flecha del teclado.

- Zoom: los controles de zoom permiten al usuario aumentar o disminuir el nivel de zoom haciendo clic en los botones de más o menos, respectivamente. Los controles de zoom incluyen también un control deslizante para ajustar el nivel de zoom. Para más información, consulte <xref:System.Windows.Controls.FlowDocumentReader.Zoom%2A>.

Estas características pueden modificarse según el control utilizado para hospedar el contenido dinámico. En la siguiente sección se describen los distintos controles.

<a name="flow_document_types"></a>

## <a name="flow-document-types"></a>Tipos de documentos dinámicos

La visualización del contenido de los documentos dinámicos y cómo aparece depende de qué objeto se utilice para hospedar el contenido dinámico. Hay cuatro controles que admiten la visualización del contenido dinámico: <xref:System.Windows.Controls.FlowDocumentReader> ,, <xref:System.Windows.Controls.FlowDocumentPageViewer> <xref:System.Windows.Controls.RichTextBox> y <xref:System.Windows.Controls.FlowDocumentScrollViewer> . Estos controles se describen brevemente a continuación.

> [!NOTE]
> <xref:System.Windows.Documents.FlowDocument>se requiere para hospedar directamente el contenido dinámico, por lo que todos estos controles de visualización utilizan <xref:System.Windows.Documents.FlowDocument> para habilitar el hospedaje del contenido dinámico.

### <a name="flowdocumentreader"></a>FlowDocumentReader

<xref:System.Windows.Controls.FlowDocumentReader>incluye características que permiten al usuario elegir dinámicamente entre distintos modos de visualización, como el modo de visualización de una sola página (de una página a la vez), un modo de visualización de dos páginas a la vez (formato de lectura de libro) y un modo de visualización de desplazamiento continuo (sin límite). Para obtener más información acerca de estos modos de visualización, vea <xref:System.Windows.Controls.FlowDocumentReaderViewingMode> . Si no necesita la capacidad de cambiar dinámicamente entre distintos modos de visualización, <xref:System.Windows.Controls.FlowDocumentPageViewer> y <xref:System.Windows.Controls.FlowDocumentScrollViewer> proporciona visores de contenido dinámico más ligeros que se corrigen en un modo de visualización determinado.

### <a name="flowdocumentpageviewer-and-flowdocumentscrollviewer"></a>FlowDocumentPageViewer y FlowDocumentScrollViewer

<xref:System.Windows.Controls.FlowDocumentPageViewer>muestra el contenido en el modo de visualización de una página a la vez, mientras que <xref:System.Windows.Controls.FlowDocumentScrollViewer> muestra el contenido en modo de desplazamiento continuo. <xref:System.Windows.Controls.FlowDocumentPageViewer>Y <xref:System.Windows.Controls.FlowDocumentScrollViewer> se corrigen en un modo de visualización determinado. Comparar con <xref:System.Windows.Controls.FlowDocumentReader> , que incluye características que permiten al usuario elegir dinámicamente entre distintos modos de visualización (tal y como lo proporciona la <xref:System.Windows.Controls.FlowDocumentReaderViewingMode> enumeración), a costa de que el uso de más recursos sea mayor que <xref:System.Windows.Controls.FlowDocumentPageViewer> o <xref:System.Windows.Controls.FlowDocumentScrollViewer> .

De manera predeterminada, siempre se muestra una barra de desplazamiento vertical y una barra de desplazamiento horizontal se vuelve visible cuando es necesario. La interfaz de usuario predeterminada de no <xref:System.Windows.Controls.FlowDocumentScrollViewer> incluye una barra de herramientas; sin embargo, la <xref:System.Windows.Controls.FlowDocumentScrollViewer.IsToolBarVisible%2A> propiedad se puede usar para habilitar una barra de herramientas integrada.

### <a name="richtextbox"></a>RichTextBox

Se usa <xref:System.Windows.Controls.RichTextBox> cuando se desea permitir al usuario editar el contenido dinámico. Por ejemplo, si desea crear un editor que permita a un usuario manipular elementos como tablas, formato en cursiva y negrita, etc., se usaría <xref:System.Windows.Controls.RichTextBox> . Vea [información general de RichTextBox](../controls/richtextbox-overview.md) para obtener más información.

> [!NOTE]
> El contenido dinámico dentro de no se <xref:System.Windows.Controls.RichTextBox> comporta exactamente igual que el contenido dinámico contenido en otros controles. Por ejemplo, no hay ninguna columna en <xref:System.Windows.Controls.RichTextBox> y, por lo tanto, no hay ningún comportamiento de cambio de tamaño automático. Además, las características integradas normalmente del contenido dinámico, como la búsqueda, el modo de visualización, la navegación de páginas y el zoom, no están disponibles en <xref:System.Windows.Controls.RichTextBox> .

<a name="creating_flow_content"></a>

## <a name="creating-flow-content"></a>Crear contenido dinámico

El contenido dinámico puede ser complejo y consta de varios elementos, como texto, imágenes, tablas e incluso <xref:System.Windows.UIElement> clases derivadas como controles. Para entender cómo crear contenido dinámico complejo, los puntos siguientes son fundamentales:

- **Clases relacionadas con el flujo**: cada clase que se utiliza en el contenido dinámico tiene un propósito específico. Además, la relación jerárquica entre las clases dinámicas le ayuda a comprender cómo se utilizan. Por ejemplo, las clases derivadas de la <xref:System.Windows.Documents.Block> clase se usan para contener otros objetos mientras que las clases derivadas de <xref:System.Windows.Documents.Inline> contienen objetos que se muestran.

- **Esquema de contenido**: un documento dinámico puede requerir un número importante de elementos anidados. El esquema de contenido especifica las relaciones posibles entre elementos primarios y secundarios.

En las secciones siguientes se repasará cada una de estas áreas con más detalle.

<a name="flow_related_classes"></a>

## <a name="flow-related-classes"></a>Clases relacionadas con el flujo

En el diagrama siguiente se muestran los objetos más utilizados con el contenido dinámico:

![Diagrama: Jerarquía de clases de elementos de contenido dinámico](./media/flow-class-hierarchy.png "Flow_Class_Hierarchy")

A los efectos del contenido dinámico, hay dos categorías importantes:

1. **Clases derivadas de Block**: también denominadas "elementos de contenido de Block" o simplemente "elementos Block". Los elementos que heredan de <xref:System.Windows.Documents.Block> se pueden usar para agrupar elementos bajo un elemento primario común o para aplicar atributos comunes a un grupo.

2. **Clases derivadas de Inline**: también denominadas "elementos de contenido de Inline" o simplemente "elementos de Inline". Los elementos que heredan de <xref:System.Windows.Documents.Inline> están incluidos dentro de un elemento de bloque u otro elemento insertado. Los elementos Inline se utilizan a menudo como contenedor directo del contenido que se representa en la pantalla. Por ejemplo, un <xref:System.Windows.Documents.Paragraph> elemento (bloque) puede contener un <xref:System.Windows.Documents.Run> (elemento insertado) pero <xref:System.Windows.Documents.Run> realmente contiene el texto que se representa en la pantalla.

Cada clase de estas dos categorías se describe brevemente a continuación.

### <a name="block-derived-classes"></a>Clases derivadas de Block

**Paragraph**

<xref:System.Windows.Documents.Paragraph>se utiliza normalmente para agrupar el contenido en un párrafo. El uso más sencillo y común de Paragraph es crear un párrafo de texto.

[!code-xaml[FlowOvwSnippets_snip#ParagraphExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/ParagraphExample.xaml#paragraphexamplewholepage)]

[!code-csharp[FlowOvwSnippets_procedural_snip#ParagraphCodeOnlyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/ParagraphExample.cs#paragraphcodeonlyexamplewholepage)]
[!code-vb[FlowOvwSnippets_procedural_snip#ParagraphCodeOnlyExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/ParagraphExample.vb#paragraphcodeonlyexamplewholepage)]

Sin embargo, también puede contener otros elementos derivados de inline, como verá a continuación.

**Sección**

<xref:System.Windows.Documents.Section>solo se usa para contener otros <xref:System.Windows.Documents.Block> elementos derivados de. No aplica ningún formato predeterminado a los elementos que contiene. Sin embargo, los valores de propiedad establecidos en <xref:System.Windows.Documents.Section> se aplican a sus elementos secundarios. Una sección permite iterar mediante programación en su colección secundaria. <xref:System.Windows.Documents.Section>se utiliza de forma similar a la \<DIV> etiqueta en HTML.

En el ejemplo siguiente, se definen tres párrafos en uno <xref:System.Windows.Documents.Section> . La sección tiene un <xref:System.Windows.Documents.TextElement.Background%2A> valor de propiedad de rojo, por lo que el color de fondo de los párrafos también es rojo.

[!code-xaml[FlowOvwSnippets_snip#SectionExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SectionExample.xaml#sectionexamplewholepage)]

[!code-csharp[FlowOvwSnippets_procedural_snip#SectionCodeOnlyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/SectionExample.cs#sectioncodeonlyexamplewholepage)]
[!code-vb[FlowOvwSnippets_procedural_snip#SectionCodeOnlyExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/SectionExample.vb#sectioncodeonlyexamplewholepage)]

**BlockUIContainer**

<xref:System.Windows.Documents.BlockUIContainer>habilita <xref:System.Windows.UIElement> los elementos (es decir, un <xref:System.Windows.Controls.Button> ) que se van a insertar en el contenido dinámico derivado del bloque. <xref:System.Windows.Documents.InlineUIContainer>(consulte a continuación) se usa para insertar <xref:System.Windows.UIElement> elementos en el contenido dinámico derivado de la línea. <xref:System.Windows.Documents.BlockUIContainer>y <xref:System.Windows.Documents.InlineUIContainer> son importantes porque no hay ninguna otra manera de usar un <xref:System.Windows.UIElement> elemento en el contenido dinámico a menos que esté dentro de uno de estos dos elementos.

En el ejemplo siguiente se muestra cómo usar el <xref:System.Windows.Documents.BlockUIContainer> elemento para hospedar <xref:System.Windows.UIElement> objetos dentro del contenido dinámico.

[!code-xaml[SpanSnippets#_BlockUIXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml#_blockuixaml)]

En la ilustración siguiente se muestra cómo se representa este ejemplo:

![Captura de pantalla que muestra un UIElement incrustado en el contenido dinámico.](./media/flow-document-overview/embedded-blockuicontainer.png)

**Lista**

<xref:System.Windows.Documents.List>se utiliza para crear una lista con viñetas o numérica. Establezca la <xref:System.Windows.Documents.List.MarkerStyle%2A> propiedad en un <xref:System.Windows.TextMarkerStyle> valor de enumeración para determinar el estilo de la lista. En el ejemplo siguiente se muestra cómo crear una lista sencilla.

[!code-xaml[FlowOvwSnippets_snip#ListExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/ListExample.xaml#listexamplewholepage)]

[!code-csharp[FlowOvwSnippets_procedural_snip#ListCodeOnlyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/ListExample.cs#listcodeonlyexamplewholepage)]
[!code-vb[FlowOvwSnippets_procedural_snip#ListCodeOnlyExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/ListExample.vb#listcodeonlyexamplewholepage)]

> [!NOTE]
> <xref:System.Windows.Documents.List>es el único elemento de flujo que utiliza <xref:System.Windows.Documents.ListItemCollection> para administrar los elementos secundarios.

**Table**

<xref:System.Windows.Documents.Table>se utiliza para crear una tabla. <xref:System.Windows.Documents.Table>es similar al <xref:System.Windows.Controls.Grid> elemento, pero tiene más funciones y, por lo tanto, requiere mayor sobrecarga de recursos. Dado que <xref:System.Windows.Controls.Grid> es <xref:System.Windows.UIElement> , no se puede usar en el contenido dinámico a menos que esté incluido en <xref:System.Windows.Documents.BlockUIContainer> o <xref:System.Windows.Documents.InlineUIContainer> . Para obtener más información sobre <xref:System.Windows.Documents.Table> , vea [información general sobre tablas](table-overview.md).

### <a name="inline-derived-classes"></a>Clases derivadas de Inline

**Ejecutar**

<xref:System.Windows.Documents.Run>se utiliza para contener texto sin formato. Es posible que espere que <xref:System.Windows.Documents.Run> se usen objetos en el contenido dinámico. Sin embargo, en el marcado, <xref:System.Windows.Documents.Run> no es necesario usar elementos explícitamente. <xref:System.Windows.Documents.Run>se necesita para usarse al crear o manipular documentos dinámicos mediante código. Por ejemplo, en el marcado siguiente, el primero <xref:System.Windows.Documents.Paragraph> especifica el <xref:System.Windows.Documents.Run> elemento explícitamente mientras que el segundo no. Ambos párrafos generan el mismo resultado.

[!code-xaml[FlowOvwSnippets_snip#RunExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/RunSnippetsExample.xaml#runexample1)]

> [!NOTE]
> A partir de la .NET Framework 4, la <xref:System.Windows.Documents.Run.Text%2A> propiedad del <xref:System.Windows.Documents.Run> objeto es una propiedad de dependencia. Puede enlazar la <xref:System.Windows.Documents.Run.Text%2A> propiedad a un origen de datos, como <xref:System.Windows.Controls.TextBlock> . La <xref:System.Windows.Documents.Run.Text%2A> propiedad es totalmente compatible con el enlace unidireccional. La <xref:System.Windows.Documents.Run.Text%2A> propiedad también admite el enlace bidireccional, excepto <xref:System.Windows.Controls.RichTextBox> . Para obtener un ejemplo, consulte <xref:System.Windows.Documents.Run.Text%2A?displayProperty=nameWithType>.

**Extienda**

<xref:System.Windows.Documents.Span>agrupa otros elementos de contenido alineado. No se aplica ninguna representación inherente al contenido dentro de un <xref:System.Windows.Documents.Span> elemento. Sin embargo, los elementos que heredan de <xref:System.Windows.Documents.Span> <xref:System.Windows.Documents.Hyperlink> , <xref:System.Windows.Documents.Bold> <xref:System.Windows.Documents.Italic> y <xref:System.Windows.Documents.Underline> aplican el formato al texto.

A continuación se muestra un ejemplo de <xref:System.Windows.Documents.Span> que se usa para incluir contenido alineado, como texto, un <xref:System.Windows.Documents.Bold> elemento y un <xref:System.Windows.Controls.Button> .

[!code-xaml[FlowOvwSnippets_snip#SpanExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SpanExample.xaml#spanexamplewholepage)]

En la captura de pantalla siguiente se muestra cómo se representa este ejemplo.

![Captura de pantalla: Ejemplo de Span representado](./media/flow-spanexample.gif "Flow_SpanExample")

**InlineUIContainer**

<xref:System.Windows.Documents.InlineUIContainer>habilita <xref:System.Windows.UIElement> los elementos (es decir, un control como <xref:System.Windows.Controls.Button> ) que se van a incrustar en un <xref:System.Windows.Documents.Inline> elemento de contenido. Este elemento es el equivalente en línea que se <xref:System.Windows.Documents.BlockUIContainer> ha descrito anteriormente. A continuación se muestra un ejemplo que usa <xref:System.Windows.Documents.InlineUIContainer> para insertar una <xref:System.Windows.Controls.Button> línea en un <xref:System.Windows.Documents.Paragraph> .

[!code-xaml[FlowOvwSnippets_snip#InlineUIContainerExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/InlineUIContainerExample.xaml#inlineuicontainerexamplewholepage)]

[!code-csharp[FlowOvwSnippets_procedural_snip#InlineUIContainerCodeOnlyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/InlineUIContainerExample.cs#inlineuicontainercodeonlyexamplewholepage)]
[!code-vb[FlowOvwSnippets_procedural_snip#InlineUIContainerCodeOnlyExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/InlineUIContainerExample.vb#inlineuicontainercodeonlyexamplewholepage)]

> [!NOTE]
> <xref:System.Windows.Documents.InlineUIContainer>no necesita usarse explícitamente en el marcado. Si lo omite, se <xref:System.Windows.Documents.InlineUIContainer> creará de todos modos cuando se compile el código.

**Figure y Floater**

<xref:System.Windows.Documents.Figure>y <xref:System.Windows.Documents.Floater> se usan para insertar contenido en documentos dinámicos con propiedades de selección de ubicación que se pueden personalizar independientemente del flujo de contenido principal. <xref:System.Windows.Documents.Figure><xref:System.Windows.Documents.Floater>los elementos o se usan a menudo para resaltar o acentuar partes del contenido, para hospedar imágenes auxiliares u otro contenido dentro del flujo de contenido principal, o para inyectar contenido de relación imprecisa como anuncios.

En el ejemplo siguiente se muestra cómo insertar un <xref:System.Windows.Documents.Figure> en un párrafo de texto.

[!code-xaml[FlowOvwSnippets_snip#FigureExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/FigureExample.xaml#figureexamplewholepage)]

[!code-csharp[FlowOvwSnippets_procedural_snip#FigureCodeOnlyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/FigureExample.cs#figurecodeonlyexamplewholepage)]
[!code-vb[FlowOvwSnippets_procedural_snip#FigureCodeOnlyExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/FigureExample.vb#figurecodeonlyexamplewholepage)]

En la ilustración siguiente se muestra cómo se representa este ejemplo.

![Captura de pantalla: Ejemplo de figura](./media/flow-ovw-figure-example.png "Flow_Ovw_Figure_Example")

<xref:System.Windows.Documents.Figure>y <xref:System.Windows.Documents.Floater> difieren de varias maneras y se utilizan para distintos escenarios.

**Figura**

- Se pueden determinar su posición: puede establecer sus delimitadores horizontal y vertical para acoplarlo con respecto a la página, el contenido, la columna o el párrafo. También puede utilizar sus <xref:System.Windows.Documents.Figure.HorizontalOffset%2A> propiedades y <xref:System.Windows.Documents.Figure.VerticalOffset%2A> para especificar desplazamientos arbitrarios.

- Es ajustable a más de una columna: puede establecer el <xref:System.Windows.Documents.Figure> alto y el ancho en múltiplos del alto o el ancho de la página, el contenido o la columna. Tenga en cuenta que, en el caso de la página y el contenido, no se permiten múltiplos mayores que 1. Por ejemplo, puede establecer el ancho de un <xref:System.Windows.Documents.Figure> para que sea "página 0,5" o "0,25 de contenido" o "2 columnas". También puede establecer el alto y ancho en valores absolutos de píxeles.

- No pagina: Si el contenido dentro de no <xref:System.Windows.Documents.Figure> cabe dentro de <xref:System.Windows.Documents.Figure> , se representará el contenido que quepa y se perderá el contenido restante.

**Floater:**

- No se puede establecer su posición y se representará en cualquier espacio que pueda estar a su disposición. No se puede establecer el desplazamiento o el delimitador a <xref:System.Windows.Documents.Floater> .

- No se puede ajustar a más de una columna: de forma predeterminada, tiene <xref:System.Windows.Documents.Floater> un tamaño de una columna. Tiene una <xref:System.Windows.Documents.Floater.Width%2A> propiedad que se puede establecer en un valor de píxel absoluto, pero si este valor es mayor que un ancho de columna, se omite y el punto flotante tiene un tamaño en una columna. Puede ajustarlo a menos de una columna estableciendo el ancho de píxel correcto, pero el tamaño no es relativo a la columna, por lo que "0.5 Column" no es una expresión válida para <xref:System.Windows.Documents.Floater> width. <xref:System.Windows.Documents.Floater>no tiene ninguna propiedad de alto y no se puede establecer su alto, es decir, el alto depende del contenido.

- <xref:System.Windows.Documents.Floater>paginaciones: Si su contenido en el ancho especificado se extiende a más de 1 alto de columna, el Floater se rompe y se pagina en la columna siguiente, en la página siguiente, etc.

 <xref:System.Windows.Documents.Figure>es un buen lugar para colocar contenido independiente en el que desea controlar el tamaño y la posición, y está seguro de que el contenido se ajustará al tamaño especificado. <xref:System.Windows.Documents.Floater>es un buen lugar para colocar más contenido de flujo libre que fluya de forma similar al contenido de la Página principal, pero que se separa de él.

**LineBreak**

<xref:System.Windows.Documents.LineBreak>hace que se produzca un salto de línea en el contenido dinámico. El siguiente ejemplo muestra el uso de <xref:System.Windows.Documents.LineBreak>.

[!code-xaml[FlowOvwSnippets_snip#LineBreakExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/LineBreakExample.xaml#linebreakexamplewholepage)]

En la captura de pantalla siguiente se muestra cómo se representa este ejemplo.

![Captura de pantalla: Ejemplo de LineBreak](./media/flow-ovw-linebreakexample.png "Flow_Ovw_LineBreakExample")

### <a name="flow-collection-elements"></a>Elementos de colección dinámica

En muchos de los ejemplos anteriores, <xref:System.Windows.Documents.BlockCollection> y <xref:System.Windows.Documents.InlineCollection> se usan para construir contenido dinámico mediante programación. Por ejemplo, para agregar elementos a un <xref:System.Windows.Documents.Paragraph> , puede utilizar la sintaxis:

```csharp
myParagraph.Inlines.Add(new Run("Some text"));
```

Esto agrega un <xref:System.Windows.Documents.Run> a la <xref:System.Windows.Documents.InlineCollection> de <xref:System.Windows.Documents.Paragraph> .  Es el mismo que el implícito <xref:System.Windows.Documents.Run> encontrado dentro de un <xref:System.Windows.Documents.Paragraph> en el marcado:

```xml
<Paragraph>
Some Text
</Paragraph>
```

Como ejemplo del uso de <xref:System.Windows.Documents.BlockCollection> , en el ejemplo siguiente se crea una nueva <xref:System.Windows.Documents.Section> y, a continuación, se usa el método **Add** para agregar una nueva <xref:System.Windows.Documents.Paragraph> al <xref:System.Windows.Documents.Section> contenido.

[!code-csharp[FlowDocumentSnippets#_SectionBlocksAdd](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksadd)]
[!code-vb[FlowDocumentSnippets#_SectionBlocksAdd](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksadd)]

Además de agregar elementos a una colección dinámica, también puede quitar elementos.  En el ejemplo siguiente se elimina el último <xref:System.Windows.Documents.Inline> elemento de <xref:System.Windows.Documents.Span> .

[!code-csharp[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesremovelast)]
[!code-vb[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesremovelast)]

En el siguiente ejemplo se borra todo el contenido ( <xref:System.Windows.Documents.Inline> elementos) de <xref:System.Windows.Documents.Span> .

[!code-csharp[SpanSnippets#_SpanInlinesClear](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesclear)]
[!code-vb[SpanSnippets#_SpanInlinesClear](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesclear)]

Cuando trabaje con contenido dinámico mediante programación, probablemente utilizará mucho estas colecciones.

El hecho de que un elemento de flujo use <xref:System.Windows.Documents.InlineCollection> (inserta) o <xref:System.Windows.Documents.BlockCollection> (bloques) para contener sus elementos secundarios depende del tipo de elementos secundarios ( <xref:System.Windows.Documents.Block> o <xref:System.Windows.Documents.Inline> ) que pueda contener el elemento primario. Las reglas de contención para los elementos de contenido dinámico se resumen en el esquema de contenido en la sección siguiente.

> [!NOTE]
> Hay un tercer tipo de colección que se usa con el contenido dinámico, <xref:System.Windows.Documents.ListItemCollection> pero esta colección solo se usa con un <xref:System.Windows.Documents.List> . Además, hay varias colecciones que se utilizan con <xref:System.Windows.Documents.Table> . Vea [información general sobre tablas](table-overview.md) para obtener más información.

<a name="content_schema"></a>

## <a name="content-schema"></a>Esquema de contenido

Dado el número de los distintos elementos de contenido dinámico, puede resultar abrumador mantener un seguimiento de qué tipo de elementos secundarios puede contener un elemento. En el diagrama siguiente se resumen las reglas de contención para los elementos dinámicos. Las flechas representan las relaciones posibles entre elementos primarios y secundarios.

![Diagrama: Esquema de contención de contenido dinámico](./media/flow-content-schema.png "Flow_Content_Schema")

Como se puede observar en el diagrama anterior, los elementos secundarios permitidos para un elemento no están determinados necesariamente por si se trata de un <xref:System.Windows.Documents.Block> elemento o de un <xref:System.Windows.Documents.Inline> elemento. Por ejemplo, un <xref:System.Windows.Documents.Span> elemento (un <xref:System.Windows.Documents.Inline> elemento) solo puede tener <xref:System.Windows.Documents.Inline> elementos secundarios mientras <xref:System.Windows.Documents.Figure> que un elemento (también un <xref:System.Windows.Documents.Inline> elemento) solo puede tener <xref:System.Windows.Documents.Block> elementos secundarios. Por tanto, un diagrama es útil para determinar rápidamente qué elemento puede incluirse en otro. Por ejemplo, vamos a usar el diagrama para determinar cómo construir el contenido dinámico de un <xref:System.Windows.Controls.RichTextBox> .

**1.** <xref:System.Windows.Controls.RichTextBox> debe contener un <xref:System.Windows.Documents.FlowDocument> que a su vez debe contener un <xref:System.Windows.Documents.Block> objeto derivado de. A continuación, se muestra el segmento correspondiente del diagrama anterior.

![Diagrama: Reglas de contención de RichTextBox](./media/flow-ovw-schemawalkthrough1.png "Flow_Ovw_SchemaWalkThrough1")

Llegados a este punto, esta es la apariencia que podría tener el marcado.

[!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough1](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough1)]

**2.** de acuerdo con el diagrama, hay varios <xref:System.Windows.Documents.Block> elementos entre los que elegir <xref:System.Windows.Documents.Paragraph> , como,, <xref:System.Windows.Documents.Section> <xref:System.Windows.Documents.Table> , <xref:System.Windows.Documents.List> y <xref:System.Windows.Documents.BlockUIContainer> (vea clases derivadas de bloques anteriores). Supongamos que queremos un <xref:System.Windows.Documents.Table> . Según el diagrama anterior, contiene un <xref:System.Windows.Documents.Table> elemento que <xref:System.Windows.Documents.TableRowGroup> contiene <xref:System.Windows.Documents.TableRow> elementos, que contienen <xref:System.Windows.Documents.TableCell> elementos que contienen un <xref:System.Windows.Documents.Block> objeto derivado de. A continuación se muestra el segmento correspondiente de <xref:System.Windows.Documents.Table> tomado del diagrama anterior.

![Diagrama: esquema primario&#47;secundario para la tabla](./media/flow-ovw-schemawalkthrough2.png "Flow_Ovw_SchemaWalkThrough2")

A continuación, se muestra el marcado correspondiente.

[!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough2](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough2)]

**3.** de nuevo, se requieren uno o varios <xref:System.Windows.Documents.Block> elementos debajo de <xref:System.Windows.Documents.TableCell> . Para facilitar el proceso, vamos a colocar texto dentro de la celda. Para ello, se usa <xref:System.Windows.Documents.Paragraph> con un <xref:System.Windows.Documents.Run> elemento. A continuación se muestran los segmentos correspondientes del diagrama que muestra que un <xref:System.Windows.Documents.Paragraph> puede tomar un <xref:System.Windows.Documents.Inline> elemento y que un <xref:System.Windows.Documents.Run> (un <xref:System.Windows.Documents.Inline> elemento) solo puede tomar texto sin formato.

![Diagrama: esquema primario&#47;secundario para el párrafo](./media/flow-ovw-schemawalkthrough3.png "Flow_Ovw_SchemaWalkThrough3")

![Diagrama: principal&#47;esquema secundario para ejecutar](./media/flow-ovw-schemawalkthrough4.png "Flow_Ovw_SchemaWalkThrough4")

A continuación se muestra el ejemplo completo en el marcado.

[!code-xaml[FlowOvwSnippets_snip#SchemaExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SchemaExample.xaml#schemaexamplewholepage)]

<a name="customizing_text"></a>

## <a name="customizing-text"></a>Personalizar texto

En general, el texto es el tipo de contenido más frecuente de un documento dinámico. Aunque los objetos descritos anteriormente pueden utilizarse para controlar la mayoría de los aspectos de cómo se representa el texto, hay otros métodos para personalizar el texto, según se describen en esta sección.

### <a name="text-decorations"></a>Decoraciones de texto

Las decoraciones de texto le permiten aplicar efectos de subrayado, línea alta, línea base y tachado al texto (consulte las imágenes siguientes). Estas decoraciones se agregan utilizando la <xref:System.Windows.Documents.Inline.TextDecorations%2A> propiedad que se expone mediante una serie de objetos <xref:System.Windows.Documents.Inline> , como, <xref:System.Windows.Documents.Paragraph> , <xref:System.Windows.Controls.TextBlock> y <xref:System.Windows.Controls.TextBox> .

En el ejemplo siguiente se muestra cómo se establece la propiedad <xref:System.Windows.Documents.Paragraph.TextDecorations%2A> de <xref:System.Windows.Documents.Paragraph>.

[!code-xaml[InlineSnippets#_Paragraph_TextDecXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/InlineSnippets/CSharp/Window1.xaml#_paragraph_textdecxaml)]

[!code-csharp[InlineSnippets#_Paragraph_TextDec](~/samples/snippets/csharp/VS_Snippets_Wpf/InlineSnippets/CSharp/Window1.xaml.cs#_paragraph_textdec)]
[!code-vb[InlineSnippets#_Paragraph_TextDec](~/samples/snippets/visualbasic/VS_Snippets_Wpf/InlineSnippets/visualbasic/window1.xaml.vb#_paragraph_textdec)]

En la ilustración siguiente se muestra cómo se representa este ejemplo.

![Captura de pantalla: Texto con efecto de tachado predeterminado](./media/inline-textdec-strike.png "Inline_TextDec_Strike")

Las ilustraciones siguientes muestran cómo se **representan las decoraciones de**subrayado, **línea de base**y **subrayado** , respectivamente.

![Captura de pantalla: TextDecorator de línea alta](./media/inline-textdec-over.png "Inline_TextDec_Over")

![Captura de pantalla: Efecto de línea base predeterminada en texto](./media/inline-textdec-base.png "Inline_TextDec_Base")

![Captura de pantalla: Texto con efecto de subrayado predeterminado](./media/inline-textdec-under.png "Inline_TextDec_Under")

### <a name="typography"></a>Tipografía

La <xref:System.Windows.Documents.TextElement.Typography%2A> propiedad se expone mediante la mayoría del contenido relacionado con el flujo <xref:System.Windows.Documents.TextElement> , incluidos,, <xref:System.Windows.Documents.FlowDocument> <xref:System.Windows.Controls.TextBlock> y <xref:System.Windows.Controls.TextBox> . Esta propiedad se utiliza para controlar características/variaciones tipográficas del texto (es decir, versalitas o mayúsculas, superíndices y subíndices, etc.).

En el ejemplo siguiente se muestra cómo establecer el <xref:System.Windows.Documents.TextElement.Typography%2A> atributo, utilizando <xref:System.Windows.Documents.Paragraph> como elemento de ejemplo.

[!code-xaml[TextElementSnippets#_TextElement_TypogXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextElementSnippets/CSharp/Window1.xaml#_textelement_typogxaml)]

En la ilustración siguiente se muestra cómo se representa este ejemplo.

![Captura de pantalla: Texto con tipografía modificada](./media/textelement-typog.png "TextElement_Typog")

En cambio, en la siguiente ilustración se muestra cómo se representa un ejemplo similar con propiedades tipográficas predeterminadas.

![Captura de pantalla: Texto con tipografía modificada](./media/textelement-typog-default.png "TextElement_Typog_Default")

En el ejemplo siguiente se muestra cómo establecer la <xref:System.Windows.Controls.TextBox.Typography%2A> propiedad mediante programación.

[!code-csharp[TextElementSnippets#_TextElement_Typog](~/samples/snippets/csharp/VS_Snippets_Wpf/TextElementSnippets/CSharp/Window1.xaml.cs#_textelement_typog)]
[!code-vb[TextElementSnippets#_TextElement_Typog](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextElementSnippets/visualbasic/window1.xaml.vb#_textelement_typog)]

Consulte [tipografía en WPF](typography-in-wpf.md) para obtener más información sobre la tipografía.

## <a name="see-also"></a>Consulte también

- [Texto](optimizing-performance-text.md)
- [Tipografía en WPF](typography-in-wpf.md)
- [Temas "Cómo..."](flow-content-elements-how-to-topics.md)
- [Información general sobre el modelo de contenido de TextElement](textelement-content-model-overview.md)
- [Información general sobre el control RichTextBox](../controls/richtextbox-overview.md)
- [Documentos en WPF](documents-in-wpf.md)
- [Información general sobre tablas](table-overview.md)
- [Información general sobre anotaciones](annotations-overview.md)
