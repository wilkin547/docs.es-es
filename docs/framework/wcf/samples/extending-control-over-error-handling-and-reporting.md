---
title: Extensión de control a control de errores y creación de informes
ms.date: 03/30/2017
ms.assetid: 45f996a7-fa00-45cb-9d6f-b368f5778aaa
ms.openlocfilehash: c7ca8d85220d65905bc4d9d220de366c331504a4
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600547"
---
# <a name="extending-control-over-error-handling-and-reporting"></a><span data-ttu-id="93edc-102">Extensión de control a control de errores y creación de informes</span><span class="sxs-lookup"><span data-stu-id="93edc-102">Extending Control Over Error Handling and Reporting</span></span>
<span data-ttu-id="93edc-103">Este ejemplo muestra cómo extender el control sobre el control de errores y los informes de errores en un servicio de Windows Communication Foundation (WCF) mediante la <xref:System.ServiceModel.Dispatcher.IErrorHandler> interfaz.</span><span class="sxs-lookup"><span data-stu-id="93edc-103">This sample demonstrates how to extend control over error handling and error reporting in a Windows Communication Foundation (WCF) service using the <xref:System.ServiceModel.Dispatcher.IErrorHandler> interface.</span></span> <span data-ttu-id="93edc-104">El ejemplo se basa en el [Introducción](getting-started-sample.md) con algún código adicional agregado al servicio para controlar los errores.</span><span class="sxs-lookup"><span data-stu-id="93edc-104">The sample is based on the [Getting Started](getting-started-sample.md) with some additional code added to the service to handle errors.</span></span> <span data-ttu-id="93edc-105">El cliente fuerza varias condiciones de error.</span><span class="sxs-lookup"><span data-stu-id="93edc-105">The client forces several error conditions.</span></span> <span data-ttu-id="93edc-106">El servicio intercepta los errores y los registra en un archivo.</span><span class="sxs-lookup"><span data-stu-id="93edc-106">The service intercepts the errors and logs them in a file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="93edc-107">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="93edc-107">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="93edc-108">Los servicios pueden interceptar los errores, realizar el procesamiento y afectar la forma en que se crean informes sobre errores usando la interfaz <xref:System.ServiceModel.Dispatcher.IErrorHandler>.</span><span class="sxs-lookup"><span data-stu-id="93edc-108">Services can intercept errors, perform processing, and affect how errors are reported using the <xref:System.ServiceModel.Dispatcher.IErrorHandler> interface.</span></span> <span data-ttu-id="93edc-109">La interfaz tiene dos métodos que pueden implementarse: <xref:System.ServiceModel.Dispatcher.IErrorHandler.ProvideFault%28System.Exception%2CSystem.ServiceModel.Channels.MessageVersion%2CSystem.ServiceModel.Channels.Message%40%29> y <xref:System.ServiceModel.Dispatcher.IErrorHandler.HandleError%2A>.</span><span class="sxs-lookup"><span data-stu-id="93edc-109">The interface has two methods that can be implemented: <xref:System.ServiceModel.Dispatcher.IErrorHandler.ProvideFault%28System.Exception%2CSystem.ServiceModel.Channels.MessageVersion%2CSystem.ServiceModel.Channels.Message%40%29> and <xref:System.ServiceModel.Dispatcher.IErrorHandler.HandleError%2A>.</span></span> <span data-ttu-id="93edc-110">El método <xref:System.ServiceModel.Dispatcher.IErrorHandler.ProvideFault%28System.Exception%2CSystem.ServiceModel.Channels.MessageVersion%2CSystem.ServiceModel.Channels.Message%40%29> le permite agregar, modificar o suprimir un mensaje de error que se genera como respuesta a una excepción.</span><span class="sxs-lookup"><span data-stu-id="93edc-110">The <xref:System.ServiceModel.Dispatcher.IErrorHandler.ProvideFault%28System.Exception%2CSystem.ServiceModel.Channels.MessageVersion%2CSystem.ServiceModel.Channels.Message%40%29> method allows you to add, modify, or suppress a fault message that is generated in response to an exception.</span></span> <span data-ttu-id="93edc-111">El método <xref:System.ServiceModel.Dispatcher.IErrorHandler.HandleError%2A> permite que tenga lugar el procesamiento de errores en el caso de un error y controla si se puede ejecutar el control de errores adicional.</span><span class="sxs-lookup"><span data-stu-id="93edc-111">The <xref:System.ServiceModel.Dispatcher.IErrorHandler.HandleError%2A> method allows error processing to take place in the event of an error and controls whether additional error handling can run.</span></span>  
  
 <span data-ttu-id="93edc-112">En este ejemplo, el tipo `CalculatorErrorHandler` implementa la interfaz <xref:System.ServiceModel.Dispatcher.IErrorHandler>.</span><span class="sxs-lookup"><span data-stu-id="93edc-112">In this sample, the `CalculatorErrorHandler` type implements the <xref:System.ServiceModel.Dispatcher.IErrorHandler> interface.</span></span> <span data-ttu-id="93edc-113">En el campo </span><span class="sxs-lookup"><span data-stu-id="93edc-113">In the</span></span>  
  
 <span data-ttu-id="93edc-114"><xref:System.ServiceModel.Dispatcher.IErrorHandler.HandleError%2A>, `CalculatorErrorHandler` escribe un registro del error en un archivo de texto Error.txt en c:\logs.</span><span class="sxs-lookup"><span data-stu-id="93edc-114"><xref:System.ServiceModel.Dispatcher.IErrorHandler.HandleError%2A> method, the `CalculatorErrorHandler` writes a log of the error to an Error.txt text file in c:\logs.</span></span> <span data-ttu-id="93edc-115">Observe que el ejemplo registra el error y no lo suprime, permitiendo que se cree un informe en el cliente.</span><span class="sxs-lookup"><span data-stu-id="93edc-115">Note that the sample logs the fault and does not suppress it, allowing it to be reported back to the client.</span></span>  
  
