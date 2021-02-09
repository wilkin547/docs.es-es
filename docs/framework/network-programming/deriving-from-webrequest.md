---
description: 'Más información acerca de: Derivar de WebRequest'
title: Derivar de WebRequest
ms.date: 03/30/2017
helpviewer_keywords:
- WebRequest class, pluggable protocols
- protocol-specific request handler
- sending data, pluggable protocols
- pluggable protocols, class criteria
- Internet, pluggable protocols
- receiving data, pluggable protocols
- protocols, pluggable
ms.assetid: 9810c177-973e-43d7-823c-14960bd625ea
ms.openlocfilehash: ede2480767f11ef66bccc79ab4e3a4bc8aafc1fb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801909"
---
# <a name="deriving-from-webrequest"></a>Derivar de WebRequest

La clase <xref:System.Net.WebRequest> es una clase base abstracta que proporciona las propiedades y métodos básicos para crear un controlador de solicitudes específico del protocolo adecuado al modelo de protocolo acoplable de .NET Framework. Las aplicaciones que usan la clase **WebRequest** pueden solicitar datos mediante cualquier protocolo admitido sin necesidad de especificar el protocolo empleado.  
  
 Para usar una clase específica del protocolo como protocolo acoplable se deben cumplir dos criterios: la clase debe implementar la interfaz <xref:System.Net.IWebRequestCreate> y se debe registrar con el método <xref:System.Net.WebRequest.RegisterPrefix%2A?displayProperty=nameWithType>. La clase debe invalidar todos los métodos y propiedades abstractos de **WebRequest** para proporcionar la interfaz acoplable.  
  
 Las instancias de **WebRequest** están diseñadas para un solo uso; si quiere realizar otra solicitud, cree una nueva instancia de **WebRequest**. **WebRequest** admite la interfaz <xref:System.Runtime.Serialization.ISerializable> para permitir que los desarrolladores serialicen una plantilla **WebRequest** y luego vuelvan a crear la plantilla para otras solicitudes.  
  
## <a name="iwebrequest-create-method"></a>Método Create de IWebRequest  

 El método <xref:System.Net.IWebRequestCreate.Create%2A> es responsable de inicializar una nueva instancia de la clase específica del protocolo. Cuando se crea una instancia de **WebRequest**, el método <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> combina el URI solicitado con los prefijos URI registrados con el método **RegisterPrefix**. El método **Create** del descendiente correcto específico del protocolo debe devolver una instancia inicializada del descendiente capaz de realizar una transacción estándar de solicitud/respuesta para el protocolo sin necesidad de modificar ningún campo específico del protocolo.  
  
## <a name="connectiongroupname-property"></a>Propiedad ConnectionGroupName  

 La propiedad <xref:System.Net.WebRequest.ConnectionGroupName%2A> se usa para asignar nombre a un grupo de conexiones a un recurso de modo que se puedan realizar varias solicitudes en una única conexión. Para implementar el uso compartido de conexiones, debe usar un método específico del protocolo de agrupación y asignación de conexiones. Por ejemplo, la clase <xref:System.Net.ServicePointManager> proporcionada implementa el uso compartido de conexiones para la clase <xref:System.Net.HttpWebRequest>. La clase **ServicePointManager** crea un elemento <xref:System.Net.ServicePoint> que proporciona una conexión a un servidor concreto para cada grupo de conexiones.  
  
## <a name="contentlength-property"></a>Propiedad ContentLength  

 La propiedad <xref:System.Net.WebRequest.ContentLength%2A> especifica el número de bytes de datos que se va a enviar al servidor al cargar datos.  
  
 Normalmente, se debe establecer la propiedad <xref:System.Net.WebRequest.Method%2A> para indicar que una carga tiene lugar cuando la propiedad **ContentLength** está establecida en un valor mayor que cero.  
  
## <a name="contenttype-property"></a>Propiedad ContentType  

 La propiedad <xref:System.Net.WebRequest.ContentType%2A> proporciona toda la información especial que el protocolo necesita que se envíe al servidor para identificar el tipo de contenido que se está enviando. Suele ser el tipo de contenido MIME de los datos cargados.  
  
