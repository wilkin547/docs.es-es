---
title: "Creaci&#243;n de servicios AJAX WCF sin ASP.NET | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ba4a7d1b-e277-4978-9f62-37684e6dc934
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Creaci&#243;n de servicios AJAX WCF sin ASP.NET
Se puede tener acceso a los servicios AJAX de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] desde cualquier página web con JavaScript habilitado, sin necesidad de AJAX de ASP.NET.  En este tema se describe cómo crear un servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 Para obtener instrucciones sobre cómo usar [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] con AJAX de ASP.NET, consulte [Creación de servicios WCF para AJAX de ASP.NET](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md).  
  
 Para crear un servicio AJAX  de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] existen tres partes:  
  
-   Creación de un extremo de AJAX al que se puede tener acceso desde el explorador.  
  
-   Creación de un contrato de servicios compatible con AJAX.  
  
-   Acceso a servicios de AJAX de WCF.  
  
## Creación de un extremo de AJAX  
 La manera más simple de habilitar la compatibilidad de AJAX en un servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] consiste en utilizar <xref:System.ServiceModel.Activation.WebServiceHostFactory> en el archivo .svc asociado al servicio, como en el ejemplo siguiente.  
  
```  
<%ServiceHost   
    language=c#  
    Debug="true"  
    Service="Microsoft.Ajax.Samples.CityService"  
    Factory=System.ServiceModel.Activation.WebServiceHostFactory  
%>  
```  
  
 Por otra parte, también puede utilizar la configuración para agregar un extremo de AJAX.  Utilice el <xref:System.ServiceModel.WebHttpBinding> en el extremo de servicio y configure ese extremo con <xref:System.ServiceModel.Description.WebHttpBehavior>, tal y como se muestra en el siguiente fragmento de código.  
  
```  
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
  
 Para ver un ejemplo ilustrativo, consulte [Servicio AJAX con JSON y XML](../../../../docs/framework/wcf/samples/ajax-service-with-json-and-xml-sample.md).  
  
## Creación de un contrato de servicios compatible con AJAX  
 De forma predeterminada, los contratos de servicios expuestos sobre un extremo de AJAX devuelven los datos en formato XML.  Asimismo, de forma predeterminada, se obtiene acceso a las operaciones de servicio a través de solicitudes HTTP POST a direcciones URL que incluyen la dirección del extremo seguidas por el nombre de operación, como se muestra en el siguiente ejemplo.  
  
```  
[OperationContract]  
string[] GetCities(string firstLetters);  
```  
  
 Se puede obtener acceso a esta operación mediante una solicitud HTTP POST a `http://serviceaddress/endpointaddress/GetCities` y devolver un mensaje XML.  
  
 Puede utilizar el Modelo de programación web completo para personalizar estos aspectos básicos.  Por ejemplo, puede usar los atributos <xref:System.ServiceModel.Web.WebGetAttribute> o <xref:System.ServiceModel.Web.WebInvokeAttribute> para controlar el verbo HTTP al que responde la operación o usar la propiedad `UriTemplate` de los atributos respectivos para especificar URIs personalizadas.  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] el tema [Modelo de programación de web HTTP de WCF](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md).  
  
 El formato de datos de JSON se utiliza a menudo en los servicios de AJAX.  Para crear una operación que devuelva JSON en lugar de XML, establezca la propiedad <xref:System.ServiceModel.Web.WebGetAttribute.ResponseFormat%2A> \(o <xref:System.ServiceModel.Web.WebInvokeAttribute.ResponseFormat%2A>\) en <xref:System.ServiceModel.Web.WebMessageFormat>.  El tema [Serialización independiente de JSON](../../../../docs/framework/wcf/feature-details/stand-alone-json-serialization.md) muestra cómo los tipos de .NET integrados y los tipos de contrato de datos se asignan a JSON.  
  
 Normalmente, las solicitudes y respuestas de JSON constan de un solo elemento.  En la operación `GetCities` anterior, la solicitud se parece a la siguiente instrucción.  
  
```  
“na”  
```  
  
 La respuesta a esa solicitud se parece a la siguiente instrucción.  
  
```  
[“Nairobi”, “Naples”, “Nashville”]  
```  
  
 Si la operación toma un parámetro adicional, el estilo de la solicitud debe ser ajustado para ajustar ambos parámetros en un objeto JSON único.  A continuación se muestra un ejemplo de este mensaje JSON de estilo.  
  
```  
{“firstLetters”: “na”, “maxNumber”: 2}  
```  
  
 El siguiente contrato acepta este mensaje.  
  
```  
[WebInvoke(BodyStyle=WebMessageBodyStyle.WrappedRequest, ResponseFormat=WebMessageFormat.Json)]  
[OperationContract]  
string[] GetCities(string firstLetters, int maxNumber);  
```  
  
## Acceso a servicios de AJAX  
 Los extremos de AJAX de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] siempre aceptan solicitudes JSON y XML.  
  
 Las solicitudes HTTP POST con un tipo de contenido de "application\/json" se tratan como JSON y aquellas con tipo de contenido que indique XML \(por ejemplo, "text\/xml"\) se tratan como XML.  
  
 Las solicitudes HTTP GET contienen todos los parámetros de solicitud en la propia dirección URL.  
  
 Depende del usuario decidir cómo crear la solicitud HTTP en el extremo.  Asimismo, el usuario tiene control completo sobre la construcción del JSON que forma el cuerpo de la solicitud.  Para obtener un ejemplo de creación de una solicitud a partir de JavaScript, consulte [Servicio AJAX con JSON y XML](../../../../docs/framework/wcf/samples/ajax-service-with-json-and-xml-sample.md).