---
title: Clases XAML y personalizadas para WPF
ms.date: 03/30/2017
helpviewer_keywords:
- custom classes in XAML [WPF]
- XAML [WPF], custom classes
- classes [WPF], custom classes in XAML
ms.assetid: e7313137-581e-4a64-8453-d44e15a6164a
ms.openlocfilehash: aa2dd7a5c30894f85ed1d4aae0228b76ece3c005
ms.sourcegitcommit: f8c36054eab877de4d40a705aacafa2552ce70e9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/31/2019
ms.locfileid: "75559877"
---
# <a name="xaml-and-custom-classes-for-wpf"></a>Clases XAML y personalizadas para WPF
XAML tal como se implementa en marcos de Common Language Runtime (CLR) admite la capacidad de definir una clase o estructura personalizada en cualquier lenguaje de Common Language Runtime (CLR) y, a continuación, tener acceso a esa clase mediante el marcado XAML. Puede usar una mezcla de tipos definidos por [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] y sus tipos personalizados dentro del mismo archivo de marcado, normalmente asignando los tipos personalizados a un prefijo de espacio de nombres de XAML. En este tema se describen los requisitos que debe satisfacer una clase personalizada para que se pueda usar como elemento XAML.  

<a name="Custom_Classes_in_Applications_vs__in_Assemblies"></a>   
## <a name="custom-classes-in-applications-or-assemblies"></a>Clases personalizadas en aplicaciones o ensamblados  
 Las clases personalizadas que se usan en XAML pueden definirse de dos maneras distintas: dentro del código subyacente o de otro código que genera la aplicación primaria de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], o como una clase en un ensamblado independiente, como una aplicación ejecutable o DLL usado como una biblioteca de clases. Cada uno de estos enfoques tiene ventajas y desventajas determinadas.  
  
- La ventaja de crear una biblioteca de clases es que cualquiera de esas clases personalizadas puede compartirse entre muchas posibles aplicaciones diferentes. Una biblioteca independiente también facilita que las versiones de las aplicaciones sean más fáciles de controlar, y simplifica la creación de una clase donde el uso previsto de la clase es como un elemento raíz en una página XAML.  
  
- La ventaja de definir las clases personalizadas en la aplicación consiste en que esta técnica es relativamente ligera, y minimiza los problemas de implementación y pruebas que se encuentran al especificar ensamblados independientes además del ejecutable principal de la aplicación.  
  
- Si se define en el mismo ensamblado o en uno diferente, las clases personalizadas deben asignarse entre el espacio de nombres CLR y el espacio de nombres XML para usarlo en XAML como elementos. Vea [Espacios de nombres y asignación de espacios de nombres XAML para WPF](xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).  
  
<a name="Requirements_for_a_Custom_Class_as_a_XAML_Element"></a>   
## <a name="requirements-for-a-custom-class-as-a-xaml-element"></a>Requisitos para una clase personalizada como elemento XAML  
 Para permitir la creación de instancias como elementos de objeto, la clase debe cumplir los requisitos siguientes:  
  
- La clase personalizada debe ser pública y admitir un constructor público predeterminado (sin parámetros). (Vea en la siguiente sección las notas relativas a las estructuras).  
  
- Su clase personalizada no debe ser una clase anidada. Las clases anidadas y el "punto" en su sintaxis de uso de CLR general interfieren con otras características de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] o XAML como las propiedades adjuntas.  
  
 Además de permitir la sintaxis de elemento de objeto, su definición del objeto también debe habilitar la sintaxis de elemento de propiedad para cualquier otra propiedad pública que admita el objeto como el tipo de valor. Esto se debe a que ahora es posible crear instancias de un objeto como un elemento de objeto y a que puede rellenar el valor de elemento de propiedad de dicha propiedad.  
  
