---
title: Información general sobre los convertidores de tipos para XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], type converters
- XAML [XAML Services], TypeConverter
- type conversion for XAML [XAML Services]
ms.assetid: 51a65860-efcb-4fe0-95a0-1c679cde66b7
ms.openlocfilehash: c3c69aebacd140a14e74545d601c0207cb8de681
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432873"
---
# <a name="overview-of-type-converters-for-xaml"></a>Descripción general de los convertidores de tipos para XAML

Los convertidores de tipos proporcionan la lógica de un sistema de escritura de objetos que convierte una cadena de marcado XAML en objetos concretos en un gráfico de objetos. En los servicios XAML de .NET, el convertidor <xref:System.ComponentModel.TypeConverter>de tipos debe ser una clase que deriva de . Algunos convertidores también admiten la ruta de acceso de guardado de XAML y se pueden usar para serializar un objeto en forma de cadena en el marcado de serialización. En este tema se describe cómo y cuándo se invocan convertidores de tipos en XAML y se incluyen consejos de implementación para los reemplazos de método de <xref:System.ComponentModel.TypeConverter>.

## <a name="type-conversion-concepts"></a>Conceptos de la conversión de tipos

En las secciones siguientes se explican conceptos básicos sobre cómo XAML usa cadenas y cómo los escritores de objetos de los servicios XAML de .NET usan convertidores de tipos para procesar algunos de los valores de cadena que se encuentran en un origen XAML.

### <a name="xaml-and-string-values"></a>Valores de cadena y XAML

Cuando se establece un valor de atributo en un archivo XAML, el tipo inicial de ese valor es una cadena en sentido general y un valor de atributo de cadena desde el punto de vista de XML. Incluso otros primitivos, como <xref:System.Double> son cadenas inicialmente para un procesador XAML.

En la mayoría de los casos, un procesador XAML necesita dos fragmentos de información para procesar un valor de atributo. El primer fragmento de información es el tipo de valor de la propiedad que se va a establecer. Cualquier cadena que defina un valor de atributo y que se procese en XAML se tiene que convertir o resolver en última instancia en un valor de ese tipo. Si el valor es un primitivo que el analizador XAML entiende (por ejemplo, un valor numérico), se tratará de convertir la cadena directamente. Si el valor del atributo hace referencia a una enumeración, se buscará un nombre en la cadena proporcionada que coincida con una constante con nombre en esa enumeración. Si el valor no es un primitivo entendido por el analizador o un nombre constante de una enumeración, el tipo aplicable debe ser capaz de proporcionar un valor o una referencia que se base en una cadena convertida.

> [!NOTE]
> Las directivas de lenguaje XAML no usan convertidores de tipos.

### <a name="type-converters-and-markup-extensions"></a>Convertidores de tipos y extensiones de marcado

Los usos de extensiones de marcado han de controlarse con un procesador XAML antes de buscar tipos de propiedades y otras consideraciones. Por ejemplo, si una propiedad que se establece como un atributo tiene normalmente una conversión de tipos, pero en un caso determinado se establece por medio de un uso de extensión de marcado, el comportamiento de la extensión de marcado se procesa primero. Una situación común donde una extensión de marcado es necesaria es a la hora de hacer referencia a un objeto que ya existe. En este escenario, un convertidor de tipos sin estado solamente puede generar una nueva instancia, algo que puede no ser deseable. Para más información sobre las extensiones de marcado, vea [Markup Extensions for XAML Overview](markup-extensions-overview.md).

### <a name="native-type-converters"></a>Convertidores de tipos nativos

En las implementaciones de servicios XAML de Windows Presentation Foundation (WPF) y .NET, hay ciertos tipos CLR que tienen control de conversión de tipos nativo. Sin embargo, esos tipos CLR no se consideran convencionalmente como primitivos. Un ejemplo de este tipo es <xref:System.DateTime>. Una razón para esto es el modo en que la arquitectura de .NET Framework funciona: el tipo <xref:System.DateTime> se define en mscorlib, la biblioteca más básica de .NET. <xref:System.DateTime>no se permite que se atribuya con un atributo<xref:System.ComponentModel.TypeConverterAttribute> que proviene de otro ensamblado que introduce una dependencia (es de System). Por lo tanto, no se puede admitir el mecanismo de detección de convertidor de tipos habitual mediante la atribución. En su lugar, el analizador XAML tiene una lista de tipos que necesitan procesamiento nativo y los procesa de manera similar a como lo hacen los primitivos genuinos. En el caso de <xref:System.DateTime>, este procesamiento conlleva llamar a <xref:System.DateTime.Parse%2A>.

