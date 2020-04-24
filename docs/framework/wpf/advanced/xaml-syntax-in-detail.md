---
title: Detalles de la sintaxis XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XML [WPF], namespaces
- XAML [WPF], parsing of attributes
- parsing of attributes [WPF]
- XAML [WPF], markup extensions
- attached properties [WPF]
- tag syntax [XAML]
- markup extensions [WPF]
- XAML [WPF], object element syntax
- XAML [WPF], syntax terminology
- attached events [WPF]
- lookup semantics [WPF]
- XAML [WPF], attached events
- XAML [WPF], content syntax
- XAML [WPF], lookup semantics
- content syntax [WPF]
- object element syntax [WPF]
- syntax terminology [XAML]
- XAML [WPF], attached properties
- attributes [XAML], parsing
- XAML [WPF], tag syntax
- XAML [WPF], attribute syntax
- property element syntax [WPF]
- terminology [XAML]
- namespaces [WPF], XML
- attribute syntax [XAML]
- XAML [WPF], property element syntax
ms.assetid: 67cce290-ca26-4c41-a797-b68aabc45479
ms.openlocfilehash: 5f8bb862ce443fd7397036b10f69cda65a6960bc
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646141"
---
# <a name="xaml-syntax-in-detail"></a>Detalles de la sintaxis XAML
En este tema se definen los términos que se usan para describir los elementos de la sintaxis XAML. Estos términos se usan con frecuencia en el resto de esta documentación, tanto para la documentación de WPF específicamente como para los otros marcos que usan XAML o los conceptos XAML básicos habilitados por la compatibilidad con el lenguaje XAML en el nivel System.Xaml. En este tema se amplía la terminología básica introducida en el tema Información general sobre [XAML (WPF).](../../../desktop-wpf/fundamentals/xaml.md)  

