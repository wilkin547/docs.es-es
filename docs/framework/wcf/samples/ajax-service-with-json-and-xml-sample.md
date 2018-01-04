---
title: Servicio AJAX con ejemplo JSON y XML
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8ea5860d-0c42-4ae9-941a-e07efdd8e29c
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 665e05907f837887a7dd0375e540b6e9167a820e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ajax-service-with-json-and-xml-sample"></a>Servicio AJAX con ejemplo JSON y XML
Este ejemplo muestra cómo utilizar [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] para crear un servicio JavaScript y XML asincrónico (AJAX) que devuelva o bien la notación del objeto de JavaScript (JSON) o los datos XML. Puede tener acceso a un servicio de AJAX utilizando el código JavaScript de un cliente del explorador web. En este ejemplo se basa en el [servicio AJAX básico](../../../../docs/framework/wcf/samples/basic-ajax-service.md) ejemplo.  
  
 A diferencia de la otra muestra AJAX, este ejemplo no utiliza AJAX de ASP.NET ni el control <xref:System.Web.UI.ScriptManager>. Con alguna configuración adicional, se puede tener acceso a los servicios de AJAX de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] desde cualquier página HTML a través de JavaScript y este escenario se muestra aquí. Para obtener un ejemplo del uso de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] con AJAX de ASP.NET, vea [muestra AJAX](http://msdn.microsoft.com/en-us/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e).  
  
 Este ejemplo muestra cómo intercambiar el tipo de respuesta de una operación entre JSON y XML. Esta funcionalidad está disponible sin tener en cuenta si el servicio se configura para el acceso mediante AJAX de ASP.NET o una página de cliente de HTML/JavaScript.  
  
> [!NOTE]
>  El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
 Para habilitar el uso de los clientes de AJAX de ASP.NET, use <xref:System.ServiceModel.Activation.WebServiceHostFactory> (no <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>) en el archivo .svc. <xref:System.ServiceModel.Activation.WebServiceHostFactory> agrega un extremo <xref:System.ServiceModel.Description.WebHttpEndpoint> estándar al servicio. El punto de conexión se configura en una dirección vacía relacionada con el archivo .svc; esto significa que la dirección del servicio es http://localhost/ServiceModelSamples/service.svc, sin ningún sufijo adicional, exceptuando el nombre de la operación.  
  
```html  
<%@ServiceHost language="c#" Debug="true" Service="Microsoft.Samples.XmlAjaxService.CalculatorService" Factory="System.ServiceModel.Activation.WebServiceHostFactory" %>  
```  
  
 La siguiente sección de Web.config se puede utilizar para realizar cambios de configuración adicionales en el punto de conexión. Se puede quitar si no se necesita ningún cambio adicional.  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>  
    <webHttpEndpoint>  
      <!-- Use this element to configure the endpoint -->  
      <standardEndpoint name="" />  
    </webHttpEndpoint>  
  </standardEndpoints>  
</system.serviceModel>  
```  
  
 Dar formato a los datos predeterminados para <xref:System.ServiceModel.Description.WebHttpEndpoint> es XML, mientras que el formato de datos predeterminado para <xref:System.ServiceModel.Description.WebScriptEndpoint> es JSON. Para obtener más información, consulte [crear servicios de AJAX WCF sin ASP.NET](../../../../docs/framework/wcf/feature-details/creating-wcf-ajax-services-without-aspnet.md).  
  
 El servicio en el ejemplo siguiente es un servicio estándar [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] con dos operaciones. Ambas operaciones requieren el estilo de cuerpo <xref:System.ServiceModel.Web.WebMessageBodyStyle.Wrapped> en <xref:System.ServiceModel.Web.WebGetAttribute> o los atributos <xref:System.ServiceModel.Web.WebInvokeAttribute>, que es concreto al comportamiento `webHttp` y no están afectados por el cambio de formato de JSON/XML.  
  
```  
[OperationContract]  
[WebInvoke(ResponseFormat = WebMessageFormat.Xml, BodyStyle = WebMessageBodyStyle.Wrapped)]  
MathResult DoMathXml(double n1, double n2);  
```  
  
 El formato de respuesta para la operación se especifica como XML, que es el valor predeterminado para la [ \<webHttp >](../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md) comportamiento. No obstante, es conveniente especificar de forma explícita al formato de respuesta.  
  
 La otra operación utiliza el atributo `WebInvokeAttribute` y explícitamente especifica JSON en lugar de XML para la respuesta.  
  
```  
[OperationContract]  
[WebInvoke(ResponseFormat = WebMessageFormat.Json, BodyStyle = WebMessageBodyStyle.Wrapped)]  
MathResult DoMathJson(double n1, double n2);  
```  
  
 Tenga en cuenta que en ambos casos las operaciones devuelven un tipo complejo, `MathResult`, que es un tipo de contrato de datos [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] estándar.  
  
 La página Web cliente XmlAjaxClientPage.htm contiene código JavaScript que invoca una de las dos operaciones anteriores, cuando el usuario hace clic en el **realizar cálculo (devuelve JSON)** o **realizar cálculo (devuelve XML)**  botones en la página. El código para invocar el servicio construye un cuerpo de JSON y lo envía utilizando HTTP POST, de manera similar al ejemplo. La solicitud se crea manualmente en JavaScript, a diferencia de la [servicio AJAX básico](../../../../docs/framework/wcf/samples/basic-ajax-service.md) ejemplo y los otros ejemplos con AJAX de ASP.NET.  
  
```  
// Create HTTP request  
var xmlHttp;  
// Request instantiation code omitted…  
// Result handler code omitted…  
  
// Build the operation URL  
var url = "service.svc/ajaxEndpoint/";  
url = url + operation;  
  
// Build the body of the JSON message  
var body = '{"n1":';  
body = body + document.getElementById("num1").value + ',"n2":';  
body = body + document.getElementById("num2").value + '}';  
  
// Send the HTTP request  
xmlHttp.open("POST", url, true);  
xmlHttp.setRequestHeader("Content-type", "application/json");  
xmlHttp.send(body);  
```  
  
 Cuando el servicio responde, la respuesta se muestra sin más procesamientos en un cuadro de texto en la página. Esto se implementa a efectos de demostración para permitir que poder observar directamente los formatos de datos de JSON y XML utilizados.  
  
```  
// Create result handler   
xmlHttp.onreadystatechange=function(){  
     if(xmlHttp.readyState == 4){  
          document.getElementById("result").value = xmlHttp.responseText;  
     }  
}  
```  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\AJAX\XmlAjaxService`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1.  Asegúrese de que ha llevado a cabo la [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Compile la solución XmlAjaxService.sln tal y como se describe en [compilar los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Desplácese por http://localhost/ServiceModelSamples/ XmlAjaxClientPage.aspx (no abra XmlAjaxClientPage.aspx en el explorador del directorio de proyecto).  
  
## <a name="see-also"></a>Vea también  
 [Servicio AJAX mediante HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md)
