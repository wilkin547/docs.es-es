---
title: "Clases TypeConverter y XAML | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "clases, TypeConverter"
  - "TypeConverter (clase)"
  - "XAML, TypeConverter (clase)"
ms.assetid: f6313e4d-e89d-497d-ac87-b43511a1ae4b
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Clases TypeConverter y XAML
En este tema se presenta el propósito de la conversión de tipos de cadena como característica general del lenguaje XAML.  En .NET Framework, la clase <xref:System.ComponentModel.TypeConverter> tiene una finalidad concreta como parte de la implementación para una clase personalizada administrada que se puede utilizar como valor de propiedad en el uso de atributos XAML.  Si escribe una clase personalizada, y desea que las instancias de su clase se puedan utilizar como valores de atributos XAML que se pueden establecer, podría necesitar aplicar <xref:System.ComponentModel.TypeConverterAttribute> a su clase, escribir una clase <xref:System.ComponentModel.TypeConverter> personalizada, o ambas cosas.  
  
   
  
## Conceptos de conversión de tipos  
  
### XAML y valores de cadena  
 Cuando se establece un valor de atributo en un archivo XAML, el tipo inicial de ese valor es una cadena en texto puro.  Incluso otros primitivos como <xref:System.Double> son inicialmente cadenas de texto para un procesador XAML.  
  
 Un procesador XAML necesita dos fragmentos de información para procesar un valor de atributo.  El primer fragmento es el tipo de valor de la propiedad que se establece.  Cualquier cadena que define un valor de atributo y que se procesa en XAML se debe convertir o resolver finalmente a un valor de ese tipo.  Si el valor es un primitivo que el analizador de XAML entiende \(como un valor numérico\), se intenta una conversión directa de la cadena.  Si el valor es una enumeración, la cadena se utiliza para comprobar una coincidencia de nombre con una constante con nombre en esa enumeración.  Si el valor no es primitivo que el analizador entiende ni una enumeración, el tipo en cuestión debe poder proporcionar una instancia del tipo, o un valor, basado en una cadena convertida.  Esto se hace indicando una clase de convertidor de tipos.  El convertidor de tipos es, en realidad, una clase de aplicación auxiliar para proporcionar valores de otra clase, tanto para el escenario de XAML como, potencialmente, para las llamadas del código en el código de .NET Framework.  
  
### Utilizar el comportamiento de conversión de tipos existente en XAML  
 Dependiendo de la medida en que esté familiarizado con los conceptos de XAML subyacentes, es posible que ya utilice el comportamiento de conversión de tipos en aplicaciones XAML básicas sin darse cuenta.  Por ejemplo, WPF define literalmente centenares de propiedades que toman un valor de tipo <xref:System.Windows.Point>.  <xref:System.Windows.Point> es un valor que describe una coordenada en un espacio de coordenadas bidimensional y, en realidad, no tiene más que dos propiedades importantes: <xref:System.Windows.Point.X%2A> y <xref:System.Windows.Point.Y%2A>.  Cuando se especifica un punto en XAML, se especifica como cadena con un delimitador \(normalmente una coma\) entre los valores <xref:System.Windows.Point.Y%2A> e <xref:System.Windows.Point.X%2A> que se proporcionan.  Por ejemplo: `<LinearGradientBrush StartPoint="0,0" EndPoint="1,1">`.  
  
 Incluso este tipo simple de <xref:System.Windows.Point> y su uso simple en XAML requieren un convertidor de tipos.  En este caso, es la clase <xref:System.Windows.PointConverter>.  
  
 El convertidor de tipos para <xref:System.Windows.Point> definido en el nivel de clase racionaliza los usos del marcado de todas las propiedades que toman <xref:System.Windows.Point>.  Si en este caso no hubiera un convertidor de tipos, se necesitaría el marcado siguiente, mucho más detallado, para obtener el mismo ejemplo mostrado previamente:  
  
 `<LinearGradientBrush>`  
  
 `<LinearGradientBrush.StartPoint>`  
  
 `<Point X="0" Y="0"/>`  
  
 `</LinearGradientBrush.StartPoint>`  
  
 `<LinearGradientBrush.EndPoint>`  
  
 `<Point X="1" Y="1"/>`  
  
 `</LinearGradientBrush.EndPoint>`  
  
 `<LinearGradientBrush>`  
  
 La decisión entre utilizar la cadena de conversión de tipos o una sintaxis equivalente más detallada suele depender del estilo de codificación.  También el flujo de trabajo de las herramientas de XAML puede influir en el modo de establecer los valores.  Algunas herramientas XAML suelen crear la forma más detallada del marcado porque facilita la operación de ida y vuelta en las vistas de los diseñadores o su propio mecanismo de serialización.  
  
 Los convertidores de tipos existentes generalmente se pueden detectar en los tipos de WPF y .NET Framework comprobando en una clase \(o propiedad\) si se ha aplicado un atributo <xref:System.ComponentModel.TypeConverterAttribute>.  Este atributo denominará la clase que es el convertidor de tipos para los valores de ese tipo, tanto para los fines de XAML como, potencialmente, para otros propósitos.  
  
