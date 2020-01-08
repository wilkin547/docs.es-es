---
title: SRMP
ms.date: 03/30/2017
ms.assetid: cf37078c-dcb4-45e0-acaf-2f196521b226
ms.openlocfilehash: 1e0290a4df688d39f84086dc4c1b41712f81076a
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75345147"
---
# <a name="srmp"></a><span data-ttu-id="12198-102">SRMP</span><span class="sxs-lookup"><span data-stu-id="12198-102">SRMP</span></span>
<span data-ttu-id="12198-103">Este ejemplo muestra cómo llevar a cabo la comunicación en cola por transacciones utilizando Message Queuing (MSMQ) a través de HTTP.</span><span class="sxs-lookup"><span data-stu-id="12198-103">This sample demonstrates how to perform transacted queued communication by using Message Queuing (MSMQ) over HTTP.</span></span>  
  
 <span data-ttu-id="12198-104">En la comunicación con colas, el cliente se comunica con el servicio mediante una cola.</span><span class="sxs-lookup"><span data-stu-id="12198-104">In queued communication, the client communicates to the service using a queue.</span></span> <span data-ttu-id="12198-105">Más exactamente, el cliente envía los mensajes a una cola.</span><span class="sxs-lookup"><span data-stu-id="12198-105">More precisely, the client sends messages to a queue.</span></span> <span data-ttu-id="12198-106">El servicio recibe los mensajes de la cola.</span><span class="sxs-lookup"><span data-stu-id="12198-106">The service receives messages from the queue.</span></span> <span data-ttu-id="12198-107">El servicio y el cliente no necesitan ejecutarse simultáneamente para comunicarse mediante una cola.</span><span class="sxs-lookup"><span data-stu-id="12198-107">The service and client therefore, do not have to be running at the same time to communicate using a queue.</span></span>  
  
 <span data-ttu-id="12198-108">MSMQ permite al uso de HTTP (incluso el uso de HTTPS) para enviar los mensajes a una cola.</span><span class="sxs-lookup"><span data-stu-id="12198-108">MSMQ enables the use of HTTP (including the use of HTTPS) to send messages to a queue.</span></span> <span data-ttu-id="12198-109">En este ejemplo, se muestra el uso de la comunicación en cola de Windows Communication Foundation (WCF) y cómo enviar mensajes a través de HTTP.</span><span class="sxs-lookup"><span data-stu-id="12198-109">In this example, we demonstrate using Windows Communication Foundation (WCF) queued communication and how to send messages over HTTP.</span></span> <span data-ttu-id="12198-110">MSMQ utiliza un protocolo llamado SRMP, que es un protocolo basado en SOAP para la comunicación sobre HTTP.</span><span class="sxs-lookup"><span data-stu-id="12198-110">MSMQ uses a protocol called SRMP, which is a SOAP-based protocol for communication over HTTP.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="12198-111">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="12198-111">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="12198-112">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="12198-112">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="12198-113">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="12198-113">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="12198-114">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="12198-114">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
4. <span data-ttu-id="12198-115">Antes de ejecutar el ejemplo en **Agregar o quitar componentes de Windows**, asegúrese de que MSMQ está instalado con compatibilidad con http.</span><span class="sxs-lookup"><span data-stu-id="12198-115">Before running the sample in **Add/Remove Windows Components**, ensure that MSMQ is installed with HTTP support.</span></span> <span data-ttu-id="12198-116">Instalando la compatibilidad HTTP se instala automáticamente Internet Information Services (IIS) y se agrega la compatibilidad con protocolos en IIS para MSMQ.</span><span class="sxs-lookup"><span data-stu-id="12198-116">Installing HTTP support automatically installs Internet Information Services (IIS) and adds the protocol support in IIS for MSMQ.</span></span>  
  
5. <span data-ttu-id="12198-117">Si desea asegurarse de que HTTP se utiliza para la comunicación, puede permitirle a MSMQ ejecutarse en modo endurecido.</span><span class="sxs-lookup"><span data-stu-id="12198-117">If you want to be certain that HTTP is used for communication, you can enable MSMQ to run in hardened mode.</span></span> <span data-ttu-id="12198-118">Esto asegurar que ningún mensaje dirigido a cualquier cola hospedada en el equipo puede llegar utilizando cualquier transporte no HTTP.</span><span class="sxs-lookup"><span data-stu-id="12198-118">This ensures that no messages to any queue hosted on the machine can arrive using any non-HTTP transport.</span></span>  
  
