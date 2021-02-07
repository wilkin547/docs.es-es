---
description: Más información acerca de la activación de TCP
title: Activación TCP
ms.date: 03/30/2017
ms.assetid: bf8c215c-0228-4f4f-85c2-e33794ec09a7
ms.openlocfilehash: bfa98eff1bcab31df3e28d46e77d90456020507c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99685639"
---
# <a name="tcp-activation"></a><span data-ttu-id="5aac0-103">Activación TCP</span><span class="sxs-lookup"><span data-stu-id="5aac0-103">TCP Activation</span></span>

<span data-ttu-id="5aac0-104">Este ejemplo muestra cómo hospedar un servicio que utiliza el servicio de activación de procesos de Windows (WAS) para activar un servicio que comunica a través del protocolo de net.tcp.</span><span class="sxs-lookup"><span data-stu-id="5aac0-104">This sample demonstrates hosting a service that uses Windows Process Activation Services (WAS) to activate a service that communicates over the net.tcp protocol.</span></span> <span data-ttu-id="5aac0-105">Este ejemplo se basa en el [Introducción](getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="5aac0-105">This sample is based on the [Getting Started](getting-started-sample.md).</span></span>

> [!NOTE]
> <span data-ttu-id="5aac0-106">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="5aac0-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5aac0-107">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="5aac0-107">The samples may already be installed on your computer.</span></span> <span data-ttu-id="5aac0-108">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="5aac0-108">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="5aac0-109">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="5aac0-109">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="5aac0-110">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="5aac0-110">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WASHost\TCPActivation`

<span data-ttu-id="5aac0-111">El ejemplo está compuesto por un programa (.exe) de consola de cliente y una biblioteca de servicios (.dll) hospedados en un proceso de trabajo activado por WAS.</span><span class="sxs-lookup"><span data-stu-id="5aac0-111">The sample consists of a client console program (.exe) and a service library (.dll) hosted in a worker process activated by WAS.</span></span> <span data-ttu-id="5aac0-112">La actividad del cliente es visible en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="5aac0-112">Client activity is visible in the console window.</span></span>

<span data-ttu-id="5aac0-113">El servicio implementa un contrato que define un modelo de comunicación de solicitud y respuesta.</span><span class="sxs-lookup"><span data-stu-id="5aac0-113">The service implements a contract that defines a request-reply communication pattern.</span></span> <span data-ttu-id="5aac0-114">La interfaz `ICalculator`, que expone las operaciones matemáticas (Sumar, Restar, Multiplicar y Dividir), define el contrato, tal y como se muestra en el código muestra siguiente:</span><span class="sxs-lookup"><span data-stu-id="5aac0-114">The contract is defined by the `ICalculator` interface, which exposes math operations (Add, Subtract, Multiply, and Divide), as shown in the following sample code:</span></span>

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

<span data-ttu-id="5aac0-115">La implementación del servicio calcula y devuelve el resultado adecuado:</span><span class="sxs-lookup"><span data-stu-id="5aac0-115">The service implementation calculates and returns the appropriate result:</span></span>

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

<span data-ttu-id="5aac0-116">El ejemplo utiliza una variante del net.tcp que enlaza con el uso compartido de un puerto TCP habilitado y con la seguridad desactivada.</span><span class="sxs-lookup"><span data-stu-id="5aac0-116">The sample uses a variant of the net.tcp binding with TCP port sharing enabled and security turned off.</span></span> <span data-ttu-id="5aac0-117">Si desea utilizar un enlace del TCP seguro, cambie el modo de seguridad del servidor al valor deseado y re-ejecute Svcutil.exe en el cliente para generar un archivo de configuración de cliente de actualización.</span><span class="sxs-lookup"><span data-stu-id="5aac0-117">If you want to use a secured TCP binding, change the server's security mode to the desired setting and re-run Svcutil.exe on the client to generate an update client configuration file.</span></span>

<span data-ttu-id="5aac0-118">El ejemplo siguiente muestra la configuración para el servicio:</span><span class="sxs-lookup"><span data-stu-id="5aac0-118">The following sample shows the configuration for the service:</span></span>

```xml
<system.serviceModel>

    <services>
      <service name="Microsoft.ServiceModel.Samples.CalculatorService"
               behaviorConfiguration="CalculatorServiceBehavior">
        <!-- This endpoint is exposed at the base address provided by host: net.tcp://localhost/servicemodelsamples/service.svc  -->
        <endpoint binding="netTcpBinding" bindingConfiguration="PortSharingBinding"
          contract="Microsoft.ServiceModel.Samples.ICalculator" />
        <!-- the mex endpoint is exposed at net.tcp://localhost/servicemodelsamples/service.svc/mex -->
        <endpoint address="mex"
                  binding="mexTcpBinding"
                  contract="IMetadataExchange" />
      </service>
    </services>
    <bindings>
      <netTcpBinding>
        <binding name="PortSharingBinding" portSharingEnabled="true">
          <security mode="None" />
        </binding>
      </netTcpBinding>
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

<span data-ttu-id="5aac0-119">El extremo del cliente se configura como se muestra en el código muestra siguiente:</span><span class="sxs-lookup"><span data-stu-id="5aac0-119">The client's endpoint is configured as shown in the following sample code:</span></span>

```xml
<system.serviceModel>
    <bindings>
        <netTcpBinding>
          <binding name="NetTcpBinding_ICalculator">
            <security mode="None"/>
          </binding>
        </netTcpBinding>
    </bindings>
    <client>
        <endpoint address="net.tcp://localhost/servicemodelsamples/service.svc"
            binding="netTcpBinding" bindingConfiguration="NetTcpBinding_ICalculator"
            contract="Microsoft.ServiceModel.Samples.ICalculator" name="NetTcpBinding_ICalculator" />
    </client>
</system.serviceModel>
```

<span data-ttu-id="5aac0-120">Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="5aac0-120">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="5aac0-121">Presione ENTRAR en la ventana de cliente para cerrar el cliente.</span><span class="sxs-lookup"><span data-stu-id="5aac0-121">Press ENTER in the client window to shut down the client.</span></span>

```console
Add(100,15.99) = 115.99
Subtract(145,76.54) = 68.46
Multiply(9,81.25) = 731.25
Divide(22,7) = 3.14285714285714

Press <ENTER> to terminate client.
```

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="5aac0-122">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="5aac0-122">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="5aac0-123">Asegúrese de que IIS 7,0 está instalado.</span><span class="sxs-lookup"><span data-stu-id="5aac0-123">Ensure that IIS 7.0 is installed.</span></span> <span data-ttu-id="5aac0-124">IIS 7,0 es necesario para la activación WAS.</span><span class="sxs-lookup"><span data-stu-id="5aac0-124">IIS 7.0 is required for WAS activation.</span></span>

2. <span data-ttu-id="5aac0-125">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="5aac0-125">Be sure you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

    <span data-ttu-id="5aac0-126">Además, debe instalar los componentes de activación que no son HTTP de WCF:</span><span class="sxs-lookup"><span data-stu-id="5aac0-126">In addition, you must install the WCF non-HTTP activation components:</span></span>

    1. <span data-ttu-id="5aac0-127">En el menú **Inicio**, elija **Panel de control**.</span><span class="sxs-lookup"><span data-stu-id="5aac0-127">From the **Start** menu, choose **Control Panel**.</span></span>

    2. <span data-ttu-id="5aac0-128">Seleccione **programas y características**.</span><span class="sxs-lookup"><span data-stu-id="5aac0-128">Select **Programs and Features**.</span></span>

    3. <span data-ttu-id="5aac0-129">Haga clic en **activar o desactivar los componentes de Windows**.</span><span class="sxs-lookup"><span data-stu-id="5aac0-129">Click **Turn Windows Components on or Off**.</span></span>

    4. <span data-ttu-id="5aac0-130">Expanda el nodo **Microsoft .NET Framework 3,0** y compruebe la **Windows Communication Foundation característica activación no http** .</span><span class="sxs-lookup"><span data-stu-id="5aac0-130">Expand the **Microsoft .NET Framework 3.0** node and check the **Windows Communication Foundation Non-HTTP Activation** feature.</span></span>

3. <span data-ttu-id="5aac0-131">Configure WAS para admitir la activación del TCP.</span><span class="sxs-lookup"><span data-stu-id="5aac0-131">Configure WAS to support TCP activation.</span></span>

    <span data-ttu-id="5aac0-132">Para su comodidad, los dos pasos siguientes se implementan en un archivo de información llamado AddNetTcpSiteBinding.cmd localizado en el directorio de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="5aac0-132">As a convenience, the following two steps are implemented in a batch file called AddNetTcpSiteBinding.cmd located in the sample directory.</span></span>

    1. <span data-ttu-id="5aac0-133">Para admitir la activación del net.tcp, el sitio web predeterminado debe enlazarse primero a un puerto net.tcp.</span><span class="sxs-lookup"><span data-stu-id="5aac0-133">To support net.tcp activation, the default Web site must first be bound to a net.tcp port.</span></span> <span data-ttu-id="5aac0-134">Esto se puede hacer utilizando Appcmd.exe, que se instala con el conjunto de herramientas de administración Internet Information Server 7.0 (IIS).</span><span class="sxs-lookup"><span data-stu-id="5aac0-134">This can be done using Appcmd.exe, which is installed with the Internet Information Services 7.0 (IIS) management toolset.</span></span> <span data-ttu-id="5aac0-135">Desde un símbolo del sistema del nivel administrador, ejecute el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="5aac0-135">From an administrator-level command prompt, run the following command:</span></span>

        ```console
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site" -+bindings.[protocol='net.tcp',bindingInformation='808:*']
        ```

        > [!TIP]
        > <span data-ttu-id="5aac0-136">Este comando es una sola línea de texto.</span><span class="sxs-lookup"><span data-stu-id="5aac0-136">This command is a single line of text.</span></span> <span data-ttu-id="5aac0-137">Este comando agrega un enlace del sitio net.tcp al sitio web predeterminado que realiza escuchas en puerto TCP 808 con cualquier nombre del host.</span><span class="sxs-lookup"><span data-stu-id="5aac0-137">This command adds a net.tcp site binding to the default Web site listening on TCP port 808 with any hostname.</span></span>

    2. <span data-ttu-id="5aac0-138">Aunque todas las aplicaciones dentro de un sitio comparten un enlace net. tcp común, cada aplicación puede habilitar la compatibilidad net. tcp individualmente.</span><span class="sxs-lookup"><span data-stu-id="5aac0-138">Although all applications within a site share a common net.tcp binding, each application can enable net.tcp support individually.</span></span> <span data-ttu-id="5aac0-139">Para habilitar el net.tcp para la aplicación /servicemodelsamples, ejecute el comando siguiente desde un símbolo del sistema del nivel del administrador:</span><span class="sxs-lookup"><span data-stu-id="5aac0-139">To enable net.tcp for the /servicemodelsamples application, run the following command from an administrator-level command prompt:</span></span>

        ```console
        %windir%\system32\inetsrv\appcmd.exe set app
        "Default Web Site/servicemodelsamples" /enabledProtocols:http,net.tcp
        ```

        > [!NOTE]
        > <span data-ttu-id="5aac0-140">Este comando es una sola línea de texto.</span><span class="sxs-lookup"><span data-stu-id="5aac0-140">This command is a single line of text.</span></span> <span data-ttu-id="5aac0-141">Este comando permite tener acceso a la aplicación/servicemodelsamples mediante `http://localhost/servicemodelsamples` y `net.tcp://localhost/servicemodelsamples` .</span><span class="sxs-lookup"><span data-stu-id="5aac0-141">This command enables the /servicemodelsamples application to be accessed using both `http://localhost/servicemodelsamples` and `net.tcp://localhost/servicemodelsamples`.</span></span>

4. <span data-ttu-id="5aac0-142">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="5aac0-142">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

5. <span data-ttu-id="5aac0-143">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="5aac0-143">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>

    <span data-ttu-id="5aac0-144">Elimine el enlace del sitio de net.tcp que ha agregado para este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="5aac0-144">Remove the net.tcp site binding you added for this sample.</span></span>

    <span data-ttu-id="5aac0-145">Para su comodidad, los dos pasos siguientes se implementan en un archivo de información llamado RemoveNetTcpSiteBinding.cmd localizado en el directorio de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="5aac0-145">As a convenience, the following two steps are implemented in a batch file called RemoveNetTcpSiteBinding.cmd located in the sample directory.</span></span>

    1. <span data-ttu-id="5aac0-146">Quite el net.tcp de la lista de protocolos habilitados ejecutando el comando siguiente desde un símbolo del sistema del nivel del administrador:</span><span class="sxs-lookup"><span data-stu-id="5aac0-146">Remove net.tcp from the list of enabled protocols by running the following command from an administrator-level command prompt:</span></span>

        ```console
        %windir%\system32\inetsrv\appcmd.exe set app
        "Default Web Site/servicemodelsamples" /enabledProtocols:http
        ```

        > [!NOTE]
        > <span data-ttu-id="5aac0-147">Este comando se debe escribir como una línea de texto única.</span><span class="sxs-lookup"><span data-stu-id="5aac0-147">This command must be entered as a single line of text.</span></span>

    2. <span data-ttu-id="5aac0-148">Quite el enlace del sitio net.tcp ejecutando el siguiente comando desde un símbolo del sistema de nivel de administrador:</span><span class="sxs-lookup"><span data-stu-id="5aac0-148">Remove the net.tcp site binding by running the following command from an administrator-level command prompt:</span></span>

        ```console
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"
        --bindings.[protocol='net.tcp',bindingInformation='808:*']
        ```

        > [!NOTE]
        > <span data-ttu-id="5aac0-149">Este comando se debe escribir en una sola línea de texto.</span><span class="sxs-lookup"><span data-stu-id="5aac0-149">This command must be typed in as a single line of text.</span></span>

## <a name="see-also"></a><span data-ttu-id="5aac0-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="5aac0-150">See also</span></span>

- <span data-ttu-id="5aac0-151">[Ejemplos de hospedaje y persistencia de AppFabric](/previous-versions/appfabric/ff383418(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="5aac0-151">[AppFabric Hosting and Persistence Samples](/previous-versions/appfabric/ff383418(v=azure.10))</span></span>
