---
description: 'Más información acerca de cómo: intercambiar mensajes dentro de una sesión confiable'
title: Procedimiento para intercambiar mensajes dentro de una sesión confiable
ms.date: 03/30/2017
ms.assetid: 87cd0e75-dd2c-44c1-8da0-7b494bbdeaea
ms.openlocfilehash: e4a8f6a180b9c2ff9471558997034d02acc817e7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802910"
---
# <a name="how-to-exchange-messages-within-a-reliable-session"></a><span data-ttu-id="b6f21-103">Procedimiento para intercambiar mensajes dentro de una sesión confiable</span><span class="sxs-lookup"><span data-stu-id="b6f21-103">How to: Exchange Messages Within a Reliable Session</span></span>

<span data-ttu-id="b6f21-104">En este tema se describen los pasos necesarios para habilitar una sesión confiable utilizando uno de los enlaces proporcionados por el sistema que admiten este tipo de sesión, pero no de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="b6f21-104">This topic outlines the steps required to enable a reliable session using one of the system-provided bindings that support such a session, but not by default.</span></span> <span data-ttu-id="b6f21-105">Habilita una sesión confiable de manera imperativa mediante código o mediante declaración en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="b6f21-105">You enable a reliable session imperatively using code or declaratively in your configuration file.</span></span> <span data-ttu-id="b6f21-106">Este procedimiento utiliza los archivos de configuración de servicio y cliente para habilitar la sesión confiable y estipular que los mensajes lleguen en el mismo orden en el que se enviaron.</span><span class="sxs-lookup"><span data-stu-id="b6f21-106">This procedure uses the client and service configuration files to enable the reliable session and to stipulate that the messages arrive in the same order in which they were sent.</span></span>

<span data-ttu-id="b6f21-107">La parte clave de este procedimiento es que el elemento de configuración de extremo contiene un `bindingConfiguration` atributo que hace referencia a una configuración de enlace denominada `Binding1` .</span><span class="sxs-lookup"><span data-stu-id="b6f21-107">The key part of this procedure is that the endpoint configuration element contain a `bindingConfiguration` attribute that references a binding configuration named `Binding1`.</span></span> <span data-ttu-id="b6f21-108">El [**\<binding>**](../../configure-apps/file-schema/wcf/bindings.md) elemento de configuración hace referencia a este nombre para habilitar las sesiones confiables estableciendo el `enabled` atributo del [**\<reliableSession>**](/previous-versions/dotnet/netframework-4.0/ms731302(v=vs.100)) elemento en `true` .</span><span class="sxs-lookup"><span data-stu-id="b6f21-108">The [**\<binding>**](../../configure-apps/file-schema/wcf/bindings.md) configuration element references this name to enable reliable sessions by setting the `enabled` attribute of the [**\<reliableSession>**](/previous-versions/dotnet/netframework-4.0/ms731302(v=vs.100)) element to `true`.</span></span> <span data-ttu-id="b6f21-109">Especifica las garantías de entrega ordenada de la sesión confiable estableciendo el atributo `ordered` en `true`.</span><span class="sxs-lookup"><span data-stu-id="b6f21-109">You specify the ordered delivery assurances for the reliable session by setting the `ordered` attribute to `true`.</span></span>

<span data-ttu-id="b6f21-110">Para la copia de origen de este ejemplo, consulte [WS Reliable Session](../samples/ws-reliable-session.md).</span><span class="sxs-lookup"><span data-stu-id="b6f21-110">For the source copy of this example, see [WS Reliable Session](../samples/ws-reliable-session.md).</span></span>

### <a name="configure-the-service-with-a-wshttpbinding-to-use-a-reliable-session"></a><span data-ttu-id="b6f21-111">Configurar el servicio con un WSHttpBinding para utilizar una sesión confiable</span><span class="sxs-lookup"><span data-stu-id="b6f21-111">Configure the service with a WSHttpBinding to use a reliable session</span></span>

