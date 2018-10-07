---
title: Configuración simplificada de los servicios de WCF
ms.date: 03/30/2017
ms.assetid: 1e39ec25-18a3-4fdc-b6a3-9dfafbd60112
ms.openlocfilehash: 333469cecdf2acae72e6d1add8f96829a127dcf8
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2018
ms.locfileid: "48836727"
---
# <a name="simplified-configuration-for-wcf-services"></a>Configuración simplificada de los servicios de WCF
Este ejemplo muestra cómo implementar y configurar un servicio típico y el cliente con Windows Communication Foundation (WCF). Este ejemplo es la base para obtener todos los otros ejemplos tecnológicos básicos.  
  
 Este servicio, que expone un extremo para comunicar con el servicio, utiliza la configuración simplificada en [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)]. Antes de [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)], el extremo se solía definir en un archivo de configuración (Web.config), como se muestra en el siguiente código de configuración de ejemplo.  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<!-- Copyright ©) Microsoft Corporation.  All Rights Reserved. -->  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="CalculatorServiceBehavior">  
          <serviceMetadata httpGetEnabled="True"/>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <services>  
      <service name="Microsoft.Samples.GettingStarted.CalculatorService"  
               behaviorConfiguration="CalculatorServiceBehavior">  
        <endpoint address="" binding="basicHttpBinding" contract="ICalculator"/>  
        <endpoint address="mex" binding="mexHttpBinding" contract="IMetadataExchange"/>  
      </service>  
    </services>  
  </system.serviceModel>  
</configuration>  
```  
  
 En [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)], el elemento `<service>` es opcional. Cuando un servicio no define ningún punto de conexión, se agregan al servicio un punto de conexión para cada dirección base y el contrato implementado. La dirección base se anexa al nombre del contrato para determinar el extremo y el esquema de direcciones determina el enlace. El siguiente ejemplo de código muestra un archivo de configuración simplificado. Como se ha configurado, puede tener acceso al servicio en `http://localhost/servicemodelsamples/service.svc` por un cliente en el mismo equipo. Para que los clientes en equipos remotos tengan acceso al servicio, se debe especificar un nombre de dominio completo en lugar del host local. El servicio no expone ningún metadato de forma predeterminada. Como tal, el servicio activa el comportamiento <xref:System.ServiceModel.Description.ServiceMetadataBehavior>.  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<!-- Copyright © Microsoft Corporation.  All Rights Reserved. -->  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="">  
          <serviceMetadata httpGetEnabled="True"/>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
### <a name="to-use-this-sample"></a>Para utilizar este ejemplo  
  
1.  Asegúrese de que ha realizado la [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Para compilar la solución, siga las instrucciones de [compilar los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Ejecute el ejemplo siguiendo estos pasos:  
  
    1.  Haga clic en el **servicio** del proyecto y seleccione **establecer como proyecto de inicio**, a continuación, presione **CTRL+F5**.  
  
    2.  Espere a que el resultado de la consola confirme que el servicio está activo y en ejecución.  
  
    3.  Haga clic en el **cliente** del proyecto y seleccione **establecer como proyecto de inicio**, a continuación, presione **CTRL+F5**.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ConfigSimplificationIn40`  
  
## <a name="see-also"></a>Vea también  
 [Ejemplos de administración de AppFabric](https://go.microsoft.com/fwlink/?LinkId=193960)  
 [Configuración simplificada](../../../../docs/framework/wcf/simplified-configuration.md)
