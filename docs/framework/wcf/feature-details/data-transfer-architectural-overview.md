---
description: 'Más información sobre: información general sobre la arquitectura de Transferencia de datos'
title: Información general sobre la arquitectura de transferencia de datos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data transfer [WCF], architectural overview
ms.assetid: 343c2ca2-af53-4936-a28c-c186b3524ee9
ms.openlocfilehash: 3064797b41e146505062a07dc1786dd492a01298
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99756505"
---
# <a name="data-transfer-architectural-overview"></a>Información general sobre la arquitectura de transferencia de datos

Windows Communication Foundation (WCF) se puede considerar como una infraestructura de mensajería. Puede recibir mensajes, procesarlos y enviarlos al código de usuario para realizar acciones adicionales o puede construir mensajes a partir de los datos proporcionados por el código de usuario y entregarlos en un destino. Este tema, que está dirigido a desarrolladores avanzados, describe la arquitectura para el manejo de mensajes y los datos contenidos. Para obtener una vista más sencilla y orientada a tareas sobre cómo enviar y recibir datos, consulte [Specifying Data Transfer in Service Contracts](specifying-data-transfer-in-service-contracts.md).  
  
> [!NOTE]
> En este tema se describen los detalles de la implementación de WCF que no son visibles al examinar el modelo de objetos WCF. Dos consejos se han de dar en relación a los detalles de implementación documentados. Primero, se simplifican las descripciones; la implementación real puede ser más compleja debido a optimizaciones u otras razones. Segundo, nunca debería basarse en detalles de implementación concretos, ni siquiera los documentados, porque puede que éstos cambien sin aviso de una versión a otra o incluso en un lanzamiento del servicio.  
  
