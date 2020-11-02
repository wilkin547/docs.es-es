---
title: Consideraciones de seguridad para datos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a7eb98da-4a93-4692-8b59-9d670c79ffb2
ms.openlocfilehash: b9b033f779b083be8bcec195caf8e55607f14d31
ms.sourcegitcommit: 7588b1f16b7608bc6833c05f91ae670c22ef56f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2020
ms.locfileid: "93188320"
---
# <a name="security-considerations-for-data"></a>Consideraciones de seguridad para datos

Al trabajar con datos en Windows Communication Foundation (WCF), debe tener en cuenta varias categorías de amenazas. En la siguiente lista se muestran las clases de amenazas más importantes relacionadas con el procesamiento de datos. WCF proporciona herramientas para mitigar estas amenazas.

* Denegación de servicio

  Al recibir datos que no son de confianza, los datos pueden hacer que el lado receptor tenga acceso a una cantidad desproporcionada de varios recursos, como memoria, subprocesos, conexiones disponibles o ciclos de procesador produciendo largos cálculos. Un ataque por denegación de servicio contra un servidor puede provocar que se bloquee y no pueda procesar los mensajes de otros clientes legítimos.

* Ejecución de código malintencionado

  Los datos entrantes que no son de confianza provocan que el lado receptor ejecute código que no pretendía ejecutar.

* Divulgación de información

  El atacante remoto obliga a la parte receptora a que responda a sus solicitudes de manera que divulga más información de la que pretende.

## <a name="user-provided-code-and-code-access-security"></a>Código proporcionado por usuario y seguridad de acceso del código

Varios lugares de la infraestructura de Windows Communication Foundation (WCF) ejecutan código proporcionado por el usuario. Por ejemplo, el motor de serialización <xref:System.Runtime.Serialization.DataContractSerializer> puede llamar a los descriptores de acceso de propiedad proporcionados por el usuario `set` y a los descriptores de acceso `get` . La infraestructura del canal de WCF también puede llamar a clases derivadas proporcionadas por el usuario de la <xref:System.ServiceModel.Channels.Message> clase.

Es responsabilidad del autor del código asegurarse de que no existan vulnerabilidades de seguridad. Por ejemplo, si crea un tipo de contrato de datos con una propiedad de miembro de datos de tipo entero, y en la implementación del descriptor de acceso `set` asigna una matriz basada en el valor de propiedad, expondrá la posibilidad de un ataque por denegación de servicio si un mensaje malintencionado contiene un valor sumamente grande para este miembro de datos. En general, evite cualquier asignación basada en datos entrantes o el procesamiento largo en código proporcionado por el usuario (sobre todo si una cantidad pequeña de los datos entrantes puede provocar un procesamiento largo). Al realizar análisis de seguridad de código proporcionado por usuario, asegúrese de considerar también todos los casos de error (es decir, todas las bifurcaciones de código donde se produzcan excepciones).

El ejemplo último de código proporcionado por usuario es el código dentro de su implementación del servicio para cada operación. La seguridad de su implementación del servicio es su responsabilidad. Es fácil crear inadvertidamente implementaciones de la operación inseguras que puedan producir vulnerabilidades de la denegación de servicio. Por ejemplo, una operación que toma una cadena y devuelve la lista de clientes de una base de datos cuyo nombre empieza con esa cadena. Si está trabajando con una base de datos grande y la cadena que se pasa simplemente es una letra única, su código puede intentar crear un mensaje mayor que toda la memoria disponible, haciendo que se produzca un error en el servicio completo. (Un <xref:System.OutOfMemoryException> no es recuperable en el .NET Framework y siempre da lugar a la finalización de la aplicación).

Debería asegurarse de que ningún código malintencionado esté conectado a los varios puntos de la extensibilidad. Esto es especialmente importante cuando la ejecución se realiza con confianza parcial, al tratar con tipos de ensamblados de confianza parcial, o al crear componentes que puede utilizar código de confianza parcial. Para obtener más información, vea "Amenazas de confianza parcial" en una sección posterior.

Tenga en cuenta que cuando se realiza la ejecución en confianza parcial, la infraestructura de serialización del contrato de datos solo admite un subconjunto limitado de modelos de programación de contratos de datos, por ejemplo, no se admiten miembros de datos privados o tipos que utilizan el atributo <xref:System.SerializableAttribute> . Para obtener más información, vea [confianza parcial](partial-trust.md).

## <a name="avoiding-unintentional-information-disclosure"></a>Evitar la divulgación involuntaria de información

Al diseñar los tipos serializables con seguridad en mente, la divulgación de información es una posible preocupación.

Considere los siguientes puntos:

- El modelo de programación <xref:System.Runtime.Serialization.DataContractSerializer> permite la exposición de datos privados e internos fuera del tipo o ensamblado durante la serialización. Además, la forma de un tipo puede exponerse durante la exportación del esquema. Asegúrese de entender la proyección de la serialización de su tipo. Si no desea nada expuesto, deshabilite la serialización (por ejemplo, no aplicando el atributo <xref:System.Runtime.Serialization.DataMemberAttribute> en el caso de un contrato de datos).

- Sea consciente de que el mismo tipo puede tener varias proyecciones de serialización, dependiendo del serializador en uso. El mismo tipo puede exponer un conjunto de datos cuando se utiliza con <xref:System.Runtime.Serialization.DataContractSerializer> y otro conjunto de datos cuando se utiliza con <xref:System.Xml.Serialization.XmlSerializer>. La utilización accidental del serializador equivocado puede provocar la divulgación de información.

- Al utilizar <xref:System.Xml.Serialization.XmlSerializer> en modo de llamada a procedimiento remoto (RPC)/codificado heredado, puede exponer involuntariamente la forma del gráfico de objeto en el lado emisor al lado receptor.

## <a name="preventing-denial-of-service-attacks"></a>Prevenir ataques de denegación de servicio

### <a name="quotas"></a>Cuotas

Hacer que el lado receptor asigne una cantidad de memoria significativa es un ataque por denegación de servicio potencial. Mientras esta sección se concentra en problemas de consumo de la memoria emite derivados de los mensajes grandes, se pueden producir otros ataques. Por ejemplo, los mensajes pueden utilizar una cantidad desproporcionada de tiempo de proceso.

Los ataques por denegación de servicio normalmente se mitigan utilizando las cuotas. Cuando se supera una cuota, normalmente se produce una excepción <xref:System.ServiceModel.QuotaExceededException> . Sin la cuota, un mensaje malintencionado puede provocar que se tenga acceso a toda la memoria disponible, provocando una excepción <xref:System.OutOfMemoryException> o que se tenga acceso a todas las pilas disponibles, lo que daría lugar a una <xref:System.StackOverflowException>.

El escenario de cuota superada es recuperable; si se encuentra en un servicio en ejecución, se descarta el mensaje que se está procesando actualmente y el servicio sigue ejecutándose y procesa otros mensajes. Sin embargo, los escenarios de memoria insuficiente y de desbordamiento de pila no se pueden recuperar en ningún lugar del .NET Framework; el servicio finaliza si encuentra tales excepciones.

Las cuotas en WCF no implican ninguna asignación previa. Por ejemplo, si la cuota <xref:System.ServiceModel.Channels.TransportBindingElement.MaxReceivedMessageSize%2A> (presente en varias clases) está establecida en 128 KB, no significa que 128 KB se asigne automáticamente a cada mensaje. La cantidad real asignada depende del tamaño del mensaje entrante real.

