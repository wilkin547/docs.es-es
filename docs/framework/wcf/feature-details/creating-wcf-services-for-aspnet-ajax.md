---
title: Creación de servicios WCF para AJAX de ASP.NET
ms.date: 03/30/2017
ms.assetid: 04c0402c-e617-4ba5-aedf-d17692234776
ms.openlocfilehash: 2ec4d2f1f2fb3a6a184a524ed0134360407b4649
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964065"
---
# <a name="creating-wcf-services-for-aspnet-ajax"></a>Creación de servicios WCF para AJAX de ASP.NET

AJAX de ASP.NET de Microsoft le permite crear rápidamente páginas web para que la experiencia del usuario sea más satisfactoria gracias a elementos de la interfaz de usuario más familiares y receptivos. AJAX de ASP.NET proporciona bibliotecas de scripts de cliente que incorporan las tecnologías ECMAScript (JavaScript) y HTML dinámico (DHTML) para varios exploradores, y las integra en la plataforma de desarrollo para servidores de ASP.NET 2.0. Gracias a las características de AJAX de ASP.NET puede mejorar la experiencia del usuario y la eficacia de sus aplicaciones web.

AJAX de ASP.NET consta de bibliotecas de scripts de cliente y de componentes de servidor que se integran para proporcionar un marco de desarrollo robusto. Para tener acceso a un servicio desde una página ASP.NET: una vez que se agrega la URL de servicio al control del administrador de scripts de ASP.NET en la página, las operaciones de servicio se pueden invocar usando código JavaScript que tiene la misma apariencia que una llamada de función de JavaScript normal.

La mayoría de los servicios de Windows Communication Foundation (WCF) se pueden exponer como un servicio compatible con ASP.NET AJAX agregando un punto de conexión de ASP.NET AJAX adecuado.

Si usa Visual Studio, puede usar una plantilla pregenerada para los servicios WCF habilitados para AJAX, disponible en el cuadro de diálogo **Agregar nuevo elemento** al trabajar con sitios web o aplicaciones web de ASP.net.

Si no está utilizando las plantillas Visual Studio, hay dos maneras de crear un punto de conexión de AJAX de ASP.NET:

- Cree el extremo utilizando la activación de host dinámica sin utilizar ninguna configuración. Éste es el enfoque más básico si no se está muy familiarizado con el sistema de configuración de WCF. Para obtener más información, consulte [Cómo: agregar un punto de conexión de ASP.NET AJAX sin usar la configuración](../../../../docs/framework/wcf/feature-details/how-to-add-an-aspnet-ajax-endpoint-without-using-configuration.md).

- Agregue un punto de conexión habilitado para AJAX a un servicio WCF mediante la configuración. Para obtener más información, consulte [Cómo: usar la configuración para agregar un punto de conexión de ASP.NET AJAX](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md).

El modelo de programación web descrito en [información general del modelo de programación web http de WCF](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model-overview.md) se puede usar con los servicios de ASP.NET AJAX. De manera específica:

- Puede utilizar los atributos <xref:System.ServiceModel.Web.WebGetAttribute> y <xref:System.ServiceModel.Web.WebInvokeAttribute> para seleccionar entre los verbos HTTP GET y HTTP POST. Si se utiliza correctamente, esto podría mejorar significativamente el rendimiento de la aplicación. Para obtener más información, consulte [Cómo: elegir entre solicitudes HTTP POST y HTTP GET para puntos de conexión de ASP.NET AJAX](../../../../docs/framework/wcf/feature-details/http-post-and-http-get-requests-for-aspnet-ajax-endpoints.md).

- Puede usar las propiedades <xref:System.ServiceModel.Web.WebGetAttribute.ResponseFormat%2A> y <xref:System.ServiceModel.Web.WebInvokeAttribute.ResponseFormat%2A> para que su servicio devuelva datos XML en lugar de hacerlo en el formato Javascript Object Notation (JSON) predeterminado. Si hace esto con el marco de AJAX de ASP.NET, el cliente JavaScript va a recibir un objeto DOM XML.

  > [!WARNING]
  > La operación debe establecer el tipo de contenido en texto o xml para que funcione. De lo contrario, el cliente JavaScript recibirá una cadena que contiene el XML en vez de un objeto DOM XML.

    A continuación se muestra un ejemplo de una operación que devuelve datos XML con el tipo de contenido establecido adecuadamente:

  ```csharp
  [OperationContract, WebGet(ResponseFormat=WebMessageFormat.Xml)]
  public XElement GetData()
  {
      XElement x;
      //Get some data here...

      WebOperationContext.Current.OutgoingResponse.ContentType = "text/xml";
      return x;
  }
  ```

- No se pueden cambiar otras propiedades de los atributos de las clases <xref:System.ServiceModel.Web.WebGetAttribute> y <xref:System.ServiceModel.Web.WebInvokeAttribute> si es necesaria la compatibilidad con AJAX de ASP.NET. Se pueden utilizar otros aspectos del modelo de programación web con tal de que no se infrinjan las convenciones de llamada de AJAX de ASP.NET.

 Los escenarios más avanzados requieren algunos detalles adicionales de la compatibilidad con AJAX en WCF:

- Para entender cómo se transfieren los datos entre un cliente de página AJAX y un servicio WCF mediante JavaScript, y para obtener detalles sobre cómo se asignan los tipos de .NET Framework a los tipos de JavaScript, vea [compatibilidad con JSON y otros formatos de transferencia de datos](../../../../docs/framework/wcf/feature-details/support-for-json-and-other-data-transfer-formats.md).

- Para aprovecharse de las características de ASP.NET, como, por ejemplo, la autenticación basada en URL y obtener acceso a la información de sesión de ASP.NET, puede que desee habilitar el modo de compatibilidad de ASP.NET mediante configuración.

Los puntos de conexión de AJAX en WCF pueden usarse incluso sin el marco de AJAX de ASP.NET. Para ello, es necesario comprender la arquitectura de soporte de compatibilidad de AJAX en WCF. Para obtener una descripción de esta arquitectura, vea [modelo de objetos de programación web http de WCF](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-object-model.md). Para ver un ejemplo de código que muestra este enfoque, vea el [servicio AJAX con JSON y XML](../../../../docs/framework/wcf/samples/ajax-service-with-json-and-xml-sample.md).

## <a name="see-also"></a>Vea también

- [Modelo de programación de web HTTP de WCF](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
- [Adición de un punto de conexión AJAX de ASP.NET sin usar la configuración](../../../../docs/framework/wcf/feature-details/how-to-add-an-aspnet-ajax-endpoint-without-using-configuration.md)
- [Uso de la configuración para agregar un punto de conexión AJAX de ASP.NET](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md)
- [Elección entre solicitudes HTTP POST y HTTP GET para puntos de conexión AJAX de ASP.NET](../../../../docs/framework/wcf/feature-details/http-post-and-http-get-requests-for-aspnet-ajax-endpoints.md)
