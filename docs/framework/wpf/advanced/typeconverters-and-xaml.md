---
title: Clases TypeConverter y XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], TypeConverter class
ms.assetid: f6313e4d-e89d-497d-ac87-b43511a1ae4b
ms.openlocfilehash: 6b8b58228e94ed12557e97406e55cc4165753076
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2020
ms.locfileid: "77095091"
---
# <a name="typeconverters-and-xaml"></a>Clases TypeConverter y XAML
En este tema se presenta el propósito de la conversión de tipos desde cadenas como característica general del lenguaje XAML. En el .NET Framework, la clase <xref:System.ComponentModel.TypeConverter> sirve para un propósito determinado como parte de la implementación de una clase personalizada administrada que se puede usar como un valor de propiedad en el uso de atributos XAML. Si escribe una clase personalizada y desea que las instancias de la clase se puedan usar como valores de atributo que se pueden establecer en XAML, puede que tenga que aplicar un <xref:System.ComponentModel.TypeConverterAttribute> a la clase, escribir una clase de <xref:System.ComponentModel.TypeConverter> personalizada o ambas cosas.  

## <a name="type-conversion-concepts"></a>Conceptos de la conversión de tipos  
  
### <a name="xaml-and-string-values"></a>Valores de cadena y XAML  
 Cuando se establece un valor de atributo en un archivo XAML, el tipo inicial de ese valor es una cadena en texto puro. Incluso otros tipos primitivos como <xref:System.Double> son cadenas de texto inicialmente para un procesador XAML.  
  
 Un procesador XAML necesita dos fragmentos de información para procesar un valor de atributo. El primer fragmento de información es el tipo de valor de la propiedad que se va a establecer. Cualquier cadena que defina un valor de atributo y que se procese en XAML se tiene que convertir o resolver en última instancia en un valor de ese tipo. Si el valor es un primitivo que el analizador XAML entiende (por ejemplo, un valor numérico), se tratará de convertir la cadena directamente. Si el valor es una enumeración, se usa la cadena para comprobar una coincidencia de nombre con una constante con nombre en esa enumeración. Si el valor no es un primitivo que el analizador entiende ni una enumeración, entonces el tipo en cuestión debe poder proporcionar una instancia del tipo, o un valor, basado en una cadena convertida. Esto se hace indicando una clase de convertidor de tipos. El convertidor de tipos es, en realidad, una clase del asistente para proporcionar valores de otra clase, tanto para el escenario de XAML como, potencialmente, para las llamadas de código en el código de .NET Framework.  
  
### <a name="using-existing-type-conversion-behavior-in-xaml"></a>Usar el comportamiento de conversión de tipos existente en XAML  
 Dependiendo de la medida en que esté familiarizado con los conceptos de XAML subyacentes, es posible que ya use el comportamiento de conversión de tipos en aplicaciones XAML básicas sin darse cuenta. Por ejemplo, WPF define literalmente cientos de propiedades que toman un valor de tipo <xref:System.Windows.Point>. Un <xref:System.Windows.Point> es un valor que describe una coordenada en un espacio de coordenadas bidimensional y, en realidad, solo tiene dos propiedades importantes: <xref:System.Windows.Point.X%2A> y <xref:System.Windows.Point.Y%2A>. Cuando se especifica un punto en XAML, se especifica como una cadena con un delimitador (normalmente una coma) entre el <xref:System.Windows.Point.X%2A> y <xref:System.Windows.Point.Y%2A> valores que se proporcionan. Por ejemplo: `<LinearGradientBrush StartPoint="0,0" EndPoint="1,1"/>`.  
  
 Incluso este tipo simple de <xref:System.Windows.Point> y su uso simple en XAML implican un convertidor de tipos. En este caso, es la clase <xref:System.Windows.PointConverter>.  
  
 El convertidor de tipos de <xref:System.Windows.Point> definido en el nivel de clase simplifica los usos de marcado de todas las propiedades que toman <xref:System.Windows.Point>. Si en este caso no hubiera un convertidor de tipos, se necesitaría el marcado siguiente, mucho más detallado, para obtener el mismo ejemplo mostrado previamente:  

