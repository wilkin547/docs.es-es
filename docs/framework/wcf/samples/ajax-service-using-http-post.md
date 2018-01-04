---
title: Servicio AJAX mediante HTTP POST
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1ac80f20-ac1c-4ed1-9850-7e49569ff44e
caps.latest.revision: "28"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c2447f641748cdcc3419fda2a6ae8f02d68ed98e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ajax-service-using-http-post"></a>Servicio AJAX mediante HTTP POST
Este ejemplo muestra cómo utilizar [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] para crear un servicio JavaScript asincrónico [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] y XML (AJAX) que utiliza HTTP POST. Un servicio AJAX es un servicio al que puede tener acceso utilizando el código JavaScript básico desde un cliente del explorador web. En este ejemplo se basa en el [servicio AJAX básico](../../../../docs/framework/wcf/samples/basic-ajax-service.md) ejemplo; la única diferencia entre las dos muestras es el uso de HTTP POST en lugar de HTTP GET.  
  
 La compatibilidad de AJAX en [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] se optimiza para su uso con ASP.NET AJAX a través del control `ScriptManager`. Para obtener un ejemplo del uso de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] con AJAX de ASP.NET, vea el [muestra Ajax](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).  
  
> [!NOTE]
>  El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
 El servicio en el ejemplo siguiente es un servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sin el código específico de AJAX.  
  
 Si el <xref:System.ServiceModel.Web.WebInvokeAttribute> se aplica el atributo en una operación, o la <xref:System.ServiceModel.Web.WebGetAttribute> no se aplica el atributo, se utiliza el verbo HTTP predeterminado ("POST"). Las solicitudes POST son más difíciles de construir que las solicitudes GET, aunque no estén almacenadas en la memoria caché. Use las solicitudes POST para todas las operaciones en las que no sea adecuado almacenar en memoria caché.  
  
```  
[ServiceContract(Namespace = "PostAjaxService")]  
    public interface ICalculator  
    {        [WebInvoke]  
        double Add(double n1, double n2);  
        //Other operations omitted…  
    }  
```  
  
 Cree un extremo AJAX en el servicio mediante el uso de la clase <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, exactamente igual que en el ejemplo de servicio AJAX básico.  
  
 A diferencia de las solicitudes GET, no se pueden invocar los servicios POST desde el explorador. Por ejemplo, navegar a http://localhost/ServiceModelSamples/service.svc/Add?n1=100&n2=200 da como resultado un error, porque el servicio POST espera que se envíen los parámetros `n1` y `n2` en el cuerpo del mensaje (en el formato JSON) y no en la dirección URL.  
  
 La página web del cliente PostAjaxClientPage.aspx contiene el código de ASP.NET para invocar el servicio siempre que el usuario haga clic en uno de los botones de operación de la página. El servicio responde de la misma manera que en el [servicio AJAX básico](../../../../docs/framework/wcf/samples/basic-ajax-service.md) ejemplo, con la solicitud GET.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\PostAjaxService`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1.  Asegúrese de que lleva a cabo las instrucciones de configuración [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Compile la solución PostAjaxService.sln tal y como se describe en [compilar los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Navegue hasta http://localhost/ServiceModelSamples/PostAjaxClientPage.aspx (no abra PostAjaxClientPage.aspx en el explorador del directorio de proyecto).  
  
## <a name="see-also"></a>Vea también
