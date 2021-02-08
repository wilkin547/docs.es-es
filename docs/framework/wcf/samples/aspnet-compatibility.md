---
description: 'Más información acerca de: compatibilidad con ASP.NET'
title: Compatibilidad de ASP.NET
ms.date: 03/30/2017
ms.assetid: c8b51f1e-c096-4c42-ad99-0519887bbbc5
ms.openlocfilehash: a5685481a16d87715d4fc9096055af5be479f459
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99778859"
---
# <a name="aspnet-compatibility"></a><span data-ttu-id="9e18e-103">Compatibilidad de ASP.NET</span><span class="sxs-lookup"><span data-stu-id="9e18e-103">ASP.NET Compatibility</span></span>

<span data-ttu-id="9e18e-104">Este ejemplo muestra cómo habilitar el modo de compatibilidad de ASP.NET en Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="9e18e-104">This sample demonstrates how to enable ASP.NET Compatibility mode in Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="9e18e-105">Los servicios que se ejecutan en modo de compatibilidad ASP.NET participan completamente en la canalización de la aplicación ASP.NET y pueden usar características de ASP.NET como la autorización de archivo/URL, el estado de sesión y la <xref:System.Web.HttpContext> clase.</span><span class="sxs-lookup"><span data-stu-id="9e18e-105">Services running in ASP.NET Compatibility mode participate fully in the ASP.NET application pipeline and can make use of ASP.NET features such as file/URL authorization, session state, and the <xref:System.Web.HttpContext> class.</span></span> <span data-ttu-id="9e18e-106">La <xref:System.Web.HttpContext> clase permite el acceso a las cookies, las sesiones y otras características de ASP.net.</span><span class="sxs-lookup"><span data-stu-id="9e18e-106">The <xref:System.Web.HttpContext> class allows access to cookies, sessions, and other ASP.NET features.</span></span> <span data-ttu-id="9e18e-107">Este modo requiere que los enlaces utilicen el transporte HTTP y el propio servicio se debe hospedar en IIS.</span><span class="sxs-lookup"><span data-stu-id="9e18e-107">This mode requires that the bindings use the HTTP transport and the service itself must be hosted in IIS.</span></span>

<span data-ttu-id="9e18e-108">En este ejemplo, el cliente es una aplicación de consola (un ejecutable) e Internet Information Servers (IIS) hospeda el servicio.</span><span class="sxs-lookup"><span data-stu-id="9e18e-108">In this sample, the client is a console application (an executable) and the service is hosted in Internet Information Services (IIS).</span></span>

> [!NOTE]
> <span data-ttu-id="9e18e-109">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="9e18e-109">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>

<span data-ttu-id="9e18e-110">Este ejemplo requiere un grupo de aplicaciones de .NET Framework 4 para poder ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="9e18e-110">This sample requires a .NET Framework 4 application pool in order to run.</span></span> <span data-ttu-id="9e18e-111">Para crear un nuevo grupo de aplicaciones o modificar el grupo de aplicaciones predeterminado, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="9e18e-111">To create a new application pool, or to modify the default application pool, follow these steps.</span></span>

1. <span data-ttu-id="9e18e-112">Abra el **Panel de control**.</span><span class="sxs-lookup"><span data-stu-id="9e18e-112">Open **Control Panel**.</span></span>  <span data-ttu-id="9e18e-113">Abra el applet **herramientas administrativas** en el encabezado **sistema y seguridad** .</span><span class="sxs-lookup"><span data-stu-id="9e18e-113">Open the **Administrative Tools** applet under the **System and Security** heading.</span></span> <span data-ttu-id="9e18e-114">Abra el applet **Administrador de Internet Information Services (IIS)** .</span><span class="sxs-lookup"><span data-stu-id="9e18e-114">Open the **Internet Information Services (IIS) Manager** applet.</span></span>

