---
title: Cómo elegir entre solicitudes HTTP POST y HTTP GET para extremos AJAX de ASP.NET
ms.date: 03/30/2017
ms.assetid: b47de82a-4c92-4af6-bceb-a5cb8bb8ede9
ms.openlocfilehash: bebaaf7703bea1b3e491f4affbcefe3ed6ed1845
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33495043"
---
# <a name="how-to-choose-between-http-post-and-http-get-requests-for-aspnet-ajax-endpoints"></a>Cómo elegir entre solicitudes HTTP POST y HTTP GET para puntos de conexión AJAX de ASP.NET
Windows Communication Foundation (WCF) le permite crear un servicio que expone un extremo habilitado para AJAX de ASP.NET que se puede llamar desde JavaScript en un sitio Web del cliente. Los procedimientos básicos para la creación de dichos servicios se describe en [Cómo: usar la configuración para agregar un extremo de AJAX de ASP.NET](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md) y [Cómo: agregar un punto de conexión sin configuración uso de AJAX de ASP.NET](../../../../docs/framework/wcf/feature-details/how-to-add-an-aspnet-ajax-endpoint-without-using-configuration.md).  
  
 AJAX de ASP.NET admite operaciones que utilizan verbos HTTP POST y HTTP GET, donde HTTP POST es el valor predeterminado. Si crea una operación que no tiene efectos secundarios y devuelve datos que raramente o nunca cambian, utilice HTTP GET en su lugar. Los resultados de operaciones GET pueden almacenarse en memoria caché, lo que significa que varias llamadas a la misma operación solo pueden producir una solicitud a su servicio. El almacenamiento en caché no se realiza por WCF sino que tiene lugar en cualquier nivel (en un explorador de usuario, en un servidor proxy y en otros niveles.) El almacenamiento  en memoria caché es ventajoso si desea aumentar el rendimiento del servicio, pero puede que no sea aceptable si los datos cambian con frecuencia o si la operación realiza alguna acción.  
  
 Por ejemplo, si está diseñando un servicio para administrar la biblioteca de música de un usuario, una operación que busca al artista basándose en el título del álbum, se beneficia del uso de GET, pero una operación que agrega un álbum a la colección personal del usuario debe utilizar POST.  
  
 Para controlar la duración de la caché, utilice el tipo <xref:System.ServiceModel.Web.OutgoingWebResponseContext>. Por ejemplo, al diseñar un servicio que devuelve los boletines de previsión meteorológica actualizados cada hora, utilizaría GET pero limitar la duración del almacenamiento en caché a una hora o menos para evitar que los usuarios del servicio tengan acceso a datos obsoletos.  
  
 Al utilizar los servicios en una página AJAX de ASP.NET que utiliza el control del administrador de scripts, no hay diferencia si la operación usa GET o POST, el mecanismo del administrador de scripts se asegurara de que se emita el tipo de petición correcto.  
  
 Las operaciones GET y HTTP utilizan cualquier parámetro de entrada admitido por operaciones POST, incluso los datos complejos como los tipos de contrato. Sin embargo, en la mayoría de los casos se recomienda evitar demasiados parámetros o parámetros que son demasiado complejos en operaciones GET, porque se reduce la eficacia de almacenamiento en caché.  
  
 En este tema se muestra cómo elegir entre GET y POST agregando atributos <xref:System.ServiceModel.Web.WebGetAttribute> o <xref:System.ServiceModel.Web.WebInvokeAttribute> a las operaciones pertinentes en el contrato de servicios. Los otros pasos (implementar, configurar y hospedar el servicio) que son necesarios para obtener el servicio en ejecución son similares a los que se usan con el servicio de AJAX de ASP.NET en WCF.  
  
 Una operación marcada con <xref:System.ServiceModel.Web.WebGetAttribute> siempre usa una solicitud GET. Una operación marcada con <xref:System.ServiceModel.Web.WebInvokeAttribute> o no marcada con ninguno de los dos atributos, usa una solicitud POST. <xref:System.ServiceModel.Web.WebInvokeAttribute> permite el uso de otros verbos HTTP, distintos de GET y POST (como PUT y DELETE) mediante la propiedad <xref:System.ServiceModel.Web.WebInvokeAttribute.Method%2A>. AJAX de ASP.NET no admite, sin embargo, estos verbos. Si piensa utilizar el servicio desde páginas ASP.NET utilizando el control del administrador de scripts, no utilice la propiedad <xref:System.ServiceModel.Web.WebInvokeAttribute.Method%2A>.  
  
 Para obtener un ejemplo de cambiar a GET, consulte el [servicio AJAX básico](../../../../docs/framework/wcf/samples/basic-ajax-service.md) ejemplo.  
  
 Para obtener un ejemplo que utiliza POST, consulte el [servicio AJAX mediante HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md) ejemplo.  
  
### <a name="to-create-a-wcf-service-that-responds-to-http-get-or-http-post-requests"></a>Creación de un servicio WCF que responda a solicitudes HTTP GET o HTTP POST  
  
1.  Definir un contrato de servicio WCF básico con una interfaz marcada con el <xref:System.ServiceModel.ServiceContractAttribute> atributo. Marque cada operación con el <xref:System.ServiceModel.OperationContractAttribute>. Agregue el atributo <xref:System.ServiceModel.Web.WebGetAttribute> para estipular que una operación debería responder a las solicitudes HTTP GET. También puede agregar el atributo <xref:System.ServiceModel.Web.WebInvokeAttribute> para especificar explícitamente HTTP POST o no especificar un atributo, que tiene como valor predeterminado HTTP POST.  
  
    ```  
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
  
2.  Implemente el contrato de servicios `IMusicService` con un `MusicService`.  
  
    ```  
    public class MusicService : IMusicService  
    {  
        public void AddAlbum(string user, string album)  
        {  
            //Add implementation here.  
        }  
  
         //Other operations omitted…  
    }  
    ```  
  
3.  Cree un nuevo archivo denominado servicio con una extensión .svc en la aplicación. Editar este archivo agregando adecuado [ @ServiceHost ](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) información de directiva para el servicio. Especificar que la <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> es que se usará en el [ @ServiceHost ](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) directiva para configurar automáticamente un punto de conexión de AJAX de ASP.NET.  
  
    ```  
    <%@ServiceHost   
        language=c#   
        Debug="true"   
        Service="Microsoft.Ajax.Samples.MusicService"  
        Factory=System.ServiceModel.Activation.WebScriptServiceHostFactory  
    %>  
    ```  
  
### <a name="to-call-the-service"></a>Realización de llamadas al servicio  
  
1.  Puede probar las operaciones GET de su servicio sin código de cliente, utilizando el examinador. Por ejemplo, si el servicio se configura en el "http://example.com/service.svc"dirección, a continuación, escriba"http://example.com/service.svc/LookUpArtist?album=SomeAlbum" en el Explorador de barra de direcciones, se invoca el servicio y provoca la respuesta ser descargadas o muestra.  
  
2.  Puede utilizar los servicios con operaciones GET de la misma manera que cualquier otro servicio de AJAX de ASP.NET: escribiendo la URL de servicio en la colección Scripts del control del administrador de scripts de AJAX de ASP.NET. Para obtener un ejemplo, vea el [servicio AJAX básico](../../../../docs/framework/wcf/samples/basic-ajax-service.md).  
  
## <a name="see-also"></a>Vea también  
 [Creación de servicios WCF para AJAX de ASP.NET](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)  
 [Migración de servicios web de ASP.NET con AJAX habilitado a WCF](../../../../docs/framework/wcf/feature-details/how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)