### <a name="structures"></a>Estructuras  
 Las estructuras que se definen como tipos personalizados siempre se pueden construir en XAML en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Esto se debe a que los compiladores de CLR crean implícitamente un constructor sin parámetros para una estructura que inicializa todos los valores de propiedad a sus valores predeterminados. En algunos casos, no es deseable para una estructura el comportamiento predeterminado de construcción o el uso de elementos de objeto. Esto se puede deber a que la estructura está pensada para rellenar valores y funcionar, desde el punto de vista conceptual, como una unión, cuyos valores contenidos pueden tener interpretaciones mutuamente excluyentes, por lo que ninguna de sus propiedades se podría establecer. Una [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ejemplo de este tipo de estructura es <xref:System.Windows.GridLength>. Generalmente, tales estructuras deberían implementar un convertidor de tipos para que los valores se puedan expresar en forma de atributo y usar las convenciones de cadena que crean las diferentes interpretaciones o modos de los valores de la estructura. La estructura también debe exponer un comportamiento similar para la construcción del código a través de un constructor sin parámetros.  
  
<a name="Requirements_for_Properties_of_a_Custom_Class_as_XAML"></a>   
## <a name="requirements-for-properties-of-a-custom-class-as-xaml-attributes"></a>Requisitos para las propiedades de una clase personalizada como atributos XAML  
 Las propiedades deben hacer referencia a un tipo por valor (como un primitivo) o usar una clase para el tipo que tiene un constructor sin parámetros o un convertidor de tipos dedicado al que un procesador XAML puede tener acceso. En la implementación XAML de CLR, los procesadores XAML encuentran tales convertidores a través de la compatibilidad nativa con primitivas del lenguaje o a través de la aplicación de <xref:System.ComponentModel.TypeConverterAttribute> a un tipo o miembro en las definiciones de tipo de respaldo.  
  
 De manera alternativa, la propiedad puede hacer referencia a un tipo de clase abstracta o a una interfaz. Para las clases abstractas o las interfaces, la expectativa del análisis de XAML es que el valor de propiedad debe rellenarse con instancias de clase prácticas que implementen la interfaz, o con instancias de tipos derivadas de la clase abstracta.  
  
 Las propiedades se pueden declarar en una clase abstracta, pero solo se pueden establecer en las clases prácticas derivadas de la clase abstracta. Esto se debe a que la creación del elemento de objeto para la clase requiere un constructor sin parámetros público en la clase.  
  
### <a name="typeconverter-enabled-attribute-syntax"></a>Sintaxis de atributo con convertidor de tipos  
 Si proporciona un convertidor de tipos dedicado, con atributos, en el nivel de clase, la conversión de tipos aplicada habilita la sintaxis de atributo para cualquier propiedad que necesita crear instancias de ese tipo. Un convertidor de tipos no habilita el uso de elementos de objeto del tipo; solo la presencia de un constructor sin parámetros para ese tipo habilita el uso de elementos de objeto. Por consiguiente, las propiedades habilitadas con convertidor de tipos, en general, no se usan en sintaxis de propiedad, a menos que el propio tipo admita también la sintaxis de elemento de objeto. La excepción consiste en que se puede especificar una sintaxis de elemento de propiedad, pero el elemento de propiedad debe contener una cadena. Ese uso es realmente equivalente a un uso de la sintaxis de atributo, y dicho uso no es común a menos que sea necesario un control de espacio en blanco más sólido del valor del atributo. Por ejemplo, lo siguiente es un uso de elemento de propiedad que toma una cadena y el uso de atributo equivalente:  
  
 [!code-xaml[XamlOvwSupport#GoofyTCPE](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#goofytcpe)]  
  
 [!code-xaml[XamlOvwSupport#GoofyTCPE2](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#goofytcpe2)]  
  
 Ejemplos de propiedades en las que se permite la sintaxis de atributo, pero la sintaxis de elementos de propiedad que contiene un elemento de objeto no se permite a través de XAML son varias propiedades que toman el tipo de <xref:System.Windows.Input.Cursor>. La clase <xref:System.Windows.Input.Cursor> tiene un convertidor de tipos dedicado <xref:System.Windows.Input.CursorConverter>, pero no expone un constructor sin parámetros, por lo que la propiedad <xref:System.Windows.FrameworkElement.Cursor%2A> solo se puede establecer a través de la sintaxis de atributo, aunque el tipo de <xref:System.Windows.Input.Cursor> real sea un tipo de referencia.  
  
### <a name="per-property-type-converters"></a>Convertidores de tipo por propiedad  
 De manera alternativa, la propia propiedad puede declarar un convertidor de tipos en el nivel de propiedad. Esto habilita un "minilenguaje" que crea instancias de objetos del tipo de la propiedad insertada, procesando los valores de cadena entrantes del atributo como entrada para una operación de <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A> basada en el tipo adecuado. Normalmente esto se realiza para proporcionar un descriptor de acceso adecuado, y no como único medio para habilitar el establecimiento de una propiedad en XAML. Sin embargo, también es posible usar convertidores de tipos para los atributos en los que desea utilizar tipos CLR existentes que no proporcionan un constructor sin parámetros o un convertidor de tipos con atributos. Algunos ejemplos de la API de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] son ciertas propiedades que toman el tipo de <xref:System.Globalization.CultureInfo>. En este caso, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] utilizó el tipo de <xref:System.Globalization.CultureInfo> de Microsoft .NET Framework existente para mejorar la compatibilidad y los escenarios de migración que se usaron en versiones anteriores de marcos de trabajo, pero el tipo de <xref:System.Globalization.CultureInfo> no admitía los constructores necesarios o la conversión de tipo de nivel de tipo para que se pueda usar directamente como valor de propiedad XAML.  
  
 Siempre que exponga una propiedad que se pueda usar en XAML, en particular si es un creador de controles, deberá considerar la posibilidad de respaldar esa propiedad con una propiedad de dependencia. Esto es especialmente cierto si usa la implementación de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] existente del procesador XAML, ya que puede mejorar el rendimiento mediante <xref:System.Windows.DependencyProperty> respaldo. Una propiedad de dependencia expondrá para la propiedad las características del sistema de propiedades que los usuarios esperan de una propiedad accesible a través de XAML. Esto incluye características tales como la animación, el enlace de datos y la compatibilidad con estilos. Para obtener más información, vea [Propiedades de dependencia personalizadas](custom-dependency-properties.md) y [Carga de XAML y propiedades de dependencia](xaml-loading-and-dependency-properties.md).  
  
### <a name="writing-and-attributing-a-type-converter"></a>Escribir y asignar atributos a un convertidor de tipos  
 En ocasiones, tendrá que escribir una clase derivada de <xref:System.ComponentModel.TypeConverter> personalizada para proporcionar la conversión de tipos para el tipo de propiedad. Para obtener instrucciones sobre cómo derivar y crear un convertidor de tipos que admita los usos de XAML y cómo aplicar el <xref:System.ComponentModel.TypeConverterAttribute>, vea [clases TypeConverter y XAML](typeconverters-and-xaml.md).  
  
<a name="Requirements_for_Events_of_a_Custom_Class_as_XAML"></a>   
## <a name="requirements-for-xaml-event-handler-attribute-syntax-on-events-of-a-custom-class"></a>Requisitos para la sintaxis de atributo del controlador de eventos XAML en los eventos de una clase personalizada  
 Para que se pueda usar como un evento CLR, el evento se debe exponer como un evento público en una clase que admita un constructor sin parámetros o en una clase abstracta en la que se pueda tener acceso al evento en las clases derivadas. Para que se pueda usar de forma cómoda como un evento enrutado, el evento CLR debe implementar métodos `add` y `remove` explícitos, que agregan y quitan Controladores para la firma de eventos CLR y reenvían esos controladores a los métodos <xref:System.Windows.UIElement.AddHandler%2A> y <xref:System.Windows.UIElement.RemoveHandler%2A>. Estos métodos agregan o quitan controladores del almacén del controlador de eventos enrutados en la instancia a la que está asociado el evento.  
  
> [!NOTE]
> Es posible registrar controladores directamente para eventos enrutados mediante <xref:System.Windows.UIElement.AddHandler%2A>y no definir deliberadamente un evento CLR que exponga el evento enrutado. Esto no suele ser recomendable porque el evento no habilitará la sintaxis de atributo de XAML para asociar controladores, y la clase resultante ofrecerá una vista menos transparente XAML de las capacidades de ese tipo.  
  
<a name="Collection_Properties"></a>   
## <a name="writing-collection-properties"></a>Escribir propiedades de colección  
 Las propiedades cuyo tipo es una colección tienen una sintaxis XAML que le permite especificar los objetos que se agregan a la colección. Esta sintaxis tiene dos características notables.  
  
- El objeto que es el objeto de colección no necesita especificarse en la sintaxis de elemento de objeto. La presencia de ese tipo de colección es implícita cuando se especifica una propiedad en XAML que toma un tipo de colección.  
  
- Los elementos secundarios de la propiedad de colección del marcado se procesan para convertirse en miembros de la colección. Normalmente, el acceso del código a los miembros de una colección se realiza a través de métodos de lista y diccionario, tales como `Add`, o mediante un indexador. Pero la sintaxis de XAML no admite los métodos o indexadores (excepción: XAML 2009 puede admitir métodos, pero con XAML 2009 limita los usos posibles de WPF; vea [Características del lenguaje XAML 2009](../../../desktop-wpf/xaml-services/xaml-2009-language-features.md)). Las colecciones son obviamente un requisito muy común para compilar un árbol de elementos y necesita alguna manera de rellenarlas en XAML declarativo. Por consiguiente, los elementos secundarios de una propiedad de colección se procesan agregándolos a la colección que es el valor de tipo de la propiedad de colección.  
  
 La implementación de los servicios XAML de.NET Framework y el procesador XAML de WPF usan así la siguiente definición de lo que constituye una propiedad de colección. El tipo de propiedad de la propiedad debe implementar una de las opciones siguientes:  
  
- Implementa <xref:System.Collections.IList>.  
  
- Implementa <xref:System.Collections.IDictionary> o el equivalente genérico (<xref:System.Collections.Generic.IDictionary%602>).  
  
- Deriva de <xref:System.Array> (para obtener más información sobre las matrices en XAML, vea la [extensión de marcado x:Array](../../../desktop-wpf/xaml-services/xarray-markup-extension.md)).  
  
- Implementa <xref:System.Windows.Markup.IAddChild> (una interfaz definida por [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]).  
  
 Cada uno de estos tipos de CLR tiene un método de `Add`, usado por el procesador XAML para agregar elementos a la colección subyacente al crear el gráfico de objetos.  
  
> [!NOTE]
> El procesador XAML de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] no admite las interfaces genéricas `List` y `Dictionary` (<xref:System.Collections.Generic.IList%601> y <xref:System.Collections.Generic.IDictionary%602>) para la detección de colecciones. Sin embargo, puede usar la clase <xref:System.Collections.Generic.List%601> como una clase base, porque implementa <xref:System.Collections.IList> directamente o <xref:System.Collections.Generic.Dictionary%602> como una clase base, porque implementa <xref:System.Collections.IDictionary> directamente.  
  
 Al declarar una propiedad que toma una colección, tenga cuidado con el modo en el que se inicializa ese valor de propiedad en las nuevas instancias del tipo. Si no está implementando la propiedad como una propiedad de dependencia, es aconsejable hacer que la propiedad use un campo de respaldo que llame al constructor del tipo de colección. Si la propiedad es una propiedad de dependencia, quizá necesite inicializar la propiedad de colección como parte del constructor de tipo predeterminado. Esto se debe a que una propiedad de dependencia toma su valor predeterminado de los metadatos y, normalmente, no es conveniente que el valor inicial de una propiedad de colección sea una colección estática compartida. Debería haber una instancia de colección por cada instancia del tipo contenedor. Para más información, consulte [Propiedades de dependencia personalizadas](custom-dependency-properties.md).  
  
 Puede implementar un tipo de colección personalizado para la propiedad de colección. Debido al tratamiento de propiedades de colección implícita, el tipo de colección personalizada no necesita proporcionar un constructor sin parámetros para que se pueda usar implícitamente en XAML. Sin embargo, opcionalmente, puede proporcionar un constructor sin parámetros para el tipo de colección. Esta puede ser una práctica útil. A menos que se proporcione un constructor sin parámetros, no se puede declarar explícitamente la colección como un elemento de objeto. Es posible que algunos autores de marcado prefieran considerar la colección explícita como una cuestión de estilo de marcado. Además, un constructor sin parámetros puede simplificar los requisitos de inicialización al crear nuevos objetos que utilicen el tipo de colección como un valor de propiedad.  
  
<a name="XAMLCONtent"></a>   
## <a name="declaring-xaml-content-properties"></a>Declarar propiedades de contenido XAML  
 El lenguaje XAML define el concepto de una propiedad de contenido de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Cada clase que se puede usar en la sintaxis de objeto puede tener exactamente una propiedad de contenido XAML. Para declarar una propiedad para que sea la propiedad de contenido XAML de la clase, aplique el <xref:System.Windows.Markup.ContentPropertyAttribute> como parte de la definición de clase. Especifique el nombre de la propiedad de contenido XAML previsto como <xref:System.Windows.Markup.ContentPropertyAttribute.Name%2A> en el atributo. La propiedad se especifica como una cadena por nombre, no como una construcción de reflexión como <xref:System.Reflection.PropertyInfo>.  
  
 Puede especificar una propiedad de colección para que sea la propiedad de contenido XAML. El resultado es un uso para esa propiedad mediante la cual el elemento de objeto puede tener uno o más elementos secundarios, sin elementos de objeto de colección intermedios ni etiquetas de elemento de propiedad. Estos elementos se tratan entonces como el valor de la propiedad de contenido XAML y se agregan a la instancia de respaldo de la colección.  
  
 Algunas propiedades existentes de contenido de XAML usan el tipo de propiedad de `Object`. Esto permite que una propiedad de contenido XAML pueda tomar valores primitivos, como un <xref:System.String>, así como tomar un valor de objeto de referencia único. Si sigue este modelo, el tipo será responsable de la determinación de tipo, así como del control de los tipos posibles. La razón típica para un tipo de contenido <xref:System.Object> es admitir un medio sencillo de agregar contenido de objeto como una cadena (que recibe un tratamiento de presentación predeterminado) o un medio avanzado de agregar contenido de objetos que especifica una presentación no predeterminada o datos adicionales.  
  
<a name="Serializing"></a>   
## <a name="serializing-xaml"></a>Serializar XAML  
 En determinados escenarios, como si es un creador de controles, quizá también quiera asegurarse de que cualquier representación de objeto de la que se pueda crear una instancia en XAML también pueda serializarse de nuevo al marcado equivalente de XAML. Los requisitos de serialización no se describen en este tema. Vea [Información general sobre la creación de controles](../controls/control-authoring-overview.md) y [Árbol de elementos y serialización](element-tree-and-serialization.md).  
  
## <a name="see-also"></a>Vea también

- [Información general sobre XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Propiedades de dependencia personalizadas](custom-dependency-properties.md)
- [Información general sobre la creación de controles](../controls/control-authoring-overview.md)
- [Información general sobre elementos base](base-elements-overview.md)
- [Carga de XAML y propiedades de dependencia](xaml-loading-and-dependency-properties.md)