### Convertidores de tipos y extensiones de marcado  
 Las extensiones de marcado y convertidores de tipos rellenan los roles ortogonales por lo que se refiere al comportamiento del procesador XAML y los escenarios a los que se aplican.  Aunque el contexto está disponible para los usos de la extensión de marcado, el comportamiento de la conversión de tipos de propiedades en las que una extensión de marcado proporciona un valor generalmente no se comprueba en las implementaciones de la extensión de marcado.  En otras palabras, aunque una extensión de marcado devuelva una cadena de texto como resultado de `ProvideValue`, no se invoca el comportamiento de la conversión de tipos en esa cadena tal y como se aplica a una propiedad concreta o al tipo de valor de propiedad. Generalmente, el propósito de una extensión de marcado es procesar una cadena y devolver un objeto sin implicar ningún convertidor de tipos.  
  
 Una situación común en la que es necesario usar una extensión de marcado en lugar de un convertidor de tipos es cuando se hace referencia a un objeto que ya existe.  En el mejor de los casos, un convertidor de tipos sin estado solamente podría generar una nueva instancia, lo cual podría no ser conveniente.  Para obtener más información sobre las extensiones de marcado, vea [Extensiones de marcado y XAML de WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
### Convertidores de tipos nativos  
 En la implementación de WPF y .NET Framework del analizador de XAML, hay algunos tipos que presentan una administración nativa de la conversión de tipos, si bien no se trata de tipos que puedan considerarse primitivos por convención.  Un ejemplo de uno de estos tipos es <xref:System.DateTime>.  El motivo reside en el funcionamiento de la arquitectura de .NET Framework: el tipo <xref:System.DateTime> se define en mscorlib, la biblioteca más básica de .NET Framework.  <xref:System.DateTime> no puede recibir un atributo que proceda de otro ensamblado que introduzca una dependencia \(<xref:System.ComponentModel.TypeConverterAttribute> pertenece a System\). Por consiguiente, el mecanismo habitual de detección de convertidores de tipos mediante el uso de atributos no se admite.  En su lugar, el analizador de XAML tiene una lista de tipos que necesitan este procesamiento nativo y, y los procesa de manera parecida a los primitivos auténticos.  \(En el caso de <xref:System.DateTime> esto conlleva una llamada a <xref:System.DateTime.Parse%2A>.  
  
<a name="Implementing_a_Type_Converter"></a>   
## Implementar un convertidor de tipos  
  
### TypeConverter  
 En el ejemplo <xref:System.Windows.Point> proporcionado previamente, se menciona la clase <xref:System.Windows.PointConverter>.  Para las implementaciones del .NET Framework de XAML, todos los convertidores de tipos que se utilizan para XAML son clases que se derivan de la clase base <xref:System.ComponentModel.TypeConverter>.  La clase <xref:System.ComponentModel.TypeConverter> existía en las versiones de .NET Framework anteriores a la existencia de XAML; uno de sus usos originales era proporcionar conversión de cadenas para los cuadros de diálogo de propiedades en los diseñadores visuales.  Para XAML, el rol de <xref:System.ComponentModel.TypeConverter> se expande para incluir el hecho de ser la clase base para las conversiones en una cadena y a partir de una cadena que permiten analizar un valor de atributo de cadena, y posiblemente, el procesamiento de un valor en tiempo de ejecución de una propiedad de objeto determinada para convertirlo en una cadena, para la serialización como un atributo.  
  
 <xref:System.ComponentModel.TypeConverter> define cuatro miembros que son pertinentes para convertir en cadenas y a partir de ellas con fines de procesamiento de XAML:  
  
-   <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A>  
  
-   <xref:System.ComponentModel.TypeConverter.CanConvertFrom%2A>  
  
-   <xref:System.ComponentModel.TypeConverter.ConvertTo%2A>  
  
-   <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A>  
  
 De ellos, el método más importante es <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A>.  Este método convierte la cadena de entrada en el tipo de objeto necesario.  Desde un punto de vista estricto, el método <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A> se podría implementar de modo que convirtiese un abanico mucho más extenso de tipos en el tipo de destino previsto del convertidor y, de este modo, servir para otros fines además de XAML, como admitir conversiones en tiempo de ejecución. Sin embargo, a los efectos de XAML lo único que cuenta es la ruta de acceso del código que puede procesar una entrada <xref:System.String>.  
  
 El siguiente método en importancia es <xref:System.ComponentModel.TypeConverter.ConvertTo%2A>.  Si una aplicación se convierte en una representación de marcado \(por ejemplo, se guarda en XAML como archivo\), <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> es responsable de generar una representación de marcado.  En este caso, la ruta de acceso del código pertinente para XAML es la que se usa al pasar `destinationType` de <xref:System.String>.  
  
 <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A> y <xref:System.ComponentModel.TypeConverter.CanConvertFrom%2A> son métodos de compatibilidad que se utilizan cuando un servicio consulta las funciones de la implementación de <xref:System.ComponentModel.TypeConverter>.  Debe implementar estos métodos de modo que devuelvan `true` para los casos específicos del tipo admitidos por los métodos de conversión equivalentes del convertidor.  Para los propósitos de XAML, suele ser el tipo <xref:System.String>.  
  
### Información de la referencia cultural y convertidores de tipo para XAML  
 Cada implementación de <xref:System.ComponentModel.TypeConverter> puede presentar su propia interpretación de lo que constituye una cadena válida para una conversión y, además, puede utilizar u omitir la descripción de tipos pasados como parámetros.  Existe una consideración importante con respecto a la referencia cultural y a la conversión de tipos de XAML.  XAML admite plenamente el uso de cadenas traducibles como valores de atributo.  Sin embargo, no se admite el uso de esa cadena traducible como entrada del convertidor de tipos con requisitos de referencia cultural concretos, porque los convertidores de tipos para los valores de atributo de XAML requieren necesariamente un comportamiento de análisis de lenguaje fijo mediante la referencia cultural `en-US`.  Para obtener más información sobre las razones de diseño que motivan esta restricción, consulte la especificación del lenguaje XAML \([\[MS\-XAML\]](http://go.microsoft.com/fwlink/?LinkId=114525)\).  
  
 Un ejemplo que ilustra por qué una referencia cultural puede ser un problema, es que algunas referencias culturales utilizan la coma como delimitador de separador decimal para los números.  Esto entra en conflicto con el comportamiento de muchos de los convertidores de tipos de XAML de WPF, consistente en utilizar una coma como delimitador \(basándose en precedentes históricos como el formato X,Y común o las listas delimitadas por comas\).  El problema tampoco se resuelve pasando una referencia cultural en el XAML circundante \(estableciendo `Language` o `xml:lang` en la referencia cultural `sl-SI`, que es una de las que utilizan la coma para separar los decimales de esta manera\).  
  
### Implementar ConvertFrom  
 Para poder utilizarlo como una implementación de <xref:System.ComponentModel.TypeConverter> que admite XAML, el método <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A> para ese convertidor debe aceptar una cadena como el parámetro `value`.  Si el formato de la cadena es válido y la implementación de <xref:System.ComponentModel.TypeConverter> la puede convertir, entonces el objeto devuelto debe admitir una conversión al tipo esperado por la propiedad.  De lo contrario, la implementación de <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A> debe devolver `null`.  
  
 Cada implementación de <xref:System.ComponentModel.TypeConverter> puede tener su propia interpretación de lo que constituye una cadena válida para una conversión y, además, puede utilizar u omitir la descripción de tipos o los contextos de referencia cultural pasados como parámetros.  Sin embargo, el procesamiento de XAML de WPF podría no pasar valores al contexto de descripción de tipos en todos los casos, ni tampoco referencias culturales basadas en `xml:lang`.  
  
> [!NOTE]
>  No utilice los caracteres de llave, en particular {, como elementos posibles del formato de cadena.  Estos caracteres están reservados como entrada y salida de una secuencia de extensión de marcado.  
  
### Implementar ConvertTo  
 <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> se utiliza potencialmente para admitir la serialización.  Compatibilidad con la serialización a través de <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> para su tipo personalizado y su convertidor de tipos no es un requisito imprescindible.  Sin embargo, si implementa un control, o utiliza la serialización como parte de las características o del diseño de la clase, debe implementar <xref:System.ComponentModel.TypeConverter.ConvertTo%2A>.  
  
 Para poder utilizarlo como una implementación de <xref:System.ComponentModel.TypeConverter> que admite XAML, el método <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> para ese convertidor debe aceptar una instancia del tipo \(o un valor\) admitido como parámetro `value`.  Cuando el parámetro `destinationType` es del tipo <xref:System.String>, el objeto devuelto debe poderse convertir a <xref:System.String>.  La cadena devuelta debe representar un valor serializado de `value`.  En la situación ideal, el formato de serialización elegido deberá ser capaz de generar el mismo valor si esa cadena se pasara a la implementación de <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A> del mismo convertidor, sin ninguna pérdida significativa de información.  
  
 Si el valor no se puede serializar, o si el convertidor no admite la serialización, la implementación de <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> debe devolver `null`, en cuyo caso se permite que inicie una excepción.  Sin embargo, si se inician excepciones, debe notificarse la incapacidad de utilizar esa conversión como parte de la implementación <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A> para que se admita el procedimiento recomendado de comprobar primero con <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A> para evitar las excepciones.  
  
 Si el parámetro `destinationType` no es del tipo <xref:System.String>, puede elegir su propia administración de convertidor.  Normalmente, se revertiría a la administración de la implementación base, que en el método <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> más básico inicia una excepción concreta.  
  
### Implementar CanConvertTo  
 La implementación de <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A> debe devolver `true` para `destinationType` de tipo <xref:System.String> y, de lo contrario, diferir la evaluación a la implementación base.  
  
### Implementar CanConvertFrom  
 La implementación de <xref:System.ComponentModel.TypeConverter.CanConvertFrom%2A> debe devolver `true` para `sourceType` de tipo <xref:System.String> y, de lo contrario, diferir la evaluación a la implementación base.  
  
<a name="Applying_the_TypeConverterAttribute"></a>   
## Aplicar TypeConverterAttribute  
 Para que el convertidor de tipos personalizado se utilice como convertidor de tipos activo para una clase personalizada por parte de un procesador XAML, es preciso aplicar el objeto <xref:System.ComponentModel.TypeConverterAttribute> de [!INCLUDE[TLA#tla_netframewkattr](../../../../includes/tlasharptla-netframewkattr-md.md)] a la definición de clase.  La propiedad <xref:System.ComponentModel.TypeConverterAttribute.ConverterTypeName%2A> que se especifica a través del atributo debe ser el nombre de tipo del convertidor de tipos personalizado.  Con este atributo aplicado, cuando un procesador XAML administra valores cuyo tipo de propiedad utiliza el tipo de la clase personalizada, puede especificar cadenas y devolver instancias de objeto.  
  
 También puede proporcionar un convertidor de tipos para cada propiedad.  En lugar de aplicar un [!INCLUDE[TLA#tla_netframewkattr](../../../../includes/tlasharptla-netframewkattr-md.md)] <xref:System.ComponentModel.TypeConverterAttribute> a la definición de clase, aplíqueselo a una definición de propiedad \(a la definición principal, no a las implementaciones de `get`\/`set` que contiene\).  El tipo de la propiedad debe coincidir con el tipo procesado por el convertidor de tipos personalizado.  Con este atributo aplicado, cuando un procesador XAML administra valores de esa propiedad, puede procesar cadenas de entrada y devolver instancias de objeto.  La técnica del convertidor de tipos para cada propiedad resulta especialmente útil si decide utilizar un tipo de propiedad de [!INCLUDE[TLA#tla_netframewk](../../../../includes/tlasharptla-netframewk-md.md)] o de alguna otra biblioteca donde no se puede controlar la definición de clase ni aplicar <xref:System.ComponentModel.TypeConverterAttribute>.  
  
## Vea también  
 <xref:System.ComponentModel.TypeConverter>   
 [Información general sobre XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)   
 [Extensiones de marcado y XAML de WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)   
 [Detalles de la sintaxis XAML](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md)