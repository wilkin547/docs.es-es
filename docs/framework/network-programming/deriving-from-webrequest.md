---
title: "Derivar de WebRequest | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "WebRequest (clase), protocolos acoplables"
  - "controlador de solicitudes específicas de protocolos"
  - "enviar datos, protocolos acoplables"
  - "protocolos acoplables, criterios de clase"
  - "Internet, protocolos acoplables"
  - "recibir datos, protocolos acoplables"
  - "protocolos, acoplables"
ms.assetid: 9810c177-973e-43d7-823c-14960bd625ea
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 7
---
# Derivar de WebRequest
La clase de <xref:System.Net.WebRequest> es una clase base abstracta que proporciona los métodos y propiedades básicos para crear un controlador protocolo\- específico de la solicitud que ajusta el modelo conectable de protocolo de .NET Framework.  Las aplicaciones que utilizan la clase de **WebRequest** pueden solicitar datos utilizando cualquier protocolo compatible sin necesidad de especificar el protocolo utilizado.  
  
 Dos criterios se deben cumplir para que una clase protocolo\- concreta se utiliza como protocolo conectable: la clase debe implementar la interfaz de <xref:System.Net.IWebRequestCreate> , y debe registrar con el método de <xref:System.Net.WebRequest.RegisterPrefix%2A?displayProperty=fullName> .  La clase debe reemplazar todos los métodos y propiedades abstractos de **WebRequest** para proporcionar la interfaz conectable.  
  
 Las instancias de **WebRequest** están pensados para el único uso; si desea realizar otra solicitud, cree un nuevo **WebRequest**.  **WebRequest** admite la interfaz de <xref:System.Runtime.Serialization.ISerializable> que permite a los desarrolladores para serializar una plantilla **WebRequest** y después volver a crear la plantilla para las solicitudes adicionales.  
  
## Método Create de IWebRequest  
 El método de <xref:System.Net.IWebRequestCreate.Create%2A> es responsable de inicializar una nueva instancia de la clase protocolo\- concreta.  Cuando se crea un nuevo **WebRequest** , las coincidencias del método de <xref:System.Net.WebRequest.Create%2A?displayProperty=fullName> que el URI solicitado con los prefijos URI registrado con el método de **RegisterPrefix** .  El método de **Crear** descendientes protocolo\- concreto adecuado debe devolver una instancia inicializada descendientes capaz de realizar una transacción estándar de solicitud y respuesta para el protocolo sin necesidad de ningún campos protocolo\- específicos modificados.  
  
## Propiedad de ConnectionGroupName  
 La propiedad de <xref:System.Net.WebRequest.ConnectionGroupName%2A> se utiliza para llamar a un grupo de conexiones a un recurso para poder hacer solicitudes varias sobre una única conexión.  Para implementar la conexión compartida, debe utilizar un método protocolo\- específico de agrupación y conexiones de la asignación.  Por ejemplo, la clase proporcionada de <xref:System.Net.ServicePointManager> implementa la conexión compartida para la clase de <xref:System.Net.HttpWebRequest> .  La clase de **ServicePointManager** crea <xref:System.Net.ServicePoint> que proporciona una conexión a un servidor específico para cada grupo de conexión.  
  
## Propiedad de ContentLength  
 La propiedad de <xref:System.Net.WebRequest.ContentLength%2A> especifica el número de bytes de los datos que se enviará al servidor al cargar datos.  
  
 La propiedad de <xref:System.Net.WebRequest.Method%2A> establecido normalmente para indicar que está teniendo lugar una carga cuando la propiedad de **ContentLength** se establece en un valor mayor que cero.  
  
## Propiedad ContentType  
 La propiedad de <xref:System.Net.WebRequest.ContentType%2A> proporciona la información especial que el protocolo necesita enviar al servidor para identificar el tipo de contenido que está enviando.  Normalmente es el tipo de contenido de MIME de los datos cargado.  
  
