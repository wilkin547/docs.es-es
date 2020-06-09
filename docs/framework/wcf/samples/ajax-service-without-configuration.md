---
title: Servicio AJAX sin configuración
ms.date: 03/30/2017
ms.assetid: e6db7acd-5679-45d4-b98a-8449c6873838
ms.openlocfilehash: ab3731ab6aeb80e0e46228b8bf702b0fe5c6e6e9
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84575906"
---
# <a name="ajax-service-without-configuration"></a>Servicio AJAX sin configuración

En este ejemplo se muestra cómo usar Windows Communication Foundation (WCF) para crear un servicio JavaScript y XML (AJAX) ASP.NET asincrónico básico (un servicio al que se puede tener acceso mediante código JavaScript desde un cliente del explorador Web) sin utilizar ninguna configuración. El servicio utiliza la sintaxis especial en el archivo .svc para habilitar automáticamente un punto de conexión de AJAX.

La compatibilidad de AJAX en WCF está optimizada para su uso con ASP.NET AJAX a través del `ScriptManager` control. Para obtener un ejemplo del uso de WCF con ASP.NET AJAX, consulte los [ejemplos de Ajax](ajax.md).

> [!NOTE]
> El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.

 Este ejemplo se compila en el servicio AJAX mediante HTTP POST. Tal y como se describe en el ejemplo de [servicio Ajax básico](basic-ajax-service.md) , <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> se usa para hospedar el servicio.

```text
<%ServiceHost
    language=c#
    Debug="true"
    Service="Microsoft.Ajax.Samples.CalculatorService
    Factory="System.ServiceModel.Activation.WebScriptServiceHostFactory"
%>
```

La clase <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> agrega automáticamente la clase <xref:System.ServiceModel.Description.WebScriptEndpoint> al servicio. Si no se necesita realizar ningún cambio de configuración en el extremo, la sección `<system.ServiceModel>` se puede quitar totalmente del archivo Web.config del servicio. El archivo Web.config contiene parte de la configuración de ASP.NET, que la usa el archivo ConfigFreeClientPage.aspx. Si este no es el caso, se podría quitar el archivo Web.config.

> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\ConfigFreeAjaxService`

#### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo

1. Asegúrese de que realiza las instrucciones de configuración en [un procedimiento de instalación único para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).

2. Compile la solución ConfigFreeAjaxService. sln tal y como se describe en [Building the Windows Communication Foundation samples](building-the-samples.md).

3. Vaya a `http://localhost/ServiceModelSamples/ConfigFreeClientPage.aspx` (no abra ConfigFreeClientPage. aspx en el explorador desde el directorio del proyecto).

> [!NOTE]
> Al ejecutar este ejemplo, asegúrese de que la Autenticación anónima y la Autenticación de Windows no están habilitadas simultáneamente para la carpeta ServiceModelSamples en IIS. Si es así, deshabilite la Autenticación de Windows. Una vez ha ejecutado el ejemplo, habilite la Autenticación de Windows y ejecute "iisreset".

## <a name="see-also"></a>Vea también

- [Servicio AJAX básico](basic-ajax-service.md)
