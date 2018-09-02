---
title: Compatibilidad de ASP.NET
ms.date: 03/30/2017
ms.assetid: c8b51f1e-c096-4c42-ad99-0519887bbbc5
ms.openlocfilehash: eeb09914fc90848c987127c789379549917063f6
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43398240"
---
# <a name="aspnet-compatibility"></a><span data-ttu-id="d94ba-102">Compatibilidad de ASP.NET</span><span class="sxs-lookup"><span data-stu-id="d94ba-102">ASP.NET Compatibility</span></span>
<span data-ttu-id="d94ba-103">Este ejemplo muestra cómo habilitar el modo de compatibilidad de ASP.NET en Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="d94ba-103">This sample demonstrates how to enable ASP.NET Compatibility mode in Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="d94ba-104">Servicios que se ejecutan en la compatibilidad de ASP.NET modo participan totalmente en la canalización de aplicación de ASP.NET y puede hacer usan de las características ASP.NET como archivo/autorización de URL, estado de sesión y el <xref:System.Web.HttpContext> clase.</span><span class="sxs-lookup"><span data-stu-id="d94ba-104">Services running in ASP.NET Compatibility mode participate fully in the ASP.NET application pipeline and can make use of ASP.NET features such as file/URL authorization, session state, and the <xref:System.Web.HttpContext> class.</span></span> <span data-ttu-id="d94ba-105">La <xref:System.Web.HttpContext> clase permite el acceso a las cookies, sesiones y otras características de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="d94ba-105">The <xref:System.Web.HttpContext> class allows access to cookies, sessions, and other ASP.NET features.</span></span> <span data-ttu-id="d94ba-106">Este modo requiere que los enlaces utilicen el transporte HTTP y el propio servicio se debe hospedar en IIS.</span><span class="sxs-lookup"><span data-stu-id="d94ba-106">This mode requires that the bindings use the HTTP transport and the service itself must be hosted in IIS.</span></span>  
  
 <span data-ttu-id="d94ba-107">En este ejemplo, el cliente es una aplicación de consola (un ejecutable) e Internet Information Servers (IIS) hospeda el servicio.</span><span class="sxs-lookup"><span data-stu-id="d94ba-107">In this sample, the client is a console application (an executable) and the service is hosted in Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d94ba-108">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="d94ba-108">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
<span data-ttu-id="d94ba-109">En este ejemplo se requiere un grupo de aplicaciones de [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] para ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="d94ba-109">This sample requires a [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] application pool in order to run.</span></span> <span data-ttu-id="d94ba-110">Para crear un nuevo grupo de aplicaciones o modificar el grupo de aplicaciones predeterminado, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="d94ba-110">To create a new application pool, or to modify the default application pool, follow these steps.</span></span>  

1.  <span data-ttu-id="d94ba-111">Abra **Panel de Control**.</span><span class="sxs-lookup"><span data-stu-id="d94ba-111">Open **Control Panel**.</span></span>  <span data-ttu-id="d94ba-112">Abra el **herramientas administrativas** subprograma en el **sistema y seguridad** encabezado.</span><span class="sxs-lookup"><span data-stu-id="d94ba-112">Open the **Administrative Tools** applet under the **System and Security** heading.</span></span> <span data-ttu-id="d94ba-113">Abra el **Internet Information Services (IIS) Manager** applet.</span><span class="sxs-lookup"><span data-stu-id="d94ba-113">Open the **Internet Information Services (IIS) Manager** applet.</span></span>  

2.  <span data-ttu-id="d94ba-114">Expanda la vista de árbol en el **conexiones** panel.</span><span class="sxs-lookup"><span data-stu-id="d94ba-114">Expand the treeview in the **Connections** pane.</span></span> <span data-ttu-id="d94ba-115">Seleccione el **grupos de aplicaciones** nodo.</span><span class="sxs-lookup"><span data-stu-id="d94ba-115">Select the **Application Pools** node.</span></span>  

