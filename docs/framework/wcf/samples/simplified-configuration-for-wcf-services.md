---
title: Configuración simplificada de los servicios de WCF
ms.date: 03/30/2017
ms.assetid: 1e39ec25-18a3-4fdc-b6a3-9dfafbd60112
ms.openlocfilehash: d303d298ca45504968b4b37bd2835381b7e2eee5
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094909"
---
# <a name="simplified-configuration-for-wcf-services"></a>Configuración simplificada de los servicios de WCF
Este ejemplo muestra cómo implementar y configurar un servicio y un cliente típicos con Windows Communication Foundation (WCF). Este ejemplo es la base para obtener todos los otros ejemplos tecnológicos básicos.  
  
 Este servicio, que expone un punto de conexión para comunicarse con el servicio, utiliza la configuración simplificada en .NET Framework 4. Antes de .NET Framework 4, el punto de conexión se define normalmente en un archivo de configuración (Web. config), tal como se muestra en el siguiente código de configuración de ejemplo.  
  
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
  
 En .NET Framework 4, el elemento `<service>` es opcional. Cuando un servicio no define ningún punto de conexión, se agregan al servicio un punto de conexión para cada dirección base y el contrato implementado. La dirección base se anexa al nombre del contrato para determinar el punto de conexión y el esquema de direcciones determina el enlace. El siguiente ejemplo de código muestra un archivo de configuración simplificado. Tal y como se ha configurado, se puede tener acceso al servicio en `http://localhost/servicemodelsamples/service.svc` un cliente en el mismo equipo. Para que los clientes en equipos remotos tengan acceso al servicio, se debe especificar un nombre de dominio completo en lugar del host local. El servicio no expone ningún metadato de forma predeterminada. Como tal, el servicio activa el comportamiento <xref:System.ServiceModel.Description.ServiceMetadataBehavior>.  
  
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
  
1. Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Para compilar la solución, siga las instrucciones de [creación de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Ejecute el ejemplo siguiendo estos pasos:  
  
    1. Haga clic con el botón derecho en el proyecto de **servicio** y seleccione **establecer como proyecto de inicio**y presione **Ctrl + F5**.  
  
    2. Espere a que el resultado de la consola confirme que el servicio está activo y en ejecución.  
  
    3. Haga clic con el botón derecho en el proyecto de **cliente** y seleccione **establecer como proyecto de inicio**y presione **Ctrl + F5**.  
  
> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos de Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)]. Este ejemplo se encuentra en el siguiente directorio.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ConfigSimplificationIn40`  
  
## <a name="see-also"></a>Consulte también

- [Ejemplos de administración de AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ff383405(v=azure.10))
- [Configuración simplificada](../../../../docs/framework/wcf/simplified-configuration.md)
