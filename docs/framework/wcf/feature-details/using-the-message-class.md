---
title: Uso de la clase de mensajes
description: Obtenga información sobre la clase de mensaje, que es fundamental para WCF. Solo necesita programar con la clase Message directamente en algunos escenarios avanzados.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d1d62bfb-2aa3-4170-b6f8-c93d3afdbbed
ms.openlocfilehash: fd19256b571727883dd877f0094f180ec47c6d63
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96289391"
---
# <a name="using-the-message-class"></a>Uso de la clase de mensajes

La <xref:System.ServiceModel.Channels.Message> clase es fundamental para Windows Communication Foundation (WCF). Toda la comunicación entre clientes y servicios, en última instancia, produce como resultado instancias <xref:System.ServiceModel.Channels.Message> que se envían y reciben.  
  
 Normalmente no interactuaría directamente con la clase <xref:System.ServiceModel.Channels.Message>. En su lugar, se usan construcciones de modelo de servicio de WCF, como contratos de datos, contratos de mensajes y contratos de operaciones, para describir los mensajes entrantes y salientes. Sin embargo, en algunos escenarios avanzados puede programar utilizando directamente la clase <xref:System.ServiceModel.Channels.Message>. Por ejemplo, es posible que desee usar la clase <xref:System.ServiceModel.Channels.Message>:  
  
- Cuando se necesita una forma alternativa de crear el contenido de los mensajes salientes (por ejemplo, crear un mensaje directamente a partir de un archivo en disco) en lugar de serializar .NET Framework objetos.  
  
- Cuando se necesita una forma alternativa de usar el contenido de los mensajes entrantes (por ejemplo, cuando se desea aplicar una transformación XSLT al contenido XML sin formato) en lugar de deserializar en objetos .NET Framework.  
  