2. <span data-ttu-id="9e18e-115">Expanda la vista de árbol en el panel **conexiones** .</span><span class="sxs-lookup"><span data-stu-id="9e18e-115">Expand the treeview in the **Connections** pane.</span></span> <span data-ttu-id="9e18e-116">Seleccione el nodo **grupos de aplicaciones** .</span><span class="sxs-lookup"><span data-stu-id="9e18e-116">Select the **Application Pools** node.</span></span>

3. <span data-ttu-id="9e18e-117">Para establecer que el grupo de aplicaciones predeterminado use .NET Framework 4 (lo que puede provocar problemas de incompatibilidad con los sitios existentes), haga clic con el botón secundario en el elemento de lista **DefaultAppPool** y seleccione **configuración básica.**...</span><span class="sxs-lookup"><span data-stu-id="9e18e-117">To set the default application pool to use .NET Framework 4 (which may cause incompatibility problems with existing sites), right-click the **DefaultAppPool** list item and select **Basic Settings…**.</span></span> <span data-ttu-id="9e18e-118">Establezca la desactivación de la **versión de .NET Framework** en **.NET Framework v 4.0.30128** (o posterior).</span><span class="sxs-lookup"><span data-stu-id="9e18e-118">Set the **.Net Framework Version** pull-down to **.Net Framework v4.0.30128** (or later).</span></span>

4. <span data-ttu-id="9e18e-119">Para crear un nuevo grupo de aplicaciones que use .NET Framework 4 (para conservar la compatibilidad con otras aplicaciones), haga clic con el botón secundario en el nodo **grupos de aplicaciones** y seleccione **Agregar grupo de aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="9e18e-119">To create a new application pool that uses .NET Framework 4 (to preserve compatibility for other applications), right-click the **Application Pools** node and select **Add Application Pool…**.</span></span> <span data-ttu-id="9e18e-120">Asigne un nombre al nuevo grupo de aplicaciones y establezca la desactivación de la **versión de .NET Framework** en **.NET Framework v 4.0.30128** (o posterior).</span><span class="sxs-lookup"><span data-stu-id="9e18e-120">Name the new application pool, and set the **.Net Framework Version** pull-down to **.Net Framework v4.0.30128** (or later).</span></span> <span data-ttu-id="9e18e-121">Después de ejecutar los pasos de configuración siguientes, haga clic con el botón derecho en la aplicación **ServiceModelSamples** y seleccione **administrar aplicación**, **Configuración avanzada.**...</span><span class="sxs-lookup"><span data-stu-id="9e18e-121">After running the setup steps below, right-click the **ServiceModelSamples** application and select **Manage Application**, **Advanced Settings…**.</span></span> <span data-ttu-id="9e18e-122">Establezca el **grupo de aplicaciones** en el nuevo grupo de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="9e18e-122">Set the **Application Pool** to the new application pool.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9e18e-123">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="9e18e-123">The samples may already be installed on your computer.</span></span> <span data-ttu-id="9e18e-124">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="9e18e-124">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="9e18e-125">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="9e18e-125">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="9e18e-126">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="9e18e-126">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebHost\ASPNetCompatibility`

<span data-ttu-id="9e18e-127">Este ejemplo se basa en el [Introducción](getting-started-sample.md), que implementa un servicio de calculadora.</span><span class="sxs-lookup"><span data-stu-id="9e18e-127">This sample is based on the [Getting Started](getting-started-sample.md), which implements a calculator service.</span></span> <span data-ttu-id="9e18e-128">El contrato `ICalculator` se ha modificado como contrato`ICalculatorSession` para permitir realizar un conjunto de operaciones, manteniendo un resultado en ejecución.</span><span class="sxs-lookup"><span data-stu-id="9e18e-128">The `ICalculator` contract has been modified as the `ICalculatorSession` contract to allow a set of operations to be performed, while keeping a running result.</span></span>

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

