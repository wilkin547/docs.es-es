---
title: "Servicio AJAX sin configuraci&#243;n | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e6db7acd-5679-45d4-b98a-8449c6873838
caps.latest.revision: 23
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 23
---
# Servicio AJAX sin configuraci&#243;n
Este ejemplo muestra cómo utilizar [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] para crear un servicio ASP.NET básico JavaScript Asincrónico y XML \(AJAX\) \(un servicio al que puede tener acceso utilizando el código JavaScript de un cliente del explorador web\) sin utilizar ninguna configuración.  El servicio utiliza la sintaxis especial en el archivo .svc para habilitar automáticamente un extremo de AJAX.  
  
 La compatibilidad de AJAX en [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se optimiza para su uso con ASP.NET AJAX a través del control `ScriptManager`.  Para obtener un ejemplo sobre cómo usar [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] con ASP.NET AJAX, vea [Ajax Samples](http://msdn.microsoft.com/es-es/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e).  
  
> [!NOTE]
>  El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
 Este ejemplo se compila en el servicio AJAX mediante HTTP POST.  Como se describe en el ejemplo [Servicio AJAX básico](../../../../docs/framework/wcf/samples/basic-ajax-service.md), se usa la clase <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> para hospedar el servicio.  
  
```  
<%ServiceHost  
    language=c#  
    Debug="true"  
    Service="Microsoft.Ajax.Samples.CalculatorService  
    Factory="System.ServiceModel.Activation.WebScriptServiceHostFactory"  
%>  
  
```  
  
 La clase <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> agrega automáticamente la clase <xref:System.ServiceModel.Description.WebScriptEndpoint> al servicio.  Si no se necesita realizar ningún cambio de configuración en el extremo, la sección \<system.ServiceModel\> se puede quitar totalmente del archivo Web.config del servicio.  El archivo Web.config contiene parte de la configuración de ASP.NET, que la usa el archivo ConfigFreeClientPage.aspx.  Si este no es el caso, se podría quitar el archivo Web.config.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.  Compruebe el siguiente directorio \(predeterminado\) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si este directorio no existe, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].  Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\ConfigFreeAjaxService`  
  
#### Configurar, compilar y ejecutar el ejemplo  
  
1.  Asegúrese de que lleva a cabo las instrucciones de configuración de [Procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Compile la solución ConfigFreeAjaxService.sln tal y como se describe en [Compilación de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Navegue en http:\/\/localhost\/ServiceModelSamples\/ConfigFreeClientPage.aspx \(no abra ConfigFreeClientPage.aspx en el explorador desde dentro del directorio de proyecto\).  
  
> [!NOTE]
>  Al ejecutar este ejemplo, asegúrese de que la Autenticación anónima y la Autenticación de Windows no están habilitadas simultáneamente para la carpeta ServiceModelSamples en IIS.  Si es así, deshabilite la Autenticación de Windows.  Una vez ha ejecutado el ejemplo, habilite la Autenticación de Windows y ejecute "iisreset".  
  
## Vea también  
 [Servicio AJAX básico](../../../../docs/framework/wcf/samples/basic-ajax-service.md)