```xaml
<LinearGradientBrush>
  <LinearGradientBrush.StartPoint>
    <Point X="0" Y="0"/>
  </LinearGradientBrush.StartPoint>
  <LinearGradientBrush.EndPoint>
    <Point X="1" Y="1"/>
  </LinearGradientBrush.EndPoint>
</LinearGradientBrush>
 ```
  
 La decisión entre usar la cadena de conversión de tipos o una sintaxis equivalente más detallada suele depender del estilo de codificación. Es posible que el flujo de trabajo de las herramientas de XAML también influya en el modo de establecer los valores. Algunas herramientas de XAML suelen crear la forma más detallada del marcado porque facilita la operación de ida y vuelta en las vistas de los diseñadores o su propio mecanismo de serialización.  
  
 Por lo general, los convertidores de tipos existentes se pueden detectar en WPF y en tipos de .NET Framework mediante la comprobación de una clase (o propiedad) para la presencia de un <xref:System.ComponentModel.TypeConverterAttribute>aplicado. Este atributo denominará la clase que es el convertidor de tipos para los valores de ese tipo, tanto para los fines de XAML como, potencialmente, para otros propósitos.  
  
### <a name="type-converters-and-markup-extensions"></a>Convertidores de tipos y extensiones de marcado  
 Las extensiones de marcado y los convertidores de tipos rellenan los roles ortogonales en lo que se refiere al comportamiento del procesador XAML y los escenarios a los que se aplican. Aunque el contexto está disponible para los usos de la extensión de marcado, en las implementaciones de extensión de marcado no se suele comprobar el comportamiento de conversión de tipos de aquellas propiedades en las que una extensión de marcado proporciona un valor. En otras palabras, aunque una extensión de marcado devuelva una cadena de texto como salida de `ProvideValue`, no se invoca el comportamiento de la conversión de tipos en esa cadena tal y como se aplica a una propiedad concreta o al tipo de valor de propiedad. Generalmente, el propósito de una extensión de marcado es procesar una cadena y devolver un objeto sin ningún convertidor de tipos implicado.  
  
 Una situación común en la que es necesario usar una extensión de marcado en lugar de un convertidor de tipos es cuando se hace referencia a un objeto que ya existe. En el mejor de los casos, un convertidor de tipos sin estado solamente podría generar una nueva instancia, lo que podría no ser conveniente. Para más información sobre las extensiones de marcado, vea [Extensiones de marcado y XAML de WPF](markup-extensions-and-wpf-xaml.md).  
  
### <a name="native-type-converters"></a>Convertidores de tipos nativos  
 En la implementación de WPF y .NET Framework del analizador de XAML, hay algunos tipos que presentan un control nativo de la conversión de tipos, si bien no se trata de tipos que puedan considerarse primitivos por convención. Un ejemplo de este tipo es <xref:System.DateTime>. El motivo de esto se basa en cómo funciona la arquitectura de .NET Framework: el tipo <xref:System.DateTime> se define en mscorlib, la biblioteca más básica de .NET. <xref:System.DateTime> no se puede atribuir con un atributo que proceda de otro ensamblado que introduzca una dependencia (<xref:System.ComponentModel.TypeConverterAttribute> proviene del sistema), por lo que no se admite el mecanismo de detección de convertidores de tipos habitual mediante atribución. En su lugar, el analizador de XAML tiene una lista de tipos que necesitan este procesamiento nativo y los procesa de manera parecida a los primitivos auténticos. (En el caso de <xref:System.DateTime> esto implica una llamada a <xref:System.DateTime.Parse%2A>).  
  
<a name="Implementing_a_Type_Converter"></a>   
## <a name="implementing-a-type-converter"></a>Implementación de un convertidor de tipos  
  
### <a name="typeconverter"></a>TypeConverter  
 En el <xref:System.Windows.Point> ejemplo dado anteriormente, se mencionó la clase <xref:System.Windows.PointConverter>. En el caso de las implementaciones de .NET de XAML, todos los convertidores de tipos que se usan para los propósitos de XAML son clases que derivan de la clase base <xref:System.ComponentModel.TypeConverter>. La clase <xref:System.ComponentModel.TypeConverter> existía en las versiones de .NET Framework que preceden a la existencia de XAML; uno de sus usos originales era proporcionar la conversión de cadenas para los cuadros de diálogo de propiedades en los diseñadores visuales. Para XAML, el rol de <xref:System.ComponentModel.TypeConverter> se expande para incluir la clase base para las conversiones de cadena y de cadena que habilitan el análisis de un valor de atributo de cadena y, posiblemente, el procesamiento de un valor en tiempo de ejecución de una propiedad de objeto determinado de nuevo en una cadena para la serialización como un atributo.  
  
 <xref:System.ComponentModel.TypeConverter> define cuatro miembros que son relevantes para la conversión a y desde cadenas para fines de procesamiento de XAML:  
  
