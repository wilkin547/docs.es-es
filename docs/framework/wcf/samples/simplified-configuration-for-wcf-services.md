---
title: Configuración simplificada de los servicios de WCF
description: Aprenda a implementar y configurar un servicio y un cliente típicos con WCF. El servicio se comunica con un punto de conexión especificado en un archivo de configuración.
ms.date: 03/30/2017
ms.assetid: 1e39ec25-18a3-4fdc-b6a3-9dfafbd60112
ms.openlocfilehash: dd05754dcfe36cb2e9c28ce20a5927585f85478f
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554272"
---
# <a name="simplified-configuration-for-wcf-services"></a>Configuración simplificada de los servicios de WCF
Este ejemplo muestra cómo implementar y configurar un servicio y un cliente típicos con Windows Communication Foundation (WCF). Este ejemplo es la base para obtener todos los otros ejemplos tecnológicos básicos.  
  
 Este servicio, que expone un punto de conexión para comunicarse con el servicio, utiliza la configuración simplificada en .NET Framework 4. Antes de .NET Framework 4, el punto de conexión se define normalmente en un archivo de configuración (Web.config), como se muestra en el siguiente código de configuración de ejemplo.  
  
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
  
 En .NET Framework 4, el `<service>` elemento es opcional. Cuando un servicio no define ningún punto de conexión, se agregan al servicio un punto de conexión para cada dirección base y el contrato implementado. La dirección base se anexa al nombre del contrato para determinar el punto de conexión y el esquema de direcciones determina el enlace. El siguiente ejemplo de código muestra un archivo de configuración simplificado. Tal y como se ha configurado, un cliente puede tener acceso al servicio `http://localhost/servicemodelsamples/service.svc` en el mismo equipo. Para que los clientes en equipos remotos tengan acceso al servicio, se debe especificar un nombre de dominio completo en lugar del host local. El servicio no expone ningún metadato de forma predeterminada. Como tal, el servicio activa el comportamiento <xref:System.ServiceModel.Description.ServiceMetadataBehavior>.  
  
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
  
1. Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Para compilar la solución, siga las instrucciones de [creación de los ejemplos de Windows Communication Foundation](building-the-samples.md).  
  
3. Ejecute el ejemplo siguiendo estos pasos:  
  
    1. Haga clic con el botón derecho en el proyecto de **servicio** y seleccione **establecer como proyecto de inicio**y presione **Ctrl + F5**.  
  
    2. Espere a que el resultado de la consola confirme que el servicio está activo y en ejecución.  
  
    3. Haga clic con el botón derecho en el proyecto de **cliente** y seleccione **establecer como proyecto de inicio**y presione **Ctrl + F5**.  
  
> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ConfigSimplificationIn40`  
  
## <a name="see-also"></a>Vea también

- [Ejemplos de administración de AppFabric](/previous-versions/appfabric/ff383405(v=azure.10))
- [Configuración simplificada](../simplified-configuration.md)