## <a name="basic-architecture"></a>Arquitectura básica  

 En el núcleo de las funcionalidades de control de mensajes de WCF se encuentra la <xref:System.ServiceModel.Channels.Message> clase, que se describe en detalle en [el uso de la clase de mensaje](using-the-message-class.md). Los componentes en tiempo de ejecución de WCF se pueden dividir en dos partes principales: la pila de canales y el marco de trabajo de servicio, con la <xref:System.ServiceModel.Channels.Message> clase como punto de conexión.  
  
 La pila de canales es la responsable de la conversión entre una instancia <xref:System.ServiceModel.Channels.Message> válida y alguna acción que corresponda al envío o recepción de datos de mensajes. En el lado del envío, la pila de canales toma una instancia <xref:System.ServiceModel.Channels.Message> válida y, después de algo de procesado, realiza alguna acción que corresponde lógicamente con el envío del mensaje. La acción puede consistir en enviar paquetes TCP o HTTP, poner en cola el mensaje en Message Queuing, escribir el mensaje en una base de datos, guardarlo en un recurso compartido de archivos, o cualquier otra acción, dependiendo de la implementación. La acción más común es la de enviar el mensaje sobre un protocolo de red. En el lado de recepción, sucede lo contrario: se detecta una acción (que puede ser la llegada de paquetes TCP o HTTP o cualquier otra acción) y, tras el procesado, la pila de canales convierte esta acción en una instancia <xref:System.ServiceModel.Channels.Message> válida.  
  
 Puede usar WCF mediante la <xref:System.ServiceModel.Channels.Message> clase y la pila de canales directamente. Sin embargo, hacer esto es difícil y exige mucho tiempo. Además, el <xref:System.ServiceModel.Channels.Message> objeto no proporciona compatibilidad con metadatos, por lo que no puede generar clientes WCF fuertemente tipados si usa WCF de esta manera.  
  
 Por lo tanto, WCF incluye un marco de trabajo de servicio que proporciona un modelo de programación fácil de usar que puede usar para construir y recibir `Message` objetos. El marco de trabajo de servicio asigna servicios a los tipos .NET Framework a través de la noción de contratos de servicios y envía mensajes a las operaciones de usuario que simplemente .NET Framework métodos marcados con el <xref:System.ServiceModel.OperationContractAttribute> atributo (para más información, consulte [diseño de contratos de servicio](../designing-service-contracts.md)). Estos métodos pueden tener parámetros y valores devueltos. En el lado del servicio, el marco de trabajo de servicio convierte las instancias <xref:System.ServiceModel.Channels.Message> de entrada en parámetros y convierte los valores devueltos en instancias <xref:System.ServiceModel.Channels.Message> de salida. En el lado de cliente, hace lo contrario. Por ejemplo, considere la operación `FindAirfare` descrita abajo.  
  
 [!code-csharp[c_DataArchitecture#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_dataarchitecture/cs/source.cs#1)]
 [!code-vb[c_DataArchitecture#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_dataarchitecture/vb/source.vb#1)]  
  
 Suponga que `FindAirfare` se llama en el cliente. El marco de trabajo de servicio en el cliente convierte los parámetros `FromCity` y `ToCity` en una instancia de <xref:System.ServiceModel.Channels.Message> de salida y la pasa a la pila de canales que se va a enviar.  
  
 En el lado del servicio, cuando una instancia de <xref:System.ServiceModel.Channels.Message> llega de la pila de canales, el marco de trabajo de servicio extrae los datos pertinentes del mensaje para rellenar los parámetros `FromCity` y `ToCity` y, a continuación, llama al método `FindAirfare` de lado de servicio. Cuando el método vuelve, el marco de trabajo de servicio toma el valor entero devuelto y el parámetro de salida `IsDirectFlight` y crea una instancia de objeto de <xref:System.ServiceModel.Channels.Message> que contiene esta información. A continuación, pasa la instancia `Message` a la pila de canales que se va a devolver al cliente.  
  
 En el lado de cliente, una instancia de <xref:System.ServiceModel.Channels.Message> que contiene el mensaje de respuesta emerge de la pila de canales. El marco de trabajo de servicio extrae el valor devuelto y el valor de `IsDirectFlight` y los devuelve al llamador del cliente.  
  
## <a name="message-class"></a>Message (clase)  

 La clase <xref:System.ServiceModel.Channels.Message> pretende ser una representación abstracta de un mensaje, pero su diseño está unido fuertemente al mensaje SOAP. <xref:System.ServiceModel.Channels.Message> contiene tres partes principales de información: un cuerpo del mensaje, encabezados del mensaje y propiedades de mensaje.  
  
## <a name="message-body"></a>Cuerpo del mensaje  

 El objetivo del cuerpo del mensaje es representar la carga útil real del mensaje. El cuerpo del mensaje siempre se representa como un conjunto de información XML. Esto no significa que todos los mensajes creados o recibidos en WCF deben estar en formato XML. Depende de la pila de canales decidir cómo interpretar el cuerpo del mensaje. Puede emitirlo como XML, convertirlo a algún otro formato o incluso omitirlo completamente. Por supuesto, con la mayoría de los enlaces que WCF proporciona, el cuerpo del mensaje se representa como contenido XML en la sección de cuerpo de una envoltura SOAP.  
  
 Es importante comprender que la clase `Message` no necesariamente contiene un búfer con datos XML que representan el cuerpo. Lógicamente, `Message` contiene un conjunto de información XML, pero este conjunto de información puede construirse dinámicamente y no existir nunca físicamente en memoria.  
  
### <a name="putting-data-into-the-message-body"></a>Colocar datos en el cuerpo del mensaje  

 No hay ningún mecanismo uniforme para colocar los datos en el cuerpo de un mensaje. La clase <xref:System.ServiceModel.Channels.Message> tiene un método abstracto, <xref:System.ServiceModel.Channels.Message.OnWriteBodyContents%28System.Xml.XmlDictionaryWriter%29>, que toma un <xref:System.Xml.XmlDictionaryWriter>. Cada subclase de la clase <xref:System.ServiceModel.Channels.Message> es responsable de la invalidación de este método y de la escritura fuera de su propio contenido. El cuerpo del mensaje contiene lógicamente el conjunto de información XML que genera `OnWriteBodyContent` . Por ejemplo, considere la siguiente subclase `Message` .  
  
 [!code-csharp[c_DataArchitecture#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_dataarchitecture/cs/source.cs#2)]
 [!code-vb[c_DataArchitecture#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_dataarchitecture/vb/source.vb#2)]  
  
 Físicamente, una instancia `AirfareRequestMessage` contiene solo dos cadenas ("fromCity" y "toCity"). Sin embargo, lógicamente el mensaje contiene el siguiente conjunto de información XML:  
  
```xml  
<airfareRequest>  
    <from>Tokyo</from>  
    <to>London</to>  
</airfareRequest>  
```  
  
 Por supuesto, no crearía normalmente mensajes de esta manera, porque puede utilizar el marco de trabajo del servicio para crear un mensaje como el anterior a partir de parámetros de contrato de operaciones. Además, la clase <xref:System.ServiceModel.Channels.Message> tiene métodos `CreateMessage` estáticos que puede utilizar para crear mensajes con tipos comunes de contenido: un mensaje vacío, un mensaje que contiene un objeto serializado a XML con <xref:System.Runtime.Serialization.DataContractSerializer>, un mensaje que contiene un error de SOAP, un mensaje que contiene XML representado por <xref:System.Xml.XmlReader>, etc.  
  
### <a name="getting-data-from-a-message-body"></a>Obtención de datos del cuerpo de un mensaje  

 Puede extraer los datos almacenados en el cuerpo de un mensaje principalmente de dos maneras:  
  
- Puede obtener una vez el cuerpo del mensaje al completo llamando al método <xref:System.ServiceModel.Channels.Message.WriteBodyContents%28System.Xml.XmlDictionaryWriter%29> y pasando un sistema de escritura de XML. El cuerpo del mensaje al completo se escribe en este sistema de escritura. Obtener el cuerpo del mensaje al completo de una vez también se llama *escribir un mensaje*. El canal de pilas realiza principalmente la escritura al enviar mensajes; una parte de la pila de canales tendrá, por lo general, acceso a todo el cuerpo del mensaje, lo codificará y enviará.  
  
- Otra manera de extraer información del cuerpo del mensaje es llamar <xref:System.ServiceModel.Channels.Message.GetReaderAtBodyContents> y obtener un lector XML. A continuación, se puede tener acceso al cuerpo del mensaje de manera consecutiva tanto como sea necesario llamando a los métodos en el lector. Obtener el cuerpo del mensaje parte por parte también se llama *leer un mensaje*. La lectura del mensaje es utilizada principalmente por el marco de trabajo de servicio al recibir mensajes. Por ejemplo, cuando <xref:System.Runtime.Serialization.DataContractSerializer> se está utilizando, el marco de trabajo de servicio obtendrá un lector XML sobre el cuerpo y lo pasará al motor de deserialización, que comenzará, a continuación, a leer el mensaje elemento a elemento y a construir el gráfico de objeto correspondiente.  
  
 Solo se puede recuperar un cuerpo de mensaje una vez. Esto permite trabajar con secuencias de solo avance. Por ejemplo, puede escribir una invalidación <xref:System.ServiceModel.Channels.Message.OnWriteBodyContents%28System.Xml.XmlDictionaryWriter%29> que lee de <xref:System.IO.FileStream> y devuelve los resultados como un conjunto de información XML. Nunca necesitará "rebobinar" al principio del archivo.  
  
 Los métodos `WriteBodyContents` y `GetReaderAtBodyContents` simplemente comprueban que el cuerpo del mensaje no se ha recuperado antes y, a continuación, llaman a `OnWriteBodyContents` o a `OnGetReaderAtBodyContents`, respectivamente.  
  
## <a name="message-usage-in-wcf"></a>Uso de mensajes en WCF  

 La mayoría de los mensajes pueden estar clasificados como *salientes* (aquéllos que crea el marco de trabajo de servicio para que la pila de canales los envíe) o *entrantes* (aquéllos que llegan desde pilas de canales y son interpretados por parte del marco de trabajo de servicio). Aún más, la pila de canales puede funcionar en modo almacenado en búfer o modo de transmisión por secuencias. El marco de trabajo de servicio también puede exponer un modelo de programación de transmisión por secuencias o sin transmisión por secuencias. Esto nos lleva a los casos enumerados en la siguiente tabla, junto con detalles simplificados de su implementación.  
  
|Tipo de mensaje|Datos del cuerpo en mensaje|Implementación de escritura (OnWriteBodyContents)|Implementación de lectura (OnGetReaderAtBodyContents)|  
|------------------|--------------------------|--------------------------------------------------|-------------------------------------------------------|  
|Saliente, creado a partir del modelo de programación sin transmisión por secuencias|Los datos tienen que escribir el mensaje (por ejemplo, un objeto y la instancia de <xref:System.Runtime.Serialization.DataContractSerializer> necesarios para serializarlo)*|Lógica personalizada para escribir el mensaje en función de los datos almacenados (por ejemplo, llamar `WriteObject` en `DataContractSerializer` si ése es el serializador en uso)*|Llamar `OnWriteBodyContents`, almacenar en búfer los resultados, devolver un lector XML sobre el búfer|  
|Saliente, creado a partir del modelo de programación de transmisión por secuencias|La `Stream` con los datos que se han de escribir*|Escriba los datos de la secuencia almacenada utilizando el mecanismo <xref:System.Xml.IStreamProvider> *|Llamar `OnWriteBodyContents`, almacenar en búfer los resultados, devolver un lector XML sobre el búfer|  
|Entrante a partir de la pila de canales de transmisión por secuencias|Un objeto `Stream` que representa los datos que entran a través de la red con <xref:System.Xml.XmlReader> sobre él|Escriba fuera el contenido del `XmlReader` almacenado utilizando `WriteNode`|Devuelve el `XmlReader`almacenado|  
|Entrante a partir de la pila de canales sin transmisión por secuencias|Un búfer que contiene datos del cuerpo con un `XmlReader` sobre él|Escribe fuera el contenido del `XmlReader` almacenado utilizando `WriteNode`|Devuelve el lenguaje almacenado|  
  
 \* Estos elementos no se implementan directamente en las `Message` subclases, sino en las subclases de la <xref:System.ServiceModel.Channels.BodyWriter> clase. Para obtener más información acerca de <xref:System.ServiceModel.Channels.BodyWriter>, vea [Using the Message Class](using-the-message-class.md).  
  
## <a name="message-headers"></a>Encabezados de mensajes  

 Un mensaje puede contener encabezados. Un encabezado se compone lógicamente de un conjunto de información XML asociado a un nombre, un espacio de nombres y algunas propiedades. Se tiene acceso a los encabezados del mensaje utilizando la propiedad `Headers` en <xref:System.ServiceModel.Channels.Message>. Cada encabezado está representado por una clase <xref:System.ServiceModel.Channels.MessageHeader> . Normalmente, los encabezados de mensajes están asignados a encabezados de mensaje SOAP al utilizar una pila de canales configurada para que funcione con mensajes SOAP.  
  
 Colocar información en un encabezado de mensaje y extraer información de él es similar a utilizar el cuerpo del mensaje. Se simplifica un poco el proceso porque no se admite la transmisión por secuencias. Es posible tener acceso más de una vez al contenido del mismo encabezado y se puede tener acceso a los encabezados en orden aleatorio, lo que hace que siempre estén almacenados en búfer. No hay ningún mecanismo de uso general disponible para obtener un lector XML sobre un encabezado, pero hay una `MessageHeader` subclase interna a WCF que representa un encabezado legible con una funcionalidad de este tipo. La pila del canal crea este tipo de `MessageHeader` cuando llega un mensaje con encabezados personalizados de la aplicación. Esto permite al marco de trabajo del servicio usar un motor de deserialización, como <xref:System.Runtime.Serialization.DataContractSerializer>, para interpretar estos encabezados.  
  
 Para obtener más información, vea [usar la clase de mensaje](using-the-message-class.md).  
  
## <a name="message-properties"></a>Message (propiedades)  

 Un mensaje puede contener propiedades. Una *propiedad* es cualquier objeto .NET Framework asociado a un nombre de cadena. Se tiene acceso a las propiedades a través de la propiedad `Properties` en `Message`.  
  
 A diferencia del cuerpo del mensaje y los encabezados del mensaje (que se asignan normalmente al cuerpo de SOAP y encabezados SOAP, respectivamente), las propiedades de mensajes normalmente no se envían ni reciben junto con los mensajes. Las propiedades de los mensajes existen principalmente como un mecanismo de comunicación para pasar datos sobre el mensaje entre los diversos canales de la pila de canales y entre la pila de canales y el modelo de servicio.  
  
 Por ejemplo, el canal de transporte HTTP incluido como parte de WCF es capaz de generar varios códigos de Estado HTTP, como "404 (no encontrado)" y "500 (error interno del servidor)", cuando envía respuestas a los clientes. Antes de enviar un mensaje de respuesta, comprueba para ver si el `Properties` de `Message` contiene una propiedad denominada "httpResponse" que contiene un objeto de tipo <xref:System.ServiceModel.Channels.HttpResponseMessageProperty> . Si se encuentra este tipo de propiedad, mirará en la propiedad <xref:System.ServiceModel.Channels.HttpResponseMessageProperty.StatusCode%2A> y utilizará ese código de estado. Si no se encuentra, se utiliza el código "200 (Aceptar)" predeterminado.  
  
 Para obtener más información, vea [usar la clase de mensaje](using-the-message-class.md).  
  
### <a name="the-message-as-a-whole"></a>El mensaje en conjunto  

 Hasta ahora, hemos discutido los métodos para tener acceso a las diversas partes del mensaje aislado. Sin embargo, la clase <xref:System.ServiceModel.Channels.Message> también proporciona métodos para trabajar con el mensaje completo como un todo. Por ejemplo, el método `WriteMessage` escribe el mensaje completo en un sistema de escritura XML.  
  
 Para que esto sea posible, se debe definir una asignación entre la instancia `Message` completa y un conjunto de información XML. Este tipo de asignación, de hecho, existe: WCF usa el estándar SOAP para definir esta asignación. Cuando una instancia `Message` se escribe como un conjunto de información XML, el conjunto de información resultante es la envoltura SOAP válida que contiene el mensaje. Así, `WriteMessage` realizaría normalmente los siguientes pasos:  
  
1. Escribir la etiqueta de apertura del elemento de envoltura SOAP.  
  
2. Escribir la etiqueta de apertura de elemento de encabezado SOAP, escribir todos los encabezados y cerrar el elemento de encabezado.  
  
3. Escribir la etiqueta de apertura del elemento de cuerpo SOAP.  
  
4. Llamar a `WriteBodyContents` o a un método equivalente para escribir el cuerpo.  
  
5. Cerrar los elementos de envoltura y cuerpo.  
  
 Los pasos anteriores están estrechamente unidos a la norma de SOAP. Esto es complicado, por el hecho de que existen múltiples versiones de SOAP, por ejemplo, es imposible escribir correctamente el elemento de envoltura de SOAP sin conocer la versión SOAP que se está utilizando. Asimismo, en algunos casos, puede ser deseable desactivar completamente esta compleja asignación específica del SOAP.  
  
 Para ello, se proporciona una propiedad `Version` en `Message`. Puede establecerse como la versión de SOAP que se va a utilizar cuando se escriba el mensaje, o puede establecerse como `None` para evitar cualquier asignación específica de SOAP. Si la propiedad `Version` se define como `None`, los métodos que operan con todo el mensaje actúan como si el mensaje solo estuviera compuesto de su cuerpo, por ejemplo, `WriteMessage` llamaría simplemente a `WriteBodyContents` en lugar de realizar los diversos pasos enumerados anteriormente. Se espera que en los mensajes entrantes, `Version` se detecte automáticamente y defina correctamente.  
  
## <a name="the-channel-stack"></a>La pila de canales  
  
### <a name="channels"></a>Canales  

 Tal y como se dijo antes, la pila de canales es responsable de la conversión de instancias <xref:System.ServiceModel.Channels.Message> salientes en alguna acción (como enviar paquetes a través de la red) o de la conversión alguna acción (como recibir paquetes de la red) en instancias `Message` entrantes.  
  
 La pila de canales consta de uno o más canales ordenados en una secuencia. Una instancia de `Message` saliente se pasa al primer canal de la pila (también llamado *canal más alto*), que lo pasa al siguiente canal que esté por debajo en la pila, y así sucesivamente. El mensaje finaliza en el último canal, que se denomina el *canal de transporte*. Los mensajes entrantes se originan en el canal de transporte y se pasan de canal en canal hacia arriba en la pila. Desde el canal más alto, el mensaje se pasa normalmente al marco de trabajo de servicio. Aunque éste es el patrón usual para los mensajes de aplicaciones, algunos canales pueden trabajar de manera algo diferente, por ejemplo, pueden enviar sus propios mensajes de infraestructura sin tener que pasar un mensaje de un canal superior.  
  
 Los canales pueden funcionar en el mensaje de varias maneras a medida que atraviesa la pila. La operación más común es agregar un encabezado a un mensaje saliente y leer los encabezados en un mensaje entrante. Por ejemplo, un canal puede calcular la firma digital de un mensaje y agregarla como un encabezado. Un canal también puede inspeccionar este encabezado de firma digital en los mensajes entrantes y bloquear los mensajes que no tienen una firma para que no asciendan en la pila de canales. Los canales también definen o inspeccionan a menudo las propiedades de mensajes. Normalmente, el cuerpo del mensaje no se modifica, aunque se permite, por ejemplo, el canal de seguridad de WCF puede cifrar el cuerpo del mensaje.  
  
### <a name="transport-channels-and-message-encoders"></a>Canales de transporte y codificadores de mensajes  

 El canal más bajo de la pila es el responsable de la transformación real de un <xref:System.ServiceModel.Channels.Message>saliente, tal y como lo modificaron otros canales, en alguna acción. En el lado de recepción, éste es el canal que convierte alguna acción en un `Message` que otros canales procesan.  
  
 Como se dijo anteriormente, se pueden variar las acciones: envío o recepción de paquetes de red a través de varios protocolos, lectura o escritura del mensaje en una base de datos o puesta o eliminación de la cola en una cola de Message Queuing, por mencionar unos pocos ejemplos. Todas estas acciones tienen algo en común: requieren una transformación entre la instancia de WCF `Message` y un grupo real de bytes que se puede enviar, recibir, leer, escribir, poner en cola o quitar de la cola. El proceso de conversión de un `Message` en un grupo de bytes se denomina *codificación* y el proceso inverso de crear `Message` a partir de un grupo de bytes se denomina *decodificación*.  
  
 La mayoría de los canales de transporte usan componentes llamados *codificadores de mensajes* para realizar las tareas de codificación y decodificación. Un codificador de mensajes es una subclase de la clase <xref:System.ServiceModel.Channels.MessageEncoder> . `MessageEncoder` incluye varias sobrecargas de método `ReadMessage` y `WriteMessage` para convertir entre `Message` y grupos de bytes.  
  
 En el lado de envío, un canal de transporte de almacenado en búfer pasa el objeto `Message` que recibió de un canal situado sobre él para `WriteMessage`. Recibe una matriz de bytes, que utiliza a continuación para realizar su acción (como empaquetar estos bytes como paquetes TCP válidos y enviarlos al destino correcto). Un canal de transporte de transmisión por secuencia crea primero una `Stream` (por ejemplo, sobre la conexión TCP de salida) y, a continuación, pasa la `Stream` y el `Message` que necesita para enviar a la sobrecarga `WriteMessage` adecuada, que escribe el mensaje.  
  
 En el lado de recepción, un canal de transporte de almacenado en búfer extrae los bytes de entrada (por ejemplo, de los paquetes TCP entrantes) en una matriz y llama `ReadMessage` para obtener un objeto `Message` que puede pasar hacia arriba en la pila de canales. Un canal de transporte de transmisión por secuencias crea un objeto `Stream` (por ejemplo, una secuencia de red sobre la conexión TCP entrante) y pasa eso a `ReadMessage` para recibir un objeto `Message` .  
  
 La separación entre los canales de transporte y el codificador de mensajes no es obligatoria; es posible escribir un canal de transporte que no use un codificador de mensajes. Sin embargo, la ventaja de esta separación es la facilidad de composición. Siempre y cuando un canal de transporte use solo la base <xref:System.ServiceModel.Channels.MessageEncoder> , puede funcionar con cualquier codificador de mensajes de WCF o de otro fabricante. De igual modo, el mismo codificador puede usarse normalmente en cualquier canal de transporte.  
  
### <a name="message-encoder-operation"></a>Operación del codificador de mensajes  

 Para describir la operación típica de un codificador, es útil considerar los cuatro casos siguientes.  
  
|Operación|Comentario|  
|---------------|-------------|  
|Codificación, almacenado en búfer|En el modo de almacenado en búfer, el codificador crea normalmente un búfer de tamaño variable y, a continuación, crea un sistema de escritura de XML sobre él. A continuación, llama a <xref:System.ServiceModel.Channels.Message.WriteMessage%28System.Xml.XmlWriter%29> en el mensaje que se está codificando que escribe los encabezados y, a continuación, el cuerpo mediante <xref:System.ServiceModel.Channels.Message.WriteBodyContents%28System.Xml.XmlDictionaryWriter%29>, como se explicó en la sección anterior sobre `Message` en este tema. El contenido del búfer (representado como una matriz de bytes) es devuelto a continuación para que lo use el canal de transporte.|  
|Codificación, secuenciada|En modo secuenciado, la operación es similar a la anterior, pero más sencilla. No hay necesidad de un búfer. Un sistema de escritura de XML se crea normalmente sobre la secuencia y se llama a <xref:System.ServiceModel.Channels.Message.WriteMessage%28System.Xml.XmlWriter%29> en el `Message` para escribirlo en este sistema de escritura.|  
|Decodificación, almacenado en búfer|Al decodificar en modo de almacenado en búfer, se crea normalmente una subclase `Message` especial que contiene los datos almacenados en búfer. Se leen los encabezados del mensaje y se crea un lector XML colocado en el cuerpo del mensaje. Éste es el lector que se devolverá con <xref:System.ServiceModel.Channels.Message.GetReaderAtBodyContents>.|  
|Decodificación, secuenciada|Al decodificar en modo secuenciado, se crea normalmente una subclase Message especial. La secuencia se avanza lo suficiente para leer todos los encabezados y colocarlos en el cuerpo del mensaje. A continuación, se crea un lector XML sobre la secuencia. Éste es el lector que se devolverá con <xref:System.ServiceModel.Channels.Message.GetReaderAtBodyContents>.|  
  
 Los codificadores también pueden realizar otras funciones. Por ejemplo, los codificadores pueden agrupar sistemas de lectura y escritura XML. Es caro crear un nuevo sistema de lectura o escritura XML cada vez que se necesita. Por consiguiente, los codificadores mantienen normalmente un grupo de sistemas de lectura y escritura de tamaño configurable. En las descripciones de la operación del codificador descrita anteriormente, cada vez que se usa la frase "crear un lector/escritor XML", normalmente significa "tomar una del grupo o crear una si no hay ninguna disponible". El codificador, así como las subclases `Message` que se crean con la descodificación, contienen la lógica para devolver sistemas de lectura y escritura a los grupos cuando ya no se necesitan, por ejemplo, cuando se cierra el `Message` ).  
  
 WCF proporciona tres codificadores de mensajes, aunque es posible crear tipos personalizados adicionales. Los tipos proporcionados son Texto, Binario y Mecanismo de optimización de transmisión de mensajes (MTOM). Estos se describen en detalle en [Choosing a Message Encoder](choosing-a-message-encoder.md).  
  
### <a name="the-istreamprovider-interface"></a>La interfaz IStreamProvider  

 Al escribir un mensaje saliente que contiene un cuerpo transmitido a un sistema de escritura XML, <xref:System.ServiceModel.Channels.Message> utilizará una secuencia de llamadas similar a la siguiente en su implementación <xref:System.ServiceModel.Channels.Message.OnWriteBodyContents%28System.Xml.XmlDictionaryWriter%29> :  
  
- Escriba cualquier información necesaria que preceda a la secuencia (por ejemplo, la etiqueta de apertura XML)  
  
- Escriba la secuencia.  
  
- Escriba cualquier información que siga a la secuencia (por ejemplo, la etiqueta de cierre XML)  
  
 Esto funciona bien con codificaciones similares a la codificación XML textual. Sin embargo, hay algunas codificaciones que no proporcionan información del conjunto de información XML (por ejemplo, etiquetas para iniciar y finalizar elementos XML) junto con los datos contenidos en los elementos. Por ejemplo, para la codificación MTOM, la codificación del mensaje se divide en varias partes. Una parte contiene el conjunto de información XML, que puede contener referencias a otras partes de contenido de elementos reales. Puesto que el conjunto de información XML es normalmente pequeño en comparación con el contenido secuenciado, tiene sentido almacenar en búfer el conjunto de información, escribirlo y, a continuación, escribir el contenido de manera secuenciada. Esto significa que cuando se escribe la etiqueta del elemento de cierre, no se debería haber escrito todavía la secuencia.  
  
 Para este propósito, se utiliza la interfaz <xref:System.Xml.IStreamProvider> . La interfaz tiene un método <xref:System.Xml.IStreamProvider.GetStream> que devuelve la secuencia que se va a escribir. La manera correcta de escribir un cuerpo de mensaje transmitido <xref:System.ServiceModel.Channels.Message.OnWriteBodyContents%28System.Xml.XmlDictionaryWriter%29> es la siguiente:  
  
1. Escriba cualquier información necesaria que preceda a la secuencia (por ejemplo, la etiqueta de apertura XML)  
  
2. Llame a la sobrecarga `WriteValue` en el <xref:System.Xml.XmlDictionaryWriter> que toma <xref:System.Xml.IStreamProvider>, con una implementación `IStreamProvider` que devuelve la secuencia que se va a escribir.  
  
3. Escriba cualquier información que siga a la secuencia (por ejemplo, la etiqueta de cierre XML)  
  
 Con este enfoque, el sistema de escritura XML puede escoger cuándo llamar <xref:System.Xml.IStreamProvider.GetStream> y escribir los datos transmitidos por secuencias. Por ejemplo, los sistemas de escritura XML textuales y binarios lo llamarán inmediatamente y escribirán el contenido transmitido por secuencias entre las etiquetas de inicio y cierre. El sistema de escritura de MTOM puede decidir llamar <xref:System.Xml.IStreamProvider.GetStream> posteriormente, cuando esté listo para escribir la parte adecuada del mensaje.  
  
## <a name="representing-data-in-the-service-framework"></a>Representación de datos en el marco de trabajo de servicio  

 Como se indica en la sección "arquitectura básica" de este tema, el marco de trabajo de servicio es la parte de WCF que, entre otras cosas, es responsable de la conversión entre un modelo de programación fácil de obtener para los datos de mensaje y `Message` las instancias reales. Normalmente, un intercambio de mensajes se representa en el marco de trabajo de servicio como un .NET Framework método marcado con el <xref:System.ServiceModel.OperationContractAttribute> atributo. El método puede tomar algunos parámetros y devolver un valor devuelto o parámetros out (o ambos). En el lado de servicio, los parámetros de entrada representan el mensaje entrante y el valor devuelto y los parámetros out representan el mensaje saliente. En el lado de cliente, se cumple lo contrario. El modelo de programación para la descripción de mensajes mediante el uso de parámetros y el valor devuelto se describe en detalle en [Specifying Data Transfer in Service Contracts](specifying-data-transfer-in-service-contracts.md). Sin embargo, esta sección proporcionará una información general resumida.  
  
## <a name="programming-models"></a>Modelos de programación  

 El marco de trabajo de servicio de WCF admite cinco modelos de programación diferentes para describir mensajes:  
  
### <a name="1-the-empty-message"></a>1. El mensaje vacío  

 Éste es el caso más simple. Para describir un mensaje entrante vacío, no utilice ningún parámetro de entrada.  
  
 [!code-csharp[C_DataArchitecture#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_dataarchitecture/cs/source.cs#3)]
 [!code-vb[C_DataArchitecture#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_dataarchitecture/vb/source.vb#3)]  
  
 Para describir un mensaje saliente vacío, utilice un valor devuelto nulo y no utilice ningún parámetro out:  
  
 [!code-csharp[C_DataArchitecture#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_dataarchitecture/cs/source.cs#4)]
 [!code-vb[C_DataArchitecture#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_dataarchitecture/vb/source.vb#4)]  
  
 Observe que esto es diferente de un contrato de operación unidireccional:  
  
 [!code-csharp[C_DataArchitecture#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_dataarchitecture/cs/source.cs#5)]
 [!code-vb[C_DataArchitecture#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_dataarchitecture/vb/source.vb#5)]  
  
 En el ejemplo `SetDesiredTemperature` , se describe un patrón de intercambio de mensajes bidireccional. Se devuelve un mensaje de la operación, pero está vacío. Es posible devolver un error de la operación. En el ejemplo "Definir bombilla", el patrón de intercambio de mensajes es unidireccional, por lo que no hay ningún mensaje saliente para describir. El servicio no puede devolver ningún estado al cliente en este caso.  
  
### <a name="2-using-the-message-class-directly"></a>2. Uso de la clase Message directamente  

 Es posible utilizar directamente la clase <xref:System.ServiceModel.Channels.Message> (o una de sus subclases) en un contrato de operación. En este caso, el marco de trabajo de servicio simplemente pasa el `Message` de la operación a la pila de canales y viceversa, sin procesamiento adicional.  
  
 Hay dos casos principales para utilizar directamente `Message` . Puede utilizar esto para escenarios avanzados, cuando ninguno de los otros modelos de programación le da suficiente flexibilidad para poder describir su mensaje. Por ejemplo, podría desear utilizar los archivos de un disco para describir un mensaje, con las propiedades de los archivos transformándose en encabezados del mensaje y el contenido de los archivos convirtiéndose en el cuerpo del mensaje. Puede crear a continuación algo similar a lo siguiente.  
  
 [!code-csharp[C_DataArchitecture#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_dataarchitecture/cs/source.cs#6)]
 [!code-vb[C_DataArchitecture#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_dataarchitecture/vb/source.vb#6)]  
  
 El segundo uso más extendido de un `Message` en un contrato de operación tiene lugar cuando un servicio no se preocupa del contenido concreto del mensaje y actúa sobre el mensaje como sobre una caja negra. Por ejemplo, puede que tenga un servicio que reenvíe los mensajes a múltiples destinatarios. El contrato se puede escribir del siguiente modo.  
  
 [!code-csharp[C_DataArchitecture#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_dataarchitecture/cs/source.cs#7)]
 [!code-vb[C_DataArchitecture#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_dataarchitecture/vb/source.vb#7)]  
  
 La línea Action = "*" desactiva eficazmente el envío de mensajes y garantiza que todos los mensajes enviados al `IForwardingService` contrato hagan su camino a la `ForwardMessage` operación. (Normalmente, el distribuidor examinaría el encabezado "Action" del mensaje para determinar la operación para la que está previsto. Action = " \* " significa "todos los valores posibles del encabezado de acción"). La combinación de Action = " \* " y el uso de Message como parámetro se conoce como "contrato universal", ya que es capaz de recibir todos los mensajes posibles. Para poder enviar todos los mensajes posibles, use Message como valor devuelto y establézcalo `ReplyAction` en " \* ". Esto evitará que el marco de trabajo de servicio agregue su propio encabezado Action, lo que permite controlar este encabezado mediante el uso del objeto `Message` devuelto.  
  
### <a name="3-message-contracts"></a>3. Contratos de mensajes  

 WCF proporciona un modelo de programación declarativo para la descripción de mensajes, denominado *contratos de mensajes*. Este modelo se describe en detalle en [Using Message Contracts](using-message-contracts.md). Esencialmente, el mensaje completo se representa mediante un tipo de .NET Framework único que utiliza atributos como <xref:System.ServiceModel.MessageBodyMemberAttribute> y <xref:System.ServiceModel.MessageHeaderAttribute> para describir qué partes de la clase de contrato de mensaje se deben asignar a qué parte del mensaje.  
  
 Los contratos de mensajes proporcionan mucho control sobre las instancias `Message` resultantes (aunque obviamente no tanto control como el resultante al utilizar directamente la clase `Message` ). Por ejemplo, los cuerpos de mensajes se crean a menudo a partir de varias partes de información, cada una representada por su propio elemento XML. Estos elementos pueden hallarse directamente en el cuerpo (modo *vacío* ) o pueden *ajustarse* en un elemento XML que los abarque. Utilizar el modelo de programación de contrato de mensajes permite decidir entre desnudo y ajustado y controlar el nombre del nombre del contenedor y del espacio de nombres.  
  
 El siguiente ejemplo de código de un contrato de mensajes muestra estas características.  
  
 [!code-csharp[C_DataArchitecture#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_dataarchitecture/cs/source.cs#9)]
 [!code-vb[C_DataArchitecture#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_dataarchitecture/vb/source.vb#9)]  
  
 Los elementos marcados para serializar (con <xref:System.ServiceModel.MessageBodyMemberAttribute>, <xref:System.ServiceModel.MessageHeaderAttribute>u otros atributos relacionados) deben ser serializables para participar en un contrato de mensaje. Para obtener más información, vea la sección "serialización" más adelante en este tema.  
  
### <a name="4-parameters"></a>4. Parámetros  

 A menudo, un desarrollador que desea describir una operación que actúa en varios pedazos de datos no necesita el grado de control que los contratos de mensajes proporcionan. Por ejemplo, al crear los nuevos servicios, uno normalmente no desea tomar la decisión de desnudo frente a ajustado, sino decidirse por el nombre del elemento contenedor. La toma de estas decisiones a menudo requiere un amplio conocimiento de servicios Web y SOAP.  
  
 El marco de trabajo de servicio de WCF puede elegir automáticamente la representación SOAP mejor y más interoperable para enviar o recibir varias partes relacionadas de la información, sin forzar a estas opciones en el usuario. Para ello, basta con describir estos fragmentos de información como parámetros o valores devueltos de un contrato de operación. Por ejemplo, considere el siguiente contrato de operación:  
  
 [!code-csharp[C_DataArchitecture#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_dataarchitecture/cs/source.cs#11)]
 [!code-vb[C_DataArchitecture#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_dataarchitecture/vb/source.vb#11)]  
  
 El marco de trabajo de servicio decide automáticamente colocar las tres piezas de información (`customerID`, `item`y `quantity`) en el cuerpo del mensaje y ajustarlas en un elemento contenedor denominado `SubmitOrderRequest`.  
  
 Describir la información que se va a enviar o recibir como una simple lista de parámetros de contratos de operaciones es el enfoque recomendado, a menos que tenga razones especiales para pasar al contrato de mensaje más complejo o a los modelos de programación basados en `Message`.  
  
### <a name="5-stream"></a>5. Secuencia  

 Utilizar `Stream` o una de sus subclases en un contrato de operación o como una sola parte del cuerpo del mensaje en un contrato de mensajes puede considerarse como  un modelo de programación independiente de los descritos anteriormente. Utilizar `Stream` de esta manera es la única manera de garantizar que su contrato se podrá usar de manera secuenciada, sin tener que escribir su propia subclase `Message` compatible con transmisión por secuencias. Para obtener más información, consulte [datos y streaming de gran tamaño](large-data-and-streaming.md).  
  
 Cuando `Stream` o una de sus subclases se utiliza de esta manera, no se invoca el serializador. Para los mensajes salientes, se crea una subclase `Message` de transmisión por secuencias y la secuencia se escribe tal y como se describe en la sección sobre la interfaz <xref:System.Xml.IStreamProvider> . Para los mensajes entrantes, el marco de trabajo de servicio crea una subclase `Stream` sobre el mensaje entrante y la proporciona a la operación.  
  
## <a name="programming-model-restrictions"></a>Restricciones del modelo de programación  

 No se pueden combinar los modelos de programación descritos anteriormente de manera arbitraria. Por ejemplo, si una operación acepta un tipo de contrato de mensajes, el contrato de mensajes debe ser su único parámetro de entrada. Lo que es más, la operación debe devolver a continuación un mensaje vacío (tipo de valor devuelto de vacío) u otro contrato de mensajes. Estas restricciones del modelo de programación se describen en los temas de cada modelo de programación concreto: [Using Message Contracts](using-message-contracts.md), [Using the Message Class](using-the-message-class.md)y [Large Data and Streaming](large-data-and-streaming.md).  
  
## <a name="message-formatters"></a>Formateadores de mensajes  

 Los modelos de programación descritos anteriormente se admiten agregando componentes llamados *formateadores de mensajes* en el marco de trabajo de servicio. Los formateadores de mensajes son tipos que implementan la <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter> <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter> interfaz o, o ambos, para su uso en clientes y clientes de WCF de servicio, respectivamente.  
  
 A los formateadores de mensajes se le agregan normalmente comportamientos. Por ejemplo, <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior> agrega el formateador de mensajes de contratos de datos. Esto se hace en el lado de servicio estableciendo <xref:System.ServiceModel.Dispatcher.DispatchOperation.Formatter%2A> en el formateador correcto en el método <xref:System.ServiceModel.Description.IOperationBehavior.ApplyDispatchBehavior%28System.ServiceModel.Description.OperationDescription%2CSystem.ServiceModel.Dispatcher.DispatchOperation%29> o en el lado de cliente estableciendo <xref:System.ServiceModel.Dispatcher.ClientOperation.Formatter%2A> en el formateador correcto en el método <xref:System.ServiceModel.Description.IOperationBehavior.ApplyClientBehavior%28System.ServiceModel.Description.OperationDescription%2CSystem.ServiceModel.Dispatcher.ClientOperation%29> .  
  
 Las siguientes tablas enumeran los métodos que un formateador de mensajes puede implementar.  
  
|Interfaz|Método|Acción|  
|---------------|------------|------------|  
|<xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter>|<xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter.DeserializeRequest%28System.ServiceModel.Channels.Message%2CSystem.Object%5B%5D%29>|Convierte un `Message` entrante en parámetros de operación|  
|<xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter>|<xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter.SerializeReply%28System.ServiceModel.Channels.MessageVersion%2CSystem.Object%5B%5D%2CSystem.Object%29>|Crea un `Message` saliente a partir del valor devuelto/parámetros out de la operación|  
|<xref:System.ServiceModel.Dispatcher.IClientMessageFormatter>|<xref:System.ServiceModel.Dispatcher.IClientMessageFormatter.SerializeRequest%28System.ServiceModel.Channels.MessageVersion%2CSystem.Object%5B%5D%29>|Crea un `Message` saliente a partir de los parámetros de operación|  
|<xref:System.ServiceModel.Dispatcher.IClientMessageFormatter>|<xref:System.ServiceModel.Dispatcher.IClientMessageFormatter.DeserializeReply%28System.ServiceModel.Channels.Message%2CSystem.Object%5B%5D%29>|Convierte un `Message` entrante en un valor devuelto/parámetros out|  
  
## <a name="serialization"></a>Serialización  

 Siempre que use contratos de mensajes o parámetros para describir el contenido de los mensajes, debe utilizar la serialización para convertir entre .NET Framework tipos y la representación del conjunto de código XML. La serialización se utiliza en otros lugares en WCF, por ejemplo, <xref:System.ServiceModel.Channels.Message> tiene un <xref:System.ServiceModel.Channels.Message.GetBody%2A> método genérico que puede usar para leer el cuerpo completo del mensaje deserializado en un objeto.  
  
 WCF admite dos tecnologías de serialización "preparadas" para serializar y deserializar parámetros y partes de mensajes: <xref:System.Runtime.Serialization.DataContractSerializer> y `XmlSerializer` . Además, puede escribir serializadores personalizados. Sin embargo, otras partes de WCF (como el `GetBody` método genérico o la serialización de errores de SOAP) pueden estar restringidas a usar solo las <xref:System.Runtime.Serialization.XmlObjectSerializer> subclases ( <xref:System.Runtime.Serialization.DataContractSerializer> y <xref:System.Runtime.Serialization.NetDataContractSerializer> , pero no <xref:System.Xml.Serialization.XmlSerializer> ) o incluso estar codificadas de forma rígida para usar solo <xref:System.Runtime.Serialization.DataContractSerializer> .  
  
 `XmlSerializer`Es el motor de serialización utilizado en los servicios Web de ASP.net. `DataContractSerializer` es el nuevo motor de serialización que entiende el nuevo modelo de programación de contrato de datos. `DataContractSerializer` es la opción predeterminada, y la decisión de usar `XmlSerializer` se puede tomar según la operación mediante el atributo <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior.DataContractFormatAttribute%2A> .  
  
 <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior> y <xref:System.ServiceModel.Description.XmlSerializerOperationBehavior> son los comportamientos de operaciones responsables de agregar los formateadores de mensajes para  el `DataContractSerializer` y `XmlSerializer`, respectivamente. El comportamiento <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior> puede realmente funcionar con cualquier serializador que derive de <xref:System.Runtime.Serialization.XmlObjectSerializer>, incluso <xref:System.Runtime.Serialization.NetDataContractSerializer> (descrito en detalle en Uso de serialización independiente). El comportamiento llama a una de las sobrecargas de método virtual `CreateSerializer` para obtener el serializador. Para agregar un serializador diferente, cree una nueva subclase <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior> e invalide ambas sobrecargas `CreateSerializer` .  
  
## <a name="see-also"></a>Vea también

- [Especificación de transferencia de datos en contratos de servicio](specifying-data-transfer-in-service-contracts.md)
