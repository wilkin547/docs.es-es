---
title: "Informaci&#243;n general sobre XAML (WPF) | Microsoft Docs"
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
  - "sintaxis de atributo [XAML]"
  - "clases base [XAML]"
  - "clases [XAML]"
  - "archivos de código subyacente [WPF], XAML"
  - "propiedades de colección [XAML]"
  - "modelos de contenido [XAML]"
  - "eventos [XAML]"
  - "Lenguaje XAML (véase XAML)"
  - "elemento de propiedad [XAML]"
  - "elemento raíz [XAML]"
  - "eventos enrutados"
  - "interfaces de usuario [XAML]"
  - "XAML [WPF], acerca de XAML"
ms.assetid: a80db4cd-dd0f-479f-a45f-3740017c22e4
caps.latest.revision: 57
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 50
---
# Informaci&#243;n general sobre XAML (WPF)
En este tema se describen las características del lenguaje XAML y se muestra cómo usar el código XAML para escribir aplicaciones [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  En este tema se describe el código XAML específicamente tal y como lo implementa por [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  El propio código XAML es un concepto de lenguaje más amplio que [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
   
  
<a name="what_is_xaml"></a>   
## ¿Qué es XAML?  
 XAML es un lenguaje declarativo de marcado  Tal y como se aplica en el modelo de programación [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)], XAML simplifica la creación de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] para una aplicación [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)].  Se pueden crear elementos visibles de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] en el marcado XAML declarativo y, a continuación, separar la definición de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de la lógica en tiempo de ejecución mediante archivos de código subyacente, que se unen al marcado mediante definiciones de clases parciales.  XAML representa directamente la creación de instancias de objetos en un conjunto concreto de tipos de respaldo definidos en ensamblados. Esto no es lo que sucede con la mayoría de lenguajes de marcado, que normalmente se interpretan sin esa relación directa con un sistema de tipos de respaldo.  El código XAML habilita un flujo de trabajo en el que las partes independientes pueden funcionar en la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] y la lógica de una aplicación, a través de herramientas potencialmente diferentes.  
  
 Cuando se representan como texto, los archivos XAML son archivos XML que generalmente tienen la extensión `.xaml`.  Los archivos se pueden codificar con cualquier codificación XML, pero lo habitual es la codificación UTF\-8.  
  
 En el ejemplo siguiente se muestra cómo podría crear un botón como parte de una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  Este ejemplo se ha pensado simplemente para que tenga una idea de cómo representa el código XAML las metáforas de programación de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] común \(no es un ejemplo completo\).  
  
 [!code-xml[XAMLOvwSupport#DirtSimple](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page2.xaml#dirtsimple)]  
  
<a name="xaml_syntax_in_brief"></a>   
## Resumen de sintaxis de XAML  
 En las secciones siguientes se explican las formas básicas de la sintaxis XAML y se proporciona un breve ejemplo de marcado.  Estas secciones no están pensadas para proporcionar información completa sobre cada sintaxis, por ejemplo, cómo se representan en el sistema de tipos de respaldo.  Para obtener más información acerca de los detalles específicos de la sintaxis de XAML para cada una de las formas de sintaxis presentadas en este tema, vea [Detalles de la sintaxis XAML](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md).  
  
 Gran parte del material de las secciones siguientes será básico para usted si tiene familiaridad con el lenguaje XML.  Esta es una consecuencia de uno de los principios de diseño básicos de XAML.  XAML El lenguaje XAML define conceptos propios, pero estos conceptos funcionan dentro del lenguaje XML y del formato de marcado.  
  
### Elementos de objeto XAML  
 Normalmente, un elemento de objeto declara una instancia de un tipo.  Ese tipo se define en los ensamblados que proporcionan los tipos de respaldo para una tecnología que utiliza XAML como un lenguaje.  
  
 La sintaxis del elemento de objeto siempre se inicia con un corchete angular de apertura \(\<\),  que va seguido del nombre del tipo donde se desea crear una instancia.  \(El nombre puede incluir un prefijo, un concepto que se explicará más adelante\). Después de esto, puede declarar opcionalmente los atributos en el elemento de objeto.  Para completar la etiqueta del elemento de objeto, finalice con un corchete angular de cierre \(\>\).  Opcionalmente, puede usar un formulario de autocierre que no tenga contenido y completar la etiqueta con una barra diagonal y un corchete angular de cierre \(\/\>\) seguidos.  Por ejemplo, examine de nuevo el fragmento de código de marcado mostrado anteriormente:  
  
 [!code-xml[XAMLOvwSupport#DirtSimple](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page2.xaml#dirtsimple)]  
  
 Esto especifica dos elementos de objeto: `<StackPanel>` \(con contenido y una etiqueta de cierre después\) y `<Button .../>` \(el formulario de autocierre, con varios atributos\).  Los elementos de objeto `StackPanel` y `Button` se asignan al nombre de una clase definida por [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y que forma parte de los ensamblados de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Al especificar una etiqueta de elemento de objeto, crea una instrucción para que el procesamiento XAML cree una nueva instancia.  Cada instancia se crea llamando al constructor predeterminado del tipo subyacente al analizar y cargar el código XAML.  
  
### Sintaxis de atributos \(propiedades\)  
 Las propiedades de un objeto se pueden expresar a menudo como atributos del elemento de objeto.  Una sintaxis de atributo denomina la propiedad que está estableciendo en la sintaxis de atributo, seguida del operador de asignación \(\=\).  El valor de un atributo siempre se especifica como una cadena incluida entre comillas.  
  
 La sintaxis de atributo es la sintaxis de establecimiento de propiedades más optimizada y será la más intuitiva para los desarrolladores que han utilizado lenguajes de marcado anteriormente.  Por ejemplo, el marcado siguiente crea un botón que tiene texto rojo y un fondo azul, además de mostrar texto especificado como `Content`.  
  
 [!code-xml[XAMLOvwSupport#BlueRedButton](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#blueredbutton)]  
  
### Sintaxis de elementos de propiedad  
 En algunas propiedades de un elemento de objeto, no es posible usar la sintaxis de atributo, ya que el objeto o la información necesaria para proporcionar el valor de propiedad no se puede expresar correctamente dentro de las comillas y restricciones de cadena de la sintaxis de atributo.  En estos casos, se puede utilizar otra sintaxis conocida como sintaxis de elementos de propiedad.  
  
 La sintaxis de la etiqueta inicial del elemento de propiedad es `<`*nombreDeTipo*`.`*nombreDePropiedad*`>`.  Generalmente, el contenido de la etiqueta es un elemento de objeto del tipo que la propiedad toma como su valor.  Después de especificar el contenido, debe cerrar el elemento de propiedad con una etiqueta de cierre.  La sintaxis de la etiqueta de cierre es `</`*nombreTipo*`.`*nombrePropiedad*`>`.  
  
 Si es posible utilizar una sintaxis de atributo, su uso es generalmente más conveniente, ya que habilita un marcado más compacto, pero suele ser una cuestión de estilo, no una limitación técnica.  El ejemplo siguiente muestra cómo se establecen las mismas propiedades que en el ejemplo anterior de sintaxis de atributo, pero ahora utilizando la sintaxis de elementos de propiedad para todas las propiedades de `Button`.  
  
 [!code-xml[XAMLOvwSupport#BlueRedButtonPE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#blueredbuttonpe)]  
  
### Sintaxis de colecciones  
 El lenguaje XAML incluye algunas optimizaciones que generan un marcado más humanamente legible.  Una de estas optimizaciones consiste en que si una propiedad determinada toma un tipo de colección, entonces los elementos que se declaran en el marcado como elementos secundarios dentro del valor de esa propiedad se convierten en parte de la colección.  En este caso, una colección de elementos de objeto secundarios es el valor que se establece para la propiedad de la colección.  
  
 En el ejemplo siguiente se muestra la sintaxis de colección para establecer los valores de la propiedad <xref:System.Windows.Media.GradientBrush.GradientStops%2A>:  
  
```xaml  
<LinearGradientBrush>  
  <LinearGradientBrush.GradientStops>  
    <!-- no explicit new GradientStopCollection, parser knows how to find or create -->  
    <GradientStop Offset="0.0" Color="Red" />  
    <GradientStop Offset="1.0" Color="Blue" />  
  </LinearGradientBrush.GradientStops>  
</LinearGradientBrush>  
```  
  
### Propiedades del contenido XAML  
 XAML especifica una característica del lenguaje por la que una clase puede designar exactamente una de sus propiedades para que sea la propiedad de contenido de XAML.  Los elementos secundarios de ese elemento de objeto se utilizan para establecer el valor de esa propiedad de contenido.  Es decir, únicamente para la propiedad de contenido puede omitir un elemento de propiedad cuando se establece esa propiedad en marcado XAML y genera una metáfora de elemento primario\/secundario más visible en el marcado.  
  
 Por ejemplo, <xref:System.Windows.Controls.Border> especifica una propiedad de contenido de <xref:System.Windows.Controls.Decorator.Child%2A>.  Los dos elementos <xref:System.Windows.Controls.Border> siguientes se tratan de la misma forma.  El primero se aprovecha de la sintaxis de la propiedad de contenido y omite el elemento de propiedad `Border.Child`.  El segundo muestra `Border.Child` explícitamente.  
  
```xaml  
<Border>  
  <TextBox Width="300"/>  
</Border>  
<!--explicit equivalent-->  
<Border>  
  <Border.Child>  
    <TextBox Width="300"/>  
  </Border.Child>  
</Border>  
```  
  
 Como regla del lenguaje XAML, el valor de una propiedad de contenido de XAML se debe proporcionar exclusivamente antes o después de cualquier otro elemento de propiedad en ese elemento de objeto.  Por ejemplo, el marcado siguiente no se puede compilar:  
  
```  
<Button>I am a   
  <Button.Background>Blue</Button.Background>  
  blue button</Button>  
```  
  
 Para obtener más información acerca de esta restricción en las propiedades de contenido de XAML, vea la sección "Propiedades del contenido XAML" de [Detalles de la sintaxis XAML](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md).  
  
### Contenido de texto  
 Un pequeño número de elementos de código XAML puede procesar directamente el texto como su contenido.  Para habilitar esto, debe ser cierto una de estas situaciones:  
  
-   La clase debe declarar una propiedad de contenido y esa propiedad de contenido debe ser de un tipo asignable a una cadena \(el tipo podría ser <xref:System.Object>\).  Por ejemplo, cualquier control <xref:System.Windows.Controls.ContentControl> usa la propiedad <xref:System.Windows.Controls.ContentControl.Content%2A> como su propiedad de contenido y es del tipo <xref:System.Object>. Esto admite el uso siguiente en un control <xref:System.Windows.Controls.ContentControl> práctico como <xref:System.Windows.Controls.Button>: `<Button>Hello</Button>`.  
  
-   El tipo debe declarar un convertidor de tipos, en cuyo caso el contenido de texto se usa como texto de inicialización para ese convertidor de tipos.  Por ejemplo: `<Brush>Blue</Brush>`.  Este caso es menos común en la práctica.  
  
-   El tipo debe ser una primitiva conocida del lenguaje XAML.  
  
### Propiedades de contenido y sintaxis de colección combinadas  
 Considere este ejemplo:  
  
```xaml  
<StackPanel>  
  <Button>First Button</Button>  
  <Button>Second Button</Button>  
</StackPanel>  
```  
  
 Aquí, cada control <xref:System.Windows.Controls.Button> es un elemento secundario de <xref:System.Windows.Controls.StackPanel>.  Éste es un marcado optimizado e intuitivo que omite dos etiquetas por dos razones diferentes.  
  
-   **Elemento de la propiedad StackPanel.Children omitido:** <xref:System.Windows.Controls.StackPanel> se deriva de <xref:System.Windows.Controls.Panel>.  <xref:System.Windows.Controls.Panel> define <xref:System.Windows.Controls.Panel.Children%2A?displayProperty=fullName> como su propiedad de contenido XAML.  
  
-   **Elemento de objeto UIElementCollection omitido:** La propiedad <xref:System.Windows.Controls.Panel.Children%2A?displayProperty=fullName> toma el tipo <xref:System.Windows.Controls.UIElementCollection>, que implementa <xref:System.Collections.IList>.  Se puede omitir la etiqueta de elemento de la colección, según las reglas del código XAML para procesar colecciones como <xref:System.Collections.IList>.  \(En este caso, no se pueden crear realmente instancias de <xref:System.Windows.Controls.UIElementCollection>, porque no expone un constructor predeterminado y, por eso, el elemento de objeto <xref:System.Windows.Controls.UIElementCollection> se muestra marcado como comentario\).  
  
```xaml  
<StackPanel>  
  <StackPanel.Children>  
    <!--<UIElementCollection>-->  
    <Button>First Button</Button>  
    <Button>Second Button</Button>  
    <!--</UIElementCollection>-->  
  </StackPanel.Children>  
</StackPanel>  
```  
  
### Sintaxis de atributos \(eventos\)  
 La sintaxis de atributos también se puede usar para los miembros que son eventos en lugar de propiedades.  En este caso, el nombre del atributo es el nombre del evento.  En la implementación WPF de eventos para XAML, el valor del atributo es el nombre de un controlador que implementa el delegado de ese evento.  Por ejemplo, el marcado siguiente asigna un controlador para el evento <xref:System.Windows.Controls.Primitives.ButtonBase.Click> al control <xref:System.Windows.Controls.Button> creado en el marcado:  
  
 [!code-xml[XAMLOvwSupport#ButtonWithCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page3.xaml#buttonwithcodebehind)]  
  
 En WPF, los eventos y el código XAML son más complejos que este ejemplo de la sintaxis de atributos.  Por ejemplo, podría preguntarse qué representa el elemento `ClickHandler` al que se hace referencia aquí y cómo se define.  Esto se explicará en la próxima sección  de este tema.  
  
<a name="case_and_whitespace_in_xaml"></a>   
## El uso de mayúsculas y minúsculas y del espacio en blanco en XAML  
 En general, XAML distingue entre mayúsculas y minúsculas.  Para fines de resolver los tipos de respaldo, el XAML de WPF distingue entre mayúsculas y minúsculas por las mismas reglas que el CLR.  Los elementos de objeto, los elementos de propiedad y los nombres de atributo se deben especificar utilizando la grafía que distinga mayúsculas de minúsculas cuando se comparan por nombre con el tipo subyacente en el ensamblado, o con un miembro de un tipo.  Las palabras clave y primitivas del lenguaje XAML también distinguen entre mayúsculas y minúsculas.  Los valores no siempre distinguen entre mayúsculas y minúsculas.  La distinción entre mayúsculas y minúsculas para los valores dependerá del comportamiento del convertidor de tipos asociado a la propiedad que toma el valor o del tipo de valor de propiedad.  Por ejemplo, las propiedades que toma el tipo <xref:System.Boolean> pueden tomar `true` o `True` como valores equivalentes, pero solo porque la conversión de tipos de cadena del analizador de código XAML de WPF nativo para la cadena a <xref:System.Boolean> ya los permite como equivalentes.  
  
 Los procesadores y serializadores XAML de WPF omiten o quitan todos los espacios en blanco no significativos y normalizan cualquier espacio en blanco significativo.  Esto es coherente con las recomendaciones de comportamiento de espacio en blanco predeterminado de la especificación de XAML.  Este comportamiento generalmente sólo tiene importancia si se especifican cadenas dentro de las propiedades de XAML.  Es decir, XAML convierte los caracteres de espacio, avance de línea y tabulación en espacios y, a continuación, conserva un espacio si lo encuentra en cualquier extremo de una cadena contigua.  La explicación completa del control de espacios en blanco de XAML no se aborda en este tema.  Para obtener información detallada, vea [Procesamiento de espacios en blanco en XAML](../../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).  
  
<a name="markup_extensions"></a>   
## Extensiones de marcado  
 Las extensiones de marcado son un concepto del lenguaje XAML.  Cuando se usan para proporcionar el valor de una sintaxis de atributos, las llaves \(`{` y `}`\) indican el uso de una extensión de marcado.  Este uso hace que el procesamiento XAML se aparte del tratamiento general de valores de atributo como una cadena literal o un valor directamente convertible en cadena.  
  
 Las extensiones de marcado más comunes utilizadas en la programación de aplicaciones de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] son [Binding](../../../../docs/framework/wpf/advanced/binding-markup-extension.md), utilizada para las expresiones de enlace de datos, y las referencias de recursos [StaticResource](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md) y [DynamicResource](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md).  Al usar las extensiones de marcado, se puede utilizar la sintaxis de atributos para proporcionar valores para las propiedades aunque esa propiedad no admita una sintaxis de atributos en general.  Las extensiones de marcado utilizan a menudo tipos de expresión intermedia para habilitar características tales como diferir los valores o hacer referencia a otros objetos que solo están presentes en tiempo de ejecución.  
  
 Por ejemplo, en el marcado siguiente se establece el valor de la propiedad <xref:System.Windows.FrameworkElement.Style%2A> mediante la sintaxis de atributos.  La propiedad <xref:System.Windows.FrameworkElement.Style%2A> toma una instancia de la clase <xref:System.Windows.Style>, cuya instancia no se podría crear mediante una cadena de sintaxis de atributo de forma predeterminada.  Pero en este caso, el atributo hace referencia a una extensión de marcado determinada, [StaticResource](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md).  Cuando se procesa dicha extensión de marcado, devuelve una referencia a un estilo del que ya se han creado instancias como un recurso con clave en un diccionario de recursos.  
  
<!-- TODO: review snippet reference  [!CODE [FEResourceSH#XAMLOvwShortResources](FEResourceSH#XAMLOvwShortResources)]  -->  
<!-- TODO: review snippet reference [!CODE [FEResourceSH#XAMLOvwShortResources2](FEResourceSH#XAMLOvwShortResources2)]  -->  
<!-- TODO: review snippet reference [!CODE [FEResourceSH#XAMLOvwShortResources3](FEResourceSH#XAMLOvwShortResources3)]  -->  
  
 Para obtener una lista de referencias de todas las extensiones de marcado para XAML implementadas específicamente en WPF, vea [Extensiones XAML de WPF](../../../../docs/framework/wpf/advanced/wpf-xaml-extensions.md).  Para obtener una lista de referencias de las extensiones de marcado definidas por System.Xaml y que están más disponibles para las implementaciones XAML de .NET Framework, vea [Características de lenguaje \(x:\) de espacios de nombres XAML](../../../../docs/framework/xaml-services/xaml-namespace-x-language-features.md).  Para obtener más información sobre los conceptos de la extensión de marcado, vea [Extensiones de marcado y XAML de WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
<a name="type_converters"></a>   
## Convertidores de tipos  
 En la sección , se ha dicho que el valor de atributo debe poder establecerlo una cadena.  El control nativo básico de cómo se convierten las cadenas en otros tipos de objeto o los valores primitivos se basa en el propio tipo <xref:System.String>, así como en algún procesamiento nativo para ciertos tipos como <xref:System.DateTime> o <xref:System.Uri>.  Pero muchos tipos o miembros de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] de esos tipos extienden el comportamiento básico del procesamiento de atributos de cadena, de tal forma que se pueden especificar instancias de tipos de objeto más complejos como cadenas y atributos.  
  
 La estructura <xref:System.Windows.Thickness> es un ejemplo de un tipo que incluye una conversión de tipos habilitada para los usos del código XAML.  <xref:System.Windows.Thickness> indica las medidas dentro de un rectángulo anidado y se usa como el valor de propiedades tales como <xref:System.Windows.FrameworkElement.Margin%2A>.  Al colocar un convertidor de tipos en <xref:System.Windows.Thickness>, todas las propiedades que usan la propiedad <xref:System.Windows.Thickness> son más fáciles de especificar en código XAML porque se pueden especificar como atributos.  En el ejemplo siguiente se usa una conversión de tipos y una sintaxis de atributos para proporcionar un valor a la propiedad <xref:System.Windows.FrameworkElement.Margin%2A>:  
  
 [!code-xml[XAMLOvwSupport#MarginTCE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page7.xaml#margintce)]  
  
 El ejemplo de sintaxis de atributo anterior es equivalente al ejemplo de sintaxis siguiente más detallado, donde la propiedad <xref:System.Windows.FrameworkElement.Margin%2A> se establece mediante la sintaxis de elementos de propiedad que contiene un elemento de objeto <xref:System.Windows.Thickness>.  Las cuatro propiedades clave de <xref:System.Windows.Thickness> se establecen como atributos en la nueva instancia:  
  
 [!code-xml[XAMLOvwSupport#MarginVerbose](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page7.xaml#marginverbose)]  
  
> [!NOTE]
>  También hay un número limitado de objetos en los que la conversión de tipos es la única manera pública de establecer una propiedad en ese tipo sin necesidad de una subclase, debido a que el propio objeto de tipo no tiene un constructor predeterminado.  Un ejemplo de ello sería <xref:System.Windows.Input.Cursor>.  
  
 Para obtener más información la compatibilidad de la conversión de tipos y su uso para la sintaxis de atributos, vea [Clases TypeConverter y XAML](../../../../docs/framework/wpf/advanced/typeconverters-and-xaml.md).  
  
<a name="xaml_root_elements_and_xaml_namespaces"></a>   
## Elementos raíz XAML y espacios de nombres XAML  
 Para que un archivo XAML pueda ser tanto un archivo XAML con un formato correcto como un archivo [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] válido, solo debe tener un elemento raíz.  Normalmente, en los escenarios WPF, se debe elegir un elemento raíz que tenga un significado notable en el modelo de aplicaciones WPF \(por ejemplo, <xref:System.Windows.Window> o <xref:System.Windows.Controls.Page> para una página, <xref:System.Windows.ResourceDictionary> para un diccionario externo o <xref:System.Windows.Application> para la definición de la aplicación\).  En el ejemplo siguiente se muestra el elemento raíz de un archivo XAML típico para una página [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], con el elemento raíz de <xref:System.Windows.Controls.Page>.  
  
 [!code-xml[XAMLOvwSupport#RootOnly](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page2.xaml#rootonly)]  
[!code-xml[XAMLOvwSupport#RootOnly2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page2.xaml#rootonly2)]  
  
 El elemento raíz también contiene los atributos `xmlns` y `xmlns:x`.  Estos atributos indican a un procesador XAML los espacios de nombres XAML que contienen las definiciones los tipos de respaldo a los que el marcado hará referencia.  El atributo `xmlns` indica específicamente el espacio de nombres XAML predeterminado.  Dentro este espacio de nombres XAML, los elementos de objeto en el marcado se pueden especificar sin un prefijo.  Para la mayoría de los escenarios de aplicaciones [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y para casi todos los ejemplos ofrecidos en las secciones de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] del [!INCLUDE[TLA2#tla_sdk](../../../../includes/tla2sharptla-sdk-md.md)], el espacio de nombres XAML predeterminado está asignado al espacio de nombres [!INCLUDE[TLA#tla_wpfxmlnsv1](../../../../includes/tlasharptla-wpfxmlnsv1-md.md)] de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  El atributo `xmlns:x` indica un espacio de nombres XAML adicional, que asigna el espacio de nombres del XAML [!INCLUDE[TLA#tla_xamlxmlnsv1](../../../../includes/tlasharptla-xamlxmlnsv1-md.md)].  
  
 Este uso de `xmlns` con el fin de definir un ámbito para el uso y asignación de un ámbito de nombres es coherente con la especificación XML 1.0.  Los ámbitos de nombres de código XAML solo se diferencian de los ámbitos de nombres de XML en que un ámbito de nombres de código XAML también implica al forma en que los tipos respaldan los elementos del ámbito de nombres cuando se trata de la resolución de tipos y del análisis del código XAML.  
  
 Observe que los atributos `xmlns` solo son estrictamente necesarios en el elemento raíz de cada archivo XAML.  Las definiciones de `xmlns` se aplicarán a todos los elementos descendientes del elemento raíz \(una vez más, este comportamiento es coherente con la especificación XML 1.0 para `xmlns`\). También se permiten atributos `xmlns` en otros elementos bajo el raíz, y se aplican a cualquier elemento descendiente del elemento de definición.  Sin embargo, una definición o redefinición frecuente de los espacios de nombres XAML puede dar lugar a un estilo de marcado XAML que resulte difícil de leer.  
  
 La implementación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] de su procesador XAML incluye una infraestructura que reconoce los ensamblados básicos de WPF.  Se sabe que los ensamblados básicos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contienen los tipos que admiten las asignaciones de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] al espacio de nombres XAML predeterminado.  Esto se habilita a través de la configuración que forma parte de su archivo de compilación de proyecto y los sistemas de compilación y proyectos de WPF.  Por consiguiente, solo es necesario declarar el espacio de nombres XAML predeterminado como `xmlns` predeterminado para hacer referencia a los elementos de código XAML que proceden de los ensamblados de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
### El prefijo x:  
 En el ejemplo de elemento raíz anterior, `x:` se usó para asignar el espacio de nombres XAML [!INCLUDE[TLA#tla_xamlxmlnsv1](../../../../includes/tlasharptla-xamlxmlnsv1-md.md)], que es el espacio de nombres XAML dedicado que admite las construcciones de lenguaje XAML.  Este prefijo `x:` se usa para asignar el espacio de nombres XAML en las plantillas de los proyectos, en los ejemplos y en la documentación de este [!INCLUDE[TLA2#tla_sdk](../../../../includes/tla2sharptla-sdk-md.md)].  El espacio de nombres XAML para el lenguaje XAML contiene varias construcciones de programación que usará con mucha frecuencia en el código XAML.  A continuación se muestra una lista de las construcciones de programación del prefijo `x:` más comunes que usará:  
  
-   [x:Key](../../../../docs/framework/xaml-services/x-key-directive.md): Establece una clave única para cada recurso de un <xref:System.Windows.ResourceDictionary> \(o conceptos de diccionario similares en otros marcos\).  Probablemente `x:Key` representará el 90% de los usos de `x:` que verá en un marcado de aplicación WPF típica.  
  
-   [x:Class](../../../../docs/framework/xaml-services/x-class-directive.md): especifica el espacio de nombres de [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] y el nombre de la clase que proporciona código subyacente para una página XAML.  Debe disponer de esta clase para admitir el código subyacente por el modelo de programación WPF; por esto casi siempre verá `x:` asignado, aun cuando no haya ningún recurso.  
  
-   [x:Name](../../../../docs/framework/xaml-services/x-name-directive.md): especifica un nombre de objeto en tiempo de ejecución para la instancia que existe en el código en tiempo de ejecución una vez procesado un elemento de objeto.  En general, utilizará frecuentemente una propiedad equivalente definida por WPF para [X:Name](../../../../docs/framework/xaml-services/x-name-directive.md).  Tales propiedades asignan específicamente a una propiedad de respaldo de CLR y así son más útiles para la programación de aplicaciones, donde frecuentemente se utiliza código del tiempo de ejecución para encontrar los elementos con nombre de XAML inicializado.  La propiedad de este tipo más común es <xref:System.Windows.FrameworkElement.Name%2A?displayProperty=fullName>.  Todavía podría utilizar [X:Name](../../../../docs/framework/xaml-services/x-name-directive.md) cuando la propiedad <xref:System.Windows.FrameworkElement.Name%2A> del nivel de marco WPF [](GTMT) equivalente no se admite en un tipo determinado.   Esto sucede en ciertos escenarios de animación.  
  
-   [x:Static](../../../../docs/framework/xaml-services/x-static-markup-extension.md): habilita una referencia que obtiene un valor estático que, de lo contrario, no sería una propiedad compatible con XAML.  
  
-   [x:Type](../../../../docs/framework/xaml-services/x-type-markup-extension.md): construye una referencia <xref:System.Type> basada en un nombre de tipo.  Esto se utiliza para especificar atributos que toman valores <xref:System.Type>, como <xref:System.Windows.Style.TargetType%2A?displayProperty=fullName>, aunque con frecuencia la propiedad dispone de una conversión de cadena a <xref:System.Type> nativa y el uso de la extensión de marcado [x:Type](../../../../docs/framework/xaml-services/x-type-markup-extension.md) es opcional.  
  
 Hay construcciones de programación adicionales en el prefijo o espacio de nombres XAML `x:` que no son tan habituales.  Para obtener información detallada, vea [Características de lenguaje \(x:\) de espacios de nombres XAML](../../../../docs/framework/xaml-services/xaml-namespace-x-language-features.md).  
  
<a name="custom_prefixes_and_custom_types_in_xaml"></a>   
## Prefijos personalizados y tipos personalizados en XAML  
 Para sus propios ensamblados personalizados o para los ensamblados fuera del núcleo WPF de PresentationCore, PresentationFramework y WindowsBase, puede especificar el ensamblado como parte de una asignación `xmlns` personalizada.  A continuación, puede hacer referencia a los tipos de ese ensamblado en su código XAML, siempre que su tipo esté implementado correctamente para admitir los usos de código XAML que intenta.  
  
 El siguiente es un ejemplo muy básico de cómo funcionan los prefijos personalizados en el marcado XAML.  El prefijo `custom` se define en la etiqueta de elemento raíz y se asigna a un ensamblado concreto que se empaqueta y está disponible con la aplicación.  Este ensamblado contiene un tipo `NumericUpDown`, que se implementa para admitir el uso XAML general, además de usar una herencia de clases que permite su inserción en este punto concreto en un modelo de contenido de código XAML de WPF.  Se declara una instancia de este control `NumericUpDown` como un elemento de objeto, utilizando el prefijo para que un analizador de código XAML sepa qué espacio de nombres XAML contiene el tipo y, por consiguiente, dónde está el ensamblado de respaldo que contiene la definición de tipo.  
  
```  
<Page  
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"   
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"   
    xmlns:custom="clr-namespace:NumericUpDownCustomControl;assembly=CustomLibrary"  
    >  
  <StackPanel Name="LayoutRoot">  
    <custom:NumericUpDown Name="numericCtrl1" Width="100" Height="60"/>  
...  
  </StackPanel>  
</Page>  
```  
  
 Para obtener más información acerca de los tipos personalizados en el código XAML, vea [Clases XAML y personalizadas para WPF](../../../../docs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md).  
  
 Para obtener más información sobre la relación existente entre los espacios de nombres XML y los espacios de nombres del código de respaldo en los ensamblados, vea [Espacios de nombres y asignación de espacios de nombres XAML para WPF](../../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).  
  
<a name="events_and_xaml_codebehind"></a>   
## Eventos y el código XAML subyacente  
 La mayoría de las aplicaciones de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] constan de marcado XAML y código subyacente.  En un proyecto, el código XAML se escribe como un archivo `.xaml` y se utiliza un lenguaje de [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)], como [!INCLUDE[TLA#tla_visualb](../../../../includes/tlasharptla-visualb-md.md)] o [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)], para escribir un archivo de código subyacente.  Cuando se compila un archivo XAML como parte de los modelos de aplicaciones y programación de WPF, la ubicación del archivo de código subyacente WPF para cada página XAML se identifica especificando un espacio de nombres y una clase como atributo `x:Class` del elemento raíz de la página XAML.  
  
 En los ejemplos presentados hasta ahora se incluían varios botones, pero ninguno de ellos tenía todavía ningún comportamiento lógico asociado.  El mecanismo primario en el nivel de la aplicación para agregar un comportamiento a un elemento de objeto consiste en utilizar un evento existente de la clase de elemento y escribir un controlador específico para dicho evento que se invocará cuando se provoque éste en tiempo de ejecución.  El nombre del evento y el nombre del controlador que se van a utilizar se especifican en el marcado, mientras que el código que implementa el controlador se define en el código subyacente.  
  
 [!code-xml[XAMLOvwSupport#ButtonWithCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page3.xaml#buttonwithcodebehind)]  
  
 [!code-csharp[XAMLOvwSupport#ButtonWithCodeBehindHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page3.xaml.cs#buttonwithcodebehindhandler)]
 [!code-vb[XAMLOvwSupport#ButtonWithCodeBehindHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/XAMLOvwSupport/VisualBasic/Page1.xaml.vb#buttonwithcodebehindhandler)]  
  
 Tenga en cuenta que el archivo de código subyacente utiliza el espacio de nombres CLR `ExampleNamespace` y declara `ExamplePage` como una clase parcial dentro de dicho espacio de nombres.  Esto es similar al valor de atributo `x:Class` de `ExampleNamespace`.`ExamplePage` que se ha proporcionado en la raíz del marcado.  El compilador de marcado WPF creará automáticamente una clase parcial para cualquier archivo XAML compilado, al derivar una clase del tipo de elemento raíz.  Al proporcionar código subyacente que también define la misma clase parcial, el código resultante se combina dentro del mismo espacio de nombres y la clase de la aplicación compilada.  
  
 Para obtener más información sobre los requisitos para la programación de código subyacente en WPF, vea la sección "Requisitos del código subyacente, los controladores de eventos y las clases parciales" de [Código subyacente y XAML en WPF](../../../../docs/framework/wpf/advanced/code-behind-and-xaml-in-wpf.md).  
  
 Si no desea crear un archivo de código subyacente independiente, también puede insertar el código dentro de un archivo XAML.  Sin embargo, el código insertado es una técnica menos versátil que tiene importantes limitaciones.  Para obtener información detallada, vea [Código subyacente y XAML en WPF](../../../../docs/framework/wpf/advanced/code-behind-and-xaml-in-wpf.md).  
  
### Eventos enrutados  
 Una característica especial de los eventos que es fundamental para [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] es un [evento enrutado](GTMT).  Los eventos enrutados permiten a un elemento controlar un evento generado por otro elemento diferente, siempre que dichos elementos estén relacionados entre sí a través de un árbol.  Al especificar el control de eventos con un atributo XAML, se puede escuchar y controlar el evento enrutado en cualquier elemento, incluidos los elementos que no contienen ese evento concreto en la tabla de miembros de clase.  Esto se consigue calificando el atributo de nombre de evento con el nombre de la clase propietaria.  Por ejemplo, el elemento primario `StackPanel` en el ejemplo de `StackPanel` \/ `Button` actual podría registrar un controlador para el evento de botón <xref:System.Windows.Controls.Primitives.ButtonBase.Click> del elemento secundario especificando el atributo `Button.Click` en el elemento de objeto `StackPanel`, con el nombre del controlador como valor de atributo.  Para obtener más información acerca del funcionamiento de los eventos enrutados, vea [Información general sobre eventos enrutados](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
<a name="x_name_and_xaml_named_elements"></a>   
## Elementos XAML con nombre  
 De forma predeterminada, la instancia de objeto que se crea en un gráfico de objetos al procesar un elemento de objeto XAML no posee un identificador único o una referencia de objeto inherente que se pueda utilizar en el código.  Por el contrario, si se llama a un constructor en el código, casi siempre se utiliza el resultado del constructor para establecer una variable en la instancia creada con objeto de que se pueda hacer referencia a dicha instancia posteriormente en el código.  Para proporcionar acceso normalizado a los objetos creados mediante una definición de marcado, XAML define el [atributo x:Name](../../../../docs/framework/xaml-services/x-name-directive.md).  Es posible establecer el valor del atributo `x:Name` en cualquier elemento de objeto.  En el código subyacente, el identificador elegido es equivalente a una variable de instancia que hace referencia a la instancia creada.  Los elementos con nombre funcionan en todos los sentidos como si fueran instancias de objeto \(el nombre hace referencia a la instancia\) y el código subyacente puede hacer referencia a dichos elementos para controlar las interacciones en tiempo de ejecución dentro de la aplicación.  Esta conexión entre las instancias y el compilador se logra por el compilador de marcado XAML de WPF y más específicamente implica características y modelos como <xref:System.Windows.Markup.IComponentConnector.InitializeComponent%2A> que no se tratarán en este tema.  
  
 Los elementos de código XAML del [nivel de marco de WPF](GTMT) heredan una propiedad <xref:System.Windows.FrameworkElement.Name%2A>, que es equivalente al atributo `x:Name` definido por XAML.  Otros tipos de clases también proporcionan equivalentes en el nivel de propiedad para `x:Name`, que en general también suele definirse como una propiedad `Name`.  En general, si no puede localizar una propiedad `Name` en la tabla de miembros del elemento\/tipo elegido, utilice en su lugar `x:Name`.  Los valores `x:Name` proporcionarán un identificador a un elemento XAML que se puede utilizar en tiempo de ejecución por subsistemas concretos o por métodos de utilidad como <xref:System.Windows.FrameworkElement.FindName%2A>.  
  
 En el ejemplo siguiente se establece <xref:System.Windows.FrameworkElement.Name%2A> en un elemento <xref:System.Windows.Controls.StackPanel>.  A continuación, un controlador en un elemento <xref:System.Windows.Controls.Button> dentro de <xref:System.Windows.Controls.StackPanel> hace referencia al objeto <xref:System.Windows.Controls.StackPanel> mediante su referencia de instancia `buttonContainer` tal y como lo establece <xref:System.Windows.FrameworkElement.Name%2A>.  
  
 [!code-xml[XAMLOvwSupport#NamedE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page7.xaml#namede)]  
[!code-xml[XAMLOvwSupport#NamedE2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page7.xaml#namede2)]  
  
 [!code-csharp[XAMLOvwSupport#NameCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page7.xaml.cs#namecode)]
 [!code-vb[XAMLOvwSupport#NameCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/XAMLOvwSupport/VisualBasic/Page1.xaml.vb#namecode)]  
  
 Al igual que una variable, el nombre XAML de una instancia está regido por un concepto de ámbito con objeto de aplicar los nombres de forma que sean únicos dentro de un ámbito predecible.  El marcado primario que define una página indica un ámbito de nombres de código XAML único, siendo el límite de dicho ámbito el elemento raíz de la página.  Sin embargo, otros orígenes de marcado pueden interactuar con una página en tiempo de ejecución, por ejemplo, los estilos o las plantillas incluidas en los estilos, y dichos orígenes tienen a menudo su propio ámbito de nombres de código XAML que no tiene por qué estar conectado necesariamente con el de la página.  Para obtener más información sobre `x:Name` y los ámbitos de nombres de código XAML, vea <xref:System.Windows.FrameworkElement.Name%2A>, [x:Name \(Directiva\)](../../../../docs/framework/xaml-services/x-name-directive.md) o [Ámbitos de nombres XAML de WPF](../../../../docs/framework/wpf/advanced/wpf-xaml-namescopes.md).  
  
<a name="attached_properties_and_attached_events"></a>   
## Propiedades y eventos asociados  
 XAML incluye una característica de lenguaje que permite especificar ciertas propiedades o eventos en cualquier elemento, independientemente de si la propiedad o el evento existe en las definiciones del tipo para el elemento en el que se establece.  La versión de esta característica para las propiedades se denomina [propiedad asociada](GTMT) y la versión para los eventos se denomina [evento asociado](GTMT).  Conceptualmente, las propiedades y los eventos adjuntos se pueden considerar como miembros globales que se pueden establecer en cualquier elemento \/ instancia de objeto XAML.  Sin embargo, ese elemento \/ clase o infraestructura mayor debe admitir un almacén de propiedades de respaldo para los valores adjuntos.  
  
 Las propiedades adjuntas de código XAML se usan normalmente mediante la sintaxis de atributos.  En la sintaxis de atributos, una propiedad adjunta se especifica con el formato *tipoDePropietario*.*nombreDePropiedad*.  
  
 A primera vista, esto se parece al uso de un elemento de propiedad, pero en este caso el *tipoDePropietario* que se especifica es siempre un tipo distinto del elemento de objeto en el que se establece la propiedad adjunta.  *tipoDePropietario* es el tipo que proporciona los métodos de descriptor de acceso que un procesador XAML requiere para poder obtener o establecer el valor de propiedad adjunto.  
  
 El escenario más común para las propiedades asociadas es permitir a los elementos secundarios enviar un valor de propiedad a su elemento primario.  
  
 En el ejemplo siguiente se muestra la propiedad asociada <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=fullName>.  La clase <xref:System.Windows.Controls.DockPanel> define los descriptores de acceso para <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=fullName> y, por lo tanto, es la propietaria de la propiedad asociada.  La clase <xref:System.Windows.Controls.DockPanel> también incluye la lógica que recorre en iteración sus elementos secundarios y busca en cada uno de ellos un valor establecido de <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=fullName>.  Si se encuentra dicho valor, éste se utiliza durante el diseño para colocar los elementos secundarios.  El uso de la propiedad asociada <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=fullName> y esta función de posición constituyen de hecho el escenario de motivación para la clase <xref:System.Windows.Controls.DockPanel>.  
  
 [!code-xml[XAMLOvwSupport#DockAP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#dockap)]  
  
 En [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], la mayoría de las propiedades adjuntas se implementan también como [propiedades de dependencia](GTMT).  Para obtener información detallada, vea [Información general sobre propiedades asociadas](../../../../docs/framework/wpf/advanced/attached-properties-overview.md).  
  
 Los eventos adjuntos usan un formato de sintaxis de atributos similar: *tipoDePropietario*.*nombreDeEvento*.  Al igual que en los eventos no adjuntos, el valor del atributo para un evento adjunto en código XAML especifica el nombre del método controlador que se invoca cuando se controla el evento en el elemento.  Los usos de eventos adjuntos en código XAML de WPF son menos comunes.  Para obtener más información, vea [Información general sobre eventos adjuntos](../../../../docs/framework/wpf/advanced/attached-events-overview.md).  
  
<a name="base_classes_and_xaml"></a>   
## Tipos base y XAML  
 Debajo del código XAML de WPF y su espacio de nombres XAML existe una colección de tipos que corresponden a los objetos de [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)], así como elementos de marcado para XAML.  Sin embargo, no todas las clases se pueden asignar a elementos.  Las clases abstractas, como <xref:System.Windows.Controls.Primitives.ButtonBase>, y ciertas clases base no abstractas se usan para la herencia en el modelo de objetos de [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)].  Las clases base, incluidas las abstractas, son importantes para el desarrollo de código XAML porque cada uno de los elementos de código XAML concretos hereda miembros de alguna clase base en su jerarquía.  A menudo, estos miembros incluyen propiedades que se pueden establecer como atributos en el elemento o eventos que se pueden controlar.  <xref:System.Windows.FrameworkElement> es la clase base concreta de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en el [nivel de marco WPF](GTMT).  Al diseñar la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], se utilizarán varias clases de forma, de panel, de decorador o de control, que se derivan de <xref:System.Windows.FrameworkElement>.  Una clase base relacionada, <xref:System.Windows.FrameworkContentElement>, admite elementos orientados a documentos que funcionan bien para una presentación de diseño de flujo, utilizando [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] que reflejan deliberadamente las [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] de <xref:System.Windows.FrameworkElement>.  La combinación de atributos en el nivel de elemento y un modelo de objetos de [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] proporciona un conjunto de propiedades comunes que se pueden establecer en la mayoría de los elementos de código XAML concretos, independientemente del tipo de elemento XAML específico y su tipo subyacente.  
  
<a name="xaml_security"></a>   
## Seguridad XAML  
 XAML es un lenguaje de marcado que representa directamente la creación de instancias y la ejecución de objetos.  Por consiguiente, los elementos creados en código XAML tienen la misma capacidad de interactuar con los recursos del sistema \(por ejemplo, el acceso a la red y la E\/S del sistema de archivos\) que el código generado equivalente.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] admite el marco de trabajo de seguridad [!INCLUDE[TLA#tla_cas](../../../../includes/tlasharptla-cas-md.md)] de [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  Esto significa que el contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] que se ejecuta en la zona de Internet tiene permisos de ejecución reducidos. "  El "código XAML dinámico" \(páginas de código XAML no compilado interpretadas en el momento de la carga por un visor de código XAML\) y las [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] se ejecutan normalmente en esta zona de Internet y usan el mismo conjunto de permisos.  No obstante, el código XAML cargado en una aplicación de plena confianza tiene el mismo acceso a los recursos del sistema que la aplicación host.  Para obtener más información, vea [Seguridad de confianza parcial de WPF](../../../../docs/framework/wpf/wpf-partial-trust-security.md).  
  
<a name="loading_xaml_from_code"></a>   
## Cargar XAML desde el código  
 XAML se puede usar para definir la totalidad de la interfaz de usuario, pero a veces también es conveniente definir solo una parte de dicha interfaz en código XAML.  Esta funcionalidad se podría usar para habilitar una personalización parcial, para el almacenamiento local de información, para proporcionar un objeto comercial mediante código XAML o para diversos escenarios posibles.  La clave para estos escenarios es la clase <xref:System.Windows.Markup.XamlReader> y su método <xref:System.Windows.Markup.XamlReader.Load%2A>.  La entrada es un archivo XAML y la salida es un objeto que representa la totalidad del árbol de objetos en tiempo de ejecución que se ha creado a partir de ese marcado.  A continuación, se puede insertar el objeto como una propiedad de otro objeto que ya existe en la aplicación.  Siempre que la propiedad sea una propiedad adecuada en el modelo de contenido que tiene funcionalidades de presentación y que notifica al motor de ejecución que se ha agregado el nuevo contenido a la aplicación, es posible modificar con gran facilidad el contenido de una aplicación en ejecución si se carga código XAML.  Tenga en cuenta que esta función normalmente sólo está disponible en las aplicaciones de plena confianza, debido a las implicaciones de seguridad obvias de la carga de archivos en aplicaciones que se están ejecutando.  
  
<a name="whats_next"></a>   
## Pasos adicionales  
 En este tema se proporciona una introducción básica a la terminología y los conceptos de la sintaxis XAML que se aplica en WPF.  Para obtener más información acerca de los términos utilizados aquí, vea [Detalles de la sintaxis XAML](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md).  
  
 Si aún no lo ha hecho, intente realizar los ejercicios del tutorial [Tutorial: Introducción a WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).  La aplicación centrada en el marcado descrita en el tutorial le ayudará a reforzar muchos de los conceptos descritos en este tema.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] utiliza un modelo de aplicación determinado que está basado en la clase <xref:System.Windows.Application>.  Para obtener información detallada, vea [Información general sobre la administración de aplicaciones](../../../../docs/framework/wpf/app-development/application-management-overview.md).  
  
 [Compilar una aplicación de WPF](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md) le ofrece información más detallada sobre cómo compilar aplicaciones que incluyen código XAML desde la línea de comandos y con [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)].  
  
 [Información general sobre las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md) le ofrece más información sobre la versatilidad de las propiedades en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], e introduce el concepto de [propiedades de dependencia](GTMT).  
  
## Vea también  
 [Detalles de la sintaxis XAML](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md)   
 [Clases XAML y personalizadas para WPF](../../../../docs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)   
 [Características de lenguaje \(x:\) de espacios de nombres XAML](../../../../docs/framework/xaml-services/xaml-namespace-x-language-features.md)   
 [Extensiones XAML de WPF](../../../../docs/framework/wpf/advanced/wpf-xaml-extensions.md)   
 [Información general sobre elementos base](../../../../docs/framework/wpf/advanced/base-elements-overview.md)   
 [Árboles en WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md)