## Propiedad credentials  
 La propiedad de <xref:System.Net.WebRequest.Credentials%2A> contiene la información necesaria para autenticar la solicitud al servidor.  Debe implementar los detalles del proceso de autenticación para el protocolo.  La clase de <xref:System.Net.AuthenticationManager> es responsable de autenticar solicitudes y proporcionar un token de autenticación.  La clase que proporciona las credenciales utilizadas por el protocolo debe implementar la interfaz de <xref:System.Net.ICredentials> .  
  
## Propiedad headers  
 La propiedad de <xref:System.Net.WebRequest.Headers%2A> contiene una colección arbitraria de pares de nombre\/valor de metadatos asociados a la solicitud.  Los metadatos requerido por el protocolo que se puede expresar como un par de nombre\/valor puede estar incluida en la propiedad de **Headers** .  Esta información debe establecerse normalmente antes de llamar a los métodos de <xref:System.Net.WebRequest.GetRequestStream%2A> o de <xref:System.Net.WebRequest.GetResponse%2A> ; la solicitud se ha realizado una vez, los metadatos se considera de solo lectura.  
  
 No es necesario usar la propiedad de **Headers** para utilizar los metadatos del encabezado.  Los metadatos Protocolo\-específicos se pueden exponer como propiedades; por ejemplo, la propiedad de <xref:System.Net.HttpWebRequest.UserAgent%2A?displayProperty=fullName> expone el encabezado HTTP de **User\-Agent** .  Cuando expone metadatos de encabezado como una propiedad, no debe permitir que la misma propiedad se establezca mediante la propiedad de **Headers** .  
  
## Propiedad de método  
 La propiedad de <xref:System.Net.WebRequest.Method%2A> contiene el verbo o action que la solicitud está solicitando al servidor efectuara.  El valor predeterminado de la propiedad de **Method** debe habilitar una acción estándar de solicitud y respuesta sin requerir ninguna propiedad protocolo\- específicas establecer.  Por ejemplo, los valores predeterminados del método de [HttpWebResponse](frlrfSystemNetHttpWebResponseClassMethodTopic) A GET, que solicita un recurso de un servidor web y devuelve la respuesta.  
  
 La propiedad de **ContentLength** establecido normalmente en un valor mayor que cero cuando la propiedad de **Method** se establece en un verbo o a una acción que indica que está teniendo lugar una carga.  
  
## Propiedad de PreAuthenticate  
 Las aplicaciones establecen la propiedad de <xref:System.Net.WebRequest.PreAuthenticate%2A> para indicar que la información de autenticación debe enviarse con la solicitud inicial en lugar de espera un desafío de autenticación.  La propiedad de **PreAuthenticate** solo es significativa si el protocolo admite las credenciales de autenticación enviadas con la solicitud inicial.  
  
## Propiedad proxy  
 La propiedad de <xref:System.Net.WebRequest.Proxy%2A> contiene una interfaz de <xref:System.Net.IWebProxy> que se utiliza para obtener acceso al recurso solicitado.  La propiedad de **Proxy** solo es significativa si los soportes de protocolo proxied solicitudes.  Debe establecer el proxy predeterminado si uno es requerido por el protocolo.  
  
 En algunos entornos, por ejemplo detrás de un firewall corporativo, el protocolo se podría requerir utilizar un proxy.  En ese caso, debe implementar la interfaz de **IWebProxy** para crear una clase de proxy que sea adecuada para el protocolo.  
  
## Propiedad de RequestUri  
 La propiedad de <xref:System.Net.WebRequest.RequestUri%2A> contiene el URI que se pasó al método de **WebRequest.Create** .  Es de solo lectura y no se puede cambiar una vez creado **WebRequest** .  Si el protocolo admite la redirección, la respuesta puede proceder de un recurso identificado por otro URI.  Si necesita proporcionar acceso al identificador URI que respondió, debe proporcionar una propiedad adicional que contiene ese URI.  
  
## Propiedad de tiempo de espera  
 La propiedad de <xref:System.Net.WebRequest.Timeout%2A> contiene el tiempo, en milisegundos, de esperar antes de los tiempos de espera y los tiros de solicitud una excepción.  **Timeout** sólo se aplica a las solicitudes sincrónicas realizadas con el método de <xref:System.Net.WebRequest.GetResponse%2A> ; las solicitudes asincrónicas deben utilizar el método de <xref:System.Net.WebRequest.Abort%2A> para cancelar una solicitud pendiente.  
  
 Establecer la propiedad de **Timeout** es significativo únicamente si la clase protocolo\- concreta implementa un proceso de tiempo de espera.  
  
