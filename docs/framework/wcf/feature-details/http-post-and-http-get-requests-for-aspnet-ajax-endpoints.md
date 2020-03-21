---
title: Cómo elegir entre solicitudes HTTP POST y HTTP GET para puntos de conexión AJAX de ASP.NET
ms.date: 03/30/2017
ms.assetid: b47de82a-4c92-4af6-bceb-a5cb8bb8ede9
ms.openlocfilehash: 0f7a221d1fd14b4a978683f008858e35cbd2df19
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184757"
---
# <a name="how-to-choose-between-http-post-and-http-get-requests-for-aspnet-ajax-endpoints"></a>Cómo elegir entre solicitudes HTTP POST y HTTP GET para puntos de conexión AJAX de ASP.NET

Windows Communication Foundation (WCF) permite crear un servicio que expone un extremo habilitado para ASP.NET AJAX que se puede llamar desde JavaScript en un sitio Web cliente. Los procedimientos básicos para crear estos servicios se describen en [Cómo: Usar la configuración para agregar un ASP.NET punto](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md) de conexión de AJAX y Cómo: agregar un ASP.NET punto de conexión de AJAX [sin usar la configuración](../../../../docs/framework/wcf/feature-details/how-to-add-an-aspnet-ajax-endpoint-without-using-configuration.md).  
  
 AJAX de ASP.NET admite operaciones que utilizan verbos HTTP POST y HTTP GET, donde HTTP POST es el valor predeterminado. Si crea una operación que no tiene efectos secundarios y devuelve datos que raramente o nunca cambian, utilice HTTP GET en su lugar. Los resultados de operaciones GET pueden almacenarse en memoria caché, lo que significa que varias llamadas a la misma operación solo pueden producir una solicitud a su servicio. WCF no realiza el almacenamiento en caché, pero puede tener lugar en cualquier nivel (en el explorador de un usuario, en un servidor proxy y otros niveles.) El almacenamiento en caché es ventajoso si desea aumentar el rendimiento del servicio, pero puede no ser aceptable si los datos cambian con frecuencia o si la operación realiza alguna acción.  
  
 Por ejemplo, si está diseñando un servicio para administrar la biblioteca de música de un usuario, una operación que busca al artista basándose en el título del álbum, se beneficia del uso de GET, pero una operación que agrega un álbum a la colección personal del usuario debe utilizar POST.  
  
 Para controlar la duración de la caché, utilice el tipo <xref:System.ServiceModel.Web.OutgoingWebResponseContext>. Por ejemplo, al diseñar un servicio que devuelve los boletines de previsión meteorológica actualizados cada hora, utilizaría GET pero limitar la duración del almacenamiento en caché a una hora o menos para evitar que los usuarios del servicio tengan acceso a datos obsoletos.  
  
 Al utilizar los servicios en una página AJAX de ASP.NET que utiliza el control del administrador de scripts, no hay diferencia si la operación usa GET o POST, el mecanismo del administrador de scripts se asegurara de que se emita el tipo de petición correcto.  
  
 Las operaciones GET y HTTP utilizan cualquier parámetro de entrada admitido por operaciones POST, incluso los datos complejos como los tipos de contrato. Sin embargo, en la mayoría de los casos se recomienda evitar demasiados parámetros o parámetros que son demasiado complejos en operaciones GET, porque se reduce la eficacia de almacenamiento en caché.  
  
 En este tema se muestra cómo elegir entre GET y POST agregando atributos <xref:System.ServiceModel.Web.WebGetAttribute> o <xref:System.ServiceModel.Web.WebInvokeAttribute> a las operaciones pertinentes en el contrato de servicios. Los otros pasos (para implementar, configurar y hospedar el servicio) que son necesarios para ejecutar el servicio son similares a los utilizados por cualquier servicio ASP.NET AJAX en WCF.  
  
 Una operación marcada con <xref:System.ServiceModel.Web.WebGetAttribute> siempre usa una solicitud GET. Una operación marcada con <xref:System.ServiceModel.Web.WebInvokeAttribute> o no marcada con ninguno de los dos atributos, usa una solicitud POST. <xref:System.ServiceModel.Web.WebInvokeAttribute> permite el uso de otros verbos HTTP, distintos de GET y POST (como PUT y DELETE) mediante la propiedad <xref:System.ServiceModel.Web.WebInvokeAttribute.Method%2A>. AJAX de ASP.NET no admite, sin embargo, estos verbos. Si piensa utilizar el servicio desde páginas ASP.NET utilizando el control del administrador de scripts, no utilice la propiedad <xref:System.ServiceModel.Web.WebInvokeAttribute.Method%2A>.  
  
 Para obtener un ejemplo de trabajo de cambio a GET, vea el ejemplo [de servicio AJAX básico.](../../../../docs/framework/wcf/samples/basic-ajax-service.md)  
  
 Para obtener un ejemplo que usa POST, vea el [ejemplo AJAX Service Using HTTP POST.](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md)  
  
## <a name="to-create-a-wcf-service-that-responds-to-http-get-or-http-post-requests"></a>Creación de un servicio WCF que responda a solicitudes HTTP GET o HTTP POST
  
1. Defina un contrato de servicio WCF <xref:System.ServiceModel.ServiceContractAttribute> básico con una interfaz marcada con el atributo. Marque cada operación con el <xref:System.ServiceModel.OperationContractAttribute>. Agregue el atributo <xref:System.ServiceModel.Web.WebGetAttribute> para estipular que una operación debería responder a las solicitudes HTTP GET. También puede agregar el atributo <xref:System.ServiceModel.Web.WebInvokeAttribute> para especificar explícitamente HTTP POST o no especificar un atributo, que tiene como valor predeterminado HTTP POST.
  
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
  
3. Cree un nuevo archivo denominado servicio con una extensión .svc en la aplicación. Edite este archivo agregando la información de directiva [ \@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) adecuada para el servicio. Especifique que <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> se va a usar en la [ \@](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) directiva ServiceHost para configurar automáticamente un ASP.NET extremo AJAX.  
  
    ```
    <%@ServiceHost
        language=c#
        Debug="true"
        Service="Microsoft.Ajax.Samples.MusicService"  
        Factory=System.ServiceModel.Activation.WebScriptServiceHostFactory  
    %>  
    ```  
  
## <a name="to-call-the-service"></a>Realización de llamadas al servicio  
  
1. Puede probar las operaciones GET de su servicio sin código de cliente, utilizando el examinador. Por ejemplo, si el servicio `http://example.com/service.svc` está configurado `http://example.com/service.svc/LookUpArtist?album=SomeAlbum` en la dirección, al escribir en la barra de direcciones del explorador se invoca el servicio y se muestra la respuesta.
  
2. Puede utilizar los servicios con operaciones GET de la misma manera que cualquier otro servicio de AJAX de ASP.NET: escribiendo la URL de servicio en la colección Scripts del control del administrador de scripts de AJAX de ASP.NET. Para obtener un ejemplo, vea el [servicio AJAX básico](../../../../docs/framework/wcf/samples/basic-ajax-service.md).
  
## <a name="see-also"></a>Consulte también

- [Creación de servicios WCF para AJAX de ASP.NET](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)
- [Cómo migrar servicios web de ASP.NET con AJAX habilitado a WCF](../../../../docs/framework/wcf/feature-details/how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)
