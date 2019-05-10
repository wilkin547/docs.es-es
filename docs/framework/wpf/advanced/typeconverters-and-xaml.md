---
title: Clases TypeConverter y XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], TypeConverter class
ms.assetid: f6313e4d-e89d-497d-ac87-b43511a1ae4b
ms.openlocfilehash: 17a4a7f4a514c07280dd5f58935fea3eed1ca4e3
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64662203"
---
# <a name="typeconverters-and-xaml"></a>Clases TypeConverter y XAML
En este tema se presenta el propósito de la conversión de tipos desde cadenas como característica general del lenguaje XAML. En .NET Framework, el <xref:System.ComponentModel.TypeConverter> clase tiene una finalidad concreta como parte de la implementación para una clase personalizada administrada que puede usarse como un valor de propiedad en el uso de atributos XAML. Si escribe una clase personalizada y desea que las instancias de la clase que se pueda usar como valores de atributo configurables de XAML, deberá aplicar un <xref:System.ComponentModel.TypeConverterAttribute> a la clase, escribir un personalizado <xref:System.ComponentModel.TypeConverter> clase, o ambos.  

## <a name="type-conversion-concepts"></a>Conceptos de la conversión de tipos  
  
### <a name="xaml-and-string-values"></a>Valores de cadena y XAML  
 Cuando se establece un valor de atributo en un archivo XAML, el tipo inicial de ese valor es una cadena en texto puro. Incluso otros primitivos como <xref:System.Double> son inicialmente cadenas de texto a un procesador XAML.  
  
 Un procesador XAML necesita dos fragmentos de información para procesar un valor de atributo. El primer fragmento de información es el tipo de valor de la propiedad que se va a establecer. Cualquier cadena que defina un valor de atributo y que se procese en XAML se tiene que convertir o resolver en última instancia en un valor de ese tipo. Si el valor es un primitivo que el analizador XAML entiende (por ejemplo, un valor numérico), se tratará de convertir la cadena directamente. Si el valor es una enumeración, se usa la cadena para comprobar una coincidencia de nombre con una constante con nombre en esa enumeración. Si el valor no es un primitivo que el analizador entiende ni una enumeración, entonces el tipo en cuestión debe poder proporcionar una instancia del tipo, o un valor, basado en una cadena convertida. Esto se hace indicando una clase de convertidor de tipos. El convertidor de tipos es, en realidad, una clase del asistente para proporcionar valores de otra clase, tanto para el escenario de XAML como, potencialmente, para las llamadas de código en el código de .NET Framework.  
  
### <a name="using-existing-type-conversion-behavior-in-xaml"></a>Usar el comportamiento de conversión de tipos existente en XAML  
 Dependiendo de la medida en que esté familiarizado con los conceptos de XAML subyacentes, es posible que ya use el comportamiento de conversión de tipos en aplicaciones XAML básicas sin darse cuenta. Por ejemplo, WPF define literalmente centenares de propiedades que toman un valor de tipo <xref:System.Windows.Point>. Un <xref:System.Windows.Point> es un valor que describe una coordenada en un espacio de coordenadas bidimensional y, en realidad tiene dos propiedades importantes: <xref:System.Windows.Point.X%2A> y <xref:System.Windows.Point.Y%2A>. Cuando se especifica un punto en XAML, se especifica como una cadena con un delimitador (normalmente una coma) entre el <xref:System.Windows.Point.X%2A> y <xref:System.Windows.Point.Y%2A> valores proporcionados. Por ejemplo: `<LinearGradientBrush StartPoint="0,0" EndPoint="1,1"/>`.  
  
 Incluso este tipo simple de <xref:System.Windows.Point> y su uso simple en XAML requieren un convertidor. En este caso es la clase <xref:System.Windows.PointConverter>.  
  
 El convertidor de tipos para <xref:System.Windows.Point> definidos en el optimiza de nivel de clase de los usos de marcado de todas las propiedades que toman <xref:System.Windows.Point>. Si en este caso no hubiera un convertidor de tipos, se necesitaría el marcado siguiente, mucho más detallado, para obtener el mismo ejemplo mostrado previamente:  

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
  
 Convertidores de tipos existentes generalmente se pueden detectar en tipos de WPF y .NET Framework mediante la comprobación de una clase (o propiedad) para la presencia de un aplicada <xref:System.ComponentModel.TypeConverterAttribute>. Este atributo denominará la clase que es el convertidor de tipos para los valores de ese tipo, tanto para los fines de XAML como, potencialmente, para otros propósitos.  
  
