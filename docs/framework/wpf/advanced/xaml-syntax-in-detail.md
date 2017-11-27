---
title: Detalles de la sintaxis XAML
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "26"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0aa85c9ec6e6b911444b07a4169dc769ac4df816
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="xaml-syntax-in-detail"></a>Detalles de la sintaxis XAML
Este tema definen los términos que se utilizan para describir los elementos de sintaxis de XAML. Estos términos se usan con frecuencia en el resto de esta documentación, tanto para la documentación de WPF específicamente y de otros marcos que utilizan XAML o los conceptos básicos de XAML habilitados por la compatibilidad del lenguaje XAML en el nivel de System.Xaml. En este tema se expande en la terminología básica presentada en el tema [información general sobre XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md).  
  

  
<a name="the_xaml_language_specification"></a>   
## <a name="the-xaml-language-specification"></a>La especificación del lenguaje XAML  
 La terminología de la sintaxis XAML definida aquí también está definida o se hace referencia en la especificación del lenguaje XAML. XAML es un lenguaje basado en XML y sigue o lo expande reglas estructurales de XML. Parte de la terminología que se comparten desde o se basa en la terminología utilizada normalmente al describir el lenguaje XML o el modelo de objetos de documento XML.  
  
 Para obtener más información acerca de la especificación del lenguaje XAML, descargue [ \[MS-XAML\] ](http://go.microsoft.com/fwlink/?LinkId=114525) desde Microsoft Download Center.  
  
<a name="xaml_and_clr"></a>   
## <a name="xaml-and-clr"></a>XAML y CLR  
 XAML es un lenguaje de marcado. El [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)], como implícita por su nombre, habilita el tiempo de ejecución. XAML no es por sí solo uno de los lenguajes comunes que se usan directamente en el tiempo de ejecución CLR. En su lugar, se puede considerar XAML como compatible con su propio sistema de tipos. El sistema de análisis de XAML determinado que se usa en WPF se basa en el CLR y el sistema de tipos CLR. Tipos XAML se asignan a los tipos CLR para crear instancias de una representación de tiempo de ejecución cuando se analiza el código XAML de WPF. Por esta razón, el resto de las explicaciones de sintaxis en este documento incluirá referencias al sistema de tipos CLR, aunque no las explicaciones de sintaxis equivalentes en la especificación del lenguaje XAML. (Según el nivel de especificación del lenguaje XAML, los tipos XAML pudieron asignarse a cualquier otro sistema de tipo, que no tiene que ser el CLR, pero que requeriría la creación y uso de un analizador XAML diferente.)  
  
#### <a name="members-of-types-and-class-inheritance"></a>Miembros de tipos y herencia de clases  
 Propiedades y eventos, a medida que aparecen como miembros XAML de un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tipo a menudo se heredan de los tipos base. Por ejemplo, considere este ejemplo: `<Button Background="Blue" .../>`. El <xref:System.Windows.Controls.Control.Background%2A> propiedad no es una propiedad declarada inmediatamente en el <xref:System.Windows.Controls.Button> de la clase, si deseara ver la definición de clase, los resultados de la reflexión o la documentación. En su lugar, <xref:System.Windows.Controls.Control.Background%2A> se hereda de la base de <xref:System.Windows.Controls.Control> clase.  
  
 El comportamiento de la herencia de clases de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elementos XAML es una desviación significativa de una interpretación aplicada por el esquema de marcado XML. Herencia de clases puede ser compleja, especialmente cuando las clases base intermedias son abstractas, o cuando se trate de interfaces. Se trata de una de las razones que el conjunto de elementos XAML y sus atributos permitidos es difícil representar con precisión y completamente con los tipos de esquema que se usa normalmente para [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] de programación, por ejemplo, formato XSD o DTD. Otro motivo es que extensibilidad y asignación de tipos de características del lenguaje XAML propio impiden la integridad de cualquier representación fija de los tipos permitidos y los miembros.  
  
<a name="object_element_syntax"></a>   
## <a name="object-element-syntax"></a>Sintaxis de elemento de objeto  
 *Sintaxis de elemento de objeto* es la sintaxis del marcado XAML que crea una instancia de una clase o estructura CLR declarando un elemento XML. Esta sintaxis es similar a la sintaxis de elemento de otros lenguajes de marcado como HTML. Sintaxis de elementos de objeto comienza con un corchete angular de apertura (\<), seguido inmediatamente por el nombre de tipo de la clase o estructura que se va a crear una instancia. Cero o más espacios pueden seguir el nombre de tipo, y también se pueden declarar cero o más atributos en el elemento de objeto, con uno o más espacios separando cada nombre de atributo = par de "value". Por último, uno de los siguientes debe cumplirse:  
  
-   El elemento y la etiqueta deben cerrarse por una barra diagonal (/), seguida inmediatamente por un corchete angular derecho (>).  
  