## <a name="credentials-property"></a>Propiedad Credentials  

 La propiedad <xref:System.Net.WebRequest.Credentials%2A> contiene información necesaria para autenticar la solicitud en el servidor. Debe implementar los detalles del proceso de autenticación del protocolo. La clase <xref:System.Net.AuthenticationManager> es responsable de autenticar las solicitudes y de proporcionar un token de autenticación. La clase que proporciona las credenciales usadas por el protocolo debe implementar la interfaz <xref:System.Net.ICredentials>.  
  
## <a name="headers-property"></a>Propiedad Headers  

 La propiedad <xref:System.Net.WebRequest.Headers%2A> contiene una colección arbitraria de pares nombre-valor de metadatos asociados a la solicitud. Los metadatos que necesita el protocolo y que se pueden expresar como un par nombre-valor se pueden incluir en la propiedad **Headers**. Normalmente, esta información se debe establecer antes de llamar a los métodos <xref:System.Net.WebRequest.GetRequestStream%2A> o <xref:System.Net.WebRequest.GetResponse%2A>; una vez que se ha realizado la solicitud, los metadatos se consideran de solo lectura.  
  
 No es necesario usar la propiedad **Headers** para usar los metadatos de encabezado. Los metadatos específicos del protocolo pueden exponerse como propiedades; por ejemplo, la propiedad <xref:System.Net.HttpWebRequest.UserAgent%2A?displayProperty=nameWithType> expone el encabezado HTTP **Usuario-Agente**. Cuando se exponen metadatos de encabezado como una propiedad, no se debe permitir que se establezca la misma propiedad mediante la propiedad **Headers**.  
  
## <a name="method-property"></a>Propiedad Method  

 La propiedad <xref:System.Net.WebRequest.Method%2A> contiene el verbo o la acción que la solicitud pide al servidor que realice. El valor predeterminado de la propiedad **Method** debe habilitar una acción estándar de solicitud/respuesta sin necesidad de establecer ninguna propiedad específica del protocolo. Por ejemplo, el método <xref:System.Net.HttpWebResponse.Method%2A> tiene como valor predeterminado GET, que solicita un recurso de un servidor web y devuelve la respuesta.  
  
 Normalmente, si la propiedad **Method** está establecida en un verbo o acción que indica que se está realizando una carga, la propiedad **ContentLength** se debe establecer en un valor mayor que cero.  
  
## <a name="preauthenticate-property"></a>Propiedad PreAuthenticate  

 Las aplicaciones establecen la propiedad <xref:System.Net.WebRequest.PreAuthenticate%2A> para indicar que la información de autenticación se debe enviar con la solicitud inicial en lugar de esperar un desafío de autenticación. La propiedad **PreAuthenticate** solo es significativa si el protocolo admite las credenciales de autenticación enviadas con la solicitud inicial.  
  
## <a name="proxy-property"></a>Propiedad Proxy  

 La propiedad <xref:System.Net.WebRequest.Proxy%2A> contiene una interfaz <xref:System.Net.IWebProxy> que se usa para acceder al recurso solicitado. La propiedad **Proxy** solo es significativa si el protocolo admite solicitudes con proxy. Si el protocolo necesita un proxy, debe establecer el proxy predeterminado.  
  
 En algunos entornos, como detrás de un firewall corporativo, es posible que el protocolo exija usar un proxy. En ese caso, debe implementar la interfaz **IWebProxy** para crear una clase de proxy que funcione para el protocolo.  
  
## <a name="requesturi-property"></a>Propiedad RequestUri  

 La propiedad <xref:System.Net.WebRequest.RequestUri%2A> contiene el URI que se ha pasado al método **WebRequest.Create**. Es de solo lectura y no se puede cambiar una vez que se ha creado **WebRequest**. Si el protocolo admite la redirección, la respuesta puede proceder de un recurso identificado por otro URI. Si tiene que proporcionar acceso al URI que ha respondido, debe proporcionar una propiedad adicional que contenga ese URI.  
  
