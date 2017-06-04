---
title: "Detalles de la sintaxis XAML | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "XML, espacios de nombres"
  - "XAML, análisis de atributos"
  - "análisis de atributos"
  - "Las extensiones de marcado XAML"
  - "propiedades asociadas"
  - "sintaxis de etiquetas [XAML]"
  - "extensiones de marcado"
  - "Sintaxis de elementos de objeto XAML"
  - "Terminología de la sintaxis XAML"
  - "eventos asociados"
  - "semántica de búsqueda"
  - "XAML, los eventos adjuntos"
  - "Sintaxis de contenido XAML"
  - "XAML, semántica de búsqueda"
  - "sintaxis de contenido"
  - "sintaxis de elementos de objeto"
  - "terminología de la sintaxis [XAML]"
  - "Propiedades adjuntas de XAML,"
  - "análisis de atributos [XAML]"
  - "XAML, la sintaxis de etiqueta"
  - "Sintaxis de atributos XAML"
  - "sintaxis de elementos de propiedad"
  - "terminología [XAML]"
  - "espacios de nombres XML"
  - "sintaxis de atributo [XAML]"
  - "Sintaxis de elemento de propiedad XAML"
ms.assetid: 67cce290-ca26-4c41-a797-b68aabc45479
caps.latest.revision: 26
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 26
---
# Detalles de la sintaxis XAML
Este tema define los términos que se utilizan para describir los elementos de sintaxis de XAML. Estos términos se utilizan con frecuencia en el resto de esta documentación, tanto para la documentación de WPF específicamente y de otros marcos que utilizan XAML o los conceptos básicos de XAML habilitados la compatibilidad del lenguaje XAML en el nivel de System.Xaml. Este tema amplía la terminología básica presentada en el tema [información general sobre XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md).  
  

  
<a name="the_xaml_language_specification"></a>   
## <a name="the-xaml-language-specification"></a>La especificación del lenguaje XAML  
 La terminología de sintaxis XAML definida aquí también se define o se hace referencia en la especificación del lenguaje XAML. XAML es un lenguaje basado en XML y sigue o expande las reglas estructurales de XML. Algunos de los términos se comparte o se basa en la terminología utilizada normalmente al describir el lenguaje XML o el modelo de objetos de documento XML.  
  
 Para obtener más información acerca de la especificación del lenguaje XAML, descargue [ \[MS XAML\] ](http://go.microsoft.com/fwlink/?LinkId=114525) desde Microsoft Download Center.  
  
<a name="xaml_and_clr"></a>   
## <a name="xaml-and-clr"></a>XAML y CLR  
 XAML es un lenguaje de marcado. El [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)], como implica su nombre, habilita el tiempo de ejecución. XAML no es por sí solo uno de los lenguajes comunes que utiliza directamente el tiempo de ejecución de CLR. En su lugar, se puede considerar XAML como compatible con su propio sistema de tipos. El sistema de análisis de XAML determinado que usa WPF se basa en el CLR y el sistema de tipos CLR. Los tipos XAML se asignan a tipos CLR para crear instancias de una representación en tiempo de ejecución cuando se analiza el XAML para WPF. Por este motivo, el resto de la explicación de la sintaxis de este documento incluirá referencias al sistema de tipos CLR, aunque no las explicaciones de sintaxis equivalentes en la especificación del lenguaje XAML. (Según el nivel de especificación del lenguaje XAML, los tipos XAML podrían asignarse a cualquier otro sistema de tipo, que no tiene que ser el CLR, pero eso requeriría la creación y uso de un analizador XAML diferente.)  
  
#### <a name="members-of-types-and-class-inheritance"></a>Miembros de tipos y herencia de clases  
 Propiedades y eventos que aparecen como miembros XAML de un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tipo a menudo se heredan de los tipos base. Por ejemplo, considere este ejemplo: `<Button Background="Blue" .../>`. El <xref:System.Windows.Controls.Control.Background%2A> propiedad no es una propiedad declarada inmediatamente en el <xref:System.Windows.Controls.Button> clase, si tuviera que ver la definición de clase, los resultados de la reflexión o la documentación. En su lugar, <xref:System.Windows.Controls.Control.Background%2A> se hereda de la base de <xref:System.Windows.Controls.Control> clase.  
  
 El comportamiento de la herencia de clases de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elementos XAML es un cambio significativo respecto a una interpretación exigida por esquema del marcado XML. Herencia de clases puede ser compleja, especialmente cuando las clases base intermedias son abstractas o cuando implican interfaces. Ésta es una razón el conjunto de elementos XAML y sus atributos permitidos resulta complicado de representar con precisión y completamente utilizando los tipos de esquema que se utiliza normalmente para [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] de programación, como formato XSD o DTD. Otro motivo es que extensibilidad y asignación de tipos de características de lenguaje XAML obstáculo para la integridad de cualquier representación fija de los posibles tipos y miembros.  
  
<a name="object_element_syntax"></a>   
## <a name="object-element-syntax"></a>Sintaxis de elementos de objeto  
 *Sintaxis de elementos de objeto* es la sintaxis del marcado XAML que crea una instancia de una clase o estructura CLR declarando un elemento XML. Esta sintaxis se parece a la sintaxis de elementos de otros lenguajes de marcado como HTML. Sintaxis de elementos de objeto comienza con un corchete angular de apertura)\<), followed immediately by the type name of the class or structure being instantiated. followed="" immediately="" by="" the="" type="" name="" of="" the="" class="" or="" structure="" being="">\</), followed immediately by the type name of the class or structure being instantiated.> Cero o más espacios después del nombre de tipo y también se pueden declarar cero o más atributos en el elemento de objeto con uno o más espacios separando cada nombre de atributo = par "value". Por último, uno de los siguientes debe ser true:  
  
