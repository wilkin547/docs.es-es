---
title: "Intercambio de mensajes dentro de una sesión confiable"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 87cd0e75-dd2c-44c1-8da0-7b494bbdeaea
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c0465f50de37d7276cad5920c4b9fb9e544caf57
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-exchange-messages-within-a-reliable-session"></a><span data-ttu-id="1523d-102">Intercambio de mensajes dentro de una sesión confiable</span><span class="sxs-lookup"><span data-stu-id="1523d-102">How to: Exchange Messages Within a Reliable Session</span></span>

<span data-ttu-id="1523d-103">En este tema se describen los pasos necesarios para habilitar una sesión confiable utilizando uno de los enlaces proporcionados por el sistema que admiten este tipo de sesión, pero no de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="1523d-103">This topic outlines the steps required to enable a reliable session using one of the system-provided bindings that support such a session, but not by default.</span></span> <span data-ttu-id="1523d-104">Habilitar una sesión confiable de manera imperativa mediante código o mediante declaración en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="1523d-104">You enable a reliable session imperatively using code or declaratively in your configuration file.</span></span> <span data-ttu-id="1523d-105">Este procedimiento utiliza los archivos de configuración de cliente y el servicio que se va a habilitar la sesión confiable como estipular que los mensajes lleguen en el mismo orden en que se enviaron.</span><span class="sxs-lookup"><span data-stu-id="1523d-105">This procedure uses the client and service configuration files to enable the reliable session and to stipulate that the messages arrive in the same order in which they were sent.</span></span>

