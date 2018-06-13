---
title: Generador de canales de configuración
ms.date: 03/30/2017
ms.assetid: 3b749493-bd8a-4ccb-893e-5948901a1486
ms.openlocfilehash: fc3a564128e520133c2404a82438e692b1381875
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2018
ms.locfileid: "33806583"
---
# <a name="configuration-channel-factory"></a>Generador de canales de configuración
En este ejemplo se explica el uso de <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>. El <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> permite la administración central de la configuración de cliente WCF. Esto también puede ser útil en escenarios en los que la configuración se selecciona o se cambia después de la carga del dominio de aplicación.  
  
## <a name="demonstrates"></a>Demostraciones  
 <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>  
  
## <a name="discussion"></a>Explicación  
 En este ejemplo se muestra cómo utilizar <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> para agregar un archivo de configuración determinado a una aplicación cliente, sin tener que utilizar el archivo de configuración de la aplicación predeterminado.  
  
 El ejemplo consta de dos proyectos. El primero es un servicio sencillo que se ejecuta para responder a los mensajes que provienen de los clientes. El segundo es una aplicación cliente que compila dos objetos <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> utilizando un <xref:System.Configuration.ExeConfigurationFileMap> para el archivo de configuración Test.config y los utiliza para comunicarse con el servicio. Ambos clientes se comunican con el servicio utilizando la configuración especificada en Test.config.  
  
 El siguiente código agrega un archivo de configuración personalizado a una aplicación cliente.  
  
```  
ExeConfigurationFileMap fileMap = new ExeConfigurationFileMap();  
fileMap.ExeConfigFilename = "Test.config";  
Configuration newConfiguration = ConfigurationManager.OpenMappedExeConfiguration(fileMap, ConfigurationUserLevel.None);  
  
ConfigurationChannelFactory<ICalculatorChannel> factory1 = new ConfigurationChannelFactory<ICalculatorChannel>("endpoint1", newConfiguration, new EndpointAddress("http://localhost:8000/servicemodelsamples/service"));  
ICalculatorChannel client1 = factory1.CreateChannel();  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1.  Abra [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] con privilegios de administrador.  
  
2.  Haga clic en la solución ConfigurationChannelFactory (2 proyectos) y, a continuación, seleccione **propiedades**.  
  
3.  En **propiedades comunes**, seleccione **proyecto de inicio**y, a continuación, haga clic en **proyectos de inicio múltiples**.  
  
4.  Mover el **servicio** proyecto hasta el principio de la lista, con el **acción 'Start'** y, a continuación, mueva el **cliente** proyecto después de la **servicio**proyecto, también con el **acción 'Start'**, por lo que la **cliente** proyecto se ejecuta después de la **servicio** proyecto.  
  
5.  Haga clic en **Aceptar**y, a continuación, presione F5 (o CTRL + F5) para ejecutar el ejemplo.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si este directorio no existe, vaya a [Windows Communication Foundation (WCF) y ejemplos de Windows Workflow Foundation (WF) para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ConfigurationChannelFactory`
