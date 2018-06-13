---
title: Servicio AJAX sin configuración
ms.date: 03/30/2017
ms.assetid: e6db7acd-5679-45d4-b98a-8449c6873838
ms.openlocfilehash: 53a0de88d08fbc12cb8861042a50da6503fa5def
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2018
ms.locfileid: "33809191"
---
# <a name="ajax-service-without-configuration"></a>Servicio AJAX sin configuración
Este ejemplo muestra cómo usar Windows Communication Foundation (WCF) para crear un servicio básico de ASP.NET Asynchronous JavaScript y XML (AJAX) (es decir, un servicio que se puede tener acceso mediante código JavaScript de un cliente del explorador Web) sin utilizar ninguna configuración Configuración. El servicio utiliza la sintaxis especial en el archivo .svc para habilitar automáticamente un punto de conexión de AJAX.  
  
 Compatibilidad con AJAX de WCF está optimizado para su uso con ASP.NET AJAX a través del `ScriptManager` control. Para obtener un ejemplo del uso de WCF con AJAX de ASP.NET, vea el [muestra Ajax](http://msdn.microsoft.com/library/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e).  
  
> [!NOTE]
>  El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
 Este ejemplo se compila en el servicio AJAX mediante HTTP POST. Como se describe en el [servicio AJAX básico](../../../../docs/framework/wcf/samples/basic-ajax-service.md) ejemplo, <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> se utiliza para hospedar el servicio.  

```svc
<%ServiceHost  
    language=c#  
    Debug="true"  
    Service="Microsoft.Ajax.Samples.CalculatorService  
    Factory="System.ServiceModel.Activation.WebScriptServiceHostFactory"  
%>  
```

 La clase <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> agrega automáticamente la clase <xref:System.ServiceModel.Description.WebScriptEndpoint> al servicio. Si no se necesita realizar ningún cambio de configuración en el extremo, la sección `<system.ServiceModel>` se puede quitar totalmente del archivo Web.config del servicio. El archivo Web.config contiene parte de la configuración de ASP.NET, que la usa el archivo ConfigFreeClientPage.aspx. Si este no es el caso, se podría quitar el archivo Web.config.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si este directorio no existe, vaya a [Windows Communication Foundation (WCF) y ejemplos de Windows Workflow Foundation (WF) para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\ConfigFreeAjaxService`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1.  Asegúrese de que lleva a cabo las instrucciones de instalación de [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Compile la solución ConfigFreeAjaxService.sln tal y como se describe en [compilar los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Vaya a http://localhost/ServiceModelSamples/ConfigFreeClientPage.aspx (no abra ConfigFreeClientPage.aspx en el explorador desde dentro del directorio del proyecto).  
  
> [!NOTE]
>  Al ejecutar este ejemplo, asegúrese de que la Autenticación anónima y la Autenticación de Windows no están habilitadas simultáneamente para la carpeta ServiceModelSamples en IIS. Si es así, deshabilite la Autenticación de Windows. Una vez ha ejecutado el ejemplo, habilite la Autenticación de Windows y ejecute "iisreset".  
  
## <a name="see-also"></a>Vea también  
 [Servicio AJAX básico](../../../../docs/framework/wcf/samples/basic-ajax-service.md)
