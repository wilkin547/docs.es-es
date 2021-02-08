---
description: 'Más información acerca de: servicio AJAX mediante HTTP POST'
title: Servicio AJAX mediante HTTP POST
ms.date: 03/30/2017
ms.assetid: 1ac80f20-ac1c-4ed1-9850-7e49569ff44e
ms.openlocfilehash: 4d319d4120310d79af5bda6026a2192d1270943b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99779106"
---
# <a name="ajax-service-using-http-post"></a>Servicio AJAX mediante HTTP POST

En este ejemplo se muestra cómo usar Windows Communication Foundation (WCF) para crear un servicio JavaScript asincrónico y XML (AJAX) ASP.NET que utiliza HTTP POST. Un servicio AJAX es un servicio al que puede tener acceso utilizando el código JavaScript básico desde un cliente del explorador web. Este ejemplo se basa en el ejemplo de [servicio Ajax básico](basic-ajax-service.md) ; la única diferencia entre los dos ejemplos es el uso de HTTP POST en lugar de HTTP GET.

La compatibilidad de AJAX en Windows Communication Foundation (WCF) se ha optimizado para su uso con ASP.NET AJAX a través del `ScriptManager` control. Para obtener un ejemplo del uso de WCF con ASP.NET AJAX, consulte los [ejemplos de Ajax](ajax-service-using-http-post.md).

> [!NOTE]
> El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.

El servicio en el ejemplo siguiente es un servicio WCF sin código específico de AJAX.

Si el <xref:System.ServiceModel.Web.WebInvokeAttribute> atributo se aplica en una operación, o <xref:System.ServiceModel.Web.WebGetAttribute> no se aplica el atributo, se utiliza el verbo http predeterminado ("post"). Las solicitudes POST son más difíciles de construir que las solicitudes GET, aunque no estén almacenadas en la memoria caché. Use las solicitudes POST para todas las operaciones en las que no sea adecuado almacenar en memoria caché.

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

A diferencia de las solicitudes GET, no se pueden invocar los servicios POST desde el explorador. Por ejemplo, al navegar a se `http://localhost/ServiceModelSamples/service.svc/Add?n1=100&n2=200` produce un error, porque el servicio post espera que `n1` `n2` se envíen los parámetros y en el cuerpo del mensaje en formato JSON y no en la dirección URL.

La página web del cliente PostAjaxClientPage.aspx contiene el código de ASP.NET para invocar el servicio siempre que el usuario haga clic en uno de los botones de operación de la página. El servicio responde de la misma manera que en el ejemplo de [servicio Ajax básico](basic-ajax-service.md) , con la solicitud GET.

> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\PostAjaxService`

## <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo

1. Asegúrese de que realiza el procedimiento de [configuración de una sola vez en las instrucciones de configuración para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).

2. Compile la solución PostAjaxService. sln tal y como se describe en [Building the Windows Communication Foundation samples](building-the-samples.md).

3. Vaya a `http://localhost/ServiceModelSamples/PostAjaxClientPage.aspx` (no abra PostAjaxClientPage. aspx en el explorador desde el directorio del proyecto).