Muchas cuotas están disponibles en el nivel de transporte. Son cuotas exigidas por el canal de transporte concreto en uso (HTTP, TCP, etc.). Aunque en este tema se abordan algunas de estas cuotas, estas se describen en detalle en [Transport Quotas](transport-quotas.md).

### <a name="hashtable-vulnerability"></a>Vulnerabilidad del objeto hashtable

Existe vulnerabilidad cuando los contratos de datos contienen tablas de objeto hashtable o colecciones. El problema aparece si un gran número de valores se insertan en un objeto hashtable donde muchos de los valores producen el mismo valor hash. Se puede usar como un ataque de DOS.  Esta vulnerabilidad se puede mitigar estableciendo la cuota de enlace MaxReceivedMessageSize. Hay que tener cuidado al establecer esta quota para evitar estos ataques. Esta cuota coloca un límite en el tamaño del mensaje de WCF. Además, evite usar tablas de objeto hashtable o colecciones en los contratos de datos.

## <a name="limiting-memory-consumption-without-streaming"></a>Limitar el consumo de la memoria sin transmisión por secuencias

El modelo de seguridad alrededor de los mensajes grandes depende de si se utiliza la transmisión por secuencias. En el caso básico, sin transmisión por secuencias, los mensajes están almacenados en el búfer de la memoria. En este caso, utilice la cuota <xref:System.ServiceModel.Channels.TransportBindingElement.MaxReceivedMessageSize%2A> de <xref:System.ServiceModel.Channels.TransportBindingElement> o en los enlaces proporcionados por el sistema, para protegerse frente a mensajes grandes limitando el tamaño máximo del mensaje al que se obtiene acceso. Tenga en cuenta que un servicio puede procesar varios mensajes al mismo tiempo, en cuyo caso todos estarán en memoria. Utilice la característica de limitación de peticiones para mitigar esta amenaza.

También observe que `MaxReceivedMessageSize` no coloca un límite superior en consumo de la memoria por mensaje, pero lo limita dentro de un factor constante. Por ejemplo, si el `MaxReceivedMessageSize` es de 1 MB, se recibe un mensaje de 1 MB y, a continuación, se deserializa, se necesitará memoria adicional para contener el gráfico de objeto deserializado, lo que provocará un consumo total de la memoria de más de 1 MB. Por esta razón, evite crear tipos serializable que podrían provocar un consumo significativo de la memoria sin muchos datos entrantes. Por ejemplo, se podría crear una instancia de un contrato de datos "DataContract" con los campos de miembro de datos opcionales 50 y otros 100 campos privados adicionales con la construcción de XML " \<MyContract/> ". Este XML provocará que se obtenga acceso a la memoria para 150 campos. Observe que los miembros de datos son de forma predeterminada opcionales. El problema se produce cuando un tipo de estas características forma parte de una matriz.

`MaxReceivedMessageSize` solo no es bastante para evitar todos los ataques por denegación de servicio. Por ejemplo, un mensaje entrante puede obligar al deserializador a deserializar un gráfico de objetos anidado de manera profunda (un objeto que contiene otro objeto que también contiene otro, etc.). <xref:System.Runtime.Serialization.DataContractSerializer> y <xref:System.Xml.Serialization.XmlSerializer> llaman a los métodos de una manera anidada para deserializar tales gráficos. El anidamiento profundo de llamadas al método puede producir un <xref:System.StackOverflowException>irrecuperable. Esta amenaza se mitiga estableciendo la cuota <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement.MaxDepth%2A> para limitar el nivel de anidamiento de XML, como se aborda en la sección "Utilizar XML con seguridad" más adelante en este tema.

Establecer las cuotas adicionales en `MaxReceivedMessageSize` es especialmente importante al utilizar codificación XML binaria. Utilizar la codificación binaria equivalente de algún modo a la compresión: un grupo pequeño de bytes en el mensaje entrante puede representar muchos datos. Por lo tanto, incluso un mensaje que se ajuste al límite `MaxReceivedMessageSize` puede ocupar mucha más memoria en su forma totalmente expandida. Para mitigar tales amenazas específicas del XML, todas las cuotas del lector XML se deben establecer correctamente, como se aborda en la sección en la "Utilizar XML con seguridad" más adelante en este tema.

## <a name="limiting-memory-consumption-with-streaming"></a>Limitar el consumo de la memoria con transmisión por secuencias

Al tener transmisión por secuencias, puede utilizar un valor `MaxReceivedMessageSize` pequeño para protegerse contra los ataques por denegación de servicio. Sin embargo, con la transmisión por secuencias se pueden dar más escenarios complicados. Por ejemplo, un servicio de carga de archivo acepta archivos mayores que la memoria total disponible. En este caso, establezca el `MaxReceivedMessageSize` con un valor sumamente grande, esperando que casi ningún dato se almacene en búfer en memoria y que el mensaje se transmita por secuencias directamente al disco. Si un mensaje malintencionado puede forzar de algún modo a WCF a almacenar en búfer los datos en lugar de transmitirlos en este caso, `MaxReceivedMessageSize` ya no protege contra el mensaje que tiene acceso a toda la memoria disponible.

Para mitigar esta amenaza, existen valores de cuota específicos en varios componentes de procesamiento de datos de WCF que limitan el almacenamiento en búfer. El más importante es la propiedad `MaxBufferSize` en varios elementos de enlace del transporte y enlaces estándares. Al transmitir por secuencias, esta cuota se debería establecer teniendo cuenta la cantidad de memoria máxima que quiere asignar por mensaje. Como con `MaxReceivedMessageSize`, el valor no coloca un máximo absoluto en consumo de la memoria sino que solo lo limita dentro de un factor constante. También, como con `MaxReceivedMessageSize`, sea consciente de la posibilidad de varios mensajes que se procesen simultáneamente.

### <a name="maxbuffersize-details"></a>Detalles de MaxBufferSize

La `MaxBufferSize` propiedad limita cualquier WCF de almacenamiento en búfer masivo. Por ejemplo, WCF siempre almacena en búfer encabezados SOAP y errores de SOAP, así como las partes MIME que no se encuentran en el orden de lectura natural en un mensaje del mecanismo de optimización de transmisión de mensajes (MTOM). Este valor limita la cantidad de almacenamiento en búfer en todos estos casos.

WCF consigue esto pasando el `MaxBufferSize` valor a los distintos componentes que pueden almacenar en búfer. Por ejemplo, algunas sobrecargas de <xref:System.ServiceModel.Channels.Message.CreateMessage%2A> de la clase <xref:System.ServiceModel.Channels.Message> toman un parámetro `maxSizeOfHeaders` . WCF pasa el `MaxBufferSize` valor a este parámetro para limitar la cantidad de almacenamiento en búfer del encabezado SOAP. Es importante establecer este parámetro al utilizar directamente la clase <xref:System.ServiceModel.Channels.Message> . En general, al utilizar un componente en WCF que toma parámetros de cuota, es importante comprender las implicaciones de seguridad de estos parámetros y establecerlos correctamente.

El codificador del mensaje de MTOM también tiene un valor `MaxBufferSize` . Al utilizar enlaces estándares, esto se establece automáticamente en el valor del nivel de transporte `MaxBufferSize` . Sin embargo, al utilizar el elemento de enlace de codificador del mensaje de MTOM para construir un enlace personalizado, es importante establecer la propiedad `MaxBufferSize` en un valor seguro cuando se utiliza la transmisión por secuencias.

