---
title: Enrutamiento por cuerpo
ms.date: 03/30/2017
ms.assetid: 07a6fc3b-c360-42e0-b663-3d0f22cf4502
ms.openlocfilehash: 146baf806f4922f5e3ddd92a762772786e61d443
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594600"
---
# <a name="route-by-body"></a><span data-ttu-id="76b41-102">Enrutamiento por cuerpo</span><span class="sxs-lookup"><span data-stu-id="76b41-102">Route by Body</span></span>
<span data-ttu-id="76b41-103">Este ejemplo muestra cómo implementar un servicio que acepta los objetos de mensaje con cualquier acción SOAP.</span><span class="sxs-lookup"><span data-stu-id="76b41-103">This sample demonstrates how to implement a service that accepts message objects with any SOAP action.</span></span> <span data-ttu-id="76b41-104">Este ejemplo se basa en el [Introducción](getting-started-sample.md) que implementa un servicio de calculadora.</span><span class="sxs-lookup"><span data-stu-id="76b41-104">This sample is based on the [Getting Started](getting-started-sample.md) that implements a calculator service.</span></span> <span data-ttu-id="76b41-105">El servicio implementa una operación `Calculate` única que acepta un parámetro de solicitud <xref:System.ServiceModel.Channels.Message> y devuelve una respuesta <xref:System.ServiceModel.Channels.Message>.</span><span class="sxs-lookup"><span data-stu-id="76b41-105">The service implements a single `Calculate` operation that accepts a <xref:System.ServiceModel.Channels.Message> request parameter and returns a <xref:System.ServiceModel.Channels.Message> response.</span></span>  
  
 <span data-ttu-id="76b41-106">En este ejemplo, el cliente es una aplicación de consola (.exe) y el servicio se hospeda en IIS.</span><span class="sxs-lookup"><span data-stu-id="76b41-106">In this sample, the client is a console application (.exe) and the service is hosted in IIS.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="76b41-107">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="76b41-107">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="76b41-108">El ejemplo muestra el envío de mensajes según el contenido del cuerpo.</span><span class="sxs-lookup"><span data-stu-id="76b41-108">The sample demonstrates message dispatch based on the body content.</span></span> <span data-ttu-id="76b41-109">El mecanismo de envío de mensajes del modelo de servicio Windows Communication Foundation (WCF) integrado se basa en las acciones de mensaje.</span><span class="sxs-lookup"><span data-stu-id="76b41-109">The built-in Windows Communication Foundation (WCF) service model message dispatch mechanism is based on message Actions.</span></span> <span data-ttu-id="76b41-110">Sin embargo, hay muchos servicios Web existentes que definen todas sus operaciones con Action="".</span><span class="sxs-lookup"><span data-stu-id="76b41-110">However, there are many existing Web services that define all of their operations with Action="".</span></span> <span data-ttu-id="76b41-111">Es imposible compilar un servicio basado en WSDL que siga enviando mensajes de solicitud según la información de Action.</span><span class="sxs-lookup"><span data-stu-id="76b41-111">It is impossible to build a service based on WSDL that keeps dispatching request messages based on Action information.</span></span> <span data-ttu-id="76b41-112">Este ejemplo muestra un contrato de servicios basado en WSDL (WSDL está contenido en Service.wsdl, que está incluido con el ejemplo).</span><span class="sxs-lookup"><span data-stu-id="76b41-112">This sample demonstrates a service contract that is based on WSDL (the WSDL is contained in Service.wsdl that is included with the sample).</span></span> <span data-ttu-id="76b41-113">El contrato de servicio es una calculadora, similar a la usada en [Introducción](getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="76b41-113">The service contract is Calculator, similar to the one used in [Getting Started](getting-started-sample.md).</span></span> <span data-ttu-id="76b41-114">Sin embargo, `[OperationContract]` especifica `Action=""` para todas las operaciones.</span><span class="sxs-lookup"><span data-stu-id="76b41-114">However the `[OperationContract]` specifies `Action=""` for all operations.</span></span>  
  
```csharp  
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples"),
                 XmlSerializerFormat, DispatchByBodyBehavior]  
    public interface ICalculator  
    {  
        [OperationContract(Action="")]  
        double Add(double n1, double n2);  
        [OperationContract(Action = "")]  
        double Subtract(double n1, double n2);  
        [OperationContract(Action = "")]  
        double Multiply(double n1, double n2);  
        [OperationContract(Action = "")]  
        double Divide(double n1, double n2);  
    }  
```  
  
 <span data-ttu-id="76b41-115">Con un contrato, un servicio exige un `DispatchByBodyBehavior` de comportamiento de distribución personalizado para permitir que los mensajes se distribuyan entre operaciones.</span><span class="sxs-lookup"><span data-stu-id="76b41-115">Given a contract, a service requires custom dispatch behavior `DispatchByBodyBehavior` to allow messages to be dispatched between operations.</span></span> <span data-ttu-id="76b41-116">Este comportamiento de distribución inicializa el `DispatchByBodyElementOperationSelector` selector de operación personalizado con una tabla de los nombres de operación con clave por QName de elementos contenedores respectivos.</span><span class="sxs-lookup"><span data-stu-id="76b41-116">This dispatch behavior initializes the `DispatchByBodyElementOperationSelector` custom operation selector with a table of the operation names keyed by QName of respective wrapper elements.</span></span> <span data-ttu-id="76b41-117">`DispatchByBodyElementOperationSelector` busca en la etiqueta de inicio del primer elemento secundario del cuerpo y selecciona la operación usando la tabla mencionada previamente.</span><span class="sxs-lookup"><span data-stu-id="76b41-117">`DispatchByBodyElementOperationSelector` looks at the start tag of the first child of the Body and selects the operation using the table previously mentioned.</span></span>  
  
 <span data-ttu-id="76b41-118">El cliente utiliza un proxy generado automáticamente a partir del WSDL exportado por el servicio mediante la [herramienta de utilidad de metadatos de ServiceModel (SvcUtil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="76b41-118">The client uses a proxy auto-generated from the WSDL exported by the service using [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span>  
  
```console  
svcutil.exe  /n:http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples /uxs http://localhost/servicemodelsamples/service.svc?wsdl /out:generatedProxy.cs  
```  
  
 <span data-ttu-id="76b41-119">El hecho de que las acciones de todas las operaciones estén vacías no tiene ningún impacto en el código de cliente, salvo los parámetros Action en el proxy generado automáticamente.</span><span class="sxs-lookup"><span data-stu-id="76b41-119">The fact that actions of all operations are empty has no impact on the client code, except for the Action parameters in the auto-generated proxy.</span></span>  
  
 <span data-ttu-id="76b41-120">El código de cliente realiza varios cálculos.</span><span class="sxs-lookup"><span data-stu-id="76b41-120">The client code performs several calculations.</span></span> <span data-ttu-id="76b41-121">Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="76b41-121">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="76b41-122">Presione ENTRAR en la ventana de cliente para cerrar el cliente.</span><span class="sxs-lookup"><span data-stu-id="76b41-122">Press ENTER in the client window to shut down the client.</span></span>  
  
```console
Add(100, 15.99) = 115.99  
Subtract(145, 76.54) = 68.46  
Multiply(9, 81.25) = 731.25  
Divide(22, 7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="76b41-123">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="76b41-123">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="76b41-124">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="76b41-124">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="76b41-125">Para compilar la solución, siga las instrucciones de [creación de los ejemplos de Windows Communication Foundation](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="76b41-125">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="76b41-126">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="76b41-126">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="76b41-127">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="76b41-127">The samples may already be installed on your machine.</span></span> <span data-ttu-id="76b41-128">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="76b41-128">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="76b41-129">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="76b41-129">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="76b41-130">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="76b41-130">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Interop\RouteByBody`  
