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
# <a name="configuration-channel-factory"></a><span data-ttu-id="ad045-102">Generador de canales de configuración</span><span class="sxs-lookup"><span data-stu-id="ad045-102">Configuration Channel Factory</span></span>
<span data-ttu-id="ad045-103">En este ejemplo se explica el uso de <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>.</span><span class="sxs-lookup"><span data-stu-id="ad045-103">This sample covers the usage of the <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>.</span></span> <span data-ttu-id="ad045-104">Permite <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> la administración central de la configuración del cliente WCF.</span><span class="sxs-lookup"><span data-stu-id="ad045-104">The <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> allows central management of WCF client configuration.</span></span> <span data-ttu-id="ad045-105">Esto también puede ser útil en escenarios en los que la configuración se selecciona o se cambia después de la carga del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="ad045-105">This can also be useful in scenarios in which configuration is selected or changed after the application domain load time.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="ad045-106">Muestra</span><span class="sxs-lookup"><span data-stu-id="ad045-106">Demonstrates</span></span>
 <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>

## <a name="discussion"></a><span data-ttu-id="ad045-107">Discusión</span><span class="sxs-lookup"><span data-stu-id="ad045-107">Discussion</span></span>
 <span data-ttu-id="ad045-108">En este ejemplo se muestra cómo utilizar <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> para agregar un archivo de configuración determinado a una aplicación cliente, sin tener que utilizar el archivo de configuración de la aplicación predeterminado.</span><span class="sxs-lookup"><span data-stu-id="ad045-108">This sample shows how to use <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> to add a particular configuration file to a client application, without having to use the default application configuration file.</span></span>

 <span data-ttu-id="ad045-109">El ejemplo consta de dos proyectos.</span><span class="sxs-lookup"><span data-stu-id="ad045-109">The sample consists of two projects.</span></span> <span data-ttu-id="ad045-110">El primero es un servicio sencillo que se ejecuta para responder a los mensajes que provienen de los clientes.</span><span class="sxs-lookup"><span data-stu-id="ad045-110">The first project is a simple service that runs to reply to messages coming from the clients.</span></span> <span data-ttu-id="ad045-111">El segundo es una aplicación cliente que compila dos objetos <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> utilizando un <xref:System.Configuration.ExeConfigurationFileMap> para el archivo de configuración Test.config y los utiliza para comunicarse con el servicio.</span><span class="sxs-lookup"><span data-stu-id="ad045-111">The second project is a client application that builds two <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> objects using a <xref:System.Configuration.ExeConfigurationFileMap> for the Test.config configuration file and uses them to communicate with the service.</span></span> <span data-ttu-id="ad045-112">Ambos clientes se comunican con el servicio utilizando la configuración especificada en Test.config.</span><span class="sxs-lookup"><span data-stu-id="ad045-112">Both clients communicate with the service using the configuration specified in Test.config.</span></span>

 <span data-ttu-id="ad045-113">El siguiente código agrega un archivo de configuración personalizado a una aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="ad045-113">The following code adds a custom configuration file to a client application.</span></span>

```csharp
ExeConfigurationFileMap fileMap = new ExeConfigurationFileMap();
fileMap.ExeConfigFilename = "Test.config";
Configuration newConfiguration = ConfigurationManager.OpenMappedExeConfiguration(fileMap, ConfigurationUserLevel.None);

ConfigurationChannelFactory<ICalculatorChannel> factory1 = new ConfigurationChannelFactory<ICalculatorChannel>("endpoint1", newConfiguration, new EndpointAddress("http://localhost:8000/servicemodelsamples/service"));
ICalculatorChannel client1 = factory1.CreateChannel();
```

#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="ad045-114">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="ad045-114">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="ad045-115">Abra Visual Studio 2012 con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="ad045-115">Open Visual Studio 2012 with administrator privileges.</span></span>

2. <span data-ttu-id="ad045-116">Haga clic con el botón secundario en la solución ConfigurationChannelFactory (2 proyectos) y, a continuación, seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="ad045-116">Right-click the ConfigurationChannelFactory solution (2 projects) and then select **Properties**.</span></span>

3. <span data-ttu-id="ad045-117">En **Propiedades comunes**, seleccione Proyecto de **inicio**y, a continuación, haga clic en Varios proyectos de **inicio**.</span><span class="sxs-lookup"><span data-stu-id="ad045-117">In **Common Properties**, select **Startup Project**, and then click **Multiple startup projects**.</span></span>

4. <span data-ttu-id="ad045-118">Mueva el proyecto **de servicio** al principio de la lista, con la **acción 'Inicio'** y, a continuación, mueva el proyecto **de cliente** después del proyecto de **servicio,** también con la **acción 'Inicio',** por lo que el proyecto **de cliente** se ejecuta después del proyecto de **servicio.**</span><span class="sxs-lookup"><span data-stu-id="ad045-118">Move the **Service** project to the beginning of the list, with the **Action ‘Start’**, and then move the **Client** project after the **Service** project, also with the **Action ‘Start’**, so the **Client** project is executed after the **Service** project.</span></span>

5. <span data-ttu-id="ad045-119">Haga clic en **Aceptar**y, a continuación, presione F5 (o CTRL+F5) para ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="ad045-119">Click **OK**, and then press F5 (or CTRL+F5) to run the sample.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ad045-120">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="ad045-120">The samples may already be installed on your machine.</span></span> <span data-ttu-id="ad045-121">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="ad045-121">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="ad045-122">Si este directorio no existe, vaya a Ejemplos de [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="ad045-122">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ad045-123">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="ad045-123">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ConfigurationChannelFactory`
