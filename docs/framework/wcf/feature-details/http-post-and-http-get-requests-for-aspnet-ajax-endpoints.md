---
title: Procedimiento para elegir entre solicitudes HTTP POST y HTTP GET para puntos de conexión AJAX de ASP.NET
ms.date: 03/30/2017
ms.assetid: b47de82a-4c92-4af6-bceb-a5cb8bb8ede9
ms.openlocfilehash: 15d7ad43ce9120e97aba9119aff6a6c1a19f301f
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596921"
---
# <a name="how-to-choose-between-http-post-and-http-get-requests-for-aspnet-ajax-endpoints"></a>Procedimiento para elegir entre solicitudes HTTP POST y HTTP GET para puntos de conexión AJAX de ASP.NET

Windows Communication Foundation (WCF) le permite crear un servicio que exponga un punto de conexión habilitado para AJAX de ASP.NET al que se pueda llamar desde JavaScript en un sitio web del cliente. Los procedimientos básicos para compilar estos servicios se explican en [Cómo: usar la configuración para agregar un punto de conexión de ASP.NET AJAX](how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md) y [Cómo: agregar un punto de conexión de AJAX de ASP.net sin usar la configuración](how-to-add-an-aspnet-ajax-endpoint-without-using-configuration.md).  
  
 AJAX de ASP.NET admite operaciones que utilizan verbos HTTP POST y HTTP GET, donde HTTP POST es el valor predeterminado. Si crea una operación que no tiene efectos secundarios y devuelve datos que raramente o nunca cambian, utilice HTTP GET en su lugar. Los resultados de operaciones GET pueden almacenarse en memoria caché, lo que significa que varias llamadas a la misma operación solo pueden producir una solicitud a su servicio. WCF no realiza el almacenamiento en caché, pero puede tener lugar en cualquier nivel (en el explorador de un usuario, en un servidor proxy y en otros niveles). El almacenamiento en caché es ventajoso si desea aumentar el rendimiento del servicio, pero es posible que no sea aceptable si los datos cambian con frecuencia o si la operación realiza alguna acción.  
  
 Por ejemplo, si está diseñando un servicio para administrar la biblioteca de música de un usuario, una operación que busca al artista basándose en el título del álbum, se beneficia del uso de GET, pero una operación que agrega un álbum a la colección personal del usuario debe utilizar POST.  
  
 Para controlar la duración de la caché, utilice el tipo <xref:System.ServiceModel.Web.OutgoingWebResponseContext>. Por ejemplo, al diseñar un servicio que devuelve los boletines de previsión meteorológica actualizados cada hora, utilizaría GET pero limitar la duración del almacenamiento en caché a una hora o menos para evitar que los usuarios del servicio tengan acceso a datos obsoletos.  
  
 Al utilizar los servicios en una página AJAX de ASP.NET que utiliza el control del administrador de scripts, no hay diferencia si la operación usa GET o POST, el mecanismo del administrador de scripts se asegurara de que se emita el tipo de petición correcto.  
  
 Las operaciones GET y HTTP utilizan cualquier parámetro de entrada admitido por operaciones POST, incluso los datos complejos como los tipos de contrato. Sin embargo, en la mayoría de los casos se recomienda evitar demasiados parámetros o parámetros que son demasiado complejos en operaciones GET, porque se reduce la eficacia de almacenamiento en caché.  
  
 En este tema se muestra cómo elegir entre GET y POST agregando atributos <xref:System.ServiceModel.Web.WebGetAttribute> o <xref:System.ServiceModel.Web.WebInvokeAttribute> a las operaciones pertinentes en el contrato de servicios. Los otros pasos (para implementar, configurar y hospedar el servicio) necesarios para que el servicio se ejecute sean similares a los que usa cualquier servicio de AJAX de ASP.NET en WCF.  
  
 Una operación marcada con <xref:System.ServiceModel.Web.WebGetAttribute> siempre usa una solicitud GET. Una operación marcada con <xref:System.ServiceModel.Web.WebInvokeAttribute> o no marcada con ninguno de los dos atributos, usa una solicitud POST. <xref:System.ServiceModel.Web.WebInvokeAttribute> permite el uso de otros verbos HTTP, distintos de GET y POST (como PUT y DELETE) mediante la propiedad <xref:System.ServiceModel.Web.WebInvokeAttribute.Method%2A>. AJAX de ASP.NET no admite, sin embargo, estos verbos. Si piensa utilizar el servicio desde páginas ASP.NET utilizando el control del administrador de scripts, no utilice la propiedad <xref:System.ServiceModel.Web.WebInvokeAttribute.Method%2A>.  
  
 Para obtener un ejemplo práctico de cómo cambiar a GET, vea el ejemplo de [servicio Ajax básico](../samples/basic-ajax-service.md) .  
  
 Para obtener un ejemplo que usa POST, vea el [servicio Ajax mediante el ejemplo http post](../samples/ajax-service-using-http-post.md) .  
  
