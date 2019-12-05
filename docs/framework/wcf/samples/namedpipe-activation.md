---
title: Activación NamedPipe
ms.date: 03/30/2017
ms.assetid: f3c0437d-006c-442e-bfb0-6b29216e4e29
ms.openlocfilehash: a562ec51d35af08f49e89b652670e9a57b0f00c2
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837862"
---
# <a name="namedpipe-activation"></a><span data-ttu-id="2edfe-102">Activación NamedPipe</span><span class="sxs-lookup"><span data-stu-id="2edfe-102">NamedPipe Activation</span></span>

<span data-ttu-id="2edfe-103">Este ejemplo muestra cómo hospedar un servicio que utiliza el servicio de activación de procesos de Windows (WAS) para activar un servicio que se comunica a través de las canalizaciones de los nombres.</span><span class="sxs-lookup"><span data-stu-id="2edfe-103">This sample demonstrates hosting a service that uses Windows Process Activation Service (WAS) to activate a service that communicates over names pipes.</span></span> <span data-ttu-id="2edfe-104">Este ejemplo se basa en el [Introducción](../../../../docs/framework/wcf/samples/getting-started-sample.md) y requiere que Windows Vista se ejecute.</span><span class="sxs-lookup"><span data-stu-id="2edfe-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) and requires Windows Vista to run.</span></span>

> [!NOTE]
> <span data-ttu-id="2edfe-105">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="2edfe-105">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2edfe-106">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="2edfe-106">The samples may already be installed on your computer.</span></span> <span data-ttu-id="2edfe-107">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="2edfe-107">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="2edfe-108">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos de Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2edfe-108">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="2edfe-109">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="2edfe-109">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WASHost\NamedPipeActivation`

## <a name="sample-details"></a><span data-ttu-id="2edfe-110">Detalles del ejemplo</span><span class="sxs-lookup"><span data-stu-id="2edfe-110">Sample Details</span></span>

<span data-ttu-id="2edfe-111">El ejemplo está compuesto de un programa (.exe) de consola de cliente y una biblioteca de servicios (.dll) hospedados en un proceso de trabajo activado por el servicio de activación de procesos de Windows (WAS).</span><span class="sxs-lookup"><span data-stu-id="2edfe-111">The sample consists of a client console program (.exe) and a service library (.dll) hosted in a worker process activated by the Windows Process Activation Services (WAS).</span></span> <span data-ttu-id="2edfe-112">La actividad del cliente es visible en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="2edfe-112">Client activity is visible in the console window.</span></span>

<span data-ttu-id="2edfe-113">El servicio implementa un contrato que define un modelo de comunicación de solicitud y respuesta.</span><span class="sxs-lookup"><span data-stu-id="2edfe-113">The service implements a contract that defines a request-reply communication pattern.</span></span> <span data-ttu-id="2edfe-114">La interfaz `ICalculator`, que expone las operaciones matemáticas (Sumar, Restar, Multiplicar y Dividir), define el contrato, tal ycomo se muestra en el código muestra siguiente.</span><span class="sxs-lookup"><span data-stu-id="2edfe-114">The contract is defined by the `ICalculator` interface, which exposes math operations (Add, Subtract, Multiply, and Divide), as shown in the following sample code.</span></span>

```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]
public interface ICalculator
{
    [OperationContract]
    double Add(double n1, double n2);
    [OperationContract]
    double Subtract(double n1, double n2);
    [OperationContract]
    double Multiply(double n1, double n2);
    [OperationContract]
    double Divide(double n1, double n2);
}
```

<span data-ttu-id="2edfe-115">El cliente realiza las solicitudes sincrónicas a una operación matemática determinada y la implementación del servicio calcula y devuelve el resultado adecuado.</span><span class="sxs-lookup"><span data-stu-id="2edfe-115">The client makes synchronous requests to a given math operation and the service implementation calculates and returns the appropriate result.</span></span>

```csharp
// Service class that implements the service contract.
public class CalculatorService : ICalculator
{
    public double Add(double n1, double n2)
    {
        return n1 + n2;
    }
    public double Subtract(double n1, double n2)
    {
        return n1 - n2;
    }
    public double Multiply(double n1, double n2)
    {
        return n1 * n2;
    }
    public double Divide(double n1, double n2)
    {
        return n1 / n2;
    }
}
```

<span data-ttu-id="2edfe-116">El ejemplo utiliza un enlace `netNamedPipeBinding` modificado sin seguridad.</span><span class="sxs-lookup"><span data-stu-id="2edfe-116">The sample uses a modified `netNamedPipeBinding` binding with no security.</span></span> <span data-ttu-id="2edfe-117">El enlace se especifica en los archivos de configuración para el cliente y servicio.</span><span class="sxs-lookup"><span data-stu-id="2edfe-117">The binding is specified in the configuration files for the client and service.</span></span> <span data-ttu-id="2edfe-118">El tipo de enlace se especifica para el servicio en el atributo `binding` del elemento del extremo, tal y como se explica en el ejemplo siguiente de configuración.</span><span class="sxs-lookup"><span data-stu-id="2edfe-118">The binding type for the service is specified in the endpoint element’s `binding` attribute as shown in the following sample configuration.</span></span>

<span data-ttu-id="2edfe-119">Si desea utilizar un enlace seguro de canalización con nombre, cambie el modo de seguridad del servidor a la configuración de seguridad deseada y ejecute de nuevo svcutil.exe en el cliente para obtener un archivo de configuración del cliente actualizado.</span><span class="sxs-lookup"><span data-stu-id="2edfe-119">If you want use a secured named pipe binding, change the server's security mode to the desired security setting and run svcutil.exe again on the client to obtain an updated client configuration file.</span></span>

```xml
<system.serviceModel>
        <services>
            <service name="Microsoft.ServiceModel.Samples.CalculatorService"
               behaviorConfiguration="CalculatorServiceBehavior">

        <!-- This endpoint is exposed at the base address provided by host: net.pipe://localhost/servicemodelsamples/service.svc  -->
        <endpoint address=""
                  binding="netNamedPipeBinding"
                  bindingConfiguration="Binding1"
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />
        <!-- the mex endpoint is exposed at net.pipe://localhost/servicemodelsamples/service.svc/mex -->
        <endpoint address="mex"
                  binding="mexNamedPipeBinding"
                  contract="IMetadataExchange" />
      </service>
        </services>
        <bindings>
            <netNamedPipeBinding>
                <binding name="Binding1" >
                    <security mode = "None">
                    </security>
                </binding >
            </netNamedPipeBinding>
        </bindings>

    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->
    <behaviors>
      <serviceBehaviors>
        <behavior name="CalculatorServiceBehavior">
          <serviceMetadata />
          <serviceDebug includeExceptionDetailInFaults="False" />
        </behavior>
      </serviceBehaviors>
    </behaviors>

  </system.serviceModel>