### <a name="type-converters-and-markup-extensions"></a>Convertidores de tipos y extensiones de marcado  
 Las extensiones de marcado y los convertidores de tipos rellenan los roles ortogonales en lo que se refiere al comportamiento del procesador XAML y los escenarios a los que se aplican. Aunque el contexto está disponible para los usos de la extensión de marcado, en las implementaciones de extensión de marcado no se suele comprobar el comportamiento de conversión de tipos de aquellas propiedades en las que una extensión de marcado proporciona un valor. En otras palabras, aunque una extensión de marcado devuelva una cadena de texto como salida de `ProvideValue`, no se invoca el comportamiento de la conversión de tipos en esa cadena tal y como se aplica a una propiedad concreta o al tipo de valor de propiedad. Generalmente, el propósito de una extensión de marcado es procesar una cadena y devolver un objeto sin ningún convertidor de tipos implicado.  
  
 Una situación común en la que es necesario usar una extensión de marcado en lugar de un convertidor de tipos es cuando se hace referencia a un objeto que ya existe. En el mejor de los casos, un convertidor de tipos sin estado solamente podría generar una nueva instancia, lo que podría no ser conveniente. Para más información sobre las extensiones de marcado, vea [Extensiones de marcado y XAML de WPF](markup-extensions-and-wpf-xaml.md).  
  
### <a name="native-type-converters"></a>Convertidores de tipos nativos  
 En la implementación de WPF y .NET Framework del analizador de XAML, hay algunos tipos que presentan un control nativo de la conversión de tipos, si bien no se trata de tipos que puedan considerarse primitivos por convención. Un ejemplo de este tipo es <xref:System.DateTime>. La razón de esto se basa en el funcionamiento de la arquitectura de .NET Framework: el tipo <xref:System.DateTime> se define en mscorlib, la biblioteca más básica de. NET. <xref:System.DateTime> no tiene permiso para atribuir con un atributo que proceda de otro ensamblado que introduce una dependencia (<xref:System.ComponentModel.TypeConverterAttribute> proviene del sistema) por lo que no se admite el mecanismo de detección de convertidor de tipos habitual mediante atribución. En su lugar, el analizador de XAML tiene una lista de tipos que necesitan este procesamiento nativo y los procesa de manera parecida a los primitivos auténticos. (En el caso de <xref:System.DateTime> esto implica una llamada a <xref:System.DateTime.Parse%2A>.)  
  
<a name="Implementing_a_Type_Converter"></a>   
## <a name="implementing-a-type-converter"></a>Implementación de un convertidor de tipos  
  
### <a name="typeconverter"></a>TypeConverter  
 En el <xref:System.Windows.Point> ejemplo presentado anteriormente, la clase <xref:System.Windows.PointConverter> mencionada. Para implementaciones de XAML de. NET, todos los convertidores de tipos que se usan para fines XAML son clases que derivan de la clase base <xref:System.ComponentModel.TypeConverter>. La <xref:System.ComponentModel.TypeConverter> clase existía en versiones de .NET Framework anteriores a la existencia de XAML; uno de sus usos originales era proporcionar conversión de cadenas para los cuadros de diálogo de propiedades en los diseñadores visuales. Para XAML, el rol de <xref:System.ComponentModel.TypeConverter> se expande para incluir el que se va a la clase base para las conversiones a cadena y de cadena que permiten analizar un valor de atributo de cadena y, posiblemente, el procesamiento en una cadena para un valor de tiempo de ejecución de una propiedad de objeto determinado serialización como un atributo.  
  
 <xref:System.ComponentModel.TypeConverter> define a cuatro miembros que son pertinentes para la conversión a y desde cadenas para fines de procesamiento de XAML:  
  
- <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A>  
  
- <xref:System.ComponentModel.TypeConverter.CanConvertFrom%2A>  
  
- <xref:System.ComponentModel.TypeConverter.ConvertTo%2A>  
  