## <a name="xml-based-streaming-attacks"></a>Ataques de la transmisión por secuencias basados en XML

`MaxBufferSize` por sí solo no es suficiente para asegurarse de que no se puede forzar a WCF en el almacenamiento en búfer cuando se espera la transmisión por secuencias. Por ejemplo, los lectores XML de WCF siempre almacenan en búfer la etiqueta inicial del elemento XML completa al empezar a leer un nuevo elemento. Se hace esto para que se procesen los espacios de nombres y atributos correctamente. Si `MaxReceivedMessageSize` se configura para ser grande (por ejemplo, para habilitar un escenario de transmisión por secuencias de archivo grande directo a disco), se puede construir un mensaje malintencionado donde el cuerpo entero del mensaje sea una etiqueta inicial de elemento XML grande. Un intento para leerlo provocará <xref:System.OutOfMemoryException>. Se trata de uno de los muchos posibles ataques de denegación de servicio basados en XML que se pueden mitigar mediante cuotas de lector XML, que se describen en la sección "usar XML con seguridad" más adelante en este tema. En la transmisión por secuencias, es especialmente importante establecer todas estas cuotas.

### <a name="mixing-streaming-and-buffering-programming-models"></a>Mezclar los modelos de programación de transmisión por secuencias y almacenamiento en búfer

Muchos posibles ataques surgen de mezclar los modelos de programación de transmisión por secuencias y sin secuencias en el mismo servicio. Suponga que hay un contrato de servicios con dos operaciones: uno toma <xref:System.IO.Stream> y otro toma una matriz de algún tipo personalizado. También suponga que `MaxReceivedMessageSize` está establecido en un valor grande para habilitar la primera operación para procesar las secuencias grandes. Desgraciadamente, esto significa que los mensajes grandes se pueden enviar también a la segunda operación, y el deserializador almacena en búfer los datos en memoria como una matriz antes de que se llame a la operación. Éste es un ataque por denegación de servicio potencial: la cuota `MaxBufferSize` no limita el tamaño del cuerpo del mensaje, que es con lo que trabaja el deserializador.

Por esta razón, evite mezclar operaciones basadas en secuencias y operaciones sin secuencias en el mismo contrato. Si debe mezclar necesariamente los dos modelos de programación, utilice las precauciones siguientes:

- Desactive la característica <xref:System.Runtime.Serialization.IExtensibleDataObject> estableciendo la propiedad <xref:System.ServiceModel.ServiceBehaviorAttribute.IgnoreExtensionDataObject%2A> de <xref:System.ServiceModel.ServiceBehaviorAttribute> en `true`. Esto garantiza que solo se deserializan los miembros que forman una parte del contrato.

- Establezca la propiedad <xref:System.Runtime.Serialization.DataContractSerializer.MaxItemsInObjectGraph%2A> de <xref:System.Runtime.Serialization.DataContractSerializer> en un valor seguro. Esta cuota también está disponible en el atributo <xref:System.ServiceModel.ServiceBehaviorAttribute> o a través de la configuración. Esta cuota limita el número de objetos que se deserializan en un episodio de deserialización. Normalmente, cada parámetro de operación o parte del cuerpo del mensaje en un contrato del mensaje se deserializa en un episodio. Al deserializar matrices, cada entrada de matriz se cuenta como un objeto independiente.

- Establezca todas las cuotas del lector XML en valores seguros. Preste atención a <xref:System.Xml.XmlDictionaryReaderQuotas.MaxDepth%2A>, <xref:System.Xml.XmlDictionaryReaderQuotas.MaxStringContentLength%2A>y <xref:System.Xml.XmlDictionaryReaderQuotas.MaxArrayLength%2A> , y evite las cadenas en operaciones de transmisión sin secuencias.

- Revise la lista de tipos conocidos, teniendo presente que se puede crear una instancia de ellos en cualquier momento (vea la sección “Evitar que se carguen tipos imprevistos” más adelante en este tema).

- No utilice tipos que implementen la interfaz <xref:System.Xml.Serialization.IXmlSerializable> que almacena en búfer muchos datos. No agregue tales tipos a la lista de tipos conocidos.

- No utilice las matrices <xref:System.Xml.XmlElement>, <xref:System.Xml.XmlNode> , matrices <xref:System.Byte> o tipos que implementen <xref:System.Runtime.Serialization.ISerializable> en un contrato.

- No utilice las matrices <xref:System.Xml.XmlElement>, <xref:System.Xml.XmlNode> , matrices <xref:System.Byte> o tipos que implementen <xref:System.Runtime.Serialization.ISerializable> en la lista de tipos conocidos.

Las precauciones anteriores se aplican cuando la operación sin transmisión por secuencias utiliza <xref:System.Runtime.Serialization.DataContractSerializer>. Nunca mezcle los modelos de programación de transmisión por secuencias y sin secuencias en el mismo servicio si está utilizando el <xref:System.Xml.Serialization.XmlSerializer>, porque no tiene la protección de la cuota <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior.MaxItemsInObjectGraph%2A> .

### <a name="slow-stream-attacks"></a>Ataques de secuencia lentos

Una clase de ataques por denegación de servicio de transmisión por secuencias no implica el consumo de la memoria. En su lugar, el ataque implica un envío o una recepción lenta de los datos. Mientras se espera a que los datos se envíen o reciban, se agotan los recursos como subprocesos y las conexiones disponibles. Esta situación se podría presentar como resultado de un ataque malintencionado o de un remitente/receptor legítimo en una conexión de red lenta.

Para mitigar estos ataques, establezca correctamente los tiempos de espera de transporte. Para obtener más información, consulte [cuotas de transporte](transport-quotas.md). En segundo lugar, nunca utilice operaciones sincrónicas `Read` u `Write` operaciones al trabajar con secuencias en WCF.

## <a name="using-xml-safely"></a>Utilizar XML con seguridad

> [!NOTE]
> Aunque esta sección trata acerca de XML, la información también se aplica a documentos de la notación de objetos JavaScript (JSON). Las cuotas funcionan de manera similar, con [Mapping Between JSON and XML](mapping-between-json-and-xml.md).

### <a name="secure-xml-readers"></a>Lectores XML seguros

El conjunto de código XML constituye la base de todo el procesamiento de mensajes en WCF. Al aceptar los datos XML de un origen que no es de confianza, existen varias posibilidades de ataque por denegación de servicio que se deben mitigar. WCF proporciona lectores XML especiales y seguros. Estos lectores se crean automáticamente al utilizar una de las codificaciones estándar en WCF (texto, binario o MTOM).

Algunas de las características de seguridad en estos lectores siempre están activas. Por ejemplo, los lectores nunca procesan definiciones de tipo de documento (DTD), que son un origen potencial de ataques por denegación de servicio y nunca deberían aparecer en mensajes SOAP legítimos. Otras características de seguridad incluyen cuotas del lector que se deben configurar, que se describen en la sección siguiente.

