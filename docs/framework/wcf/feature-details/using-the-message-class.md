---
title: "Uso de la clase de mensajes | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d1d62bfb-2aa3-4170-b6f8-c93d3afdbbed
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# Uso de la clase de mensajes
El <xref:System.ServiceModel.Channels.Message> es fundamental para la clase [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]. Toda la comunicación entre clientes y servicios resultará finalmente en <xref:System.ServiceModel.Channels.Message> instancias enviadas y recibidas.  
  
 Normalmente no interactuaría con el <xref:System.ServiceModel.Channels.Message> clase directamente. En su lugar, construcciones de modelo de servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], como contratos de datos, contratos del mensaje y contratos de operación, se utilizan para describir los mensajes de entrada y salida. Sin embargo, en algunos escenarios avanzados puede programar utilizando el <xref:System.ServiceModel.Channels.Message> clase directamente. Por ejemplo, puede usar el <xref:System.ServiceModel.Channels.Message> clase:  
  
-   Cuando necesite una manera alternativa de crear el contenido del mensaje saliente (por ejemplo, crear un mensaje directamente a partir de un archivo en disco) en lugar de serializar los objetos [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].  
  
-   Cuando necesite una manera alternativa de utilizar el contenido del mensaje de entrada (por ejemplo, al desear aplicar una transformación XSLT al contenido de XML sin formato) en lugar de deserializar en los objetos [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].  
  
