---
title: Compatibilidad de ASP.NET
ms.date: 03/30/2017
ms.assetid: c8b51f1e-c096-4c42-ad99-0519887bbbc5
ms.openlocfilehash: 1f1690cdd1a880c852abc04ea8e4958bae2c5432
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728023"
---
# <a name="aspnet-compatibility"></a><span data-ttu-id="c3aa9-102">Compatibilidad de ASP.NET</span><span class="sxs-lookup"><span data-stu-id="c3aa9-102">ASP.NET Compatibility</span></span>

<span data-ttu-id="c3aa9-103">Este ejemplo muestra cómo habilitar el modo de compatibilidad de ASP.NET en Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="c3aa9-103">This sample demonstrates how to enable ASP.NET Compatibility mode in Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="c3aa9-104">Los servicios que se ejecutan en modo de compatibilidad ASP.NET participan completamente en la canalización de la aplicación ASP.NET y pueden usar características de ASP.NET como la autorización de archivo/URL, el estado de sesión y la clase <xref:System.Web.HttpContext>.</span><span class="sxs-lookup"><span data-stu-id="c3aa9-104">Services running in ASP.NET Compatibility mode participate fully in the ASP.NET application pipeline and can make use of ASP.NET features such as file/URL authorization, session state, and the <xref:System.Web.HttpContext> class.</span></span> <span data-ttu-id="c3aa9-105">La clase <xref:System.Web.HttpContext> permite el acceso a las cookies, las sesiones y otras características de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="c3aa9-105">The <xref:System.Web.HttpContext> class allows access to cookies, sessions, and other ASP.NET features.</span></span> <span data-ttu-id="c3aa9-106">Este modo requiere que los enlaces utilicen el transporte HTTP y el propio servicio se debe hospedar en IIS.</span><span class="sxs-lookup"><span data-stu-id="c3aa9-106">This mode requires that the bindings use the HTTP transport and the service itself must be hosted in IIS.</span></span>

<span data-ttu-id="c3aa9-107">En este ejemplo, el cliente es una aplicación de consola (un ejecutable) e Internet Information Servers (IIS) hospeda el servicio.</span><span class="sxs-lookup"><span data-stu-id="c3aa9-107">In this sample, the client is a console application (an executable) and the service is hosted in Internet Information Services (IIS).</span></span>

> [!NOTE]
> <span data-ttu-id="c3aa9-108">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="c3aa9-108">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>

<span data-ttu-id="c3aa9-109">Este ejemplo requiere un grupo de aplicaciones de .NET Framework 4 para poder ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="c3aa9-109">This sample requires a .NET Framework 4 application pool in order to run.</span></span> <span data-ttu-id="c3aa9-110">Para crear un nuevo grupo de aplicaciones o modificar el grupo de aplicaciones predeterminado, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="c3aa9-110">To create a new application pool, or to modify the default application pool, follow these steps.</span></span>

1. <span data-ttu-id="c3aa9-111">Abra el **Panel de control**.</span><span class="sxs-lookup"><span data-stu-id="c3aa9-111">Open **Control Panel**.</span></span>  <span data-ttu-id="c3aa9-112">Abra el applet **herramientas administrativas** en el encabezado **sistema y seguridad** .</span><span class="sxs-lookup"><span data-stu-id="c3aa9-112">Open the **Administrative Tools** applet under the **System and Security** heading.</span></span> <span data-ttu-id="c3aa9-113">Abra el applet **Administrador de Internet Information Services (IIS)** .</span><span class="sxs-lookup"><span data-stu-id="c3aa9-113">Open the **Internet Information Services (IIS) Manager** applet.</span></span>

2. <span data-ttu-id="c3aa9-114">Expanda la vista de árbol en el panel **conexiones** .</span><span class="sxs-lookup"><span data-stu-id="c3aa9-114">Expand the treeview in the **Connections** pane.</span></span> <span data-ttu-id="c3aa9-115">Seleccione el nodo **grupos de aplicaciones** .</span><span class="sxs-lookup"><span data-stu-id="c3aa9-115">Select the **Application Pools** node.</span></span>

