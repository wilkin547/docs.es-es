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
ms.openlocfilehash: 98ca530da28591fec23a5036b421d02b393e83b5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59149310"
---
# <a name="xaml-syntax-in-detail"></a>Detalles de la sintaxis XAML
Este tema definen los términos que se utilizan para describir los elementos de sintaxis XAML. Estos términos se usan con frecuencia en el resto de esta documentación, tanto para la documentación de WPF específicamente y otros marcos que utilizan XAML o los conceptos básicos de XAML habilitados por la compatibilidad del lenguaje XAML en el nivel de System.Xaml. En este tema se amplía la terminología básica presentada en el tema [información general sobre XAML (WPF)](xaml-overview-wpf.md).  

<a name="the_xaml_language_specification"></a>   
## <a name="the-xaml-language-specification"></a>La especificación del lenguaje XAML  
 La terminología de sintaxis XAML definida aquí también se define o hace referencia en la especificación del lenguaje XAML. XAML es un lenguaje basado en XML y sigue o lo expande reglas estructurales de XML. La terminología se comparte o se basa en la terminología utilizada normalmente al describir el lenguaje XML o el modelo de objetos de documento XML.  
  
 Para obtener más información acerca de la especificación del lenguaje XAML, descargue [ \[MS-XAML\] ](https://go.microsoft.com/fwlink/?LinkId=114525) desde Microsoft Download Center.  
  
<a name="xaml_and_clr"></a>   
## <a name="xaml-and-clr"></a>XAML y CLR  
 XAML es un lenguaje de marcado. El [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)], como implícita por su nombre, habilita la ejecución. XAML no es por sí solo uno de los lenguajes comunes que se consume directamente en el tiempo de ejecución CLR. En su lugar, se puede considerar XAML como compatible con su propio sistema de tipos. El sistema de análisis de XAML concreto que usa WPF se basa en el CLR y el sistema de tipos CLR. Tipos XAML se asignan a tipos CLR para crear una representación en tiempo de ejecución cuando se analiza el XAML para WPF. Por este motivo, el resto de la explicación de la sintaxis de este documento incluirá referencias al sistema de tipos CLR, aunque no lo hacen las discusiones de sintaxis equivalente en la especificación del lenguaje XAML. (Por el nivel de especificación del lenguaje XAML, los tipos XAML podrían asignarse a cualquier otro sistema de tipo, que no tiene que ser el CLR, pero que requeriría la creación y uso de un analizador XAML diferente.)  
  
#### <a name="members-of-types-and-class-inheritance"></a>Miembros de tipos y herencia de clases  
 Propiedades y eventos que aparecen como miembros XAML de un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tipo a menudo se heredan de tipos base. Por ejemplo, considere este ejemplo: `<Button Background="Blue" .../>`. El <xref:System.Windows.Controls.Control.Background%2A> propiedad no es una propiedad declarada inmediatamente en el <xref:System.Windows.Controls.Button> clase, si fuera a mirar la definición de clase, los resultados de la reflexión o la documentación. En su lugar, <xref:System.Windows.Controls.Control.Background%2A> se hereda de la base de <xref:System.Windows.Controls.Control> clase.  
  
 El comportamiento de herencia de clases de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elementos XAML es un cambio significativo respecto de una interpretación impuestas por el esquema de marcado XML. Herencia de clases puede ser compleja, especialmente cuando las clases base intermedias son abstractas o cuando se trata de interfaces. Se trata de una razón por la que el conjunto de elementos XAML y sus atributos permitidos es difícil representar con precisión y completamente con los tipos de esquema que se usa normalmente para [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] de programación, como formato XSD o DTD. Otro motivo es que extensibilidad e -asignación de tipos de características del lenguaje XAML propio impidan la integridad de cualquier representación fija de los tipos permitidos y miembros.  
  
<a name="object_element_syntax"></a>   
## <a name="object-element-syntax"></a>Sintaxis de elemento de objeto  
 *Sintaxis de elemento de objeto* es la sintaxis de marcado XAML que crea una instancia de una clase o estructura CLR declarando un elemento XML. Esta sintaxis es similar a la sintaxis de elemento de otros lenguajes de marcado, como HTML. Sintaxis de elemento de objeto comienza con un corchete angular de apertura (\<), seguida inmediatamente por el nombre de la clase o estructura que se crea una instancia de tipo. Cero o más espacios pueden seguir el nombre de tipo, y también se pueden declarar cero o más atributos en el elemento de objeto, con uno o varios espacios, separando cada nombre de atributo = par "value". Por último, uno de los siguientes debe ser true:  
  
-   El elemento y la etiqueta deben cerrarse por una barra diagonal (/), seguida inmediatamente por un corchete angular derecho (>).  
  
