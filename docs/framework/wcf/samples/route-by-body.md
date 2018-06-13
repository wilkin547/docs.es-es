---
title: Enrutamiento por cuerpo
ms.date: 03/30/2017
ms.assetid: 07a6fc3b-c360-42e0-b663-3d0f22cf4502
ms.openlocfilehash: e9a0c947a1dd7ac2a6c7af74baaa072aae67358c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33504239"
---
# <a name="route-by-body"></a><span data-ttu-id="e7bda-102">Enrutamiento por cuerpo</span><span class="sxs-lookup"><span data-stu-id="e7bda-102">Route by Body</span></span>
<span data-ttu-id="e7bda-103">Este ejemplo muestra cómo implementar un servicio que acepta los objetos de mensaje con cualquier acción SOAP.</span><span class="sxs-lookup"><span data-stu-id="e7bda-103">This sample demonstrates how to implement a service that accepts message objects with any SOAP action.</span></span> <span data-ttu-id="e7bda-104">En este ejemplo se basa en el [Introducción](../../../../docs/framework/wcf/samples/getting-started-sample.md) que implementa un servicio de calculadora.</span><span class="sxs-lookup"><span data-stu-id="e7bda-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) that implements a calculator service.</span></span> <span data-ttu-id="e7bda-105">El servicio implementa una operación `Calculate` única que acepta un parámetro de solicitud <xref:System.ServiceModel.Channels.Message> y devuelve una respuesta <xref:System.ServiceModel.Channels.Message>.</span><span class="sxs-lookup"><span data-stu-id="e7bda-105">The service implements a single `Calculate` operation that accepts a <xref:System.ServiceModel.Channels.Message> request parameter and returns a <xref:System.ServiceModel.Channels.Message> response.</span></span>  
  
 <span data-ttu-id="e7bda-106">En este ejemplo, el cliente es una aplicación de consola (.exe) y el servicio se hospeda en IIS.</span><span class="sxs-lookup"><span data-stu-id="e7bda-106">In this sample, the client is a console application (.exe) and the service is hosted in IIS.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e7bda-107">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="e7bda-107">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="e7bda-108">El ejemplo muestra el envío de mensajes según el contenido del cuerpo.</span><span class="sxs-lookup"><span data-stu-id="e7bda-108">The sample demonstrates message dispatch based on the body content.</span></span> <span data-ttu-id="e7bda-109">El mecanismo de envío mensaje integrada del modelo de servicio Windows Communication Foundation (WCF) se basa en las acciones del mensaje.</span><span class="sxs-lookup"><span data-stu-id="e7bda-109">The built-in Windows Communication Foundation (WCF) service model message dispatch mechanism is based on message Actions.</span></span> <span data-ttu-id="e7bda-110">Sin embargo, hay muchos servicios Web existentes que definen todas sus operaciones con Action="".</span><span class="sxs-lookup"><span data-stu-id="e7bda-110">However, there are many existing Web services that define all of their operations with Action="".</span></span> <span data-ttu-id="e7bda-111">Es imposible compilar un servicio basado en WSDL que siga enviando mensajes de solicitud según la información de Action.</span><span class="sxs-lookup"><span data-stu-id="e7bda-111">It is impossible to build a service based on WSDL that keeps dispatching request messages based on Action information.</span></span> <span data-ttu-id="e7bda-112">Este ejemplo muestra un contrato de servicios basado en WSDL (WSDL está contenido en Service.wsdl, que está incluido con el ejemplo).</span><span class="sxs-lookup"><span data-stu-id="e7bda-112">This sample demonstrates a service contract that is based on WSDL (the WSDL is contained in Service.wsdl that is included with the sample).</span></span> <span data-ttu-id="e7bda-113">El contrato de servicio es la Calculadora, similar al utilizado en [Introducción](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="e7bda-113">The service contract is Calculator, similar to the one used in [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span> <span data-ttu-id="e7bda-114">Sin embargo, `[OperationContract]` especifica `Action=""` para todas las operaciones.</span><span class="sxs-lookup"><span data-stu-id="e7bda-114">However the `[OperationContract]` specifies `Action=""` for all operations.</span></span>  
  