```csharp
public class CalculatorErrorHandler : IErrorHandler
{
    // Provide a fault. The Message fault parameter can be replaced, or set to
    // null to suppress reporting a fault.

    public void ProvideFault(Exception error, MessageVersion version, ref Message fault)
    {
    }

    // HandleError. Log an error, then allow the error to be handled as usual.
    // Return true if the error is considered as already handled

    public bool HandleError(Exception error)
    {
        using (TextWriter tw = File.AppendText(@"c:\logs\error.txt"))
        {
            if (error != null)
            {
                tw.WriteLine("Exception: " + error.GetType().Name + " - " + error.Message);
            }
            tw.Close();
        }
        return true;
    }
}  
```  
  
 <span data-ttu-id="93edc-116">`ErrorBehaviorAttribute` existe como mecanismo para registrar un controlador de errores con un servicio.</span><span class="sxs-lookup"><span data-stu-id="93edc-116">The `ErrorBehaviorAttribute` exists as a mechanism to register an error handler with a service.</span></span> <span data-ttu-id="93edc-117">Este atributo toma un parámetro de tipo único.</span><span class="sxs-lookup"><span data-stu-id="93edc-117">This attribute takes a single type parameter.</span></span> <span data-ttu-id="93edc-118">Ese tipo debería implementar la interfaz <xref:System.ServiceModel.Dispatcher.IErrorHandler> y tener un constructor público y vacío.</span><span class="sxs-lookup"><span data-stu-id="93edc-118">That type should implement the <xref:System.ServiceModel.Dispatcher.IErrorHandler> interface and should have a public, empty constructor.</span></span> <span data-ttu-id="93edc-119">El atributo crea instancias de una instancia de ese tipo de controlador de errores y lo instala en el servicio.</span><span class="sxs-lookup"><span data-stu-id="93edc-119">The attribute then instantiates an instance of that error handler type and installs it into the service.</span></span> <span data-ttu-id="93edc-120">Hace esto implementando la interfaz <xref:System.ServiceModel.Description.IServiceBehavior> y utilizando el método <xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A> para agregar instancias del controlador de errores al servicio.</span><span class="sxs-lookup"><span data-stu-id="93edc-120">It does this by implementing the <xref:System.ServiceModel.Description.IServiceBehavior> interface and then using the <xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A> method to add instances of the error handler to the service.</span></span>  
  
```csharp
// This attribute can be used to install a custom error handler for a service.  
public class ErrorBehaviorAttribute : Attribute, IServiceBehavior  
{  
    Type errorHandlerType;  
  
    public ErrorBehaviorAttribute(Type errorHandlerType)  
    {  
        this.errorHandlerType = errorHandlerType;  
    }  
  
    void IServiceBehavior.Validate(ServiceDescription description, ServiceHostBase serviceHostBase)  
    {  
    }  
  
    void IServiceBehavior.AddBindingParameters(ServiceDescription description, ServiceHostBase serviceHostBase, System.Collections.ObjectModel.Collection<ServiceEndpoint> endpoints, BindingParameterCollection parameters)  
    {  
    }  
  
    void IServiceBehavior.ApplyDispatchBehavior(ServiceDescription description, ServiceHostBase serviceHostBase)  
    {  
        IErrorHandler errorHandler;  
  
        try  
        {  
            errorHandler = (IErrorHandler)Activator.CreateInstance(errorHandlerType);  
        }  
        catch (MissingMethodException e)  
        {  
            throw new ArgumentException("The errorHandlerType specified in the ErrorBehaviorAttribute constructor must have a public empty constructor.", e);  
        }  
        catch (InvalidCastException e)  
        {  
            throw new ArgumentException("The errorHandlerType specified in the ErrorBehaviorAttribute constructor must implement System.ServiceModel.Dispatcher.IErrorHandler.", e);  
        }  
  
        foreach (ChannelDispatcherBase channelDispatcherBase in serviceHostBase.ChannelDispatchers)  
        {  
            ChannelDispatcher channelDispatcher = channelDispatcherBase as ChannelDispatcher;  
            channelDispatcher.ErrorHandlers.Add(errorHandler);  
        }
    }  
}  
```  
  
 <span data-ttu-id="93edc-121">El ejemplo implementa un servicio de calculadora.</span><span class="sxs-lookup"><span data-stu-id="93edc-121">The sample implements a calculator service.</span></span> <span data-ttu-id="93edc-122">El cliente hace que se produzcan dos errores de manera deliberada en el servicio proporcionando parámetros con valores no válidos.</span><span class="sxs-lookup"><span data-stu-id="93edc-122">The client deliberately causes two errors to occur on the service by providing parameters with illegal values.</span></span> <span data-ttu-id="93edc-123">`CalculatorErrorHandler` utiliza la interfaz <xref:System.ServiceModel.Dispatcher.IErrorHandler> para registrar los errores en un archivo local y, a continuación, informar de ellos al cliente.</span><span class="sxs-lookup"><span data-stu-id="93edc-123">The `CalculatorErrorHandler` uses the <xref:System.ServiceModel.Dispatcher.IErrorHandler> interface to log the errors to a local file and then allows them to be reported back to the client.</span></span> <span data-ttu-id="93edc-124">El cliente fuerza una división por cero y una condición de argumento fuera de intervalo.</span><span class="sxs-lookup"><span data-stu-id="93edc-124">The client forces a divide by zero and an argument-out-of-range condition.</span></span>  
  