```

<span data-ttu-id="2edfe-120">La información de punto de conexión del cliente se configura como se muestra en el código muestra siguiente.</span><span class="sxs-lookup"><span data-stu-id="2edfe-120">The client’s endpoint information is configured as shown in the following sample code.</span></span>

```xml
<system.serviceModel>

    <client>
      <endpoint name=""
                          address="net.pipe://localhost/servicemodelsamples/service.svc"
                          binding="netNamedPipeBinding"
                          bindingConfiguration="Binding1"
                          contract="Microsoft.ServiceModel.Samples.ICalculator" />
    </client>

    <bindings>

      <!--  Following is the expanded configuration section for a NetNamedPipeBinding.
            Each property is configured with the default value. -->

      <netNamedPipeBinding>
        <binding name="Binding1"
                         maxBufferSize="65536"
                         maxConnections="10">
          <security mode = "None">
          </security>
        </binding >

      </netNamedPipeBinding>
    </bindings>

  </system.serviceModel>
```

<span data-ttu-id="2edfe-121">Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="2edfe-121">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="2edfe-122">Presione ENTRAR en la ventana de cliente para cerrar el cliente.</span><span class="sxs-lookup"><span data-stu-id="2edfe-122">Press ENTER in the client window to shut down the client.</span></span>

```console
Add(100,15.99) = 115.99
Subtract(145,76.54) = 68.46
Multiply(9,81.25) = 731.25
Divide(22,7) = 3.14285714285714