3. <span data-ttu-id="c3aa9-116">Para establecer que el grupo de aplicaciones predeterminado use .NET Framework 4 (lo que puede provocar problemas de incompatibilidad con los sitios existentes), haga clic con el botón secundario en el elemento de lista **DefaultAppPool** y seleccione **configuración básica.** ...</span><span class="sxs-lookup"><span data-stu-id="c3aa9-116">To set the default application pool to use .NET Framework 4 (which may cause incompatibility problems with existing sites), right-click the **DefaultAppPool** list item and select **Basic Settings…**.</span></span> <span data-ttu-id="c3aa9-117">Establezca la desactivación de la **versión de .NET Framework** en **.NET Framework v 4.0.30128** (o posterior).</span><span class="sxs-lookup"><span data-stu-id="c3aa9-117">Set the **.Net Framework Version** pull-down to **.Net Framework v4.0.30128** (or later).</span></span>

4. <span data-ttu-id="c3aa9-118">Para crear un nuevo grupo de aplicaciones que use .NET Framework 4 (para conservar la compatibilidad con otras aplicaciones), haga clic con el botón secundario en el nodo **grupos de aplicaciones** y seleccione **Agregar grupo de aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="c3aa9-118">To create a new application pool that uses .NET Framework 4 (to preserve compatibility for other applications), right-click the **Application Pools** node and select **Add Application Pool…**.</span></span> <span data-ttu-id="c3aa9-119">Asigne un nombre al nuevo grupo de aplicaciones y establezca la desactivación de la **versión de .NET Framework** en **.NET Framework v 4.0.30128** (o posterior).</span><span class="sxs-lookup"><span data-stu-id="c3aa9-119">Name the new application pool, and set the **.Net Framework Version** pull-down to **.Net Framework v4.0.30128** (or later).</span></span> <span data-ttu-id="c3aa9-120">Después de ejecutar los pasos de configuración siguientes, haga clic con el botón derecho en la aplicación **ServiceModelSamples** y seleccione **administrar aplicación**, **Configuración avanzada.** ...</span><span class="sxs-lookup"><span data-stu-id="c3aa9-120">After running the setup steps below, right-click the **ServiceModelSamples** application and select **Manage Application**, **Advanced Settings…**.</span></span> <span data-ttu-id="c3aa9-121">Establezca el **grupo de aplicaciones** en el nuevo grupo de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="c3aa9-121">Set the **Application Pool** to the new application pool.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c3aa9-122">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="c3aa9-122">The samples may already be installed on your computer.</span></span> <span data-ttu-id="c3aa9-123">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="c3aa9-123">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="c3aa9-124">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos de Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c3aa9-124">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="c3aa9-125">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="c3aa9-125">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebHost\ASPNetCompatibility`

<span data-ttu-id="c3aa9-126">Este ejemplo se basa en el [Introducción](../../../../docs/framework/wcf/samples/getting-started-sample.md), que implementa un servicio de calculadora.</span><span class="sxs-lookup"><span data-stu-id="c3aa9-126">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md), which implements a calculator service.</span></span> <span data-ttu-id="c3aa9-127">El contrato `ICalculator` se ha modificado como contrato`ICalculatorSession` para permitir realizar un conjunto de operaciones, manteniendo un resultado en ejecución.</span><span class="sxs-lookup"><span data-stu-id="c3aa9-127">The `ICalculator` contract has been modified as the `ICalculatorSession` contract to allow a set of operations to be performed, while keeping a running result.</span></span>

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

<span data-ttu-id="c3aa9-128">El servicio mantiene el estado, utilizando la característica, para cada cliente ya que se llama a varias operaciones de servicio para realizar un cálculo.</span><span class="sxs-lookup"><span data-stu-id="c3aa9-128">The service maintains state, using the feature, for each client as multiple service operations are called to perform a calculation.</span></span> <span data-ttu-id="c3aa9-129">El cliente puede recuperar el resultado actual llamando a `Result` y borrar el resultado para ponerlo a cero llamando a `Clear`.</span><span class="sxs-lookup"><span data-stu-id="c3aa9-129">The client can retrieve the current result by calling `Result` and can clear the result to zero by calling `Clear`.</span></span>

<span data-ttu-id="c3aa9-130">El servicio utiliza la sesión ASP.NET para almacenar el resultado de cada sesión de cliente.</span><span class="sxs-lookup"><span data-stu-id="c3aa9-130">The service uses the ASP.NET session to store the result for each client session.</span></span> <span data-ttu-id="c3aa9-131">Esto permite al servicio mantener el resultado en ejecución para cada cliente por varias llamadas al servicio.</span><span class="sxs-lookup"><span data-stu-id="c3aa9-131">This allows the service to maintain the running result for each client across multiple calls to the service.</span></span>

> [!NOTE]
> <span data-ttu-id="c3aa9-132">El estado de sesión de ASP.NET y las sesiones de WCF son cosas muy diferentes.</span><span class="sxs-lookup"><span data-stu-id="c3aa9-132">ASP.NET session state and WCF sessions are very different things.</span></span> <span data-ttu-id="c3aa9-133">Vea la [sesión](../../../../docs/framework/wcf/samples/session.md) para obtener más información sobre las sesiones de WCF.</span><span class="sxs-lookup"><span data-stu-id="c3aa9-133">See [Session](../../../../docs/framework/wcf/samples/session.md) for details on WCF sessions.</span></span>

<span data-ttu-id="c3aa9-134">El servicio tiene una dependencia íntima en el estado de sesión ASP.NET y requiere que el modo de compatibilidad ASP.NET funcione correctamente.</span><span class="sxs-lookup"><span data-stu-id="c3aa9-134">The service has an intimate dependency on ASP.NET session state and requires ASP.NET compatibility mode to function correctly.</span></span> <span data-ttu-id="c3aa9-135">Estos requisitos se expresan mediante declaración aplicando el atributo `AspNetCompatibilityRequirements`.</span><span class="sxs-lookup"><span data-stu-id="c3aa9-135">These requirements are expressed declaratively by applying the `AspNetCompatibilityRequirements` attribute.</span></span>

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

<span data-ttu-id="c3aa9-136">Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="c3aa9-136">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="c3aa9-137">Presione ENTRAR en la ventana de cliente para cerrar el cliente.</span><span class="sxs-lookup"><span data-stu-id="c3aa9-137">Press ENTER in the client window to shut down the client.</span></span>

```console
0, + 100, - 50, * 17.65, / 2 = 441.25
Press <ENTER> to terminate client.
```

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="c3aa9-138">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="c3aa9-138">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="c3aa9-139">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="c3aa9-139">Be sure you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="c3aa9-140">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="c3aa9-140">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

3. <span data-ttu-id="c3aa9-141">Una vez compilada la solución, ejecute setup. bat para configurar la aplicación ServiceModelSamples en IIS 7,0.</span><span class="sxs-lookup"><span data-stu-id="c3aa9-141">After the solution has been built, run Setup.bat to set up the ServiceModelSamples Application in IIS 7.0.</span></span> <span data-ttu-id="c3aa9-142">El directorio ServiceModelSamples debería aparecer ahora como una aplicación de IIS 7,0.</span><span class="sxs-lookup"><span data-stu-id="c3aa9-142">The ServiceModelSamples directory should now appear as an IIS 7.0 Application.</span></span>

4. <span data-ttu-id="c3aa9-143">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="c3aa9-143">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c3aa9-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="c3aa9-144">See also</span></span>

- <span data-ttu-id="c3aa9-145">[Ejemplos de hospedaje y persistencia de AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ff383418(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="c3aa9-145">[AppFabric Hosting and Persistence Samples](https://docs.microsoft.com/previous-versions/appfabric/ff383418(v=azure.10))</span></span>