- <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A>  
  
- <xref:System.ComponentModel.TypeConverter.CanConvertFrom%2A>  
  
- <xref:System.ComponentModel.TypeConverter.ConvertTo%2A>  
  
- <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A>  
  
 De estos, el método más importante es <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A>. Este método convierte la cadena de entrada en el tipo de objeto necesario. En realidad, el método <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A> podría implementarse para convertir una gama mucho más amplia de tipos en el tipo de destino previsto del convertidor y, por tanto, atender los propósitos que van más allá de XAML, como admitir conversiones en tiempo de ejecución, pero para los propósitos de XAML es solo la ruta de acceso del código que puede procesar una entrada <xref:System.String> que sea importante.  
  
 El siguiente método más importante es <xref:System.ComponentModel.TypeConverter.ConvertTo%2A>. Si una aplicación se convierte en una representación de marcado (por ejemplo, si se guarda en XAML como un archivo), <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> es responsable de generar una representación de marcado. En este caso, la ruta de acceso del código que es importante para XAML es cuando se pasa una `destinationType` de <xref:System.String>.  
  
 <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A> y <xref:System.ComponentModel.TypeConverter.CanConvertFrom%2A> son métodos de compatibilidad que se usan cuando un servicio consulta las capacidades de la implementación de <xref:System.ComponentModel.TypeConverter> . Estos métodos se tienen que implementar para obtener `true` en los casos específicos de tipo que los métodos de conversión equivalentes de su convertidor admiten. Para los propósitos de XAML, esto suele traducirse en el tipo <xref:System.String> .  
  