## <a name="implementing-a-type-converter"></a>Implementación de un convertidor de tipos

En las siguientes secciones se describe la API de la clase <xref:System.ComponentModel.TypeConverter> .

### <a name="typeconverter"></a>TypeConverter

En Servicios XAML de .NET, todos los convertidores de tipos que <xref:System.ComponentModel.TypeConverter>se usan con fines XAML son clases que derivan de la clase base. La clase <xref:System.ComponentModel.TypeConverter> ya estaba en versiones de .NET Framework previas a la existencia de XAML; uno de los escenarios de <xref:System.ComponentModel.TypeConverter> originales era proporcionar la conversión de cadenas a los editores de propiedades de los diseñadores visuales.

Para XAML, el rol de <xref:System.ComponentModel.TypeConverter> se amplía. Para los propósitos de XAML, <xref:System.ComponentModel.TypeConverter> es la clase base que proporciona compatibilidad con determinadas conversiones a cadena y desde cadena. La conversión desde cadena permite analizar un valor de atributo de cadena desde XAML. En cuanto a la conversión a cadena, puede permitir el procesamiento de un valor de tiempo de ejecución de una propiedad de objeto determinado de vuelta a un atributo en XAML para su serialización.

<xref:System.ComponentModel.TypeConverter> define a cuatro miembros que son importantes para convertir a cadena y desde cadena con fines de procesamiento de XAML:

- <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A>

- <xref:System.ComponentModel.TypeConverter.CanConvertFrom%2A>

- <xref:System.ComponentModel.TypeConverter.ConvertTo%2A>

- <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A>

De estos miembros, el método más importante es <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A>, que convierte la cadena de entrada en el tipo de objeto necesario. El método <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A> se puede implementar para convertir una gama más amplia de tipos en el tipo de destino previsto del convertidor. Por lo tanto, se puede utilizar con fines que van más allá de XAML, como admitir conversiones en tiempo de ejecución. Con todo, en el uso de XAML, solamente es importante la ruta de código que puede procesar una entrada <xref:System.String> .

El segundo método más <xref:System.ComponentModel.TypeConverter.ConvertTo%2A>importante es . Si una aplicación se convierte en una representación de marcado (por <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> ejemplo, si se guarda en XAML como un archivo), está implicada en el escenario más grande de un escritor de texto XAML para generar una representación de marcado. En tal caso, la ruta de acceso de código importante para XAML es cuando el autor de la llamada pasa un `destinationType` de <xref:System.String>.

<xref:System.ComponentModel.TypeConverter.CanConvertTo%2A> y <xref:System.ComponentModel.TypeConverter.CanConvertFrom%2A> son métodos de compatibilidad que se usan cuando un servicio consulta las capacidades de la implementación de <xref:System.ComponentModel.TypeConverter> . Estos métodos se tienen que implementar para obtener `true` en los casos específicos de tipo que los métodos de conversión equivalentes de su convertidor admiten. Para los propósitos de XAML, esto suele traducirse en el tipo <xref:System.String> .

### <a name="culture-information-and-type-converters-for-xaml"></a>Información de referencia cultural y convertidores de tipos para XAML

Cada implementación de <xref:System.ComponentModel.TypeConverter> puede interpretar de manera única lo que es una cadena válida para una conversión y, también, puede usar o ignorar la descripción del tipo pasado como parámetros. Una consideración importante para la conversión de tipos de referencia cultural y XAML es la siguiente: aunque XAML admite el uso de cadenas localizables como valores de atributo, estas cadenas localizables no se pueden usar como entrada del convertidor de tipos con determinados requisitos de referencia cultural. Esta limitación obedece a que los convertidores de tipos de los valores de atributo XAML conllevan un comportamiento de procesamiento XAML de lenguaje obligatoriamente fijo que usa la referencia cultural `en-US` . Para obtener más información acerca de los motivos de diseño de esta restricción, vea la especificación del lenguaje XAML ([\[MS-XAML\]](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))) o [WPF Globalization and Localization Overview](../../framework/wpf/advanced/wpf-globalization-and-localization-overview.md).