Press <ENTER> to terminate client.
```

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="2edfe-123">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="2edfe-123">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="2edfe-124">Asegúrese de que IIS 7,0 está instalado.</span><span class="sxs-lookup"><span data-stu-id="2edfe-124">Ensure that IIS 7.0 is installed.</span></span> <span data-ttu-id="2edfe-125">IIS 7,0 es necesario para la activación WAS.</span><span class="sxs-lookup"><span data-stu-id="2edfe-125">IIS 7.0 is required for WAS activation.</span></span>

2. <span data-ttu-id="2edfe-126">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="2edfe-126">Ensure you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

    <span data-ttu-id="2edfe-127">Además, debe instalar los componentes de activación que no son HTTP de WCF:</span><span class="sxs-lookup"><span data-stu-id="2edfe-127">In addition, you must install the WCF non-HTTP activation components:</span></span>

    1. <span data-ttu-id="2edfe-128">En el menú **Inicio**, elija **Panel de control**.</span><span class="sxs-lookup"><span data-stu-id="2edfe-128">From the **Start** menu, choose **Control Panel**.</span></span>

    2. <span data-ttu-id="2edfe-129">Seleccione **programas y características**.</span><span class="sxs-lookup"><span data-stu-id="2edfe-129">Select **Programs and Features**.</span></span>

    3. <span data-ttu-id="2edfe-130">Haga clic en **activar o desactivar los componentes de Windows**.</span><span class="sxs-lookup"><span data-stu-id="2edfe-130">Click **Turn Windows Components on or Off**.</span></span>

    4. <span data-ttu-id="2edfe-131">Expanda el nodo **Microsoft .NET Framework 3,0** y compruebe la **Windows Communication Foundation característica activación no http** .</span><span class="sxs-lookup"><span data-stu-id="2edfe-131">Expand the **Microsoft .NET Framework 3.0** node and check the **Windows Communication Foundation Non-HTTP Activation** feature.</span></span>

3. <span data-ttu-id="2edfe-132">Configure el servicio de activación de procesos de Windows (WAS) para admitir la activación de la canalización con nombre.</span><span class="sxs-lookup"><span data-stu-id="2edfe-132">Configure the Windows Process Activation Service (WAS) to support named pipe activation.</span></span>

    <span data-ttu-id="2edfe-133">Para su comodidad, los dos pasos siguientes se implementan en un archivo de información llamado AddNetPipeSiteBinding.cmd localizado en el directorio de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="2edfe-133">As a convenience, the following two steps are implemented in a batch file called AddNetPipeSiteBinding.cmd located in the sample directory.</span></span>

    1. <span data-ttu-id="2edfe-134">Para admitir la activación de net.pipe, el sitio web predeterminado se debe enlazar primero al protocolo net.pipe.</span><span class="sxs-lookup"><span data-stu-id="2edfe-134">To support net.pipe activation, the default Web site must first be bound to the net.pipe protocol.</span></span> <span data-ttu-id="2edfe-135">Esto se puede hacer utilizando appcmd.exe, que se instala con el conjunto de herramientas de administración de IIS 7.0.</span><span class="sxs-lookup"><span data-stu-id="2edfe-135">This can be done using appcmd.exe, which is installed with the IIS 7.0 management toolset.</span></span> <span data-ttu-id="2edfe-136">Desde un símbolo del sistema con permisos elevados (administrador), ejecute el comando siguiente.</span><span class="sxs-lookup"><span data-stu-id="2edfe-136">From an elevated (administrator) command prompt, run the following command.</span></span>

        ```console
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"
        -+bindings.[protocol='net.pipe',bindingInformation='*']
        ```

        > [!NOTE]
        > <span data-ttu-id="2edfe-137">Este comando es una sola línea de texto.</span><span class="sxs-lookup"><span data-stu-id="2edfe-137">This command is a single line of text.</span></span>

        <span data-ttu-id="2edfe-138">Este comando agrega un enlace del sitio de net.pipe al sitio web predeterminado.</span><span class="sxs-lookup"><span data-stu-id="2edfe-138">This command adds a net.pipe site binding to the default Web site.</span></span>

    2. <span data-ttu-id="2edfe-139">Aunque todas las aplicaciones dentro de un sitio comparten un enlace net.pipe común, cada aplicación puede habilitar la compatibilidad net.pipe individualmente.</span><span class="sxs-lookup"><span data-stu-id="2edfe-139">Although all applications within a site share a common net.pipe binding, each application can enable net.pipe support individually.</span></span> <span data-ttu-id="2edfe-140">Para habilitar net.pipe para la aplicación /servicemodelsamples, ejecute el comando siguiente desde un símbolo del sistema con permisos elevados.</span><span class="sxs-lookup"><span data-stu-id="2edfe-140">To enable net.pipe for the /servicemodelsamples application, run the following command from an elevated command prompt.</span></span>

        ```console
        %windir%\system32\inetsrv\appcmd.exe set app "Default Web Site/servicemodelsamples" /enabledProtocols:http,net.pipe
        ```

        > [!NOTE]
        > <span data-ttu-id="2edfe-141">Este comando es una sola línea de texto.</span><span class="sxs-lookup"><span data-stu-id="2edfe-141">This command is a single line of text.</span></span>

        <span data-ttu-id="2edfe-142">Este comando permite tener acceso a la aplicación/servicemodelsamples mediante `http://localhost/servicemodelsamples` y `net.tcp://localhost/servicemodelsamples`.</span><span class="sxs-lookup"><span data-stu-id="2edfe-142">This command enables the /servicemodelsamples application to be accessed using both `http://localhost/servicemodelsamples` and `net.tcp://localhost/servicemodelsamples`.</span></span>