## <a name="timeout-property"></a>Propiedad de tiempo de espera  

 La propiedad <xref:System.Net.WebRequest.Timeout%2A> contiene el tiempo, en milisegundos, que se espera antes de que se agote el tiempo de espera de la solicitud y se produzca una excepción. **Timeout** se aplica solo a las solicitudes sincrónicas realizadas con el método <xref:System.Net.WebRequest.GetResponse%2A>; las solicitudes asincrónicas deben usar el método <xref:System.Net.WebRequest.Abort%2A> para cancelar una solicitud pendiente.  
  
 El establecimiento de la propiedad **Timeout** solo es significativo si la clase específica del protocolo implementa un proceso de tiempo de espera.  
  
## <a name="abort-method"></a>Abort (Método)  

 El método <xref:System.Net.WebRequest.Abort%2A> cancela una solicitud asincrónica pendiente a un servidor. Después de cancelar la solicitud, una llamada a **GetResponse**, **BeginGetResponse**, **EndGetResponse**, **GetRequestStream**, **BeginGetRequestStream** o **EndGetRequestStream** produce una <xref:System.Net.WebException> con la propiedad <xref:System.Net.WebException.Status%2A> establecida en <xref:System.Net.WebExceptionStatus>.  
  
## <a name="begingetrequeststream-and-endgetrequeststream-methods"></a>Métodos BeginGetRequestStream y EndGetRequestStream  

 El método <xref:System.Net.WebRequest.BeginGetRequestStream%2A> inicia una solicitud asincrónica para el flujo que se usa para cargar datos en el servidor. El método <xref:System.Net.WebRequest.EndGetRequestStream%2A> completa la solicitud asincrónica y devuelve el flujo solicitado. Estos métodos implementan el método **GetRequestStream** mediante el modelo asincrónico estándar de .NET Framework.  
  
## <a name="begingetresponse-and-endgetresponse-methods"></a>Métodos BeginGetResponse y EndGetResponse  

 El método <xref:System.Net.WebRequest.BeginGetResponse%2A> inicia una solicitud asincrónica a un servidor. El método <xref:System.Net.WebRequest.EndGetResponse%2A> completa la solicitud asincrónica y devuelve la respuesta solicitada. Estos métodos implementan el método **GetResponse** mediante el modelo asincrónico estándar de .NET Framework.  
  
## <a name="getrequeststream-method"></a>Método GetRequestStream  

 El método <xref:System.Net.WebRequest.GetRequestStream%2A> devuelve un flujo que se usa para escribir datos en el servidor solicitado. El flujo devuelto debe ser un flujo de solo escritura que no busque; está diseñado como flujo unidireccional de datos que se escriben en el servidor. El flujo devuelve false para las propiedades <xref:System.IO.Stream.CanRead%2A> y <xref:System.IO.Stream.CanSeek%2A> y true para la propiedad <xref:System.IO.Stream.CanWrite%2A>.  
  
 El método **GetRequestStream** normalmente abre una conexión al servidor y, antes de devolver el flujo, envía la información de encabezado que indica que los datos se están enviando al servidor. Dado que **GetRequestStream** inicia la solicitud, el establecimiento de cualquier propiedad **Header** o **ContentLength** normalmente no se permite después de llamar a **GetRequestStream**.  
  
## <a name="getresponse-method"></a>Método GetResponse  

 El método <xref:System.Net.WebRequest.GetResponse%2A> devuelve un descendiente específico del protocolo de la clase <xref:System.Net.WebResponse> que representa la respuesta del servidor. A menos que la solicitud ya haya sido iniciada por el método **GetRequestStream**, el método **GetResponse** crea una conexión al recurso identificado por **RequestUri**, envía información de encabezado que indica el tipo de solicitud realizada y luego recibe la respuesta del recurso.  
  
 Una vez que se ha llamado al método **GetResponse**, todas las propiedades deben considerarse de solo lectura. Las instancias de **WebRequest** están diseñadas para un solo uso; si quiere realizar otra solicitud, debe crear una nueva instancia de **WebRequest**.  
  
 El método **GetResponse** es responsable de crear un descendiente **WebResponse** adecuado para contener la respuesta entrante.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Net.WebRequest>
- <xref:System.Net.HttpWebRequest>
- <xref:System.Net.FileWebRequest>
- [Programming Pluggable Protocols (Programar protocolos acoplables)](programming-pluggable-protocols.md)
- [Derivar de WebResponse](deriving-from-webresponse.md)
