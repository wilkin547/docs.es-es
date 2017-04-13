---
title: "Clases XAML y personalizadas para WPF | Microsoft Docs"
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
  - "clases, clases personalizadas en XAML"
  - "clases personalizadas en XAML"
  - "XAML, clases personalizadas"
ms.assetid: e7313137-581e-4a64-8453-d44e15a6164a
caps.latest.revision: 22
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 21
---
# Clases XAML y personalizadas para WPF
XAML implementados en marcos de [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] admite la capacidad de definir una clase o estructura personalizada en cualquier lenguaje de [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] , y después tiene acceso a esa clase mediante marcado XAML.  Puede usar una mezcla de tipos definidos por el [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] y sus tipos personalizados dentro del mismo archivo de marcado, normalmente asignando los tipos personalizados a un prefijo de espacio de nombres de XAML.  Este tema describe los requisitos que debe satisfacer una clase personalizada para ser utilizable como elemento XAML.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="Custom_Classes_in_Applications_vs__in_Assemblies"></a>   
## Clases personalizadas en aplicaciones o ensamblados  
 Las clases personalizadas que se utilizan en XAML pueden definir de dos maneras distintas: dentro del código subyacente o de otro código que genera la aplicación primaria de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] , o como una clase en un ensamblado independiente, como una aplicación ejecutable o DLL utilizado como una biblioteca de clases.  Cada uno de estos enfoques tiene ventajas y desventajas particulares.  
  
-   La ventaja de crear una biblioteca de clases es que cualquiera de esas clases personalizadas puede compartirse entre muchas posibles aplicaciones diferentes.  Una biblioteca independiente también facilita las versión de las aplicaciones sean más fáciles de controlar, y simplifica la creación de una clase donde el uso previsto de la clase como un elemento raíz en una página XAML.  
  
-   La ventaja de definir las clases personalizadas en la aplicación consiste en que esta técnica es relativamente ligera, y minimiza los problemas de implementación y pruebas que se encuentran al introducir ensamblados independientes además del ejecutable principal de la aplicación.  
  
-   Si se define en el mismo ensamblado o en uno diferente, clases personalizadas deben asignarse entre el espacio de nombres CLR y el espacio de nombres XML para utilizarlo en XAML como elementos.  Vea [Espacios de nombres y asignación de espacios de nombres XAML para WPF](../../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).  
  
<a name="Requirements_for_a_Custom_Class_as_a_XAML_Element"></a>   
## Requisitos para una clase personalizada como elemento XAML  
 Para permitir la creación de instancias como elementos de objeto, la clase debe cumplir los requisitos siguientes:  
  
-   La clase personalizada debe ser pública y admitir un constructor público predeterminado \(sin parámetros\).  \(Vea en la siguiente sección las notas relativas a las estructuras\).  
  
-   Su clase personalizada no debe ser una clase anidada.  Las clases anidadas y el "punto" en su sintaxis de uso de CLR general interfieren con otras características de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y\/o XAML como, por ejemplo, las propiedades adjuntas.  
  
 Además de permitir la sintaxis de elemento de objeto, su definición del objeto también debe habilitar la sintaxis de elemento de propiedad para cualquier otra propiedad pública que admita el objeto como el tipo de valor.  Esto se debe a que ahora es posible crear instancias de un objeto como un elemento de objeto y a que el objeto puede rellenar el valor de elemento de propiedad de tales propiedades.  
  
### Estructuras  
 Las estructuras que se definen como tipos personalizados siempre pueden construirse en XAML en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] . Esto es porque los compiladores de [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] crean implícitamente un constructor predeterminado para una estructura que inicializa todos los valores de propiedad a sus valores predeterminados.  En algunos casos, no es deseable para una estructura el comportamiento predeterminado de construcción o de uso de elementos de objeto.  Esto se puede deber a que la estructura está pensada para rellenar valores y funcionar, desde el punto de vista conceptual, como una unión, cuyos valores contenidos pueden tener interpretaciones mutuamente excluyentes, en cuyo caso ninguna de sus propiedades se podría establecer.  Un ejemplo de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] de este tipo de estructura es <xref:System.Windows.GridLength>.  Generalmente, tales estructuras deberían implementar un convertidor de tipos para que los valores se puedan expresar en forma de atributo y usar las convenciones de cadena que crean las diferentes interpretaciones o modos de los valores de la estructura.  La estructura también debería exponer un comportamiento similar por la construcción del código a través de un constructor no predeterminado.  
  