6. <span data-ttu-id="12198-119">Después de haber seleccionado MSMQ para que se ejecute en modo protegido, el equipo requiere un reinicio en Windows Server 2003.</span><span class="sxs-lookup"><span data-stu-id="12198-119">After you have selected MSMQ to run in hardened mode, the machine requires a re-boot on Windows Server 2003.</span></span>  
  
7. <span data-ttu-id="12198-120">Ejecute el servicio.</span><span class="sxs-lookup"><span data-stu-id="12198-120">Run the service.</span></span>  
  
8. <span data-ttu-id="12198-121">Ejecute el cliente.</span><span class="sxs-lookup"><span data-stu-id="12198-121">Run the client.</span></span> <span data-ttu-id="12198-122">Aseguúrese de que cambia la dirección del extremo para señalar al nombre de equipo o dirección IP en lugar del host local.</span><span class="sxs-lookup"><span data-stu-id="12198-122">Ensure that you change the endpoint address to point to the machine name or IP address instead of localhost.</span></span> <span data-ttu-id="12198-123">El cliente envía un mensaje y sale.</span><span class="sxs-lookup"><span data-stu-id="12198-123">The client sends a message and exits.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12198-124">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="12198-124">Requirements</span></span>  
 <span data-ttu-id="12198-125">Para ejecutar este ejemplo, IIS se debe instalar en el servicio y en los equipos cliente además de en MSMQ.</span><span class="sxs-lookup"><span data-stu-id="12198-125">To run this sample, IIS must be installed on both the service and the client machines in addition to MSMQ.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="12198-126">Demostraciones</span><span class="sxs-lookup"><span data-stu-id="12198-126">Demonstrates</span></span>  
 <span data-ttu-id="12198-127">En el ejemplo se muestra el envío de mensajes en cola WCF mediante MSMQ sobre HTTP.</span><span class="sxs-lookup"><span data-stu-id="12198-127">The sample demonstrates sending WCF queued messages using MSMQ over HTTP.</span></span> <span data-ttu-id="12198-128">Esto también se denomina mensajería de SRMP.</span><span class="sxs-lookup"><span data-stu-id="12198-128">This is also called SRMP messaging.</span></span> <span data-ttu-id="12198-129">Cuando se envía un mensaje en cola, MSMQ en el equipo emisor transfiere los mensajes al administrador receptor de cola mediante TCP o transporte HTTP.</span><span class="sxs-lookup"><span data-stu-id="12198-129">When a queued message is sent, MSMQ on the sending machine transfers the messages to the receiving queue manager over TCP or HTTP transport.</span></span> <span data-ttu-id="12198-130">Eligiendo SRMP, el usuario indica la opción de HTTP como un transporte para la transferencia de la cola.</span><span class="sxs-lookup"><span data-stu-id="12198-130">By choosing SRMP, the user indicates the choice of HTTP as a transport for queue transfer.</span></span> <span data-ttu-id="12198-131">SRMP Secure habilita el uso de HTTPS.</span><span class="sxs-lookup"><span data-stu-id="12198-131">SRMP Secure enables the use of HTTPS.</span></span>  
  
