---
title: "Generador de canales de configuraci&#243;n | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3b749493-bd8a-4ccb-893e-5948901a1486
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# Generador de canales de configuraci&#243;n
En este ejemplo se explica el uso de <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>.<xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> permite la administración central de la configuración de cliente de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].Esto también puede ser útil en escenarios en los que la configuración se selecciona o se cambia después de la carga del dominio de aplicación.  
  
## Demostraciones  
 <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>  
  
## Análisis  
 En este ejemplo se muestra cómo utilizar <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> para agregar un archivo de configuración determinado a una aplicación cliente, sin tener que utilizar el archivo de configuración de la aplicación predeterminado.  
  
 El ejemplo consta de dos proyectos.El primero es un servicio sencillo que se ejecuta para responder a los mensajes que provienen de los clientes.El segundo es una aplicación cliente que compila dos objetos <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> utilizando un <xref:System.Configuration.ExeConfigurationFileMap> para el archivo de configuración Test.config y los utiliza para comunicarse con el servicio.Ambos clientes se comunican con el servicio utilizando la configuración especificada en Test.config.  
  
 El siguiente código agrega un archivo de configuración personalizado a una aplicación cliente.  
  
```  
ExeConfigurationFileMap fileMap = new ExeConfigurationFileMap();  
fileMap.ExeConfigFilename = "Test.config";  
Configuration newConfiguration = ConfigurationManager.OpenMappedExeConfiguration(fileMap, ConfigurationUserLevel.None);  
  
ConfigurationChannelFactory<ICalculatorChannel> factory1 = new ConfigurationChannelFactory<ICalculatorChannel>("endpoint1", newConfiguration, new EndpointAddress("http://localhost:8000/servicemodelsamples/service"));  
ICalculatorChannel client1 = factory1.CreateChannel();  
  
```  
  
#### Para configurar, compilar y ejecutar el ejemplo  
  
1.  Abra [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] con privilegios de administrador.  
  
2.  Haga clic con el botón secundario en la solución ConfigurationChannelFactory \(dos proyectos\) y, a continuación, seleccione **Propiedades**.  
  
3.  En **Propiedades comunes**, seleccione **Proyecto de inicio** y, a continuación, haga clic en **Proyectos de inicio múltiples**.  
  
4.  Mueva el proyecto **Servicio** al principio de la lista, con la **Acción 'Iniciar'** y, a continuación, mueva el proyecto **Cliente** a continuación del proyecto **Servicio**, también con la **Acción 'Iniciar'**, de modo que el proyecto **Cliente** se ejecute después del proyecto **Servicio**.  
  
5.  Haga clic en **Aceptar** y, a continuación, presione F5 \(o CTRL\+F5\) para ejecutar el ejemplo.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WCF\Basic\Services\ConfigurationChannelFactory`