3.  <span data-ttu-id="d94ba-116">Para establecer el grupo de aplicaciones predeterminado a usar [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] (lo que puede producir problemas de incompatibilidad con los sitios existentes), haga clic en el **DefaultAppPool** de elemento de lista y seleccione **configuración básica...** .</span><span class="sxs-lookup"><span data-stu-id="d94ba-116">To set the default application pool to use [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] (which may cause incompatibility problems with existing sites), right-click the **DefaultAppPool** list item and select **Basic Settings…**.</span></span> <span data-ttu-id="d94ba-117">Establecer el **.Net Framework versión** desplegable para **.Net Framework v4.0.30128** (o posterior).</span><span class="sxs-lookup"><span data-stu-id="d94ba-117">Set the **.Net Framework Version** pull-down to **.Net Framework v4.0.30128** (or later).</span></span>  

4.  <span data-ttu-id="d94ba-118">Para crear un nuevo grupo de aplicaciones que usa [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] (para conservar la compatibilidad con otras aplicaciones), haga clic en el **grupos de aplicaciones** nodo y seleccione **Agregar grupo de aplicaciones...** .</span><span class="sxs-lookup"><span data-stu-id="d94ba-118">To create a new application pool that uses [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] (to preserve compatibility for other applications), right-click the **Application Pools** node and select **Add Application Pool…**.</span></span> <span data-ttu-id="d94ba-119">Nombre del nuevo grupo de aplicaciones y establecer el **.Net Framework versión** desplegable para **.Net Framework v4.0.30128** (o posterior).</span><span class="sxs-lookup"><span data-stu-id="d94ba-119">Name the new application pool, and set the **.Net Framework Version** pull-down to **.Net Framework v4.0.30128** (or later).</span></span> <span data-ttu-id="d94ba-120">Después de ejecutar el programa de instalación de pasos a continuación, haga clic en el **ServiceModelSamples** aplicación y seleccione **administrar aplicación**, **configuración avanzada...** .</span><span class="sxs-lookup"><span data-stu-id="d94ba-120">After running the setup steps below, right-click the **ServiceModelSamples** application and select **Manage Application**, **Advanced Settings…**.</span></span> <span data-ttu-id="d94ba-121">Establecer el **AppPool** al nuevo grupo de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="d94ba-121">Set the **Application Pool** to the new application pool.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d94ba-122">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="d94ba-122">The samples may already be installed on your computer.</span></span> <span data-ttu-id="d94ba-123">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="d94ba-123">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="d94ba-124">Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="d94ba-124">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="d94ba-125">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="d94ba-125">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebHost\ASPNetCompatibility`  
  
 <span data-ttu-id="d94ba-126">En este ejemplo se basa en el [Introducción](../../../../docs/framework/wcf/samples/getting-started-sample.md), que implementa un servicio de calculadora.</span><span class="sxs-lookup"><span data-stu-id="d94ba-126">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md), which implements a calculator service.</span></span> <span data-ttu-id="d94ba-127">El contrato `ICalculator` se ha modificado como contrato`ICalculatorSession` para permitir realizar un conjunto de operaciones, manteniendo un resultado en ejecución.</span><span class="sxs-lookup"><span data-stu-id="d94ba-127">The `ICalculator` contract has been modified as the `ICalculatorSession` contract to allow a set of operations to be performed, while keeping a running result.</span></span>  
  
