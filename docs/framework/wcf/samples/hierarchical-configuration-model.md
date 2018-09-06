---
title: Modelo de configuración jerárquica
ms.date: 03/30/2017
ms.assetid: 28dcc698-226c-4b77-9e51-8bf45a36216c
ms.openlocfilehash: 8ca9b01eb022e2e2ab940866a6230e8227ceb2dc
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2018
ms.locfileid: "43736398"
---
# <a name="hierarchical-configuration-model"></a><span data-ttu-id="55943-102">Modelo de configuración jerárquica</span><span class="sxs-lookup"><span data-stu-id="55943-102">Hierarchical Configuration Model</span></span>
<span data-ttu-id="55943-103">En este ejemplo se muestra cómo implementar una jerarquía de archivos de configuración para los servicios.</span><span class="sxs-lookup"><span data-stu-id="55943-103">This sample demonstrates how to implement a hierarchy of configuration files for services.</span></span> <span data-ttu-id="55943-104">También muestra cómo se heredan los enlaces, los comportamientos de servicio y los comportamientos de punto de conexión de los niveles superiores de la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="55943-104">It also shows how bindings, service behaviors, and endpoint behaviors are inherited from higher levels in the hierarchy.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="55943-105">Detalles del ejemplo</span><span class="sxs-lookup"><span data-stu-id="55943-105">Sample details</span></span>  
 <span data-ttu-id="55943-106">Una de las características desarrolladas para WCF en [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] es la mejora en el modelo de configuración jerárquica.</span><span class="sxs-lookup"><span data-stu-id="55943-106">One of the features developed for WCF in [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] is the improvement in the hierarchical configuration model.</span></span> <span data-ttu-id="55943-107">Un ejemplo de modelo de configuración jerárquico sería el definido por Machine.config -> Rootweb.config -> Web.config. En [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)], los enlaces y comportamientos que se definen en los niveles superiores en la jerarquía de configuración se agrega a sus servicios sin una configuración explícita.</span><span class="sxs-lookup"><span data-stu-id="55943-107">An example of a hierarchical configuration model would be the one defined by Machine.config -> Rootweb.config -> Web.config. In [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)], those bindings and behaviors that are defined in upper levels in the configuration hierarchy are added to your services with no explicit configuration.</span></span> <span data-ttu-id="55943-108">En este ejemplo se muestra cómo es posible simplificar la configuración de servicio basándose en los elementos de configuración definidos en el nivel de equipo o aplicación.</span><span class="sxs-lookup"><span data-stu-id="55943-108">This sample shows how it is possible to simplify your service configuration by relying on configuration elements defined at the computer or the application level.</span></span>  
  
 <span data-ttu-id="55943-109">Este ejemplo consta de nueve servicios, definidos en tres niveles de jerarquía.</span><span class="sxs-lookup"><span data-stu-id="55943-109">This sample consists of nine services, defined in three levels of hierarchy.</span></span> <span data-ttu-id="55943-110">`Service1` está en la raíz.</span><span class="sxs-lookup"><span data-stu-id="55943-110">`Service1` is at the root.</span></span> <span data-ttu-id="55943-111">`Service2` y `Service3` heredan los elementos predeterminados de `Service1`.</span><span class="sxs-lookup"><span data-stu-id="55943-111">`Service2` and `Service3` inherit the default elements from `Service1`.</span></span> <span data-ttu-id="55943-112">`Service4`, `Service5`, `Service6` y `Service7` se definen en un tercer nivel de la jerarquía y heredan los elementos predeterminados de `Service3`.</span><span class="sxs-lookup"><span data-stu-id="55943-112">`Service4`, `Service5`, `Service6` and `Service7` are defined at a third level of the hierarchy, inheriting the default elements from `Service3`.</span></span> <span data-ttu-id="55943-113">Finalmente, `Service10` y `Service11` están en el cuarto nivel de la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="55943-113">Finally `Service10` and `Service11` are at a fourth level of the hierarchy.</span></span>  
  
 <span data-ttu-id="55943-114">Todos los servicios implementan el contrato `IDesc`.</span><span class="sxs-lookup"><span data-stu-id="55943-114">All the services implement the `IDesc` contract.</span></span> <span data-ttu-id="55943-115">La siguiente definición corresponde a la interfaz `IDesc` que muestra los métodos expuestos en esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="55943-115">The following is the definition of the `IDesc` interface that shows the methods exposed in this interface.</span></span> <span data-ttu-id="55943-116">La interfaz `IDesc` se define en Service1.cs.</span><span class="sxs-lookup"><span data-stu-id="55943-116">The `IDesc` interface is defined in Service1.cs.</span></span>  
  