-   La etiqueta de apertura debe realizarse por un corchete angular derecho (>). Otros elementos de objeto, los elementos de propiedad o el texto interno, puede seguir la etiqueta de apertura. Exactamente qué contenido puede ser incluido aquí normalmente está restringido por el modelo de objetos del elemento. El equivalente en la etiqueta de cierre para el elemento de objeto también debe existir en un anidamiento correcto y equilibrar con otros pares de etiqueta de apertura y cierre.  
  
 XAML forma implementada por .NET tiene un conjunto de reglas que asignan elementos de objeto en tipos de atributos en las propiedades o eventos y los espacios de nombres XAML para espacios de nombres CLR y ensamblados. Para WPF y .NET Framework, se asignan a elementos de objeto XAML [!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)] tipos definidos en ensamblados de referencia y los atributos se asignan a los miembros de esos tipos. Cuando se hace referencia a un tipo CLR en XAML, tendrá acceso a los miembros heredados de ese tipo también.  
  
 Por ejemplo, el ejemplo siguiente es la sintaxis de elemento de objeto que se crea una nueva instancia de la <xref:System.Windows.Controls.Button> clase y también especifica un <xref:System.Windows.FrameworkElement.Name%2A> atributo y un valor para ese atributo:  
  
 [!code-xaml[XAMLOvwSupport#SyntaxOE](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#syntaxoe)]  
  
 El ejemplo siguiente es la sintaxis de elemento de objeto que también incluyen la sintaxis de propiedad de contenido XAML. El texto interno dentro de que se usará para establecer el <xref:System.Windows.Controls.TextBox> propiedad de contenido XAML, <xref:System.Windows.Controls.TextBox.Text%2A>.  
  
 [!code-xaml[XAMLOvwSupport#ThisIsATextBox](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#thisisatextbox)]  
  
### <a name="content-models"></a>Modelos de contenido  
 Una clase podría admitir su uso como un elemento de objeto XAML en términos de la sintaxis, pero ese elemento solo funcionará correctamente en una aplicación o página cuando se coloca en una posición esperada de un árbol de modelo o elemento de contenido general. Por ejemplo, un <xref:System.Windows.Controls.MenuItem> normalmente solo se debe colocar como un elemento secundario de un <xref:System.Windows.Controls.Primitives.MenuBase> clase derivada como <xref:System.Windows.Controls.Menu>. Contenido de los modelos para elementos específicos se documentan como parte de la sección de comentarios en las páginas de la clase de controles y otros [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] las clases que se pueden usar como elementos XAML.  
  
<a name="properties_of_object_elements"></a>   
## <a name="properties-of-object-elements"></a>Propiedades de elementos de objeto  
 Se establecen propiedades en XAML mediante una variedad de posibles sintaxis. La sintaxis que se puede usar para una propiedad determinada varían en función de las características del sistema de tipo subyacente de la propiedad que se va a establecer.  
  
 Al establecer los valores de propiedades, se agregan características a los objetos tal y como aparecen en el gráfico de objetos de tiempo de ejecución. El estado inicial del objeto creado desde un elemento de objeto se basa en el comportamiento del constructor predeterminado. Normalmente, la aplicación usará un valor distinto de una instancia completamente predeterminada de cualquier objeto determinado.  
  
<a name="attribute_syntax_properties"></a>   
## <a name="attribute-syntax-properties"></a>Sintaxis de atributos (propiedades)  
 Sintaxis de atributo es la sintaxis de marcado XAML que establece un valor para una propiedad declarando un atributo en un elemento de objeto existente. El nombre del atributo debe coincidir con el nombre de miembro CLR de la propiedad de la clase que respalda el elemento del objeto pertinente. El nombre de atributo es seguido por un operador de asignación (=). El valor del atributo debe ser una cadena entre comillas.  
  
> [!NOTE]
>  Puede usar comillas alternas para colocar una comilla literal dentro de un atributo. Por ejemplo puede usar comillas simples como un medio para declarar una cadena que contiene un carácter de comillas dobles dentro de él. Si utiliza comillas simples o dobles, debe usar un par coincidente de apertura y cierre de la cadena del valor de atributo. También hay secuencias de escape u otras técnicas disponibles para evitar las restricciones de caracteres impuestas por cualquier sintaxis XAML determinada. Consulte [entidades de caracteres XML y XAML](../../xaml-services/xml-character-entities-and-xaml.md).  
  
 Para poder establecerse a través de la sintaxis de atributo, una propiedad debe ser pública y debe ser grabable. El valor de la propiedad en el sistema de tipos de respaldo debe ser un tipo de valor, o debe ser un tipo de referencia que se puede crear una instancia o hace referencia a un procesador XAML al obtener acceso a la correspondiente tipo de respaldo.  
  
 Para los eventos de WPF XAML, el evento que se hace referencia como el nombre del atributo debe ser público y tener un delegado público.  
  
 La propiedad o evento debe ser miembro de la clase o estructura que se crea una instancia por el elemento del objeto contenedor.  
  
### <a name="processing-of-attribute-values"></a>Procesamiento de valores de atributo  
 El valor de cadena dentro de la apertura y comillas de cierre es procesado por un procesador XAML. Para las propiedades, el comportamiento del procesamiento predeterminado viene determinada por el tipo de la propiedad CLR subyacente.  
  
 El valor del atributo se rellena con uno de los siguientes, con este orden de procesamiento:  
  
1.  Si el procesador XAML encuentra una llave de cierre o un elemento de objeto que se deriva de <xref:System.Windows.Markup.MarkupExtension>, a continuación, se evalúa primero la extensión de marcado que se hace referencia en lugar de procesar el valor como una cadena y el objeto devuelto por la extensión de marcado se utiliza como el valor. En muchos casos, el objeto devuelto por una extensión de marcado será una referencia a un objeto existente, o una expresión que aplaza la evaluación hasta el tiempo de ejecución y no es un objeto de instancia recién creado.  
  
2.  Si se declara la propiedad con un atributo <xref:System.ComponentModel.TypeConverter>, o el tipo de valor de esa propiedad se declara con un atributo <xref:System.ComponentModel.TypeConverter>, se envía el valor de cadena del atributo para el convertidor de tipos como una entrada de conversión y el convertidor devolverá un nueva instancia de objeto.  
  
3.  Si no hay ningún <xref:System.ComponentModel.TypeConverter>, se intenta realizar una conversión directa para el tipo de propiedad. Este nivel final es una conversión directa en el valor de analizador nativo entre los tipos primitivos del lenguaje XAML o una comprobación de los nombres de constantes con nombre en una enumeración (el analizador tiene acceso a los valores de búsqueda de coincidencias).  
  
#### <a name="enumeration-attribute-values"></a>Valores de atributo de enumeración  
 Las enumeraciones en XAML se procesan intrínsecamente analizadores de XAML y se deben especificar los miembros de una enumeración especificando el nombre de la cadena de una de las constantes con nombre de la enumeración.  
  
 Para los valores de enumeración sin marcadores, el comportamiento nativo es procesar la cadena de un valor de atributo y resolverlo en uno de los valores de enumeración. No se especifica la enumeración en el formato *enumeración*. *Valor*, al igual que en el código. En su lugar, especifique solo *valor*, y *enumeración* se deduce el tipo de la propiedad que se va a establecer. Si especifica un atributo en el *enumeración*. *Valor* formulario, no se resolverá correctamente.  
  
 Para las enumeraciones basada en marcas, el comportamiento se basa en el <xref:System.Enum.Parse%2A?displayProperty=nameWithType> método. Puede especificar varios valores para una enumeración basada en marcadores separando cada valor con una coma. Sin embargo, no puede combinar valores de enumeración que no están basados en marcadores. Por ejemplo, no se puede usar la sintaxis de comas para intentar crear un <xref:System.Windows.Trigger> que actúa en varias condiciones de una enumeración sin marcadores:  
  
```  
<!--This will not compile, because Visibility is not a flagwise enumeration.-->  
...  
<Trigger Property="Visibility" Value="Collapsed,Hidden">  
  <Setter ... />  
</Trigger>  
...  
```  
  
 Basada en marcas enumeraciones que admiten los atributos que se pueden configurables en XAML son poco frecuentes en WPF. Sin embargo, es una de estas enumeraciones <xref:System.Windows.Media.StyleSimulations>. Por ejemplo, podría usar la sintaxis de atributo basada en marcas delimitada por comas para modificar el ejemplo proporcionado en la sección Comentarios para el <xref:System.Windows.Documents.Glyphs> clase; `StyleSimulations = "BoldSimulation"` podría convertirse en `StyleSimulations = "BoldSimulation,ItalicSimulation"`. <xref:System.Windows.Input.KeyBinding.Modifiers%2A?displayProperty=nameWithType> es otra propiedad donde se puede especificar más de un valor de enumeración. Sin embargo, esta propiedad resulta ser un caso especial, porque el <xref:System.Windows.Input.ModifierKeys> enumeración es compatible con su propio convertidor de tipos. El convertidor de tipos para los modificadores usa un signo más (+) como un delimitador en lugar de una coma (,). Esta conversión es compatible con la sintaxis más tradicional para representar las combinaciones de teclas en la programación de Microsoft Windows, por ejemplo, "Ctrl + Alt".  
  
### <a name="properties-and-event-member-name-references"></a>Las propiedades y las referencias de nombre de miembro de evento  
 Al especificar un atributo, puede hacer referencia a cualquier propiedad o evento que existe como miembro del tipo CLR que crea una instancia para el elemento del objeto contenedor.  
  
 O bien, puede hacer referencia a una propiedad adjunta o evento asociado, independiente del elemento de objeto contenedor. (Las propiedades adjuntas se tratan en una sección posterior).  
  
 También puede asignar cualquier evento de cualquier objeto que sea accesible a través del espacio de nombres predeterminado mediante una *typeName*. *evento* nombre parcialmente completo; esta sintaxis permite adjuntar controladores para eventos enrutados donde el controlador está diseñado para controlar los eventos de enrutamiento de los elementos secundarios, pero el elemento primario no tiene ese evento en su tabla de miembros. Esta sintaxis se parece a una sintaxis del evento adjunto, pero aquí el evento no es un evento adjunto es true. En su lugar, se hace referencia a un evento con un nombre completo. Para obtener más información, consulte [Routed Events Overview](routed-events-overview.md).  
  
 En algunos escenarios, a veces se ofrecen los nombres de propiedad como valor de un atributo, en lugar de con el nombre del atributo. Este nombre de propiedad también puede incluir calificadores, como la propiedad especificada en el formulario *tipoDePropietario*. *dependencyPropertyName*. Este escenario es común cuando se escribe estilos o plantillas de XAML. Las reglas de procesamiento para los nombres de propiedad que se proporciona como un valor de atributo son diferentes y se rigen por el tipo de la propiedad que se va a establecer o por los comportamientos de subsistemas WPF determinados. Para obtener más información, consulte [aplicar estilos y plantillas](../controls/styling-and-templating.md).  
  
 Otro uso para los nombres de propiedad es cuando un valor de atributo describe una relación de propiedades. Esta característica se usa para el enlace de datos y para los destinos de guión gráfico y se habilita mediante la <xref:System.Windows.PropertyPath> clase y su convertidor de tipos. Para obtener una descripción más completa de la semántica de búsqueda, vea [PropertyPath XAML Syntax](propertypath-xaml-syntax.md).  
  
<a name="property_element_syntax"></a>   
## <a name="property-element-syntax"></a>Sintaxis de elementos de propiedad  
 *Sintaxis de elemento de propiedad* es una sintaxis que difiere ligeramente de las reglas de sintaxis XML básicas para los elementos. En XML, el valor de un atributo es una cadena de hecho, con la variación solo es posible que se está usando el formato de codificación de cadena. En XAML, puede asignar el valor de una propiedad de otros elementos de objeto. Esta funcionalidad se habilita mediante la sintaxis de elemento de propiedad. En lugar de la propiedad que se especifica como un atributo dentro de la etiqueta de elemento, la propiedad se especifica mediante un elemento de apertura de etiquetas en *elementTypeName*. *propertyName* formulario, el valor de la propiedad se especifica en y, a continuación, se cierra el elemento de propiedad.  
  
 En concreto, la sintaxis comienza con un corchete angular de apertura (\<), seguida inmediatamente por el nombre de tipo de la clase o estructura que está dentro de la sintaxis de elemento de propiedad. Esto es seguido inmediatamente por un solo punto (.), a continuación, por el nombre de una propiedad, a continuación, un corchete angular derecho (>). Al igual que con la sintaxis de atributo, esa propiedad debe existir dentro de los miembros públicos declarados del tipo especificado. El valor que se asignará a la propiedad está incluido dentro del elemento de propiedad. Normalmente, se asigna un valor como uno o varios elementos de objeto, porque la especificación de objetos como valores es el escenario de esa sintaxis de elemento de propiedad se pretende abarcar. Por último, una etiqueta de cierre equivalente especificando las mismas *elementTypeName*. *propertyName* debe proporcionarse combinación en anidada y equilibrada con otras etiquetas de elemento correctamente.  
  
 Por ejemplo, la siguiente es la sintaxis de elemento de propiedad para el <xref:System.Windows.FrameworkElement.ContextMenu%2A> propiedad de un <xref:System.Windows.Controls.Button>.  
  
 [!code-xaml[XAMLOvwSupport#ContextMenu](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#contextmenu)]  
  
 El valor dentro de un elemento de propiedad también se puede asignar como texto interno, en casos donde el tipo de propiedad que se ha especificado es un tipo de valor primitivo, como <xref:System.String>, o una enumeración que se especifica un nombre. Estos dos usos son un poco raro, ya que cada uno de estos casos también podría usar una sintaxis más sencilla de atributo. Es un escenario para rellenar un elemento de propiedad con una cadena para las propiedades que no son de la propiedad de contenido XAML, pero se utilizan para la representación de texto de la interfaz de usuario y determinados elementos de espacio en blanco como saltos de línea deben aparecer en ese texto de la interfaz de usuario. Sintaxis de atributo no puede conservar saltos de línea, pero pueden sintaxis de elemento de propiedad, siempre y cuando esté activa la conservación de espacio en blanco significativo (para obtener más información, consulte [espacio en blanco en XAML de procesamiento](../../xaml-services/whitespace-processing-in-xaml.md)). Otro escenario es poder [x: Uid (directiva)](../../xaml-services/x-uid-directive.md) se pueden aplicar al elemento property y marcar, por tanto, el valor dentro de como un valor que se debe traducir en WPF BAML de salida o por otras técnicas.  
  
 Un elemento de propiedad no se representa en el árbol lógico de WPF. Un elemento de propiedad es simplemente una sintaxis para establecer una propiedad determinada y no es un elemento que tiene una instancia o un objeto de seguridad. (Para obtener más información sobre el concepto de árbol lógico, vea [árboles en WPF](trees-in-wpf.md).)  
  
 Para las propiedades que se admiten la sintaxis de elementos de atributo y de propiedad, las dos sintaxis generalmente tienen el mismo resultado, aunque sutilezas como el tratamiento de espacio en blanco pueden variar ligeramente entre sintaxis.  
  
<a name="collection_syntax"></a>   
## <a name="collection-syntax"></a>Sintaxis de colecciones  
 La especificación XAML requiere que las implementaciones de procesadores XAML para identificar las propiedades donde el tipo de valor es una colección. La implementación del procesador XAML general en .NET se basa en código administrado y el CLR e identifica los tipos de colección a través de uno de los siguientes:  
  
-   Escriba implementa <xref:System.Collections.IList>.  
  
-   Escriba implementa <xref:System.Collections.IDictionary>.  
  
-   Tipo se deriva de <xref:System.Array> (para obtener más información acerca de las matrices en XAML, vea [x: Array Markup Extension](../../xaml-services/x-array-markup-extension.md).)  
  
 Si el tipo de una propiedad es una colección, el tipo de colección deducido no debe especificarse en el marcado como un elemento de objeto. En su lugar, los elementos que se van a convertirse en los elementos de la colección se especifican como uno o varios elementos secundarios del elemento de propiedad. Cada elemento de este tipo se evalúa a un objeto durante la carga y se agrega a la colección mediante una llamada a la `Add` método de la colección implícita. Por ejemplo, el <xref:System.Windows.Style.Triggers%2A> propiedad de <xref:System.Windows.Style> toma el tipo de colección especializadas <xref:System.Windows.TriggerCollection>, que implementa <xref:System.Collections.IList>. No es necesario crear una instancia de un <xref:System.Windows.TriggerCollection> elemento de objeto en el marcado. En su lugar, especifique uno o más <xref:System.Windows.Trigger> elementos como elementos dentro de la `Style.Triggers` elemento de propiedad, donde <xref:System.Windows.Trigger> (o una clase derivada) es el tipo esperado como el tipo de elemento para fuertemente tipada e implícita <xref:System.Windows.TriggerCollection>.  
  
 [!code-xaml[XAMLOvwSupport#SyntaxPECollection](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#syntaxpecollection)]  
  
 Una propiedad puede ser un tipo de colección y la propiedad de contenido XAML para ese tipo y tipos derivados, que se describe en la siguiente sección de este tema.  
  
 Un elemento de colección implícito crea a un miembro en la representación de árbol lógico, incluso si no aparece en el marcado como un elemento. Normalmente, el constructor del tipo primario realiza la creación de instancias de la colección que es uno de sus propiedades y la colección inicialmente vacía se convierte en parte del árbol de objetos.  
  
> [!NOTE]
>  Las interfaces de lista y diccionario genéricas (<xref:System.Collections.Generic.IList%601> y <xref:System.Collections.Generic.IDictionary%602>) no se admiten para la detección de la colección. Sin embargo, puede usar el <xref:System.Collections.Generic.List%601> clase como clase base, porque implementa <xref:System.Collections.IList> directamente, o <xref:System.Collections.Generic.Dictionary%602> como una clase base, porque implementa <xref:System.Collections.IDictionary> directamente.  
  
 En las páginas de referencia de .NET para los tipos de colección, esta sintaxis con la omisión deliberada del elemento de objeto para una colección en ocasiones, se indica en las secciones de sintaxis XAML como la sintaxis de colección implícito.  
  
 Salvo el elemento raíz, cada elemento de objeto en un archivo XAML que se anida como un elemento secundario de otro elemento es realmente un elemento que es uno o ambos de los siguientes casos: un miembro de una propiedad de colección implícito de su elemento primario , o un elemento que especifica el valor de la propiedad de contenido XAML para el elemento primario (el XAML contenido de las propiedades se tratarán en una sección posterior). En otras palabras, la relación de elementos primarios y secundarios en una página de marcado es realmente un objeto único en la raíz, y cada elemento de objeto debajo de la raíz es una instancia única que proporciona un valor de propiedad del elemento primario o uno de los elementos dentro de una columna selección que también es un valor de propiedad de tipo de colección del elemento primario. Este concepto de raíz única es común en XML y se refuerza con frecuencia en el comportamiento de las API que cargan XAML como <xref:System.Windows.Markup.XamlReader.Load%2A>.  
  
 El ejemplo siguiente es una sintaxis con el elemento de objeto para una colección (<xref:System.Windows.Media.GradientStopCollection>) especificado explícitamente.  
  
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
  
 Tenga en cuenta que no siempre es posible declarar explícitamente la colección. Por ejemplo, intenta declarar <xref:System.Windows.TriggerCollection> explícitamente en el que se muestra anteriormente <xref:System.Windows.Style.Triggers%2A> ejemplo produciría un error. La declaración explícita de la colección requiere que la clase de colección debe admitir un constructor predeterminado, y <xref:System.Windows.TriggerCollection> no tiene un constructor predeterminado.  
  
<a name="xaml_content_properties"></a>   
## <a name="xaml-content-properties"></a>Propiedades del contenido XAML  
 Sintaxis de contenido XAML es una sintaxis que sólo está habilitada en las clases que especifican el <xref:System.Windows.Markup.ContentPropertyAttribute> como parte de su declaración de clase. El <xref:System.Windows.Markup.ContentPropertyAttribute> hace referencia al nombre de propiedad que es la propiedad de contenido de ese tipo de elemento (incluidas las clases derivadas). Cuando procesa un procesador XAML, los elementos secundarios o texto interno que se encuentran entre las etiquetas de cierre del elemento de objeto y apertura se asignará el valor de la propiedad de contenido XAML para ese objeto. Se puede especificar los elementos de propiedad explícita de la propiedad de contenido, pero este uso no se muestra con carácter general en las secciones de sintaxis XAML en la referencia. NET. La técnica explícita detallado tiene valor ocasional para lograr claridad en el marcado o como una cuestión de estilo de marcado, pero normalmente es el propósito de una propiedad de contenido simplificar el marcado para que los elementos que están relacionados de forma intuitiva como elementos primarios y secundarios pueden anidarse directamente. Las etiquetas de elemento de propiedad para otras propiedades en un elemento no se asignan como "contenido" por una definición estricta de lenguaje XAML; que se procesan previamente en el orden de procesamiento del analizador XAML y no se consideran "contenido".  
  
### <a name="xaml-content-property-values-must-be-contiguous"></a>Los valores de propiedad de contenido XAML deben ser contiguos  
 El valor de una propiedad de contenido XAML se debe proporcionar exclusivamente antes o después de cualquier otro elemento de propiedad en ese elemento de objeto. Esto es cierto si se especifica el valor de una propiedad de contenido XAML como una cadena o como uno o varios objetos. Por ejemplo, no se analiza el marcado siguiente:  
  
```  
<Button>I am a   
  <Button.Background>Blue</Button.Background>  
  blue button</Button>  
```  
  
 Esto no es válido básicamente porque si esta sintaxis se realizaron explícita utilizando la sintaxis de elemento de propiedad para la propiedad de contenido, a continuación, la propiedad de contenido se establecería dos veces:  
  
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
 Con el fin de aceptar más de un elemento de objeto único como contenido, el tipo de la propiedad de contenido concreto debe ser un tipo de colección. Al igual que la sintaxis de elemento de propiedad para tipos de colección, un procesador XAML debe identificar tipos que son tipos de colección. Si un elemento tiene una propiedad de contenido XAML y el tipo de la propiedad de contenido XAML es una colección, el tipo de colección implícito no necesita especificarse en el marcado como un elemento de objeto y la propiedad de contenido XAML no debe especificarse como el de una propiedad ependen. Por lo tanto, el modelo de contenido aparente en el marcado ahora puede tener más de un elemento secundario asignado como el contenido. El siguiente es la sintaxis de contenido para un <xref:System.Windows.Controls.Panel> clase derivada. Todos los <xref:System.Windows.Controls.Panel> las clases derivadas establecer la propiedad de contenido XAML para que sea <xref:System.Windows.Controls.Panel.Children%2A>, que requiere un valor de tipo <xref:System.Windows.Controls.UIElementCollection>.  
  
 [!code-xaml[XAMLOvwSupport#SyntaxContent](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page5.xaml#syntaxcontent)]  
  
 Tenga en cuenta que ni el elemento de propiedad para <xref:System.Windows.Controls.Panel.Children%2A> ni el elemento para el <xref:System.Windows.Controls.UIElementCollection> es necesaria en el marcado. Esta es una característica de diseño de XAML para que los contenidos de forma recursiva los elementos que definen un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] son la manera más intuitiva representado como un árbol de elementos anidados con relaciones de elementos de elementos primarios y secundarios inmediata, sin que intervengan etiquetas de elemento de propiedad o recopilación de objetos. De hecho, <xref:System.Windows.Controls.UIElementCollection> no puede especificarse explícitamente en el marcado como un elemento de objeto, por diseño. Dado que es su uso previsto solo como una colección implícita, <xref:System.Windows.Controls.UIElementCollection> no expone un constructor público predeterminado y, por tanto, no pueden crearse instancias como un elemento de objeto.  
  
### <a name="mixing-property-elements-and-object-elements-in-an-object-with-a-content-property"></a>Combinación de elementos de propiedad y los elementos de objeto en un objeto con una propiedad de contenido  
 La especificación XAML declara que un procesador XAML puede exigir que los elementos de objeto que se usan para rellenar la propiedad de contenido XAML dentro de un elemento de objeto deben ser contiguos y no deben ser mixto. Se aplica esta restricción contra la mezcla de elementos de propiedad y el contenido por el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] procesadores XAML.  
  
 Puede tener un elemento de objeto secundario como el primer marcado inmediato dentro de un elemento de objeto. A continuación, puede introducir los elementos de propiedad. O bien, puede especificar uno o más elementos de propiedad, contenido y, luego, más los elementos de propiedad. Pero una vez que un elemento de propiedad sigue al contenido, no puede introducir cualquier otro tipo de contenido, solo se pueden agregar elementos de propiedad.  
  
 Este contenido o el requisito de orden de elemento de propiedad no se aplica al texto interno utilizado como contenido. Sin embargo, aún resulta un buen estilo de marcado para mantener el texto interno contiguo, porque el espacio en blanco significativo será difícil de detectar visualmente en el marcado si los elementos de propiedad están intercalados con texto interno.  
  
<a name="xaml_namespaces"></a>   
## <a name="xaml-namespaces"></a>Espacios de nombres XAML  
 Ninguno de los ejemplos de sintaxis anterior especifica un espacio de nombres XAML que no sean de espacio de nombres XAML predeterminado. En los típicos [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplicaciones, el espacio de nombres XAML predeterminado se especifica como el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] espacio de nombres. Puede especificar espacios de nombres XAML que no sean de espacio de nombres XAML predeterminado y seguir usando una sintaxis similar. Pero, a continuación, en cualquier lugar donde se denomina una clase que no es accesible dentro del espacio de nombres XAML predeterminado, ese nombre de clase debe ir precedido por el prefijo del espacio de nombres XAML como asignado al espacio de nombres CLR correspondiente. Por ejemplo, `<custom:Example/>` es una sintaxis de elemento de objeto para crear una instancia de la `Example` (clase), donde el espacio de nombres CLR que contiene esa clase (y, posiblemente, la información de ensamblado externo que contiene los tipos de respaldo) estaba asignada previamente a la `custom` prefijo.  
  
 Para obtener más información acerca de los espacios de nombres XAML, vea [los espacios de nombres XAML y Namespace Mapping for WPF XAML](xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).  
  
<a name="markup_extensions"></a>   
## <a name="markup-extensions"></a>Extensiones de marcado  
 XAML define una entidad que permite un carácter de escape de la administración normal de procesador XAML de los valores de atributo de cadena o elementos de objeto y retrasa el procesamiento a una clase de respaldo de programación de la extensión de marcado. El carácter que identifica una extensión de marcado para un procesador XAML cuando se usa la sintaxis de atributo es la llave de apertura ({}), seguida de cualquier carácter que no sea una llave de cierre (}). La primera cadena de la llave de apertura debe hacer referencia a la clase que proporciona el comportamiento de extensión determinado, donde la referencia puede omitir la subcadena "Extension" si esa subcadena es parte del nombre de clase es true. Posteriormente, puede aparecer un espacio y, a continuación, cada carácter subsiguiente se usa como entrada mediante la implementación de extensión, hasta que se encuentra la llave de cierre.  
  
 La implementación XAML de .NET usa la <xref:System.Windows.Markup.MarkupExtension> clase abstracta como base para todas las extensiones de marcado compatibles con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , así como otros marcos o tecnologías. Las extensiones de marcado que [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] implementa específicamente a menudo está diseñado para proporcionar un medio para hacer referencia a otros objetos ya existentes, o para realizar aplazadas referencias a objetos que se va a evaluar en tiempo de ejecución. Por ejemplo, un enlace de datos simple de WPF se consigue especificando la `{Binding}` extensión de marcado en lugar del valor que tomaría normalmente una propiedad determinada. Muchas de las extensiones de marcado WPF permiten una sintaxis de atributo para las propiedades donde una sintaxis de atributo no sería posible. Por ejemplo, un <xref:System.Windows.Style> objeto es un tipo relativamente complejo que contiene una serie de objetos y propiedades anidada. Los estilos en WPF se definen normalmente como un recurso en un <xref:System.Windows.ResourceDictionary>y, a continuación, hace referencia a través de una de las dos extensiones de marcado WPF que solicitan un recurso. La extensión de marcado se aplaza la evaluación del valor de propiedad para una búsqueda de recursos y permite que proporciona el valor de la <xref:System.Windows.FrameworkElement.Style%2A> propiedad, toma tipo <xref:System.Windows.Style>, en sintaxis como en el siguiente ejemplo de atributo:  
  
 `<Button Style="{StaticResource MyStyle}">My button</Button>`  
  
 En este caso, `StaticResource` identifica el <xref:System.Windows.StaticResourceExtension> clase que proporciona la implementación de la extensión de marcado. La siguiente cadena `MyStyle` se usa como entrada para el valor no predeterminado <xref:System.Windows.StaticResourceExtension> constructor, donde el parámetro que se toman de la cadena de extensión declara solicitado <xref:System.Windows.ResourceKey>. `MyStyle` se espera que sea el [x: Key](../../xaml-services/x-key-directive.md) valor de un <xref:System.Windows.Style> define como un recurso. El [StaticResource Markup Extension](staticresource-markup-extension.md) uso solicita que el recurso se utiliza para proporcionar la <xref:System.Windows.Style> valor de propiedad a través de la lógica de búsqueda de recursos estáticos en tiempo de carga.  
  
 Para más información sobre las extensiones de marcado, consulte [Extensiones de marcado y XAML de WPF](markup-extensions-and-wpf-xaml.md). Para obtener una referencia de extensiones de marcado y otra características habilitadas en la implementación XAML de .NET general de programación de XAML, vea [XAML Namespace (x:) Características del lenguaje](../../xaml-services/xaml-namespace-x-language-features.md). Para las extensiones de marcado específicas de WPF, vea [extensiones XAML de WPF](wpf-xaml-extensions.md).  
  
<a name="attached_properties"></a>   
## <a name="attached-properties"></a>Propiedades asociadas  
 Las propiedades adjuntas son un concepto de programación introducido en XAML mediante el cual se pueden que pertenecen las propiedades y definidas por un tipo determinado, pero establezca como atributos o elementos de propiedad en cualquier elemento. El escenario principal que están destinadas a las propiedades adjuntas es permitir que los elementos secundarios en una estructura de marcado para notificar la información a un elemento primario sin necesidad de un modelo de objetos compartido entre todos los elementos. Por el contrario, las propiedades adjuntas pueden usarse por los elementos primarios para notificar la información a los elementos secundarios. Para obtener más información sobre el propósito de las propiedades adjuntas y cómo crear sus propias propiedades adjuntas, consulte [Attached Properties Overview](attached-properties-overview.md).  
  
 Las propiedades adjuntas utilizan una sintaxis que se parezca ligeramente a la sintaxis de elemento de propiedad, en que especifique también una *typeName*. *propertyName* combinación. Hay dos diferencias importantes:  
  
-   Puede usar el *typeName*. *propertyName* incluso al establecer una propiedad adjunta mediante la sintaxis de atributo de combinación. Las propiedades adjuntas son que el único caso donde calificar el nombre de propiedad es un requisito en una sintaxis de atributo.  
  
-   También puede usar la sintaxis de elemento de propiedad para las propiedades adjuntas. Sin embargo, para la sintaxis de elemento de propiedad típica, el *typeName* especificar es el elemento de objeto que contiene el elemento de propiedad. Si se hace referencia a una propiedad adjunta, el *typeName* es la clase que define la propiedad adjunta, no el elemento contenedor del objeto.  
  
<a name="attached_events"></a>   
## <a name="attached-events"></a>Eventos asociados  
 Los eventos adjuntos son otro concepto de programación introducida en XAML donde se pueden definir eventos con un tipo específico, pero los controladores se pueden adjuntar a cualquier elemento de objeto. En la implementación de WOF, a menudo, el tipo que define un evento adjunto es un tipo estático que define un servicio y, a veces un alias de evento enrutado en tipos que exponen el servicio expone los eventos adjuntos. Controladores para eventos adjuntos se especifican mediante la sintaxis de atributo. Como con los eventos adjuntos, la sintaxis de atributo se expande para que los eventos adjuntos permitir que un *typeName*. *eventName* uso, donde *typeName* es la clase que proporciona `Add` y `Remove` descriptores de acceso de controlador de eventos para la infraestructura de evento adjunto, y *eventName* es el nombre del evento.  
  
<a name="anatomy_of_a_xaml_page_root_element"></a>   
## <a name="anatomy-of-a-xaml-root-element"></a>Anatomía de un elemento raíz XAML  
 En la tabla siguiente se muestra un típica XAML elemento raíz desglosado, que muestra los atributos específicos de un elemento raíz:  
  
|||  
|-|-|  
|`<Page`|Abrir elemento de objeto del elemento raíz|  
|`xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"`|El valor predeterminado ([!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]) espacio de nombres XAML|  
|`xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`|El espacio de nombres XAML de lenguaje XAML|  
|`x:Class="ExampleNamespace.ExampleCode"`|La declaración de clase parcial que conecta el marcado con cualquier código subyacente definido para la clase parcial|  
|`>`|Final del elemento de objeto para la raíz. Objeto todavía no se cierra porque el elemento contiene elementos secundarios|  
  
<a name="optional_and_nonrecommended_xaml_usages"></a>   
## <a name="optional-and-nonrecommended-xaml-usages"></a>Usos de XAML no recomendados y opcionales  
 Las secciones siguientes describen los usos de XAML que son técnicamente compatibles con procesadores XAML, pero que producen nivel de detalle u otros problemas estéticos que interfieren con archivos XAML restantes legible al desarrollar aplicaciones que contienen los orígenes de XAML.  
  
### <a name="optional-property-element-usages"></a>Usos de elemento de propiedad opcional  
 Usos de elemento de propiedad opcional incluir acciones como escribir explícitamente las propiedades de contenido del elemento que el procesador XAML considera implícito. Por ejemplo, cuando se declara el contenido de un <xref:System.Windows.Controls.Menu>, podría optar por declarar explícitamente el <xref:System.Windows.Controls.ItemsControl.Items%2A> colección de la <xref:System.Windows.Controls.Menu> como un `<Menu.Items>` etiqueta de elemento de propiedad y coloque cada <xref:System.Windows.Controls.MenuItem> dentro de `<Menu.Items>`, en lugar que el uso del comportamiento del procesador XAML implícito que todos los elementos secundarios de un <xref:System.Windows.Controls.Menu> debe ser un <xref:System.Windows.Controls.MenuItem> y se colocan en el <xref:System.Windows.Controls.ItemsControl.Items%2A> colección. A veces los usos opcionales pueden ayudar a clarificar visualmente la estructura de objetos, como se representa en el marcado. O bien, en ocasiones, el uso de un elemento de propiedad explícita puede evitar el marcado que es técnicamente funcional pero visualmente confuso, como las extensiones de marcado anidados dentro de un valor de atributo.  
  
### <a name="full-typenamemembername-qualified-attributes"></a>Atributos nombreDeTipo.nombreDeMiembro completos  
 El *typeName*. *memberName* formulario para un atributo realmente funciona más universalmente que solo el caso del evento enrutado. Pero en otras situaciones ese formulario es superfluo y debe evitar, si solo por motivos de estilo de marcado y mejorar la legibilidad. En el ejemplo siguiente, cada una de las tres referencias a la <xref:System.Windows.Controls.Control.Background%2A> atributo son completamente equivalentes:  
  
 [!code-xaml[XAMLOvwSupport#TypeNameProp](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#typenameprop)]  
  
 `Button.Background` funciona porque la búsqueda calificada de esa propiedad en <xref:System.Windows.Controls.Button> es correcta (<xref:System.Windows.Controls.Control.Background%2A> se heredó de Control) y <xref:System.Windows.Controls.Button> es la clase del elemento de objeto o una clase base. `Control.Background` funciona porque el <xref:System.Windows.Controls.Control> clase realmente define <xref:System.Windows.Controls.Control.Background%2A> y <xref:System.Windows.Controls.Control> es un <xref:System.Windows.Controls.Button> clase base.  
  
 Sin embargo, la siguiente *typeName*. *memberName* ejemplo de formulario no funciona y, por tanto, se muestra marcado como:  
  
 [!code-xaml[XAMLOvwSupport#TypeNameBadProp](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#typenamebadprop)]  
  
 <xref:System.Windows.Controls.Label> es otra clase derivada de <xref:System.Windows.Controls.Control>, y si hubiera especificado `Label.Background` dentro de un <xref:System.Windows.Controls.Label> elemento de objeto, este uso habría funcionado. Sin embargo, dado que <xref:System.Windows.Controls.Label> no es la clase o clase base de <xref:System.Windows.Controls.Button>, el comportamiento del procesador XAML especificado es, a continuación, procesar `Label.Background` como una propiedad adjunta. `Label.Background` no es una propiedad adjunta disponible y se produce un error en este uso.  
  
### <a name="basetypenamemembername-property-elements"></a>Propiedad nombreDeTipoBase.nombreDeMiembro  
 De forma similar a cómo la *typeName*. *memberName* formulario funciona para la sintaxis de atributo, un *nombreDeTipoBase*. *memberName* sintaxis funciona para la sintaxis de elemento de propiedad. Por ejemplo, la sintaxis siguiente funciona:  
  
 [!code-xaml[XAMLOvwSupport#GoofyPE](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#goofype)]  
  
 En este caso, se proporcionó el elemento de propiedad como `Control.Background` , aunque el elemento de propiedad se encuentra en `Button`.  
  
 Pero al igual que *typeName*. *memberName* formato de los atributos, *nombreDeTipoBase*. *memberName* un estilo pobre en el marcado, y se debe evitar.  
  
## <a name="see-also"></a>Vea también

- [Información general sobre XAML (WPF)](xaml-overview-wpf.md)
- [Espacio de nombres de XAML (x:) Características del lenguaje](../../xaml-services/xaml-namespace-x-language-features.md)
- [Extensiones XAML de WPF](wpf-xaml-extensions.md)
- [Información general sobre las propiedades de dependencia](dependency-properties-overview.md)
- [Clases TypeConverter y XAML](typeconverters-and-xaml.md)
- [Clases XAML y personalizadas para WPF](xaml-and-custom-classes-for-wpf.md)
