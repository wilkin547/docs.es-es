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
ms.openlocfilehash: 66158d14b7686f520260cd24fbf6c1b0e7dda1d4
ms.sourcegitcommit: 30a83efb57c468da74e9e218de26cf88d3254597
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/20/2019
ms.locfileid: "68364095"
---
# <a name="xaml-syntax-in-detail"></a>Detalles de la sintaxis XAML
En este tema se definen los términos que se usan para describir los elementos de la sintaxis XAML. Estos términos se usan con frecuencia en el resto de esta documentación, tanto para la documentación de WPF específicamente como para los otros marcos de trabajo que usan XAML o los conceptos básicos de XAML habilitados por la compatibilidad del lenguaje XAML en el nivel System. Xaml. En este tema se amplía la terminología básica introducida en el tema [información general sobre XAML (WPF)](xaml-overview-wpf.md).  

<a name="the_xaml_language_specification"></a>   
## <a name="the-xaml-language-specification"></a>Especificación del lenguaje XAML  
 También se define o se hace referencia a la terminología de sintaxis XAML definida aquí en la especificación del lenguaje XAML. XAML es un lenguaje basado en XML y sigue o amplía las reglas estructurales de XML. Parte de la terminología se comparte desde o se basa en la terminología que se usa normalmente al describir el lenguaje XML o el modelo de objetos de documento XML.  
  
 Para obtener más información sobre la especificación del lenguaje XAML, descargue [ \[MS\] -XAML](https://go.microsoft.com/fwlink/?LinkId=114525) desde el centro de descarga de Microsoft.  
  
<a name="xaml_and_clr"></a>   
## <a name="xaml-and-clr"></a>XAML y CLR  
 XAML es un lenguaje de marcado. , [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]Como está implicado en su nombre, habilita la ejecución en tiempo de ejecución. XAML no es en sí mismo uno de los lenguajes comunes que el Runtime de CLR usa directamente. En su lugar, puede considerar XAML como compatible con su propio sistema de tipos. El sistema de análisis de XAML concreto que usa WPF se basa en CLR y en el sistema de tipos de CLR. Los tipos XAML se asignan a los tipos de CLR para crear instancias de una representación en tiempo de ejecución cuando se analiza el XAML para WPF. Por esta razón, el resto de la explicación de la sintaxis de este documento incluirá referencias al sistema de tipos de CLR, aunque las discusiones de sintaxis equivalentes en la especificación del lenguaje XAML no lo hacen. (Según el nivel de especificación del lenguaje XAML, los tipos XAML pueden asignarse a cualquier otro sistema de tipos, que no tiene que ser el CLR, pero eso requeriría la creación y el uso de un analizador XAML diferente).  
  
#### <a name="members-of-types-and-class-inheritance"></a>Miembros de tipos y herencia de clases  
 Las propiedades y los eventos tal como aparecen como miembros XAML [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] de un tipo se suelen heredar de los tipos base. Por ejemplo, considere este ejemplo: `<Button Background="Blue" .../>`. La <xref:System.Windows.Controls.Control.Background%2A> propiedad no es una propiedad declarada inmediatamente <xref:System.Windows.Controls.Button> en la clase, si se va a examinar la definición de clase, los resultados de la reflexión o la documentación. En su lugar <xref:System.Windows.Controls.Control.Background%2A> , se hereda de la <xref:System.Windows.Controls.Control> clase base.  
  
 El comportamiento de la herencia [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] de clases de los elementos XAML es una salida significativa de una interpretación impuesta por el esquema del marcado XML. La herencia de clases puede ser compleja, especialmente cuando las clases base intermedias son abstractas o cuando intervienen interfaces. Esta es una de las razones por las que el conjunto de elementos XAML y sus atributos permisibles es difícil de representar con precisión y por completo con los tipos [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] de esquema que se suelen usar para la programación, como el formato DTD o xsd. Otra razón es que las características de extensibilidad y asignación de tipos del propio lenguaje XAML impiden la integridad de cualquier representación fija de los tipos y miembros permitidos.  
  
<a name="object_element_syntax"></a>   
## <a name="object-element-syntax"></a>Sintaxis de elemento de objeto  
 La *Sintaxis de elementos de objeto* es la sintaxis de marcado XAML que crea instancias de una clase o estructura de CLR declarando un elemento XML. Esta sintaxis es similar a la sintaxis de los elementos de otros lenguajes de marcado, como HTML. La sintaxis del elemento de objeto comienza con un corchete angular de apertura (\<), seguido inmediatamente del nombre de tipo de la clase o estructura de la que se crea una instancia. Cero o más espacios pueden seguir el nombre del tipo, y también se pueden declarar cero o más atributos en el elemento de objeto, con uno o más espacios que separan cada atributo name = "Value". Por último, debe cumplirse una de las siguientes condiciones:  
  
- El elemento y la etiqueta deben cerrarse con una barra diagonal (/) seguida inmediatamente de un corchete angular de cierre (>).  
  
- La etiqueta de apertura debe completarse con un corchete angular de cierre (>). Otros elementos de objeto, elementos de propiedad o texto interno, pueden seguir la etiqueta de apertura. Exactamente, el contenido que se puede incluir aquí está restringido por el modelo de objetos del elemento. También debe existir la etiqueta de cierre equivalente para el elemento de objeto, en el anidamiento y el equilibrio adecuados con otros pares de etiquetas de apertura y cierre.  
  
 XAML, tal y como lo implementa .NET, tiene un conjunto de reglas que asignan elementos de objeto a tipos, atributos en propiedades o eventos, y espacios de nombres XAML a espacios de nombres CLR y ensamblado. Para WPF y el .NET Framework, los elementos de objeto XAML [!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)] se asignan a los tipos tal y como se definen en los ensamblados a los que se hace referencia, y los atributos se asignan a los miembros de esos tipos. Cuando se hace referencia a un tipo CLR en XAML, también se tiene acceso a los miembros heredados de ese tipo.  
  
 Por ejemplo, el ejemplo siguiente es la sintaxis de elementos de objeto que crea instancias de una <xref:System.Windows.Controls.Button> nueva instancia de la clase y <xref:System.Windows.FrameworkElement.Name%2A> también especifica un atributo y un valor para ese atributo:  
  
 [!code-xaml[XAMLOvwSupport#SyntaxOE](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#syntaxoe)]  
  
 En el ejemplo siguiente se muestra la sintaxis de elementos de objeto que también incluye sintaxis de propiedad de contenido XAML. El texto interno incluido en se usará para establecer la <xref:System.Windows.Controls.TextBox> propiedad de contenido XAML,. <xref:System.Windows.Controls.TextBox.Text%2A>  
  
 [!code-xaml[XAMLOvwSupport#ThisIsATextBox](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#thisisatextbox)]  
  
### <a name="content-models"></a>Modelos de contenido  
 Una clase podría admitir un uso como elemento de objeto XAML en términos de sintaxis, pero ese elemento solo funcionará correctamente en una aplicación o página cuando se coloca en una posición esperada de un árbol de elementos o un modelo de contenido general. Por ejemplo, <xref:System.Windows.Controls.MenuItem> normalmente solo se debe colocar como elemento secundario de una <xref:System.Windows.Controls.Primitives.MenuBase> clase <xref:System.Windows.Controls.Menu>derivada como. Los modelos de contenido para elementos específicos se documentan como parte de los comentarios en las páginas de clases [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] para los controles y otras clases que se pueden usar como elementos XAML.  
  
<a name="properties_of_object_elements"></a>   
## <a name="properties-of-object-elements"></a>Propiedades de los elementos de objeto  
 Las propiedades de XAML se establecen mediante una variedad de posibles sintaxis. La sintaxis que se puede usar para una propiedad determinada variará en función de las características del sistema de tipos subyacentes de la propiedad que se está estableciendo.  
  
 Al establecer valores de propiedades, se agregan características o características a los objetos tal como existen en el gráfico de objetos en tiempo de ejecución. El estado inicial del objeto creado a partir de un elemento de objeto se basa en el comportamiento del constructor sin parámetros. Normalmente, la aplicación usará algo distinto de una instancia totalmente predeterminada de cualquier objeto dado.  
  
<a name="attribute_syntax_properties"></a>   
## <a name="attribute-syntax-properties"></a>Sintaxis de atributos (propiedades)  
 La sintaxis de atributo es la sintaxis de marcado XAML que establece un valor para una propiedad declarando un atributo en un elemento de objeto existente. El nombre del atributo debe coincidir con el nombre del miembro CLR de la propiedad de la clase que respalda el elemento de objeto pertinente. El nombre del atributo va seguido de un operador de asignación (=). El valor de atributo debe ser una cadena entre comillas.  
  
> [!NOTE]
>  Puede usar comillas alternas para colocar una comilla literal dentro de un atributo. Por ejemplo, puede usar comillas simples como medio para declarar una cadena que contenga un carácter de comilla doble dentro de ella. Tanto si usa comillas simples como dobles, debe utilizar un par coincidente para abrir y cerrar la cadena de valor de atributo. También hay secuencias de escape u otras técnicas disponibles para trabajar en torno a las restricciones de caracteres impuesta por cualquier sintaxis XAML determinada. Vea [entidades de caracteres XML y XAML](../../xaml-services/xml-character-entities-and-xaml.md).  
  
 Para establecerse mediante la sintaxis de atributo, una propiedad debe ser pública y debe poder escribirse. El valor de la propiedad en el sistema de tipo de respaldo debe ser un tipo de valor, o debe ser un tipo de referencia al que se pueda crear una instancia o hacer referencia a él mediante un procesador XAML al tener acceso al tipo de respaldo pertinente.  
  
 En el caso de los eventos XAML de WPF, el evento al que se hace referencia como el nombre de atributo debe ser público y tener un delegado público.  
  
 La propiedad o el evento debe ser un miembro de la clase o estructura de la que se crea una instancia mediante el elemento de objeto contenedor.  
  
### <a name="processing-of-attribute-values"></a>Procesamiento de valores de atributo  
 Un procesador XAML procesa el valor de cadena contenido en las comillas de apertura y cierre. En el caso de las propiedades, el comportamiento de procesamiento predeterminado viene determinado por el tipo de la propiedad CLR subyacente.  
  
 El valor del atributo se rellena con uno de los siguientes elementos, mediante este orden de procesamiento:  
  
1. Si el procesador XAML encuentra una llave, o un elemento de objeto que se deriva de, la <xref:System.Windows.Markup.MarkupExtension>extensión de marcado a la que se hace referencia se evalúa primero en lugar de procesar el valor como una cadena, y el objeto devuelto por la extensión de marcado se utiliza como valor. En muchos casos, el objeto devuelto por una extensión de marcado es una referencia a un objeto existente, o una expresión que aplaza la evaluación hasta el tiempo de ejecución, y no es un objeto recién creado.  
  
2. Si la propiedad se declara con un atributo <xref:System.ComponentModel.TypeConverter>, o el tipo de valor de esa propiedad se declara con un <xref:System.ComponentModel.TypeConverter>atributo, el valor de cadena del atributo se envía al convertidor de tipos como una entrada de conversión y el convertidor devolverá un nueva instancia de objeto.  
  
3. Si no hay ningún <xref:System.ComponentModel.TypeConverter>, se intenta realizar una conversión directa al tipo de propiedad. Este último nivel es una conversión directa en el valor de analizador-nativo entre los tipos primitivos del lenguaje XAML o una comprobación de los nombres de las constantes con nombre en una enumeración (el analizador accede a los valores coincidentes).  
  
#### <a name="enumeration-attribute-values"></a>Valores de atributo de enumeración  
 Los analizadores XAML procesan de forma intrínseca las enumeraciones en XAML y los miembros de una enumeración se deben especificar especificando el nombre de cadena de una de las constantes con nombre de la enumeración.  
  
 En el caso de los valores de enumeración que no son de marcador, el comportamiento nativo es procesar la cadena de un valor de atributo y resolverlo en uno de los valores de enumeración. No se especifica la enumeración en la *enumeración*de formato. *Valor*, como se hace en el código. En su lugar, solo se especifica el *valor*y la *enumeración* se deduce por el tipo de la propiedad que se establece. Si especifica un atributo en la *enumeración*. Formato de *valor* , no se resolverá correctamente.  
  
 En el caso de las enumeraciones basadas en marcadores, <xref:System.Enum.Parse%2A?displayProperty=nameWithType> el comportamiento se basa en el método. Puede especificar varios valores para una enumeración basada en marcadores separando cada valor con una coma. Sin embargo, no se pueden combinar valores de enumeración que no estén en marcadores. Por ejemplo, no puede usar la sintaxis de coma para intentar crear un <xref:System.Windows.Trigger> que actúe en varias condiciones de una enumeración de no marca:  
  
```  
<!--This will not compile, because Visibility is not a flagwise enumeration.-->  
...  
<Trigger Property="Visibility" Value="Collapsed,Hidden">  
  <Setter ... />  
</Trigger>  
...  
```  
  
 Las enumeraciones de marcas de marcado que admiten atributos que se pueden establecer en XAML son poco frecuentes en WPF. Sin embargo, una enumeración <xref:System.Windows.Media.StyleSimulations>de este tipo es. Podría, por ejemplo, usar la sintaxis de atributo de marcas delimitada por comas para modificar el ejemplo proporcionado en las notas <xref:System.Windows.Documents.Glyphs> de la clase; podría convertirse `StyleSimulations = "BoldSimulation,ItalicSimulation"`en. `StyleSimulations = "BoldSimulation"` <xref:System.Windows.Input.KeyBinding.Modifiers%2A?displayProperty=nameWithType>es otra propiedad en la que se puede especificar más de un valor de enumeración. Sin embargo, esta propiedad es un caso especial, porque la enumeración admite su propio convertidor de <xref:System.Windows.Input.ModifierKeys> tipos. El convertidor de tipos para los modificadores usa un signo más (+) como delimitador en lugar de una coma (,). Esta conversión admite la sintaxis más tradicional para representar combinaciones de teclas en la programación de Microsoft Windows, como "Ctrl + Alt".  
  
### <a name="properties-and-event-member-name-references"></a>Propiedades y referencias de nombres de miembros de eventos  
 Al especificar un atributo, puede hacer referencia a cualquier propiedad o evento que exista como miembro del tipo CLR del que creó una instancia para el elemento de objeto contenedor.  
  
 O bien, puede hacer referencia a una propiedad adjunta o a un evento adjunto, independientemente del elemento de objeto contenedor. (Las propiedades adjuntas se describen en una próxima sección).  
  
 También puede asignar un nombre a cualquier evento de cualquier objeto al que se pueda tener acceso a través del espacio de nombres predeterminado mediante un *TypeName*. nombre parcial del *evento* ; Esta sintaxis admite la Asociación de controladores para eventos enrutados donde el controlador está diseñado para controlar el enrutamiento de eventos de los elementos secundarios, pero el elemento primario no tiene también ese evento en su tabla de miembros. Esta sintaxis es similar a la sintaxis de un evento adjunto, pero el evento aquí no es un evento adjunto verdadero. En su lugar, hace referencia a un evento con un nombre completo. Para obtener más información, vea [información general sobre eventos](routed-events-overview.md)enrutados.  
  
 En algunos escenarios, a veces se proporcionan nombres de propiedad como el valor de un atributo, en lugar del nombre de atributo. Ese nombre de propiedad también puede incluir calificadores, como la propiedad especificada en el formato *ownerType*. *dependencyPropertyName*. Este escenario es común cuando se escriben estilos o plantillas en XAML. Las reglas de procesamiento para los nombres de propiedad proporcionados como un valor de atributo son diferentes y se rigen por el tipo de la propiedad que se establece o por los comportamientos de subsistemas WPF concretos. Para obtener más información, consulte [aplicar estilos y plantillas](../controls/styling-and-templating.md).  
  
 Otro uso de los nombres de propiedad es cuando un valor de atributo describe una relación propiedad-propiedad. Esta característica se usa para el enlace de datos y para los destinos de guion gráfico, <xref:System.Windows.PropertyPath> y está habilitada por la clase y su convertidor de tipos. Para obtener una descripción más completa de la semántica de búsqueda, consulte [sintaxis XAML de PropertyPath](propertypath-xaml-syntax.md).  
  
<a name="property_element_syntax"></a>   
## <a name="property-element-syntax"></a>Sintaxis de elementos de propiedad  
 La *Sintaxis de elementos de propiedad* es una sintaxis que difiere ligeramente de las reglas de sintaxis XML básicas para los elementos. En XML, el valor de un atributo es una cadena de hecho, con la única variación posible en que se usa el formato de codificación de cadenas. En XAML, puede asignar otros elementos de objeto para que sea el valor de una propiedad. Esta funcionalidad está habilitada por la sintaxis del elemento de propiedad. En lugar de especificar la propiedad como un atributo dentro de la etiqueta de elemento, la propiedad se especifica mediante una etiqueta de elemento de apertura en *elementTypeName*. formulario *PropertyName* , el valor de la propiedad se especifica en y, a continuación, se cierra el elemento Property.  
  
 En concreto, la sintaxis comienza con un corchete\<angular de apertura (), seguido inmediatamente del nombre de tipo de la clase o estructura en la que se encuentra la sintaxis del elemento de propiedad. Va seguido inmediatamente de un punto (.), después por el nombre de una propiedad y, después, por un corchete angular de cierre (>). Como con la sintaxis de atributo, esa propiedad debe existir dentro de los miembros públicos declarados del tipo especificado. El valor que se va a asignar a la propiedad se encuentra dentro del elemento de propiedad. Normalmente, el valor se proporciona como uno o varios elementos de objeto, porque la especificación de objetos como valores es el escenario que la sintaxis del elemento de propiedad está pensada para solucionar. Por último, una etiqueta de cierre equivalente que especifica el mismo *elementTypeName*. se debe proporcionar la combinación *PropertyName* , en el anidamiento y el equilibrio adecuados con otras etiquetas de elemento.  
  
 Por ejemplo, la siguiente sintaxis de elementos de propiedad para <xref:System.Windows.FrameworkElement.ContextMenu%2A> la propiedad <xref:System.Windows.Controls.Button>de.  
  
 [!code-xaml[XAMLOvwSupport#ContextMenu](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#contextmenu)]  
  
 También se puede proporcionar el valor de un elemento de propiedad como texto interno, en los casos en los que el tipo de propiedad que se especifica es un <xref:System.String>tipo de valor primitivo, como, o una enumeración en la que se especifica un nombre. Estos dos usos son algo poco frecuentes, ya que cada uno de estos casos también podría usar una sintaxis de atributo más sencilla. Un escenario para rellenar un elemento de propiedad con una cadena es para las propiedades que no son la propiedad de contenido XAML pero que se usan para la representación del texto de la interfaz de usuario, y se requiere que los elementos de espacio en blanco, como los avances de tecla, aparezcan en ese texto de la interfaz de usuario. La sintaxis de atributo no puede conservar los saltos de tecla, pero la sintaxis de los elementos de propiedad puede, siempre que esté activa la preservación de espacio en blanco significativa (para obtener más información, vea [procesamiento de espacios en blanco en XAML](../../xaml-services/whitespace-processing-in-xaml.md)). Otro escenario es para que la [Directiva x:UID](../../xaml-services/x-uid-directive.md) se pueda aplicar al elemento de propiedad y, por tanto, marque el valor de como un valor que debe localizarse en el BAML de salida de WPF o en otras técnicas.  
  
 Un elemento de propiedad no se representa en el árbol lógico de WPF. Un elemento Property es simplemente una sintaxis determinada para establecer una propiedad, y no es un elemento que tiene una instancia o un objeto que realiza la copia de seguridad. (Para obtener más información sobre el concepto de árbol lógico, consulte [árboles en WPF](trees-in-wpf.md)).  
  
 En el caso de las propiedades en las que se admiten la sintaxis de elementos de atributo y de propiedad, las dos sintaxis suelen tener el mismo resultado, aunque los matices como el control de los espacios en blanco pueden variar ligeramente entre las sintaxis.  
  
<a name="collection_syntax"></a>   
## <a name="collection-syntax"></a>Sintaxis de colecciones  
 La especificación XAML requiere implementaciones de procesador XAML para identificar las propiedades en las que el tipo de valor es una colección. La implementación del procesador XAML general en .NET se basa en el código administrado y en el CLR, e identifica los tipos de colección mediante una de las siguientes acciones:  
  
- El tipo implementa <xref:System.Collections.IList>.  
  
- El tipo implementa <xref:System.Collections.IDictionary>.  
  
- El tipo deriva de <xref:System.Array> (para obtener más información sobre las matrices en XAML, consulte [extensión de marcado x:Array](../../xaml-services/x-array-markup-extension.md)).  
  
 Si el tipo de una propiedad es una colección, no es necesario especificar el tipo de colección deducido en el marcado como un elemento de objeto. En su lugar, los elementos que se van a convertir en elementos de la colección se especifican como uno o varios elementos secundarios del elemento de propiedad. Cada elemento de este tipo se evalúa como un objeto durante la carga y se agrega a la `Add` colección llamando al método de la colección implícita. Por ejemplo, la <xref:System.Windows.Style.Triggers%2A> propiedad de <xref:System.Windows.Style> toma el <xref:System.Collections.IList>tipo <xref:System.Windows.TriggerCollection>de colección especializado, que implementa. No es necesario crear una instancia de un <xref:System.Windows.TriggerCollection> elemento de objeto en el marcado. En su lugar, especifique uno o varios <xref:System.Windows.Trigger> elementos como elementos dentro del `Style.Triggers` elemento de propiedad, <xref:System.Windows.Trigger> donde (o una clase derivada) es el tipo esperado como el tipo de elemento para el fuertemente tipado <xref:System.Windows.TriggerCollection>e implícito.  
  
 [!code-xaml[XAMLOvwSupport#SyntaxPECollection](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#syntaxpecollection)]  
  
 Una propiedad puede ser tanto un tipo de colección como la propiedad de contenido XAML para ese tipo y los tipos derivados, que se describe en la sección siguiente de este tema.  
  
 Un elemento de colección implícito crea un miembro en la representación del árbol lógico, aunque no aparece en el marcado como un elemento. Normalmente, el constructor del tipo primario realiza la creación de instancias para la colección que es una de sus propiedades, y la colección inicialmente vacía se convierte en parte del árbol de objetos.  
  
> [!NOTE]
>  La lista genérica y las interfaces de<xref:System.Collections.Generic.IList%601> diccionario <xref:System.Collections.Generic.IDictionary%602>(y) no se admiten para la detección de colecciones. Sin embargo, puede usar la <xref:System.Collections.Generic.List%601> clase como una clase base, porque <xref:System.Collections.IList> implementa directamente, o <xref:System.Collections.Generic.Dictionary%602> como <xref:System.Collections.IDictionary> una clase base, porque implementa directamente.  
  
 En las páginas de referencia de .NET para los tipos de colección, en ocasiones se anota esta sintaxis con la omisión intencional del elemento de objeto de una colección en las secciones de sintaxis de XAML como sintaxis de colección implícita.  
  
 A excepción del elemento raíz, cada elemento de objeto de un archivo XAML anidado como elemento secundario de otro elemento es realmente un elemento que es uno de los siguientes casos o ambos: un miembro de una propiedad de colección implícita de su elemento primario. , o un elemento que especifica el valor de la propiedad de contenido XAML para el elemento primario (las propiedades de contenido XAML se tratarán en una próxima sección). En otras palabras, la relación de los elementos primarios y secundarios en una página de marcado es en realidad un objeto único en la raíz, y cada elemento de objeto situado debajo de la raíz es una sola instancia que proporciona un valor de propiedad del elemento primario, o uno de los elementos de una columna lection, que también es un valor de propiedad de tipo de colección del elemento primario. Este concepto de raíz única es común con XML y a menudo se refuerza en el comportamiento de las API que cargan <xref:System.Windows.Markup.XamlReader.Load%2A>XAML como.  
  
 El ejemplo siguiente es una sintaxis con el elemento Object para una colección (<xref:System.Windows.Media.GradientStopCollection>) especificada explícitamente.  
  
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
  
 Tenga en cuenta que no siempre es posible declarar explícitamente la colección. Por ejemplo, si se intenta declarar <xref:System.Windows.TriggerCollection> explícitamente en el ejemplo <xref:System.Windows.Style.Triggers%2A> anterior, se produciría un error. Declarar explícitamente la colección requiere que la clase de colección admita un constructor sin parámetros y <xref:System.Windows.TriggerCollection> que no tenga un constructor sin parámetros.  
  
<a name="xaml_content_properties"></a>   
## <a name="xaml-content-properties"></a>Propiedades del contenido XAML  
 La <xref:System.Windows.Markup.ContentPropertyAttribute> sintaxis de contenido XAML es una sintaxis que solo está habilitada en las clases que especifican como parte de su declaración de clase. <xref:System.Windows.Markup.ContentPropertyAttribute> Hace referencia al nombre de la propiedad que es la propiedad de contenido para ese tipo de elemento (incluidas las clases derivadas). Cuando lo procesa un procesador XAML, los elementos secundarios o el texto interno que se encuentre entre las etiquetas de apertura y cierre del elemento de objeto se asignarán para ser el valor de la propiedad de contenido XAML para ese objeto. Se permite especificar elementos de propiedad explícitos para la propiedad de contenido, pero este uso no se muestra generalmente en las secciones de sintaxis XAML de la referencia de .NET. La técnica explícita/verbose tiene un valor ocasional para la claridad de marcado o como una cuestión de estilo de marcado, pero normalmente la intención de una propiedad de contenido es simplificar el marcado para que los elementos que están relacionados de forma intuitiva como primario-secundario se puedan anidar directamente. Las etiquetas de elemento de propiedad de otras propiedades de un elemento no se asignan como "Content" por una definición de lenguaje XAML estricta; se procesan previamente en el orden de procesamiento del analizador de XAML y no se consideran "contenido".  
  
### <a name="xaml-content-property-values-must-be-contiguous"></a>Los valores de propiedad de contenido XAML deben ser contiguos  
 El valor de una propiedad de contenido XAML se debe proporcionar en su totalidad antes o por completo después de cualquier otro elemento de propiedad de ese elemento de objeto. Esto es así si el valor de una propiedad de contenido XAML se especifica como una cadena o como uno o más objetos. Por ejemplo, el marcado siguiente no se analiza:  
  
```  
<Button>I am a   
  <Button.Background>Blue</Button.Background>  
  blue button</Button>  
```  
  
 Esto no es válido básicamente porque si esta sintaxis se hizo explícita mediante la sintaxis de elementos de propiedad para la propiedad de contenido, la propiedad de contenido se establecería dos veces:  
  
```xml  
<Button>  
  <Button.Content>I am a </Button.Content>  
  <Button.Background>Blue</Button.Background>  
  <Button.Content> blue button</Button.Content>  
</Button>  
```  
  
 Un ejemplo no válido similar es si la propiedad de contenido es una colección y los elementos secundarios se intercalan con elementos de propiedad:  
  
```xml  
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
 Para aceptar más de un elemento de objeto único como contenido, el tipo de la propiedad de contenido debe ser específicamente un tipo de colección. De forma similar a la sintaxis de elementos de propiedad para los tipos de colección, un procesador XAML debe identificar tipos que son tipos de colección. Si un elemento tiene una propiedad de contenido XAML y el tipo de la propiedad de contenido XAML es una colección, no es necesario especificar el tipo de colección implícito en el marcado como un elemento de objeto y no es necesario especificar la propiedad de contenido XAML como la propiedad ependen. Por lo tanto, el modelo de contenido aparente en el marcado ahora puede tener más de un elemento secundario asignado como contenido. La siguiente es la sintaxis de contenido <xref:System.Windows.Controls.Panel> para una clase derivada. Todas <xref:System.Windows.Controls.Panel> las clases derivadas establecen la propiedad de contenido <xref:System.Windows.Controls.Panel.Children%2A>XAML en, que requiere un valor <xref:System.Windows.Controls.UIElementCollection>de tipo.  
  
 [!code-xaml[XAMLOvwSupport#SyntaxContent](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page5.xaml#syntaxcontent)]  
  
 Tenga en cuenta que <xref:System.Windows.Controls.Panel.Children%2A> <xref:System.Windows.Controls.UIElementCollection> no se requiere ni el elemento de propiedad para ni el elemento para en el marcado. Se trata de una característica de diseño de XAML para que los elementos contenidos de forma recursiva que definen un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] se representen de forma más intuitiva como un árbol de elementos anidados con relaciones de elementos primarios y secundarios inmediatas, sin incluir etiquetas de elemento de propiedad o objetos de colección. De hecho, <xref:System.Windows.Controls.UIElementCollection> no se puede especificar explícitamente en el marcado como un elemento de objeto, por diseño. Dado que su único uso previsto es como una colección implícita <xref:System.Windows.Controls.UIElementCollection> , no expone un constructor sin parámetros público y, por tanto, no se puede crear una instancia de él como un elemento de objeto.  
  
### <a name="mixing-property-elements-and-object-elements-in-an-object-with-a-content-property"></a>Combinar elementos de propiedad y elementos de objeto en un objeto con una propiedad de contenido  
 La especificación XAML declara que un procesador XAML puede exigir que los elementos de objeto que se usan para rellenar la propiedad de contenido XAML dentro de un elemento de objeto deben ser contiguos y no deben ser mixtos. Esta restricción contra la combinación de elementos y contenido de propiedad se aplica mediante [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] los procesadores XAML.  
  
 Puede tener un elemento de objeto secundario como el primer marcado inmediato dentro de un elemento de objeto. A continuación, puede introducir elementos de propiedad. O bien, puede especificar uno o varios elementos de propiedad, el contenido y, después, más elementos de propiedad. Pero una vez que un elemento de propiedad sigue contenido, no puede introducir más contenido, solo puede agregar elementos de propiedad.  
  
 Este requisito de orden de elementos de contenido/propiedad no se aplica al texto interno que se usa como contenido. Sin embargo, sigue siendo un buen estilo de marcado para mantener el texto interno contiguo, ya que el espacio en blanco significativo será difícil de detectar visualmente en el marcado si los elementos de propiedad se intercalan con texto interno.  
  
<a name="xaml_namespaces"></a>   
## <a name="xaml-namespaces"></a>Espacios de nombres XAML  
 Ninguno de los ejemplos de sintaxis anteriores especificaba un espacio de nombres XAML distinto del espacio de nombres XAML predeterminado. En las [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplicaciones típicas, se especifica que el espacio de nombres XAML [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] predeterminado sea el espacio de nombres. Puede especificar espacios de nombres XAML distintos del espacio de nombres XAML predeterminado y seguir usando una sintaxis similar. Pero después, en cualquier lugar donde se llame a una clase que no sea accesible dentro del espacio de nombres XAML predeterminado, ese nombre de clase debe ir precedido del prefijo del espacio de nombres XAML asignado al espacio de nombres CLR correspondiente. Por ejemplo, `<custom:Example/>` es una sintaxis de elemento de objeto para crear instancias de `Example` una instancia de la clase, donde el espacio de nombres CLR que contiene esa clase (y posiblemente la información de ensamblado externo que contiene tipos de respaldo) se asignó previamente al `custom` prefijo.  
  
 Para obtener más información sobre los espacios de nombres XAML, vea [espacios de nombres y asignación de espacios de nombres XAML para WPF](xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).  
  
<a name="markup_extensions"></a>   
## <a name="markup-extensions"></a>Extensiones de marcado  
 XAML define una entidad de programación de extensión de marcado que permite un escape desde el procesamiento normal del procesador XAML de los valores de atributo de cadena u objetos de objeto, y pospone el procesamiento a una clase de respaldo. El carácter que identifica una extensión de marcado para un procesador XAML cuando se usa la sintaxis de atributo es la llave de apertura ({), seguida de cualquier carácter que no sea una llave de cierre (}). La primera cadena que sigue a la llave de apertura debe hacer referencia a la clase que proporciona el comportamiento de la extensión concreta, donde la referencia puede omitir la subcadena "Extension" si esa subcadena forma parte del nombre de clase true. Después, puede aparecer un solo espacio y, a continuación, cada carácter correcto se usa como entrada en la implementación de la extensión, hasta que se encuentre la llave de cierre.  
  
 La implementación de XAML de .net <xref:System.Windows.Markup.MarkupExtension> usa la clase abstracta como base para todas las extensiones de marcado admitidas por [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , así como otros marcos o tecnologías. Las extensiones de marcado [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] que implementa específicamente suelen estar diseñadas para proporcionar un medio para hacer referencia a otros objetos existentes o para realizar referencias diferidas a objetos que se evaluarán en tiempo de ejecución. Por ejemplo, un enlace de datos de WPF sencillo se logra especificando `{Binding}` la extensión de marcado en lugar del valor que normalmente tardaría una propiedad determinada. Muchas de las extensiones de marcado de WPF habilitan una sintaxis de atributo para las propiedades en las que, de lo contrario, no sería posible una sintaxis de atributo. Por ejemplo, un <xref:System.Windows.Style> objeto es un tipo relativamente complejo que contiene una serie anidada de objetos y propiedades. Los estilos en WPF se definen normalmente como un recurso en <xref:System.Windows.ResourceDictionary>y, a continuación, se hace referencia a ellos a través de una de las dos extensiones de marcado de WPF que solicitan un recurso. La extensión de marcado pospone la evaluación del valor de la propiedad a una búsqueda de recursos y permite proporcionar el valor <xref:System.Windows.FrameworkElement.Style%2A> de la propiedad, <xref:System.Windows.Style>que toma el tipo, en la sintaxis de atributo como en el ejemplo siguiente:  
  
 `<Button Style="{StaticResource MyStyle}">My button</Button>`  
  
 Aquí, `StaticResource` se identifica <xref:System.Windows.StaticResourceExtension> la clase que proporciona la implementación de la extensión de marcado. La cadena `MyStyle` siguiente se usa como entrada para el constructor no predeterminado <xref:System.Windows.StaticResourceExtension> , donde el parámetro tomado de la cadena de extensión declara el solicitado <xref:System.Windows.ResourceKey>. `MyStyle`se espera que sea el valor [x:Key](../../xaml-services/x-key-directive.md) de un <xref:System.Windows.Style> definido como recurso. El uso de la [extensión de marcado StaticResource](staticresource-markup-extension.md) solicita que el recurso se use <xref:System.Windows.Style> para proporcionar el valor de la propiedad a través de la lógica de búsqueda de recursos estáticos en tiempo de carga.  
  
 Para más información sobre las extensiones de marcado, consulte [Extensiones de marcado y XAML de WPF](markup-extensions-and-wpf-xaml.md). Para obtener una referencia de las extensiones de marcado y otras características de programación XAML habilitadas en la implementación [de XAML de .net general, vea espacio de nombres XAML (x:). Características](../../xaml-services/xaml-namespace-x-language-features.md)del lenguaje. Para las extensiones de marcado específicas de WPF, vea [extensiones XAML de WPF](wpf-xaml-extensions.md).  
  
<a name="attached_properties"></a>   
## <a name="attached-properties"></a>Propiedades asociadas  
 Las propiedades adjuntas son un concepto de programación introducido en XAML, en el que las propiedades pueden ser propiedad y definidas por un tipo determinado, pero se establecen como atributos o elementos de propiedad en cualquier elemento. El escenario principal para el que se pretenden las propiedades adjuntas es permitir que los elementos secundarios de una estructura de marcado informen sobre la información a un elemento primario sin necesidad de un modelo de objetos compartidos exhaustivamente en todos los elementos. Por el contrario, los elementos primarios pueden usar las propiedades adjuntas para notificar información a los elementos secundarios. Para obtener más información sobre el propósito de las propiedades adjuntas y cómo crear sus propias propiedades adjuntas, vea [información general sobre las propiedades](attached-properties-overview.md)adjuntas.  
  
 Las propiedades adjuntas usan una sintaxis que se parece superficialmente a la sintaxis de los elementos de propiedad, en que también se especifica un *TypeName*. combinación *PropertyName* . Hay dos diferencias importantes:  
  
- Puede usar *TypeName*. combinación *PropertyName* incluso cuando se establece una propiedad adjunta a través de la sintaxis de atributo. Las propiedades adjuntas son el único caso en el que calificar el nombre de la propiedad es un requisito en una sintaxis de atributo.  
  
- También puede usar la sintaxis de elementos de propiedad para las propiedades adjuntas. Sin embargo, para la sintaxis de elementos de propiedad típica, el *TypeName* que especifique es el elemento de objeto que contiene el elemento de propiedad. Si hace referencia a una propiedad adjunta, *TypeName* es la clase que define la propiedad adjunta, no el elemento de objeto contenedor.  
  
<a name="attached_events"></a>   
## <a name="attached-events"></a>Eventos asociados  
 Los eventos adjuntos son otro concepto de programación incluido en XAML donde los eventos se pueden definir mediante un tipo específico, pero los controladores se pueden adjuntar en cualquier elemento de objeto. En la implementación de WOF, a menudo el tipo que define un evento adjunto es un tipo estático que define un servicio y, a veces, los eventos adjuntos se exponen mediante un alias de evento enrutado en los tipos que exponen el servicio. Los controladores de eventos adjuntos se especifican a través de la sintaxis de atributo. Al igual que con los eventos adjuntos, la sintaxis de atributo se expande para los eventos adjuntos para permitir un *TypeName*. *eventName* Usage, donde *TypeName* es la clase que proporciona `Add` los `Remove` descriptores de acceso y controladores de eventos para la infraestructura de eventos adjuntos y *eventName* es el nombre del evento.  
  
<a name="anatomy_of_a_xaml_page_root_element"></a>   
## <a name="anatomy-of-a-xaml-root-element"></a>Anatomía de un elemento raíz XAML  
 En la tabla siguiente se muestra un elemento raíz XAML típico dividido en el que se muestran los atributos específicos de un elemento raíz:  
  
|||  
|-|-|  
|`<Page`|Abrir el elemento de objeto del elemento raíz|  
|`xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"`|El espacio de[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]nombres XAML predeterminado ()|  
|`xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`|Espacio de nombres XAML del lenguaje XAML|  
|`x:Class="ExampleNamespace.ExampleCode"`|Declaración de clase parcial que conecta el marcado con cualquier código subyacente definido para la clase parcial.|  
|`>`|Fin del elemento de objeto para la raíz. El objeto no está cerrado todavía porque el elemento contiene elementos secundarios.|  
  
<a name="optional_and_nonrecommended_xaml_usages"></a>   
## <a name="optional-and-nonrecommended-xaml-usages"></a>Usos de XAML opcionales y no recomendados  
 En las secciones siguientes se describen los usos de XAML que técnicamente admiten los procesadores de XAML, pero que generan detalle u otros problemas estéticos que interfieren con los archivos XAML que quedan legibles para el usuario al desarrollar aplicaciones que contienen orígenes XAML.  
  
### <a name="optional-property-element-usages"></a>Usos opcionales de los elementos de propiedad  
 Los usos opcionales de los elementos de propiedad incluyen la escritura explícita de las propiedades de contenido del elemento que el procesador XAML considera implícita. Por ejemplo, al declarar el <xref:System.Windows.Controls.Menu>contenido de, podría elegir declarar explícitamente la <xref:System.Windows.Controls.ItemsControl.Items%2A> colección de <xref:System.Windows.Controls.Menu> como una `<Menu.Items>` etiqueta de elemento de propiedad y colocar cada una de ellas <xref:System.Windows.Controls.MenuItem> en `<Menu.Items>`, en lugar de en que usar el comportamiento del procesador XAML implícito que todos los elementos secundarios <xref:System.Windows.Controls.Menu> de un deben <xref:System.Windows.Controls.MenuItem> ser un y se colocan en la <xref:System.Windows.Controls.ItemsControl.Items%2A> colección. A veces, los usos opcionales pueden ayudar a aclarar visualmente la estructura del objeto como se representa en el marcado. O, en ocasiones, el uso explícito de un elemento de propiedad puede evitar el marcado que es técnicamente funcional pero confuso visualmente, como las extensiones de marcado anidadas dentro de un valor de atributo.  
  
### <a name="full-typenamemembername-qualified-attributes"></a>Atributos completos de typeName. memberName completos  
 *TypeName*. el formulario *memberName* para un atributo funciona realmente de forma más universal que el caso de los eventos enrutados. Pero en otras situaciones es superflua y debe evitarlo, si solo por motivos de estilo de marcado y legibilidad. En el siguiente ejemplo, cada una de las tres referencias al <xref:System.Windows.Controls.Control.Background%2A> atributo es completamente equivalente:  
  
 [!code-xaml[XAMLOvwSupport#TypeNameProp](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#typenameprop)]  
  
 `Button.Background`funciona porque la búsqueda calificada para esa propiedad <xref:System.Windows.Controls.Button> en es correcta<xref:System.Windows.Controls.Control.Background%2A> (se heredó del control) <xref:System.Windows.Controls.Button> y es la clase del elemento de objeto o una clase base. `Control.Background`funciona porque la <xref:System.Windows.Controls.Control> clase define <xref:System.Windows.Controls.Control.Background%2A> realmente y <xref:System.Windows.Controls.Control> es una <xref:System.Windows.Controls.Button> clase base.  
  
 Sin embargo, el *TypeName*siguiente. el ejemplo del formulario *memberName* no funciona y, por tanto, se muestra comentado:  
  
 [!code-xaml[XAMLOvwSupport#TypeNameBadProp](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#typenamebadprop)]  
  
 <xref:System.Windows.Controls.Label>es otra clase derivada de <xref:System.Windows.Controls.Control>y, si se hubiera especificado `Label.Background` dentro de <xref:System.Windows.Controls.Label> un elemento de objeto, este uso habría funcionado. Sin embargo, <xref:System.Windows.Controls.Label> dado que no es la clase o clase <xref:System.Windows.Controls.Button>base de, el comportamiento del procesador XAML especificado es `Label.Background` procesar después como una propiedad adjunta. `Label.Background`no es una propiedad adjunta disponible y se produce un error en este uso.  
  
### <a name="basetypenamemembername-property-elements"></a>Elementos de la propiedad Nombredetipobase. memberName  
 De forma análoga a como el *TypeName*. el formulario *memberName* funciona para la sintaxis de atributo, un *nombredetipobase*. la sintaxis *memberName* funciona para la sintaxis de elementos de propiedad. Por ejemplo, la sintaxis siguiente funciona:  
  
 [!code-xaml[XAMLOvwSupport#GoofyPE](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#goofype)]  
  
 Aquí, el elemento de propiedad se proporcionó como `Control.Background` aunque el elemento de propiedad estuviera incluido en. `Button`  
  
 Pero igual que *TypeName*. formulario *memberName* para atributos, *nombredetipobase*. *memberName* es un estilo pobre en el marcado y debe evitarlo.  
  
## <a name="see-also"></a>Vea también

- [Información general sobre XAML (WPF)](xaml-overview-wpf.md)
- [Espacio de nombres XAML (x:) Características del lenguaje](../../xaml-services/xaml-namespace-x-language-features.md)
- [Extensiones XAML de WPF](wpf-xaml-extensions.md)
- [Información general sobre las propiedades de dependencia](dependency-properties-overview.md)
- [Clases TypeConverter y XAML](typeconverters-and-xaml.md)
- [Clases XAML y personalizadas para WPF](xaml-and-custom-classes-for-wpf.md)