## Método abort  
 El método de <xref:System.Net.WebRequest.Abort%2A> cancela una solicitud asincrónica pendiente en un servidor.  Después de que la solicitud ha cancelado, llamando a **GetResponse**, **BeginGetResponse**, **EndGetResponse**, **GetRequestStream**, **BeginGetRequestStream**, o **EndGetRequestStream** producirán <xref:System.Net.WebException> con la propiedad de <xref:System.Net.WebException.Status%2A> establecida en [RequestCanceled](frlrfSystemNetWebExceptionStatusClassTopic).  
  
## Métodos de BeginGetRequestStream y de EndGetRequestStream  
 El método de <xref:System.Net.WebRequest.BeginGetRequestStream%2A> inicia una solicitud asincrónica para la secuencia que se utiliza para cargar datos en el servidor.  El método de <xref:System.Net.WebRequest.EndGetRequestStream%2A> completa la solicitud asincrónica y devuelve la secuencia solicitada.  Estos métodos implementan el método de **GetRequestStream** mediante el modelo asincrónico de .NET Framework estándar de.  
  
## Métodos de BeginGetResponse y de EndGetResponse  
 El método de <xref:System.Net.WebRequest.BeginGetResponse%2A> inicia una solicitud asincrónica a un servidor.  El método de <xref:System.Net.WebRequest.EndGetResponse%2A> completa la solicitud asincrónica y devuelve la respuesta solicitada.  Estos métodos implementan el método de **GetResponse** mediante el modelo asincrónico de .NET Framework estándar de.  
  
## Método de GetRequestStream  
 El método de <xref:System.Net.WebRequest.GetRequestStream%2A> devuelve una secuencia que se utiliza para escribir datos en el servidor solicitado.  La secuencia devuelta debe ser un solo escritura transmitir que no busca; está pensado como una secuencia de datos unidireccional que se escribe en el servidor.  La secuencia devuelve false para las propiedades de <xref:System.IO.Stream.CanRead%2A> y de <xref:System.IO.Stream.CanSeek%2A> y lo true para la propiedad de <xref:System.IO.Stream.CanWrite%2A> .  
  
 El método de **GetRequestStream** abra normalmente una conexión al servidor y, antes de devolver la secuencia, envía la información de encabezado que indica que los datos se están enviando al servidor.  Dado que inicia **GetRequestStream** la solicitud, establecer ninguna propiedad de **Encabezado** o la propiedad de **ContentLength** no se permite normalmente después de llamar a **GetRequestStream**.  
  
## Método de GetResponse  
 El método de <xref:System.Net.WebRequest.GetResponse%2A> devuelve un descendiente protocolo\- específico de la clase de <xref:System.Net.WebResponse> que representa la respuesta del servidor.  A menos que la solicitud se haya iniciada ya por el método de **GetRequestStream** , el método de **GetResponse** crea una conexión al recurso identificado por **RequestUri**, envía la información de encabezado que indica el tipo de solicitud que se crea, y después recibe la respuesta del recurso.  
  
 Una vez que se llama al método de **GetResponse** , todas las propiedades se deben considerar de sólo lectura.  Las instancias de **WebRequest** están pensados para el único uso; si desea realizar otra solicitud, debe crear un nuevo **WebRequest**.  
  
 El método de **GetResponse** es responsable de crear un descendiente adecuado de **WebResponse** para contener la respuesta de entrada.  
  
## Vea también  
 <xref:System.Net.WebRequest>   
 <xref:System.Net.HttpWebRequest>   
 <xref:System.Net.FileWebRequest>   
 [Programar protocolos acoplables](../../../docs/framework/network-programming/programming-pluggable-protocols.md)   
 [Derivar de WebResponse](../../../docs/framework/network-programming/deriving-from-webresponse.md)