<span data-ttu-id="9e18e-129">El servicio mantiene el estado, utilizando la característica, para cada cliente ya que se llama a varias operaciones de servicio para realizar un cálculo.</span><span class="sxs-lookup"><span data-stu-id="9e18e-129">The service maintains state, using the feature, for each client as multiple service operations are called to perform a calculation.</span></span> <span data-ttu-id="9e18e-130">El cliente puede recuperar el resultado actual llamando a `Result` y borrar el resultado para ponerlo a cero llamando a `Clear`.</span><span class="sxs-lookup"><span data-stu-id="9e18e-130">The client can retrieve the current result by calling `Result` and can clear the result to zero by calling `Clear`.</span></span>

<span data-ttu-id="9e18e-131">El servicio utiliza la sesión ASP.NET para almacenar el resultado de cada sesión de cliente.</span><span class="sxs-lookup"><span data-stu-id="9e18e-131">The service uses the ASP.NET session to store the result for each client session.</span></span> <span data-ttu-id="9e18e-132">Esto permite al servicio mantener el resultado en ejecución para cada cliente por varias llamadas al servicio.</span><span class="sxs-lookup"><span data-stu-id="9e18e-132">This allows the service to maintain the running result for each client across multiple calls to the service.</span></span>

> [!NOTE]
> <span data-ttu-id="9e18e-133">El estado de sesión de ASP.NET y las sesiones de WCF son cosas muy diferentes.</span><span class="sxs-lookup"><span data-stu-id="9e18e-133">ASP.NET session state and WCF sessions are very different things.</span></span> <span data-ttu-id="9e18e-134">Vea la [sesión](session.md) para obtener más información sobre las sesiones de WCF.</span><span class="sxs-lookup"><span data-stu-id="9e18e-134">See [Session](session.md) for details on WCF sessions.</span></span>

<span data-ttu-id="9e18e-135">El servicio tiene una dependencia íntima en el estado de sesión ASP.NET y requiere que el modo de compatibilidad ASP.NET funcione correctamente.</span><span class="sxs-lookup"><span data-stu-id="9e18e-135">The service has an intimate dependency on ASP.NET session state and requires ASP.NET compatibility mode to function correctly.</span></span> <span data-ttu-id="9e18e-136">Estos requisitos se expresan mediante declaración aplicando el atributo `AspNetCompatibilityRequirements`.</span><span class="sxs-lookup"><span data-stu-id="9e18e-136">These requirements are expressed declaratively by applying the `AspNetCompatibilityRequirements` attribute.</span></span>

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

<span data-ttu-id="9e18e-137">Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="9e18e-137">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="9e18e-138">Presione ENTRAR en la ventana de cliente para cerrar el cliente.</span><span class="sxs-lookup"><span data-stu-id="9e18e-138">Press ENTER in the client window to shut down the client.</span></span>

```console
0, + 100, - 50, * 17.65, / 2 = 441.25
Press <ENTER> to terminate client.
```

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="9e18e-139">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="9e18e-139">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="9e18e-140">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="9e18e-140">Be sure you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="9e18e-141">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="9e18e-141">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

3. <span data-ttu-id="9e18e-142">Una vez compilada la solución, ejecute Setup.bat para configurar la aplicación ServiceModelSamples en IIS 7,0.</span><span class="sxs-lookup"><span data-stu-id="9e18e-142">After the solution has been built, run Setup.bat to set up the ServiceModelSamples Application in IIS 7.0.</span></span> <span data-ttu-id="9e18e-143">El directorio ServiceModelSamples debería aparecer ahora como una aplicación de IIS 7,0.</span><span class="sxs-lookup"><span data-stu-id="9e18e-143">The ServiceModelSamples directory should now appear as an IIS 7.0 Application.</span></span>

4. <span data-ttu-id="9e18e-144">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="9e18e-144">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9e18e-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="9e18e-145">See also</span></span>

- <span data-ttu-id="9e18e-146">[Ejemplos de hospedaje y persistencia de AppFabric](/previous-versions/appfabric/ff383418(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="9e18e-146">[AppFabric Hosting and Persistence Samples](/previous-versions/appfabric/ff383418(v=azure.10))</span></span>
