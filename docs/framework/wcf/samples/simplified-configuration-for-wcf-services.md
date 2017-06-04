---
title: "Configuraci&#243;n simplificada de los servicios de WCF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1e39ec25-18a3-4fdc-b6a3-9dfafbd60112
caps.latest.revision: 11
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 11
---
# Configuraci&#243;n simplificada de los servicios de WCF
Este ejemplo muestra cómo implementar y configurar un cliente y un servicio típicos con [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Este ejemplo es la base para obtener todos los demás ejemplos tecnológicos básicos.  
  
 Este servicio, que expone un extremo para comunicar con el servicio, utiliza la configuración simplificada en [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)].Antes de [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)], el extremo se solía definir en un archivo de configuración \(Web.config\), como se muestra en el siguiente código de configuración de ejemplo.  
  
```  
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
  
 En [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)], el elemento `<service>` es opcional.Cuando un servicio no define ningún extremo, se agregan al servicio un extremo para cada dirección base y el contrato implementado.La dirección base se anexa al nombre del contrato para determinar el extremo y el esquema de direcciones determina el enlace.El siguiente ejemplo de código muestra un archivo de configuración simplificado.Tal y como se ha configurado, un cliente puede tener acceso al servicio en http:\/\/localhost\/servicemodelsamples\/service.svc en el mismo equipo.Para que los clientes en equipos remotos tengan acceso al servicio, se debe especificar un nombre de dominio completo en lugar del host local.El servicio no expone ningún metadato de forma predeterminada.Como tal, el servicio activa el comportamiento <xref:System.ServiceModel.Description.ServiceMetadataBehavior>.  
  
```  
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
  
### Para utilizar este ejemplo  
  
1.  Asegúrese de realizar los [Procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Para compilar la solución, siga las instrucciones de [Compilación de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Ejecute el ejemplo siguiendo estos pasos:  
  
    1.  Haga clic con el botón secundario en el proyecto de **Servicio**, seleccione **Establecer como proyecto de inicio** y, a continuación, presione **Ctrl\+F5**.  
  
    2.  Espere a que el resultado de la consola confirme que el servicio está activo y en ejecución.  
  
    3.  Haga clic con el botón secundario en el proyecto de **Cliente**, seleccione **Establecer como proyecto de inicio** y, a continuación, presione **Ctrl\+F5**.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WCF\Basic\Services\ConfigSimplificationIn40`  
  
## Vea también  
 [Ejemplos de administración de AppFabric](http://go.microsoft.com/fwlink/?LinkId=193960)   
 [Configuración simplificada](../../../../docs/framework/wcf/simplified-configuration.md)