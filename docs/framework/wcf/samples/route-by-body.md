---
title: Enrutamiento por cuerpo
ms.date: 03/30/2017
ms.assetid: 07a6fc3b-c360-42e0-b663-3d0f22cf4502
ms.openlocfilehash: 5b6a9ec6c862e501e6d04c27391a601a7cf6e66a
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716373"
---
# <a name="route-by-body"></a><span data-ttu-id="70a4d-102">Enrutamiento por cuerpo</span><span class="sxs-lookup"><span data-stu-id="70a4d-102">Route by Body</span></span>
<span data-ttu-id="70a4d-103">Este ejemplo muestra cómo implementar un servicio que acepta los objetos de mensaje con cualquier acción SOAP.</span><span class="sxs-lookup"><span data-stu-id="70a4d-103">This sample demonstrates how to implement a service that accepts message objects with any SOAP action.</span></span> <span data-ttu-id="70a4d-104">Este ejemplo se basa en el [Introducción](../../../../docs/framework/wcf/samples/getting-started-sample.md) que implementa un servicio de calculadora.</span><span class="sxs-lookup"><span data-stu-id="70a4d-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) that implements a calculator service.</span></span> <span data-ttu-id="70a4d-105">El servicio implementa una operación `Calculate` única que acepta un parámetro de solicitud <xref:System.ServiceModel.Channels.Message> y devuelve una respuesta <xref:System.ServiceModel.Channels.Message>.</span><span class="sxs-lookup"><span data-stu-id="70a4d-105">The service implements a single `Calculate` operation that accepts a <xref:System.ServiceModel.Channels.Message> request parameter and returns a <xref:System.ServiceModel.Channels.Message> response.</span></span>  
  
 <span data-ttu-id="70a4d-106">En este ejemplo, el cliente es una aplicación de consola (.exe) y el servicio se hospeda en IIS.</span><span class="sxs-lookup"><span data-stu-id="70a4d-106">In this sample, the client is a console application (.exe) and the service is hosted in IIS.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="70a4d-107">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="70a4d-107">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="70a4d-108">El ejemplo muestra el envío de mensajes según el contenido del cuerpo.</span><span class="sxs-lookup"><span data-stu-id="70a4d-108">The sample demonstrates message dispatch based on the body content.</span></span> <span data-ttu-id="70a4d-109">El mecanismo de envío de mensajes del modelo de servicio Windows Communication Foundation (WCF) integrado se basa en las acciones de mensaje.</span><span class="sxs-lookup"><span data-stu-id="70a4d-109">The built-in Windows Communication Foundation (WCF) service model message dispatch mechanism is based on message Actions.</span></span> <span data-ttu-id="70a4d-110">Sin embargo, hay muchos servicios Web existentes que definen todas sus operaciones con Action="".</span><span class="sxs-lookup"><span data-stu-id="70a4d-110">However, there are many existing Web services that define all of their operations with Action="".</span></span> <span data-ttu-id="70a4d-111">Es imposible compilar un servicio basado en WSDL que siga enviando mensajes de solicitud según la información de Action.</span><span class="sxs-lookup"><span data-stu-id="70a4d-111">It is impossible to build a service based on WSDL that keeps dispatching request messages based on Action information.</span></span> <span data-ttu-id="70a4d-112">Este ejemplo muestra un contrato de servicios basado en WSDL (WSDL está contenido en Service.wsdl, que está incluido con el ejemplo).</span><span class="sxs-lookup"><span data-stu-id="70a4d-112">This sample demonstrates a service contract that is based on WSDL (the WSDL is contained in Service.wsdl that is included with the sample).</span></span> <span data-ttu-id="70a4d-113">El contrato de servicio es una calculadora, similar a la usada en [Introducción](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="70a4d-113">The service contract is Calculator, similar to the one used in [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span> <span data-ttu-id="70a4d-114">Sin embargo, `[OperationContract]` especifica `Action=""` para todas las operaciones.</span><span class="sxs-lookup"><span data-stu-id="70a4d-114">However the `[OperationContract]` specifies `Action=""` for all operations.</span></span>  
  
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
  
 <span data-ttu-id="70a4d-115">Con un contrato, un servicio exige un `DispatchByBodyBehavior` de comportamiento de distribución personalizado para permitir que los mensajes se distribuyan entre operaciones.</span><span class="sxs-lookup"><span data-stu-id="70a4d-115">Given a contract, a service requires custom dispatch behavior `DispatchByBodyBehavior` to allow messages to be dispatched between operations.</span></span> <span data-ttu-id="70a4d-116">Este comportamiento de distribución inicializa el selector de operación personalizado `DispatchByBodyElementOperationSelector` con una tabla de los nombres de operación con clave por QName de elementos contenedores respectivos.</span><span class="sxs-lookup"><span data-stu-id="70a4d-116">This dispatch behavior initializes the `DispatchByBodyElementOperationSelector` custom operation selector with a table of the operation names keyed by QName of respective wrapper elements.</span></span> <span data-ttu-id="70a4d-117">`DispatchByBodyElementOperationSelector` busca en la etiqueta de inicio del primer elemento secundario del cuerpo y selecciona la operación usando la tabla mencionada previamente.</span><span class="sxs-lookup"><span data-stu-id="70a4d-117">`DispatchByBodyElementOperationSelector` looks at the start tag of the first child of the Body and selects the operation using the table previously mentioned.</span></span>  
  
 <span data-ttu-id="70a4d-118">El cliente utiliza un proxy generado automáticamente a partir del WSDL exportado por el servicio mediante la [herramienta de utilidad de metadatos de ServiceModel (SvcUtil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="70a4d-118">The client uses a proxy auto-generated from the WSDL exported by the service using [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span>  
  
```console  
svcutil.exe  /n:http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples /uxs http://localhost/servicemodelsamples/service.svc?wsdl /out:generatedProxy.cs  
```  
  
 <span data-ttu-id="70a4d-119">El hecho de que las acciones de todas las operaciones estén vacías no tiene ningún impacto en el código de cliente, salvo los parámetros Action en el proxy generado automáticamente.</span><span class="sxs-lookup"><span data-stu-id="70a4d-119">The fact that actions of all operations are empty has no impact on the client code, except for the Action parameters in the auto-generated proxy.</span></span>  
  
 <span data-ttu-id="70a4d-120">El código de cliente realiza varios cálculos.</span><span class="sxs-lookup"><span data-stu-id="70a4d-120">The client code performs several calculations.</span></span> <span data-ttu-id="70a4d-121">Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="70a4d-121">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="70a4d-122">Presione ENTRAR en la ventana de cliente para cerrar el cliente.</span><span class="sxs-lookup"><span data-stu-id="70a4d-122">Press ENTER in the client window to shut down the client.</span></span>  
  
```console
Add(100, 15.99) = 115.99  
Subtract(145, 76.54) = 68.46  
Multiply(9, 81.25) = 731.25  
Divide(22, 7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="70a4d-123">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="70a4d-123">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="70a4d-124">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="70a4d-124">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="70a4d-125">Para compilar la solución, siga las instrucciones de [creación de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="70a4d-125">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="70a4d-126">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="70a4d-126">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="70a4d-127">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="70a4d-127">The samples may already be installed on your machine.</span></span> <span data-ttu-id="70a4d-128">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="70a4d-128">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="70a4d-129">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos de Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="70a4d-129">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="70a4d-130">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="70a4d-130">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Interop\RouteByBody`  
