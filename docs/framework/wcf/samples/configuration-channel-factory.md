---
title: Generador de canales de configuración
ms.date: 03/30/2017
ms.assetid: 3b749493-bd8a-4ccb-893e-5948901a1486
ms.openlocfilehash: 0f00ba5e217420fe416100071d380e413c3df118
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183948"
---
# <a name="configuration-channel-factory"></a>Generador de canales de configuración
En este ejemplo se explica el uso de <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>. Permite <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> la administración central de la configuración del cliente WCF. Esto también puede ser útil en escenarios en los que la configuración se selecciona o se cambia después de la carga del dominio de aplicación.

## <a name="demonstrates"></a>Muestra
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

2. Haga clic con el botón secundario en la solución ConfigurationChannelFactory (2 proyectos) y, a continuación, seleccione **Propiedades**.

3. En **Propiedades comunes**, seleccione Proyecto de **inicio**y, a continuación, haga clic en Varios proyectos de **inicio**.

4. Mueva el proyecto **de servicio** al principio de la lista, con la **acción 'Inicio'** y, a continuación, mueva el proyecto **de cliente** después del proyecto de **servicio,** también con la **acción 'Inicio',** por lo que el proyecto **de cliente** se ejecuta después del proyecto de **servicio.**

5. Haga clic en **Aceptar**y, a continuación, presione F5 (o CTRL+F5) para ejecutar el ejemplo.

> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Si este directorio no existe, vaya a Ejemplos de [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF). Este ejemplo se encuentra en el siguiente directorio.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ConfigurationChannelFactory`