Al trabajar directamente con lectores XML (como al escribir su propio Codificador personalizado o al trabajar directamente con la <xref:System.ServiceModel.Channels.Message> clase), utilice siempre los lectores seguros de WCF cuando exista la posibilidad de trabajar con datos que no son de confianza. Cree los lectores seguros llamando a una de las sobrecargas estáticas del método del generador de <xref:System.Xml.XmlDictionaryReader.CreateTextReader%2A>, <xref:System.Xml.XmlDictionaryReader.CreateBinaryReader%2A>o <xref:System.Xml.XmlDictionaryReader.CreateMtomReader%2A> en la clase <xref:System.Xml.XmlDictionaryReader> . Al crear un lector, pase valores de cuota seguros. No llame a las sobrecargas de método `Create` . Estos no crean un lector de WCF. En su lugar, se crea un lector que no está protegido por las características de seguridad descritas en esta sección.

### <a name="reader-quotas"></a>Cuotas del lector

Los lectores XML seguros tienen cinco cuotas configurables. Normalmente se configuran utilizando la propiedad `ReaderQuotas` en los elementos de enlace de la codificación o enlaces estándares, o utilizando un objeto <xref:System.Xml.XmlDictionaryReaderQuotas> pasado al crear un lector.

#### <a name="maxbytesperread"></a>MaxBytesPerRead

Esta cuota limita el número de bytes que se leen en una operación `Read` única al leer la etiqueta de inicio de elemento y sus atributos. (En los casos en que no haya transmisión, el propio nombre del elemento no se cuenta para la cuota). <xref:System.Xml.XmlDictionaryReaderQuotas.MaxBytesPerRead%2A> es importante por los motivos siguientes:

- El nombre de elemento y sus atributos siempre están almacenados en búfer en memoria cuando se leen. Por consiguiente, es importante establecer correctamente esta cuota en modo de transmisión por secuencias para evitar el almacenado en búfer excesivo. Vea la sección de la cuota `MaxDepth` para obtener información acerca de la cantidad real de almacenamiento en búfer que tiene lugar.

- Tener demasiados atributos XML puede usar un tiempo de proceso desproporcionado porque se tiene que comprobar la unicidad de los nombres de atributo. `MaxBytesPerRead` mitiga esta amenaza.

#### <a name="maxdepth"></a>MaxDepth

Esta cuota limita la profundidad máxima del anidamiento de elementos XML. Por ejemplo, el documento " \<A> \<B> \<C/> \</B> \</A> " tiene una profundidad de anidamiento de tres. <xref:System.Xml.XmlDictionaryReaderQuotas.MaxDepth%2A> es importante por los motivos siguientes:

- `MaxDepth` interactúa con `MaxBytesPerRead`: el lector siempre mantiene los datos en memoria para el elemento vigente y todos sus antecesores, por lo que el consumo máximo de la memoria del lector es proporcional al producto de estos dos valores.

- Al deserializar un gráfico de objetos profundamente anidado, el deserializador se ve obligado a obtener acceso a la pila completa e iniciar una <xref:System.StackOverflowException>irrecuperable. Existe una correlación directa entre anidamiento de XML y anidamiento de objeto para <xref:System.Runtime.Serialization.DataContractSerializer> y <xref:System.Xml.Serialization.XmlSerializer>. Utilice `MaxDepth` para mitigar esta amenaza.

#### <a name="maxnametablecharcount"></a>MaxNameTableCharCount

Esta cuota limita el tamaño de la *tabla de nombres* del lector. La tabla de nombres contiene ciertas cadenas (como espacios de nombres y prefijos) que se encuentran al procesar un documento XML. Puesto que estas cadenas están almacenadas en búfer en memoria, establezca esta cuota para evitar el almacenamiento en búfer excesivo cuando se espera la transmisión por secuencias.

#### <a name="maxstringcontentlength"></a>MaxStringContentLength

Esta cuota limita el tamaño máximo de la cadena que el lector XML devuelve. Esta cuota no limita el consumo de la memoria en el propio lector XML, sino en el componente que está utilizando el lector. Por ejemplo, cuando <xref:System.Runtime.Serialization.DataContractSerializer> utiliza un lector protegido con <xref:System.Xml.XmlDictionaryReaderQuotas.MaxStringContentLength%2A>, no deserializa cadenas mayores que esta cuota. Al utilizar directamente la clase <xref:System.Xml.XmlDictionaryReader> , no todos los métodos respetan esta cuota, solo los métodos que están diseñados específicamente para leer cadenas, como el método <xref:System.Xml.XmlDictionaryReader.ReadContentAsString%2A> . Esta cuota no afecta a la propiedad <xref:System.Xml.XmlReader.Value%2A> en el lector y por lo tanto no se debería utilizar cuando la protección que proporciona esta cuota es necesaria.

#### <a name="maxarraylength"></a>MaxArrayLength

Esta cuota limita el tamaño máximo de una matriz de primitivas que devuelve el lector XML, incluidas las matrices de bytes. Esta cuota no limita el consumo de la memoria en el propio lector XML, sino en cualquier componente que esté utilizando el lector. Por ejemplo, cuando <xref:System.Runtime.Serialization.DataContractSerializer> utiliza un lector protegido con <xref:System.Xml.XmlDictionaryReaderQuotas.MaxArrayLength%2A>, no deserializa matrices de bytes mayores que esta cuota. Es importante establecer esta cuota al intentar mezclar modelos de programación de transmisión por secuencias y almacenamiento en búfer en un contrato único. Tenga presente que al utilizar directamente la clase <xref:System.Xml.XmlDictionaryReader> , solo los métodos que están diseñados específicamente para leer matrices de tamaño arbitrario de ciertos tipos primitivos, como <xref:System.Xml.XmlDictionaryReader.ReadInt32Array%2A>, respetan esta cuota.

## <a name="threats-specific-to-the-binary-encoding"></a>Amenazas específicas a la codificación binaria

La codificación XML binaria WCF compatible con incluye una característica de *cadenas de diccionario* . Una cadena grande puede estar codificada utilizando solo unos bytes. Esto permite considerables ganancias de rendimiento, pero introduce nuevas amenazas de la denegación de servicio que se deben mitigar.

Hay dos tipos de diccionarios: *estático* y *dinámico* . El diccionario estático es una lista integrada de cadenas largas que se puede representar utilizando un código corto en la codificación binaria. Esta lista de cadenas se fija cuando el lector se crea y no se puede modificar. Ninguna de las cadenas del diccionario estático que WCF utiliza de forma predeterminada es lo suficientemente grande como para suponer una amenaza grave de denegación de servicio, aunque todavía se pueden utilizar en un ataque de expansión de diccionario. En escenarios avanzados donde proporciona su propio diccionario estático, vaya con cuidado al introducir cadenas de diccionario grandes.

La característica de diccionarios dinámicos permite a los mensajes definir sus propias cadenas y asociarlas a códigos cortos. Estas asignaciones de cadena a código se mantienen en memoria durante la sesión completa de comunicación, de manera que los mensajes subsiguientes no tienen que reenviar las cadenas y pueden utilizar los códigos ya definidos. Estas cadenas pueden ser de longitud arbitraria y por consiguiente provocar una amenaza más seria que aquellas en el diccionario estático.

La primera amenaza que se debe mitigar es la posibilidad de que el diccionario dinámico (la tabla de asignación de cadena a código) se vuelva demasiado grande. Este diccionario se puede expandir a lo largo del curso de varios mensajes y así que la cuota `MaxReceivedMessageSize` no proporciona ninguna protección porque solo se aplica separadamente a cada mensaje. Por consiguiente, existe una propiedad <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement.MaxSessionSize%2A> independiente en <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement> que limita el tamaño del diccionario.

