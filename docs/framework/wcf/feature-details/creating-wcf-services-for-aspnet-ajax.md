---
title: "Creación de servicios WCF para AJAX de ASP.NET"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 04c0402c-e617-4ba5-aedf-d17692234776
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c2e3ba1d360c55f10cde9447b3961d84ffe1cdb2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="creating-wcf-services-for-aspnet-ajax"></a>Creación de servicios WCF para AJAX de ASP.NET
AJAX de ASP.NET de Microsoft le permite crear rápidamente páginas web para que la experiencia del usuario sea más satisfactoria gracias a elementos de la interfaz de usuario más familiares y receptivos. AJAX de ASP.NET proporciona bibliotecas de scripts de cliente que incorporan las tecnologías ECMAScript (JavaScript) y HTML dinámico (DHTML) para varios exploradores, y las integra en la plataforma de desarrollo para servidores de ASP.NET 2.0. Gracias a las características de AJAX de ASP.NET puede mejorar la experiencia del usuario y la eficacia de sus aplicaciones web.  
  
 AJAX de ASP.NET consta de bibliotecas de scripts de cliente y de componentes de servidor que se integran para proporcionar un marco de desarrollo robusto. Para tener acceso a un servicio desde una página ASP.NET: una vez que se agrega la URL de servicio al control del administrador de scripts de ASP.NET en la página, las operaciones de servicio se pueden invocar usando código JavaScript que tiene la misma apariencia que una llamada de función de JavaScript normal. Vea [Obtenga información acerca de ASP.NET AJAX](http://go.microsoft.com/fwlink/?LinkId=186475) sobre el uso de servicios Web en el marco de AJAX.  
  
 La mayoría de los servicios de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] se pueden exponer como servicio compatible con AJAX de ASP.NET agregando un extremo de AJAX de ASP.NET adecuado.  
  
 Si se utiliza Visual Studio, puede usar una plantilla precompilada para servicios WCF con AJAX habilitado, disponibles en la **Agregar nuevo elemento** cuadro de diálogo cuando se trabaja con sitios Web de ASP.NET o aplicaciones Web.  
  
 Si no está utilizando las plantillas Visual Studio, hay dos maneras de crear un punto de conexión de AJAX de ASP.NET:  
  
-   Cree el punto de conexión utilizando la activación de host dinámica sin utilizar ninguna configuración. Éste es el enfoque más básico si no se está muy familiarizado con el sistema de configuración de WCF. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Cómo: agregar un extremo de AJAX de ASP.NET sin usar la configuración](../../../../docs/framework/wcf/feature-details/how-to-add-an-aspnet-ajax-endpoint-without-using-configuration.md).  
  
-   Agregue un extremo compatible con AJAX a un servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] mediante configuración. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Cómo: usar la configuración para agregar un extremo de AJAX de ASP.NET](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md).  
  
 El modelo de programación Web descrito en el [HTTP Web WCF Programming Model Overview](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model-overview.md) pueden utilizarse con servicios de AJAX de ASP.NET. De manera específica:  
  
-   Puede utilizar los atributos <xref:System.ServiceModel.Web.WebGetAttribute> y <xref:System.ServiceModel.Web.WebInvokeAttribute> para seleccionar entre los verbos HTTP GET y HTTP POST. Si se utiliza correctamente, esto podría mejorar significativamente el rendimiento de la aplicación. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Cómo: elegir entre HTTP POST y HTTP GET solicitudes para los extremos de AJAX de ASP.NET](../../../../docs/framework/wcf/feature-details/http-post-and-http-get-requests-for-aspnet-ajax-endpoints.md).  
  
-   Puede usar las propiedades <xref:System.ServiceModel.Web.WebGetAttribute.ResponseFormat%2A> y <xref:System.ServiceModel.Web.WebInvokeAttribute.ResponseFormat%2A> para que su servicio devuelva datos XML en lugar de hacerlo en el formato Javascript Object Notation (JSON) predeterminado. Si hace esto con el marco de AJAX de ASP.NET, el cliente JavaScript va a recibir un objeto DOM XML.  
  
    > [!WARNING]
    >  La operación debe establecer el tipo de contenido en texto o xml para que funcione. De lo contrario, el cliente JavaScript recibirá una cadena que contiene el XML en vez de un objeto DOM XML.  
  
     A continuación se muestra un ejemplo de una operación que devuelve datos XML con el tipo de contenido establecido adecuadamente:  
  
    ```  
    [OperationContract, WebGet(ResponseFormat=WebMessageFormat.Xml)]  
    public XElement GetData()  
    {  
    XElement x;  
    //Get some data here...  
  
    WebOperationContext.Current.OutgoingResponse.ContentType = "text/xml";      
    return x;  
    }  
    ```  
  
-   No se pueden cambiar otras propiedades de los atributos de las clases <xref:System.ServiceModel.Web.WebGetAttribute> y <xref:System.ServiceModel.Web.WebInvokeAttribute> si es necesaria la compatibilidad con AJAX de ASP.NET. Se pueden utilizar otros aspectos del modelo de programación web con tal de que no se infrinjan las convenciones de llamada de AJAX de ASP.NET.  
  
 Los escenarios más avanzados requieren que se comprendan algunos detalles adicionales de compatibilidad de AJAX en [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:  
  
-   Para comprender cómo se transfieren los datos entre un cliente de la página de AJAX y un [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] servicio con JavaScript y para obtener información detallada sobre cómo se asignan los tipos de .NET Framework en tipos de JavaScript, consulte [compatibilidad con JSON y otros formatos de transferencia de datos](../../../../docs/framework/wcf/feature-details/support-for-json-and-other-data-transfer-formats.md) .  
  
-   Para aprovecharse de las características de ASP.NET, como, por ejemplo, la autenticación basada en URL y obtener acceso a la información de sesión de ASP.NET, puede que desee habilitar el modo de compatibilidad de ASP.NET mediante configuración.  
  
 Los extremos de AJAX en [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] incluso se pueden utilizar sin el marco de AJAX de ASP.NET. Para hacer esto es necesario comprender la arquitectura de compatibilidad de AJAX en [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Para obtener una descripción de esta arquitectura, consulte [modelo de objetos de programación de WCF Web HTTP](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-object-model.md). Para obtener un ejemplo de código que muestra este enfoque, consulte el [servicio AJAX con JSON y XML](../../../../docs/framework/wcf/samples/ajax-service-with-json-and-xml-sample.md).  
  
## <a name="see-also"></a>Vea también  
 [Modelo de programación de web HTTP de WCF](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)  
 [Adición de un punto de conexión AJAX de ASP.NET sin usar la configuración](../../../../docs/framework/wcf/feature-details/how-to-add-an-aspnet-ajax-endpoint-without-using-configuration.md)  
 [Uso de la configuración para agregar un punto de conexión AJAX de ASP.NET](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md)  
 [Elección entre solicitudes HTTP POST y HTTP GET para puntos de conexión AJAX de ASP.NET](../../../../docs/framework/wcf/feature-details/http-post-and-http-get-requests-for-aspnet-ajax-endpoints.md)