```  
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
  
 <span data-ttu-id="e7bda-115">Con un contrato, un servicio exige un `DispatchByBodyBehavior` de comportamiento de distribución personalizado para permitir que los mensajes se distribuyan entre operaciones.</span><span class="sxs-lookup"><span data-stu-id="e7bda-115">Given a contract, a service requires custom dispatch behavior `DispatchByBodyBehavior` to allow messages to be dispatched between operations.</span></span> <span data-ttu-id="e7bda-116">Este comportamiento de distribución inicializa el `DispatchByBodyElementOperationSelector` selector de operaciones personalizado con una tabla de los nombres de operación con clave por QName de elementos contenedores respectivos.</span><span class="sxs-lookup"><span data-stu-id="e7bda-116">This dispatch behavior initializes the `DispatchByBodyElementOperationSelector` custom operation selector with a table of the operation names keyed by QName of respective wrapper elements.</span></span> <span data-ttu-id="e7bda-117">`DispatchByBodyElementOperationSelector` busca en la etiqueta de inicio del primer elemento secundario del cuerpo y selecciona la operación usando la tabla mencionada previamente.</span><span class="sxs-lookup"><span data-stu-id="e7bda-117">`DispatchByBodyElementOperationSelector` looks at the start tag of the first child of the Body and selects the operation using the table previously mentioned.</span></span>  
  
 <span data-ttu-id="e7bda-118">El cliente utiliza un proxy generado automáticamente desde el WSDL exportado mediante el servicio [la herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="e7bda-118">The client uses a proxy auto-generated from the WSDL exported by the service using [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span>  
  
```  
svcutil.exe  /n:http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples /uxs http://localhost/servicemodelsamples/service.svc?wsdl /out:generatedProxy.cs  
```  
  
 <span data-ttu-id="e7bda-119">El hecho de que las acciones de todas las operaciones estén vacías no tiene ningún impacto en el código de cliente, salvo los parámetros Action en el proxy generado automáticamente.</span><span class="sxs-lookup"><span data-stu-id="e7bda-119">The fact that actions of all operations are empty has no impact on the client code, except for the Action parameters in the auto-generated proxy.</span></span>  
  
 <span data-ttu-id="e7bda-120">El código de cliente realiza varios cálculos.</span><span class="sxs-lookup"><span data-stu-id="e7bda-120">The client code performs several calculations.</span></span> <span data-ttu-id="e7bda-121">Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="e7bda-121">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="e7bda-122">Presione ENTRAR en la ventana de cliente para cerrar el cliente.</span><span class="sxs-lookup"><span data-stu-id="e7bda-122">Press ENTER in the client window to shut down the client.</span></span>  
  
```  
Add(100, 15.99) = 115.99  
Subtract(145, 76.54) = 68.46  
Multiply(9, 81.25) = 731.25  
Divide(22, 7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="e7bda-123">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="e7bda-123">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="e7bda-124">Asegúrese de que ha llevado a cabo la [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e7bda-124">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="e7bda-125">Para compilar la solución, siga las instrucciones que aparecen en [compilar los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e7bda-125">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="e7bda-126">Para ejecutar el ejemplo en una configuración de equipo único o de varios, siga las instrucciones de [ejecutando los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e7bda-126">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e7bda-127">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="e7bda-127">The samples may already be installed on your machine.</span></span> <span data-ttu-id="e7bda-128">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="e7bda-128">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="e7bda-129">Si este directorio no existe, vaya a [Windows Communication Foundation (WCF) y ejemplos de Windows Workflow Foundation (WF) para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="e7bda-129">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="e7bda-130">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="e7bda-130">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Interop\RouteByBody`  
  
## <a name="see-also"></a><span data-ttu-id="e7bda-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="e7bda-131">See Also</span></span>
