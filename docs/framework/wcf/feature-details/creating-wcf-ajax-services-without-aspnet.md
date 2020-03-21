---
title: Creación de servicios AJAX WCF sin ASP.NET
ms.date: 03/30/2017
ms.assetid: ba4a7d1b-e277-4978-9f62-37684e6dc934
ms.openlocfilehash: f4d1d093132c501844aacbaa9cf28ecc3cede442
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185233"
---
# <a name="creating-wcf-ajax-services-without-aspnet"></a>Creación de servicios AJAX WCF sin ASP.NET
Se puede tener acceso a los servicios AJAX de Windows Communication Foundation (WCF) desde cualquier página Web habilitada para JavaScript, sin necesidad de ASP.NET AJAX. En este tema se describe cómo crear un servicio WCF de este tipo.  
  
 Para obtener instrucciones sobre el uso de WCF con ASP.NET AJAX, vea [crear servicios WCF para ASP.NET AJAX](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md).  
  
 Hay tres partes para crear un servicio WCF AJAX:  
  
- Creación de un extremo de AJAX al que se puede tener acceso desde el explorador.  
  
- Creación de un contrato de servicios compatible con AJAX.  
  
- Acceso a servicios de AJAX de WCF.  
  
## <a name="creating-an-ajax-endpoint"></a>Creación de un extremo de AJAX  
 La forma más básica de habilitar la compatibilidad <xref:System.ServiceModel.Activation.WebServiceHostFactory> con AJAX en un servicio WCF es usar el archivo .svc asociado al servicio, como en el ejemplo siguiente.  
  
```text
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
  
 Para obtener un ejemplo de trabajo, consulte el [servicio AJAX con JSON y XML.](../../../../docs/framework/wcf/samples/ajax-service-with-json-and-xml-sample.md)  
  
## <a name="creating-an-ajax-compatible-service-contract"></a>Creación de un contrato de servicios compatible con AJAX  
 De forma predeterminada, los contratos de servicios expuestos sobre un extremo de AJAX devuelven los datos en formato XML. Asimismo, de forma predeterminada, se obtiene acceso a las operaciones de servicio a través de solicitudes HTTP POST a direcciones URL que incluyen la dirección del punto de conexión seguidas por el nombre de operación, como se muestra en el siguiente ejemplo.  
  
```csharp
[OperationContract]  
string[] GetCities(string firstLetters);  
```  
  
 Esta operación es accesible `http://serviceaddress/endpointaddress/GetCities` mediante http POST y devuelve un mensaje XML.  
  
 Puede utilizar el Modelo de programación web completo para personalizar estos aspectos básicos. Por ejemplo, puede usar los atributos <xref:System.ServiceModel.Web.WebGetAttribute> o <xref:System.ServiceModel.Web.WebInvokeAttribute> para controlar el verbo HTTP al que responde la operación o usar la propiedad `UriTemplate` de los atributos respectivos para especificar URIs personalizadas. Para obtener más información, vea el tema Modelo de [programación WEB HTTP](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md) de WCF.  
  
 El formato de datos de JSON se utiliza a menudo en los servicios de AJAX. Para crear una operación que devuelva JSON en lugar de XML, establezca la propiedad <xref:System.ServiceModel.Web.WebGetAttribute.ResponseFormat%2A> (o <xref:System.ServiceModel.Web.WebInvokeAttribute.ResponseFormat%2A>) en <xref:System.ServiceModel.Web.WebMessageFormat.Json>. El tema [Serialización JSON independiente](../../../../docs/framework/wcf/feature-details/stand-alone-json-serialization.md) muestra cómo los tipos de .NET integrados y los tipos de contrato de datos se asignan a JSON.  
  
 Normalmente, las solicitudes y respuestas de JSON constan de un solo elemento. En la operación `GetCities` anterior, la solicitud se parece a la siguiente instrucción.  
  
```json
"na"  
```  
  
 La respuesta a esa solicitud se parece a la siguiente instrucción.  
  
```json
["Nairobi", "Naples", "Nashville"]  
```  
  
 Si la operación toma un parámetro adicional, el estilo de la solicitud debe ser ajustado para ajustar ambos parámetros en un objeto JSON único. A continuación se muestra un ejemplo de este mensaje JSON de estilo.  
  
```json  
{"firstLetters": "na", "maxNumber": 2}  
```  
  
 El siguiente contrato acepta este mensaje.  
  
```csharp
[WebInvoke(BodyStyle=WebMessageBodyStyle.WrappedRequest, ResponseFormat=WebMessageFormat.Json)]  
[OperationContract]  
string[] GetCities(string firstLetters, int maxNumber);  
```  
  
## <a name="accessing-ajax-services"></a>Acceso a servicios de AJAX  
 Los extremos de WCF AJAX siempre aceptan solicitudes JSON y XML.  
  
 Las solicitudes HTTP POST con un tipo de contenido de "application/json" se tratan como JSON y las que tienen un tipo de contenido que indican XML (por ejemplo, "text/xml") se tratan como XML.  
  
 Las solicitudes HTTP GET contienen todos los parámetros de solicitud en la propia dirección URL.  
  
 Depende del usuario decidir cómo crear la solicitud HTTP en el punto de conexión. Asimismo, el usuario tiene control completo sobre la construcción del JSON que forma el cuerpo de la solicitud. Para obtener un ejemplo de creación de una solicitud desde JavaScript, consulte el [servicio AJAX con JSON y XML.](../../../../docs/framework/wcf/samples/ajax-service-with-json-and-xml-sample.md)