<a name="Requirements_for_Properties_of_a_Custom_Class_as_XAML"></a>   
## Requisitos para las propiedades de una clase personalizada como atributos XAML  
 Las propiedades deben hacer referencia a un tipo por valor \(tal como un tipo primitivo\) o usar una clase para tipos que tenga un constructor predeterminado o un convertidor de tipos dedicado al que pueda obtener acceso un procesador XAML.  En la implementación de CLR XAML, los procesadores de XAML buscan estos convertidores a través de la compatibilidad nativa con los primitivos del lenguaje o a través de la aplicación de <xref:System.ComponentModel.TypeConverterAttribute> a un tipo o miembro en las definiciones de tipo de respaldo.  
  
 Como alternativa, la propiedad puede hacer referencia a un tipo de clase abstracto o a una interfaz.  Para las clases abstractas o las interfaces, la expectativa del análisis de XAML es que el valor de propiedad deba rellenarse con instancias de clase prácticas que implementen la interfaz, o con instancias de tipos derivadas de la clase abstracta.  
  
 Las propiedades se pueden declarar en una clase abstracta, pero solo se pueden establecer en las clases prácticas derivadas de la clase abstracta.  Esto se debe a que crear el elemento de objeto para la clase requiere un constructor predeterminado público en la clase.  
  
### Sintaxis de atributo con convertidor de tipos  
 Si se proporciona un convertidor de tipos dedicado, con atributos, en el nivel de clase, la conversión de tipos aplicada habilita la sintaxis de atributo para cualquier propiedad que necesita crear instancias de ese tipo.  Un convertidor de tipos no permite el uso de elemento de objeto del tipo; solamente la presencia de un constructor predeterminado para ese tipo habilita el uso de elemento de objeto.  Por consiguiente, las propiedades habilitadas con convertidor de tipos, en general, no son utilizables en sintaxis de propiedad, a menos que el propio tipo admita también la sintaxis de elemento de objeto.  La excepción consiste en que se puede especificar una sintaxis de elemento de propiedad, pero el elemento de propiedad debe contener una cadena.  Ese uso es esencialmente el equivalente a un uso de sintaxis de atributo, realmente; este tipo de uso no es común a menos que se necesite una administración más sólida del espacio en blanco en el valor del atributo.  Por ejemplo, lo siguiente es un uso de elemento de propiedad que toma una cadena y el uso de atributo equivalente:  
  
 [!code-xml[XamlOvwSupport#GoofyTCPE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#goofytcpe)]  
  
 [!code-xml[XamlOvwSupport#GoofyTCPE2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#goofytcpe2)]  
  
 Ejemplos de propiedades donde se permite la sintaxis de atributo sólo de la sintaxis de elementos de propiedad que contiene un elemento de objeto denegados con XAML hay varias propiedades que toman el tipo de <xref:System.Windows.Input.Cursor> .  La clase <xref:System.Windows.Input.Cursor> tiene un objeto <xref:System.Windows.Input.CursorConverter> convertidor de tipos dedicado, pero no expone un constructor predeterminado, por lo que la propiedad <xref:System.Windows.FrameworkElement.Cursor%2A> solamente se puede establecer mediante sintaxis de atributo aunque el tipo <xref:System.Windows.Input.Cursor> real sea un tipo de referencia.  
  
### Convertidores de tipo por propiedad  
 La propia propiedad puede declarar también un convertidor de tipos en el nivel de propiedad.  Esto habilita un "minilenguaje" que crea instancias de objetos del tipo de la propiedad en el propio código, procesando valores de cadena de entrada del atributo como entrada para una operación <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A> basada en el tipo correspondiente.  Esto suele hacerse proporcionar un descriptor de acceso adecuado, y no como único medio para habilitar establecer una propiedad en XAML.  Sin embargo, también es posible utilizar convertidores de tipos para atributos cuando se desee utilizar tipos [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] que no proporcionen un constructor predeterminado ni un convertidor de tipos con atributos.  los ejemplos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] API son ciertas propiedades que toman el tipo de <xref:System.Globalization.CultureInfo> .  En este caso, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] utilizó el tipo existente de[!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)]<xref:System.Globalization.CultureInfo> para mejorar los escenarios de compatibilidad y la migración de dirección que se utilizaron en versiones anteriores de marcos, pero el tipo de <xref:System.Globalization.CultureInfo> no admitía a constructores o a la conversión de tipo necesarios de tipo que se pueda usar como valor de propiedad XAML directamente.  
  
 Siempre que exponga una propiedad que se pueda utilizar en XAML, en particular si está creando controles, deberá considerar la posibilidad de respaldar esa propiedad con una propiedad de dependencia.  Esto es especialmente cierto si se utiliza la implementación existente de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] del procesador XAML, porque puede mejorar el rendimiento utilizando el soporte de <xref:System.Windows.DependencyProperty> .  Una propiedad de dependencia expondrá para la propiedad las características del sistema de propiedades que los usuarios esperen de una propiedad accesible a través de XAML.  Esto incluye características tales como la animación, el enlace de datos y la compatibilidad con estilos.  Para obtener más información, vea [Propiedades de dependencia personalizadas](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md) y [Carga de XAML y propiedades de dependencia](../../../../docs/framework/wpf/advanced/xaml-loading-and-dependency-properties.md).  
  
