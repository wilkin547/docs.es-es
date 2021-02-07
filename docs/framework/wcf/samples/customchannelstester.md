---
description: 'Más información acerca de: CustomChannelsTester'
title: CustomChannelsTester
ms.date: 03/30/2017
ms.assetid: ee1fa307-98b1-4647-8860-2e9217ba6082
ms.openlocfilehash: f1b84d8de0a93edf685d63b2bfd3c51f8b3e0420
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99755920"
---
# <a name="customchannelstester"></a><span data-ttu-id="70da6-103">CustomChannelsTester</span><span class="sxs-lookup"><span data-stu-id="70da6-103">CustomChannelsTester</span></span>

<span data-ttu-id="70da6-104">El `CustomChannelsTester` es una herramienta que se utiliza para probar las implementaciones del canal personalizadas contra un conjunto de contratos de servicios predefinidos.</span><span class="sxs-lookup"><span data-stu-id="70da6-104">The `CustomChannelsTester` is a tool that you can use to test your custom channel implementations against a set of predefined service contracts.</span></span> <span data-ttu-id="70da6-105">Puede seleccionar el conjunto de contratos de servicios y pasarlo a la herramienta utilizando un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="70da6-105">You can select the set of service contracts and pass it to the tool using an XML file.</span></span> <span data-ttu-id="70da6-106">La herramienta genera a continuación el servicio y el cliente que ejerce sus implementaciones del canal personalizadas durante el intercambio de mensajes.</span><span class="sxs-lookup"><span data-stu-id="70da6-106">The tool then generates the service and client that exercises your custom channel implementations during message exchange.</span></span>  
  
### <a name="to-build-the-tool"></a><span data-ttu-id="70da6-107">Para compilar la herramienta</span><span class="sxs-lookup"><span data-stu-id="70da6-107">To build the tool</span></span>  
  
1. <span data-ttu-id="70da6-108">Para compilar la solución, siga las instrucciones de [creación de los ejemplos de Windows Communication Foundation](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="70da6-108">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
2. <span data-ttu-id="70da6-109">Al compilar la solución, se generan tres archivos: CustomChannelsTester.exe, TestSpec.xml y SampleRun.cmd.</span><span class="sxs-lookup"><span data-stu-id="70da6-109">Building the solution generates three files: CustomChannelsTester.exe, TestSpec.xml and SampleRun.cmd.</span></span> <span data-ttu-id="70da6-110">El archivo SampleRun. cmd tiene una línea de comandos de ejemplo que muestra cómo usar esta herramienta para probar el ejemplo [Transport: UDP](transport-udp.md) .</span><span class="sxs-lookup"><span data-stu-id="70da6-110">The file SampleRun.cmd has a sample command line that shows how to use this tool to test the [Transport: UDP](transport-udp.md) sample.</span></span>  
  
### <a name="to-run-the-tool"></a><span data-ttu-id="70da6-111">Para ejecutar la herramienta</span><span class="sxs-lookup"><span data-stu-id="70da6-111">To run the tool</span></span>  
  
- <span data-ttu-id="70da6-112">Escriba el siguiente comando en el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="70da6-112">At the command prompt type the following command:</span></span>  
  
    ```console  
    CustomChannelsTester.exe /binding:YourCustomBindngName /dll:TheAssemblyWhereThisTypeisDefined /testspec:XmlFileNameWhichContainsTestOptions  
    ```  
  
     <span data-ttu-id="70da6-113">Se requiere utilizar la opción `/binding`.</span><span class="sxs-lookup"><span data-stu-id="70da6-113">Using the `/binding` option is required.</span></span>  
  
     <span data-ttu-id="70da6-114">`/dll` es necesario si "Binding" no es un enlace proporcionado por el sistema proporcionado por Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="70da6-114">`/dll` is required if "binding" is not a system-provided binding provided by Windows Communication Foundation (WCF).</span></span>  
  
     <span data-ttu-id="70da6-115">`/testspec` es opcional.</span><span class="sxs-lookup"><span data-stu-id="70da6-115">`/testspec` is optional.</span></span>  
  
     <span data-ttu-id="70da6-116">Esto crea el servidor y los clientes basados en las características técnicas de pruebas y el enlace.</span><span class="sxs-lookup"><span data-stu-id="70da6-116">This creates server and clients based on the test specifications and the binding.</span></span>  
  
     <span data-ttu-id="70da6-117">Ejecuta el cliente y el servidor y devuelve los resultados.</span><span class="sxs-lookup"><span data-stu-id="70da6-117">Executes the client and server and returns the results.</span></span>  
  
     <span data-ttu-id="70da6-118">A continuación, se muestra el ejemplo XML para la descripción de las características técnicas de pruebas (testspec.xml):</span><span class="sxs-lookup"><span data-stu-id="70da6-118">The following is the sample XML for the description of the test specifications (testspec.xml):</span></span>  
  
    ```xml  
    <TestSpec xmlns="http://WCF/TestSpec" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" >  
    <ServiceContract>  
    <!-- Test a contract which has oneway / twoway operations. If you set ExpandAll = true, both types of contracts are tested -->    <IsOneWay ExpandAll="true">true</IsOneWay>  
    <!-- Test a contract with Asynchronous / Synchronous Operations-->  
        <IsAsync>false</IsAsync>
    <!-- Test a sessionful / sessionless contract-->
        <IsSession ExpandAll="true">true</IsSession>  
    <!-- If the Service Contract includes a CallBack Contract-->
        <IsCallBack ExpandAll="true">true</IsCallBack>  
    </ServiceContract>  
    <TestDetails>  
    <!-- Name of the machine that runs the server - required if you want to run the test crossmachine-->  
        <ServerName>ReplaceThisWithTheServerMachineName</ServerName>  
    <!-- Port Number - Optional-->  
        <Port>8000</Port>  
    <!--URI for the callBack address for the client. The client will receive the messages from the server on this address in case of a CallBack Contract-->  
        <ClientCallBackAddress/>
    <!-- Duration (in sec) after the server has started, it times out - optional(default = 300sec) -->  
        <ServerTimeout>300</ServerTimeout>  
    <!-- Duration (in sec) before the Client initializes -optional(default = 60sec) -->  
        <ClientTimeout>60</ClientTimeout>  
    <!-- Number of clients for each service - optional(default = 1) -->  
        <NumberOfClients>1</NumberOfClients>  
    <!-- Number of messages each client sends to the service - optional(default = 1) -->  
        <MessagesPerClient>1</MessagesPerClient>  
    </TestDetails>  
    </TestSpec>  
    ```  