## <a name="example"></a><span data-ttu-id="12198-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="12198-132">Example</span></span>  
 <span data-ttu-id="12198-133">El código muestra de este ejemplo está basado en el ejemplo de transacción.</span><span class="sxs-lookup"><span data-stu-id="12198-133">The sample code is based on the transacted sample.</span></span> <span data-ttu-id="12198-134">El modo en que se envía un mensaje a la cola y se recibe un mensaje de la cola utilizando SRMP es igual al modo en que se envían y reciben mensajes mediante un protocolo Native.</span><span class="sxs-lookup"><span data-stu-id="12198-134">How you send a message to the queue and receive a message from the queue using SRMP is the same as sending and receiving messages using a Native protocol.</span></span>  
  
 <span data-ttu-id="12198-135">La configuración para el cliente se cambia para indicar la opción del protocolo de transferencia de la cola.</span><span class="sxs-lookup"><span data-stu-id="12198-135">The configuration for the client is changed to indicate the choice of the queue transfer protocol.</span></span> <span data-ttu-id="12198-136">El protocolo de transferencia de la cola puede ser uno de Nativo, SRMP o SrmpSecure.</span><span class="sxs-lookup"><span data-stu-id="12198-136">The queue transfer protocol can be one of Native, SRMP or SrmpSecure.</span></span> <span data-ttu-id="12198-137">De forma predeterminada, el protocolo de transferencia es Nativo.</span><span class="sxs-lookup"><span data-stu-id="12198-137">By default, the transfer protocol is Native.</span></span> <span data-ttu-id="12198-138">El cliente y el servicio se especifican en la configuración para utilizar SRMP en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="12198-138">The client and service specify in the configuration to use SRMP in this example.</span></span>  
  
 <span data-ttu-id="12198-139">Hay respecto a limitaciones a SRMP la seguridad de transporte.</span><span class="sxs-lookup"><span data-stu-id="12198-139">There are limitations to SRMP in relation to transport security.</span></span> <span data-ttu-id="12198-140">La seguridad de transporte de MSMQ predeterminada requiere Active Directory, que a su vez requiere que el administrador de cola emisor y el administrador de cola receptor residan en el mismo dominio de Windows.</span><span class="sxs-lookup"><span data-stu-id="12198-140">The default MSMQ transport security requires Active Directory that requires that the sending queue manager and the receiving queue manager reside in the same Windows domain.</span></span> <span data-ttu-id="12198-141">Esto no es posible al enviar los mensajes sobre el límite del HTTP.</span><span class="sxs-lookup"><span data-stu-id="12198-141">This is not possible when sending messages over HTTP boundary.</span></span> <span data-ttu-id="12198-142">Como tal, la seguridad de transporte predeterminada no funciona.</span><span class="sxs-lookup"><span data-stu-id="12198-142">As such, the default transport security does not work.</span></span> <span data-ttu-id="12198-143">La seguridad de transporte se debe establecer para Certificar si se desea la seguridad de transporte.</span><span class="sxs-lookup"><span data-stu-id="12198-143">The transport security must be set to Certificate if transport security is desired.</span></span> <span data-ttu-id="12198-144">El modo de seguridad también se puede utilizar para proteger el mensaje.</span><span class="sxs-lookup"><span data-stu-id="12198-144">Message security can also be used to secure the message.</span></span> <span data-ttu-id="12198-145">En este ejemplo, transporte y el modo de seguridad están desactivados para mostrar la mensajería de SRMP.</span><span class="sxs-lookup"><span data-stu-id="12198-145">In this sample, both transport and message security is turned off to illustrate SRMP messaging.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  
  <system.serviceModel>  
  
    <client>  
      <!-- Define NetMsmqEndpoint -->  
      <endpoint name="OrderProcessorEndpoint"  
           address=  
          "net.msmq://localhost/private/ServiceModelSamplesSrmp"   
           bindingConfiguration="srmpBinding"   
           binding="netMsmqBinding"   
           contract="IOrderProcessor" />  
    </client>  
    <bindings>  
      <netMsmqBinding>  
        <binding name="srmpBinding"  
                 queueTransferProtocol="Srmp">  
          <security mode="None" />  
        </binding>  
      </netMsmqBinding>  
    </bindings>  
  </system.serviceModel>  
  
</configuration>  
```  
  
 <span data-ttu-id="12198-146">Al ejecutar el ejemplo, se produce el resultado siguiente.</span><span class="sxs-lookup"><span data-stu-id="12198-146">Running the sample yields the following output.</span></span>  
  
```console  
Processing Purchase Order: 556b70be-31ee-4a3b-8df4-ed5e538015a4   
Customer: somecustomer.com   
OrderDetails   
    Order LineItem: 54 of Blue Widget @unit price: $29.99   
    Order LineItem: 890 of Red Widget @unit price: $45.89   
    Total cost of this order: $42461.56   
    Order status: Pending  
```  
  
> [!IMPORTANT]
> <span data-ttu-id="12198-147">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="12198-147">The samples may already be installed on your machine.</span></span> <span data-ttu-id="12198-148">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="12198-148">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="12198-149">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos de Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="12198-149">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="12198-150">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="12198-150">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\SRMP`  