### <a name="culture-information-and-type-converters-for-xaml"></a>Información de referencia cultural y convertidores de tipos para XAML  

 Cada implementación de <xref:System.ComponentModel.TypeConverter> puede tener su propia interpretación de lo que constituye una cadena válida para una conversión y también puede usar o ignorar la descripción de tipo que se pasa como parámetros. Existe una consideración importante con respecto a la referencia cultural y a la conversión de tipos de XAML. XAML admite plenamente el uso de cadenas traducibles como valores de atributo. Pero no se admite el uso de esa cadena traducible como entrada del convertidor de tipos con requisitos de referencia cultural concretos, porque los convertidores de tipos para los valores de atributo de XAML requieren necesariamente un comportamiento de análisis de lenguaje fijo mediante la referencia cultural `en-US`. Para obtener más información sobre los motivos de diseño de esta restricción, debe consultar la especificación del lenguaje XAML ([\[MS-XAML\]](https://download.microsoft.com/download/0/A/6/0A6F7755-9AF5-448B-907D-13985ACCF53E/[MS-XAML].pdf).  
  
 Un ejemplo que ilustra por qué una referencia cultural puede ser un problema, es que algunas referencias culturales usan una coma como delimitador de separador decimal para los números. Esto entra en conflicto con el comportamiento de muchos de los convertidores de tipos de XAML de WPF, consistente en usar una coma como delimitador (basándose en precedentes históricos como el formato X,Y común o las listas delimitadas por comas). El problema tampoco se resuelve pasando una referencia cultural en el XAML circundante (estableciendo `Language` o `xml:lang` en la referencia cultural `sl-SI`, que es una de las que usan la coma para separar los decimales de esta manera).  
  
### <a name="implementing-convertfrom"></a>Implementación de ConvertFrom  
 Para ser igual de utilizable que una implementación de <xref:System.ComponentModel.TypeConverter> que admite XAML, el método <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A> para ese convertidor tiene que aceptar una cadena como parámetro `value` . Si la cadena tiene un formato válido y la implementación de <xref:System.ComponentModel.TypeConverter> puede convertirla, el objeto devuelto debe admitir una conversión al tipo esperado por la propiedad. De lo contrario, la implementación de <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A> debe devolver `null`.  
  
 Cada implementación de <xref:System.ComponentModel.TypeConverter> puede tener su propia interpretación de lo que constituye una cadena válida para una conversión y también puede usar o ignorar la descripción del tipo o los contextos de referencia cultural pasados como parámetros. Pero es posible que el procesamiento de XAML de WPF no pase valores al contexto de descripción del tipo en todos los casos y que tampoco pase referencias culturales basadas en `xml:lang`.  
  
> [!NOTE]
> No use los caracteres de llave, en concreto {, como elementos posibles del formato de cadena. Estos caracteres están reservados como entrada y salida de una secuencia de extensión de marcado.  
  
### <a name="implementing-convertto"></a>Implementación de ConvertTo  
 <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> se usa en teoría para admitir la serialización. La compatibilidad con la serialización a través de <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> para el tipo personalizado y su convertidor de tipos no es un requisito imprescindible. Pero, si implementa un control, o usa la serialización como parte de las características o del diseño de la clase, conviene implementar <xref:System.ComponentModel.TypeConverter.ConvertTo%2A>.  
  
 Para que se pueda usar como una implementación <xref:System.ComponentModel.TypeConverter> que admite XAML, el método de <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> para ese convertidor debe aceptar una instancia del tipo (o un valor) que se admita como el parámetro `value`. Cuando el parámetro `destinationType` es el tipo <xref:System.String>, el objeto devuelto debe poder convertirse en <xref:System.String>. La cadena devuelta debe representar un valor serializado de `value`. Idealmente, el formato de serialización elegido debe ser capaz de generar el mismo valor si esa cadena se pasa a la implementación de <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A> del mismo convertidor, sin una pérdida significativa de información.  
  
 Si el valor no se puede serializar o el convertidor no admite la serialización, la implementación de <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> debe devolver `null`y se le permite producir una excepción en este caso. Pero si inicia excepciones, debe notificar la imposibilidad de usar esa conversión como parte de la implementación de <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A> para que se admita el procedimiento recomendado de comprobar con <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A> primero para evitar excepciones.  
  
 Si `destinationType` parámetro no es de tipo <xref:System.String>, puede elegir su propio control de convertidor. Normalmente, se revertiría a la administración de la implementación base, que en el <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> método genera una excepción específica.  
  
### <a name="implementing-canconvertto"></a>Implementación de CanConvertTo  
 Su implementación de <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A> debe devolver `true` para `destinationType` de tipo <xref:System.String>o, si no, respetar la implementación base.  
  
### <a name="implementing-canconvertfrom"></a>Implementación de CanConvertFrom  
 Su implementación de <xref:System.ComponentModel.TypeConverter.CanConvertFrom%2A> debe devolver `true` para `sourceType` de tipo <xref:System.String>o, si no, respetar la implementación base.  
  
<a name="Applying_the_TypeConverterAttribute"></a>   
## <a name="applying-the-typeconverterattribute"></a>Aplicación de TypeConverterAttribute  
 Para que un procesador XAML utilice el convertidor de tipos personalizado como convertidor de tipos que actúa para una clase personalizada, debe aplicar el <xref:System.ComponentModel.TypeConverterAttribute> a la definición de clase. El <xref:System.ComponentModel.TypeConverterAttribute.ConverterTypeName%2A> que se especifica a través del atributo debe ser el nombre de tipo del convertidor de tipos personalizado. Con este atributo aplicado, cuando un procesador XAML controla valores en los que el tipo de propiedad usa el tipo de la clase personalizada, puede especificar cadenas y devolver instancias de objeto.  
  
 También puede proporcionar un convertidor de tipos por cada propiedad. En lugar de aplicar un <xref:System.ComponentModel.TypeConverterAttribute> a la definición de clase, aplíquelo a una definición de propiedad (la definición principal, no a la `get`/`set` implementaciones que contiene). El tipo de la propiedad tiene que coincidir con el tipo que el convertidor de tipos personalizado procesa. Con este atributo aplicado, cuando un procesador XAML controla valores de esa propiedad, puede procesar cadenas de entrada y devolver instancias de objeto. La técnica de convertidor de tipos por propiedad resulta especialmente útil si decide usar un tipo de propiedad de Microsoft .NET Framework o de otra biblioteca donde no se puede controlar la definición de clase y no se puede aplicar un <xref:System.ComponentModel.TypeConverterAttribute> allí.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.ComponentModel.TypeConverter>
- [Información general sobre XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Extensiones de marcado y XAML de WPF](markup-extensions-and-wpf-xaml.md)
- [Detalles de la sintaxis XAML](xaml-syntax-in-detail.md)