<span data-ttu-id="1523d-106">La parte clave de este procedimiento es que el elemento de configuración de extremo contenga un `bindingConfiguration` atributo que hace referencia a una configuración de enlace denominada `Binding1`.</span><span class="sxs-lookup"><span data-stu-id="1523d-106">The key part of this procedure is that the endpoint configuration element contain a `bindingConfiguration` attribute that references a binding configuration named `Binding1`.</span></span> <span data-ttu-id="1523d-107">El [  **\<enlace >** ](../../../../docs/framework/misc/binding.md) elemento de configuración hace referencia a este nombre para habilitar sesiones confiables estableciendo la `enabled` atributo de la [  **\<reliableSession >** ](http://msdn.microsoft.com/en-us/9c93818a-7dfa-43d5-b3a1-1aafccf3a00b) elemento `true`.</span><span class="sxs-lookup"><span data-stu-id="1523d-107">The [**\<binding>**](../../../../docs/framework/misc/binding.md) configuration element references this name to enable reliable sessions by setting the `enabled` attribute of the [**\<reliableSession>**](http://msdn.microsoft.com/en-us/9c93818a-7dfa-43d5-b3a1-1aafccf3a00b) element to `true`.</span></span> <span data-ttu-id="1523d-108">Especifica las garantías de entrega ordenada de la sesión confiable estableciendo el atributo `ordered` en `true`.</span><span class="sxs-lookup"><span data-stu-id="1523d-108">You specify the ordered delivery assurances for the reliable session by setting the `ordered` attribute to `true`.</span></span>

<span data-ttu-id="1523d-109">Para la copia de origen de este ejemplo, vea [sesión confiable WS](../../../../docs/framework/wcf/samples/ws-reliable-session.md).</span><span class="sxs-lookup"><span data-stu-id="1523d-109">For the source copy of this example, see [WS Reliable Session](../../../../docs/framework/wcf/samples/ws-reliable-session.md).</span></span>

### <a name="configure-the-service-with-a-wshttpbinding-to-use-a-reliable-session"></a><span data-ttu-id="1523d-110">Configurar el servicio con WSHttpBinding para utilizar una sesión confiable</span><span class="sxs-lookup"><span data-stu-id="1523d-110">Configure the service with a WSHttpBinding to use a reliable session</span></span>

1. <span data-ttu-id="1523d-111">Defina un contrato de servicios para el tipo de servicio.</span><span class="sxs-lookup"><span data-stu-id="1523d-111">Define a service contract for the type of service.</span></span>

   [!code-csharp[c_HowTo_UseReliableSession#1121](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/service.cs#1121)]

1. <span data-ttu-id="1523d-112">Implemente el contrato de servicios en una clase de servicio.</span><span class="sxs-lookup"><span data-stu-id="1523d-112">Implement the service contract in a service class.</span></span> <span data-ttu-id="1523d-113">Tenga en cuenta que no se especifica la información de dirección o enlace dentro de la implementación del servicio.</span><span class="sxs-lookup"><span data-stu-id="1523d-113">Note that the address or binding information isn't specified inside the implementation of the service.</span></span> <span data-ttu-id="1523d-114">No es necesario escribir código para recuperar la información de dirección o enlace desde el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="1523d-114">You aren't required to write code to retrieve the address or binding information information from the configuration file.</span></span>

   [!code-csharp[c_HowTo_UseReliableSession#1122](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/service.cs#1122)]

1. <span data-ttu-id="1523d-115">Crear un *Web.config* archivo para configurar un extremo para la `CalculatorService` que usa el <xref:System.ServiceModel.WSHttpBinding> con sesión confiable habilitada y entrega ordenada de mensajes requerida.</span><span class="sxs-lookup"><span data-stu-id="1523d-115">Create a *Web.config* file to configure an endpoint for the `CalculatorService` that uses the <xref:System.ServiceModel.WSHttpBinding> with reliable session enabled and ordered delivery of messages required.</span></span>

   [!code-xml[c_HowTo_UseReliableSession#2111](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/common/web.config#2111)]

1. <span data-ttu-id="1523d-116">Crear un *Service.svc* archivo que contiene la línea:</span><span class="sxs-lookup"><span data-stu-id="1523d-116">Create a *Service.svc* file that contains the line:</span></span>

   ```
   <%@ServiceHost language=c# Service="CalculatorService" %>
   ```

1.  <span data-ttu-id="1523d-117">Lugar la *Service.svc* archivo en el directorio virtual de Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="1523d-117">Place the *Service.svc* file in your Internet Information Services (IIS) virtual directory.</span></span>

### <a name="configure-the-client-with-a-wshttpbinding-to-use-a-reliable-session"></a><span data-ttu-id="1523d-118">Configurar al cliente con un WSHttpBinding para utilizar una sesión confiable</span><span class="sxs-lookup"><span data-stu-id="1523d-118">Configure the client with a WSHttpBinding to use a reliable session</span></span>

1. <span data-ttu-id="1523d-119">Use la [ServiceModel Metadata Utility Tool (*Svcutil.exe*)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) desde la línea de comandos para generar código a partir de metadatos del servicio:</span><span class="sxs-lookup"><span data-stu-id="1523d-119">Use the [ServiceModel Metadata Utility Tool (*Svcutil.exe*)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) from the command line to generate code from service metadata:</span></span>

   ```console
   Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>
   ```

1. <span data-ttu-id="1523d-120">El cliente generado contiene el `ICalculator` interfaz que define el contrato de servicio que debe satisfacer la implementación del cliente.</span><span class="sxs-lookup"><span data-stu-id="1523d-120">The generated client contains the `ICalculator` interface that defines the service contract that the client implementation must satisfy.</span></span>

   [!code-csharp[C_HowTo_UseReliableSession#1221](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1221)]

1. <span data-ttu-id="1523d-121">La aplicación de cliente generada también contiene la implementación de `ClientCalculator`.</span><span class="sxs-lookup"><span data-stu-id="1523d-121">The generated client application also contains the implementation of the `ClientCalculator`.</span></span> <span data-ttu-id="1523d-122">Tenga en cuenta que la información de dirección y el enlace no se especifica en cualquier lugar dentro de la implementación del servicio.</span><span class="sxs-lookup"><span data-stu-id="1523d-122">Note that the address and binding information isn't specified anywhere inside the implementation of the service.</span></span> <span data-ttu-id="1523d-123">No es necesario escribir código para recuperar la información de dirección o enlace desde el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="1523d-123">You aren't required to write code to retrieve the address or binding information information from the configuration file.</span></span>

   [!code-csharp[C_HowTo_UseReliableSession#1222](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1222)]

1. <span data-ttu-id="1523d-124">*Svcutil.exe* también genera la configuración para el cliente que utiliza el <xref:System.ServiceModel.WSHttpBinding> clase.</span><span class="sxs-lookup"><span data-stu-id="1523d-124">*Svcutil.exe* also generates the configuration for the client that uses the <xref:System.ServiceModel.WSHttpBinding> class.</span></span> <span data-ttu-id="1523d-125">Asignar nombre al archivo de configuración *App.config* al usar [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1523d-125">Name the configuration file *App.config* when using [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].</span></span>

   [!code-xml[C_HowTo_UseReliableSession#2211](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/common/app.config#2211)]

1. <span data-ttu-id="1523d-126">Cree una instancia de la `ClientCalculator` en una aplicación y llamar a las operaciones de servicio.</span><span class="sxs-lookup"><span data-stu-id="1523d-126">Create an instance of the `ClientCalculator` in an application and call the service operations.</span></span>

   [!code-csharp[C_HowTo_UseReliableSession#1223](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1223)]

1. <span data-ttu-id="1523d-127">Compile y ejecute el cliente.</span><span class="sxs-lookup"><span data-stu-id="1523d-127">Compile and run the client.</span></span>

## <a name="example"></a><span data-ttu-id="1523d-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1523d-128">Example</span></span>

<span data-ttu-id="1523d-129">Algunos de los enlaces proporcionados por el sistema admiten de forma predeterminada las sesiones confiables.</span><span class="sxs-lookup"><span data-stu-id="1523d-129">Several of the system-provided bindings support reliable sessions by default.</span></span> <span data-ttu-id="1523d-130">Se incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="1523d-130">These include:</span></span>

- <xref:System.ServiceModel.WSDualHttpBinding>

- <xref:System.ServiceModel.NetNamedPipeBinding>

- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>

<span data-ttu-id="1523d-131">Para obtener un ejemplo de cómo crear un enlace personalizado que admite sesiones confiables, consulte [Cómo: crear un enlace personalizado de la sesión confiable con HTTPS](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md).</span><span class="sxs-lookup"><span data-stu-id="1523d-131">For an example of how to create a custom binding that supports reliable sessions, see [How to: Create a Custom Reliable Session Binding with HTTPS](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1523d-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="1523d-132">See also</span></span>

[<span data-ttu-id="1523d-133">Sesiones confiables</span><span class="sxs-lookup"><span data-stu-id="1523d-133">Reliable Sessions</span></span>](../../../../docs/framework/wcf/feature-details/reliable-sessions.md)
