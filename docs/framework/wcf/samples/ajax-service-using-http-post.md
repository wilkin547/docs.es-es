---
title: Servicio AJAX mediante HTTP POST
ms.date: 03/30/2017
ms.assetid: 1ac80f20-ac1c-4ed1-9850-7e49569ff44e
ms.openlocfilehash: 2fb98e38956719608517caa0e7eeaebd14df8d95
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2019
ms.locfileid: "65882148"
---
# <a name="ajax-service-using-http-post"></a>Servicio AJAX mediante HTTP POST
Este ejemplo muestra cómo usar Windows Communication Foundation (WCF) para crear un servicio ASP.NET JavaScript asincrónico y XML (AJAX) que utiliza HTTP POST. Un servicio AJAX es un servicio al que puede tener acceso utilizando el código JavaScript básico desde un cliente del explorador web. En este ejemplo se basa en el [servicio AJAX básico](../../../../docs/framework/wcf/samples/basic-ajax-service.md) ejemplo; la única diferencia entre los dos ejemplos es el uso de HTTP POST en lugar de HTTP GET.  
  
 Compatibilidad con AJAX en Windows Communication Foundation (WCF) está optimizado para su uso con AJAX de ASP.NET a través de la `ScriptManager` control. Para obtener un ejemplo del uso de WCF con AJAX de ASP.NET, vea el [muestras de Ajax](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).  
  
> [!NOTE]
>  El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
 El servicio en el ejemplo siguiente es un servicio WCF con ningún código específico de AJAX.  
  
 Si el <xref:System.ServiceModel.Web.WebInvokeAttribute> se aplica el atributo en una operación, o el <xref:System.ServiceModel.Web.WebGetAttribute> no se aplica el atributo, se utiliza el verbo HTTP predeterminado ("POST"). Las solicitudes POST son más difíciles de construir que las solicitudes GET, aunque no estén almacenadas en la memoria caché. Use las solicitudes POST para todas las operaciones en las que no sea adecuado almacenar en memoria caché.  

```csharp
[ServiceContract(Namespace = "PostAjaxService")]  
public interface ICalculator  
{
    [WebInvoke]  
    double Add(double n1, double n2);  
    //Other operations omitted…  
}
```

 Cree un extremo AJAX en el servicio mediante el uso de la clase <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, exactamente igual que en el ejemplo de servicio AJAX básico.  
  
 A diferencia de las solicitudes GET, no se pueden invocar los servicios POST desde el explorador. Por ejemplo, navegar a `http://localhost/ServiceModelSamples/service.svc/Add?n1=100&n2=200` da como resultado un error, porque el servicio POST espera el `n1` y `n2` parámetros que se enviarán en el cuerpo del mensaje en el formato JSON y no en la dirección URL.  
  
 La página web del cliente PostAjaxClientPage.aspx contiene el código de ASP.NET para invocar el servicio siempre que el usuario haga clic en uno de los botones de operación de la página. El servicio responde de la misma manera que en el [servicio AJAX básico](../../../../docs/framework/wcf/samples/basic-ajax-service.md) ejemplo, con la solicitud GET.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\PostAjaxService`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1. Asegúrese de realizar las instrucciones de configuración [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Compile la solución postajaxservice.sln tal y como se describe en [compilar los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Vaya a `http://localhost/ServiceModelSamples/PostAjaxClientPage.aspx` (no abra PostAjaxClientPage.aspx en el explorador desde el directorio del proyecto).