```csharp
try
{  
    Console.WriteLine("Forcing an error in Divide");  
    // Call the Divide service operation - trigger a divide by 0 error.  
    value1 = 22;  
    value2 = 0;  
    result = proxy.Divide(value1, value2);  
    Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result);  
}  
catch (FaultException e)  
{  
    Console.WriteLine("FaultException: " + e.GetType().Name + " - " + e.Message);  
}  
catch (Exception e)  
{  
    Console.WriteLine("Exception: " + e.GetType().Name + " - " + e.Message);  
}  
```  
  
 <span data-ttu-id="93edc-125">Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="93edc-125">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="93edc-126">Ve la división por cero y las condiciones del argumento fuera del intervalo que aparecen en el informe como errores.</span><span class="sxs-lookup"><span data-stu-id="93edc-126">You see the division by zero and the argument-out-of-range conditions being reported as faults.</span></span> <span data-ttu-id="93edc-127">Presione ENTRAR en la ventana de cliente para cerrar el cliente.</span><span class="sxs-lookup"><span data-stu-id="93edc-127">Press ENTER in the client window to shut down the client.</span></span>  
  
```console  
Add(15,3) = 18  
Subtract(145,76) = 69  
Multiply(9,81) = 729  
Forcing an error in Divide  
FaultException: FaultException - Invalid Argument: The second argument must not be zero.  
Forcing an error in Factorial  
FaultException: FaultException - Invalid Argument: The argument must be greater than zero.  
  
Press <ENTER> to terminate client.  
```  
  
 <span data-ttu-id="93edc-128">El archivo c:\logs\errors.txt contiene la información registrada sobre los errores por el servicio.</span><span class="sxs-lookup"><span data-stu-id="93edc-128">The file c:\logs\errors.txt contains the information logged about the errors by the service.</span></span> <span data-ttu-id="93edc-129">Tenga en cuenta que para que el servicio escriba en el directorio, debe asegurarse de que el proceso en el que se ejecuta el servicio (por lo general, ASP.NET o servicio de red) tiene permiso para escribir en el directorio.</span><span class="sxs-lookup"><span data-stu-id="93edc-129">Note that for the service to write to the directory you must make sure that the process under which the service is running (typically ASP.NET or Network Service) has permission to write to the directory.</span></span>  
  
```txt
Fault: Reason = Invalid Argument: The second argument must not be zero.  
Fault: Reason = Invalid Argument: The argument must be greater than zero.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="93edc-130">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="93edc-130">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="93edc-131">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="93edc-131">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="93edc-132">Para compilar la solución, siga las instrucciones de [creación de los ejemplos de Windows Communication Foundation](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="93edc-132">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="93edc-133">Asegúrese de que ha creado el directorio c:\logs para el archivo error.txt.</span><span class="sxs-lookup"><span data-stu-id="93edc-133">Ensure you have created the c:\logs directory for the error.txt file.</span></span> <span data-ttu-id="93edc-134">O modifique el nombre de archivo utilizado en `CalculatorErrorHandler.HandleError`.</span><span class="sxs-lookup"><span data-stu-id="93edc-134">Or modify the file name used in `CalculatorErrorHandler.HandleError`.</span></span>  
  
4. <span data-ttu-id="93edc-135">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="93edc-135">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="93edc-136">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="93edc-136">The samples may already be installed on your machine.</span></span> <span data-ttu-id="93edc-137">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="93edc-137">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="93edc-138">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="93edc-138">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="93edc-139">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="93edc-139">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\ErrorHandling`  