Un ejemplo donde la referencia cultural puede ser un problema son algunas referencias culturales que usan una coma en lugar de un punto como delimitador de separador decimal para los números en forma de cadena. Este uso entra en conflicto con el comportamiento de muchos convertidores de tipos existentes, que consiste en usar una coma como delimitador. Pasar una referencia cultural por `xml:lang` en el XAML adyacente no soluciona el problema.

### <a name="implementing-convertfrom"></a>Implementación de ConvertFrom

Para ser igual de utilizable que una implementación de <xref:System.ComponentModel.TypeConverter> que admite XAML, el método <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A> para ese convertidor tiene que aceptar una cadena como parámetro `value` . Si la cadena tiene un formato válido y la implementación de <xref:System.ComponentModel.TypeConverter> puede convertirla, el objeto devuelto debe admitir una conversión al tipo que la propiedad espera. De lo contrario, la implementación de <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A> debe devolver `null`.

Cada implementación de <xref:System.ComponentModel.TypeConverter> puede interpretar de manera única qué constituye una cadena válida para una conversión y, también, puede usar o ignorar la descripción del tipo o los contextos de referencia cultural pasados como parámetros. Sin embargo, el procesamiento de XAML de WPF podría no pasar valores al contexto de descripción del tipo en todos los casos y, asimismo, no pasar referencias culturales basadas en `xml:lang`.

> [!NOTE]
> No utilice las llaves{}( ), específicamente la llave de apertura ( ) como un elemento del formato de cadena. Estos caracteres están reservados como entrada y salida de una secuencia de extensión de marcado.

Es adecuado producir una excepción cuando el convertidor de tipos debe tener acceso a <xref:System.IServiceProvider.GetService%2A> un servicio XAML desde el escritor de objetos de servicios XAML de .NET, pero la llamada que se realiza en el contexto no devuelve ese servicio.

### <a name="implementing-convertto"></a>Implementación de ConvertTo

<xref:System.ComponentModel.TypeConverter.ConvertTo%2A> se usa en teoría para admitir la serialización. La compatibilidad con la serialización a través de <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> para el tipo personalizado y su convertidor de tipos no es un requisito imprescindible. Pero, si implementa un control, o usa la serialización como parte de las características o del diseño de la clase, conviene implementar <xref:System.ComponentModel.TypeConverter.ConvertTo%2A>.

Para ser igual de utilizable que una implementación de <xref:System.ComponentModel.TypeConverter> que admite XAML, el método <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> para ese convertidor tiene que aceptar una instancia del tipo (o un valor) que se pueda usar como parámetro `value` . Cuando el parámetro `destinationType` es de tipo <xref:System.String>, el objeto devuelto debe poder convertirse en <xref:System.String>. La cadena devuelta debe representar un valor serializado de `value`. Lo ideal sería que el formato de serialización elegido sea capaz de generar el mismo valor que si esa cadena se pasara a la implementación de <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A> del mismo convertidor sin incurrir en una pérdida significativa de información.

Si el valor no se puede serializar o el convertidor no admite la serialización, la implementación de <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> debe devolver `null` y puede producir una excepción. Pero, si se producen excepciones, será necesario dejar constancia de la imposibilidad de usar esa conversión como parte de su implementación de <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A> para, así, poder dar cabida al procedimiento recomendado de comprobar primero con <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A> para evitar excepciones.

Si el parámetro `destinationType` no es de tipo <xref:System.String>, puede elegir su propio control de convertidor. Normalmente, se vuelve al control de implementación base, que en el <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> base genera una excepción específica.

Es adecuado producir una excepción cuando el convertidor de tipos debe tener acceso a <xref:System.IServiceProvider.GetService%2A> un servicio XAML desde el escritor de objetos de servicios XAML de .NET, pero la llamada que se realiza en el contexto no devuelve ese servicio.