- <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A>  
  
 De estos, el método más importante es <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A>. Este método convierte la cadena de entrada en el tipo de objeto necesario. En realidad, el <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A> método se puede implementar para convertir una gama mucho más amplia de tipos en el tipo de destino previsto del convertidor y, por tanto, se usan con fines que van más allá de XAML, como admitir conversiones en tiempo de ejecución, pero para fines XAML es sólo la ruta de acceso de código que puede procesar un <xref:System.String> entrada que es importante.  
  
 El siguiente método más importante es <xref:System.ComponentModel.TypeConverter.ConvertTo%2A>. Si una aplicación se convierte en una representación de marcado (por ejemplo, si se guarda en XAML como un archivo), <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> es responsable de producir una representación de marcado. En este caso, la ruta de acceso del código pertinente para XAML es cuando se pasa un `destinationType` de <xref:System.String> .  
  
 <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A> y <xref:System.ComponentModel.TypeConverter.CanConvertFrom%2A> son métodos de compatibilidad que se usan cuando un servicio consulta las capacidades de la implementación de <xref:System.ComponentModel.TypeConverter> . Estos métodos se tienen que implementar para obtener `true` en los casos específicos de tipo que los métodos de conversión equivalentes de su convertidor admiten. Para los propósitos de XAML, esto suele traducirse en el tipo <xref:System.String> .  
  
