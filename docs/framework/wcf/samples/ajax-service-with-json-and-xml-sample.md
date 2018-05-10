---
title: Servicio AJAX con ejemplo JSON y XML
ms.date: 03/30/2017
ms.assetid: 8ea5860d-0c42-4ae9-941a-e07efdd8e29c
ms.openlocfilehash: 32964c287b0064daf529aa4c1e28f0927d29a6d5
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2018
---
# <a name="ajax-service-with-json-and-xml-sample"></a>Servicio AJAX con ejemplo JSON y XML
Este ejemplo muestra cómo usar Windows Communication Foundation (WCF) para crear un servicio JavaScript asincrónico y XML (AJAX) que devuelva datos JavaScript Object Notation (JSON) o XML. Puede tener acceso a un servicio de AJAX utilizando el código JavaScript de un cliente del explorador web. En este ejemplo se basa en el [servicio AJAX básico](../../../../docs/framework/wcf/samples/basic-ajax-service.md) ejemplo.  
  
 A diferencia de la otra muestra AJAX, este ejemplo no utiliza AJAX de ASP.NET ni el control <xref:System.Web.UI.ScriptManager>. Con cierta configuración adicional, se pueden tener acceso a servicios de AJAX de WCF desde cualquier página HTML a través de JavaScript y este escenario se muestra aquí. Para obtener un ejemplo del uso de WCF con AJAX de ASP.NET, vea [muestra AJAX](http://msdn.microsoft.com/library/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e).  
  
 Este ejemplo muestra cómo intercambiar el tipo de respuesta de una operación entre JSON y XML. Esta funcionalidad está disponible sin tener en cuenta si el servicio se configura para el acceso mediante AJAX de ASP.NET o una página de cliente de HTML/JavaScript.  
  
> [!NOTE]
>  El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
 Para habilitar el uso de los clientes de AJAX de ASP.NET, use <xref:System.ServiceModel.Activation.WebServiceHostFactory> (no <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>) en el archivo .svc. <xref:System.ServiceModel.Activation.WebServiceHostFactory> agrega un extremo <xref:System.ServiceModel.Description.WebHttpEndpoint> estándar al servicio. El extremo se configura en una dirección vacía relativa al archivo .svc; Esto significa que la dirección del servicio es http://localhost/ServiceModelSamples/service.svc, sin ningún sufijo adicional que no sea el nombre de la operación.  
  
```svc
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
  
 El servicio en el ejemplo siguiente es un servicio WCF estándar con dos operaciones. Ambas operaciones requieren el estilo de cuerpo <xref:System.ServiceModel.Web.WebMessageBodyStyle.Wrapped> en <xref:System.ServiceModel.Web.WebGetAttribute> o los atributos <xref:System.ServiceModel.Web.WebInvokeAttribute>, que es concreto al comportamiento `webHttp` y no están afectados por el cambio de formato de JSON/XML.  

```csharp
[OperationContract]  
[WebInvoke(ResponseFormat = WebMessageFormat.Xml, BodyStyle = WebMessageBodyStyle.Wrapped)]  
MathResult DoMathXml(double n1, double n2);  
```

 El formato de respuesta para la operación se especifica como XML, que es el valor predeterminado para la [ \<webHttp >](../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md) comportamiento. No obstante, es conveniente especificar de forma explícita al formato de respuesta.  
  
 La otra operación utiliza el atributo `WebInvokeAttribute` y explícitamente especifica JSON en lugar de XML para la respuesta.  

```csharp
[OperationContract]  
[WebInvoke(ResponseFormat = WebMessageFormat.Json, BodyStyle = WebMessageBodyStyle.Wrapped)]  
MathResult DoMathJson(double n1, double n2);  
```

 Tenga en cuenta que en ambos casos las operaciones devuelven un tipo complejo, `MathResult`, que es un tipo de contrato de datos WCF estándar.  
  
 La página Web cliente XmlAjaxClientPage.htm contiene código JavaScript que invoca una de las dos operaciones anteriores, cuando el usuario hace clic en el **realizar cálculo (devuelve JSON)** o **realizar cálculo (devuelve XML)**  botones en la página. El código para invocar el servicio construye un cuerpo de JSON y lo envía utilizando HTTP POST, de manera similar al ejemplo. La solicitud se crea manualmente en JavaScript, a diferencia de la [servicio AJAX básico](../../../../docs/framework/wcf/samples/basic-ajax-service.md) ejemplo y los otros ejemplos con AJAX de ASP.NET.  

```csharp
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

```javascript
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
>  Si este directorio no existe, vaya a [Windows Communication Foundation (WCF) y ejemplos de Windows Workflow Foundation (WF) para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\AJAX\XmlAjaxService`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1.  Asegúrese de que ha llevado a cabo la [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Compile la solución XmlAjaxService.sln tal y como se describe en [compilar los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Vaya a http://localhost/ServiceModelSamples/XmlAjaxClientPage.htm (no abra Xmlajaxclientpage.aspx en el explorador desde el directorio del proyecto).  
  
## <a name="see-also"></a>Vea también  
 [Servicio AJAX mediante HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md)