1. <span data-ttu-id="b6f21-112">Defina un contrato de servicios para el tipo de servicio.</span><span class="sxs-lookup"><span data-stu-id="b6f21-112">Define a service contract for the type of service.</span></span>

   [!code-csharp[c_HowTo_UseReliableSession#1121](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/service.cs#1121)]

1. <span data-ttu-id="b6f21-113">Implemente el contrato de servicios en una clase de servicio.</span><span class="sxs-lookup"><span data-stu-id="b6f21-113">Implement the service contract in a service class.</span></span> <span data-ttu-id="b6f21-114">Tenga en cuenta que la información de dirección o enlace no se especifica dentro de la implementación del servicio.</span><span class="sxs-lookup"><span data-stu-id="b6f21-114">Note that the address or binding information isn't specified inside the implementation of the service.</span></span> <span data-ttu-id="b6f21-115">No es necesario escribir código para recuperar la dirección o la información de enlace del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="b6f21-115">You aren't required to write code to retrieve the address or binding information from the configuration file.</span></span>

   [!code-csharp[c_HowTo_UseReliableSession#1122](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/service.cs#1122)]

1. <span data-ttu-id="b6f21-116">Cree un archivo de *Web.config* para configurar un extremo para `CalculatorService` que use <xref:System.ServiceModel.WSHttpBinding> con sesión confiable habilitada y entrega ordenada de los mensajes necesarios.</span><span class="sxs-lookup"><span data-stu-id="b6f21-116">Create a *Web.config* file to configure an endpoint for the `CalculatorService` that uses the <xref:System.ServiceModel.WSHttpBinding> with reliable session enabled and ordered delivery of messages required.</span></span>

   [!code-xml[c_HowTo_UseReliableSession#2111](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/common/web.config#2111)]

1. <span data-ttu-id="b6f21-117">Cree un archivo *Service. SVC* que contenga la línea:</span><span class="sxs-lookup"><span data-stu-id="b6f21-117">Create a *Service.svc* file that contains the line:</span></span>

   ```aspx-csharp
   <%@ServiceHost language=c# Service="CalculatorService" %>
   ```

1. <span data-ttu-id="b6f21-118">Coloque el archivo *Service. SVC* en el directorio virtual de Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="b6f21-118">Place the *Service.svc* file in your Internet Information Services (IIS) virtual directory.</span></span>

### <a name="configure-the-client-with-a-wshttpbinding-to-use-a-reliable-session"></a><span data-ttu-id="b6f21-119">Configurar el cliente con un WSHttpBinding para utilizar una sesión confiable</span><span class="sxs-lookup"><span data-stu-id="b6f21-119">Configure the client with a WSHttpBinding to use a reliable session</span></span>

1. <span data-ttu-id="b6f21-120">Use la [herramienta de utilidad de metadatos de ServiceModel (*Svcutil.exe*)](../servicemodel-metadata-utility-tool-svcutil-exe.md) desde la línea de comandos para generar código a partir de los metadatos de servicio:</span><span class="sxs-lookup"><span data-stu-id="b6f21-120">Use the [ServiceModel Metadata Utility Tool (*Svcutil.exe*)](../servicemodel-metadata-utility-tool-svcutil-exe.md) from the command line to generate code from service metadata:</span></span>

   ```console
   Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>
   ```

1. <span data-ttu-id="b6f21-121">El cliente generado contiene la `ICalculator` interfaz que define el contrato de servicio que la implementación del cliente debe cumplir.</span><span class="sxs-lookup"><span data-stu-id="b6f21-121">The generated client contains the `ICalculator` interface that defines the service contract that the client implementation must satisfy.</span></span>

   [!code-csharp[C_HowTo_UseReliableSession#1221](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1221)]

1. <span data-ttu-id="b6f21-122">La aplicación de cliente generada también contiene la implementación de `ClientCalculator`.</span><span class="sxs-lookup"><span data-stu-id="b6f21-122">The generated client application also contains the implementation of the `ClientCalculator`.</span></span> <span data-ttu-id="b6f21-123">Tenga en cuenta que la dirección y la información de enlace no se especifican en ningún lugar dentro de la implementación del servicio.</span><span class="sxs-lookup"><span data-stu-id="b6f21-123">Note that the address and binding information isn't specified anywhere inside the implementation of the service.</span></span> <span data-ttu-id="b6f21-124">No es necesario escribir código para recuperar la dirección o la información de enlace del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="b6f21-124">You aren't required to write code to retrieve the address or binding information from the configuration file.</span></span>

   [!code-csharp[C_HowTo_UseReliableSession#1222](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1222)]

1. <span data-ttu-id="b6f21-125">*Svcutil.exe* también genera la configuración para el cliente que utiliza la <xref:System.ServiceModel.WSHttpBinding> clase.</span><span class="sxs-lookup"><span data-stu-id="b6f21-125">*Svcutil.exe* also generates the configuration for the client that uses the <xref:System.ServiceModel.WSHttpBinding> class.</span></span> <span data-ttu-id="b6f21-126">Asigne un nombre al archivo de configuración *App.config* al utilizar Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b6f21-126">Name the configuration file *App.config* when using Visual Studio.</span></span>

   [!code-xml[C_HowTo_UseReliableSession#2211](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/common/app.config#2211)]

1. <span data-ttu-id="b6f21-127">Cree una instancia de `ClientCalculator` en una aplicación y llame a las operaciones del servicio.</span><span class="sxs-lookup"><span data-stu-id="b6f21-127">Create an instance of the `ClientCalculator` in an application and call the service operations.</span></span>

   [!code-csharp[C_HowTo_UseReliableSession#1223](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1223)]

1. <span data-ttu-id="b6f21-128">Compile y ejecute el cliente.</span><span class="sxs-lookup"><span data-stu-id="b6f21-128">Compile and run the client.</span></span>

## <a name="example"></a><span data-ttu-id="b6f21-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b6f21-129">Example</span></span>

<span data-ttu-id="b6f21-130">Algunos de los enlaces proporcionados por el sistema admiten de forma predeterminada las sesiones confiables.</span><span class="sxs-lookup"><span data-stu-id="b6f21-130">Several of the system-provided bindings support reliable sessions by default.</span></span> <span data-ttu-id="b6f21-131">Se incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="b6f21-131">These include:</span></span>

- <xref:System.ServiceModel.WSDualHttpBinding>

- <xref:System.ServiceModel.NetNamedPipeBinding>

- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>

<span data-ttu-id="b6f21-132">Para obtener un ejemplo de cómo crear un enlace personalizado que admita sesiones confiables, consulte [Cómo: crear un enlace de sesión confiable personalizado con https](how-to-create-a-custom-reliable-session-binding-with-https.md).</span><span class="sxs-lookup"><span data-stu-id="b6f21-132">For an example of how to create a custom binding that supports reliable sessions, see [How to: Create a Custom Reliable Session Binding with HTTPS](how-to-create-a-custom-reliable-session-binding-with-https.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b6f21-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="b6f21-133">See also</span></span>

- [<span data-ttu-id="b6f21-134">Sesiones de confianza</span><span class="sxs-lookup"><span data-stu-id="b6f21-134">Reliable Sessions</span></span>](reliable-sessions.md)