A diferencia de la mayoría de las otras cuotas, esta cuota también se aplica al escribir los mensajes. Si se supera al leer un mensaje, se inicia `QuotaExceededException` como de costumbre. Si se supera al escribir un mensaje, cualquier cadena que provoque que la cuota se supere se escribe como es, sin utilizar la característica de diccionarios dinámicos.

### <a name="dictionary-expansion-threats"></a>Amenazas de expansión de diccionario

Una clase significativa de ataques específicos binarios deriva de la expansión del diccionario. Un mensaje pequeño en formato binario se puede convertir en un mensaje muy grande en forma textual totalmente expandida si realiza uso extenso de la característica de diccionarios de cadena. La cuota <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement.MaxSessionSize%2A> limita el factor de expansión para las cadenas del diccionario dinámico, ya que ninguna cadena del diccionario dinámico supera el tamaño máximo del diccionario completo.

Las propiedades <xref:System.Xml.XmlDictionaryReaderQuotas.MaxNameTableCharCount%2A>, `MaxStringContentLength`y `MaxArrayLength` solo limitan el consumo de memoria. Normalmente no se necesitan para mitigar ninguna amenaza en el uso de transmisión sin secuencias porque `MaxReceivedMessageSize`ya limita la utilización de memoria. Sin embargo, `MaxReceivedMessageSize` cuenta los bytes de la pre-expansión. Cuando se utiliza la codificación binaria, el consumo de la memoria podría exceder potencialmente `MaxReceivedMessageSize`, limitado solo por un factor de <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement.MaxSessionSize%2A>. Por esta razón, es importante establecer siempre todas las cuotas del lector (sobre todo <xref:System.Xml.XmlDictionaryReaderQuotas.MaxStringContentLength%2A>) al utilizar la codificación binaria.

Al utilizar la codificación binaria junto con <xref:System.Runtime.Serialization.DataContractSerializer>, la interfaz `IExtensibleDataObject` se puede emplear mal para organizar un ataque de expansión de diccionario. Esta interfaz proporciona esencialmente el almacenamiento ilimitado para datos arbitrarios que no forman parte del contrato. Si no se pueden establecer las cuotas suficientemente bajas de manera que `MaxSessionSize` multiplicado por `MaxReceivedMessageSize` no suponga un problema, deshabilite la característica `IExtensibleDataObject` al utilizar la codificación binaria. Establezca la `IgnoreExtensionDataObject` propiedad en `true` en el `ServiceBehaviorAttribute` atributo. Alternativamente, no implemente la interfaz `IExtensibleDataObject` . Para obtener más información, vea [Forward-Compatible Data Contracts](forward-compatible-data-contracts.md) (Contratos de datos compatibles con el reenvío).

### <a name="quotas-summary"></a>Resumen de las cuotas

La tabla siguiente resume la guía sobre las cuotas.

|Condición|Cuotas importantes a establecer|
|---------------|-----------------------------|
|Ninguna transmisión por secuencias o transmisión por secuencias de mensajes pequeños, texto o codificación de MTOM|`MaxReceivedMessageSize`, `MaxBytesPerRead` y `MaxDepth`|
|Ninguna transmisión por secuencias o transmisión por secuencias de mensajes pequeños, codificación binaria|`MaxReceivedMessageSize`, `MaxSessionSize`y todas las `ReaderQuotas`|
|Transmisión por secuencias de mensajes grandes, texto o codificación de MTOM|`MaxBufferSize` y todas las `ReaderQuotas`|
|Transmisión por secuencias de mensajes grandes, codificación binaria|`MaxBufferSize`, `MaxSessionSize`y todas las `ReaderQuotas`|

- Siempre se deben establecer tiempos de espera del nivel de transporte y no se debe utilizar nunca la lectura/escritura sincrónica cuando se utilice la transmisión por secuencias, independientemente de si está transmitiendo por secuencias mensajes grandes o pequeños.

- Cuando dude sobre una cuota, establézcala en un valor seguro en lugar de dejarla abierta.

## <a name="preventing-malicious-code-execution"></a>Evitar la ejecución de código malintencionado

Las clases generales siguientes de amenazas pueden ejecutar código y tener los efectos imprevistos:

- El deserializador carga un tipo malintencionado, no seguro o que afecta a la seguridad.

- Un mensaje entrante hace que el deserializador construya una instancia de un tipo normalmente seguro de de manera que tiene consecuencias imprevistas.

Las secciones siguientes abordan detalladamente estas clases de amenazas.

## <a name="datacontractserializer"></a>DataContractSerializer

(Para obtener información de seguridad en <xref:System.Xml.Serialization.XmlSerializer> , vea la documentación correspondiente). El modelo de seguridad para <xref:System.Xml.Serialization.XmlSerializer> es similar al de <xref:System.Runtime.Serialization.DataContractSerializer> y difiere principalmente en detalles. Por ejemplo, el atributo <xref:System.Xml.Serialization.XmlIncludeAttribute> se utiliza para la inclusión de tipo en lugar del atributo <xref:System.Runtime.Serialization.KnownTypeAttribute> . Sin embargo, algunas amenazas únicas de <xref:System.Xml.Serialization.XmlSerializer> se discuten más adelante en este tema.

### <a name="preventing-unintended-types-from-being-loaded"></a>Evitar que se carguen tipos imprevistos

Cargar tipos imprevistos puede tener consecuencias significativas, tanto si el tipo es malintencionado o simplemente tiene efectos secundarios que afectan a la seguridad. Un tipo puede contener vulnerabilidad de seguridad explotable, realizar acciones que afecten a la seguridad en su constructor o constructor de clase, tener una superficie de memoria grande que facilite los ataques por denegación de servicio, o bien puede provocar excepciones no recuperables. Los tipos pueden tener constructores de clase que se ejecutan en cuanto se cargue el tipo y antes de que se cree cualquier instancia. Por estas razones, es importante controlar el conjunto de tipos que el deserializador puede cargar.

<xref:System.Runtime.Serialization.DataContractSerializer> deserializa con acoplamiento separado. Nunca lee el tipo de Common Language Runtime (CLR) y los nombres de ensamblado de los datos entrantes. Esto es similar al comportamiento de <xref:System.Xml.Serialization.XmlSerializer>, pero difiere del comportamiento de <xref:System.Runtime.Serialization.NetDataContractSerializer>, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>, y <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>. El acoplamiento separado introduce un grado de seguridad, porque el atacante remoto no puede indicar que se cargue un tipo arbitrario simplemente denominando ese tipo en el mensaje.

Siempre se permite que <xref:System.Runtime.Serialization.DataContractSerializer> cargue un tipo que se espera actualmente según el contrato. Por ejemplo, si un contrato de datos tiene un miembro de datos de tipo `Customer`, <xref:System.Runtime.Serialization.DataContractSerializer> puede cargar el tipo `Customer` cuando deserializa este miembro de datos.

Además, <xref:System.Runtime.Serialization.DataContractSerializer> admite el polimorfismo. Un miembro de datos se puede declarar como <xref:System.Object>, pero los datos entrantes pueden contener una instancia `Customer` . Esto solo es posible si el tipo `Customer` se ha dado a conocer al deserializador a través de uno de estos mecanismos:

- Atributo<xref:System.Runtime.Serialization.KnownTypeAttribute> aplicado al tipo.

- Atributo`KnownTypeAttribute` que especifica un método que devuelve una lista de tipos.

- Atributo`ServiceKnownTypeAttribute` .

- Sección de configuración `KnownTypes` .