4. <span data-ttu-id="2edfe-143">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="2edfe-143">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

5. <span data-ttu-id="2edfe-144">Quite el enlace del sitio de net.pipe que ha agregado para obtener este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="2edfe-144">Remove the net.pipe site binding you added for this sample.</span></span>

    <span data-ttu-id="2edfe-145">Para su comodidad, los dos pasos siguientes se implementan en un archivo por lotes denominado RemoveNetPipeSiteBinding.cmd que se encuentra en el directorio de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2edfe-145">As a convenience, the following two steps are implemented in a batch file called RemoveNetPipeSiteBinding.cmd located in the sample directory:</span></span>

    1. <span data-ttu-id="2edfe-146">Quite net.tcp de la lista de protocolos habilitados ejecutando el comando siguiente desde un símbolo del sistema con permisos elevados.</span><span class="sxs-lookup"><span data-stu-id="2edfe-146">Remove net.tcp from the list of enabled protocols by running the following command from an elevated command prompt.</span></span>

        ```console
        %windir%\system32\inetsrv\appcmd.exe set app "Default Web Site/servicemodelsamples" /enabledProtocols:http
        ```

        > [!NOTE]
        > <span data-ttu-id="2edfe-147">Este comando se debe escribir como una línea de texto única.</span><span class="sxs-lookup"><span data-stu-id="2edfe-147">This command must be entered as a single line of text.</span></span>

    2. <span data-ttu-id="2edfe-148">Quite el enlace del sitio net.tcp ejecutando el comando siguiente desde un símbolo del sistema con permisos elevados.</span><span class="sxs-lookup"><span data-stu-id="2edfe-148">Remove the net.tcp site binding by running the following command from an elevated command prompt.</span></span>

        ```console
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site" --bindings.[protocol='net.pipe',bindingInformation='*']
        ```

        > [!NOTE]
        > <span data-ttu-id="2edfe-149">Este comando se debe escribir en una sola línea de texto.</span><span class="sxs-lookup"><span data-stu-id="2edfe-149">This command must be typed in as a single line of text.</span></span>

## <a name="see-also"></a><span data-ttu-id="2edfe-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="2edfe-150">See also</span></span>

- <span data-ttu-id="2edfe-151">[Ejemplos de hospedaje y persistencia de AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ff383418(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="2edfe-151">[AppFabric Hosting and Persistence Samples](https://docs.microsoft.com/previous-versions/appfabric/ff383418(v=azure.10))</span></span>