### <a name="implementing-canconvertfrom"></a>Implementación de CanConvertFrom

Su implementación de <xref:System.ComponentModel.TypeConverter.CanConvertFrom%2A> debe devolver `true` para `sourceType` de tipo <xref:System.String> o, si no, respetar la implementación base. No genere excepciones desde <xref:System.ComponentModel.TypeConverter.CanConvertFrom%2A>.

### <a name="implementing-canconvertto"></a>Implementación de CanConvertTo

Su implementación de <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A> debe devolver `true` para `destinationType` de tipo <xref:System.String>o, si no, respetar la implementación base. No genere excepciones desde <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A>.

## <a name="applying-the-typeconverterattribute"></a>Aplicación de TypeConverterAttribute

Para que los servicios XAML de .NET usen el convertidor de tipos personalizado <xref:System.ComponentModel.TypeConverterAttribute> como convertidor de tipos que actuará para una clase personalizada, debe aplicar la definición de clase. El <xref:System.ComponentModel.TypeConverterAttribute.ConverterTypeName%2A> que se especifica a través del atributo debe ser el nombre de tipo del convertidor de tipos personalizado. Si aplica este atributo, cuando un procesador XAML controla valores donde el tipo de propiedad usa el tipo de la clase personalizada, puede especificar cadenas y devolver instancias de objeto.

También puede proporcionar un convertidor de tipos por cada propiedad. En lugar de <xref:System.ComponentModel.TypeConverterAttribute> aplicar a a la definición de clase, aplíquela a una definición de propiedad (la definición principal, no las implementaciones dentro de ella). `get` / `set` El tipo de la propiedad tiene que coincidir con el tipo que el convertidor de tipos personalizado procesa. Con este atributo aplicado, cuando un procesador XAML controla valores de esa propiedad, puede procesar cadenas de entrada y devolver instancias de objeto. La técnica de convertidor de tipos por propiedad es útil si elige usar un tipo de propiedad de Microsoft <xref:System.ComponentModel.TypeConverterAttribute> .NET Framework o de alguna otra biblioteca donde no puede controlar la definición de clase y no puede aplicar una allí.

Para proporcionar un comportamiento de conversión de tipos para un miembro asociado personalizado, aplique <xref:System.ComponentModel.TypeConverterAttribute> al método de descriptor de acceso `Get` del patrón de implementación del miembro asociado.

## <a name="accessing-service-provider-context-from-a-markup-extension-implementation"></a>Acceder al contexto del proveedor de servicios desde una implementación de la extensión de marcado

Los servicios disponibles son los mismos para todos los convertidores de valores. La diferencia radica en la manera en que cada convertidor de valores recibe el contexto de servicio. El acceso a los servicios y los servicios disponibles se documentan en el tema [Type Converters and Markup Extensions for XAML](type-converters-and-markup-extensions.md).

## <a name="type-converters-in-the-xaml-node-stream"></a>Convertidores de tipos en el flujo de nodo XAML

Si está trabajando con un flujo de nodo XAML, la acción o el resultado final de un convertidor de tipos no se ejecuta todavía. En una ruta de acceso de carga, la cadena de atributo que finalmente se debe convertir en tipo para poder cargarse permanece como un valor de texto dentro de un miembro de inicio y un miembro de finalización. El convertidor de tipos necesario en última instancia para esta operación se puede averiguar con la propiedad <xref:System.Xaml.XamlMember.TypeConverter%2A?displayProperty=nameWithType> . Sin embargo, para obtener un valor válido de <xref:System.Xaml.XamlMember.TypeConverter%2A?displayProperty=nameWithType> hay que tener un contexto de esquema XAML, que puede tener acceso a dicha información a través del miembro subyacente, o el tipo del valor del objeto que el miembro usa. Invocar el comportamiento de conversión de tipos también precisa del contexto de esquema XAML, porque requiere la asignación de tipos y crear una instancia del convertidor.

## <a name="see-also"></a>Consulte también

- <xref:System.ComponentModel.TypeConverterAttribute>
- [Convertidores de tipos y extensiones de marcado para XAML](type-converters-and-markup-extensions.md)
- [Información general sobre XAML (WPF)](../fundamentals/xaml.md)
