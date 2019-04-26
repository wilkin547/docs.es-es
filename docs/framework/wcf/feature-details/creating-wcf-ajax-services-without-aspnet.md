---
title: Creación de servicios AJAX WCF sin ASP.NET
ms.date: 03/30/2017
ms.assetid: ba4a7d1b-e277-4978-9f62-37684e6dc934
ms.openlocfilehash: 77a850408c3d952dbd4f682ea704d3248ae17c3e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61857212"
---
# <a name="creating-wcf-ajax-services-without-aspnet"></a>Creación de servicios AJAX WCF sin ASP.NET
Servicios de AJAX de Windows Communication Foundation (WCF) se pueden acceder desde cualquier página Web con JavaScript habilitado, sin necesidad de AJAX de ASP.NET. Este tema describe cómo crear este tipo de servicio WCF.  
  
 Para obtener instrucciones sobre el uso de WCF con AJAX de ASP.NET, consulte [crear servicios WCF para AJAX de ASP.NET](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md).  
  
 Hay tres partes para crear un servicio AJAX de WCF:  
  
-   Creación de un extremo de AJAX al que se puede tener acceso desde el explorador.  
  
-   Creación de un contrato de servicios compatible con AJAX.  
  
-   Acceso a servicios de AJAX de WCF.  
  
## <a name="creating-an-ajax-endpoint"></a>Creación de un extremo de AJAX  
 La manera más sencilla de habilitar la compatibilidad con AJAX en un servicio WCF es usar el <xref:System.ServiceModel.Activation.WebServiceHostFactory> en el archivo .svc asociado con el servicio, como se muestra en el ejemplo siguiente.  
  
```  
<%ServiceHost   
    language=c#  
    Debug="true"  
    Service="Microsoft.Ajax.Samples.CityService"  
    Factory=System.ServiceModel.Activation.WebServiceHostFactory  
%>  
```  
  
 Por otra parte, también puede utilizar la configuración para agregar un punto de conexión de AJAX. Utilice el <xref:System.ServiceModel.WebHttpBinding> en el punto de conexión de servicio y configure ese punto de conexión con <xref:System.ServiceModel.Description.WebHttpBehavior>, tal y como se muestra en el siguiente fragmento de código.  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="AjaxBehavior">  
          <webHttp/>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    <services>  
      <service name="Microsoft.Ajax.Samples.CityService">  
        <endpoint   
          address="ajaxEndpoint"  
          behaviorConfiguration="AjaxBehavior"  
          binding="webHttpBinding"  
          contract="Microsoft.Ajax.Samples.ICityService" />  
      </service>  
    </services>  
  </system.serviceModel>  
</configuration>  
```  
  
 Para obtener un ejemplo ilustrativo, consulte el [servicio AJAX con JSON y XML](../../../../docs/framework/wcf/samples/ajax-service-with-json-and-xml-sample.md).  
  
## <a name="creating-an-ajax-compatible-service-contract"></a>Creación de un contrato de servicios compatible con AJAX  
 De forma predeterminada, los contratos de servicios expuestos sobre un extremo de AJAX devuelven los datos en formato XML. Asimismo, de forma predeterminada, se obtiene acceso a las operaciones de servicio a través de solicitudes HTTP POST a direcciones URL que incluyen la dirección del punto de conexión seguidas por el nombre de operación, como se muestra en el siguiente ejemplo.  
  
```  
[OperationContract]  
string[] GetCities(string firstLetters);  
```  
  
 Esta operación es accesible mediante una solicitud HTTP POST a `http://serviceaddress/endpointaddress/GetCities` y devolver un mensaje XML.  
  
 Puede utilizar el Modelo de programación web completo para personalizar estos aspectos básicos. Por ejemplo, puede usar los atributos <xref:System.ServiceModel.Web.WebGetAttribute> o <xref:System.ServiceModel.Web.WebInvokeAttribute> para controlar el verbo HTTP al que responde la operación o usar la propiedad `UriTemplate` de los atributos respectivos para especificar URIs personalizadas. Para obtener más información, consulte el [modelo de programación de WCF Web HTTP](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md) tema.  
  
 El formato de datos de JSON se utiliza a menudo en los servicios de AJAX. Para crear una operación que devuelva JSON en lugar de XML, establezca la propiedad <xref:System.ServiceModel.Web.WebGetAttribute.ResponseFormat%2A> (o <xref:System.ServiceModel.Web.WebInvokeAttribute.ResponseFormat%2A>) en <xref:System.ServiceModel.Web.WebMessageFormat.Json>. El [de serialización JSON independiente](../../../../docs/framework/wcf/feature-details/stand-alone-json-serialization.md) tema muestra cómo integradas .NET datos y tipos de contrato los tipos se asignan a JSON.  
  
 Normalmente, las solicitudes y respuestas de JSON constan de un solo elemento. En la operación `GetCities` anterior, la solicitud se parece a la siguiente instrucción.  
  
```  
"na"  
```  
  
 La respuesta a esa solicitud se parece a la siguiente instrucción.  
  
```  
["Nairobi", "Naples", "Nashville"]  
```  
  
 Si la operación toma un parámetro adicional, el estilo de la solicitud debe ser ajustado para ajustar ambos parámetros en un objeto JSON único. A continuación se muestra un ejemplo de este mensaje JSON de estilo.  
  
```json  
{"firstLetters": "na", "maxNumber": 2}  
```  
  
 El siguiente contrato acepta este mensaje.  
  
```  
[WebInvoke(BodyStyle=WebMessageBodyStyle.WrappedRequest, ResponseFormat=WebMessageFormat.Json)]  
[OperationContract]  
string[] GetCities(string firstLetters, int maxNumber);  
```  
  
## <a name="accessing-ajax-services"></a>Acceso a servicios de AJAX  
 Puntos de conexión AJAX de WCF siempre aceptan solicitudes JSON y XML.  
  
 Las solicitudes HTTP POST con un tipo de contenido de "application/json" se tratan como JSON y aquellas cuyo tipo de contenido que indique XML (por ejemplo, "texto/xml") se tratan como XML.  
  
 Las solicitudes HTTP GET contienen todos los parámetros de solicitud en la propia dirección URL.  
  
 Depende del usuario decidir cómo crear la solicitud HTTP en el punto de conexión. Asimismo, el usuario tiene control completo sobre la construcción del JSON que forma el cuerpo de la solicitud. Para obtener un ejemplo de creación de una solicitud desde JavaScript, consulte el [servicio AJAX con JSON y XML](../../../../docs/framework/wcf/samples/ajax-service-with-json-and-xml-sample.md).