-   La etiqueta de apertura debe realizarse por un corchete angular derecho (>). Otros elementos de objeto, los elementos de propiedad o texto interno, puede seguir la etiqueta de apertura. Exactamente qué contenido puede incluirse aquí normalmente está restringido por el modelo de objetos del elemento. El equivalente de una etiqueta para el elemento de objeto de cierre también debe existir en un anidamiento correcto y equilibrar con otros pares de etiqueta de apertura y cierre.  
  
 XAML forma implementada por .NET tiene un conjunto de reglas que se asignan elementos de objeto en los tipos, atributos a propiedades o eventos y espacios de nombres XAML para espacios de nombres CLR, además de ensamblado. Para WPF y .NET Framework, los elementos de objeto XAML se asignan a [!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)] tipos tal como se define en hace referencia a ensamblados y los atributos se asignan a los miembros de esos tipos. Cuando se hace referencia a un tipo CLR en XAML, tendrá acceso a los miembros heredados de ese tipo también.  
  
 Por ejemplo, en el ejemplo siguiente es una sintaxis de elemento de objeto que crea una nueva instancia de la <xref:System.Windows.Controls.Button> clase y también especifica un <xref:System.Windows.FrameworkElement.Name%2A> atributo y un valor para ese atributo:  
  
 [!code-xaml[XAMLOvwSupport#SyntaxOE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#syntaxoe)]  
  
 En el ejemplo siguiente es una sintaxis de elemento de objeto que también incluyen la sintaxis de la propiedad de contenido de XAML. El texto interno dentro se utilizará para establecer el <xref:System.Windows.Controls.TextBox> propiedad de contenido de XAML, <xref:System.Windows.Controls.TextBox.Text%2A>.  
  
 [!code-xaml[XAMLOvwSupport#ThisIsATextBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#thisisatextbox)]  
  
### <a name="content-models"></a>Modelos de contenido  
 Una clase podría admitir su uso como un elemento de objeto XAML en cuanto a la sintaxis, pero dicho elemento sólo funcionará correctamente en una aplicación o página cuando se coloca en una posición esperada de un árbol de modelo o elemento de contenido general. Por ejemplo, un <xref:System.Windows.Controls.MenuItem> normalmente sólo deben colocarse como un elemento secundario de un <xref:System.Windows.Controls.Primitives.MenuBase> clase derivada como <xref:System.Windows.Controls.Menu>. Contenido de modelos para elementos específicos se documentan como parte de la sección de comentarios en las páginas de clase para los controles y otros [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] las clases que se pueden usar como elementos XAML.  
  
<a name="properties_of_object_elements"></a>   
## <a name="properties-of-object-elements"></a>Propiedades de los elementos de objeto  
 Propiedades en XAML se establecen mediante una variedad de posibles sintaxis. Qué sintaxis se puede usar para una propiedad determinada puede variar, según las características de sistema de tipo subyacente de la propiedad que se va a establecer.  
  
 Estableciendo valores de propiedades, se agregan características a los objetos tal como aparecen en el gráfico de objetos de tiempo de ejecución. El estado inicial del objeto creado desde un elemento de objeto se basa en el comportamiento del constructor predeterminado. Normalmente, la aplicación usará un valor distinto de una instancia completamente predeterminada de cualquier objeto determinado.  
  
<a name="attribute_syntax_properties"></a>   
## <a name="attribute-syntax-properties"></a>Sintaxis de atributos (propiedades)  
 La sintaxis de atributo es la sintaxis del marcado XAML que establece un valor para una propiedad declarando un atributo en un elemento de objeto existente. El nombre del atributo debe coincidir con el nombre de miembro CLR de la propiedad de la clase que respalda el elemento de objeto pertinente. El nombre de atributo es seguido por un operador de asignación (=). El valor del atributo debe ser una cadena entre comillas.  
  
> [!NOTE]
>  Puede usar comillas alternas para colocar una comilla literal dentro de un atributo. Por ejemplo puede utilizar comillas simples como medio para declarar una cadena que contiene un carácter de comillas dobles dentro de él. Si usa comillas simples o dobles, le conviene usar una pareja coincidente para abrir y cerrar la cadena del valor de atributo. También hay secuencias de escape u otras técnicas disponibles para trabajar con las restricciones de caracteres impuestas por una sintaxis XAML determinada. Vea [entidades de caracteres XML y XAML](../../../../docs/framework/xaml-services/xml-character-entities-and-xaml.md).  
  
 Para establecer a través de la sintaxis de atributo, una propiedad debe ser pública y debe ser de escritura. El valor de la propiedad en el sistema de tipos de respaldo debe ser un tipo de valor o debe ser un tipo de referencia que se pueden crear instancias o al que hace referencia un procesador XAML al obtener acceso a la correspondiente tipo de respaldo.  
  
 Para los eventos de XAML de WPF, el evento que se hace referencia como el nombre de atributo debe ser públicos y tener un delegado público.  
  
 La propiedad o evento debe ser un miembro de la clase o estructura que se crea una instancia del elemento de objeto contenedor.  
  
### <a name="processing-of-attribute-values"></a>Procesamiento de valores de atributo  
 El valor de cadena dentro de la apertura y comillas de cierre se procesa un procesador XAML. Para las propiedades, el comportamiento del procesamiento predeterminado viene determinado por el tipo de la propiedad CLR subyacente.  
  
 El valor del atributo se rellena mediante uno de los siguientes valores, utilizando este orden de procesamiento:  
  
1.  Si el procesador XAML encuentra una llave o un elemento de objeto que se deriva de <xref:System.Windows.Markup.MarkupExtension>, a continuación, se evalúa primero la extensión de marcado que se hace referencia en lugar de procesar el valor como una cadena y se utiliza el objeto devuelto por la extensión de marcado como el valor. En muchos casos, el objeto devuelto por una extensión de marcado será una referencia a un objeto existente, o una expresión que aplaza evaluación hasta el tiempo de ejecución y no es un objeto de la instancia recién creado.  
  
2.  Si la propiedad se declara con un con atributos <xref:System.ComponentModel.TypeConverter>, o el tipo de valor de esa propiedad se declara con un con atributos <xref:System.ComponentModel.TypeConverter>, se envía el valor de cadena del atributo para el convertidor de tipos como una entrada de conversión y devolverá el convertidor un nueva instancia de objeto.  
  
3.  Si no hay ningún <xref:System.ComponentModel.TypeConverter>, se intenta realizar una conversión directa para el tipo de propiedad. Este nivel final es una conversión directa en el valor analizador nativo entre los tipos primitivos del lenguaje XAML o una comprobación de los nombres de constantes con nombre en una enumeración (el analizador tiene acceso a los valores de búsqueda de coincidencias).  
  
#### <a name="enumeration-attribute-values"></a>Valores de atributo de enumeración  
 Enumeraciones en XAML se procesan de forma intrínseca analizadores de XAML y los miembros de una enumeración deben especificarse especificando el nombre de cadena de uno de constantes con nombre de la enumeración.  
  
 Para los valores de enumeración sin marcadores, el comportamiento nativo es procesar la cadena de un valor de atributo y resolverlo en uno de los valores de enumeración. No se especifica la enumeración en el formato *enumeración*. *Valor*, tal y como lo hace en el código. En su lugar, solo especifica *valor*, y *enumeración* se deduce el tipo de la propiedad que se va a establecer. Si especifica un atributo en el *enumeración*. *Valor* formulario, no se resolverá correctamente.  
  
 Para las enumeraciones basada en marcadores, el comportamiento se basa en el <xref:System.Enum.Parse%2A?displayProperty=nameWithType> método. Puede especificar varios valores para una enumeración basada en marcadores separando cada valor con una coma. Sin embargo, no se puede combinar valores de enumeración que no están basados en marcadores. Por ejemplo, no puede usar la sintaxis de comas para intentar crear un <xref:System.Windows.Trigger> que actúa en varias condiciones de una enumeración sin marcadores:  
  
```  
<!--This will not compile, because Visibility is not a flagwise enumeration.-->  
...  
<Trigger Property="Visibility" Value="Collapsed,Hidden">  
  <Setter ... />  
</Trigger>  
...  
```  
  
 Basada en marcadores enumeraciones que admiten los atributos que se pueden configurables en XAML son poco frecuentes en WPF. Sin embargo, es una de estas enumeraciones <xref:System.Windows.Media.StyleSimulations>. Por ejemplo, puede utilizar la sintaxis de atributo basada en marcadores delimitada por comas para modificar el ejemplo proporcionado en la sección Comentarios para el <xref:System.Windows.Documents.Glyphs> clase; `StyleSimulations = "BoldSimulation"` dejen de estar `StyleSimulations = "BoldSimulation,ItalicSimulation"`. <xref:System.Windows.Input.KeyBinding.Modifiers%2A?displayProperty=nameWithType>es otra propiedad donde se puede especificar más de un valor de enumeración. Sin embargo, esta propiedad resulta ser un caso especial, porque la <xref:System.Windows.Input.ModifierKeys> enumeración es compatible con su propio convertidor de tipos. El convertidor de tipos para los modificadores usa un signo más (+) como un delimitador en lugar de una coma (,). Esta conversión es compatible con la sintaxis más tradicional para representar las combinaciones de teclas en la programación de Microsoft Windows, como "CTRL+ALT".  
  
### <a name="properties-and-event-member-name-references"></a>Propiedades y referencias de nombre de miembro de evento  
 Al especificar un atributo, puede hacer referencia a cualquier propiedad o evento que existe como miembro del tipo CLR que crea una instancia para el elemento de objeto contenedor.  
  
 O bien, puede hacer referencia a una propiedad adjunta o evento asociado, independiente del elemento de objeto contenedor. (Propiedades adjuntas se tratan en una sección posterior).  
  
 También puede nombrar los eventos de cualquier objeto que sea accesible a través del espacio de nombres predeterminado mediante una *typeName*. *evento* nombre parcialmente completo; esta sintaxis permite asociar controladores para los eventos enrutados donde el controlador está diseñado para controlar los eventos de enrutamiento de los elementos secundarios, pero el elemento primario no tiene ese evento en su tabla de miembros. Esta sintaxis es similar a la sintaxis de eventos asociados, pero aquí el evento no es un evento adjunto es true. En su lugar, hace referencia a un evento con un nombre completo. Para obtener más información, consulte [enrutan Events Overview](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
 En algunos escenarios, los nombres de propiedad se proporcionan a veces como el valor de un atributo, en lugar de en el nombre del atributo. Ese nombre de propiedad también puede incluir calificadores, como la propiedad especificada en el formulario *ownerType*. *dependencyPropertyName*. Este escenario es común al escribir estilos o plantillas en XAML. Las reglas de procesamiento para los nombres de propiedad proporcionados como un valor de atributo son diferentes y se rigen por el tipo de la propiedad que se va a establecer o por los comportamientos de subsistemas WPF determinados. Para obtener más información, consulte [estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md).  
  
 Otro uso de nombres de propiedad es cuando un valor de atributo describe una relación de propiedades. Esta característica se usa para el enlace de datos y para los destinos de guión gráfico y está habilitada de forma la <xref:System.Windows.PropertyPath> clase y su convertidor de tipos. Para obtener una descripción más completa de la semántica de búsqueda, vea [sintaxis de PropertyPath XAML](../../../../docs/framework/wpf/advanced/propertypath-xaml-syntax.md).  
  
<a name="property_element_syntax"></a>   
## <a name="property-element-syntax"></a>Sintaxis de elementos de propiedad  
 *Sintaxis de elemento de propiedad* es una sintaxis que difiere ligeramente de las reglas de sintaxis XML básicas para los elementos. En XML, el valor de un atributo es de hecho una cadena, con la variación solo es posible que se está usando el formato de codificación de cadena. En XAML, puede asignar otros elementos de objeto para que sea el valor de una propiedad. Esta capacidad se habilita mediante la sintaxis de elemento de propiedad. En lugar de la propiedad que se especifica como un atributo dentro de la etiqueta de elemento, la propiedad se especifica utilizando un elemento de apertura de etiquetas en *elementTypeName*. *propertyName* formulario, el valor de la propiedad se especifica en y, a continuación, se cierra el elemento de propiedad.  
  
 En concreto, la sintaxis comienza con un corchete angular de apertura (\<), seguido inmediatamente por el nombre de tipo de la clase o estructura que está dentro de la sintaxis de elemento de propiedad. Esto va seguido inmediatamente por un punto (.), a continuación, por el nombre de una propiedad, a continuación, un corchete angular derecho (>). Al igual que con la sintaxis de atributo, esa propiedad debe existir dentro de los miembros públicos declarados del tipo especificado. El valor que se asignará a la propiedad está incluido dentro del elemento de propiedad. Por lo general, se asigna un valor como uno o más elementos de objeto, porque la especificación de objetos como valores es el escenario de esta sintaxis de elemento de propiedad está diseñada para la dirección. Por último, una etiqueta de cierre equivalente especificando el mismo *elementTypeName*. *propertyName* combinación debe proporcionarse, anidada y equilibrada con otras etiquetas de elemento correctamente.  
  
 Por ejemplo, la siguiente es la sintaxis de elemento de propiedad para el <xref:System.Windows.FrameworkElement.ContextMenu%2A> propiedad de un <xref:System.Windows.Controls.Button>.  
  
 [!code-xaml[XAMLOvwSupport#ContextMenu](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#contextmenu)]  
  
 El valor dentro de un elemento de propiedad también se puede asignar como texto interno, en casos donde se especifican el tipo de propiedad es un tipo de valor primitivo, como <xref:System.String>, o una enumeración que se especifique un nombre. Estos dos usos son un poco comunes, ya que cada uno de estos casos también podría usar una sintaxis de atributo más sencilla. Un escenario para rellenar un elemento de propiedad con una cadena es para las propiedades que no son propiedad de contenido XAML pero que se utilizan para la representación de texto de la interfaz de usuario y elementos de espacio en blanco determinados, como avances de línea deben aparecer en ese texto de interfaz de usuario. La sintaxis de atributo no puede conservar los avances de línea, pero pueden sintaxis de elemento de propiedad, siempre y cuando esté activa la conservación de espacios en blanco significativos (para obtener más información, consulte [procesamiento de espacios en blanco en XAML](../../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md)). Otro escenario es para que [x: Uid (directiva)](../../../../docs/framework/xaml-services/x-uid-directive.md) puede aplicarse al elemento property y, por tanto, marque el valor en como un valor que se debe traducir en WPF BAML de salida o por otras técnicas.  
  
 Un elemento de propiedad no se representa en el árbol lógico de WPF. Un elemento de propiedad es simplemente una sintaxis determinada para establecer una propiedad y no es un elemento que tiene una instancia o un objeto de copia de seguridad. (Para obtener más información sobre el concepto de árbol lógico, vea [árboles de WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md).)  
  
 Para las propiedades que se admiten la sintaxis de atributo y propiedad de elemento, las dos sintaxis tienen generalmente el mismo resultado, aunque sus detalles, como el control de espacios en blanco pueden variar ligeramente entre sintaxis.  
  
<a name="collection_syntax"></a>   
## <a name="collection-syntax"></a>Sintaxis de colecciones  
 La especificación de XAML requiere que las implementaciones de procesador XAML para identificar las propiedades que el tipo de valor es una colección. La implementación de procesador XAML general en .NET se basa en código administrado y el CLR e identifica los tipos de colección a través de uno de los siguientes:  
  
-   Escriba implementa <xref:System.Collections.IList>.  
  
-   Escriba implementa <xref:System.Collections.IDictionary>.  
  
-   Tipo que se deriva de <xref:System.Array> (para obtener más información acerca de las matrices en XAML, vea [extensión de marcado x: Array](../../../../docs/framework/xaml-services/x-array-markup-extension.md).)  
  
 Si el tipo de una propiedad es una colección, a continuación, el tipo de colección que se infiere no deben especificarse en el marcado como un elemento de objeto. En su lugar, los elementos que se van a ser los elementos de la colección se especifican como uno o más elementos secundarios del elemento property. Cada elemento de este tipo se evalúa en el objeto durante la carga y se agrega a la colección mediante una llamada a la `Add` método de la colección implícita. Por ejemplo, el <xref:System.Windows.Style.Triggers%2A> propiedad de <xref:System.Windows.Style> toma el tipo de colección especializadas <xref:System.Windows.TriggerCollection>, que implementa <xref:System.Collections.IList>. No es necesario crear una instancia de un <xref:System.Windows.TriggerCollection> elemento de objeto en el marcado. En su lugar, especifique uno o varios <xref:System.Windows.Trigger> elementos como elementos dentro de la `Style.Triggers` elemento de propiedad, donde <xref:System.Windows.Trigger> (o una clase derivada) es el tipo esperado como el tipo de elemento para fuertemente tipada e implícitas <xref:System.Windows.TriggerCollection>.  
  
 [!code-xaml[XAMLOvwSupport#SyntaxPECollection](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#syntaxpecollection)]  
  
 Una propiedad puede ser un tipo de colección y la propiedad de contenido XAML para ese tipo y tipos derivados, que se describe en la siguiente sección de este tema.  
  
 Un elemento de colección implícito crea a un miembro en la representación de árbol lógico, aunque no aparece en el marcado como un elemento. Normalmente el constructor del tipo primario realiza la creación de instancias para la colección que es una de sus propiedades y la colección inicialmente vacía se convierte en parte del árbol de objetos.  
  
> [!NOTE]
>  Las interfaces de lista y diccionario genéricas (<xref:System.Collections.Generic.IList%601> y <xref:System.Collections.Generic.IDictionary%602>) no se admiten para la detección de la colección. Sin embargo, puede usar el <xref:System.Collections.Generic.List%601> de clase como una clase base, porque implementa <xref:System.Collections.IList> directamente, o <xref:System.Collections.Generic.Dictionary%602> como una clase base, porque implementa <xref:System.Collections.IDictionary> directamente.  
  
 En las páginas de referencia de .NET para los tipos de colección, esta sintaxis con la omisión deliberada del elemento de objeto para una colección en ocasiones se indica en las secciones de sintaxis XAML como la sintaxis de colección implícita.  
  
 Con la excepción del elemento raíz, cada elemento de objeto en un archivo XAML que está anidado como elemento secundario de otro elemento es realmente un elemento que es uno o ambos de los siguientes casos: un miembro de una propiedad de colección implícita de su elemento primario , o un elemento que especifica el valor de la propiedad de contenido XAML del elemento primario (el XAML contenido propiedades se tratarán en una sección posterior). En otras palabras, la relación de elementos primarios y secundarios en una página de marcado es realmente un objeto único de la raíz, y cada elemento de objeto debajo de la raíz es una instancia única que proporciona un valor de propiedad del elemento primario o uno de los elementos dentro de una columna selección que también es un valor de propiedad de tipo de colección del elemento primario. Este concepto de raíz única es común en XML y se refuerza con frecuencia en el comportamiento de las API que cargan XAML como <xref:System.Windows.Markup.XamlReader.Load%2A>.  
  
 En el ejemplo siguiente se muestra una sintaxis con el elemento de objeto en una colección (<xref:System.Windows.Media.GradientStopCollection>) especificado explícitamente.  
  
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
  
 Tenga en cuenta que no siempre puede declarar explícitamente la colección. Por ejemplo, se intenta declarar <xref:System.Windows.TriggerCollection> explícitamente en el que se muestra anteriormente <xref:System.Windows.Style.Triggers%2A> en el ejemplo se produciría un error. La declaración explícita de la colección requiere que la clase de colección debe admitir un constructor predeterminado, y <xref:System.Windows.TriggerCollection> no tiene un constructor predeterminado.  
  
<a name="xaml_content_properties"></a>   
## <a name="xaml-content-properties"></a>Propiedades del contenido XAML  
 Sintaxis de contenido XAML es una sintaxis que sólo está habilitada en las clases que especifican el <xref:System.Windows.Markup.ContentPropertyAttribute> como parte de su declaración de clase. El <xref:System.Windows.Markup.ContentPropertyAttribute> hace referencia al nombre de propiedad que es la propiedad de contenido de ese tipo de elemento (incluidas las clases derivadas). Cuando se procesa un procesador XAML, los elementos secundarios o texto interno que se encuentran entre las etiquetas de cierre del elemento de objeto y de apertura se asignará a ser el valor de la propiedad de contenido XAML para ese objeto. Se puede especificar los elementos de propiedad explícitos de la propiedad de contenido, pero este uso no se muestra normalmente en las secciones de sintaxis XAML en la referencia. NET. La técnica explícita/detallada resulta útil a veces para lograr claridad en el marcado o como una cuestión de estilo de marcado, pero normalmente es el propósito de una propiedad de contenido mejorar el marcado que se pueden anidar elementos que están relacionados de manera intuitiva como elementos primarios y secundarios directamente. Etiquetas de elemento de propiedad para otras propiedades de un elemento no se asignan como "contenido" por una definición estricta de lenguaje XAML; que se procesan previamente en orden de procesamiento del analizador XAML y no se consideran "contenido".  
  
### <a name="xaml-content-property-values-must-be-contiguous"></a>Valores de propiedad de contenido XAML deben ser contiguos  
 El valor de una propiedad de contenido XAML debe contar con completamente antes o después de cualquier otro elemento de propiedad en ese elemento de objeto. Esto es cierto si el valor de una propiedad de contenido de XAML se especifica como una cadena o como uno o varios objetos. Por ejemplo, no analiza el siguiente marcado:  
  
```  
<Button>I am a   
  <Button.Background>Blue</Button.Background>  
  blue button</Button>  
```  
  
 Esto no es válido básicamente porque si esta sintaxis se hiciera explícita utilizando la sintaxis de elemento de propiedad para la propiedad de contenido, a continuación, la propiedad de contenido se establecería dos veces:  
  
```xml  
<Button>  
  <Button.Content>I am a </Button.Content>  
  <Button.Background>Blue</Button.Background>  
  <Button.Content> blue button</Button.Content>  
</Button>  
```  
  
 Un ejemplo del mismo modo no válido es si la propiedad de contenido es una colección y los elementos secundarios están intercalados con elementos de propiedad:  
  
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
 Para poder aceptar más de un elemento de objeto único como contenido, el tipo de la propiedad de contenido concreto debe ser un tipo de colección. Similar a la sintaxis de elemento de propiedad para los tipos de colección, un procesador XAML debe identificar tipos que son tipos de colección. Si un elemento tiene una propiedad de contenido de XAML y el tipo de la propiedad de contenido XAML es una colección, a continuación, el tipo de colección implícita no tiene que especificarse en el marcado como un elemento de objeto y la propiedad de contenido XAML no deben especificarse como una lista de eventos de propiedad ependen. Por lo tanto, el modelo de contenido aparente en el marcado ahora puede tener más de un elemento secundario que se asigna como el contenido. La siguiente es la sintaxis de contenido para un <xref:System.Windows.Controls.Panel> clase derivada. Todos los <xref:System.Windows.Controls.Panel> clases derivadas establecer la propiedad de contenido XAML para que sea <xref:System.Windows.Controls.Panel.Children%2A>, lo que requiere un valor de tipo <xref:System.Windows.Controls.UIElementCollection>.  
  
 [!code-xaml[XAMLOvwSupport#SyntaxContent](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page5.xaml#syntaxcontent)]  
  
 Tenga en cuenta que ni el elemento de propiedad para <xref:System.Windows.Controls.Panel.Children%2A> ni el elemento para el <xref:System.Windows.Controls.UIElementCollection> se requiere en el marcado. Esta es una característica de diseño de XAML para que los elementos que definen de contenidos de forma recursiva un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] son más intuitiva, se representan como un árbol de elementos anidados con relaciones del elemento inmediata de elementos primarios y secundarios, sin etiquetas de elemento de propiedad intermedias o objetos de colección. De hecho, <xref:System.Windows.Controls.UIElementCollection> no puede especificarse explícitamente en el marcado como un elemento de objeto, por diseño. Dado que su único uso previsto es como una colección implícita, <xref:System.Windows.Controls.UIElementCollection> no expone un constructor público predeterminado y, por tanto, no pueden crearse instancias como un elemento de objeto.  
  
### <a name="mixing-property-elements-and-object-elements-in-an-object-with-a-content-property"></a>Combinación de elementos de propiedad y los elementos de objeto en un objeto con una propiedad de contenido  
 La especificación de XAML declara que un procesador XAML puede exigir que los elementos de objeto que se usan para rellenar la propiedad de contenido XAML dentro de un elemento de objeto deben ser contiguos y no se deben combinar. Se aplica esta restricción contra la mezcla de elementos de propiedad y el contenido por el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] procesadores XAML.  
  
 Puede tener un elemento de objeto secundario como el primer marcado inmediato dentro de un elemento de objeto. A continuación, puede introducir elementos de propiedad. O bien, puede especificar uno o más elementos de propiedad, contenido y, luego, más elementos de propiedad. Sin embargo, una vez que un elemento de propiedad sigue al contenido, no puede introducir cualquier otro tipo de contenido, solo puede agregar elementos de propiedad.  
  
 Este contenido o el requisito de orden del elemento de propiedad no se aplica al texto interno utilizado como contenido. Sin embargo, sigue siendo un buen estilo de marcado para mantener el texto interno contiguo, porque el espacio en blanco significativo será difícil de detectar visualmente en el marcado si los elementos de propiedad están intercalados con texto interno.  
  
<a name="xaml_namespaces"></a>   
## <a name="xaml-namespaces"></a>Espacios de nombres XAML  
 Ninguno de los ejemplos de sintaxis anterior especifica un espacio de nombres XAML que no sea de espacio de nombres XAML predeterminado. En los típicos [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplicaciones, el espacio de nombres XAML predeterminado se especifica como el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] espacio de nombres. Puede especificar espacios de nombres XAML que no sea de espacio de nombres XAML predeterminado y seguir usando una sintaxis similar. Pero, a continuación, en cualquier lugar donde se denomina una clase que no es accesible dentro del espacio de nombres XAML predeterminado, ese nombre de clase debe ir precedido por el prefijo de espacio de nombres XAML según se ha asignado para el espacio de nombres CLR correspondiente. Por ejemplo, `<custom:Example/>` es una sintaxis de elemento de objeto para crear una instancia de la `Example` (clase), donde el espacio de nombres CLR que contiene esa clase (y, posiblemente, la información de ensamblado externo que contiene los tipos de respaldo) se ha asignado anteriormente a la `custom` prefijo.  
  
 Para obtener más información acerca de espacios de nombres XAML, vea [XAML Namespaces and Namespace Mapping para XAML de WPF](../../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).  
  
<a name="markup_extensions"></a>   
## <a name="markup-extensions"></a>Extensiones de marcado  
 XAML define una entidad que permite un escape desde el control de procesador XAML normal de valores de atributo de cadena o elementos de objeto y cede el procesamiento a una clase de respaldo de programación de la extensión de marcado. El carácter que identifica una extensión de marcado para un procesador XAML cuando se utiliza la sintaxis de atributo es la llave de apertura ({}), seguida de cualquier carácter que no sea una llave de cierre (}). La primera cadena que sigue la llave de apertura debe hacer referencia a la clase que proporciona el comportamiento de extensión determinado, donde la referencia puede omitir la subcadena "Extensión" si dicha subcadena forma parte del nombre de clase es true. Posteriormente, puede aparecer un solo espacio y, a continuación, cada carácter subsiguiente se usa como entrada mediante la implementación de extensión, hasta que se encuentra la llave de cierre.  
  
 La implementación de XAML de .NET utiliza la <xref:System.Windows.Markup.MarkupExtension> clase abstracta como base para todas las extensiones de marcado compatibles con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , así como otros marcos o tecnologías. Las extensiones de marcado que [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] específicamente implementa a menudo está pensada para proporcionar un medio para hacer referencia a otros objetos ya existentes, o para hacer referencias diferidas a los objetos que se evaluará en tiempo de ejecución. Por ejemplo, un enlace de datos simple de WPF se consigue especificando la `{Binding}` extensión de marcado en lugar del valor que tomaría normalmente una propiedad determinada. Muchas de las extensiones de marcado WPF permiten una sintaxis de atributo para las propiedades donde una sintaxis de atributo no sería posible. Por ejemplo, un <xref:System.Windows.Style> objeto es un tipo relativamente complejo que contiene una serie de objetos y propiedades anidada. Los estilos en WPF se definen normalmente como un recurso en un <xref:System.Windows.ResourceDictionary>y, a continuación, hacer referencia a través de una de las dos extensiones de marcado WPF que solicitan un recurso. La extensión de marcado cede la evaluación del valor de propiedad para una búsqueda de recursos y permite proporcionar el valor de la <xref:System.Windows.FrameworkElement.Style%2A> propiedad, teniendo un tipo <xref:System.Windows.Style>, en atributo sintaxis como en el ejemplo siguiente:  
  
 `<Button Style="{StaticResource MyStyle}">My button</Button>`  
  
 En este caso, `StaticResource` identifica el <xref:System.Windows.StaticResourceExtension> clase que proporciona la implementación de extensión de marcado. La siguiente cadena `MyStyle` se utiliza como entrada para los valores no predeterminados <xref:System.Windows.StaticResourceExtension> constructor, donde el parámetro que se toman de la cadena de extensión declara solicitado <xref:System.Windows.ResourceKey>. `MyStyle`se espera que sea la [x: Key](../../../../docs/framework/xaml-services/x-key-directive.md) valor de un <xref:System.Windows.Style> define como un recurso. El [extensión de marcado StaticResource](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md) uso solicita que el recurso se usa para proporcionar la <xref:System.Windows.Style> valor de propiedad a través de la lógica de búsqueda de recurso estático en tiempo de carga.  
  
 Para más información sobre las extensiones de marcado, consulte [Extensiones de marcado y XAML de WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md). Para obtener una referencia de extensiones de marcado y otra características habilitadas en la implementación XAML de .NET general de programación de XAML, vea [XAML Namespace (x:) Características del lenguaje](../../../../docs/framework/xaml-services/xaml-namespace-x-language-features.md). Para las extensiones de marcado específico de WPF, vea [las extensiones de XAML de WPF](../../../../docs/framework/wpf/advanced/wpf-xaml-extensions.md).  
  
<a name="attached_properties"></a>   
## <a name="attached-properties"></a>Propiedades asociadas  
 Las propiedades asociadas son un concepto de programación introducido en XAML mediante el cual se pueden propiedad propiedades y definidas por un tipo determinado, pero establecer como atributos o elementos de propiedad en cualquier elemento. El escenario principal que están destinadas a las propiedades adjuntas es permitir que los elementos secundarios en una estructura de marcado para proporcionar información a un elemento primario sin necesidad de un modelo de objetos compartido por todos los elementos. Por el contrario, las propiedades adjuntas pueden usarse por los elementos primarios para proporcionar información a los elementos secundarios. Para obtener más información sobre el propósito de las propiedades adjuntas y cómo crear sus propias propiedades adjuntas, vea [Attached Properties Overview](../../../../docs/framework/wpf/advanced/attached-properties-overview.md).  
  
 Propiedades adjuntas utilizan una sintaxis que parece superficialmente a la sintaxis de elemento de propiedad, en que especifique también una *typeName*. *propertyName* combinación. Hay dos diferencias importantes:  
  
-   Puede usar el *typeName*. *propertyName* combinación incluso cuando se establece una propiedad asociada a través de la sintaxis de atributo. Las propiedades asociadas son el único caso en el que certificar el nombre de propiedad es un requisito en una sintaxis de atributo.  
  
-   También puede utilizar la sintaxis de elemento de propiedad para las propiedades asociadas. Sin embargo, para la sintaxis de elementos de propiedad típica, el *typeName* especificar es el elemento de objeto que contiene el elemento de propiedad. Si se hace referencia a una propiedad adjunta, la *typeName* es la clase que define la propiedad adjunta, no el elemento de objeto contenedor.  
  
<a name="attached_events"></a>   
## <a name="attached-events"></a>Eventos asociados  
 Los eventos adjuntos son otro concepto de programación introducido en XAML donde se pueden definir eventos con un tipo específico, pero los controladores se pueden adjuntar a cualquier elemento de objeto. En la implementación de WOF, a menudo el tipo que define un evento adjunto es un tipo estático que define un servicio y, a veces un alias de evento enrutado en tipos que expone el servicio expone los eventos asociados. Controladores de eventos asociados se especifican mediante la sintaxis de atributo. Como con eventos asociados, la sintaxis de atributo se expande para que los eventos asociados permitir que un *typeName*. *eventName* uso, donde *typeName* es la clase que proporciona `Add` y `Remove` descriptores de acceso de controlador de eventos para la infraestructura de evento adjunto, y *eventName* es el nombre del evento.  
  
<a name="anatomy_of_a_xaml_page_root_element"></a>   
## <a name="anatomy-of-a-xaml-root-element"></a>Anatomía de un elemento raíz XAML  
 En la tabla siguiente muestra un típico elemento raíz XAML desglosado, que muestra los atributos específicos de un elemento raíz:  
  
|||  
|-|-|  
|`<Page`|Elemento de objeto de apertura del elemento raíz|  
|`xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"`|El valor predeterminado ([!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]) espacio de nombres XAML|  
|`xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`|El espacio de nombres XAML de lenguaje XAML|  
|`x:Class="ExampleNamespace.ExampleCode"`|La declaración de clase parcial que conecta el marcado con cualquier código subyacente definido para la clase parcial|  
|`>`|Final del elemento de objeto para la raíz. Objeto todavía no se cierra porque el elemento contiene elementos secundarios|  
  
<a name="optional_and_nonrecommended_xaml_usages"></a>   
## <a name="optional-and-nonrecommended-xaml-usages"></a>Usos XAML es opcional y recomiendan  
 En las siguientes secciones se describen los usos XAML que son técnicamente compatibles con los procesadores XAML, pero que generan detalle u otros problemas estéticos que interfieren con archivos XAML restantes legible cuando el desarrollo de aplicaciones que contienen orígenes XAML .  
  
### <a name="optional-property-element-usages"></a>Usos de elemento de propiedad opcional  
 Usos de elemento de propiedad opcional incluyen la escritura explícitamente las propiedades de contenido del elemento que el procesador XAML considera implícito. Por ejemplo, cuando se declara el contenido de un <xref:System.Windows.Controls.Menu>, podría optar por declarar explícitamente la <xref:System.Windows.Controls.ItemsControl.Items%2A> colección de la <xref:System.Windows.Controls.Menu> como un `<Menu.Items>` etiqueta de elemento de propiedad y colóquelo cada <xref:System.Windows.Controls.MenuItem> dentro de `<Menu.Items>`, en su lugar que el uso del comportamiento del procesador XAML implícita que todos los elementos secundarios de un <xref:System.Windows.Controls.Menu> debe ser un <xref:System.Windows.Controls.MenuItem> y se colocan en la <xref:System.Windows.Controls.ItemsControl.Items%2A> colección. A veces los usos opcionales pueden ayudar a clarificar visualmente la estructura del objeto tal como está representado en el marcado. O bien, en ocasiones, el uso de un elemento de propiedad explícitos puede evitar un marcado que es técnicamente funcional pero visualmente confuso, como las extensiones de marcado anidados dentro de un valor de atributo.  
  
### <a name="full-typenamemembername-qualified-attributes"></a>Atributos nombreDeTipo.nombreDeMiembro completos  
 El *typeName*. *memberName* formulario para un atributo funciona más universalmente que solo el caso del evento enrutado. Pero en otras situaciones ese formulario es superfluo y no debe, si solo por razones de estilo de marcado y mejorar la legibilidad. En el ejemplo siguiente, cada una de las tres referencias a la <xref:System.Windows.Controls.Control.Background%2A> atributo son completamente equivalentes:  
  
 [!code-xaml[XAMLOvwSupport#TypeNameProp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#typenameprop)]  
  
 `Button.Background`funciona porque la búsqueda calificada de esa propiedad en <xref:System.Windows.Controls.Button> es correcta (<xref:System.Windows.Controls.Control.Background%2A> se heredó de Control) y <xref:System.Windows.Controls.Button> es la clase del elemento de objeto o una clase base. `Control.Background`funciona porque el <xref:System.Windows.Controls.Control> clase realmente define <xref:System.Windows.Controls.Control.Background%2A> y <xref:System.Windows.Controls.Control> es un <xref:System.Windows.Controls.Button> clase base.  
  
 Sin embargo, la siguiente *typeName*. *memberName* ejemplo de form no funciona y, por tanto, se muestra marcado como comentario:  
  
 [!code-xaml[XAMLOvwSupport#TypeNameBadProp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#typenamebadprop)]  
  
 <xref:System.Windows.Controls.Label>es otra clase derivada de <xref:System.Windows.Controls.Control>, y si hubiera especificado `Label.Background` dentro de un <xref:System.Windows.Controls.Label> elemento de objeto, este uso habría funcionado. Sin embargo, dado que <xref:System.Windows.Controls.Label> no es la clase o clase base de <xref:System.Windows.Controls.Button>, el comportamiento del procesador XAML especificado es, a continuación, procesar `Label.Background` como una propiedad adjunta. `Label.Background`no es una propiedad adjunta disponible y se produce un error en este uso.  
  
### <a name="basetypenamemembername-property-elements"></a>Propiedad nombreDeTipoBase.nombreDeMiembro  
 De forma similar a cómo el *typeName*. *memberName* formulario funciona para la sintaxis de atributo, una *nombreDeTipoBase*. *memberName* sintaxis funciona para la sintaxis de elemento de propiedad. Por ejemplo, la sintaxis siguiente funciona:  
  
 [!code-xaml[XAMLOvwSupport#GoofyPE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#goofype)]  
  
 En este caso, el elemento de propiedad se proporciona como `Control.Background` aunque contenía el elemento de propiedad `Button`.  
  
 Pero al igual que *typeName*. *memberName* formato de los atributos, *nombreDeTipoBase*. *memberName* un estilo pobre en el marcado y se debe evitar.  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [Características de lenguaje (x:) de espacios de nombres XAML](../../../../docs/framework/xaml-services/xaml-namespace-x-language-features.md)  
 [Extensiones XAML de WPF](../../../../docs/framework/wpf/advanced/wpf-xaml-extensions.md)  
 [Información general sobre las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
 [Clases TypeConverter y XAML](../../../../docs/framework/wpf/advanced/typeconverters-and-xaml.md)  
 [Clases XAML y personalizadas para WPF](../../../../docs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)