```csharp  
// Define a service contract  
[ServiceContract(Namespace="http://Microsoft.Samples.ConfigHierarchicalModel")]  
public interface IDesc  
{  
    [OperationContract]  
    List<string> ListEndpoints();  
    [OperationContract]  
    List<string> ListServiceBehaviors();  
    [OperationContract]  
    List<string> ListEndpointBehaviors();  
}  
```  
  
 <span data-ttu-id="55943-117">La implementación de estos métodos por parte de los servicios es sencilla.</span><span class="sxs-lookup"><span data-stu-id="55943-117">The implementation of these methods by the services is straightforward.</span></span> <span data-ttu-id="55943-118">`ListEndpoints` recorre todos las extremos de servicio y devuelve una lista de todos los extremos que el servicio tiene.</span><span class="sxs-lookup"><span data-stu-id="55943-118">`ListEndpoints` iterates through all the service endpoints and returns a list of all the endpoints that the service has.</span></span> <span data-ttu-id="55943-119">`ListServiceBehaviors` recorre todos los comportamientos agregados al servicio y devuelve la lista de todos los comportamientos de servicio asociados al servicio.</span><span class="sxs-lookup"><span data-stu-id="55943-119">`ListServiceBehaviors` iterates through all the behaviors added to the service and returns the list of all the service behaviors associated with the service.</span></span> <span data-ttu-id="55943-120">`ListEndpointBehaviors` se comporta de forma similar a `ListServiceBehaviors`, pero devuelve la lista de comportamientos de extremo en su lugar.</span><span class="sxs-lookup"><span data-stu-id="55943-120">`ListEndpointBehaviors` behaves in a similar way to `ListServiceBehaviors`, but it returns the list of endpoint behaviors instead.</span></span>  
  
 <span data-ttu-id="55943-121">Esta implementación permite al cliente saber cuántos extremos expone el servicio y qué comportamientos de servicio y de extremo se han agregado al servicio.</span><span class="sxs-lookup"><span data-stu-id="55943-121">This implementation allows the client to know how many endpoints the service is exposing and which service behaviors and endpoint behaviors have been added to the service.</span></span> <span data-ttu-id="55943-122">El cliente implementado como parte del ejemplo agrega una referencia de servicio a todos los servicios en la solución y muestra estos elementos para cada uno de los servicios.</span><span class="sxs-lookup"><span data-stu-id="55943-122">The client that has been implemented as part of the sample adds a service reference to all the services in the solution and shows these elements for each one of the services.</span></span>  
  
## <a name="to-use-this-sample"></a><span data-ttu-id="55943-123">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="55943-123">To use this sample</span></span>  
  
#### <a name="to-run-the-client"></a><span data-ttu-id="55943-124">Para ejecutar el cliente</span><span class="sxs-lookup"><span data-stu-id="55943-124">To run the client</span></span>  
  
1.  <span data-ttu-id="55943-125">Mediante [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], abra el archivo ConfigHierarchicalModel.sln.</span><span class="sxs-lookup"><span data-stu-id="55943-125">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open the ConfigHierarchicalModel.sln file.</span></span>  
  
2.  <span data-ttu-id="55943-126">El proyecto de cliente aún no está configurado como proyecto de inicio; siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="55943-126">The client project is not already set up as the start-up project, follow these steps.</span></span>  
  
    1.  <span data-ttu-id="55943-127">En **el Explorador de soluciones**, haga clic en la solución y, a continuación, seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="55943-127">In **Solution Explorer**, right-click the solution and then select **Properties**.</span></span>  
  
    2.  <span data-ttu-id="55943-128">En **propiedades comunes**, seleccione **proyecto de inicio**y, a continuación, haga clic en **proyecto de inicio único**.</span><span class="sxs-lookup"><span data-stu-id="55943-128">In **Common Properties**, select **Startup Project**, and then click **Single startup project**.</span></span>  
  
    3.  <span data-ttu-id="55943-129">Desde el **proyecto de inicio único** lista desplegable, seleccione **cliente**.</span><span class="sxs-lookup"><span data-stu-id="55943-129">From the **Single startup project** drop-down, select **Client**.</span></span>  
  
    4.  <span data-ttu-id="55943-130">Haga clic en **Aceptar** para cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="55943-130">Click **OK** to close the dialog.</span></span>  
  
3.  <span data-ttu-id="55943-131">Para generar el ejemplo, presione Ctrl+Mayús+B.</span><span class="sxs-lookup"><span data-stu-id="55943-131">To build the sample, press CTRL+SHIFT+B.</span></span>  
  
4.  <span data-ttu-id="55943-132">Para ejecutar el cliente, presione Ctrl+F5.</span><span class="sxs-lookup"><span data-stu-id="55943-132">To run the client, press Ctrl+F5.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="55943-133">Si estos pasos no funcionan, asegúrese de que el entorno ha se ha establecido correctamente, mediante los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="55943-133">If these steps do not work, make sure that your environment has been properly set up, using the following steps:</span></span>  
>   
> 1.  <span data-ttu-id="55943-134">Asegúrese de que ha realizado la [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="55943-134">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
> 2.  <span data-ttu-id="55943-135">Para compilar la solución, siga las instrucciones de [compilar los ejemplos de Windows Communication Foundation](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="55943-135">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
> 3.  <span data-ttu-id="55943-136">Para ejecutar el ejemplo en una o varias configuraciones de equipo, siga las instrucciones de [ejecutando los ejemplos de Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="55943-136">To run the sample in a single or multiple computer configurations, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="55943-137">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="55943-137">The samples may already be installed on your computer.</span></span> <span data-ttu-id="55943-138">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="55943-138">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="55943-139">Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="55943-139">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="55943-140">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="55943-140">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ConfigHierarchicalModel`  
  
## <a name="see-also"></a><span data-ttu-id="55943-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="55943-141">See Also</span></span>  
 [<span data-ttu-id="55943-142">Ejemplos de administración de AppFabric</span><span class="sxs-lookup"><span data-stu-id="55943-142">AppFabric Management Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=193960)