-   Cuando necesite tratar con mensajes de una manera general sin tener en cuenta el contenido del mensaje (por ejemplo, cuando enrute o reenvíe mensajes al crear un enrutador, equilibrador de carga o un sistema publicación-suscripción  
  
 Antes de utilizar el <xref:System.ServiceModel.Channels.Message> de clases, familiarícese con el [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] arquitectura de transferencia de datos [información general de arquitectura de transferencia de datos](../../../../docs/framework/wcf/feature-details/data-transfer-architectural-overview.md).  
  
 Un <xref:System.ServiceModel.Channels.Message> es un contenedor para los datos de uso general, pero su diseño sigue estrechamente el diseño de un mensaje en el protocolo SOAP. Simplemente como en SOAP, un mensaje tiene un cuerpo de mensaje y encabezados. El cuerpo del mensaje contiene los datos de carga reales, mientras que los encabezados contienen los contenedores de datos con nombre adicionales. Las reglas para leer y escribir el cuerpo y los encabezados son diferentes; Por ejemplo, los encabezados están almacenados siempre en memoria búfer y se puede tener acceso a ellos todas las veces que se quiera, mientras que el cuerpo se puede leer solo una vez y puede ser transmitido. Normalmente, cuando se utiliza SOAP, el cuerpo del mensaje está asignado al cuerpo SOAP y los encabezados del mensaje están asignados a los encabezados SOAP.  
  
## <a name="using-the-message-class-in-operations"></a>Utilizar la clase de mensaje en Operaciones  
 Puede usar el <xref:System.ServiceModel.Channels.Message> clase como un parámetro de entrada de una operación, el valor devuelto de una operación, o ambos. Si <xref:System.ServiceModel.Channels.Message> se utiliza en cualquier lugar una operación, se aplican las siguientes restricciones:  
  
-   La operación no puede tener ningún `out` o parámetro `ref`.  
  
-   No puede haber más de un parámetro `input`. Si el parámetro está presente, debe ser Mensaje o un tipo de contrato de mensaje.  
  
-   El tipo de valor devuelto debe ser `void`, `Message`o un tipo de contrato de mensaje.  
  
 El ejemplo de código siguiente contiene un contrato de operación válido.  
  
 [!code-csharp[C_UsingTheMessageClass#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_usingthemessageclass/cs/source.cs#1)]
 [!code-vb[C_UsingTheMessageClass#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_usingthemessageclass/vb/source.vb#1)]  
  
## <a name="creating-basic-messages"></a>Creación de mensajes básicos  
 El <xref:System.ServiceModel.Channels.Message> clase proporciona estático `CreateMessage` métodos de generador que puede utilizar para crear mensajes básicos.  
  
 Todos los `CreateMessage` sobrecargas toman un parámetro de versión de tipo <xref:System.ServiceModel.Channels.MessageVersion> que indica las versiones SOAP y WS-Addressing que se utilizará para el mensaje. Si desea utilizar las mismas versiones de protocolo que el mensaje entrante, puede utilizar el <xref:System.ServiceModel.OperationContext.IncomingMessageVersion%2A> propiedad en el <xref:System.ServiceModel.OperationContext> Obtiene la instancia de la <xref:System.ServiceModel.OperationContext.Current%2A> propiedad. La mayoría de las sobrecargas `CreateMessage` también tienen un parámetro de cadena que indica la acción SOAP que se utilizará en el mensaje. La versión se puede establecer en `None` para deshabilitar la generación de la envoltura SOAP; el mensaje solamente se compone del cuerpo.  
  
## <a name="creating-messages-from-objects"></a>Crear mensajes a partir de objetos  
 La sobrecarga `CreateMessage` más básica que toma solo una versión y una acción crea un mensaje con un cuerpo vacío. Otra sobrecarga toma adicionales <xref:System.Object> parámetro; Esto crea un mensaje cuyo cuerpo es la representación serializada del objeto especificado. Utilice la <xref:System.Runtime.Serialization.DataContractSerializer> con la configuración predeterminada para la serialización. Si desea utilizar un serializador diferente, o quiere que `DataContractSerializer` se configure de manera diferente, utilice la sobrecarga `CreateMessage` que también toma un parámetro `XmlObjectSerializer`.  
  
 Por ejemplo, para devolver un objeto en un mensaje, puede utilizar el siguiente código.  
  
 [!code-csharp[C_UsingTheMessageClass#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_usingthemessageclass/cs/source.cs#2)]
 [!code-vb[C_UsingTheMessageClass#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_usingthemessageclass/vb/source.vb#2)]  
  
## <a name="creating-messages-from-xml-readers"></a>Crear los mensajes a partir de los lectores XML  
 Hay `CreateMessage` sobrecargas que toman una <xref:System.Xml.XmlReader> o un <xref:System.Xml.XmlDictionaryReader> para el cuerpo en lugar de un objeto. En este caso, el cuerpo del mensaje contiene el XML que se obtiene al leer con el lector XML pasado. Por ejemplo, el código siguiente devuelve un mensaje con el contenido del cuerpo leído desde un archivo XML.  
  
 [!code-csharp[C_UsingTheMessageClass#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_usingthemessageclass/cs/source.cs#3)]
 [!code-vb[C_UsingTheMessageClass#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_usingthemessageclass/vb/source.vb#3)]  
  
 Además, hay `CreateMessage` sobrecargas que toman una <xref:System.Xml.XmlReader> o un <xref:System.Xml.XmlDictionaryReader> que representa el mensaje completo y no simplemente el cuerpo. Estas sobrecargas también toman un parámetro `maxSizeOfHeaders` entero. Los encabezados siempre se almacenan en búfer en la memoria en cuanto se crea el mensaje, y este parámetro limita la cantidad de almacenamiento en búfer que tiene lugar. Es importante establecer este parámetro en un valor seguro si el XML procede de un origen que no es de confianza para mitigar la posibilidad de un ataque por denegación de servicio. El SOAP y versiones de WS-Addressing del mensaje que el lector XML representa deben coincidir con las versiones indicadas utilizando el parámetro de versión.  
  
## <a name="creating-messages-with-bodywriter"></a>Crear los mensajes con BodyWriter  
 Una sobrecarga `CreateMessage` toma una instancia `BodyWriter` para describir el cuerpo del mensaje. `BodyWriter` es una clase abstracta que se puede derivar para personalizar cómo se crean los cuerpos del mensaje. Puede crear su propia clase `BodyWriter` derivada para describir los cuerpos del mensaje de una manera personalizada. Debe invalidar el `BodyWriter.OnWriteBodyContents` método que toma un <xref:System.Xml.XmlDictionaryWriter>; este método es responsable de escribir el cuerpo.  
  
 Los sistemas de escritura del cuerpo se pueden almacenar en búfer o no (se pueden transmitir por secuencias). Los sistemas de escritura del cuerpo almacenados en búfer pueden escribir su contenido todas las veces que se quiera, mientras que los transmitidos solo pueden escribir sus contenidos una vez. La propiedad `IsBuffered` indica si un sistema de escritura del cuerpo está almacenado en búfer o no. Puede establecerlo para su sistema de escritura de cuerpo mediante una llamada al constructor `BodyWriter` protegido que toma un parámetro booleano `isBuffered`. Los sistemas de escritura de cuerpo permiten crear un sistema de escritura de cuerpo almacenado en búfer a partir de un sistema de escritura de cuerpo no almacenado en búfer. Puede invalidar el método `OnCreateBufferedCopy` para personalizar este proceso. De forma predeterminada, se usa un búfer en memoria que contiene el XML devuelto por `OnWriteBodyContents`. `OnCreateBufferedCopy` toma un parámetro entero `maxBufferSize`; si invalida este método, no debe crear búferes mayores que este tamaño máximo.  
  
 La clase `BodyWriter` proporciona respectivamente `WriteBodyContents` y los métodos `CreateBufferedCopy`, que son contenedores esencialmente delgados alrededor de `OnWriteBodyContents` y los métodos `OnCreateBufferedCopy`. Estos métodos realizan la comprobación de estado para asegurarse de que no se tiene acceso a un sistema de escritura de cuerpo no almacenado en búfer más de una vez. Solo se llama a estos métodos directamente al crear clases `Message` derivadas personalizadas basadas en `BodyWriters`.  
  
## <a name="creating-fault-messages"></a>Crear los mensajes de error  
 Puede utilizar ciertas sobrecargas `CreateMessage` para crear los mensajes del error de SOAP. La más básica toma un <xref:System.ServiceModel.Channels.MessageFault> objeto que describe el error. Otras sobrecargas se proporcionan para comodidad. La primera sobrecarga toma `FaultCode` y una cadena de la razón y crea `MessageFault` mediante `MessageFault.CreateFault` mediante esta información. La otra sobrecarga toma un objeto de datos y también lo pasa a `CreateFault` junto con el código de error y la razón. Por ejemplo, la operación siguiente devuelve un error.  
  
 [!code-csharp[C_UsingTheMessageClass#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_usingthemessageclass/cs/source.cs#4)]
 [!code-vb[C_UsingTheMessageClass#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_usingthemessageclass/vb/source.vb#4)]  
  
## <a name="extracting-message-body-data"></a>Extraer los datos del cuerpo del mensaje  
 La clase `Message` admite varias maneras de extraer información de su cuerpo. Éstos pueden estar clasificados en las categorías siguientes:  
  
-   Obtener el cuerpo del mensaje completo escrito de una vez en un sistema de escritura de XML. Esto se conoce como *escribir un mensaje*.  
  
-   Obtener un lector XML sobre el cuerpo del mensaje. Esto le permite al acceso posterior el cuerpo del mensaje parte por parte, según se requiera. Esto se conoce como *leer un mensaje*.  
  
-   El mensaje completo, incluido su cuerpo, puede copiarse a un búfer en memoria de la <xref:System.ServiceModel.Channels.MessageBuffer> tipo. Esto se conoce como *copiar un mensaje*.  
  
 Solo puede tener acceso una vez al cuerpo de `Message`, independientemente de cómo se tiene acceso. Un objeto de mensaje tiene una propiedad `State`, la cual se establece inicialmente en Creada. Los tres métodos de acceso descritos en la lista anterior establecen el estado en Escrito, Leído, y Copiado, respectivamente. Además, un método `Close` puede establecer el estado en Cerrado cuando ya no se necesita el contenido del cuerpo del mensaje. Se puede tener acceso al cuerpo del mensaje solo en el estado Creado y no hay ninguna manera de regresar al estado Creado después de que el estado haya cambiado.  
  
## <a name="writing-messages"></a>Escribir los mensajes  
 El <xref:System.ServiceModel.Channels.Message.WriteBodyContents%28System.Xml.XmlDictionaryWriter%29> método escribe el contenido del cuerpo de un determinado `Message` instancia a un sistema de escritura XML determinado. El <xref:System.ServiceModel.Channels.Message.WriteBody%2A> método hace lo mismo, salvo que agrega el contenido del cuerpo en el elemento contenedor adecuado (por ejemplo, `soap:body`>). Por último, <xref:System.ServiceModel.Channels.Message.WriteMessage%2A> escribe el mensaje completo, incluido el ajuste de la envoltura SOAP y los encabezados. Si SOAP está desactivado (Version es `MessageVersion.None`), los tres métodos hacen lo mismo: escriben el contenido del cuerpo del mensaje.  
  
 Por ejemplo, el código siguiente escribe el cuerpo de un mensaje de entrada en un archivo.  
  
 [!code-csharp[C_UsingTheMessageClass#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_usingthemessageclass/cs/source.cs#5)]
 [!code-vb[C_UsingTheMessageClass#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_usingthemessageclass/vb/source.vb#5)]  
  
 Dos métodos auxiliares adicionales escriben ciertas etiquetas de elemento de inicio de SOAP. Estos métodos no tienen acceso al cuerpo del mensaje, de modo que no cambian el estado del mensaje. Se incluyen los siguientes:  
  
-   <xref:System.ServiceModel.Channels.Message.WriteStartBody%2A> escribe el elemento de cuerpo de inicio, por ejemplo, `<soap:Body>`.  
  
-   <xref:System.ServiceModel.Channels.Message.WriteStartEnvelope%2A> escribe el elemento de envoltura de inicio, por ejemplo, `<soap:Envelope>`.  
  
 Para escribir las etiquetas de elementos finales correspondientes, llame `WriteEndElement` en el sistema de escritura XML correspondiente. Rara vez se llama a estos métodos directamente.  
  
## <a name="reading-messages"></a>Leer mensajes  
 La principal manera de leer un cuerpo del mensaje es llamar a <xref:System.ServiceModel.Channels.Message.GetReaderAtBodyContents%2A>. Obtendrá un <xref:System.Xml.XmlDictionaryReader> que puede utilizar para leer el cuerpo del mensaje. Tenga en cuenta que el <xref:System.ServiceModel.Channels.Message> transiciones al estado leído en cuanto <xref:System.ServiceModel.Channels.Message.GetReaderAtBodyContents%2A> se llama, y no cuando se usa el lector XML devuelto.  
  
 El <xref:System.ServiceModel.Channels.Message.GetBody%2A> método también le permite tener acceso al cuerpo de mensaje como un objeto con tipo. Internamente, este método utiliza `GetReaderAtBodyContents`, y así también pasa el estado del mensaje a la <xref:System.ServiceModel.Channels.MessageState> estado (consulte la <xref:System.ServiceModel.Channels.Message.State%2A> propiedad).  
  
 Es recomendable comprobar la <xref:System.ServiceModel.Channels.Message.IsEmpty%2A> propiedad, en cuyo caso el cuerpo del mensaje está vacío y <xref:System.ServiceModel.Channels.Message.GetReaderAtBodyContents%2A> produce una <xref:System.InvalidOperationException>. Además, si es un mensaje recibido (por ejemplo, la respuesta), también puede comprobar <xref:System.ServiceModel.Channels.Message.IsFault%2A>, lo que indica si el mensaje contiene un error.  
  
 La sobrecarga más básica de <xref:System.ServiceModel.Channels.Message.GetBody%2A> deserializa el cuerpo del mensaje en una instancia de un tipo (indicado por el parámetro genérico) mediante un <xref:System.Runtime.Serialization.DataContractSerializer> configurada con la configuración predeterminada y con el <xref:System.Runtime.Serialization.DataContractSerializer.MaxItemsInObjectGraph%2A> cuota deshabilitado. Si desea usar un motor de serialización diferente o configurar la `DataContractSerializer` de una manera no predeterminado, use el <xref:System.ServiceModel.Channels.Message.GetBody%2A> sobrecarga que toma un <xref:System.Runtime.Serialization.XmlObjectSerializer>.  
  
 Por ejemplo, el código siguiente extrae los datos de un cuerpo de mensaje que contiene un objeto `Person` serializado e imprime el nombre de la persona.  
  
 [!code-csharp[C_UsingTheMessageClass#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_usingthemessageclass/cs/source.cs#6)]
 [!code-vb[C_UsingTheMessageClass#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_usingthemessageclass/vb/source.vb#6)]  
  
## <a name="copying-a-message-into-a-buffer"></a>Copiar un mensaje en un búfer  
 A veces es necesario tener acceso más de una vez al cuerpo del mensaje, por ejemplo, para reenviar el mismo mensaje a varios destinos como parte de un sistema de publicación-suscripción. En este caso, es necesario almacenar en búfer el mensaje completo (incluido el cuerpo) en memoria. Puede hacerlo mediante una llamada a <xref:System.ServiceModel.Channels.Message.CreateBufferedCopy%28System.Int32%29>. Este método toma un parámetro entero que representa el tamaño máximo de búfer y crea un búfer inferior a este tamaño. Es importante establecer esto en un valor seguro si el mensaje procede de un origen que no es de confianza.  
  
 El búfer se devuelve como un <xref:System.ServiceModel.Channels.MessageBuffer> instancia. Puede tener acceso a los datos del búfer de varias maneras. La principal manera es llamar a <xref:System.ServiceModel.Channels.Message.CreateMessage%2A> crear `Message` instancias del búfer.  
  
 Otra manera de obtener acceso a los datos en el búfer es implementar la <xref:System.Xml.XPath.IXPathNavigable> de la interfaz que el <xref:System.ServiceModel.Channels.MessageBuffer> clase implementa para tener acceso directamente el XML subyacente. Algunos <xref:System.ServiceModel.Channels.MessageBuffer.CreateNavigator%2A> sobrecargas permiten crear <xref:System.Xml.XPath> exploradores protegidos por una cuota de nodo, limitando el número de nodos XML que se pueden visitar. Esto ayuda a evitar ataques por denegación de servicio en función del tiempo de procesamiento largo. Esta cuota está deshabilitada de forma predeterminada. Algunos `CreateNavigator` sobrecargas permiten especificar cómo se deben tratar los espacios en blanco en el archivo XML utilizando la <xref:System.Xml.XmlSpace> enumeración con el valor predeterminado `XmlSpace.None`.  
  
 Una última manera de tener acceso al contenido de un búfer de mensajes es escribir su contenido en una secuencia utilizando <xref:System.ServiceModel.Channels.Message.WriteMessage%2A>.  
  
 El ejemplo siguiente muestra el proceso de trabajar con `MessageBuffer`: un mensaje de entrada se reenvía a varios destinatarios y, a continuación, se registra en un archivo. Sin el almacenamiento en búfer, esto no es posible, porque se puede tener acceso al cuerpo del mensaje una sola vez.  
  
 [!code-csharp[C_UsingTheMessageClass#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_usingthemessageclass/cs/source.cs#7)]
 [!code-vb[C_UsingTheMessageClass#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_usingthemessageclass/vb/source.vb#7)]  
  
 La clase `MessageBuffer` tiene otro miembros que hay que tener en cuenta. El <xref:System.ServiceModel.Channels.MessageBuffer.Close%2A> se puede llamar el método para liberar recursos cuando ya no es necesario el contenido del búfer. El <xref:System.ServiceModel.Channels.MessageBuffer.BufferSize%2A> propiedad devuelve el tamaño del búfer asignado. El <xref:System.ServiceModel.Channels.MessageBuffer.MessageContentType%2A> propiedad devuelve el tipo de contenido MIME del mensaje.  
  
## <a name="accessing-the-message-body-for-debugging"></a>Tener acceso al cuerpo del mensaje para depuración  
 Con fines de depuración, puede llamar a la <xref:System.ServiceModel.Channels.Message.ToString%2A> método para obtener una representación del mensaje como una cadena. Esta representación por lo general coincide con la manera en que se mostraría un mensaje en la conexión si estuviera codificado con el codificador de texto, con la excepción de que se le aplicaría un formato más legible que XML. La excepción a esto es el cuerpo del mensaje. El cuerpo se puede leer una sola vez y `ToString` no cambia el estado del mensaje. Por lo tanto, la `ToString` método no podrá tener acceso al cuerpo y podría sustituir un marcador de posición (por ejemplo, "..." o tres puntos) en lugar del cuerpo del mensaje. Por consiguiente, no use `ToString` para registrar los mensajes si el contenido del cuerpo de los mensajes es importante.  
  
## <a name="accessing-other-message-parts"></a>Tener acceso a otras partes del mensaje  
 Se proporcionan varias propiedades para tener acceso a la información del mensaje que no sea el contenido del cuerpo. Sin embargo, no se puede llamar a éstos una vez se ha cerrado el mensaje:  
  
-   El <xref:System.ServiceModel.Channels.Message.Headers%2A> propiedad representa los encabezados de mensaje. Consulte la sección en "Trabajar con encabezados" más adelante en este tema.  
  
-   El <xref:System.ServiceModel.Channels.Message.Properties%2A> propiedad representa las propiedades de mensaje, que son fragmentos de datos con nombre adjuntadas al mensaje que generalmente no se emiten cuando se envía el mensaje. Consulte la sección en "Trabajar con propiedades" más adelante en este tema.  
  
-   El <xref:System.ServiceModel.Channels.Message.Version%2A> propiedad indica la versión SOAP y WS-Addressing asociada al mensaje, o `None` si SOAP está deshabilitado.  
  
-   El <xref:System.ServiceModel.Channels.Message.IsFault%2A> propiedad devuelve `true` si el mensaje es un mensaje de error SOAP.  
  
-   El <xref:System.ServiceModel.Channels.Message.IsEmpty%2A> propiedad devuelve `true` si el mensaje está vacío.  
  
 Puede usar el <xref:System.ServiceModel.Channels.Message.GetBodyAttribute%28System.String%2CSystem.String%29> método para acceder a un atributo determinado en el elemento contenedor del cuerpo (por ejemplo, `<soap:Body>`) identificado por un nombre determinado y el espacio de nombres. Si no se encuentra dicho atributo, se devuelve `null`. Se puede llamar a este método solo cuando `Message` está en el estado Creado (cuando todavía no se ha tenido acceso al cuerpo del mensaje).  
  
## <a name="working-with-headers"></a>Trabajar con encabezados  
 Un `Message` puede contener cualquier número de fragmentos XML con nombre, llamados *encabezados*. Cada fragmento asigna normalmente a un encabezado SOAP. Encabezados que se tiene acceso a través de la `Headers` propiedad de tipo <xref:System.ServiceModel.Channels.MessageHeaders>. <xref:System.ServiceModel.Channels.MessageHeaders> es una colección de <xref:System.ServiceModel.Channels.MessageHeaderInfo> pueden tener acceso a objetos y los encabezados individuales a través de su <xref:System.Collections.IEnumerable> interfaz o a través de su indizador. Por ejemplo, el código siguiente hace una lista de los nombres de todos los encabezados en `Message`.  
  
 [!code-csharp[C_UsingTheMessageClass#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_usingthemessageclass/cs/source.cs#8)]
 [!code-vb[C_UsingTheMessageClass#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_usingthemessageclass/vb/source.vb#8)]  
  
#### <a name="adding-removing-finding-headers"></a>Agregar, quitar, buscar encabezados  
 Puede agregar un nuevo encabezado al final de todos los encabezados existentes utilizando la <xref:System.ServiceModel.Channels.MessageHeaders.Add%2A> método. Puede usar el <xref:System.ServiceModel.Channels.MessageHeaders.Insert%2A> método para insertar un encabezado en un índice determinado. Los encabezados existentes se desplazan para el elemento insertado. Los encabezados se ordenan según su índice y el primer índice disponible es 0. Puede usar las distintas <xref:System.ServiceModel.Channels.MessageHeaders.CopyHeadersFrom%2A> sobrecargas del método para agregar encabezados desde otro `Message` o `MessageHeaders` instancia. Algunas sobrecargas copian un encabezado individual, mientras que otras copian todos ellos. El <xref:System.ServiceModel.Channels.MessageHeaders.Clear%2A> método quita todos los encabezados. El <xref:System.ServiceModel.Channels.MessageHeaders.RemoveAt%2A> método quita un encabezado en un índice determinado (desplazando todos los encabezados después de él). El <xref:System.ServiceModel.Channels.MessageHeaders.RemoveAll%2A> método quita todos los encabezados con un nombre determinado y el espacio de nombres.  
  
 Recuperar un encabezado determinado mediante la <xref:System.ServiceModel.Channels.MessageHeaders.FindHeader%2A> método. Este método toma el nombre y espacio de nombres del encabezado para buscar y devuelve su índice. Si el encabezado se produce más de una vez, se produce una excepción. Si no se encuentra el encabezado, devuelve -1.  
  
 En el modelo del encabezado SOAP, los encabezados pueden tener un valor `Actor` que especifica el destinatario previsto del encabezado. La sobrecarga `FindHeader` más básica solo busca en los encabezados que están pensados para el receptor definitivo del mensaje. Sin embargo, otra sobrecarga le permite especificar qué valores `Actor` están incluidos en la búsqueda. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] la especificación SOAP.  
  
 Un [CopyTo (MessageHeaderInfo\<xref:System.ServiceModel.Channels.MessageHeaders.CopyTo%28System.ServiceModel.Channels.MessageHeaderInfo%5B%5D%2CSystem.Int32%29> método se proporciona para copiar los encabezados de un <xref:System.ServiceModel.Channels.MessageHeaders> colección a una matriz de <xref:System.ServiceModel.Channels.MessageHeaderInfo> objetos.  
  
 Para obtener acceso a los datos XML en un encabezado, se puede llamar a <xref:System.ServiceModel.Channels.MessageHeaders.GetReaderAtHeader%2A> y devolver un lector XML para el índice de encabezado específico. Si desea deserializar el contenido del encabezado en un objeto, utilice <xref:System.ServiceModel.Channels.MessageHeaders.GetHeader%60%601%28System.Int32%29> o una de las otras sobrecargas. Las sobrecargas más básicas deserializan los encabezados con el <xref:System.Runtime.Serialization.DataContractSerializer> configurado en el valor predeterminado forma. Si desea utilizar un serializador diferente o una configuración diferente de `DataContractSerializer`, utilice una de las sobrecargas que toman `XmlObjectSerializer`. También hay sobrecarga que toma el nombre del encabezado, espacio de nombres y opcionalmente una lista de los valores `Actor` en lugar de un índice; ésta es una combinación de `FindHeader` y `GetHeader`.  
  
## <a name="working-with-properties"></a>Trabajar con propiedades  
 Una instancia `Message` puede contener un número arbitrario de objetos con nombre de tipos arbitrarios. Se accede a esta colección a través de la  propiedad`Properties` de tipo `MessageProperties`. La colección implementa la <xref:System.Collections.Generic.IDictionary%602> de la interfaz y actúa como una asignación de <xref:System.String> a <xref:System.Object>.\</TKey, TValue> Normalmente, los valores de propiedad no se asignan directamente a cualquier parte del mensaje en la conexión, sino que proporcionan varias sugerencias de procesamiento de mensajes a los diferentes canales de la [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] pila de canales o a la [CopyTo (MessageHeaderInfo\<xref:System.ServiceModel.Channels.MessageHeaders.CopyTo%28System.ServiceModel.Channels.MessageHeaderInfo%5B%5D%2CSystem.Int32%29> marco de servicio. Para obtener un ejemplo, vea [datos de introducción a la arquitectura de transferencia](../../../../docs/framework/wcf/feature-details/data-transfer-architectural-overview.md).  
  
## <a name="inheriting-from-the-message-class"></a>Herencia de la clase de mensaje  
 Si los tipos de mensaje integrados creados mediante `CreateMessage` no cumplen sus requisitos, cree una clase que derive de la clase `Message`.  
  
### <a name="defining-the-message-body-contents"></a>Definir el contenido del cuerpo del mensaje  
 Existen tres técnicas primarias para tener acceso a los datos dentro de un cuerpo del mensaje: escribir, leer y copiar en un búfer. Estas operaciones como resultado final en el <xref:System.ServiceModel.Channels.Message.OnWriteBodyContents%2A>, <xref:System.ServiceModel.Channels.Message.OnGetReaderAtBodyContents%2A>, y <xref:System.ServiceModel.Channels.Message.OnCreateBufferedCopy%2A> métodos que se llama, respectivamente, en la clase derivada de `Message`. La clase base `Message` garantiza que se llamará a uno de estos métodos por cada instancia de `Message` y que no se llama más de una vez. La clase base también garantiza que no se llama a los métodos en un mensaje cerrado. No hay ninguna necesidad de realizar el seguimiento del estado del mensaje en su implementación.  
  
 <xref:System.ServiceModel.Channels.Message.OnWriteBodyContents%2A> es un método abstracto y debe implementarse. La manera más básica de definir el contenido del cuerpo de un mensaje es escribirlo con este método. Por ejemplo, el mensaje siguiente contiene 100,000 números aleatorios de 1 a 20.  
  
 [!code-csharp[C_UsingTheMessageClass#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_usingthemessageclass/cs/source.cs#9)]
 [!code-vb[C_UsingTheMessageClass#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_usingthemessageclass/vb/source.vb#9)]  
  
 
          `OnGetReaderAtBodyContents` y los métodos `OnCreateBufferedCopy` tienen implementaciones predeterminadas que funcionan en la mayoría de los casos.   Las implementaciones predeterminadas llaman a `OnWriteBodyContents`, almacenan en búfer los resultados y funcionan con el búfer resultante. Sin embargo, en algunos casos esto puede no ser bastante. En el ejemplo anterior, leer el mensaje resulta en 100,000 elementos XML almacenados en búfer, lo cual podría no ser deseable. Es posible que desee invalidar `OnGetReaderAtBodyContents` para devolver una clase `XmlDictionaryReader` derivada personalizada que proporcione números aleatorios. Puede invalidar a continuación `OnWriteBodyContents` para utilizar el lector que devuelve la propiedad `OnGetReaderAtBodyContents`, tal y como se muestra en el ejemplo siguiente.  
  
 [!code-csharp[C_UsingTheMessageClass#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_usingthemessageclass/cs/source.cs#10)]
 [!code-vb[C_UsingTheMessageClass#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_usingthemessageclass/vb/source.vb#10)]  
  
 De igual forma, podría desear invalidar `OnCreateBufferedCopy` para devolver su propia clase derivada `MessageBuffer`.  
  
 Además de proporcionar el contenido del cuerpo del mensaje, la clase derivada del mensaje también debe invalidar las propiedades `Version`, `Headers` y `Properties`.  
  
 Tenga en cuenta que si crea una copia de un mensaje, la copia utiliza los encabezados del mensaje del original.  
  
### <a name="other-members-that-can-be-overridden"></a>Otros miembros que se pueden invalidar  
 Puede invalidar el <xref:System.ServiceModel.Channels.Message.OnWriteStartEnvelope%2A>, <xref:System.ServiceModel.Channels.Message.OnWriteStartHeaders%2A>, y <xref:System.ServiceModel.Channels.Message.OnWriteStartBody%2A> se escriben métodos para especificar cómo la envoltura SOAP, encabezados SOAP y elemento de cuerpo SOAP etiquetas de apertura. Éstos corresponden normalmente a `<soap:Envelope>``<soap:Body>`, `<soap:Header>`y . Estos métodos no deberían escribir normalmente nada si la propiedad `Version` devuelve `MessageVersion.None`.  
  
> [!NOTE]
>  La implementación predeterminada de `OnGetReaderAtBodyContents` llama `OnWriteStartEnvelope` y `OnWriteStartBody` antes de llamar `OnWriteBodyContents` y almacenar en búfer los resultados. Los encabezados no se escriben.  
  
 Invalidar el <xref:System.ServiceModel.Channels.Message.OnWriteMessage%2A> método para cambiar la manera de construir el mensaje completo de sus diferentes partes. El `OnWriteMessage` método se llama desde <xref:System.ServiceModel.Channels.Message.WriteMessage%2A> y el valor predeterminado <xref:System.ServiceModel.Channels.Message.OnCreateBufferedCopy%2A> implementación. Tenga en cuenta que invalidar <xref:System.ServiceModel.Channels.Message.WriteMessage%2A> no es una práctica recomendada. Es mejor invalidar adecuado `On` métodos (por ejemplo, <xref:System.ServiceModel.Channels.Message.OnWriteStartEnvelope%2A>, <xref:System.ServiceModel.Channels.Message.OnWriteStartHeaders%2A>, y <xref:System.ServiceModel.Channels.BodyWriter.OnWriteBodyContents%2A>.  
  
 Invalidar <xref:System.ServiceModel.Channels.Message.OnBodyToString%2A> para invalidar cómo se representa el cuerpo del mensaje durante la depuración. El valor predeterminado es representarlo con tres puntos ("..."). Tenga en cuenta que se puede llamar a este método varias veces cuando el estado del mensaje es otro distinto de Cerrado. Una implementación de este método no debería producir nunca una acción que solo se deba realizar una vez (como leer de una secuencia solo hacia adelante).  
  
 Invalidar el <xref:System.ServiceModel.Channels.Message.OnGetBodyAttribute%2A> método para permitir el acceso a los atributos en el elemento de cuerpo SOAP. Este método se puede llamar todas las veces que se desee, pero el tipo base `Message` garantiza que solo se llama cuando el mensaje se encuentre en estado Creado. No se requiere para comprobar el estado en una implementación. La implementación predeterminada siempre devuelve `null`, lo que indica que no hay ningún atributo en el elemento del cuerpo.  
  
 Si su `Message` objeto debe realizar las operaciones de limpieza especial cuando ya no se requiere el cuerpo del mensaje, puede invalidar <xref:System.ServiceModel.Channels.Message.OnClose%2A>. La implementación predeterminada no hace nada.  
  
 `IsEmpty` y las propiedades `IsFault` se pueden invalidar. De forma predeterminada, ambos devuelven `false`.