### <a name="culture-information-and-type-converters-for-xaml"></a>Información de referencia cultural y convertidores de tipos para XAML  
 Cada <xref:System.ComponentModel.TypeConverter> implementación puede tener su propia interpretación de lo que constituye una cadena válida para una conversión y también puede usar o ignorar la descripción de tipo pasada como parámetros. Existe una consideración importante con respecto a la referencia cultural y a la conversión de tipos de XAML. XAML admite plenamente el uso de cadenas traducibles como valores de atributo. Pero no se admite el uso de esa cadena traducible como entrada del convertidor de tipos con requisitos de referencia cultural concretos, porque los convertidores de tipos para los valores de atributo de XAML requieren necesariamente un comportamiento de análisis de lenguaje fijo mediante la referencia cultural `en-US`. Para más información sobre las razones de diseño que motivan esta restricción, vea la especificación del lenguaje XAML ([\[MS-XAML\]](https://go.microsoft.com/fwlink/?LinkId=114525)).  
  
 Un ejemplo que ilustra por qué una referencia cultural puede ser un problema, es que algunas referencias culturales usan una coma como delimitador de separador decimal para los números. Esto entra en conflicto con el comportamiento de muchos de los convertidores de tipos de XAML de WPF, consistente en usar una coma como delimitador (basándose en precedentes históricos como el formato X,Y común o las listas delimitadas por comas). El problema tampoco se resuelve pasando una referencia cultural en el XAML circundante (estableciendo `Language` o `xml:lang` en la referencia cultural `sl-SI`, que es una de las que usan la coma para separar los decimales de esta manera).  
  
### <a name="implementing-convertfrom"></a>Implementación de ConvertFrom  
 Para ser igual de utilizable que una implementación de <xref:System.ComponentModel.TypeConverter> que admite XAML, el método <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A> para ese convertidor tiene que aceptar una cadena como parámetro `value` . Si la cadena estaba en válido, dar formato y se puede convertir el <xref:System.ComponentModel.TypeConverter> implementación y, a continuación, el objeto devuelto debe admitir una conversión al tipo esperado por la propiedad. De lo contrario, la implementación de <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A> debe devolver `null`.  
  
 Cada <xref:System.ComponentModel.TypeConverter> implementación puede tener su propia interpretación de lo que constituye una cadena válida para una conversión y también puede usar o ignorar los contextos de referencia cultural o la descripción de tipo pasados como parámetros. Pero es posible que el procesamiento de XAML de WPF no pase valores al contexto de descripción del tipo en todos los casos y que tampoco pase referencias culturales basadas en `xml:lang`.  
  
> [!NOTE]
>  No use los caracteres de llave, en concreto {, como elementos posibles del formato de cadena. Estos caracteres están reservados como entrada y salida de una secuencia de extensión de marcado.  
  
### <a name="implementing-convertto"></a>Implementación de ConvertTo  
 <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> se usa en teoría para admitir la serialización. La compatibilidad con la serialización a través de <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> para el tipo personalizado y su convertidor de tipos no es un requisito imprescindible. Pero, si implementa un control, o usa la serialización como parte de las características o del diseño de la clase, conviene implementar <xref:System.ComponentModel.TypeConverter.ConvertTo%2A>.  
  
 Para poder usarlo como un <xref:System.ComponentModel.TypeConverter> implementación que admite XAML, el <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> método para ese convertidor debe aceptar una instancia del tipo (o un valor) que se admita como el `value` parámetro. Cuando el `destinationType` parámetro es el tipo <xref:System.String>, a continuación, el objeto devuelto debe poder convertirse en <xref:System.String>. La cadena devuelta debe representar un valor serializado de `value`. Idealmente, el formato de serialización elegido debería ser capaz de generar el mismo valor si esa cadena se pasara a la <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A> implementación del mismo convertidor, sin ninguna pérdida significativa de información.  
  
 Si no se puede serializar el valor o el convertidor no admite la serialización, el <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> implementación debe devolver `null`y puede producir una excepción en este caso. Pero si se producen excepciones, debe notificar la incapacidad de usar esa conversión como parte de su <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A> implementación para que el procedimiento recomendado de comprobar con <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A> en primer lugar se admite evitar las excepciones.  
  
 Si `destinationType` parámetro no es de tipo <xref:System.String>, puede elegir su propio control de convertidor. Normalmente, se revertiría al control, lo que en el método de implementación base <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> genera una excepción específica.  
  
### <a name="implementing-canconvertto"></a>Implementación de CanConvertTo  
 Su implementación de <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A> debe devolver `true` para `destinationType` de tipo <xref:System.String>o, si no, respetar la implementación base.  
  
### <a name="implementing-canconvertfrom"></a>Implementación de CanConvertFrom  
 Su implementación de <xref:System.ComponentModel.TypeConverter.CanConvertFrom%2A> debe devolver `true` para `sourceType` de tipo <xref:System.String>o, si no, respetar la implementación base.  
  
<a name="Applying_the_TypeConverterAttribute"></a>   
## <a name="applying-the-typeconverterattribute"></a>Aplicación de TypeConverterAttribute  
 En orden para el convertidor de tipos personalizado para usarse como el que actúa el convertidor de tipos para una clase personalizada por un procesador XAML, debe aplicar el [!INCLUDE[TLA#tla_netframewkattr](../../../../includes/tlasharptla-netframewkattr-md.md)] <xref:System.ComponentModel.TypeConverterAttribute> a su definición de clase. El <xref:System.ComponentModel.TypeConverterAttribute.ConverterTypeName%2A> que se especifica a través del atributo debe ser el nombre de tipo del convertidor de tipos personalizado. Con este atributo aplicado, cuando un procesador XAML controla valores en los que el tipo de propiedad usa el tipo de la clase personalizada, puede especificar cadenas y devolver instancias de objeto.  
  
 También puede proporcionar un convertidor de tipos por cada propiedad. En lugar de aplicar un [!INCLUDE[TLA#tla_netframewkattr](../../../../includes/tlasharptla-netframewkattr-md.md)] <xref:System.ComponentModel.TypeConverterAttribute> a la definición de clase, aplíquelo a una definición de propiedad (la definición principal, no las implementaciones de `get`/`set` dentro de ella). El tipo de la propiedad tiene que coincidir con el tipo que el convertidor de tipos personalizado procesa. Con este atributo aplicado, cuando un procesador XAML controla valores de esa propiedad, puede procesar cadenas de entrada y devolver instancias de objeto. La técnica de convertidor de tipos por propiedad resulta especialmente útil si decide usar un tipo de propiedad de Microsoft .NET Framework o de alguna otra biblioteca donde no se puede controlar la definición de clase y no se puede aplicar un <xref:System.ComponentModel.TypeConverterAttribute> no existe.  
  
## <a name="see-also"></a>Vea también

- <xref:System.ComponentModel.TypeConverter>
- [Información general sobre XAML (WPF)](xaml-overview-wpf.md)
- [Extensiones de marcado y XAML de WPF](markup-extensions-and-wpf-xaml.md)
- [Detalles de la sintaxis XAML](xaml-syntax-in-detail.md)