- Cuando necesite tratar con mensajes de una manera general sin tener en cuenta el contenido del mensaje (por ejemplo, cuando enrute o reenvíe mensajes al crear un enrutador, equilibrador de carga o un sistema publicación-suscripción  
  
 Antes de usar la <xref:System.ServiceModel.Channels.Message> clase, familiarícese con la arquitectura de transferencia de datos de WCF en [transferencia de datos información general sobre la arquitectura](data-transfer-architectural-overview.md).  
  
 <xref:System.ServiceModel.Channels.Message> es un contenedor de uso general para los datos, pero su diseño sigue estrechamente el diseño de un mensaje en el protocolo SOAP. Simplemente como en SOAP, un mensaje tiene un cuerpo de mensaje y encabezados. El cuerpo del mensaje contiene los datos de carga reales, mientras que los encabezados contienen los contenedores de datos con nombre adicionales. Las reglas para leer y escribir el cuerpo y los encabezados son diferentes; Por ejemplo, los encabezados están almacenados siempre en memoria búfer y se puede tener acceso a ellos todas las veces que se quiera, mientras que el cuerpo se puede leer solo una vez y puede ser transmitido. Normalmente, cuando se utiliza SOAP, el cuerpo del mensaje está asignado al cuerpo SOAP y los encabezados del mensaje están asignados a los encabezados SOAP.  
  
## <a name="using-the-message-class-in-operations"></a>Utilizar la clase de mensaje en Operaciones  

 Puede utilizar la clase <xref:System.ServiceModel.Channels.Message> como un parámetro de entrada de una operación, el valor devuelto de una operación, o ambos. Si <xref:System.ServiceModel.Channels.Message> se utiliza en cualquier parte en una operación, se aplican las restricciones siguientes:  
  
- La operación no puede tener ningún `out` o parámetro `ref`.  
  
- No puede haber más de un parámetro `input`. Si el parámetro está presente, debe ser Mensaje o un tipo de contrato de mensaje.  
  
- El tipo de valor devuelto debe ser `void`, `Message`o un tipo de contrato de mensaje.  
  
 El ejemplo de código siguiente contiene un contrato de operación válido.  
  
 [!code-csharp[C_UsingTheMessageClass#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_usingthemessageclass/cs/source.cs#1)]
 [!code-vb[C_UsingTheMessageClass#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_usingthemessageclass/vb/source.vb#1)]  
  
## <a name="creating-basic-messages"></a>Creación de mensajes básicos  

 La clase <xref:System.ServiceModel.Channels.Message> proporciona métodos de generación estáticos `CreateMessage` que se pueden usar para crear mensajes básicos.  
  
 Todas las sobrecargas `CreateMessage` toman un parámetro de versión de tipo <xref:System.ServiceModel.Channels.MessageVersion> que indica el SOAP y versiones de WS-Addressing para utilizarlas para el mensaje. Si desea utilizar las mismas versiones de protocolo que el mensaje de entrada, puede utilizar la propiedad <xref:System.ServiceModel.OperationContext.IncomingMessageVersion%2A> en la instancia <xref:System.ServiceModel.OperationContext> obtenida de la propiedad <xref:System.ServiceModel.OperationContext.Current%2A>. La mayoría de las sobrecargas `CreateMessage` también tienen un parámetro de cadena que indica la acción SOAP que se utilizará en el mensaje. La versión se puede establecer en `None` para deshabilitar la generación de la envoltura SOAP; el mensaje solamente se compone del cuerpo.  
  
## <a name="creating-messages-from-objects"></a>Crear mensajes a partir de objetos  

 La sobrecarga `CreateMessage` más básica que toma solo una versión y una acción crea un mensaje con un cuerpo vacío. Otra sobrecarga toma un parámetro <xref:System.Object> adicional; esto crea un mensaje cuyo cuerpo es la representación serializada del objeto determinado. Utilice <xref:System.Runtime.Serialization.DataContractSerializer> con configuración predeterminada para la serialización. Si desea utilizar un serializador diferente, o quiere que `DataContractSerializer` se configure de manera diferente, utilice la sobrecarga `CreateMessage` que también toma un parámetro `XmlObjectSerializer`.  
  
 Por ejemplo, para devolver un objeto en un mensaje, puede utilizar el siguiente código.  
  
 [!code-csharp[C_UsingTheMessageClass#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_usingthemessageclass/cs/source.cs#2)]
 [!code-vb[C_UsingTheMessageClass#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_usingthemessageclass/vb/source.vb#2)]  
  
## <a name="creating-messages-from-xml-readers"></a>Crear los mensajes a partir de los lectores XML  

 Hay sobrecargas `CreateMessage` que toman <xref:System.Xml.XmlReader> o <xref:System.Xml.XmlDictionaryReader> para el cuerpo en lugar de un objeto. En este caso, el cuerpo del mensaje contiene el XML que se obtiene al leer con el lector XML pasado. Por ejemplo, el código siguiente devuelve un mensaje con el contenido del cuerpo leído desde un archivo XML.  
  
 [!code-csharp[C_UsingTheMessageClass#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_usingthemessageclass/cs/source.cs#3)]
 [!code-vb[C_UsingTheMessageClass#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_usingthemessageclass/vb/source.vb#3)]  
  
 Hay además, sobrecargas `CreateMessage` que toman <xref:System.Xml.XmlReader> o <xref:System.Xml.XmlDictionaryReader> que representa el mensaje completo y no simplemente el cuerpo. Estas sobrecargas también toman un parámetro `maxSizeOfHeaders` entero. Los encabezados siempre se almacenan en búfer en la memoria en cuanto se crea el mensaje, y este parámetro limita la cantidad de almacenamiento en búfer que tiene lugar. Es importante establecer este parámetro en un valor seguro si el XML procede de un origen que no es de confianza para mitigar la posibilidad de un ataque por denegación de servicio. El SOAP y versiones de WS-Addressing del mensaje que el lector XML representa deben coincidir con las versiones indicadas utilizando el parámetro de versión.  
  
## <a name="creating-messages-with-bodywriter"></a>Crear los mensajes con BodyWriter  

 Una sobrecarga `CreateMessage` toma una instancia `BodyWriter` para describir el cuerpo del mensaje. `BodyWriter` es una clase abstracta que se puede derivar para personalizar cómo se crean los cuerpos del mensaje. Puede crear su propia clase `BodyWriter` derivada para describir los cuerpos del mensaje de una manera personalizada. Debe invalidar el método `BodyWriter.OnWriteBodyContents` que toma <xref:System.Xml.XmlDictionaryWriter>; este método es el responsable de la escritura del cuerpo.  
  
 Los sistemas de escritura del cuerpo se pueden almacenar en búfer o no (se pueden transmitir por secuencias). Los sistemas de escritura del cuerpo almacenados en búfer pueden escribir su contenido todas las veces que se quiera, mientras que los transmitidos solo pueden escribir sus contenidos una vez. La propiedad `IsBuffered` indica si un sistema de escritura del cuerpo está almacenado en búfer o no. Puede establecerlo para su sistema de escritura de cuerpo mediante una llamada al constructor `BodyWriter` protegido que toma un parámetro booleano `isBuffered`. Los sistemas de escritura de cuerpo permiten crear un sistema de escritura de cuerpo almacenado en búfer a partir de un sistema de escritura de cuerpo no almacenado en búfer. Puede invalidar el método `OnCreateBufferedCopy` para personalizar este proceso. De forma predeterminada, se usa un búfer en memoria que contiene el XML devuelto por `OnWriteBodyContents`. `OnCreateBufferedCopy` toma un parámetro entero `maxBufferSize`; si invalida este método, no debe crear búferes mayores que este tamaño máximo.  
  
 La clase `BodyWriter` proporciona respectivamente `WriteBodyContents` y los métodos `CreateBufferedCopy`, que son contenedores esencialmente delgados alrededor de `OnWriteBodyContents` y los métodos `OnCreateBufferedCopy`. Estos métodos realizan la comprobación de estado para asegurarse de que no se tiene acceso a un sistema de escritura de cuerpo no almacenado en búfer más de una vez. Solo se llama a estos métodos directamente al crear clases `Message` derivadas personalizadas basadas en `BodyWriters`.  
  
## <a name="creating-fault-messages"></a>Crear los mensajes de error  

 Puede utilizar ciertas sobrecargas `CreateMessage` para crear los mensajes del error de SOAP. La más básica toma un objeto <xref:System.ServiceModel.Channels.MessageFault> que describe el error. Otras sobrecargas se proporcionan para comodidad. La primera sobrecarga toma `FaultCode` y una cadena de la razón y crea `MessageFault` mediante `MessageFault.CreateFault` mediante esta información. La otra sobrecarga toma un objeto de datos y también lo pasa a `CreateFault` junto con el código de error y la razón. Por ejemplo, la operación siguiente devuelve un error.  
  
 [!code-csharp[C_UsingTheMessageClass#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_usingthemessageclass/cs/source.cs#4)]
 [!code-vb[C_UsingTheMessageClass#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_usingthemessageclass/vb/source.vb#4)]  
  
## <a name="extracting-message-body-data"></a>Extraer los datos del cuerpo del mensaje  

 La clase `Message` admite varias maneras de extraer información de su cuerpo. Éstos pueden estar clasificados en las categorías siguientes:  
  
- Obtener el cuerpo del mensaje completo escrito de una vez en un sistema de escritura de XML. Esto se conoce como *escribir un mensaje*.  
  
- Obtener un lector XML sobre el cuerpo del mensaje. Esto le permite al acceso posterior el cuerpo del mensaje parte por parte, según se requiera. Esto se conoce como *leer un mensaje*.  
  
- El mensaje completo, incluido su cuerpo, se puede copiar en un búfer en memoria del tipo <xref:System.ServiceModel.Channels.MessageBuffer>. Esto se conoce como *copia de un mensaje*.  
  
 Solo puede tener acceso una vez al cuerpo de `Message`, independientemente de cómo se tiene acceso. Un objeto de mensaje tiene una propiedad `State`, la cual se establece inicialmente en Creada. Los tres métodos de acceso descritos en la lista anterior establecen el estado en Escrito, Leído, y Copiado, respectivamente. Además, un método `Close` puede establecer el estado en Cerrado cuando ya no se necesita el contenido del cuerpo del mensaje. Se puede tener acceso al cuerpo del mensaje solo en el estado Creado y no hay ninguna manera de regresar al estado Creado después de que el estado haya cambiado.  
  
## <a name="writing-messages"></a>Escribir los mensajes  

 El método <xref:System.ServiceModel.Channels.Message.WriteBodyContents%28System.Xml.XmlDictionaryWriter%29> escribe el contenido del cuerpo de un `Message` determinado cree instancias a un sistema de escritura XML determinado. El <xref:System.ServiceModel.Channels.Message.WriteBody%2A> método hace lo mismo, salvo que incluye el contenido del cuerpo en el elemento contenedor adecuado (por ejemplo, <`soap:body`>). Finalmente, <xref:System.ServiceModel.Channels.Message.WriteMessage%2A> escribe el mensaje completo, incluso la envoltura SOAP de ajuste y los encabezados. Si SOAP está desactivado ( <xref:System.ServiceModel.Channels.Message.Version> es <xref:System.ServiceModel.Channels.MessageVersion.None?displayProperty=nameWithType> ), los tres métodos hacen lo mismo: escriben el contenido del cuerpo del mensaje.  
  
 Por ejemplo, el código siguiente escribe el cuerpo de un mensaje de entrada en un archivo.  
  
 [!code-csharp[C_UsingTheMessageClass#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_usingthemessageclass/cs/source.cs#5)]
 [!code-vb[C_UsingTheMessageClass#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_usingthemessageclass/vb/source.vb#5)]  
  
 Dos métodos del asistente adicionales escriben ciertas etiquetas de elemento de inicio de SOAP. Estos métodos no tienen acceso al cuerpo del mensaje, de modo que no cambian el estado del mensaje. Se incluyen los siguientes:  
  
- <xref:System.ServiceModel.Channels.Message.WriteStartBody%2A> escribe el elemento de cuerpo de inicio, por ejemplo, `<soap:Body>`.  
  
- <xref:System.ServiceModel.Channels.Message.WriteStartEnvelope%2A> escribe el elemento de envoltura de inicio, por ejemplo, `<soap:Envelope>`.  
  
 Para escribir las etiquetas de elementos finales correspondientes, llame `WriteEndElement` en el sistema de escritura XML correspondiente. Rara vez se llama a estos métodos directamente.  
  
## <a name="reading-messages"></a>Leer mensajes  

 La manera principal para leer un cuerpo del mensaje es llamar <xref:System.ServiceModel.Channels.Message.GetReaderAtBodyContents%2A>. Se recibe <xref:System.Xml.XmlDictionaryReader>, que se puede usar para leer el cuerpo del mensaje. Tenga en cuenta que <xref:System.ServiceModel.Channels.Message> pasa al estado Leído en cuanto se llama a <xref:System.ServiceModel.Channels.Message.GetReaderAtBodyContents%2A> y no cuando se usa el lector XML devuelto.  
  
 El método <xref:System.ServiceModel.Channels.Message.GetBody%2A> también le permite tener acceso al cuerpo del mensaje como un objeto con tipo. Internamente, este método utiliza `GetReaderAtBodyContents`y así también pasa el estado del mensaje al estado <xref:System.ServiceModel.Channels.MessageState.Read> (vea la propiedad <xref:System.ServiceModel.Channels.Message.State%2A> ).  
  
 Es recomendable comprobar la propiedad <xref:System.ServiceModel.Channels.Message.IsEmpty%2A>, en cuyo caso el cuerpo del mensaje está vacío y <xref:System.ServiceModel.Channels.Message.GetReaderAtBodyContents%2A> inicia <xref:System.InvalidOperationException>. Además, si es un mensaje recibido (por ejemplo, la respuesta), es posible que también desee comprobar <xref:System.ServiceModel.Channels.Message.IsFault%2A>, que indica si el mensaje contiene un error.  
  
 La sobrecarga más básica de <xref:System.ServiceModel.Channels.Message.GetBody%2A> deserializa el cuerpo del mensaje en una instancia de un tipo (indicado por el parámetro genérico) mediante el uso de un <xref:System.Runtime.Serialization.DataContractSerializer> establecido con la configuración predeterminada y con la cuota <xref:System.Runtime.Serialization.DataContractSerializer.MaxItemsInObjectGraph%2A> deshabilitada. Si desea usar un motor de serialización diferente o configurar `DataContractSerializer` de una manera distinta a la predeterminada, use la sobrecarga <xref:System.ServiceModel.Channels.Message.GetBody%2A> que toma <xref:System.Runtime.Serialization.XmlObjectSerializer>.  
  
 Por ejemplo, el código siguiente extrae los datos de un cuerpo de mensaje que contiene un objeto `Person` serializado e imprime el nombre de la persona.  
  
 [!code-csharp[C_UsingTheMessageClass#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_usingthemessageclass/cs/source.cs#6)]
 [!code-vb[C_UsingTheMessageClass#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_usingthemessageclass/vb/source.vb#6)]  
  
## <a name="copying-a-message-into-a-buffer"></a>Copiar un mensaje en un búfer  

 A veces es necesario tener acceso más de una vez al cuerpo del mensaje, por ejemplo, para reenviar el mismo mensaje a varios destinos como parte de un sistema de publicación-suscripción. En este caso, es necesario almacenar en búfer el mensaje completo (incluido el cuerpo) en memoria. Puede hacerlo llamando <xref:System.ServiceModel.Channels.Message.CreateBufferedCopy%28System.Int32%29>. Este método toma un parámetro entero que representa el tamaño máximo de búfer y crea un búfer inferior a este tamaño. Es importante establecer esto en un valor seguro si el mensaje procede de un origen que no es de confianza.  
  
 Se devuelve el búfer como una instancia <xref:System.ServiceModel.Channels.MessageBuffer>. Puede tener acceso a los datos del búfer de varias maneras. El modo principal es llamar <xref:System.ServiceModel.Channels.Message.CreateMessage%2A> para crear las instancias `Message` a partir del búfer.  
  
 Otra manera de tener acceso a los datos del búfer es implementar la interfaz <xref:System.Xml.XPath.IXPathNavigable> que la clase <xref:System.ServiceModel.Channels.MessageBuffer> implementa para tener acceso directamente al XML subyacente. Algunas sobrecargas <xref:System.ServiceModel.Channels.MessageBuffer.CreateNavigator%2A> permiten crear navegadores <xref:System.Xml.XPath> protegidos por una cuota de nodo que limita el número de nodos XML que se pueden visitar. Esto ayuda a evitar ataques por denegación de servicio en función del tiempo de procesamiento largo. Esta cuota está deshabilitada de forma predeterminada. Algunas sobrecargas `CreateNavigator` le permiten especificar cómo se debería administrar el espacio en blanco en el XML utilizando la enumeración <xref:System.Xml.XmlSpace>, con los valores predeterminados `XmlSpace.None`.  
  
 Una última manera de tener acceso al contenido de un búfer del mensaje es escribir su contenido en una secuencia utilizando <xref:System.ServiceModel.Channels.Message.WriteMessage%2A>.  
  
 El ejemplo siguiente muestra el proceso de trabajar con `MessageBuffer`: un mensaje de entrada se reenvía a varios destinatarios y, a continuación, se registra en un archivo. Sin el almacenamiento en búfer, esto no es posible, porque se puede tener acceso al cuerpo del mensaje una sola vez.  
  
 [!code-csharp[C_UsingTheMessageClass#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_usingthemessageclass/cs/source.cs#7)]
 [!code-vb[C_UsingTheMessageClass#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_usingthemessageclass/vb/source.vb#7)]  
  
 La clase `MessageBuffer` tiene otro miembros que hay que tener en cuenta. Se puede llamar al método <xref:System.ServiceModel.Channels.MessageBuffer.Close%2A> para liberar recursos cuando ya no se requiera el contenido del búfer. La propiedad <xref:System.ServiceModel.Channels.MessageBuffer.BufferSize%2A> devuelve el tamaño del búfer asignado. La propiedad <xref:System.ServiceModel.Channels.MessageBuffer.MessageContentType%2A> devuelve el tipo de contenido de MIME del mensaje.  
  
## <a name="accessing-the-message-body-for-debugging"></a>Tener acceso al cuerpo del mensaje para depuración  

 Para la depuración, puede llamar al método <xref:System.ServiceModel.Channels.Message.ToString%2A> con el fin de obtener una representación del mensaje como una cadena. Esta representación por lo general coincide con la manera en que se mostraría un mensaje en la conexión si estuviera codificado con el codificador de texto, con la excepción de que se le aplicaría un formato más legible que XML. La excepción a esto es el cuerpo del mensaje. El cuerpo se puede leer una sola vez y `ToString` no cambia el estado del mensaje. Por consiguiente, el `ToString` método podría no tener acceso al cuerpo y podría sustituir un marcador de posición (por ejemplo, "..." o tres puntos) en lugar del cuerpo del mensaje. Por consiguiente, no use `ToString` para registrar los mensajes si el contenido del cuerpo de los mensajes es importante.  
  
## <a name="accessing-other-message-parts"></a>Tener acceso a otras partes del mensaje  

 Se proporcionan varias propiedades para tener acceso a la información del mensaje que no sea el contenido del cuerpo. Sin embargo, no se puede llamar a éstos una vez se ha cerrado el mensaje:  
  
- La propiedad <xref:System.ServiceModel.Channels.Message.Headers%2A> representa los encabezados del mensaje. Vea la sección "trabajar con encabezados" más adelante en este tema.  
  
- La propiedad <xref:System.ServiceModel.Channels.Message.Properties%2A> representa las propiedades del mensaje, que son partes de datos con nombre adjuntadas al mensaje que generalmente no se emiten cuando se envía el mensaje. Consulte la sección en "Trabajar con propiedades" más adelante en este tema.  
  
- La propiedad <xref:System.ServiceModel.Channels.Message.Version%2A> indica el SOAP y versión WS-Addressing asociada al mensaje o `None` si SOAP está deshabilitado.  
  
- La propiedad <xref:System.ServiceModel.Channels.Message.IsFault%2A> devuelve `true` si el mensaje es un mensaje de error de SOAP.  
  
- La propiedad <xref:System.ServiceModel.Channels.Message.IsEmpty%2A> devuelve `true` si el mensaje está vacío.  
  
 Puede utilizar el método <xref:System.ServiceModel.Channels.Message.GetBodyAttribute%28System.String%2CSystem.String%29> para tener acceso a un atributo determinado en el elemento contenedor del cuerpo (por ejemplo, `<soap:Body>`) identificado por un nombre y espacio de nombres determinados. Si no se encuentra dicho atributo, se devuelve `null`. Se puede llamar a este método solo cuando `Message` está en el estado Creado (cuando todavía no se ha tenido acceso al cuerpo del mensaje).  
  
## <a name="working-with-headers"></a>Trabajar con encabezados  

 Un `Message` puede contener cualquier número de fragmentos XML con nombre, denominados *encabezados*. Cada fragmento asigna normalmente a un encabezado SOAP. Se tiene acceso a los encabezados a través de la propiedad `Headers` de tipo <xref:System.ServiceModel.Channels.MessageHeaders>. <xref:System.ServiceModel.Channels.MessageHeaders> es una colección de objetos <xref:System.ServiceModel.Channels.MessageHeaderInfo>, y se puede tener acceso a los encabezados individuales a través de su interfaz <xref:System.Collections.IEnumerable> o a través de su indizador. Por ejemplo, el código siguiente hace una lista de los nombres de todos los encabezados en `Message`.  
  
 [!code-csharp[C_UsingTheMessageClass#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_usingthemessageclass/cs/source.cs#8)]
 [!code-vb[C_UsingTheMessageClass#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_usingthemessageclass/vb/source.vb#8)]  
  
#### <a name="adding-removing-finding-headers"></a>Agregar, quitar, buscar encabezados  

 Puede agregar un nuevo encabezado al final de todos los encabezados existentes utilizando el método <xref:System.ServiceModel.Channels.MessageHeaders.Add%2A>. Puede utilizar el método <xref:System.ServiceModel.Channels.MessageHeaders.Insert%2A> para insertar un encabezado en un índice determinado. Los encabezados existentes se desplazan para el elemento insertado. Los encabezados se ordenan según su índice y el primer índice disponible es 0. Puede usar las distintas sobrecargas del método <xref:System.ServiceModel.Channels.MessageHeaders.CopyHeadersFrom%2A> para agregar encabezados de una instancia de `Message` o `MessageHeaders` diferente. Algunas sobrecargas copian un encabezado individual, mientras que otras copian todos ellos. El método <xref:System.ServiceModel.Channels.MessageHeaders.Clear%2A> quita todos los encabezados. El método <xref:System.ServiceModel.Channels.MessageHeaders.RemoveAt%2A> quita un encabezado en un índice determinado (desplazando todos los encabezados después de él). El método <xref:System.ServiceModel.Channels.MessageHeaders.RemoveAll%2A> quita todos los encabezados con un nombre y espacio de nombres determinados.  
  
 Recupere un encabezado determinado mediante el método <xref:System.ServiceModel.Channels.MessageHeaders.FindHeader%2A>. Este método toma el nombre y espacio de nombres del encabezado para buscar y devuelve su índice. Si el encabezado se produce más de una vez, se produce una excepción. Si no se encuentra el encabezado, devuelve -1.  
  
 En el modelo del encabezado SOAP, los encabezados pueden tener un valor `Actor` que especifica el destinatario previsto del encabezado. La sobrecarga `FindHeader` más básica solo busca en los encabezados que están pensados para el receptor definitivo del mensaje. Sin embargo, otra sobrecarga le permite especificar qué valores `Actor` están incluidos en la búsqueda. Para obtener más información, vea la especificación SOAP.  
  
 Se proporciona un método <xref:System.ServiceModel.Channels.MessageHeaders.CopyTo%28System.ServiceModel.Channels.MessageHeaderInfo%5B%5D%2CSystem.Int32%29> para copiar los encabezados de una colección <xref:System.ServiceModel.Channels.MessageHeaders> en una matriz de los objetos <xref:System.ServiceModel.Channels.MessageHeaderInfo>.  
  
 Para tener acceso a los datos XML en un encabezado, puede llamar <xref:System.ServiceModel.Channels.MessageHeaders.GetReaderAtHeader%2A> y devolver un lector XML para el índice del encabezado concreto. Si quiere deserializar el contenido del encabezado en un objeto, utilice <xref:System.ServiceModel.Channels.MessageHeaders.GetHeader%60%601%28System.Int32%29> o una de las otras sobrecargas. Las sobrecargas más básicas deserializan los encabezados mediante el uso del <xref:System.Runtime.Serialization.DataContractSerializer> configurado de la manera predeterminada. Si desea utilizar un serializador diferente o una configuración diferente de `DataContractSerializer`, utilice una de las sobrecargas que toman `XmlObjectSerializer`. También hay sobrecarga que toma el nombre del encabezado, espacio de nombres y opcionalmente una lista de los valores `Actor` en lugar de un índice; ésta es una combinación de `FindHeader` y `GetHeader`.  
  
## <a name="working-with-properties"></a>Trabajar con propiedades  

 Una instancia `Message` puede contener un número arbitrario de objetos con nombre de tipos arbitrarios. Se accede a esta colección a través de la  propiedad`Properties` de tipo `MessageProperties`. La colección implementa la interfaz <xref:System.Collections.Generic.IDictionary%602> y actúa como una asignación de <xref:System.String> a <xref:System.Object>. Normalmente, los valores de propiedad no se asignan directamente a ninguna parte del mensaje en la conexión, sino que proporcionan varias sugerencias de procesamiento de mensajes a los distintos canales de la pila de canales de WCF o al <xref:System.ServiceModel.Channels.MessageHeaders.CopyTo%28System.ServiceModel.Channels.MessageHeaderInfo%5B%5D%2CSystem.Int32%29> marco de trabajo de servicio. Para obtener un ejemplo, consulte [información general sobre la arquitectura de transferencia de datos](data-transfer-architectural-overview.md).  
  
## <a name="inheriting-from-the-message-class"></a>Herencia de la clase de mensaje  

 Si los tipos de mensaje integrados creados mediante `CreateMessage` no cumplen sus requisitos, cree una clase que derive de la clase `Message`.  
  
### <a name="defining-the-message-body-contents"></a>Definir el contenido del cuerpo del mensaje  

 Existen tres técnicas primarias para tener acceso a los datos dentro de un cuerpo del mensaje: escribir, leer y copiar en un búfer. En última instancia, como consecuencia de estas operaciones se llama a los métodos <xref:System.ServiceModel.Channels.Message.OnWriteBodyContents%2A>, <xref:System.ServiceModel.Channels.Message.OnGetReaderAtBodyContents%2A> y <xref:System.ServiceModel.Channels.Message.OnCreateBufferedCopy%2A>, respectivamente, en la clase derivada de `Message`. La clase base `Message` garantiza que se llamará a uno de estos métodos por cada instancia de `Message` y que no se llama más de una vez. La clase base también garantiza que no se llama a los métodos en un mensaje cerrado. No hay ninguna necesidad de realizar el seguimiento del estado del mensaje en su implementación.  
  
 <xref:System.ServiceModel.Channels.Message.OnWriteBodyContents%2A> es un método abstracto y se implementa. La manera más básica de definir el contenido del cuerpo de un mensaje es escribirlo con este método. Por ejemplo, el mensaje siguiente contiene 100,000 números aleatorios de 1 a 20.  
  
 [!code-csharp[C_UsingTheMessageClass#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_usingthemessageclass/cs/source.cs#9)]
 [!code-vb[C_UsingTheMessageClass#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_usingthemessageclass/vb/source.vb#9)]  
  
 <xref:System.ServiceModel.Channels.Message.OnGetReaderAtBodyContents> y los métodos <xref:System.ServiceModel.Channels.Message.OnCreateBufferedCopy%2A> tienen implementaciones predeterminadas que funcionan en la mayoría de los casos.   Las implementaciones predeterminadas llaman a <xref:System.ServiceModel.Channels.Message.OnWriteBodyContents%2A>, almacenan en búfer los resultados y funcionan con el búfer resultante. Sin embargo, en algunos casos esto puede no ser bastante. En el ejemplo anterior, leer el mensaje resulta en 100,000 elementos XML almacenados en búfer, lo cual podría no ser deseable. Es posible que desee invalidar <xref:System.ServiceModel.Channels.Message.OnGetReaderAtBodyContents> para devolver una clase <xref:System.Xml.XmlDictionaryReader> derivada personalizada que proporcione números aleatorios. Después, puede invalidar <xref:System.ServiceModel.Channels.Message.OnWriteBodyContents%2A> para usar el lector que <xref:System.ServiceModel.Channels.Message.OnGetReaderAtBodyContents> devuelve el método, como se muestra en el ejemplo siguiente.  
  
 [!code-csharp[C_UsingTheMessageClass#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_usingthemessageclass/cs/source.cs#10)]
 [!code-vb[C_UsingTheMessageClass#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_usingthemessageclass/vb/source.vb#10)]  
  
 De igual forma, podría desear invalidar `OnCreateBufferedCopy` para devolver su propia clase derivada `MessageBuffer`.  
  
 Además de proporcionar el contenido del cuerpo del mensaje, la clase derivada del mensaje también debe invalidar las propiedades `Version`, `Headers` y `Properties`.  
  
 Tenga en cuenta que si crea una copia de un mensaje, la copia utiliza los encabezados del mensaje del original.  
  
### <a name="other-members-that-can-be-overridden"></a>Otros miembros que se pueden invalidar  

 Puede invalidar los <xref:System.ServiceModel.Channels.Message.OnWriteStartEnvelope%2A> <xref:System.ServiceModel.Channels.Message.OnWriteStartHeaders%2A> métodos, y <xref:System.ServiceModel.Channels.Message.OnWriteStartBody%2A> para especificar cómo se escriben los elementos SOAP Envelope, los encabezados SOAP y las etiquetas de inicio del elemento BODY de SOAP. Normalmente, se corresponden con `<soap:Envelope>` , `<soap:Header>` y `<soap:Body>` . Estos métodos no deberían escribir normalmente nada si la propiedad <xref:System.ServiceModel.Channels.Message.Version> devuelve <xref:System.ServiceModel.Channels.MessageVersion.None>.  
  
> [!NOTE]
> La implementación predeterminada de `OnGetReaderAtBodyContents` llama `OnWriteStartEnvelope` y `OnWriteStartBody` antes de llamar `OnWriteBodyContents` y almacenar en búfer los resultados. Los encabezados no se escriben.  
  
 Invalide el método <xref:System.ServiceModel.Channels.Message.OnWriteMessage%2A> para cambiar la manera de construir el mensaje completo a partir de sus diferentes partes. El método `OnWriteMessage` es llamado por <xref:System.ServiceModel.Channels.Message.WriteMessage%2A> y por la implementación predeterminada <xref:System.ServiceModel.Channels.Message.OnCreateBufferedCopy%2A>. Tenga en cuenta que invalidar <xref:System.ServiceModel.Channels.Message.WriteMessage%2A> no es un procedimiento recomendado. Es mejor invalidar los métodos `On` adecuados (por ejemplo, <xref:System.ServiceModel.Channels.Message.OnWriteStartEnvelope%2A>, <xref:System.ServiceModel.Channels.Message.OnWriteStartHeaders%2A>y <xref:System.ServiceModel.Channels.BodyWriter.OnWriteBodyContents%2A>.  
  
 Invalide <xref:System.ServiceModel.Channels.Message.OnBodyToString%2A> para invalidar cómo se representa el cuerpo del mensaje durante la depuración. El valor predeterminado es representarlo con tres puntos ("..."). Tenga en cuenta que se puede llamar a este método varias veces cuando el estado del mensaje es otro distinto de Cerrado. Una implementación de este método no debería producir nunca una acción que solo se deba realizar una vez (como leer de una secuencia solo hacia adelante).  
  
 Invalide el método <xref:System.ServiceModel.Channels.Message.OnGetBodyAttribute%2A> para permitir el acceso a los atributos en el elemento de cuerpo SOAP. Este método se puede llamar todas las veces que se desee, pero el tipo base `Message` garantiza que solo se llama cuando el mensaje se encuentre en estado Creado. No se requiere para comprobar el estado en una implementación. La implementación predeterminada siempre devuelve `null`, lo que indica que no hay ningún atributo en el elemento del cuerpo.  
  
 Si el objeto `Message` debe llevar a cabo alguna operación de limpieza especial cuando ya no se necesita el cuerpo del mensaje, puede invalidar <xref:System.ServiceModel.Channels.Message.OnClose%2A>. La implementación predeterminada no hace nada.  
  
 `IsEmpty` y las propiedades `IsFault` se pueden invalidar. De forma predeterminada, ambos devuelven `false`.