- Una lista de tipos conocidos pasada explícitamente a <xref:System.Runtime.Serialization.DataContractSerializer> durante la construcción, si se utiliza directamente el serializador.

Cada uno de estos mecanismos aumenta el área de superficie introduciendo más tipos que el deserializador puede cargar. Controle cada uno de estos mecanismos para asegurarse de que ningún tipo malintencionado o imprevisto se agregue a la lista de tipos conocidos.

Una vez un tipo conocido está en el ámbito, se puede cargar en cualquier momento y se pueden crear las instancias del tipo, aun cuando el contrato prohíba realmente utilizarlo. Por ejemplo, suponga que el tipo "MyDangerousType" se agregue a la lista de tipos conocidos utilizando uno de los mecanismos anteriores. Esto significa que:

- Se carga`MyDangerousType` y su constructor de clase se ejecuta.

- Incluso al deserializar un contrato de datos con un miembro de datos de cadena, un mensaje malintencionado puede provocar la creación de una instancia de `MyDangerousType` . El código en `MyDangerousType`, como establecedores de propiedades, se puede ejecutar. Una vez hecho, el deserializador intenta asignar esta instancia al miembro de dato de cadena y se produce un error con una excepción.

Al escribir un método que devuelve una lista de tipos conocidos o al pasar directamente una lista al constructor <xref:System.Runtime.Serialization.DataContractSerializer> , asegúrese de que el código que prepara la lista sea seguro y funcione solo en datos que sean de confianza.

Si especifica los tipos conocidos en configuración, asegúrese de que el archivo de configuración sea seguro. Utilice siempre nombres seguros en configuración (especificando la clave pública del ensamblado firmado donde el tipo reside), pero no especifique la versión del tipo a cargar. El cargador de tipo escoge automáticamente la última versión, si es posible. Si especifica una versión determinada en configuración, corre el riesgo siguiente: un tipo puede tener una vulnerabilidad de seguridad que se puede fijar en una versión futura, pero la versión vulnerable todavía se carga porque está explícitamente especificado en configuración.

Tener demasiados tipos conocidos tiene otra consecuencia: <xref:System.Runtime.Serialization.DataContractSerializer> crea una memoria caché de código de serialización/deserialización en el dominio de aplicación, con una entrada para cada tipo que debe serializar y deserializar. Esta memoria caché nunca se borra mientras se esté ejecutando el dominio de aplicación. Por consiguiente, un atacante que es consciente que una aplicación utiliza muchos tipos conocidos puede desencadenar la deserialización de todos estos tipos, haciendo que la caché utilice una cantidad desproporcionadamente grande de memoria.

### <a name="preventing-types-from-being-in-an-unintended-state"></a>Evitando que los tipos estén en un estado imprevisto

Un tipo puede tener restricciones de coherencia internas que se deban cumplir. Se debe proceder con cuidado para evitar la ruptura de estas restricciones durante la deserialización.

El siguiente ejemplo de un tipo representa el estado de una cámara estanca en una nave espacial y exige la restricción de que las puertas internas y externas no pueden abrirse al mismo tiempo.