<a name="the_xaml_language_specification"></a>
## <a name="the-xaml-language-specification"></a>La especificación del lenguaje XAML  
 La terminología de sintaxis XAML definida aquí también se define o se hace referencia dentro de la especificación del lenguaje XAML. XAML es un lenguaje basado en XML y sigue o expande las reglas estructurales XML. Parte de la terminología se comparte o se basa en la terminología que se utiliza comúnmente al describir el lenguaje XML o el modelo de objetos de documento XML.  
  
 Para obtener más información acerca de la especificación del lenguaje XAML, descargue [ \[MS-XAML\] ](https://download.microsoft.com/download/0/A/6/0A6F7755-9AF5-448B-907D-13985ACCF53E/[MS-XAML].pdf) desde el Centro de descarga de Microsoft.  
  
<a name="xaml_and_clr"></a>
## <a name="xaml-and-clr"></a>XAML y CLR  
 XAML es un lenguaje de marcado. Common Language Runtime (CLR), tal como lo implica su nombre, habilita la ejecución en tiempo de ejecución. XAML no es por sí mismo uno de los lenguajes comunes que consume directamente el tiempo de ejecución de CLR. En su lugar, puede pensar que XAML admite su propio sistema de tipos. El sistema de análisis XAML determinado que usa WPFWPF se basa en el sistema de tipos CLR y CLR. Los tipos XAML se asignan a tipos CLR para crear instancias de una representación en tiempo de ejecución cuando se analiza XAML para WPF. Por este motivo, el resto de la discusión de la sintaxis en este documento incluirá referencias al sistema de tipos CLR, aunque las discusiones de sintaxis equivalentes en la especificación del lenguaje XAML no lo hacen. (Según el nivel de especificación del lenguaje XAML, los tipos XAML se podrían asignar a cualquier otro sistema de tipos, que no tiene que ser el CLR, pero que requeriría la creación y el uso de un analizador XAML diferente.)  
  
#### <a name="members-of-types-and-class-inheritance"></a>Miembros de Tipos y Herencia de Clases  
 Las propiedades y los eventos que [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aparecen como miembros XAML de un tipo a menudo se heredan de los tipos base. Por ejemplo, considere `<Button Background="Blue" .../>`este ejemplo: . La <xref:System.Windows.Controls.Control.Background%2A> propiedad no es una <xref:System.Windows.Controls.Button> propiedad declarada inmediatamente en la clase, si se va a examinar la definición de clase, los resultados de reflexión o la documentación. En <xref:System.Windows.Controls.Control.Background%2A> su lugar, <xref:System.Windows.Controls.Control> se hereda de la clase base.  
  
 El comportamiento de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] herencia de clases de los elementos XAML es una desviación significativa de una interpretación aplicada por el esquema del marcado XML. La herencia de clases puede volverse compleja, especialmente cuando las clases base intermedias son abstractas o cuando intervienen interfaces. Esta es una razón por la que el conjunto de elementos XAML y sus atributos permisibles es difícil de representar con precisión y completamente utilizando los tipos de esquema que se usan normalmente para la programación XML, como el formato DTD o XSD. Otra razón es que las características de extensibilidad y asignación de tipos del propio lenguaje XAML impiden la integridad de cualquier representación fija de los tipos y miembros permitidos.  
  
<a name="object_element_syntax"></a>
## <a name="object-element-syntax"></a>Sintaxis de elemento de objeto  
 *Sintaxis* de elemento de objeto es la sintaxis de marcado XAML que crea una instancia de una clase o estructura CLR mediante la declaración de un elemento XML. Esta sintaxis es similar a la sintaxis de elemento de otros lenguajes de marcado como HTML. La sintaxis del elemento de\<objeto comienza con un corchete angular izquierdo ( ), seguido inmediatamente por el nombre de tipo de la clase o estructura que se crea una instancia. Cero o más espacios pueden seguir el nombre de tipo, y también se pueden declarar cero o más atributos en el elemento de objeto, con uno o más espacios que separan cada par de nombre de atributo "valor". Por último, debe cumplirse una de las siguientes condiciones:  
  
- El elemento y la etiqueta deben cerrarse con una barra diagonal (/) seguida inmediatamente de un corchete de ángulo recto (>).  
  
- La etiqueta de apertura debe completarse con un corchete de ángulo recto (>). Otros elementos de objeto, elementos de propiedad o texto interno, pueden seguir la etiqueta de apertura. Exactamente qué contenido puede estar contenido aquí normalmente está restringido por el modelo de objetos del elemento. La etiqueta de cierre equivalente para el elemento de objeto también debe existir, en el anidamiento y equilibrio adecuados con otros pares de etiquetas de apertura y cierre.  
  
 XAML implementado por .NET tiene un conjunto de reglas que asignan elementos de objeto en tipos, atributos en propiedades o eventos y espacios de nombres XAML a espacios de nombres CLR más ensamblado. Para WPF wpf y .NET, los elementos de objeto XAML se asignan a tipos .NET tal como se definen en los ensamblados a los que se hace referencia y los atributos se asignan a los miembros de esos tipos. Al hacer referencia a un tipo CLR en XAML, también tiene acceso a los miembros heredados de ese tipo.  
  
 Por ejemplo, el ejemplo siguiente es la sintaxis <xref:System.Windows.Controls.Button> de elemento de objeto <xref:System.Windows.FrameworkElement.Name%2A> que crea una instancia nueva de la clase y también especifica un atributo y un valor para ese atributo:  
  
 [!code-xaml[XAMLOvwSupport#SyntaxOE](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#syntaxoe)]  
  
 El ejemplo siguiente es la sintaxis de elemento de objeto que también incluye la sintaxis de propiedad de contenido XAML. El texto interno contenido se usará <xref:System.Windows.Controls.TextBox> para establecer <xref:System.Windows.Controls.TextBox.Text%2A>la propiedad de contenido XAML, .  
  
 [!code-xaml[XAMLOvwSupport#ThisIsATextBox](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#thisisatextbox)]  
  
### <a name="content-models"></a>Modelos de contenido  
 Una clase puede admitir un uso como un elemento de objeto XAML en términos de la sintaxis, pero ese elemento solo funcionará correctamente en una aplicación o página cuando se coloca en una posición esperada de un modelo de contenido general o árbol de elementos. Por ejemplo, <xref:System.Windows.Controls.MenuItem> normalmente, solo se debe <xref:System.Windows.Controls.Primitives.MenuBase> colocar como elemento <xref:System.Windows.Controls.Menu>secundario de una clase derivada como . Los modelos de contenido para elementos específicos se documentan [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] como parte de las observaciones de las páginas de clase para los controles y otras clases que se pueden usar como elementos XAML.  
  
<a name="properties_of_object_elements"></a>
## <a name="properties-of-object-elements"></a>Propiedades de los elementos de objeto  
 Las propiedades de XAML se establecen mediante una variedad de sintaxis posibles. La sintaxis que se puede usar para una propiedad determinada variará en función de las características del sistema de tipos subyacentes de la propiedad que se va a establecer.  
  
 Al establecer valores de propiedades, se agregan entidades o características a los objetos tal como existen en el gráfico de objetos de tiempo de ejecución. El estado inicial del objeto creado a partir de un elemento de objeto se basa en el comportamiento del constructor sin parámetros. Normalmente, la aplicación usará algo distinto de una instancia completamente predeterminada de cualquier objeto determinado.  
  
<a name="attribute_syntax_properties"></a>
## <a name="attribute-syntax-properties"></a>Sintaxis de atributos (propiedades)  
 Sintaxis de atributo es la sintaxis de marcado XAML que establece un valor para una propiedad mediante la declaración de un atributo en un elemento de objeto existente. El nombre del atributo debe coincidir con el nombre de miembro CLR de la propiedad de la clase que respalda el elemento de objeto relevante. El nombre del atributo va seguido de un operador de asignación (-). El valor del atributo debe ser una cadena entre comillas.  
  
> [!NOTE]
> Puede utilizar comillas alternas para colocar una comilla literal dentro de un atributo. Por ejemplo, puede utilizar comillas simples como medio para declarar una cadena que contiene un carácter de comillas dobles dentro de ella. Si utiliza comillas simples o dobles, debe usar un par coincidente para abrir y cerrar la cadena de valor de atributo. También hay secuencias de escape u otras técnicas disponibles para evitar las restricciones de caracteres impuestas por cualquier sintaxis XAML en particular. Consulte [Entidades de caracteres XML y XAML](../../../desktop-wpf/xaml-services/xml-character-entities.md).  
  
 Para establecerse a través de la sintaxis de atributo, una propiedad debe ser pública y debe ser grabable. El valor de la propiedad en el sistema de tipos de respaldo debe ser un tipo de valor o debe ser un tipo de referencia al que se pueda crear una instancia o al que haga referencia un procesador XAML al tener acceso al tipo de respaldo relevante.  
  
 Para los eventos XAML de WPF, el evento al que se hace referencia como el nombre del atributo debe ser público y tener un delegado público.  
  
 La propiedad o evento debe ser un miembro de la clase o estructura que crea una instancia del elemento de objeto contenedor.  
  
### <a name="processing-of-attribute-values"></a>Procesamiento de valores de atributo  
 Un procesador XAML procesa el valor de cadena contenido entre comillas de apertura y cierre. Para las propiedades, el comportamiento de procesamiento predeterminado viene determinado por el tipo de la propiedad CLR subyacente.  
  
 El valor del atributo se rellena con una de las siguientes opciones, utilizando este orden de procesamiento:  
  
1. Si el procesador XAML encuentra una llave o un elemento <xref:System.Windows.Markup.MarkupExtension>de objeto que deriva de , la extensión de marcado a la que se hace referencia se evalúa primero en lugar de procesar el valor como una cadena y el objeto devuelto por la extensión de marcado se usa como valor. En muchos casos, el objeto devuelto por una extensión de marcado será una referencia a un objeto existente o una expresión que aplace la evaluación hasta el tiempo de ejecución y no sea un objeto recién creado.  
  
2. Si la propiedad se declara <xref:System.ComponentModel.TypeConverter>con un atributo o el tipo de <xref:System.ComponentModel.TypeConverter>valor de esa propiedad se declara con un atributo , el valor de cadena del atributo se envía al convertidor de tipos como una entrada de conversión y el convertidor devolverá una nueva instancia de objeto.  
  
3. Si no <xref:System.ComponentModel.TypeConverter>hay , se intenta una conversión directa al tipo de propiedad. Este nivel final es una conversión directa en el valor nativo del analizador entre los tipos primitivos del lenguaje XAML, o una comprobación de los nombres de constantes con nombre en una enumeración (el analizador tiene acceso a los valores coincidentes).  
  
#### <a name="enumeration-attribute-values"></a>Valores de atributo de enumeración  
 Las enumeraciones en XAML se procesan intrínsecamente por analizadores XAML y los miembros de una enumeración deben especificarse especificando el nombre de cadena de una de las constantes con nombre de la enumeración.  
  
 Para los valores de enumeración no marcados, el comportamiento nativo consiste en procesar la cadena de un valor de atributo y resolverlo en uno de los valores de enumeración. No se especifica la enumeración en el formato *Enumeración*. *Valor*, como se hace en el código. En su lugar, solo se especifica *Value*y *Enumeration* se deduce por el tipo de la propiedad que se va a establecer. Si especifica un atributo en la *enumeración*. *Forma de valor,* no se resolverá correctamente.  
  
 Para las enumeraciones flagwise, el <xref:System.Enum.Parse%2A?displayProperty=nameWithType> comportamiento se basa en el método. Puede especificar varios valores para una enumeración flagwise separando cada valor con una coma. Sin embargo, no puede combinar valores de enumeración que no sean con marca. Por ejemplo, no puede utilizar la sintaxis de coma para intentar crear un <xref:System.Windows.Trigger> que actúa en varias condiciones de una enumeración que no es de marca:  
  
```xaml  
<!--This will not compile, because Visibility is not a flagwise enumeration.-->  
...  
<Trigger Property="Visibility" Value="Collapsed,Hidden">  
  <Setter ... />  
</Trigger>  
...  
```  
  
 Las enumeraciones Flagwise que admiten atributos que se pueden establecer en XAML son poco frecuentes en WPFWPF. Sin embargo, <xref:System.Windows.Media.StyleSimulations>una de estas enumeraciones es . Por ejemplo, podría utilizar la sintaxis de atributo flagwise delimitada por comas para modificar el ejemplo proporcionado en Comentarios para la <xref:System.Windows.Documents.Glyphs> clase; `StyleSimulations = "BoldSimulation"` podría `StyleSimulations = "BoldSimulation,ItalicSimulation"`llegar a ser . <xref:System.Windows.Input.KeyBinding.Modifiers%2A?displayProperty=nameWithType>es otra propiedad donde se puede especificar más de un valor de enumeración. Sin embargo, esta propiedad resulta ser <xref:System.Windows.Input.ModifierKeys> un caso especial, porque la enumeración admite su propio convertidor de tipos. El convertidor de tipos para modificadores utiliza un signo más (+) como delimitador en lugar de una coma (,). Esta conversión admite la sintaxis más tradicional para representar combinaciones de teclas en la programación de Microsoft Windows, como "Ctrl+Alt".  
  
### <a name="properties-and-event-member-name-references"></a>Propiedades y referencias de nombre de miembro de evento  
 Al especificar un atributo, puede hacer referencia a cualquier propiedad o evento que exista como miembro del tipo CLR que ha creado una instancia para el elemento de objeto contenedor.  
  
 O bien, puede hacer referencia a una propiedad adjunta o un evento adjunto, independientemente del elemento de objeto contenedor. (Las propiedades adjuntas se describen en una próxima sección.)  
  
 También puede asignar un nombre a cualquier evento de cualquier objeto al que se pueda acceder a través del espacio de nombres predeterminado mediante un *typeName*. nombre parcialmente calificado del *evento;* esta sintaxis admite la asociación de controladores para eventos enrutados donde el controlador está diseñado para controlar el enrutamiento de eventos desde elementos secundarios, pero el elemento primario no tiene también ese evento en su tabla members. Esta sintaxis se asemeja a una sintaxis de evento adjunta, pero el evento aquí no es un evento adjunto verdadero. En su lugar, hace referencia a un evento con un nombre completo. Para obtener más información, consulte [Información general sobre eventos enrutados](routed-events-overview.md).  
  
 Para algunos escenarios, los nombres de propiedad a veces se proporcionan como el valor de un atributo, en lugar del nombre del atributo. Ese nombre de propiedad también puede incluir calificadores, como la propiedad especificada en el formulario *ownerType*. *dependencyPropertyName*. Este escenario es común al escribir estilos o plantillas en XAML. Las reglas de procesamiento para los nombres de propiedad proporcionados como un valor de atributo son diferentes y se rigen por el tipo de la propiedad que se establece o por los comportamientos de determinados subsistemas WPFWPF. Para obtener más información, consulte [Estilo y plantillas](../../../desktop-wpf/fundamentals/styles-templates-overview.md).  
  
 Otro uso de los nombres de propiedad es cuando un valor de atributo describe una relación propiedad-propiedad. Esta característica se utiliza para el enlace de datos <xref:System.Windows.PropertyPath> y para destinos de guión gráfico, y está habilitada por la clase y su convertidor de tipos. Para obtener una descripción más completa de la semántica de búsqueda, vea [Sintaxis XAML PropertyPath](propertypath-xaml-syntax.md).  
  
<a name="property_element_syntax"></a>
## <a name="property-element-syntax"></a>Sintaxis de elementos de propiedad  
 *Sintaxis* de elemento de propiedad es una sintaxis que difiere un poco de las reglas de sintaxis XML básicas para los elementos. En XML, el valor de un atributo es una cadena de facto, con la única variación posible es qué formato de codificación de cadena se está utilizando. En XAML, puede asignar otros elementos de objeto para que sean el valor de una propiedad. Esta funcionalidad está habilitada por la sintaxis del elemento de propiedad. En lugar de especificar la propiedad como un atributo dentro de la etiqueta de elemento, la propiedad se especifica mediante una etiqueta de elemento de apertura en *elementTypeName*. *PropertyName* form, el valor de la propiedad se especifica dentro y, a continuación, se cierra el elemento de propiedad.  
  
 En concreto, la sintaxis comienza con\<un corchete angular izquierdo ( ), seguido inmediatamente por el nombre de tipo de la clase o estructura en la que se encuentra la sintaxis del elemento de propiedad. Esto es seguido inmediatamente por un único punto (.), luego por el nombre de una propiedad y, a continuación, por un corchete de ángulo recto (>). Al igual que con la sintaxis de atributo, esa propiedad debe existir dentro de los miembros públicos declarados del tipo especificado. El valor que se asignará a la propiedad se encuentra dentro del elemento de propiedad. Normalmente, el valor se proporciona como uno o varios elementos de objeto, porque especificar objetos como valores es el escenario que la sintaxis del elemento de propiedad está diseñada para abordar. Por último, una etiqueta de cierre equivalente que especifica el mismo *elementTypeName*. Se debe proporcionar una combinación *propertyName,* en el anidamiento adecuado y el equilibrio con otras etiquetas de elemento.  
  
 Por ejemplo, la siguiente es <xref:System.Windows.FrameworkElement.ContextMenu%2A> la sintaxis de elemento de propiedad para la propiedad de un <xref:System.Windows.Controls.Button>archivo .  
  
 [!code-xaml[XAMLOvwSupport#ContextMenu](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#contextmenu)]  
  
 El valor dentro de un elemento de propiedad también se puede dar como texto interno, <xref:System.String>en los casos en que el tipo de propiedad que se especifica es un tipo de valor primitivo, como , o una enumeración donde se especifica un nombre. Estos dos usos son algo poco comunes, porque cada uno de estos casos también podría usar una sintaxis de atributo más simple. Un escenario para rellenar un elemento de propiedad con una cadena es para las propiedades que no son la propiedad de contenido XAML pero todavía se usan para la representación del texto de la interfaz de usuario, y determinados elementos de espacio en blanco como sfines deben aparecer en ese texto de la interfaz de usuario. La sintaxis de atributo no puede conservar sellos de línea, pero la sintaxis de elementos de propiedad puede, siempre y cuando la conservación de espacios en blanco significativa esté activa (para obtener más información, vea Procesamiento de [espacio en blanco en XAML](../../../desktop-wpf/xaml-services/white-space-processing.md)). Otro escenario es para que [x:Uid Directiva](../../../desktop-wpf/xaml-services/xuid-directive.md) se puede aplicar al elemento de propiedad y, por lo tanto, marcar el valor dentro como un valor que se debe localizar en el WPFWPF salida BAML o por otras técnicas.  
  
 Un elemento de propiedad no se representa en el árbol lógico WPFWPF. Un elemento de propiedad es solo una sintaxis determinada para establecer una propiedad y no es un elemento que tiene una instancia u objeto que la respalda. (Para obtener más información sobre el concepto de árbol lógico, vea [árboles en WPFWPF](trees-in-wpf.md).)  
  
 Para las propiedades donde se admite la sintaxis de atributo y elemento de propiedad, las dos sintaxis suelen tener el mismo resultado, aunque las sutilezas, como el control de espacios en blanco, pueden variar ligeramente entre las sintaxis.  
  
<a name="collection_syntax"></a>
## <a name="collection-syntax"></a>Sintaxis de colecciones  
 La especificación XAML requiere implementaciones de procesador XAML para identificar las propiedades donde el tipo de valor es una colección. La implementación general del procesador XAML en .NET se basa en código administrado y CLR, e identifica los tipos de colección a través de uno de los siguientes:  
  
- Implementaciones <xref:System.Collections.IList>de tipo .  
  
- Implementaciones <xref:System.Collections.IDictionary>de tipo .  
  
- Tipo deriva <xref:System.Array> de (para obtener más información acerca de las matrices en XAML, vea [x:Array Markup Extension](../../../desktop-wpf/xaml-services/xarray-markup-extension.md).)  
  
 Si el tipo de una propiedad es una colección, no es necesario especificar el tipo de colección deduducto en el marcado como un elemento de objeto. En su lugar, los elementos que están diseñados para convertirse en los elementos de la colección se especifican como uno o varios elementos secundarios del elemento de propiedad. Cada elemento de este tipo se evalúa en un objeto `Add` durante la carga y se agrega a la colección mediante una llamada al método de la colección implícita. Por ejemplo, <xref:System.Windows.Style.Triggers%2A> la <xref:System.Windows.Style> propiedad de toma <xref:System.Windows.TriggerCollection>el tipo <xref:System.Collections.IList>de colección especializada , que implementa . No es necesario crear <xref:System.Windows.TriggerCollection> una instancia de un elemento de objeto en el marcado. En su lugar, <xref:System.Windows.Trigger> especifique uno o `Style.Triggers` varios elementos como elementos dentro del elemento de propiedad, donde <xref:System.Windows.Trigger> (o <xref:System.Windows.TriggerCollection>una clase derivada) es el tipo esperado como el tipo de elemento para el fuertemente tipado e implícito .  
  
 [!code-xaml[XAMLOvwSupport#SyntaxPECollection](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#syntaxpecollection)]  
  
 Una propiedad puede ser un tipo de colección y la propiedad de contenido XAML para ese tipo y tipos derivados, que se describe en la siguiente sección de este tema.  
  
 Un elemento de colección implícita crea un miembro en la representación de árbol lógico, aunque no aparece en el marcado como un elemento. Normalmente, el constructor del tipo primario realiza la creación de instancias de la colección que es una de sus propiedades y la colección inicialmente vacía pasa a formar parte del árbol de objetos.  
  
> [!NOTE]
> Las interfaces genéricas<xref:System.Collections.Generic.IList%601> de <xref:System.Collections.Generic.IDictionary%602>lista y diccionario ( y ) no se admiten para la detección de colecciones. Sin embargo, <xref:System.Collections.Generic.List%601> puede usar la clase como <xref:System.Collections.IList> una clase <xref:System.Collections.Generic.Dictionary%602> base, porque se implementa <xref:System.Collections.IDictionary> directamente, o como una clase base, porque se implementa directamente.  
  
 En las páginas de referencia de .NET para tipos de colección, esta sintaxis con la omisión deliberada del elemento de objeto para una colección se observa ocasionalmente en las secciones de sintaxis XAML como sintaxis de colección implícita.  
  
 Con la excepción del elemento raíz, cada elemento de objeto de un archivo XAML anidado como un elemento secundario de otro elemento es realmente un elemento que es uno o ambos de los siguientes casos: un miembro de una propiedad de colección implícita de su elemento primario o un elemento que especifica el valor de la propiedad de contenido XAML para el elemento primario (las propiedades de contenido XAML se tratarán en una sección próxima). En otras palabras, la relación de los elementos primarios y secundarios en una página de marcado es realmente un único objeto en la raíz y cada elemento de objeto debajo de la raíz es una única instancia que proporciona un valor de propiedad del elemento primario o uno de los elementos de una colección que también es un valor de propiedad de tipo de colección del elemento primario. Este concepto de raíz única es común con XML y se refuerza con <xref:System.Windows.Markup.XamlReader.Load%2A>frecuencia en el comportamiento de las API que cargan XAML como .  
  
 El ejemplo siguiente es una sintaxis con<xref:System.Windows.Media.GradientStopCollection>el elemento object para una colección ( ) especificada explícitamente.  
  
```xaml  
<LinearGradientBrush>  
  <LinearGradientBrush.GradientStops>  
    <GradientStopCollection>  
      <GradientStop Offset="0.0" Color="Red" />  
      <GradientStop Offset="1.0" Color="Blue" />  
    </GradientStopCollection>  
  </LinearGradientBrush.GradientStops>  
</LinearGradientBrush>  
```  
  
 Tenga en cuenta que no siempre es posible declarar explícitamente la colección. Por ejemplo, se <xref:System.Windows.TriggerCollection> produciría un error <xref:System.Windows.Style.Triggers%2A> al intentar declarar explícitamente en el ejemplo mostrado anteriormente. Declarar explícitamente la colección requiere que la clase de <xref:System.Windows.TriggerCollection> colección debe admitir un constructor sin parámetros y no tiene un constructor sin parámetros.  
  
<a name="xaml_content_properties"></a>
## <a name="xaml-content-properties"></a>Propiedades del contenido XAML  
 Sintaxis de contenido XAML es una sintaxis <xref:System.Windows.Markup.ContentPropertyAttribute> que solo está habilitada en las clases que especifican como parte de su declaración de clase. Hace <xref:System.Windows.Markup.ContentPropertyAttribute> referencia al nombre de propiedad que es la propiedad content para ese tipo de elemento (incluidas las clases derivadas). Cuando se procesa mediante un procesador XAML, los elementos secundarios o texto interno que se encuentran entre las etiquetas de apertura y cierre del elemento de objeto se asignarán para que sean el valor de la propiedad de contenido XAML para ese objeto. Se le permite especificar elementos de propiedad explícitos para la propiedad content, pero este uso no se muestra generalmente en las secciones de sintaxis XAML de la referencia de .NET. La técnica explícita/detallada tiene un valor ocasional para la claridad del marcado o como una cuestión de estilo de marcado, pero normalmente la intención de una propiedad de contenido es simplificar el marcado para que los elementos que están relacionados intuitivamente como elementos primarios y secundarios se pueden anidar directamente. Las etiquetas de elemento de propiedad para otras propiedades de un elemento no se asignan como "contenido" según una definición de lenguaje XAML estricta; se procesan previamente en el orden de procesamiento del analizador XAML y no se consideran "contenido".  
  
### <a name="xaml-content-property-values-must-be-contiguous"></a>Los valores de propiedad de contenido XAML deben ser contiguos  
 El valor de una propiedad de contenido XAML debe darse completamente antes o completamente después de cualquier otro elemento de propiedad en ese elemento de objeto. Esto es cierto si el valor de una propiedad de contenido XAML se especifica como una cadena o como uno o varios objetos. Por ejemplo, el siguiente marcado no analiza:  
  
```xaml  
<Button>I am a
  <Button.Background>Blue</Button.Background>  
  blue button</Button>  
```  
  
 Esto es ilegal esencialmente porque si esta sintaxis se hizo explícita mediante el uso de sintaxis de elemento de propiedad para la propiedad content, la propiedad content se establecería dos veces:  
  
```xaml  
<Button>  
  <Button.Content>I am a </Button.Content>  
  <Button.Background>Blue</Button.Background>  
  <Button.Content> blue button</Button.Content>  
</Button>  
```  
  
 Un ejemplo igualmente ilegal es si la propiedad content es una colección y los elementos secundarios se intercalan con elementos de propiedad:  
  
```xaml  
<StackPanel>  
  <Button>This example</Button>  
  <StackPanel.Resources>  
    <SolidColorBrush x:Key="BlueBrush" Color="Blue"/>  
  </StackPanel.Resources>  
  <Button>... is illegal XAML</Button>  
</StackPanel>  
```  
  
<a name="content_properties_and_collection_syntax_combined"></a>
## <a name="content-properties-and-collection-syntax-combined"></a>Propiedades de contenido y sintaxis de colección combinadas  
 Para aceptar más de un único elemento de objeto como contenido, el tipo de la propiedad content debe ser específicamente un tipo de colección. De forma similar a la sintaxis de elemento de propiedad para los tipos de colección, un procesador XAML debe identificar los tipos que son tipos de colección. Si un elemento tiene una propiedad de contenido XAML y el tipo de la propiedad de contenido XAML es una colección, no es necesario especificar el tipo de colección implícita en el marcado como un elemento de objeto y no es necesario especificar la propiedad de contenido XAML como un elemento de propiedad. Por lo tanto, el modelo de contenido aparente en el marcado ahora puede tener más de un elemento secundario asignado como contenido. A continuación se muestra <xref:System.Windows.Controls.Panel> la sintaxis de contenido para una clase derivada. Todas <xref:System.Windows.Controls.Panel> las clases derivadas establecen <xref:System.Windows.Controls.Panel.Children%2A>la propiedad de contenido <xref:System.Windows.Controls.UIElementCollection>XAML , que requiere un valor de tipo .  
  
 [!code-xaml[XAMLOvwSupport#SyntaxContent](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page5.xaml#syntaxcontent)]  
  
 Tenga en cuenta que <xref:System.Windows.Controls.Panel.Children%2A> ni el <xref:System.Windows.Controls.UIElementCollection> elemento de propiedad para ni el elemento para el es necesario en el marcado. Se trata de una característica de diseño de XAML [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] para que los elementos contenidos recursivamente que definen a se representan de forma más intuitiva como un árbol de elementos anidados con relaciones de elementos primarios y secundarios inmediatas, sin intervenir etiquetas de elementos de propiedad u objetos de colección. De hecho, <xref:System.Windows.Controls.UIElementCollection> no se puede especificar explícitamente en el marcado como un elemento de objeto, por diseño. Dado que su único uso previsto <xref:System.Windows.Controls.UIElementCollection> es como una colección implícita, no expone un constructor público sin parámetros y, por lo tanto, no se puede crear una instancia como un elemento de objeto.  
  
### <a name="mixing-property-elements-and-object-elements-in-an-object-with-a-content-property"></a>Mezcla de elementos de propiedad y elementos de objeto en un objeto con una propiedad Content  
 La especificación XAML declara que un procesador XAML puede exigir que los elementos de objeto que se usan para rellenar la propiedad de contenido XAML dentro de un elemento de objeto deben ser contiguos y no se deben mezclar. Los procesadores [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] XAML aplican esta restricción para mezclar elementos de propiedad y contenido.  
  
 Puede tener un elemento de objeto secundario como el primer marcado inmediato dentro de un elemento de objeto. A continuación, puede introducir elementos de propiedad. O bien, puede especificar uno o varios elementos de propiedad, a continuación, el contenido y, a continuación, más elementos de propiedad. Pero una vez que un elemento de propiedad sigue el contenido, no puede introducir más contenido, solo puede agregar elementos de propiedad.  
  
 Este requisito de orden de elemento de contenido /propiedad no se aplica al texto interno utilizado como contenido. Sin embargo, sigue siendo un buen estilo de marcado para mantener el texto interno contiguo, porque un espacio en blanco significativo será difícil de detectar visualmente en el marcado si los elementos de propiedad se intercalan con el texto interno.  
  
<a name="xaml_namespaces"></a>
## <a name="xaml-namespaces"></a>Espacios de nombres XAML  
 Ninguno de los ejemplos de sintaxis anteriores especificó un espacio de nombres XAML distinto del espacio de nombres XAML predeterminado. En [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] las aplicaciones típicas, se especifica [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] que el espacio de nombres XAML predeterminado es el espacio de nombres. Puede especificar espacios de nombres XAML distintos del espacio de nombres XAML predeterminado y seguir usando una sintaxis similar. Pero, a continuación, en cualquier lugar donde se nombra una clase que no es accesible dentro del espacio de nombres XAML predeterminado, ese nombre de clase debe ir precedido por el prefijo del espacio de nombres XAML tal como se asigna al espacio de nombres CLR correspondiente. Por ejemplo, `<custom:Example/>` es sintaxis de elemento `Example` de objeto para crear instancias de una instancia de la clase, donde `custom` el espacio de nombres CLR que contiene esa clase (y posiblemente la información de ensamblado externo que contiene tipos de respaldo) se asignó previamente al prefijo.  
  
 Para obtener más información acerca de los espacios de nombres XAML, vea [Espacios de nombres XAML y Asignación](xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)de espacios de nombres para XAML de WPF .  
  
<a name="markup_extensions"></a>
## <a name="markup-extensions"></a>Extensiones de marcado  
 XAML define una entidad de programación de extensión de marcado que habilita un escape del control normal del procesador XAML de valores de atributo de cadena o elementos de objeto y aplaza el procesamiento a una clase de respaldo. El carácter que identifica una extensión de marcado a un procesador XAML cuando se usa la sintaxis de atributo es la llave de apertura (-), seguida de cualquier carácter que no sea una llave de cierre ( . La primera cadena que sigue a la llave de apertura debe hacer referencia a la clase que proporciona el comportamiento de extensión determinado, donde la referencia puede omitir la subcadena "Extension" si esa subcadena forma parte del nombre de clase true. A partir de entonces, puede aparecer un único espacio y, a continuación, la implementación de la extensión utiliza cada carácter sucesivo como entrada, hasta que se encuentra la llave de cierre.  
  
 La implementación XAML <xref:System.Windows.Markup.MarkupExtension> de .NET usa la clase abstracta [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] como base para todas las extensiones de marcado admitidas por otros marcos o tecnologías. Las extensiones [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] de marcado que implementan específicamente a menudo están diseñadas para proporcionar un medio para hacer referencia a otros objetos existentes o para hacer referencias diferidas a objetos que se evaluarán en tiempo de ejecución. Por ejemplo, un simple WPFWPF enlace `{Binding}` de datos se realiza mediante la especificación de la extensión de marcado en lugar del valor que una propiedad determinada normalmente tomaría. Muchas de las extensiones de marcado WPFWPF habilitan una sintaxis de atributo para las propiedades en las que una sintaxis de atributo no sería posible de otro modo. Por ejemplo, <xref:System.Windows.Style> un objeto es un tipo relativamente complejo que contiene una serie anidada de objetos y propiedades. Los estilos de WPFWPF se <xref:System.Windows.ResourceDictionary>definen normalmente como un recurso en un archivo , y, a continuación, se hace referencia a través de una de las dos extensiones de marcado de WPFWPF que solicitan un recurso. La extensión de marcado aplaza la evaluación del valor de propiedad <xref:System.Windows.FrameworkElement.Style%2A> a una <xref:System.Windows.Style>búsqueda de recursos y permite proporcionar el valor de la propiedad, tomando el tipo , en la sintaxis de atributo como en el ejemplo siguiente:  
  
 `<Button Style="{StaticResource MyStyle}">My button</Button>`  
  
 Aquí, `StaticResource` identifica <xref:System.Windows.StaticResourceExtension> la clase que proporciona la implementación de extensión de marcado. La siguiente `MyStyle` cadena se utiliza como entrada <xref:System.Windows.StaticResourceExtension> para el constructor no predeterminado, donde el <xref:System.Windows.ResourceKey>parámetro tomado de la cadena de extensión declara el solicitado . `MyStyle`se espera que sea el valor <xref:System.Windows.Style> [x:Key](../../../desktop-wpf/xaml-services/xkey-directive.md) de un definido como recurso. El uso de la extensión de [marcado StaticResource](staticresource-markup-extension.md) solicita que el recurso se use para proporcionar el <xref:System.Windows.Style> valor de propiedad a través de la lógica de búsqueda de recursos estáticos en tiempo de carga.  
  
 Para más información sobre las extensiones de marcado, consulte [Extensiones de marcado y XAML de WPF](markup-extensions-and-wpf-xaml.md). Para obtener una referencia de extensiones de marcado y otras características de programación XAML habilitadas en la implementación XAML general de .NET, vea [Espacio de nombres XAML (x:) Características del idioma](../../../desktop-wpf/xaml-services/namespace-language-features.md). Para las extensiones de marcado específicas de WPF, vea [Extensiones XAML de WPF](wpf-xaml-extensions.md).  
  
<a name="attached_properties"></a>
## <a name="attached-properties"></a>Propiedades asociadas  
 Las propiedades adjuntas son un concepto de programación introducido en XAML mediante el cual las propiedades pueden ser propiedad de un tipo determinado y definirse como atributos o elementos de propiedad en cualquier elemento. El escenario principal para el que están diseñadas las propiedades adjuntas es permitir que los elementos secundarios de una estructura de marcado notifiquen información a un elemento primario sin necesidad de un modelo de objetos ampliamente compartido en todos los elementos. Por el contrario, los elementos primarios pueden usar las propiedades adjuntas para notificar información a los elementos secundarios. Para obtener más información sobre el propósito de las propiedades adjuntas y cómo crear sus propias propiedades adjuntas, vea Información general sobre [propiedades adjuntas](attached-properties-overview.md).  
  
 Las propiedades adjuntas utilizan una sintaxis que se asemeja superficialmente a la sintaxis del elemento de propiedad, ya que también se especifica un *typeName*. *combinación propertyName.* Hay dos diferencias importantes:  
  
- Puede usar *typeName*. *combinación propertyName* incluso al establecer una propiedad adjunta a través de la sintaxis de atributo. Las propiedades adjuntas son el único caso en el que calificar el nombre de propiedad es un requisito en una sintaxis de atributo.  
  
- También puede utilizar la sintaxis de elemento de propiedad para las propiedades adjuntas. Sin embargo, para la sintaxis de elemento de propiedad típica, *typeName* que especifique es el elemento de objeto que contiene el elemento de propiedad. Si hace referencia a una propiedad adjunta, *typeName* es la clase que define la propiedad adjunta, no el elemento de objeto contenedor.  
  
<a name="attached_events"></a>
## <a name="attached-events"></a>Eventos asociados  
 Los eventos adjuntos son otro concepto de programación introducido en XAML donde los eventos se pueden definir por un tipo específico, pero los controladores se pueden adjuntar en cualquier elemento de objeto. En la implementación WOF, a menudo el tipo que define un evento adjunto es un tipo estático que define un servicio y, a veces, esos eventos adjuntos se exponen mediante un alias de evento enrutado en tipos que exponen el servicio. Los controladores de eventos adjuntos se especifican mediante la sintaxis de atributo. Al igual que con los eventos adjuntos, la sintaxis de atributo se expande para los eventos adjuntos para permitir un *typeName*. *eventName* usage, donde *typeName* es `Add` `Remove` la clase que proporciona y descriptores de acceso de controlador de eventos para la infraestructura de eventos adjunta y *eventName* es el nombre del evento.  
  
<a name="anatomy_of_a_xaml_page_root_element"></a>
## <a name="anatomy-of-a-xaml-root-element"></a>Anatomía de un elemento raíz XAML  
 En la tabla siguiente se muestra un elemento raíz XAML típico desglosado, que muestra los atributos específicos de un elemento raíz:  
  
|||  
|-|-|  
|`<Page`|Abrir el elemento de objeto del elemento raíz|  
|`xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"`|El espacio[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]de nombres XAML predeterminado ( )|  
|`xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`|El espacio de nombres XAML del lenguaje XAML|  
|`x:Class="ExampleNamespace.ExampleCode"`|La declaración de clase parcial que conecta el marcado con cualquier código subyacente definido para la clase parcial|  
|`>`|Fin del elemento object para la raíz. El objeto aún no está cerrado porque el elemento contiene elementos secundarios|  
  
<a name="optional_and_nonrecommended_xaml_usages"></a>
## <a name="optional-and-nonrecommended-xaml-usages"></a>Usos XAML opcionales y no recomendados  
 En las secciones siguientes se describen los usos de XAML que son técnicamente compatibles con los procesadores XAML, pero que producen detalles u otros problemas estéticos que interfieren con los archivos XAML que siguen siendo legibles al desarrollar aplicaciones que contienen orígenes XAML.  
  
### <a name="optional-property-element-usages"></a>Usos opcionales de elementos de propiedad  
 Los usos de elementos de propiedad opcionales incluyen escribir explícitamente las propiedades de contenido de elemento que el procesador XAML considera implícitas. Por ejemplo, al declarar el <xref:System.Windows.Controls.Menu>contenido de un , <xref:System.Windows.Controls.ItemsControl.Items%2A> puede optar <xref:System.Windows.Controls.Menu> por `<Menu.Items>` declarar explícitamente la <xref:System.Windows.Controls.MenuItem> `<Menu.Items>`colección de la etiqueta de elemento de <xref:System.Windows.Controls.Menu> propiedad como <xref:System.Windows.Controls.MenuItem> y colocar <xref:System.Windows.Controls.ItemsControl.Items%2A> cada uno dentro de , en lugar de usar el comportamiento de procesador XAML implícito que todos los elementos secundarios de a deben ser y se colocan en la colección. A veces, los usos opcionales pueden ayudar a aclarar visualmente la estructura del objeto como se representa en el marcado. O a veces un uso explícito de elementos de propiedad puede evitar el marcado que es técnicamente funcional pero visualmente confuso, como extensiones de marcado anidadas dentro de un valor de atributo.  
  
### <a name="full-typenamemembername-qualified-attributes"></a>Atributos calificados typeName.memberName completos  
 El *typeName*. *memberName* form para un atributo realmente funciona de forma más universal que solo el caso de evento enrutado. Pero en otras situaciones que la forma es superflua y debe evitarlo, aunque sólo sea por razones de estilo de marcado y legibilidad. En el ejemplo siguiente, cada una <xref:System.Windows.Controls.Control.Background%2A> de las tres referencias al atributo son completamente equivalentes:  
  
 [!code-xaml[XAMLOvwSupport#TypeNameProp](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#typenameprop)]  
  
 `Button.Background`funciona porque la búsqueda calificada <xref:System.Windows.Controls.Button> para<xref:System.Windows.Controls.Control.Background%2A> esa propiedad en <xref:System.Windows.Controls.Button> es correcta (se heredó de Control) y es la clase del elemento de objeto o una clase base. `Control.Background`funciona porque <xref:System.Windows.Controls.Control> la <xref:System.Windows.Controls.Control.Background%2A> clase <xref:System.Windows.Controls.Control> realmente <xref:System.Windows.Controls.Button> define y es una clase base.  
  
 Sin embargo, el siguiente *typeName*. *memberName* form example does not work and thus is shown commented:  
  
 [!code-xaml[XAMLOvwSupport#TypeNameBadProp](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#typenamebadprop)]  
  
 <xref:System.Windows.Controls.Label>es otra clase <xref:System.Windows.Controls.Control>derivada de , y `Label.Background` si <xref:System.Windows.Controls.Label> hubiera especificado dentro de un elemento de objeto, este uso habría funcionado. Sin <xref:System.Windows.Controls.Label> embargo, dado que no <xref:System.Windows.Controls.Button>es la clase o clase `Label.Background` base de , el comportamiento del procesador XAML especificado es procesar como una propiedad adjunta. `Label.Background`no es una propiedad adjunta disponible y se produce un error en este uso.  
  
### <a name="basetypenamemembername-property-elements"></a>elementos de propiedad baseTypeName.memberName  
 De forma análoga a cómo *typeName*. *memberName* form funciona para la sintaxis de atributo, *un baseTypeName*. La sintaxis *memberName* funciona para la sintaxis de elemento de propiedad. Por ejemplo, la sintaxis siguiente funciona:  
  
 [!code-xaml[XAMLOvwSupport#GoofyPE](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#goofype)]  
  
 Aquí, el elemento de `Control.Background` propiedad se dio como `Button`aunque el elemento de propiedad estaba contenido en .  
  
 Pero al igual que *typeName*. *memberName* form for attributes, *baseTypeName*. *memberName* es un estilo deficiente en el marcado y debe evitarlo.  
  
## <a name="see-also"></a>Consulte también

- [Información general sobre XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Espacio de nombres de XAML (x:) Características del lenguaje](../../../desktop-wpf/xaml-services/namespace-language-features.md)
- [Extensiones XAML de WPF](wpf-xaml-extensions.md)
- [Información general sobre las propiedades de dependencia](dependency-properties-overview.md)
- [Clases TypeConverter y XAML](typeconverters-and-xaml.md)
- [Clases XAML y personalizadas para WPF](xaml-and-custom-classes-for-wpf.md)
