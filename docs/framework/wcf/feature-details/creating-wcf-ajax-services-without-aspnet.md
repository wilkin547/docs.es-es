---
title: Creación de servicios AJAX WCF sin ASP.NET
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ba4a7d1b-e277-4978-9f62-37684e6dc934
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b652bcd522a8eea81b3d1218fbd054ee0b2caea8
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="creating-wcf-ajax-services-without-aspnet"></a>Creación de servicios AJAX WCF sin ASP.NET
Se puede tener acceso a los servicios AJAX de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] desde cualquier página web con JavaScript habilitado, sin necesidad de AJAX de ASP.NET. En este tema se describe cómo crear un servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 Para obtener instrucciones sobre el uso de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] con AJAX de ASP.NET, vea [crear servicios de WCF para AJAX de ASP.NET](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md).  
  
 Para crear un servicio AJAX  de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] existen tres partes:  
  
-   Creación de un extremo de AJAX al que se puede tener acceso desde el explorador.  
  
-   Creación de un contrato de servicios compatible con AJAX.  
  
-   Acceso a servicios de AJAX de WCF.  
  
## <a name="creating-an-ajax-endpoint"></a>Creación de un extremo de AJAX  
 La manera más simple de habilitar la compatibilidad de AJAX en un servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] consiste en utilizar <xref:System.ServiceModel.Activation.WebServiceHostFactory> en el archivo .svc asociado al servicio, como en el ejemplo siguiente.  
  
```  
<%ServiceHost   
    language=c#  
    Debug="true"  
    Service="Microsoft.Ajax.Samples.CityService"  
    Factory=System.ServiceModel.Activation.WebServiceHostFactory  
%>  
```  
  
 Por otra parte, también puede utilizar la configuración para agregar un extremo de AJAX. Utilice el <xref:System.ServiceModel.WebHttpBinding> en el extremo de servicio y configure ese extremo con <xref:System.ServiceModel.Description.WebHttpBehavior>, tal y como se muestra en el siguiente fragmento de código.  
  
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
  
 Para obtener un ejemplo, vea el [servicio AJAX con JSON y XML](../../../../docs/framework/wcf/samples/ajax-service-with-json-and-xml-sample.md).  
  
## <a name="creating-an-ajax-compatible-service-contract"></a>Creación de un contrato de servicios compatible con AJAX  
 De forma predeterminada, los contratos de servicios expuestos sobre un extremo de AJAX devuelven los datos en formato XML. Asimismo, de forma predeterminada, se obtiene acceso a las operaciones de servicio a través de solicitudes HTTP POST a direcciones URL que incluyen la dirección del punto de conexión seguidas por el nombre de operación, como se muestra en el siguiente ejemplo.  
  
```  
[OperationContract]  
string[] GetCities(string firstLetters);  
```  
  
 Esta operación es accesible mediante una solicitud HTTP POST a `http://serviceaddress/endpointaddress/GetCities` y devolver un mensaje XML.  
  
 Puede utilizar el Modelo de programación web completo para personalizar estos aspectos básicos. Por ejemplo, puede usar los atributos <xref:System.ServiceModel.Web.WebGetAttribute> o <xref:System.ServiceModel.Web.WebInvokeAttribute> para controlar el verbo HTTP al que responde la operación o usar la propiedad `UriTemplate` de los atributos respectivos para especificar URIs personalizadas. Para obtener más información, consulte el [modelo de programación de Web HTTP de WCF](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md) tema.  
  
 El formato de datos de JSON se utiliza a menudo en los servicios de AJAX. Para crear una operación que devuelva JSON en lugar de XML, establezca la propiedad <xref:System.ServiceModel.Web.WebGetAttribute.ResponseFormat%2A> (o <xref:System.ServiceModel.Web.WebInvokeAttribute.ResponseFormat%2A>) en <xref:System.ServiceModel.Web.WebMessageFormat.Json>. El [de serialización JSON independiente](../../../../docs/framework/wcf/feature-details/stand-alone-json-serialization.md) tema muestra cómo integradas .NET datos y tipos de contrato tipos asignación a JSON.  
  
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
 Los extremos de AJAX de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] siempre aceptan solicitudes JSON y XML.  
  
 Las solicitudes HTTP POST con un tipo de contenido de "application/json" se tratan como JSON y aquellas cuyo tipo de contenido que indique XML (por ejemplo, "text/xml") se tratan como XML.  
  
 Las solicitudes HTTP GET contienen todos los parámetros de solicitud en la propia dirección URL.  
  
 Depende del usuario decidir cómo crear la solicitud HTTP en el extremo. Asimismo, el usuario tiene control completo sobre la construcción del JSON que forma el cuerpo de la solicitud. Para obtener un ejemplo de creación de una solicitud de JavaScript, consulte el [servicio AJAX con JSON y XML](../../../../docs/framework/wcf/samples/ajax-service-with-json-and-xml-sample.md).