## <a name="to-create-a-wcf-service-that-responds-to-http-get-or-http-post-requests"></a>Creación de un servicio WCF que responda a solicitudes HTTP GET o HTTP POST
  
1. Defina un contrato de servicio WCF básico con una interfaz marcada con el <xref:System.ServiceModel.ServiceContractAttribute> atributo. Marque cada operación con el <xref:System.ServiceModel.OperationContractAttribute>. Agregue el atributo <xref:System.ServiceModel.Web.WebGetAttribute> para estipular que una operación debería responder a las solicitudes HTTP GET. También puede agregar el atributo <xref:System.ServiceModel.Web.WebInvokeAttribute> para especificar explícitamente HTTP POST o no especificar un atributo, que tiene como valor predeterminado HTTP POST.
  
    ```csharp
    [ServiceContract]  
    public interface IMusicService  
    {  
        //This operation uses a GET method.  
        [OperationContract]  
        [WebGet]  
        string LookUpArtist(string album);  
  
        //This operation will use a POST method.  
        [OperationContract]  
        [WebInvoke]  
        void AddAlbum(string user, string album);  
  
        //This operation will use POST method by default  
        //since nothing else is explicitly specified.  
        [OperationContract]  
        string[] GetAlbums(string user);  
  
        //Other operations omitted…  
  
    }  
    ```  
  
2. Implemente el contrato de servicios `IMusicService` con un `MusicService`.
  
    ```csharp
    public class MusicService : IMusicService  
    {  
        public void AddAlbum(string user, string album)  
        {  
            //Add implementation here.  
        }  
  
         //Other operations omitted…  
    }  
    ```  
  
3. Cree un nuevo archivo denominado servicio con una extensión .svc en la aplicación. Edite este archivo agregando la información de directiva de [ \@ ServiceHost](../../configure-apps/file-schema/wcf-directive/servicehost.md) adecuada para el servicio. Especifique que <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> se va a usar en la Directiva de [ \@ ServiceHost](../../configure-apps/file-schema/wcf-directive/servicehost.md) para configurar automáticamente un punto de conexión de ASP.NET AJAX.  
  
    ```
    <%@ServiceHost
        language=c#
        Debug="true"
        Service="Microsoft.Ajax.Samples.MusicService"  
        Factory=System.ServiceModel.Activation.WebScriptServiceHostFactory  
    %>  
    ```  
  
## <a name="to-call-the-service"></a>Realización de llamadas al servicio  
  
1. Puede probar las operaciones GET de su servicio sin código de cliente, utilizando el examinador. Por ejemplo, si el servicio está configurado en la `http://example.com/service.svc` dirección, al escribir `http://example.com/service.svc/LookUpArtist?album=SomeAlbum` en la barra de direcciones del explorador se invoca el servicio y se descarga o se muestra la respuesta.
  
2. Puede utilizar los servicios con operaciones GET de la misma manera que cualquier otro servicio de AJAX de ASP.NET: escribiendo la URL de servicio en la colección Scripts del control del administrador de scripts de AJAX de ASP.NET. Para obtener un ejemplo, vea el [servicio Ajax básico](../samples/basic-ajax-service.md).
  
## <a name="see-also"></a>Vea también

- [Creación de servicios WCF para AJAX de ASP.NET](creating-wcf-services-for-aspnet-ajax.md)
- [Procedimiento para migrar servicios web de ASP.NET con AJAX habilitado a WCF](how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)