### Escribir y asignar atributos a un convertidor de tipos  
 A veces, necesitará escribir una clase personalizada derivada de <xref:System.ComponentModel.TypeConverter> para proporcionar conversión de tipos a un tipo de propiedad.  Para obtener instrucciones sobre cómo derivar y crear un convertidor de tipos que admita usos XAML y cómo aplicar el objeto <xref:System.ComponentModel.TypeConverterAttribute>, vea [Clases TypeConverter y XAML](../../../../docs/framework/wpf/advanced/typeconverters-and-xaml.md).  
  
<a name="Requirements_for_Events_of_a_Custom_Class_as_XAML"></a>   
## Requisitos para la sintaxis de atributo del controlador de eventos XAML en los eventos de una clase personalizada  
 Para ser utilizable como un evento [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)], el evento se debe exponer como un evento público en una clase que admita un constructor predeterminado o en una clase abstracta donde se pueda tener acceso al evento en clases derivadas.  Para poder utilizarse cómodamente como un [evento enrutado](GTMT), el evento de [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] debe implementar métodos `add` y `remove` explícitos que agreguen y quiten controladores para la firma de evento [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] y reenvíen esos controladores a los métodos <xref:System.Windows.UIElement.AddHandler%2A> y <xref:System.Windows.UIElement.RemoveHandler%2A>.  Estos métodos agregan o quitan controladores del almacén del controlador de eventos enrutados en la instancia a la que está asociado el evento.  
  
> [!NOTE]
>  Es posible registrar controladores directamente para eventos enrutados utilizando <xref:System.Windows.UIElement.AddHandler%2A>, así como no definir deliberadamente un evento [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] que exponga el [evento enrutado](GTMT).  Esto no suele ser recomendable porque el evento no habilitará la sintaxis de atributo de XAML para asociar controladores, y la clase resultante ofrecerá una vista menos transparente XAML de las capacidades de ese tipo.  
  
<a name="Collection_Properties"></a>   
## Escribir propiedades de colección  
 Las propiedades cuyo tipo es una colección tienen una sintaxis XAML que permite especificar los objetos que se agregan a la colección.  Esta sintaxis tiene dos características notables.  
  
-   El objeto que es el objeto de colección no necesita especificarse en la sintaxis de elemento de objeto.  La presencia de ese tipo de colección es implícita cuando se especifica una propiedad en XAML que tome un tipo de colección.  
  
-   Los elementos secundarios de la propiedad de colección del marcado se procesan para convertirse en miembros de la colección.  Normalmente, el acceso del código a los miembros de una colección se realiza a través de métodos de lista y diccionario, tales como `Add`, o mediante un indizador.  Pero la sintaxis de XAML no admite los métodos o indizadores \(excepción: XAML 2009 puede admitir métodos, pero con XAML 2009 limita los usos posibles de WPF; vea [Características del lenguaje XAML 2009](../../../../docs/framework/xaml-services/xaml-2009-language-features.md)\).  Las colecciones son obviamente un requisito muy común para compilar un árbol de elementos y se necesita alguna manera de rellenarlas en XAML declarativo.  Por consiguiente, los elementos secundarios de una propiedad de colección se procesan agregándolos a la colección que es el valor de tipo de la propiedad de colección.  
  
 La implementación de los servicios XAML de.NET Framework y el procesador XAML de WPF utiliza así la siguiente definición de lo que constituye una propiedad de colección.  El tipo de propiedad de la propiedad debe implementar una de las opciones siguientes:  
  
-   Implementa <xref:System.Collections.IList>.  
  
-   Implementa <xref:System.Collections.IDictionary> o el equivalente genérico \(<xref:System.Collections.Generic.IDictionary%602>\).  
  
-   Deriva de <xref:System.Array> \(para obtener más información sobre las matrices en XAML, vea [x:Array \(Extensión de marcado\)](../../../../docs/framework/xaml-services/x-array-markup-extension.md).\)  
  