-   El elemento y la etiqueta deben cerrarse mediante una barra diagonal (/), seguida inmediatamente por un corchete angular derecho (>).  
  
-   La etiqueta de apertura debe realizarla un corchete angular derecho (>). Otros elementos de objeto, los elementos de propiedad o texto interno, puede seguir la etiqueta de apertura. Exactamente qué contenido puede incluirse aquí está restringido por el modelo de objetos del elemento. El equivalente en la etiqueta de cierre para el elemento de objeto también debe existir en un anidamiento correcto y equilibrar con otros pares de etiqueta de apertura y cierre.  
  
 XAML que se implementa .NET tiene un conjunto de reglas que se asignan elementos de objeto en tipos de atributos en las propiedades o eventos y espacios de nombres XAML a espacios de nombres CLR y ensamblado. Para WPF y .NET Framework, los elementos de objeto XAML se asignan a [!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)] tipos definidos en ensamblados de referencia y los atributos se asignan a los miembros de esos tipos. Al hacer referencia a un tipo CLR en XAML, tendrá acceso a los miembros heredados de ese tipo.  
  
 Por ejemplo, el ejemplo siguiente es la sintaxis de elementos de objeto que se crea una nueva instancia de la <xref:System.Windows.Controls.Button> de clase y también especifica un <xref:System.Windows.FrameworkElement.Name%2A> atributo y un valor para ese atributo:  
  
 [!code-xml[XAMLOvwSupport#SyntaxOE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#syntaxoe)]  
  
 El ejemplo siguiente es la sintaxis de elementos de objeto que también incluyen la sintaxis de propiedad de contenido XAML. El texto interno incluido dentro se utilizará para establecer el <xref:System.Windows.Controls.TextBox> propiedad de contenido XAML, <xref:System.Windows.Controls.TextBox.Text%2A>.  
  
 [!code-xml[XAMLOvwSupport#ThisIsATextBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#thisisatextbox)]  
  
### <a name="content-models"></a>Modelos de contenido  
 Una clase podría admitir su uso como un elemento de objeto XAML en términos de la sintaxis, pero dicho elemento sólo funcionará correctamente en una aplicación o página cuando se coloca en una posición esperada de un árbol de modelo o elemento de contenido general. Por ejemplo, un <xref:System.Windows.Controls.MenuItem> normalmente sólo deben colocarse como elemento secundario de un <xref:System.Windows.Controls.Primitives.MenuBase> clase derivada como <xref:System.Windows.Controls.Menu>. Contenido de modelos para elementos específicos se documentan como parte de la sección de comentarios en las páginas de la clase de controles y otros [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] las clases que se pueden usar como elementos XAML.  
  
<a name="properties_of_object_elements"></a>   
## <a name="properties-of-object-elements"></a>Propiedades de los elementos de objeto  
 Propiedades en XAML se establecen mediante diversas sintaxis posibles. Qué sintaxis se puede usar para una propiedad determinada variarán según las características del sistema de tipo subyacente de la propiedad que está configurando.  
  
 Estableciendo valores de propiedades, se agregan características a los objetos que existen en el gráfico de objetos de tiempo de ejecución. El estado inicial del objeto creado desde un elemento de objeto se basa en el comportamiento del constructor predeterminado. Normalmente, la aplicación utilizará algo distinto de una instancia completamente predeterminada de cualquier objeto determinado.  
  
<a name="attribute_syntax_properties"></a>   
## <a name="attribute-syntax-properties"></a>Sintaxis de atributo (propiedades)  
 La sintaxis de atributo es la sintaxis del marcado XAML que establece un valor para una propiedad declarando un atributo en un elemento de objeto existente. El nombre del atributo debe coincidir con el nombre de miembro CLR de la propiedad de la clase que respalda el elemento de objeto pertinente. El nombre del atributo seguido de un operador de asignación (=). El valor del atributo debe ser una cadena entre comillas.  
  
> [!NOTE]
>  Puede utilizar comillas alternas para poner una comilla literal dentro de un atributo. Por ejemplo puede utilizar comillas simples como medio para declarar una cadena que contiene un carácter de comillas dobles dentro de él. Si utiliza comillas simples o dobles, debe usar una pareja coincidente para abrir y cerrar la cadena de valor de atributo. También hay secuencias de escape y otras técnicas disponibles para solucionar las restricciones de caracteres impuesta por una sintaxis XAML determinada. Consulte [entidades de caracteres XML y XAML](../../../../docs/framework/xaml-services/xml-character-entities-and-xaml.md).  
  
 Para establecer a través de la sintaxis de atributo, una propiedad debe ser pública y debe ser grabable. El valor de la propiedad en el sistema de tipos de respaldo debe ser un tipo de valor o debe ser un tipo de referencia que se puede crear instancias o al que hace referencia un procesador XAML al obtener acceso a los correspondientes tipo de respaldo.  
  
 Para los eventos XAML de WPF, el evento que se hace referencia como el nombre de atributo debe ser públicos y tener un delegado público.  
  
 La propiedad o evento debe ser un miembro de la clase o estructura que se crea una instancia del elemento de objeto que contiene.  
  
### <a name="processing-of-attribute-values"></a>Procesamiento de valores de atributo  
 El valor de cadena dentro de la apertura y comillas de cierre es procesado por un procesador XAML. Para las propiedades, el comportamiento de procesamiento predeterminado se determina por el tipo de propiedad CLR subyacente.  
  
 El valor de atributo se rellena mediante uno de los siguientes, utilizando este orden de procesamiento:  
  
1.  Si el procesador XAML encuentra una llave o un elemento de objeto que se deriva de <xref:System.Windows.Markup.MarkupExtension>, a continuación, se evalúa primero la extensión de marcado que se hace referencia en lugar de procesar el valor como una cadena y se utiliza el objeto devuelto por la extensión de marcado como el valor. En muchos casos, el objeto devuelto por una extensión de marcado será una referencia a un objeto existente o una expresión que difiere la evaluación hasta el tiempo de ejecución y no es un objeto de la instancia recién creado.  
  
2.  Si la propiedad se declara con un atributo <xref:System.ComponentModel.TypeConverter>, o el tipo de valor de esa propiedad se declara con un atributo <xref:System.ComponentModel.TypeConverter>, se envía el valor de cadena del atributo para el convertidor de tipos como una entrada de conversión y el convertidor devolverá una nueva instancia de objeto.  
  
3.  Si no hay ningún <xref:System.ComponentModel.TypeConverter>, se intenta una conversión directa para el tipo de propiedad. Este nivel final es una conversión directa en el valor analizador nativo entre los tipos primitivos del lenguaje XAML o una comprobación de los nombres de constantes con nombre en una enumeración (el analizador tiene acceso a los valores correspondientes).  
  
#### <a name="enumeration-attribute-values"></a>Valores de atributo (enumeración)  
 Las enumeraciones en XAML se procesan intrínsecamente analizadores de XAML, y los miembros de una enumeración deben especificarse especificando el nombre de cadena de una de las constantes con nombre de la enumeración.  
  
 Para los valores de enumeración sin marcadores, el comportamiento nativo es procesar la cadena de un valor de atributo y resolverlo en uno de los valores de enumeración. No se especifica la enumeración en el formato *enumeración*.*Valor*, al igual que en el código. En su lugar, especifique sólo *valor*, y *enumeración* se deduce el tipo de la propiedad que se va a configurar. Si especifica un atributo en el *enumeración*.*Valor* formulario, no se resolverá correctamente.  
  
 Para las enumeraciones basada en marcadores, el comportamiento se basa en el <xref:System.Enum.Parse%2A?displayProperty=fullName> método. Puede especificar varios valores para una enumeración basada en marcadores separando cada valor con una coma. Sin embargo, no puede combinar los valores de enumeración que no estén basados en marcadores. Por ejemplo, no puede utilizar la sintaxis de comas para intentar crear un <xref:System.Windows.Trigger> que actúa en varias condiciones de una enumeración sin marcadores:  
  
```  
<!--This will not compile, because Visibility is not a flagwise enumeration.-->  
...  
<Trigger Property="Visibility" Value="Collapsed,Hidden">  
  <Setter ... />  
</Trigger>  
...  
```  
  
 Enumeraciones basada en marcadores que admiten atributos que pueden establecerse en XAML son raras en WPF. Sin embargo, es una de estas enumeraciones <xref:System.Windows.Media.StyleSimulations>. Por ejemplo, puede utilizar la sintaxis de atributo basada en marcadores delimitada por comas para modificar el ejemplo proporcionado en la sección Comentarios para la <xref:System.Windows.Documents.Glyphs> clase; `StyleSimulations = "BoldSimulation"` podría ser `StyleSimulations = "BoldSimulation,ItalicSimulation"`. <xref:System.Windows.Input.KeyBinding.Modifiers%2A?displayProperty=fullName> es otra propiedad donde se puede especificar más de un valor de enumeración. Sin embargo, esta propiedad es un caso especial, porque la <xref:System.Windows.Input.ModifierKeys> enumeración es compatible con su propio convertidor de tipos. El convertidor de tipos para los modificadores usa un signo más (+) como delimitador, en lugar de una coma (,). Esta conversión admite la sintaxis más tradicional para representar las combinaciones de teclas en la programación de Microsoft Windows, como "CTRL+ALT".  
  
### <a name="properties-and-event-member-name-references"></a>Propiedades y referencias de nombre de miembro de evento  
 Al especificar un atributo, puede hacer referencia a cualquier propiedad o evento que exista como miembro del tipo CLR que se crean instancias para el elemento de objeto contenedor.  
  
 O bien, puede hacer referencia a una propiedad adjunta o evento asociado, independiente del elemento de objeto contenedor. (Las propiedades adjuntas se analizan en una sección posterior).  
  
 También puede asignar cualquier evento desde cualquier objeto que es accesible a través del espacio de nombres predeterminado mediante una *typeName*.*evento* nombre parcialmente completo; esta sintaxis permite asociar controladores para eventos enrutados donde el controlador está diseñado para controlar los eventos de enrutamiento desde elementos secundarios, pero el elemento primario no tiene ese evento en su tabla de miembros. Esta sintaxis se parece a la sintaxis de eventos asociados, pero aquí el evento no es un verdadero evento asociado. En su lugar, se hace referencia a un evento con un nombre completo. Para obtener más información, consulte [Routed Events Overview](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
 En algunos escenarios, los nombres de propiedad se proporcionan a veces como el valor de un atributo, en lugar de con el nombre del atributo. Nombre de la propiedad también puede incluir calificadores, como la propiedad especificada en el formulario *ownerType*.*dependencyPropertyName*. Este escenario es habitual al escribir estilos o plantillas en XAML. Las reglas de procesamiento para los nombres de propiedad proporcionados como un valor de atributo son diferentes y se rigen por el tipo de la propiedad que se va a establecer o por los comportamientos de subsistemas WPF determinados. Para obtener más información, consulte [estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md).  
  
 Otro uso de nombres de propiedad es cuando un valor de atributo describe una relación de propiedades. Esta característica se utiliza para el enlace de datos y para los destinos de guión gráfico y está habilitada por la <xref:System.Windows.PropertyPath> clase y su convertidor de tipos. Para obtener una descripción más completa de la semántica de búsqueda, consulte [sintaxis de PropertyPath de XAML](../../../../docs/framework/wpf/advanced/propertypath-xaml-syntax.md).  
  
<a name="property_element_syntax"></a>   
## <a name="property-element-syntax"></a>Sintaxis de elementos de propiedad  
 *Sintaxis de elementos de propiedad* es una sintaxis que difiere ligeramente de las reglas de sintaxis XML básicas para los elementos. En XML, el valor de un atributo es de hecho una cadena, con la única variación posible que se utiliza el formato de codificación de la cadena. En XAML, puede asignar otros elementos de objeto es el valor de una propiedad. Esta capacidad se habilita mediante la sintaxis de elemento de propiedad. En lugar de la propiedad que se especifica como un atributo dentro de la etiqueta de elemento, la propiedad se especifica utilizando un elemento de apertura de etiquetas en *elementTypeName*.*propertyName* formulario, el valor de la propiedad se especifica dentro de y, a continuación, se cierra el elemento de propiedad.  
  
 En concreto, la sintaxis comienza con un corchete angular de apertura)\<), followed immediately by the type name of the class or structure that the property element syntax is contained within. followed="" immediately="" by="" the="" type="" name="" of="" the="" class="" or="" structure="" that="" the="" property="" element="" syntax="" is="" contained="">\</), followed immediately by the type name of the class or structure that the property element syntax is contained within.> Esto va seguido inmediatamente por un solo punto (.), a continuación, por el nombre de una propiedad, a continuación, un corchete angular derecho (>). Al igual que con la sintaxis de atributo, esa propiedad debe existir dentro de los miembros públicos declarados del tipo especificado. El valor que se asignará a la propiedad está incluido dentro del elemento de propiedad. Normalmente, el valor se muestra como uno o más elementos de objeto, porque la especificación de objetos como valores es el escenario de esa sintaxis de elementos de propiedad pretende resolver. Por último, una etiqueta de cierre equivalente especificando el mismo *elementTypeName*.*propertyName* debe proporcionarse combinación en anidada y equilibrada con otras etiquetas de elemento correctamente.  
  
 Por ejemplo, la siguiente es la sintaxis de elemento de propiedad para la <xref:System.Windows.FrameworkElement.ContextMenu%2A> propiedad de un <xref:System.Windows.Controls.Button>.  
  
 [!code-xml[XAMLOvwSupport#ContextMenu](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#contextmenu)]  
  
 El valor dentro de un elemento de propiedad también se muestra como texto interno, en casos donde el tipo de propiedad especificado es un tipo de valor primitivo, como <xref:System.String>, o una enumeración cuando se especifica un nombre. Estos dos usos no son habituales, porque cada uno de estos casos también podría utilizar una sintaxis de atributo más sencilla. Un escenario para rellenar un elemento de propiedad con una cadena es para las propiedades que no son propiedad de contenido XAML, pero se utilizan para la representación de texto de la interfaz de usuario y elementos de espacio en blanco determinados, como saltos de línea son necesarios para aparecen en el texto de la IU. La sintaxis de atributo no puede conservar saltos de línea, pero pueden sintaxis de elemento de propiedad, siempre y cuando esté activa la conservación de espacio en blanco significativo (para obtener más información, consulte [Whitespace Processing in XAML](../../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md)). Otro escenario es para que [x: Uid (directiva)](../../../../docs/framework/xaml-services/x-uid-directive.md) se puede aplicar al elemento property y marcar, por tanto, el valor como un valor que se debe traducir en WPF BAML de salida o por otras técnicas.  
  
 Un elemento de propiedad no se representa en el árbol lógico de WPF. Un elemento de propiedad es simplemente una sintaxis determinada para establecer una propiedad y no es un elemento que tiene una instancia o un objeto de copia de seguridad. (Para obtener más información sobre el concepto de árbol lógico, consulte [árboles en WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md).)  
  
 Para las propiedades que se admiten la sintaxis de atributo y propiedad de elemento, las dos sintaxis generalmente tienen el mismo resultado, aunque sutilezas como el control de espacios en blanco pueden variar ligeramente entre las sintaxis.  
  
<a name="collection_syntax"></a>   
## <a name="collection-syntax"></a>Sintaxis de colección  
 La especificación XAML requiere que las implementaciones de procesador XAML para identificar las propiedades que el tipo de valor es una colección. La implementación de procesador XAML general en .NET se basa en código administrado y el CLR e identifica los tipos de colección a través de uno de los siguientes:  
  
-   Escriba implementa <xref:System.Collections.IList>.  
  
-   Escriba implementa <xref:System.Collections.IDictionary>.  
  
-   Tipo que se deriva de <xref:System.Array> (para obtener más información acerca de las matrices en XAML, vea [x: Array Markup Extension](../../../../docs/framework/xaml-services/x-array-markup-extension.md).)  
  
 Si el tipo de una propiedad es una colección, el tipo deducido de colección no necesita especificarse en el marcado como un elemento de objeto. En su lugar, los elementos que van a convertirse en los elementos de la colección se especifican como uno o más elementos secundarios del elemento de propiedad. Cada elemento de este tipo se evalúa a un objeto durante la carga y se agrega a la colección mediante una llamada a la `Add` el método de la colección implícita. Por ejemplo, el <xref:System.Windows.Style.Triggers%2A> propiedad de <xref:System.Windows.Style> toma el tipo de colección especializado <xref:System.Windows.TriggerCollection>, que implementa <xref:System.Collections.IList>. No es necesario crear una instancia de un <xref:System.Windows.TriggerCollection> elemento de objeto en el marcado. En su lugar, especifique uno o más <xref:System.Windows.Trigger> elementos como elementos dentro de la `Style.Triggers` elemento de propiedad, donde <xref:System.Windows.Trigger> (o una clase derivada) es el tipo esperado como el tipo de elemento para fuertemente tipada e implícita <xref:System.Windows.TriggerCollection>.  
  
 [!code-xml[XAMLOvwSupport#SyntaxPECollection](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#syntaxpecollection)]  
  
 Una propiedad puede ser un tipo de colección y la propiedad de contenido XAML para ese tipo y tipos derivados, que se describe en la sección siguiente de este tema.  
  
 Un elemento de colección implícito crea a un miembro en la representación de árbol lógico, aunque no aparece en el marcado como un elemento. Normalmente el constructor del tipo primario realiza la creación de instancias de la colección que es una de sus propiedades y la colección inicialmente vacía se convierte en parte del árbol de objetos.  
  
> [!NOTE]
>  Las interfaces de lista y diccionario genéricas (<xref:System.Collections.Generic.IList%601> y <xref:System.Collections.Generic.IDictionary%602>) no se admiten para la detección de la colección.\</TKey, TValue> Sin embargo, puede usar el <xref:System.Collections.Generic.List%601> de clase como una clase base, ya que implementa <xref:System.Collections.IList> directamente, o <xref:System.Collections.Generic.Dictionary%602> como una clase base, ya que implementa <xref:System.Collections.IDictionary> directamente.\</TKey, TValue>  
  
 En las páginas de referencia de .NET para los tipos de colección, esta sintaxis con la omisión deliberada del elemento de objeto para una colección ocasionalmente se indica en las secciones de sintaxis XAML como sintaxis de colección implícita.  
  
 Con la excepción del elemento raíz, cada elemento de objeto en un archivo XAML que está anidado como elemento secundario de otro elemento es realmente un elemento que es uno o ambos de los siguientes casos: un miembro de una propiedad de colección implícita de su elemento primario o un elemento que especifica el valor de la propiedad de contenido XAML para el elemento primario (el XAML contenido propiedades se describirá en una sección posterior). En otras palabras, la relación de elementos primarios y secundarios en una página de marcado es realmente un objeto único en la raíz, y cada elemento de objeto debajo de la raíz es una instancia única que proporciona un valor de propiedad del elemento primario o uno de los elementos de una colección que es también un valor de propiedad de tipo de colección del elemento primario. Este concepto de raíz única es común en XML y se refuerza con frecuencia en el comportamiento de las API que cargan XAML como <xref:System.Windows.Markup.XamlReader.Load%2A>.  
  
 En el ejemplo siguiente se muestra una sintaxis con el elemento de objeto para una colección (<xref:System.Windows.Media.GradientStopCollection>) especificado explícitamente.  
  
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
  
 Tenga en cuenta que no siempre es posible declarar explícitamente la colección. Por ejemplo, intenta declarar <xref:System.Windows.TriggerCollection> explícitamente en el que se muestra anteriormente <xref:System.Windows.Style.Triggers%2A> ejemplo produciría un error. Declarar explícitamente la colección requiere que la clase de colección debe admitir un constructor predeterminado, y <xref:System.Windows.TriggerCollection> no tiene un constructor predeterminado.  
  
<a name="xaml_content_properties"></a>   
## <a name="xaml-content-properties"></a>Propiedades de contenido XAML  
 Sintaxis de contenido XAML es una sintaxis que sólo está habilitada en las clases que especifican la <xref:System.Windows.Markup.ContentPropertyAttribute> como parte de su declaración de clase. El <xref:System.Windows.Markup.ContentPropertyAttribute> hace referencia al nombre de propiedad es la propiedad de contenido de ese tipo de elemento (incluidas las clases derivadas). Cuando procesa un procesador XAML, los elementos secundarios o texto interno que se encuentran entre las etiquetas apertura y cierre del elemento de objeto se asignará el valor de la propiedad de contenido XAML para ese objeto. Se le permite especificar los elementos de propiedad explícitos de la propiedad de contenido, pero este uso no se muestra normalmente en las secciones de sintaxis XAML en la referencia. NET. La técnica explícita/detallada tiene valor ocasional para mayor claridad del marcado o como una cuestión de estilo de marcado, pero normalmente es el propósito de una propiedad de contenido optimizar el marcado para que los elementos que están relacionados de manera intuitiva como elementos primarios y secundarios se pueden anidar directamente. Etiquetas de elemento de propiedad para otras propiedades de un elemento no se asignan como "contenido" por una definición estricta de lenguaje XAML; que se procesan previamente en el orden de procesamiento del analizador XAML y no se consideran "contenido".  
  
### <a name="xaml-content-property-values-must-be-contiguous"></a>Valores de propiedad de contenido XAML deben ser contiguos  
 El valor de una propiedad de contenido XAML se debe proporcionar exclusivamente antes o después de cualquier otro elemento de propiedad en ese elemento de objeto. Esto es cierto si el valor de una propiedad de contenido de XAML se especifica como una cadena o como uno o más objetos. Por ejemplo, no se analiza el marcado siguiente:  
  
```  
<Button>I am a   
  <Button.Background>Blue</Button.Background>  
  blue button</Button>  
```  
  
 Esto no es válido básicamente porque si esta sintaxis se hiciera explícita utilizando la sintaxis de elemento de propiedad para la propiedad de contenido, a continuación, la propiedad de contenido se establecería dos veces:  
  
```  
<Button>  
  <Button.Content>I am a </Button.Content>  
  <Button.Background>Blue</Button.Background>  
  <Button.Content> blue button</Button.Content>  
</Button>  
```  
  
 Un ejemplo de igual forma ilegal es si la propiedad de contenido es una colección y los elementos secundarios están intercalados con elementos de propiedad:  
  
```  
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
 Para poder aceptar más de un elemento de objeto único como contenido, el tipo de la propiedad de contenido concreto debe ser un tipo de colección. De forma similar a la sintaxis de elemento de propiedad para los tipos de colección, un procesador XAML debe identificar los tipos que son tipos de colección. Si un elemento tiene una propiedad de contenido XAML y el tipo de propiedad de contenido XAML es una colección, el tipo de colección implícito no necesita especificarse en el marcado como un elemento de objeto y la propiedad de contenido XAML no necesita estar especificado como un elemento de propiedad. Por lo tanto, el modelo de contenido aparente en el marcado puede tener ahora más elementos secundarios asignados como contenido. La siguiente es la sintaxis de contenido para un <xref:System.Windows.Controls.Panel> clase derivada. Todos los <xref:System.Windows.Controls.Panel> clases derivadas establecer la propiedad de contenido XAML para que sea <xref:System.Windows.Controls.Panel.Children%2A>, que requiere un valor de tipo <xref:System.Windows.Controls.UIElementCollection>.  
  
 [!code-xml[XAMLOvwSupport#SyntaxContent](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page5.xaml#syntaxcontent)]  
  
 Tenga en cuenta que ni el elemento de propiedad para <xref:System.Windows.Controls.Panel.Children%2A> ni el elemento para el <xref:System.Windows.Controls.UIElementCollection> se requiere en el marcado. Esta es una característica de diseño de XAML para que los contenidos de forma recursiva los elementos que definen un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] representan una forma más intuitiva como un árbol de elementos anidados con relaciones de elemento primario-secundario inmediato, sin que intervenga etiquetas de elemento de propiedad u objetos de colección. De hecho, <xref:System.Windows.Controls.UIElementCollection> no puede especificarse explícitamente en el marcado como un elemento de objeto, por diseño. Dado que su único uso previsto es como una colección implícita, <xref:System.Windows.Controls.UIElementCollection> no expone un constructor público predeterminado y, por tanto, no pueden crearse instancias como elemento de objeto.  
  
### <a name="mixing-property-elements-and-object-elements-in-an-object-with-a-content-property"></a>Combinación de elementos de propiedad y los elementos de objeto en un objeto con una propiedad de contenido  
 La especificación XAML declara que un procesador XAML puede exigir que los elementos de objeto que se usan para rellenar la propiedad de contenido XAML dentro de un elemento de objeto deben ser contiguos y no se deben combinar. Esta restricción contra la mezcla de elementos de propiedad y contenido la aplica el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] procesadores XAML.  
  
 Puede tener un elemento de objeto secundario como el primer marcado inmediato dentro de un elemento de objeto. A continuación, puede introducir elementos de propiedad. O bien, puede especificar uno o más elementos de propiedad, luego contenido y más elementos de propiedad. Pero una vez que un elemento de propiedad sigue al contenido, no se puede introducir cualquier otro tipo de contenido, sólo se pueden agregar elementos de propiedad.  
  
 Este contenido o el requisito de orden del elemento de propiedad no se aplica al texto interno utilizado como contenido. Sin embargo, sigue siendo un buen estilo de marcado para mantener el texto interno contiguo, porque el espacio en blanco significativo será difícil de detectar visualmente en el marcado si los elementos de propiedad están intercalados con texto interno.  
  
<a name="xaml_namespaces"></a>   
## <a name="xaml-namespaces"></a>Espacios de nombres XAML  
 Ninguno de los ejemplos de sintaxis anterior especifica un espacio de nombres XAML que no sea el espacio de nombres XAML. En los típicos [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplicaciones, el valor predeterminado de espacio de nombres XAML se especifica como el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] espacio de nombres. Puede especificar espacios de nombres XAML que no sea el espacio de nombres XAML predeterminado y seguir usando sintaxis similar. Pero, a continuación, en cualquier lugar donde se denomina una clase que no es accesible dentro del espacio de nombres XAML predeterminado, ese nombre de clase debe ir precedido por el prefijo de espacio de nombres XAML como asignado al espacio de nombres CLR correspondiente. Por ejemplo, `<custom:Example/>` es una sintaxis de elemento de objeto para crear una instancia de la `Example` (clase), donde el espacio de nombres CLR que contiene esa clase (y posiblemente la información de ensamblado externo que contiene tipos de respaldo) estaba asignada previamente a la `custom` prefijo.  
  
 Para obtener más información acerca de espacios de nombres XAML, vea [XAML Namespaces and Namespace Mapping for WPF XAML](../../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).  
  
<a name="markup_extensions"></a>   
## <a name="markup-extensions"></a>Extensiones de marcado  
 XAML define una entidad que permite un escape desde el control de procesador XAML normal de valores de atributo de cadena o elementos de objeto y cede el procesamiento a una clase de respaldo de programación de la extensión de marcado. El carácter que identifica una extensión de marcado para un procesador XAML cuando se utiliza la sintaxis de atributo es la llave de apertura ({}), seguida de cualquier carácter que no sea una llave de cierre (}). La primera cadena de la llave de apertura debe hacer referencia a la clase que proporciona el comportamiento de extensión determinado, donde la referencia puede omitir la subcadena "Extensión" si dicha subcadena forma parte del nombre de clase es true. Posteriormente, puede aparecer un espacio y, a continuación, cada carácter subsiguiente se utiliza como entrada mediante la implementación de la extensión, hasta que se encuentra la llave de cierre.  
  
 La implementación de XAML de .NET utiliza la <xref:System.Windows.Markup.MarkupExtension> clase abstracta como base para todas las extensiones de marcado admitidas por [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , así como otros marcos o tecnologías. Las extensiones de marcado que [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] implementa específicamente a menudo está diseñada para proporcionar un medio para hacer referencia a otros objetos existentes, o para hacer referencias diferidas a los objetos que se evaluará en tiempo de ejecución. Por ejemplo, un enlace de datos simple de WPF se consigue especificando la `{Binding}` la extensión de marcado en lugar del valor que tomaría normalmente una propiedad determinada. Muchas de las extensiones de marcado WPF permiten una sintaxis de atributo para las propiedades donde una sintaxis de atributo no sería posible. Por ejemplo, un <xref:System.Windows.Style> objeto es un tipo relativamente complejo que contiene una serie de objetos y propiedades anidada. Los estilos en WPF se definen normalmente como un recurso en un <xref:System.Windows.ResourceDictionary>y, a continuación, hace referencia a través de una de las dos extensiones de marcado WPF que solicitan un recurso. La extensión de marcado cede la evaluación del valor de propiedad para una búsqueda de recursos y permite ofrecer el valor de la <xref:System.Windows.FrameworkElement.Style%2A> propiedad, tomando el tipo <xref:System.Windows.Style>, en atributo sintaxis como en el ejemplo siguiente:  
  
 `<Button Style="{StaticResource MyStyle}">My button</Button>`  
  
 Aquí, `StaticResource` identifica el <xref:System.Windows.StaticResourceExtension> clase proporciona la implementación de extensión de marcado. La siguiente cadena `MyStyle` se utiliza como entrada para el valor no predeterminado <xref:System.Windows.StaticResourceExtension> constructor, donde el parámetro que se toman de la cadena de extensión declara solicitado <xref:System.Windows.ResourceKey>. `MyStyle`se espera que la [x: Key](../../../../docs/framework/xaml-services/x-key-directive.md) valor de un <xref:System.Windows.Style> definido como un recurso. El [extensión de marcado StaticResource](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md) uso solicita que el recurso se utiliza para proporcionar la <xref:System.Windows.Style> valor de propiedad a través de la lógica de búsqueda de recursos estáticos en tiempo de carga.  
  
 Para obtener más información acerca de las extensiones de marcado, consulte [las extensiones de marcado y XAML de WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md). Para obtener una referencia de extensiones de marcado y otra características habilitadas en la implementación de XAML de .NET general de programación de XAML, vea [XAML Namespace (x:) Características del lenguaje](../../../../docs/framework/xaml-services/xaml-namespace-x-language-features.md). Para las extensiones de marcado específico de WPF, vea [extensiones XAML de WPF](../../../../docs/framework/wpf/advanced/wpf-xaml-extensions.md).  
  
<a name="attached_properties"></a>   
## <a name="attached-properties"></a>Propiedades asociadas  
 Las propiedades asociadas son un concepto de programación introducido en XAML mediante el cual propiedades pueden pertenecen y definidos por un tipo determinado, pero establezca como atributos o elementos de propiedad en cualquier elemento. El escenario principal que están destinadas a las propiedades adjuntas es permitir que los elementos secundarios en una estructura de marcado enviar información a un elemento primario sin necesidad de un modelo de objetos compartido por todos los elementos. Por el contrario, las propiedades adjuntas pueden usarse por los elementos primarios para enviar información a los elementos secundarios. Para obtener más información sobre el propósito de las propiedades asociadas y cómo crear sus propias propiedades asociadas, consulte [Attached Properties Overview](../../../../docs/framework/wpf/advanced/attached-properties-overview.md).  
  
 Propiedades asociadas utilizan una sintaxis que a primera vista es similar a la sintaxis de elementos de propiedad, que también especificar un *typeName*.*propertyName* combinación. Hay dos diferencias importantes:  
  
-   Puede usar el *typeName*.*propertyName* combinación incluso al establecer una propiedad asociada a través de la sintaxis de atributo. Las propiedades asociadas son el único caso en el que certificar el nombre de propiedad es un requisito en una sintaxis de atributo.  
  
-   También puede utilizar la sintaxis de elementos de propiedad para las propiedades asociadas. Sin embargo, para la sintaxis de elementos de propiedad típica, el *typeName* especificar es el elemento de objeto que contiene el elemento de propiedad. Si hace referencia a una propiedad adjunta la *typeName* es la clase que define la propiedad adjunta, no el elemento contenedor del objeto.  
  
<a name="attached_events"></a>   
## <a name="attached-events"></a>Eventos asociados  
 Eventos adjuntos son otro concepto de programación introducido en XAML donde se pueden definir eventos con un tipo específico, pero los controladores se pueden adjuntar a cualquier elemento de objeto. En la implementación de WOF, a menudo, el tipo que define un evento adjunto es un tipo estático que define un servicio y, a veces estos eventos adjuntos expuestos por un alias de evento enrutado en los tipos que exponen el servicio. Controladores de eventos asociados se especifican mediante la sintaxis de atributo. Como con eventos adjuntos, la sintaxis de atributo se expande para que los eventos asociados permitir una *typeName*.*eventName* uso, donde *typeName* es la clase que proporciona `Add` y `Remove` descriptores de acceso de controlador de eventos para la infraestructura de evento adjunto y *eventName* es el nombre del evento.  
  
<a name="anatomy_of_a_xaml_page_root_element"></a>   
## <a name="anatomy-of-a-xaml-root-element"></a>Anatomía de un elemento raíz XAML  
 En la tabla siguiente muestra un típico elemento raíz XAML desglosado que muestra los atributos específicos de un elemento raíz:  
  
|||  
|-|-|  
|`<Page`|Elemento de objeto de apertura del elemento raíz|  
|`xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"`|El valor predeterminado ([!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]) espacio de nombres XAML|  
|`xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`|El espacio de nombres XAML de lenguaje XAML|  
|`x:Class="ExampleNamespace.ExampleCode"`|La declaración de clase parcial que conecta el marcado con cualquier código subyacente definido para la clase parcial|  
|`>`|Final del elemento de objeto para la raíz. Objeto todavía no se cierra porque el elemento contiene elementos secundarios|  
  
<a name="optional_and_nonrecommended_xaml_usages"></a>   
## <a name="optional-and-nonrecommended-xaml-usages"></a>Usos opcionales y no recomendados de XAML  
 Las secciones siguientes describen los usos de XAML que son admitidos técnicamente por procesadores XAML, pero que producen nivel de detalle u otros problemas estéticos que interfieren con archivos XAML restantes legible cuando el desarrollo de aplicaciones que contienen orígenes XAML.  
  
### <a name="optional-property-element-usages"></a>Usos de elemento de propiedad opcional  
 Usos de elemento de propiedad opcional incluyen la escritura explícita de las propiedades de contenido del elemento que el procesador XAML considera implícito. Por ejemplo, cuando se declara el contenido de un <xref:System.Windows.Controls.Menu>, puede declarar explícitamente el <xref:System.Windows.Controls.ItemsControl.Items%2A> colección de la <xref:System.Windows.Controls.Menu> como un `<Menu.Items>` etiqueta de elemento de propiedad y se coloca cada <xref:System.Windows.Controls.MenuItem> dentro de `<Menu.Items>`, en lugar de utilizar el comportamiento implícito del procesador XAML que todos los elementos secundarios de un <xref:System.Windows.Controls.Menu> debe ser un <xref:System.Windows.Controls.MenuItem> y se colocan en el <xref:System.Windows.Controls.ItemsControl.Items%2A> colección. A veces los usos opcionales pueden ayudar a clarificar visualmente la estructura del objeto tal como se representa en el marcado. O bien, a veces, el uso de un elemento de propiedad explícitos puede evitar un marcado que es técnicamente funcional pero visualmente confuso, como las extensiones de marcado anidados dentro de un valor de atributo.  
  
### <a name="full-typenamemembername-qualified-attributes"></a>Atributos nombreDeTipo.nombreDeMiembro completos  
 The *typeName*.*memberName* formulario para un atributo funciona más universalmente que el caso de eventos enrutados. Pero en otras situaciones ese formato es superfluo y se debería evitar, aunque sólo sea por motivos de estilo de marcado y legibilidad. En el ejemplo siguiente, cada una de las tres referencias a la <xref:System.Windows.Controls.Control.Background%2A> atributo son completamente equivalentes:  
  
 [!code-xml[XAMLOvwSupport#TypeNameProp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#typenameprop)]  
  
 `Button.Background`funciona porque la búsqueda calificada de esa propiedad en <xref:System.Windows.Controls.Button> es correcta (<xref:System.Windows.Controls.Control.Background%2A> se ha heredado de Control) y <xref:System.Windows.Controls.Button> es la clase del elemento de objeto o una clase base. `Control.Background`funciona porque la <xref:System.Windows.Controls.Control> clase define realmente <xref:System.Windows.Controls.Control.Background%2A> y <xref:System.Windows.Controls.Control> es una <xref:System.Windows.Controls.Button> clase base.  
  
 Sin embargo, la siguiente *typeName*.*memberName* ejemplo de formulario no funciona y, por tanto, se muestra marcado como comentario:  
  
 [!code-xml[XAMLOvwSupport#TypeNameBadProp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#typenamebadprop)]  
  
 <xref:System.Windows.Controls.Label> es otra clase derivada de <xref:System.Windows.Controls.Control>, y si se había especificado `Label.Background` dentro de un <xref:System.Windows.Controls.Label> elemento de objeto, este uso habría funcionado. Sin embargo, dado que <xref:System.Windows.Controls.Label> no es la clase o clase base de <xref:System.Windows.Controls.Button>, el comportamiento especificado del procesador XAML es procesar `Label.Background` como una propiedad adjunta. `Label.Background`no es una propiedad adjunta disponible y se produce un error en este uso.  
  
### <a name="basetypenamemembername-property-elements"></a>Propiedad nombreDeTipoBase.nombreDeMiembro  
 De forma similar a cómo el *typeName*.*memberName* formulario funciona para la sintaxis de atributo, un *baseTypeName*.* memberName* sintaxis funciona para la sintaxis de elemento de propiedad. Por ejemplo, la sintaxis siguiente funciona:  
  
 [!code-xml[XAMLOvwSupport#GoofyPE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#goofype)]  
  
 En este caso, el elemento de propiedad se proporcionó como `Control.Background` , aunque el elemento estaba incluido en `Button`.  
  
 Pero como *typeName*.*memberName* formato de los atributos, *baseTypeName*.* memberName* un estilo pobre en el marcado y se debe evitar.  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)   
 [XAML Namespace (x:) Características del lenguaje](../../../../docs/framework/xaml-services/xaml-namespace-x-language-features.md)   
 [Extensiones XAML de WPF](../../../../docs/framework/wpf/advanced/wpf-xaml-extensions.md)   
 [Información general sobre propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)   
 [Clases TypeConverter y XAML](../../../../docs/framework/wpf/advanced/typeconverters-and-xaml.md)   
 [Clases XAML y personalizadas para WPF](../../../../docs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)