```csharp  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface ICalculatorSession  
{  
    [OperationContract]  
    void Clear();  
    [OperationContract]  
    void AddTo(double n);  
    [OperationContract]  
    void SubtractFrom(double n);  
    [OperationContract]  
    void MultiplyBy(double n);  
    [OperationContract]  
    void DivideBy(double n);  
    [OperationContract]  
    double Result();  
}  
```  
  
 <span data-ttu-id="d94ba-128">El servicio mantiene el estado, utilizando la característica, para cada cliente ya que se llama a varias operaciones de servicio para realizar un cálculo.</span><span class="sxs-lookup"><span data-stu-id="d94ba-128">The service maintains state, using the feature, for each client as multiple service operations are called to perform a calculation.</span></span> <span data-ttu-id="d94ba-129">El cliente puede recuperar el resultado actual llamando a `Result` y borrar el resultado para ponerlo a cero llamando a `Clear`.</span><span class="sxs-lookup"><span data-stu-id="d94ba-129">The client can retrieve the current result by calling `Result` and can clear the result to zero by calling `Clear`.</span></span>  
  
 <span data-ttu-id="d94ba-130">El servicio utiliza la sesión de ASP.NET para almacenar el resultado de cada sesión de cliente.</span><span class="sxs-lookup"><span data-stu-id="d94ba-130">The service uses the ASP.NET session to store the result for each client session.</span></span> <span data-ttu-id="d94ba-131">Esto permite al servicio mantener el resultado en ejecución para cada cliente por varias llamadas al servicio.</span><span class="sxs-lookup"><span data-stu-id="d94ba-131">This allows the service to maintain the running result for each client across multiple calls to the service.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d94ba-132">Estado de sesión ASP.NET y las sesiones WCF son cosas muy diferentes.</span><span class="sxs-lookup"><span data-stu-id="d94ba-132">ASP.NET session state and WCF sessions are very different things.</span></span> <span data-ttu-id="d94ba-133">Consulte [sesión](../../../../docs/framework/wcf/samples/session.md) para obtener más información sobre las sesiones WCF.</span><span class="sxs-lookup"><span data-stu-id="d94ba-133">See [Session](../../../../docs/framework/wcf/samples/session.md) for details on WCF sessions.</span></span>
  
 <span data-ttu-id="d94ba-134">El servicio tiene una dependencia íntima en estado de sesión ASP.NET y requiere el modo de compatibilidad ASP.NET funcione correctamente.</span><span class="sxs-lookup"><span data-stu-id="d94ba-134">The service has an intimate dependency on ASP.NET session state and requires ASP.NET compatibility mode to function correctly.</span></span> <span data-ttu-id="d94ba-135">Estos requisitos se expresan mediante declaración aplicando el atributo `AspNetCompatibilityRequirements`.</span><span class="sxs-lookup"><span data-stu-id="d94ba-135">These requirements are expressed declaratively by applying the `AspNetCompatibilityRequirements` attribute.</span></span>  
  
```csharp  
[AspNetCompatibilityRequirements(RequirementsMode =  
                       AspNetCompatibilityRequirementsMode.Required)]  
public class CalculatorService : ICalculatorSession  
{  
    double Result  
    {  // store result in AspNet Session  
       get {  
          if (HttpContext.Current.Session["Result"] != null)  
             return (double)HttpContext.Current.Session["Result"];  
          return 0.0D;  
       }  
       set  
       {  
          HttpContext.Current.Session["Result"] = value;  
       }  
    }  
    public void Clear()  
    {  
        Result = 0.0D;  
    }  
    public void AddTo(double n)  
    {  
        Result += n;  
    }  
    public void SubtractFrom(double n)  
    {  
        Result -= n;  
    }  
    public void MultiplyBy(double n)  
    {  
        Result *= n;  
    }  
    public void DivideBy(double n)  
    {  
        Result /= n;  
    }  
    public double Result()  
    {  
        return Result;  
    }  
}  
```
  
 <span data-ttu-id="d94ba-136">Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="d94ba-136">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="d94ba-137">Presione ENTRAR en la ventana de cliente para cerrar el cliente.</span><span class="sxs-lookup"><span data-stu-id="d94ba-137">Press ENTER in the client window to shut down the client.</span></span>  
  
```console
0, + 100, - 50, * 17.65, / 2 = 441.25  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="d94ba-138">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="d94ba-138">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="d94ba-139">Asegúrese de que ha realizado la [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="d94ba-139">Be sure you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="d94ba-140">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="d94ba-140">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="d94ba-141">Una vez compilada la solución, ejecute Setup.bat para configurar la aplicación ServiceModelSamples en [!INCLUDE[iisver](../../../../includes/iisver-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d94ba-141">After the solution has been built, run Setup.bat to set up the ServiceModelSamples Application in [!INCLUDE[iisver](../../../../includes/iisver-md.md)].</span></span> <span data-ttu-id="d94ba-142">El directorio ServiceModelSamples debería aparecer ahora como una aplicación de [!INCLUDE[iisver](../../../../includes/iisver-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d94ba-142">The ServiceModelSamples directory should now appear as an [!INCLUDE[iisver](../../../../includes/iisver-md.md)] Application.</span></span>  
  
4.  <span data-ttu-id="d94ba-143">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecutando los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="d94ba-143">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d94ba-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="d94ba-144">See Also</span></span>  
 [<span data-ttu-id="d94ba-145">Ejemplos de persistencia y el hospedaje de AppFabric</span><span class="sxs-lookup"><span data-stu-id="d94ba-145">AppFabric Hosting and Persistence Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=193961)