-   Implementa <xref:System.Windows.Markup.IAddChild> \(una interfaz definida por [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\).  
  
 Cada uno de estos tipos de CLR tiene un método de `Add` , utilizado por el procesador XAML para agregar elementos a la colección subyacente al crear el gráfico de objetos.  
  
> [!NOTE]
>  `List` e interfaces genéricos de `Dictionary` \(<xref:System.Collections.Generic.IList%601> y <xref:System.Collections.Generic.IDictionary%602>\) no se admiten para la detección de la colección el procesador de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]XAML.  Sin embargo, puede utilizar <xref:System.Collections.Generic.List%601> como una clase base, ya que implementa directamente <xref:System.Collections.IList> o <xref:System.Collections.Generic.Dictionary%602>, ya que ésta implementa directamente <xref:System.Collections.IDictionary>.  
  
 Al declarar una propiedad que toma una colección, tenga cuidado con el modo en el que se inicializa ese valor de propiedad en las nuevas instancias del tipo.  Si no está implementando la propiedad como una propiedad de dependencia, es aconsejable hacer que la propiedad utilice un campo de respaldo que llame al constructor del tipo de colección.  Si la propiedad es una propiedad de dependencia, quizá necesite inicializar la propiedad de colección como parte del constructor de tipo predeterminado.  Esto se debe a que una propiedad de dependencia toma su valor predeterminado de los metadatos y, normalmente, no es conveniente que el valor inicial de una propiedad de colección sea una colección estática compartida.  Debería haber una instancia de colección por cada instancia del tipo contenedor.  Para obtener más información, vea [Propiedades de dependencia personalizadas](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md).  
  
 Puede implementar un tipo de colección personalizado para la propiedad de colección.  Debido al tratamiento de propiedad de colección implícito, no es necesario que el tipo de colección personalizado proporcione un constructor predeterminado para que sea utilizado implícitamente en XAML.  Sin embargo, puede proporcionar un constructor predeterminado para el tipo de colección.  Esta puede ser una práctica que vale la pena.  A menos que proporcione un constructor predeterminado, no puede declarar explícitamente la colección como un elemento de objeto.  Es posible que algunos autores de marcado prefieran considerar la colección explícita como una cuestión de estilo de marcado.  Además, un constructor predeterminado puede simplificar los requisitos de inicialización al crear nuevos objetos que utilicen el tipo de colección como un valor de propiedad.  
  
<a name="XAMLCONtent"></a>   
## Declarar propiedades de contenido XAML  
 El lenguaje XAML define el concepto de una propiedad de contenido de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  Cada clase utilizable en la sintaxis de objeto puede tener exactamente una propiedad de contenido XAML.  Para declarar una propiedad como propiedad de contenido XAML de la clase, aplique <xref:System.Windows.Markup.ContentPropertyAttribute> como parte de la definición de clase.  Especifique el nombre de la propiedad de contenido XAML en cuestión como valor de <xref:System.Windows.Markup.ContentPropertyAttribute.Name%2A> en el atributo.  La propiedad se especifica como una cadena por nombre, no como construcción de reflexión como<xref:System.Reflection.PropertyInfo>.  
  
 Puede especificar una propiedad de colección como propiedad de contenido XAML.  El resultado es un uso para esa propiedad mediante la cual el elemento de objeto puede tener uno o más elementos secundarios, sin elementos de objeto de colección intermedios ni etiquetas de elemento de propiedad.  Estos elementos se tratan entonces como valor de la propiedad de contenido XAML y se agregan a la instancia de respaldo de la colección.  
  
 Algunas propiedades existentes de contenido de XAML utilizan el tipo de propiedad de `Object`.  Esto permite que una propiedad de contenido XAML tome valores primitivos, como un valor de tipo <xref:System.String>, así como un valor de objeto de referencia único.  Si sigue este modelo, el tipo será responsable de la determinación de tipo, así como del control de los tipos posibles.  La razón típica para un tipo de contenido <xref:System.Object> es admitir tanto un medio simple para agregar contenido de objetos en forma de cadena \(que recibe un tratamiento de presentación predeterminado\) como un medio avanzado de agregar contenido de objetos que especifique una presentación no predeterminada o datos adicionales.  
  
<a name="Serializing"></a>   
## Serializar XAML  
 En algunos escenarios, tales como la creación de controles, quizá desee asegurarse de que toda representación de objeto que se puede crear instancias en XAML también pueda ser serializado a marcado equivalente de XAML.  Los requisitos de serialización no se describen en este tema.  Vea [Información general sobre la creación de controles](../../../../docs/framework/wpf/controls/control-authoring-overview.md) y [Árbol de elementos y serialización](../../../../docs/framework/wpf/advanced/element-tree-and-serialization.md).  
  
## Vea también  
 [Información general sobre XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)   
 [Propiedades de dependencia personalizadas](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)   
 [Información general sobre la creación de controles](../../../../docs/framework/wpf/controls/control-authoring-overview.md)   
 [Información general sobre elementos base](../../../../docs/framework/wpf/advanced/base-elements-overview.md)   
 [Carga de XAML y propiedades de dependencia](../../../../docs/framework/wpf/advanced/xaml-loading-and-dependency-properties.md)