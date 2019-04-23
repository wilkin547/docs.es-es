---
title: Generador de canales de configuración
ms.date: 03/30/2017
ms.assetid: 3b749493-bd8a-4ccb-893e-5948901a1486
ms.openlocfilehash: 5bee4c7cc2c2e64c6e0d8d0ec2634f9500cd9d51
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2019
ms.locfileid: "59975876"
---
# <a name="configuration-channel-factory"></a>Generador de canales de configuración
En este ejemplo se explica el uso de <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>. El <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> permite la administración central de configuración de cliente WCF. Esto también puede ser útil en escenarios en los que la configuración se selecciona o se cambia después de la carga del dominio de aplicación.

## <a name="demonstrates"></a>Demostraciones
 <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>

## <a name="discussion"></a>Discusión
 En este ejemplo se muestra cómo utilizar <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> para agregar un archivo de configuración determinado a una aplicación cliente, sin tener que utilizar el archivo de configuración de la aplicación predeterminado.

 El ejemplo consta de dos proyectos. El primero es un servicio sencillo que se ejecuta para responder a los mensajes que provienen de los clientes. El segundo es una aplicación cliente que compila dos objetos <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> utilizando un <xref:System.Configuration.ExeConfigurationFileMap> para el archivo de configuración Test.config y los utiliza para comunicarse con el servicio. Ambos clientes se comunican con el servicio utilizando la configuración especificada en Test.config.

 El siguiente código agrega un archivo de configuración personalizado a una aplicación cliente.

```csharp
ExeConfigurationFileMap fileMap = new ExeConfigurationFileMap();
fileMap.ExeConfigFilename = "Test.config";
Configuration newConfiguration = ConfigurationManager.OpenMappedExeConfiguration(fileMap, ConfigurationUserLevel.None);

ConfigurationChannelFactory<ICalculatorChannel> factory1 = new ConfigurationChannelFactory<ICalculatorChannel>("endpoint1", newConfiguration, new EndpointAddress("http://localhost:8000/servicemodelsamples/service"));
ICalculatorChannel client1 = factory1.CreateChannel();
```

#### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo

1. Abra Visual Studio 2012 con privilegios de administrador.

2. Haga clic en la solución ConfigurationChannelFactory (2 proyectos) y, a continuación, seleccione **propiedades**.

3. En **propiedades comunes**, seleccione **proyecto de inicio**y, a continuación, haga clic en **varios proyectos de inicio**.

4. Mover el **servicio** al principio de la lista, el proyecto con el **acción 'Start'** y, a continuación, mueva el **cliente** proyecto después de la **servicio**proyecto, también con la **acción 'Start'**, por lo que **cliente** proyecto se ejecuta después de la **servicio** proyecto.

5. Haga clic en **Aceptar**y, a continuación, presione F5 (o CTRL + F5) para ejecutar el ejemplo.

> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ConfigurationChannelFactory`