[!code-csharp[DataContractAttribute#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/datacontractattribute/cs/overview.cs#3)]
[!code-vb[DataContractAttribute#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/datacontractattribute/vb/overview.vb#3)]

Un atacante puede enviar un mensaje malintencionado como esté, evitando las restricciones y poniendo el objeto en un estado no válido, lo que puede tener consecuencias imprevistas e imprevisibles.

```xml
<SpaceStationAirlock>
    <innerDoorOpen>true</innerDoorOpen>
    <outerDoorOpen>true</outerDoorOpen>
</SpaceStationAirlock>
```

Esta situación se puede evitar siendo consciente de los puntos siguientes:

- Cuando <xref:System.Runtime.Serialization.DataContractSerializer> deserializa la mayoría de las clases, los constructores no se ejecutan. Por consiguiente, no confíe en cualquier administración de estados hecha en el constructor.

- Utilice las devoluciones de llamada para asegurarse de que el objeto esté en un estado válido. La devolución de llamada marcada con el atributo <xref:System.Runtime.Serialization.OnDeserializedAttribute> es especialmente útil porque se ejecuta después de que la deserialización se haya completado y tiene una oportunidad para examinar y corregir el estado total. Para obtener más información, consulte [devoluciones de llamada de serialización tolerante a versiones](version-tolerant-serialization-callbacks.md).

- No diseñe los tipos de contrato de datos para confiar en cualquier orden determinado en el que se deba llamar a los establecedores de propiedad.

- Tenga cuidado utilizando los tipos heredados marcado con el atributo <xref:System.SerializableAttribute> . Muchos de ellos se diseñaron para trabajar con .NET Framework la comunicación remota para su uso solo con datos de confianza. Los tipos existentes marcados con este atributo pueden no haber sido diseñados con la seguridad del estado en mente.

- No confíe en la propiedad <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> del atributo <xref:System.Runtime.Serialization.DataMemberAttribute> para garantizar la presencia de datos en lo relativo a la seguridad del estado. Los datos siempre podrían ser `null`, `zero`o `invalid`.

- Nunca confíe en un gráfico de objeto deserializado de un origen de datos que no es de confianza sin validarlo primero. Cada objeto individual puede estar en un estado coherente, pero el gráfico de objeto en conjunto puede no estarlo. Además, aun cuando el modo de preservación de gráfico de objeto está deshabilitado, el gráfico deserializado puede tener varias referencias al mismo objeto o tener referencias circulares. Para obtener más información, vea [serialización y deserialización](serialization-and-deserialization.md).

### <a name="using-the-netdatacontractserializer-securely"></a>Utilizar NetDataContractSerializer con seguridad

<xref:System.Runtime.Serialization.NetDataContractSerializer> es un motor de serialización que utiliza el acoplamiento apretado a los tipos. Es similar a <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> y <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>. Es decir, determina el tipo del que se crea una instancia leyendo el .NET Framework ensamblado y el nombre de tipo de los datos entrantes. Aunque forma parte de WCF, no hay ninguna manera proporcionada de conectarse a este motor de serialización; se debe escribir código personalizado. `NetDataContractSerializer`Se proporciona principalmente para facilitar la migración de .NET Framework comunicación remota a WCF. Para obtener más información, vea la sección correspondiente en [serialización y deserialización](serialization-and-deserialization.md).

Dado que el propio mensaje puede indicar que se puede cargar cualquier tipo, el mecanismo <xref:System.Runtime.Serialization.NetDataContractSerializer> es inherentemente inseguro y debería utilizarse solo con datos que sean de confianza. Para obtener más información, vea la [Guía de seguridad BinaryFormatter](../../../standard/serialization/binaryformatter-security-guide.md).

Incluso cuando se utiliza con datos que son de confianza, los datos entrantes pueden especificar de forma insuficiente el tipo que se debe cargar, sobre todo si la propiedad <xref:System.Runtime.Serialization.NetDataContractSerializer.AssemblyFormat%2A> está establecida en <xref:System.Runtime.Serialization.Formatters.FormatterAssemblyStyle.Simple>. Cualquiera con acceso al directorio de la aplicación o a la caché global de ensamblados puede sustituir un tipo malintencionado en lugar del que se supone que debe cargarse. Garantice siempre la seguridad del directorio de su aplicación y de la caché global de ensamblados estableciendo correctamente los permisos.

En general, si permite que el código de confianza parcial tenga acceso a la instancia de `NetDataContractSerializer` o controle de algún otro modo el selector de suplentes (<xref:System.Runtime.Serialization.ISurrogateSelector>) o el enlazador de serialización (<xref:System.Runtime.Serialization.SerializationBinder>), el código puede ejercer un gran control sobre el proceso de serialización o deserialización. Por ejemplo, puede insertar tipos arbitrarios, provocar la divulgación de información, manipular el gráfico de objetos resultante o los datos serializados, o bien desbordar la secuencia serializada resultante.

Otra preocupación de seguridad con `NetDataContractSerializer` es una denegación de servicio, no una amenaza de ejecución de código malintencionado. Al utilizar `NetDataContractSerializer`, establezca siempre la cuota <xref:System.Runtime.Serialization.NetDataContractSerializer.MaxItemsInObjectGraph%2A> en un valor seguro. Es fácil construir un mensaje malintencionado pequeño que asigne una matriz de objetos cuyo tamaño está solo limitado por esta cuota.

### <a name="xmlserializer-specific-threats"></a>Amenazas específicas de XmlSerializer

El modelo de seguridad <xref:System.Xml.Serialization.XmlSerializer> es similar al de <xref:System.Runtime.Serialization.DataContractSerializer>. Sin embargo, algunas amenazas son exclusivas de <xref:System.Xml.Serialization.XmlSerializer>.

<xref:System.Xml.Serialization.XmlSerializer> genera *ensamblados de serialización* en tiempo de ejecución que contienen código que realmente serializa y deserializa; estos ensamblados se crean en un directorio de archivos temporales. Si algún otro proceso o usuario tiene derechos de acceso a ese directorio, pueden sobrescribir el código de serialización/deserialización con código arbitrario. <xref:System.Xml.Serialization.XmlSerializer> ejecuta a continuación este código utilizando su contexto de seguridad, en lugar del código de serialización/deserialización. Asegúrese de que los permisos estén correctamente establecidos en el directorio de archivos temporales para evitar que esto suceda.

<xref:System.Xml.Serialization.XmlSerializer> también tiene un modo en el que utiliza los ensamblados de serialización generados previamente en lugar de generarlos en tiempo de ejecución. Este modo se activa cuando <xref:System.Xml.Serialization.XmlSerializer> puede encontrar un ensamblado de serialización conveniente. <xref:System.Xml.Serialization.XmlSerializer> comprueba si se firmó o no el ensamblado de serialización con la misma clave utilizada para firmar el ensamblado que contiene los tipos que se están serializando. Esto proporciona protección e impide que los ensamblados malintencionados se oculten como ensamblados de serialización. Sin embargo, si no se firma el ensamblado que contiene los tipos serializables, <xref:System.Xml.Serialization.XmlSerializer> no puede realizar esta comprobación y utiliza cualquier ensamblado con el nombre correcto. Esto hace que sea posible ejecutar código malintencionado. Firme siempre los ensamblados que contienen sus tipos serializables o controle bien el acceso al directorio de su aplicación y la caché global de ensamblados para evitar la introducción de ensamblados malintencionados.

<xref:System.Xml.Serialization.XmlSerializer> puede estar sujeto a un ataque por denegación de servicio. <xref:System.Xml.Serialization.XmlSerializer> no tiene una cuota `MaxItemsInObjectGraph` (como está disponible en <xref:System.Runtime.Serialization.DataContractSerializer>). Por lo tanto, deserializará una cantidad arbitraria de objetos, limitada solo por el tamaño del mensaje.

### <a name="partial-trust-threats"></a>Otras amenazas de confianza parcial

Tenga en cuenta las preocupaciones siguientes con respecto a las amenazas de código ejecutado con confianza parcial. Estas amenazas incluyen el código malintencionado de confianza parcial así como el código malintencionado de confianza parcial en combinación con otros escenarios de ataque, por ejemplo, código de confianza parcial que construye una cadena concreta y después la deserializa.

- Al utilizar cualquier componente de serialización, nunca valide ningún permiso antes del uso, incluso si el escenario de serialización completo esté dentro del ámbito de su validez y no esté tratando con datos u objetos que no son de confianza. Tal uso puede provocar vulnerabilidades de seguridad.

- En los casos en los que el código de confianza parcial tiene control sobre el proceso de serialización, bien a través de puntos de extensibilidad (suplentes), tipos que se están serializando o de otra manera, el código de confianza parcial puede provocar que el serializador produzca una gran cantidad de datos en la secuencia serializada, lo que podría dar lugar a la denegación del servicio (DoS) al receptor de la secuencia. Si serializa datos previstos para un destino vulnerable a las amenazas de denegación de servicio, no serialice tipos de confianza parcial o bien permita que el código de confianza parcial controle la serialización.

- Si permite el acceso del código de confianza parcial a la <xref:System.Runtime.Serialization.DataContractSerializer> instancia de o controle de algún otro modo los [suplentes del contrato de datos](../extending/data-contract-surrogates.md), puede ejercer un gran control sobre el proceso de serialización y deserialización. Por ejemplo, puede insertar tipos arbitrarios, provocar la divulgación de información, manipular el gráfico de objetos resultante o los datos serializados, o bien desbordar la secuencia serializada resultante. Se describe una amenaza <xref:System.Runtime.Serialization.NetDataContractSerializer> equivalente en la sección "Utilizar NetDataContractSerializer con seguridad".

- Si el atributo <xref:System.Runtime.Serialization.DataContractAttribute> se aplica a un tipo (o el tipo marcado como <xref:System.SerializableAttribute> pero no es <xref:System.Runtime.Serialization.ISerializable>), el deserializador puede crear una instancia de este tipo aun cuando todos los constructores no sean públicos o estén protegidos por peticiones.

- Nunca confíe en el resultado de la deserialización salvo que los datos que se deserializan sean de confianza y esté seguro de que todos los tipos conocidos son de su confianza. Tenga en cuenta que cuando se realiza la ejecución en confianza parcial, los tipos conocidos no se cargan desde el archivo de configuración de la aplicación, sino desde el archivo de configuración del equipo.

- Si pasa una instancia de <xref:System.Runtime.Serialization.DataContractSerializer> con un suplente agregado a un código de confianza parcial, el código puede cambiar cualquier valor modificable de ese suplente.

- Para un objeto deserializado, si el lector XML (o los datos que contiene) procede del código de confianza parcial, trate el objeto deserializado resultante como datos que no son de confianza.

- El hecho de que el tipo <xref:System.Runtime.Serialization.ExtensionDataObject> no tenga ningún miembro público no significa que los datos dentro de él sean seguros. Por ejemplo, si deserializa desde un origen de datos privilegiado a un objeto en el que residen algunos datos, entregue el objeto al código de confianza parcial, éste puede leer los datos del `ExtensionDataObject` serializando el objeto. Considere establecer <xref:System.Runtime.Serialization.DataContractSerializer.IgnoreExtensionDataObject%2A> en `true` cuando realice la deserialización desde un origen de datos con privilegios en un objeto que se pase después al código de confianza parcial.

- <xref:System.Runtime.Serialization.DataContractSerializer> y <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> admiten la serialización de miembros privados, protegidos, internos y públicos con plena confianza. Sin embargo, en confianza parcial, solo se pueden serializar los miembros públicos. Se inicia una excepción <xref:System.Security.SecurityException> si una aplicación intenta serializar un miembro no público.

    Para permitir la serialización de los miembros internos o los miembros internos protegidos con confianza parcial, utilice el atributo de ensamblado <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> . Este atributo permite a un ensamblado declarar que sus miembros internos están visibles para algún otro ensamblado. En este caso, un ensamblado que desee la serialización de sus miembros internos declara que sus miembros internos estén visibles para System.Runtime.Serialization.dll.

    La ventaja de este enfoque es que no requiere una ruta de acceso de generación de código elevada.

    Al mismo tiempo, hay dos inconvenientes importantes.

    El primero es que la propiedad de participación del atributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> afecta a todo el ensamblado. Es decir, no puede especificar que solo se serialicen los miembros internos de una clase determinada. No cabe duda de que todavía puede decidir no serializar un miembro interno concreto. Basta con no agregar un atributo <xref:System.Runtime.Serialization.DataMemberAttribute> a ese miembro. De igual forma, un desarrollador también puede decidir que un miembro sea interno en lugar de privado o protegido, con ligeros problemas de visibilidad.

    El segundo inconveniente es que todavía no se admiten miembros privados o protegidos.

    Para mostrar el uso del atributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> en confianza parcial, considere el siguiente programa:

    [!code-csharp[CDF_WCF_SecurityConsiderationsForData#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/cdf_wcf_securityconsiderationsfordata/cs/program.cs#1)]

    En el ejemplo anterior, `PermissionsHelper.InternetZone` corresponde a <xref:System.Security.PermissionSet> para confianza parcial. Ahora, sin el <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> atributo, se producirá un error en la aplicación y se iniciará una excepción que <xref:System.Security.SecurityException> indica que los miembros no públicos no se pueden serializar en confianza parcial.

    Sin embargo, si agregamos la siguiente línea al archivo de código fuente, el programa se ejecuta correctamente.

    [!code-csharp[CDF_WCF_SecurityConsiderationsForData#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/cdf_wcf_securityconsiderationsfordata/cs/program.cs#2)]

## <a name="other-state-management-concerns"></a>Otros problemas relativos a la administración de estados

Cabe mencionar otros problemas relacionados con la administración de los estados de objeto:

- Al utilizar el modelo de programación basado en secuencias con un transporte de transmisión por secuencias, el procesamiento del mensaje se produce cuando llega el mensaje. El remitente del mensaje puede anular la operación de envío en medio de la secuencia, dejando su código en un estado imprevisible si se esperaba más contenido. En general, no confíe en que la secuencia sea completa y no realice ningún trabajo en una operación basada en secuencias que no se pueda deshacer en caso de que se anule la secuencia. Esto también se aplica a la situación donde un mensaje puede estar malformado después del cuerpo de transmisión por secuencias (por ejemplo, puede faltar una etiqueta de cierre para el sobre SOAP o puede tener un segundo cuerpo del mensaje).

- Utilizar la característica `IExtensibleDataObject` puede provocar que se emitan datos confidenciales. Si está aceptando datos desde un origen que no es de confianza a los contratos de datos con `IExtensibleObjectData` y después vuelve a emitir en un canal seguro en el que se firman los mensajes, está respondiendo potencialmente de datos sobre los que no sabe absolutamente nada. Es más, el estado total que está enviando puede no ser válido si tiene en cuenta tanto las partes conocidas como desconocidas de los datos. Evite esta situación estableciendo selectivamente la propiedad de datos de extensión en `null` o deshabilitando selectivamente la característica `IExtensibleObjectData` .

## <a name="schema-import"></a>Importación de esquema

Normalmente, el proceso de importar el esquema para generar los tipos solo sucede en tiempo de diseño, por ejemplo, al usar [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) en un servicio Web para generar una clase de cliente. Sin embargo, en escenarios más avanzados, puede procesar el esquema en tiempo de ejecución. Tenga en cuenta que hacerlo puede exponerle a los riesgos de la denegación de servicio. Algunos esquemas pueden tardar mucho tiempo en importarse. No utilice nunca el componente de importación de esquema <xref:System.Xml.Serialization.XmlSerializer> en tales escenarios si es posible que los esquemas procedan de un origen que no es de confianza.

## <a name="threats-specific-to-aspnet-ajax-integration"></a>Amenazas específicas de la integración de AJAX de ASP.NET

Cuando el usuario implementa <xref:System.ServiceModel.Description.WebScriptEnablingBehavior> o <xref:System.ServiceModel.Description.WebHttpBehavior> , WCF expone un punto de conexión que puede aceptar mensajes XML y JSON. No obstante, solo existe un conjunto de cuotas de lector, utilizado tanto por el lector XML como por el lector JSON. Algunos valores de cuota pueden ser apropiados para un lector pero demasiado grandes para otro.

Al implementar `WebScriptEnablingBehavior`, el usuario tiene la opción de exponer un proxy de JavaScript en el extremo. Deben tenerse en cuenta las siguientes cuestiones relacionadas con la seguridad:

- Puede obtenerse información acerca del servicio (nombres de operación, nombres de parámetro, etc.) mediante el examen del proxy de JavaScript.

- Al utilizar el extremo de JavaScript, la información confidencial y privada puede retenerse en la memoria caché del explorador web cliente.

## <a name="a-note-on-components"></a>Un nota sobre componentes

WCF es un sistema flexible y personalizable. La mayor parte del contenido de este tema se centra en los escenarios de uso más comunes de WCF. Sin embargo, es posible crear componentes que WCF proporciona de muchas maneras diferentes. Es importante entender las implicaciones de seguridad de utilizar cada componente. En concreto:

- Cuando deba utilizar lectores XML, utilice los lectores que la clase <xref:System.Xml.XmlDictionaryReader> proporciona en oposición a cualquier otro lector. Los lectores seguros se crean utilizando los métodos <xref:System.Xml.XmlDictionaryReader.CreateTextReader%2A>, <xref:System.Xml.XmlDictionaryReader.CreateBinaryReader%2A>o <xref:System.Xml.XmlDictionaryReader.CreateMtomReader%2A> . No utilice el método <xref:System.Xml.XmlReader.Create%2A> . Configure siempre los lectores con cuotas seguras. Los motores de serialización en WCF solo son seguros cuando se utilizan con lectores XML seguros de WCF.

- Al utilizar <xref:System.Runtime.Serialization.DataContractSerializer> para deserializar los datos que potencialmente no son de confianza, establezca siempre la propiedad <xref:System.Runtime.Serialization.DataContractSerializer.MaxItemsInObjectGraph%2A> .

- Al crear un mensaje, establezca el parámetro `maxSizeOfHeaders` si `MaxReceivedMessageSize` no proporciona protección suficiente.

- Al crear un codificador, configure siempre las cuotas pertinentes, como `MaxSessionSize` y `MaxBufferSize`.

- Al utilizar un filtro de mensajes XPath, establezca <xref:System.ServiceModel.Dispatcher.XPathMessageFilter.NodeQuota%2A> para limitar la cantidad de nodos XML que el filtro visita. No utilice expresiones XPath que podrían tardar mucho tiempo en calcularse sin visitar muchos nodos.

- En general, al utilizar cualquier componente que acepte una cuota, entienda sus implicaciones de seguridad y establézcalo en un valor seguro.

## <a name="see-also"></a>Consulte también

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.Xml.XmlDictionaryReader>
- <xref:System.Xml.Serialization.XmlSerializer>
- [Tipos conocidos de contratos de datos](data-contract-known-types.md)
