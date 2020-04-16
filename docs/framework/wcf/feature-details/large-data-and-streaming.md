---
title: Datos de gran tamaño y secuencias
ms.date: 03/30/2017
ms.assetid: ab2851f5-966b-4549-80ab-c94c5c0502d2
ms.openlocfilehash: 4b6275a27fb1e09ecac1f8f00f56068a80a214ef
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2020
ms.locfileid: "81464080"
---
# <a name="large-data-and-streaming"></a>Datos de gran tamaño y secuencias

Windows Communication Foundation (WCF) es una infraestructura de comunicaciones basada en XML. Dado que los datos XML se codifican normalmente en el formato de texto estándar definido en la [especificación XML 1.0,](https://www.w3.org/TR/REC-xml/)los desarrolladores y arquitectos de sistemas conectados suelen estar preocupados por la huella de cable (o tamaño) de los mensajes enviados a través de la red, y la codificación basada en texto de XML plantea desafíos especiales para la transferencia eficiente de datos binarios.  
  
## <a name="basic-considerations"></a>Consideraciones básicas  
 Para proporcionar información general acerca de la siguiente información para WCF, esta sección destaca algunas preocupaciones y consideraciones generales para las codificaciones, datos binarios y streaming que generalmente se aplican a las infraestructuras de sistemas conectados.  
  
### <a name="encoding-data-text-vs-binary"></a>Codificar datos: Texto y Binario  
 Entre las preocupaciones que suelen expresar los programadores se incluyen la percepción de que XML supone un exceso de trabajo significativo en comparación con los formatos binarios debido a la naturaleza repetitiva de las etiquetas de inicio y de cierre, que la codificación de los valores numéricos es significativamente más larga porque se expresan en valores de texto y que esos datos binarios no se pueden expresar eficazmente porque deben codificarse de forma especial para incrustarse en un formato de texto.  
  
 Aunque muchos de estos aspectos y otros similares son válidos, la diferencia real entre los mensajes codificados en texto XML en un entorno de servicios Web XML y los mensajes con codificación binaria en un entorno de llamada a procedimiento remoto (RPC) heredado es, a menudo, mucho menos significativa que la consideración inicial podría sugerir.  
  
 Mientras que los mensajes codificados en texto XML son transparentes y legibles, en comparación, los mensajes binarios son, a menudo, bastante oscuros y difíciles de descifrar sin herramientas. Esta diferencia de legibilidad hace que nos olvidemos de que los mensajes binarios, a menudo, también llevan metadatos insertados en la carga útil, lo cual agrega sobrecarga, como ocurre con los mensajes de texto XML. Esto es específicamente verdadero para los formatos binarios que pretenden proporcionar correspondencia imprecisa y funciones de invocación dinámicas.  
  
 Sin embargo, normalmente los formatos binarios llevan esta información descriptiva de los metadatos en un "encabezado", que también declara el diseño de datos para los registros de datos siguientes. A continuación, la carga útil sigue esta declaración de bloque de metadatos comunes con sobrecarga mínima. En cambio, XML incluye cada elemento de datos en un elemento o atributo para que los metadatos envolventes estén incluidos repetidamente en cada objeto de carga útil serializado. Como resultado, el tamaño de un objeto de carga útil serializado único es similar si se comparan las representaciones binaria y de texto cuando es necesario expresar metadatos descriptivos para ambos. Sin embargo, el formato binario se beneficia de la descripción de metadatos compartida con cada objeto de carga útil adicional que se transfiere, ya que la sobrecarga total es más baja.  
  
 No obstante, para ciertos tipos de datos, como números, podría haber un inconveniente al utilizar representaciones numéricas binarias de tamaño fijo, como un tipo decimal de 128 bits en lugar de texto sin formato, ya que la representación de texto sin formato podría ser varios bytes menor. Los datos de texto también podrían tener ventajas de tamaño por las opciones de codificación de texto XML normalmente más flexibles, mientras que algunos formatos binarios podrían establecerse como valor predeterminado a 16 bits o incluso Unicode de 32 bits, lo cual no se aplica a Binario .NET y Formato XML.  
  
 Por lo tanto, la decisión entre el formato de texto y el binario no consiste solamente en suponer que los mensajes binarios son siempre más pequeños que los mensajes de texto XML.  
  
 Una ventaja clara de los mensajes de texto XML es que están basados en estándares y proporcionan la opción más completa en cuanto a interoperabilidad y compatibilidad de plataforma. Para obtener más información, consulte la sección "Codificaciones" más adelante en este tema.  
  
### <a name="binary-content"></a>Contenido binario  
 Un área en la cual las codificaciones binarias son superiores a las codificaciones basadas en texto con respecto al tamaño del mensaje resultante es elementos de datos binarios de gran tamaño como imágenes, vídeos, secuencias de sonido o cualquier otra forma de datos opacos y binarios que se deben intercambiar entre los servicios y sus consumidores. Para ajustar estos tipos de datos en el texto XML, el enfoque común es codificarlos utilizando la codificación de Base64.  
  
 En una cadena codificada con Base64, cada carácter representa 6 bits de los datos originales de 8 bits, que producen una proporción de sobrecarga de codificación de 4:3 para Base64, sin contar caracteres de formato adicionales (retorno de carro/salto de línea) que se agregan normalmente por convención. Aunque la trascendencia de las diferencias entre la codificación XML y binaria depende normalmente del escenario, un aumento de tamaño superior al 33% cuando se transmite una carga útil de 500 MB no suele ser aceptable.  
  
 Para evitar esta sobrecarga de codificación, la norma del Mecanismo de optimización de transmisión del mensaje (MTOM) permite exteriorizar elementos de datos de gran tamaño contenidos en un mensaje y llevarlos con el mensaje como datos binarios sin ninguna codificación especial. Con MTOM, los mensajes se intercambian de forma similar a los mensajes de correo electrónico del Protocolo simple de transferencia de correo (SMTP) con archivos adjuntos o contenido incrustado (imágenes y otro contenido incrustado); Los mensajes MTOM se empaquetan como secuencias MIME multiparte/relacionadas con la parte raíz como el mensaje SOAP real.  
  
 Un mensaje SOAP de MTOM se modifica a partir de su versión descodificada para que las etiquetas de elementos especiales que hacen referencia a las correspondientes partes MIME sustituyan a los elementos originales que contenían datos binarios en el mensaje. Como resultado, el mensaje SOAP hace referencia al contenido binario señalando las partes MIME enviadas con él, pero, de lo contrario, solo lleva datos de texto XML. Dado que este modelo está alineado estrechamente con el modelo de SMTP bien establecido, hay una gran compatibilidad con las herramientas para codificar y descodificar los mensajes MTOM en muchas plataformas, lo cual lo convierte en una opción sumamente interoperable.  
  
 No obstante, como con Base64, MTOM viene también con alguna sobrecarga necesaria para el formato MIME, para que solamente se vean las ventajas de utilizar MTOM cuando el tamaño de un elemento de datos binarios supera aproximadamente 1 KB. Debido a la sobrecarga, los mensajes codificados por MTOM podrían ser mayores que los mensajes que usan la codificación Base64 para datos binarios, si la carga binaria permanece bajo ese umbral. Para obtener más información, consulte la sección "Codificaciones" más adelante en este tema.  
  
### <a name="large-data-content"></a>Contenido de datos de gran tamaño  
 Superficie de la conexión a parte, la carga útil de 500 MB previamente mencionada también supone un gran desafío local para el servicio y para el cliente. De forma predeterminada, WCF procesa los mensajes en modo almacenado en *búfer.* Esto significa que todo el contenido de un mensaje está presente en la memoria antes de enviarse o una vez recibido. Aunque es una estrategia acertada para la mayoría de los escenarios y necesaria para el uso de características de mensajería tales como las firmas digitales y la entrega confiable, los mensajes grandes podrían agotar los recursos del sistema.  
  
 La estrategia para tratar con cargas útiles de gran tamaño es usar secuencias. Aunque se suele considerar que los mensajes, en especial aquellos que se expresan en XML, son paquetes de datos relativamente compactos, un mensaje podría tener un tamaño de varios gigabytes y parecerse más a un flujo de datos continuo que a un paquete de datos. Cuando los datos se transfieren en modo de transmisión por secuencias en lugar de en modo de almacenamiento en búfer, el remitente hace que el contenido del cuerpo del mensaje esté disponible para el destinatario en forma de secuencia y la infraestructura del mensaje reenvía continuamente los datos del remitente al receptor a medida que están disponibles.  
  
 El escenario más común en el que se producen estas transferencias de contenido de datos de gran tamaño son transferencias de objetos de datos binarios que:  
  
- No se pueden dividir con facilidad en una secuencia del mensaje.  
  
- Se deben entregar de forma puntual.  
  
- No están disponibles en su totalidad cuando se inicia la transferencia.  
  
 Para los datos que no tienen estas restricciones, normalmente es mejor enviar secuencias de mensajes dentro del ámbito de una sesión que un mensaje de gran tamaño. Para obtener más información, consulte la sección "Streaming Data" más adelante en este tema.  
  
 Al enviar grandes cantidades de datos, `maxAllowedContentLength` deberá establecer la configuración de IIS (para `maxReceivedMessageSize` obtener más información, vea Configuración de límites de solicitudes de [IIS](https://docs.microsoft.com/iis/configuration/system.webServer/security/requestFiltering/requestLimits/)) y la configuración de enlace (por [ejemplo, System.ServiceModel.BasicHttpBinding.MaxReceivedMessageSize](xref:System.ServiceModel.HttpBindingBase.MaxReceivedMessageSize%2A) o <xref:System.ServiceModel.NetTcpBinding.MaxReceivedMessageSize%2A>). El `maxAllowedContentLength` valor predeterminado de la propiedad `maxReceivedMessageSize` es 28,6 MB y el valor predeterminado de la propiedad es 64KB.  
  
## <a name="encodings"></a>Codificaciones  
 Una *codificación* define un conjunto de reglas sobre cómo presentar mensajes en la conexión. Un *codificador* implementa dicha codificación y es responsable, en el <xref:System.ServiceModel.Channels.Message> lado del remitente, de convertir una secuencia de bytes o un búfer de bytes que se puede enviar a través de la red. En el lado del receptor, el codificador convierte una secuencia de bytes en un mensaje en memoria.  
  
 WCF incluye tres codificadores y le permite escribir y conectar sus propios codificadores, si es necesario.  
  
 Cada uno de los enlaces estándar incluyen un codificador preconfigurado, por medio del cual los enlaces con el prefijo Net* utilizan el codificador binario (incluyendo la clase <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>) mientras que <xref:System.ServiceModel.BasicHttpBinding> y las clases <xref:System.ServiceModel.WSHttpBinding> utilizan de forma predeterminada el codificador del mensaje de texto (por medio de la clase <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>).  
  
|Elemento de enlace del codificador.|Descripción|  
|-----------------------------|-----------------|  
|<xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>|El codificador del mensaje de texto es el codificador predeterminado para todos los enlaces basados en HTTP y la opción adecuada para todos los enlaces personalizados donde la interoperabilidad es la preocupación superior. Este codificador lee y escribe los mensajes de texto SOAP 1.1/SOAP 1.2 estándar sin control especial para los datos binarios. Si <xref:System.ServiceModel.Channels.MessageVersion?displayProperty=nameWithType> la propiedad de un <xref:System.ServiceModel.Channels.MessageVersion.None?displayProperty=nameWithType>mensaje se establece en , el contenedor de sobresoap se omite de la salida y solo se serializa el contenido del cuerpo del mensaje.|  
|<xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>|El codificador del mensaje MTOM es un codificador de texto que implementa el control especial para los datos binarios y no se utiliza de forma predeterminada en ninguno de los enlaces estándar porque es estrictamente una utilidad de optimización caso por caso. Si el mensaje contiene datos binarios que superan un umbral donde la codificación MTOM produce una ventaja, los datos se exteriorizan en una parte MIME que sigue a la envoltura del mensaje. Vea "Habilitar MTOM" más adelante en esta sección.|  
|<xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>|El codificador de mensajes binarios es el codificador predeterminado para los enlaces Net* y la opción adecuada siempre que ambas partes comunicantes se basan en WCF. El codificador del mensaje binario utiliza el Formato XML Binario .NET, una representación binaria específica de Microsoft para conjuntos de información XML (Infosets) que generalmente produce una superficie menor que la representación equivalente XML 1.0 y codifica los datos binarios como una secuencia de bytes.|  
  
 La codificación de mensajes de texto es normalmente la mejor opción para cualquier ruta de comunicación que requiere interoperabilidad, mientras que la codificación de mensajes binaria es la mejor opción para cualquier otra ruta de comunicación. La codificación de mensajes binarios produce normalmente tamaños de mensaje menores comparados con el texto para un mensaje único e, incluso, tamaños de mensaje progresivamente menores durante la duración de una sesión de comunicación. A diferencia de la codificación de texto, la codificación binaria no tiene que utilizar control especial para los datos binarios, como cuando se utiliza Base64, pero representa los bytes como bytes.  
  
 Si su solución no requiere interoperabilidad, pero todavía quiere utilizar el transporte HTTP, puede crear <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement> en un enlace personalizado que utiliza la clase <xref:System.ServiceModel.Channels.HttpTransportBindingElement> para el transporte. Si varios clientes en su servicio requieren interoperabilidad, se recomienda que exponga puntos de conexión paralelos que tengan el transporte adecuado y las opciones de codificación para los respectivos clientes habilitadas.  
  
### <a name="enabling-mtom"></a>Habilitar MTOM  
 Cuando la interoperabilidad es un requisito y se deben enviar datos binarios de gran tamaño, a continuación, la codificación de mensajes MTOM es la estrategia alternativa de codificación que puede habilitar en los <xref:System.ServiceModel.BasicHttpBinding> estándar o enlaces <xref:System.ServiceModel.WSHttpBinding> estableciendo la propiedad `MessageEncoding` respectiva a <xref:System.ServiceModel.WSMessageEncoding.Mtom> o creando <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> en <xref:System.ServiceModel.Channels.CustomBinding>. El siguiente código de ejemplo, extraído del ejemplo [de codificación MTOM,](../../../../docs/framework/wcf/samples/mtom-encoding.md) muestra cómo habilitar MTOM en la configuración.  
  
```xml  
<system.serviceModel>  
     …  
    <bindings>  
      <wsHttpBinding>  
        <binding name="ExampleBinding" messageEncoding="Mtom"/>  
      </wsHttpBinding>  
    </bindings>  
     …  
</system.serviceModel>  
```  
  
 Tal y como se ha mencionado anteriormente, la decisión de utilizar la codificación MTOM depende del volumen de datos que está enviando. Además, como MTOM está habilitado en el nivel de enlace, habilitar MTOM afecta a todas las operaciones en un punto de conexión determinado.  
  
 Dado que el codificador MTOM siempre emite un mensaje MIME/de varias partes codificado con MTOM sin tener en cuenta si los datos binarios acaban exteriorizándose, generalmente se debería habilitar MTOM solo para los puntos de conexión que intercambian los mensajes con más de 1 KB de datos binarios. Asimismo, los contratos de servicios diseñados para el uso con puntos de conexión habilitados por MTOM deben, cuando sea posible, ser restringidos a especificar tales operaciones de transferencia de datos. La funcionalidad de control relacionada debería residir en un contrato independiente. Esta norma "solo MTOM" se aplica solamente a los mensajes enviados a través de un punto de conexión habilitado por MTOM; el codificador MTOM puede descodificar y analizar también los mensajes de entrada no MTOM.  
  
 El uso del codificador MTOM se ajusta a todas las demás características de WCF. Tenga en cuenta que tal vez no sea posible respetar esta regla en todos los casos, por ejemplo, cuando se requiere la compatibilidad de la sesión.  
  
### <a name="programming-model"></a>Modelo de programación  
 Independientemente de cuál de los tres codificadores integrados utiliza en su aplicación, la experiencia de programación es idéntica con respecto a la transferencia de datos binarios. La diferencia está en cómo WCF controla los datos en función de sus tipos de datos.  
  
```csharp
[DataContract]  
class MyData  
{  
    [DataMember]  
    byte[] binaryBuffer;  
    [DataMember]  
    string someStringData;  
}
```  
  
 Al utilizar MTOM, el contrato de datos anterior se serializa según las reglas siguientes:  
  
- Si `binaryBuffer` no es `null` y contiene individualmente bastantes datos para justificar la sobrecarga de externalización de MTOM (encabezados MIME, etc.) cuando se compara con codificación Base64, los datos se exteriorizan y se llevan con el mensaje como una parte binaria de MIME. Si no se supera el umbral, se codifican los datos como Base64.  
  
- La cadena (y todos los otros tipos no binarios) se representa siempre como una cadena dentro del cuerpo del mensaje, sin tener en cuenta el tamaño.  
  
 El efecto en la codificación MTOM es el mismo con independencia de si se usa un contrato de datos explícito, como se muestra en el ejemplo anterior, si se usa una lista de parámetros en una operación, si se tienen contratos de datos anidados o si se transfiere un objeto de contrato de datos dentro de una colección. Las matrices de bytes son siempre candidatas para la optimización y se optimizan si se cumplen los umbrales de optimización.  
  
> [!NOTE]
> No debería estar utilizando tipos derivados <xref:System.IO.Stream?displayProperty=nameWithType> dentro de los contratos de datos. Los datos de la secuencia se deberían comunicar utilizando el modelo de secuencias, explicado en la sección "Transmisión por secuencias de datos".  
  
## <a name="streaming-data"></a>Transmisión por secuencias de datos  
 Cuando tiene una gran cantidad de datos para transferir, el modo de transferencia de streaming en WCF es una alternativa factible al comportamiento predeterminado de almacenamiento en búfer y procesamiento de mensajes en la memoria en su totalidad.  
  
 Como se ha mencionado anteriormente, habilite la transmisión por secuencias solo para los mensajes de gran tamaño (con contenido de texto o binario) si no se pueden segmentar los datos, si el mensaje debe entregarse puntualmente o si los datos no están todavía totalmente disponibles cuando se inicia la transferencia.  
  
### <a name="restrictions"></a>Restricciones  
 No puede usar un número significativo de características de WCF cuando se habilita la transmisión por secuencias:  
  
- No se pueden utilizar firmas digitales para el cuerpo del mensaje porque requieren calcular un hash sobre el contenido completo del mensaje. Con transmisión por secuencias, el contenido no está totalmente disponible cuando los encabezados del mensaje se construyen y envían y, por consiguiente, no se puede calcular una firma digital.  
  
- El cifrado depende de firmas digitales para comprobar que se han reconstruido los datos correctamente.  
  
- Las sesiones de confianza deben almacenar en búfer los mensajes enviados al cliente para entregarlos más tarde si se pierde un mensaje durante la transferencia y deben contener los mensajes en el servicio antes de entregarlos a la implementación del servicio para conservar el orden del mensaje en caso de que los mensajes se reciban fuera de secuencia.  
  
 Debido a estas restricciones funcionales, puede utilizar solo las opciones de seguridad de nivel de transporte para la transmisión por secuencias y no puede activar las sesiones de confianza. La transmisión por secuencias solo está disponible con los siguientes enlaces definidos por el sistema:  
  
- <xref:System.ServiceModel.BasicHttpBinding>  
  
- <xref:System.ServiceModel.NetTcpBinding>  
  
- <xref:System.ServiceModel.NetNamedPipeBinding>  
  
- <xref:System.ServiceModel.WebHttpBinding>  
  
 Dado que los transportes subyacentes de <xref:System.ServiceModel.NetTcpBinding> y <xref:System.ServiceModel.NetNamedPipeBinding> tienen una compatibilidad inherente con sesiones según la conexión y permiten una entrega confiable, a diferencia de HTTP, en la práctica estas restricciones afectan mínimamente a estos dos enlaces.  
  
 La transmisión por secciones no está disponible con el transporte de Message Queuing Server (MSMQ) y, por lo tanto, no se puede utilizar con <xref:System.ServiceModel.NetMsmqBinding> o la clase <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>. El transporte de Message Queuing solo admite las transferencias de datos almacenadas en búfer con un tamaño de mensaje restringido, mientras que el resto de transportes no tienen ningún límite del tamaño de mensaje práctico para la inmensa mayoría de escenarios.  
  
 La transmisión por secuencias no está tampoco disponible al utilizar el transporte del canal del mismo nivel, por lo que no está disponible con <xref:System.ServiceModel.NetPeerTcpBinding>.  
  
#### <a name="streaming-and-sessions"></a>Transmisión por secuencias y sesiones  
 Puede obtener un comportamiento inesperado al transmitir mediante secuencias las llamadas con un enlace basado en sesión. Todas las llamadas de transferencias por secuencias se realizan a través de un canal único (el canal del datagrama) que no admite sesiones incluso si el enlace utilizado esté configurado para utilizar sesiones. Si varios clientes realizan llamadas de transferencia por secuencias al mismo objeto de servicio sobre un enlace basado en sesión y el modo de simultaneidad del objeto de servicio se establece en Single y su modo de contexto de instancia está establecido en PerSession, todas las llamadas deben pasar por el canal de datagramas y solo se procesará una llamada al mismo tiempo. Uno o más clientes pueden entonces tiempo de espera. Puede solucionar este problema estableciendo el modo de contexto de instancia del objeto de servicio en PerCall o Simultaneidad en múltiple.  
  
> [!NOTE]
> MaxConcurrentSessions no influye en este caso porque solo hay una "sesión" disponible.  
  
### <a name="enabling-streaming"></a>Habilitar la transmisión por secuencias  
 Puede habilitar la transmisión por secuencias de las siguientes maneras:  
  
- Envíe y acepte las solicitudes en modo de transmisión y acepte y devuelva las respuestas en modo almacenado en búfer (<xref:System.ServiceModel.TransferMode.StreamedRequest>).  
  
- Envíe y acepte las solicitudes en modo de almacenamiento en búfer y acepte y devuelva las respuestas en modo de transmisión (<xref:System.ServiceModel.TransferMode.StreamedResponse>).  
  
- Envíe y reciba solicitudes y respuestas en modo de transmisión en ambas direcciones. (<xref:System.ServiceModel.TransferMode.Streamed>).  
  
 Puede deshabilitar la transmisión por secuencias estableciendo el modo de transferencia en <xref:System.ServiceModel.TransferMode.Buffered>, que es la configuración predeterminada en todos los enlaces. El código siguiente muestra cómo establecer el modo de transferencia en la configuración.  
  
```xml  
<system.serviceModel>  
     …  
    <bindings>  
      <basicHttpBinding>  
        <binding name="ExampleBinding" transferMode="Streamed"/>  
      </basicHttpBinding>  
    </bindings>  
     …  
</system.serviceModel>  
```  
  
 Cuando cree instancias de su enlace en el código, debe establecer la propiedad `TransferMode` respectiva del enlace (o el elemento de enlace del transporte si está creando un enlace personalizado) en uno de los valores previamente mencionados.  
  
 Puede activar transmisiones por secuencias para las solicitudes y respuestas o para ambas direcciones independientemente en cualquier lado de las partes en comunicación sin afectar a la funcionalidad. Sin embargo, siempre debería suponer que el tamaño de datos transferido es tan significativo que habilitar la transmisión por secuencias se justifica en ambos puntos de conexión de un enlace de comunicación. Para la comunicación multiplataforma donde uno de los extremos no se implementa con WCF, la capacidad de usar la transmisión por secuencias depende de las capacidades de transmisión por secuencias de la plataforma. Otra excepción poco frecuente podría ser un escenario conducido por consumo de memoria donde un cliente o servicio debe minimizar su espacio de trabajo y permitir solo los tamaños de búfer pequeños.  
  
### <a name="enabling-asynchronous-streaming"></a>Habilitar la transmisión de datos asincrónica  
 Para habilitar el streaming asincrónico, agregue el comportamiento de punto de conexión <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior> al host de servicio y establezca la propiedad <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior.AsynchronousSendEnabled%2A> en `true`. También hemos agregado la capacidad de transmisión de datos asincrónica verdadera en el lado de envío. Esto mejora la escalabilidad del servicio en escenarios donde transmite por secuencias mensajes para varios clientes, algunos de los cuales son lentos en la lectura; posiblemente debido a la congestión de red o que no leen en absoluto. En estos escenarios ahora no bloqueamos subprocesos individuales en el servicio por cliente. Esto garantiza que el servicio pueda procesar muchos más clientes, mejorando así la escalabilidad del servicio.  
  
### <a name="programming-model-for-streamed-transfers"></a>Modelo de programación para las transferencias de transmisión  
 El modelo de programación para transmisión es sencillo. Para recibir los datos transmitidos, especifique un contrato de operación que tiene un parámetro de entrada único de tipo <xref:System.IO.Stream>. Para devolver los datos transmitidos, devuelva una referencia <xref:System.IO.Stream>.  
  
```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface IStreamedService  
{  
    [OperationContract]  
    Stream Echo(Stream data);  
    [OperationContract]  
    Stream RequestInfo(string query);  
    [OperationContract(OneWay=true)]  
    void ProvideInfo(Stream data);  
}  
```  
  
 `Echo` en el ejemplo anterior recibe y devuelve una secuencia y se debería utilizar por consiguiente en un enlace con <xref:System.ServiceModel.TransferMode.Streamed>. Para `RequestInfo` de la operación, <xref:System.ServiceModel.TransferMode.StreamedResponse> se adapta mejor, porque solo devuelve <xref:System.IO.Stream>. La operación unidireccional se adapta mejor para <xref:System.ServiceModel.TransferMode.StreamedRequest>.  
  
 Tenga en cuenta que si se agrega un segundo parámetro a las operaciones `Echo` o `ProvideInfo` siguientes, se hace que el modelo de servicio se revierta a una estrategia con almacenamiento en búfer y se utilice la representación de serialización en tiempo de ejecución de la secuencia. Solo las operaciones con un parámetro de flujo de entrada único son compatibles con la transmisión por secuencias de solicitud de principio a fin.  
  
 Esta regla se aplica de igual forma a los contratos de mensaje. Como se muestra en el contrato de mensaje siguiente, puede tener solo un miembro de un único cuerpo en el contrato del mensaje que sea una secuencia. Si desea comunicar la información adicional con la secuencia, esta información debe estar incluida en los encabezados del mensaje. El cuerpo del mensaje se reserva exclusivamente para el contenido de la secuencia.  
  
```csharp
[MessageContract]  
public class UploadStreamMessage  
{  
   [MessageHeader]  
   public string appRef;  
   [MessageBodyMember]  
   public Stream data;  
}
```  
  
 Las transferencias con secuencias finalizan y el mensaje se cierra cuando la secuencia alcanza el final del archivo (EOF). Al enviar un mensaje (devolver un valor o invocar <xref:System.IO.FileStream> una operación), puede pasar una y la infraestructura WCF posteriormente extrae todos los datos de esa secuencia hasta que la secuencia se ha leído completamente y se ha alcanzado EOF. Para transferir datos transmitidos al origen cuando no existe clase derivada <xref:System.IO.Stream> previamente generada, construya esta clase, superponga la clase sobre su origen de secuencia y utilícelo como el argumento o valor devuelto.  
  
 Al recibir un mensaje, WCF construye una secuencia sobre el contenido del cuerpo del mensaje codificado en Base64 (o la parte MIME respectiva si se usa MTOM) y la secuencia llega a EOF cuando se ha leído el contenido.  
  
 La transmisión por secuencias del nivel de transporte también funciona con cualquier otro tipo de contrato de mensaje (listas de parámetros, argumentos de contrato de datos y el contrato del mensaje explícito), pero como la serialización y deserialización de estos mensajes con tipo definido requieren el almacenado en búfer por el serializador, no se recomienda utilizar estas variantes de contrato.  
  
### <a name="special-security-considerations-for-large-data"></a>Consideraciones de seguridad específicas para datos de gran tamaño  
 Todos los enlaces le permiten restringir el tamaño de los mensajes entrantes para evitar los ataques por denegación de servicio. El <xref:System.ServiceModel.BasicHttpBinding>, por ejemplo, expone un [System.ServiceModel.BasicHttpBinding.MaxReceivedMessageSize](xref:System.ServiceModel.HttpBindingBase.MaxReceivedMessageSize%2A) propiedad que limita el tamaño del mensaje entrante y, por lo tanto, también limita la cantidad máxima de memoria que se tiene acceso al procesar el mensaje. Esta unidad se establece en bytes con un valor predeterminado de 65.536 bytes.  
  
 Una amenaza de seguridad específica del escenario de transmisión por flujos de datos grandes provoca una denegación de servicio haciendo que se almacenen en búfer los datos cuando el receptor espera que se transmitan. Por ejemplo, WCF siempre almacena en búfer los encabezados SOAP de un mensaje, por lo que un atacante puede construir un mensaje malintencionado grande que consta enteramente de encabezados para forzar que los datos se almacenen en búfer. Cuando está habilitada la transmisión por secuencias, `MaxReceivedMessageSize` puede estar establecido en un valor sumamente grande, porque el receptor nunca espera que el mensaje completo esté almacenado en búfer en memoria a la vez. Si WCF se ve obligado a almacenar en búfer el mensaje, se produce un desbordamiento de memoria.  
  
 Por consiguiente, restringir el tamaño máximo del mensaje entrante no es suficiente en este caso. La `MaxBufferSize` propiedad es necesaria para restringir la memoria que almacena en búfer WCF. Es importante establecer esto en un valor seguro (o mantenerlo en el valor predeterminado) en la transmisión por secuencias. Por ejemplo, suponga que su servicio debe recibir los archivos hasta 4 GB en tamaño y almacenarlos en el disco local. Suponga además que su memoria se restringe de tal manera que puede almacenar en búfer solo 64 KB de datos a la vez. A continuación, establecería `MaxReceivedMessageSize` en 4 GB y `MaxBufferSize` a 64 KB. Asimismo, en su implementación de servicio debe asegurarse de que solo lee de la secuencia entrante en fragmentos de 64 KB y no leer el fragmento siguiente antes de que el anterior se haya escrito en el disco y haya sido descartado de la memoria.  
  
 También es importante comprender que esta cuota solo limita el almacenamiento en búfer realizado por WCF y no puede protegerle contra cualquier almacenamiento en búfer que realice en su propio servicio o implementación de cliente. Para obtener más información acerca de consideraciones de seguridad adicionales, vea [Consideraciones](../../../../docs/framework/wcf/feature-details/security-considerations-for-data.md)de seguridad para datos .  
  
> [!NOTE]
> La decisión de utilizar transferencias almacenadas en búfer o transmitidas es una decisión local del punto de conexión. Para los transportes HTTP, el modo de transferencia no se propaga a través de una conexión o a los servidores proxy y otros intermediarios. Establecer el modo de transferencia no se refleja en la descripción de la interfaz de servicio. Después de generar un cliente WCF a un servicio, debe editar el archivo de configuración para los servicios destinados a usarse con transferencias transmitidas para establecer el modo. En los transportes con canalizaciones con nombre y TCP, el modo de transferencia se propaga como una aserción de directiva.  
  
## <a name="see-also"></a>Consulte también

- [Procedimiento para habilitar el streaming](../../../../docs/framework/wcf/feature-details/how-to-enable-streaming.md)
