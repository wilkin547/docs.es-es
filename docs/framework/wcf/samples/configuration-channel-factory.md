---
title: Generador de canales de configuración
ms.date: 03/30/2017
ms.assetid: 3b749493-bd8a-4ccb-893e-5948901a1486
ms.openlocfilehash: 1b74c15599ebc932a2a0ed46d646b54bec986794
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2019
ms.locfileid: "70045654"
---
# <a name="configuration-channel-factory"></a><span data-ttu-id="bdd08-102">Generador de canales de configuración</span><span class="sxs-lookup"><span data-stu-id="bdd08-102">Configuration Channel Factory</span></span>
<span data-ttu-id="bdd08-103">En este ejemplo se explica el uso de <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>.</span><span class="sxs-lookup"><span data-stu-id="bdd08-103">This sample covers the usage of the <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>.</span></span> <span data-ttu-id="bdd08-104">Permite <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> la administración central de la configuración del cliente de WCF.</span><span class="sxs-lookup"><span data-stu-id="bdd08-104">The <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> allows central management of WCF client configuration.</span></span> <span data-ttu-id="bdd08-105">Esto también puede ser útil en escenarios en los que la configuración se selecciona o se cambia después de la carga del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="bdd08-105">This can also be useful in scenarios in which configuration is selected or changed after the application domain load time.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="bdd08-106">Demostraciones</span><span class="sxs-lookup"><span data-stu-id="bdd08-106">Demonstrates</span></span>
 <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>

## <a name="discussion"></a><span data-ttu-id="bdd08-107">Discusión</span><span class="sxs-lookup"><span data-stu-id="bdd08-107">Discussion</span></span>
 <span data-ttu-id="bdd08-108">En este ejemplo se muestra cómo utilizar <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> para agregar un archivo de configuración determinado a una aplicación cliente, sin tener que utilizar el archivo de configuración de la aplicación predeterminado.</span><span class="sxs-lookup"><span data-stu-id="bdd08-108">This sample shows how to use <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> to add a particular configuration file to a client application, without having to use the default application configuration file.</span></span>

 <span data-ttu-id="bdd08-109">El ejemplo consta de dos proyectos.</span><span class="sxs-lookup"><span data-stu-id="bdd08-109">The sample consists of two projects.</span></span> <span data-ttu-id="bdd08-110">El primero es un servicio sencillo que se ejecuta para responder a los mensajes que provienen de los clientes.</span><span class="sxs-lookup"><span data-stu-id="bdd08-110">The first project is a simple service that runs to reply to messages coming from the clients.</span></span> <span data-ttu-id="bdd08-111">El segundo es una aplicación cliente que compila dos objetos <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> utilizando un <xref:System.Configuration.ExeConfigurationFileMap> para el archivo de configuración Test.config y los utiliza para comunicarse con el servicio.</span><span class="sxs-lookup"><span data-stu-id="bdd08-111">The second project is a client application that builds two <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> objects using a <xref:System.Configuration.ExeConfigurationFileMap> for the Test.config configuration file and uses them to communicate with the service.</span></span> <span data-ttu-id="bdd08-112">Ambos clientes se comunican con el servicio utilizando la configuración especificada en Test.config.</span><span class="sxs-lookup"><span data-stu-id="bdd08-112">Both clients communicate with the service using the configuration specified in Test.config.</span></span>

 <span data-ttu-id="bdd08-113">El siguiente código agrega un archivo de configuración personalizado a una aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="bdd08-113">The following code adds a custom configuration file to a client application.</span></span>

```csharp
ExeConfigurationFileMap fileMap = new ExeConfigurationFileMap();
fileMap.ExeConfigFilename = "Test.config";
Configuration newConfiguration = ConfigurationManager.OpenMappedExeConfiguration(fileMap, ConfigurationUserLevel.None);

ConfigurationChannelFactory<ICalculatorChannel> factory1 = new ConfigurationChannelFactory<ICalculatorChannel>("endpoint1", newConfiguration, new EndpointAddress("http://localhost:8000/servicemodelsamples/service"));
ICalculatorChannel client1 = factory1.CreateChannel();
```

#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="bdd08-114">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="bdd08-114">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="bdd08-115">Abra Visual Studio 2012 con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="bdd08-115">Open Visual Studio 2012 with administrator privileges.</span></span>

2. <span data-ttu-id="bdd08-116">Haga clic con el botón secundario en la solución ConfigurationChannelFactory (2 proyectos) y, a continuación, seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="bdd08-116">Right-click the ConfigurationChannelFactory solution (2 projects) and then select **Properties**.</span></span>

3. <span data-ttu-id="bdd08-117">En **propiedades comunes**, seleccione **proyecto de inicio**y, a continuación, haga clic en **proyectos de inicio múltiples**.</span><span class="sxs-lookup"><span data-stu-id="bdd08-117">In **Common Properties**, select **Startup Project**, and then click **Multiple startup projects**.</span></span>

4. <span data-ttu-id="bdd08-118">Mueva el proyecto de **servicio** al principio de la lista, con la **Acción ' iniciar '** y, a continuación, mueva el proyecto de **cliente** después del proyecto de **servicio** , también con la **Acción ' iniciar '** , de modo que se ejecute el proyecto de **cliente** . después del proyecto de **servicio** .</span><span class="sxs-lookup"><span data-stu-id="bdd08-118">Move the **Service** project to the beginning of the list, with the **Action ‘Start’**, and then move the **Client** project after the **Service** project, also with the **Action ‘Start’**, so the **Client** project is executed after the **Service** project.</span></span>

5. <span data-ttu-id="bdd08-119">Haga clic en **Aceptar**y, a continuación, presione F5 (o Ctrl + F5) para ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="bdd08-119">Click **OK**, and then press F5 (or CTRL+F5) to run the sample.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bdd08-120">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="bdd08-120">The samples may already be installed on your machine.</span></span> <span data-ttu-id="bdd08-121">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="bdd08-121">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="bdd08-122">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y ejemplos.</span><span class="sxs-lookup"><span data-stu-id="bdd08-122">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="bdd08-123">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="bdd08-123">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ConfigurationChannelFactory`
