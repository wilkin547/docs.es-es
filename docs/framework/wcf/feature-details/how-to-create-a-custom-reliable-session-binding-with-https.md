---
title: "Creación de un enlace personalizado de sesión confiable con HTTPS"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fa772232-da1f-4c66-8c94-e36c0584b549
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6e891f266a8159a6367a0a936d6ba11197484267
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-create-a-custom-reliable-session-binding-with-https"></a><span data-ttu-id="63163-102">Creación de un enlace personalizado de sesión confiable con HTTPS</span><span class="sxs-lookup"><span data-stu-id="63163-102">How to: Create a Custom Reliable Session Binding with HTTPS</span></span>

<span data-ttu-id="63163-103">En este tema se muestra el uso de la seguridad de transporte de capa de sockets seguros (SSL) con sesiones confiables.</span><span class="sxs-lookup"><span data-stu-id="63163-103">This topic demonstrates the use of Secure Sockets Layer (SSL) transport security with reliable sessions.</span></span> <span data-ttu-id="63163-104">Para utilizar una sesión confiable sobre HTTPS, debe crear un enlace personalizado que utilice una sesión confiable y el transporte de HTTPS.</span><span class="sxs-lookup"><span data-stu-id="63163-104">To use a reliable session over HTTPS, you must create a custom binding that uses a reliable session and the HTTPS transport.</span></span> <span data-ttu-id="63163-105">Habilitar la sesión confiable de manera imperativa mediante código o mediante declaración en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="63163-105">You enable the reliable session either imperatively by using code or declaratively in the configuration file.</span></span> <span data-ttu-id="63163-106">Este procedimiento utiliza los archivos de configuración de cliente y servicio para habilitar la sesión confiable y [  **\<httpsTransport >** ](../../../../docs/framework/configure-apps/file-schema/wcf/httpstransport.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="63163-106">This procedure uses the client and service configuration files to enable the reliable session and the [**\<httpsTransport>**](../../../../docs/framework/configure-apps/file-schema/wcf/httpstransport.md) element.</span></span>

<span data-ttu-id="63163-107">La parte clave de este procedimiento es que la  **\<extremo >** elemento de configuración contienen un `bindingConfiguration` atributo que hace referencia a una configuración de enlace personalizado denominada `reliableSessionOverHttps`.</span><span class="sxs-lookup"><span data-stu-id="63163-107">The key part of this procedure is that the **\<endpoint>** configuration element contain a `bindingConfiguration` attribute that references a custom binding configuration named `reliableSessionOverHttps`.</span></span> <span data-ttu-id="63163-108">El [  **\<enlace >** ](../../../../docs/framework/misc/binding.md) elemento de configuración hace referencia a este nombre para especificar que se utilizan una sesión confiable y el transporte HTTPS mediante la inclusión de  **\< reliableSession >** y  **\<httpsTransport >** elementos.</span><span class="sxs-lookup"><span data-stu-id="63163-108">The [**\<binding>**](../../../../docs/framework/misc/binding.md) configuration element references this name to specify that a reliable session and the HTTPS transport are used by including **\<reliableSession>** and **\<httpsTransport>** elements.</span></span>

<span data-ttu-id="63163-109">Para la copia de origen de este ejemplo, vea [personalizado de enlace sesión confiable sobre HTTPS](../../../../docs/framework/wcf/samples/custom-binding-reliable-session-over-https.md).</span><span class="sxs-lookup"><span data-stu-id="63163-109">For the source copy of this example, see [Custom Binding Reliable Session over HTTPS](../../../../docs/framework/wcf/samples/custom-binding-reliable-session-over-https.md).</span></span>

### <a name="configure-the-service-with-a-custombinding-to-use-a-reliable-session-with-https"></a><span data-ttu-id="63163-110">Configurar el servicio con un CustomBinding para utilizar una sesión confiable con HTTPS</span><span class="sxs-lookup"><span data-stu-id="63163-110">Configure the service with a CustomBinding to use a reliable session with HTTPS</span></span>

1. <span data-ttu-id="63163-111">Defina un contrato de servicios para el tipo de servicio.</span><span class="sxs-lookup"><span data-stu-id="63163-111">Define a service contract for the type of service.</span></span>

   [!code-csharp[c_HowTo_CreateReliableSessionHTTPS#1121](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/service.cs#1121)]

1. <span data-ttu-id="63163-112">Implemente el contrato de servicios en una clase de servicio.</span><span class="sxs-lookup"><span data-stu-id="63163-112">Implement the service contract in a service class.</span></span> <span data-ttu-id="63163-113">Tenga en cuenta que no se especifica la información de dirección o enlace dentro de la implementación del servicio.</span><span class="sxs-lookup"><span data-stu-id="63163-113">Note that the address or binding information isn't specified inside the implementation of the service.</span></span> <span data-ttu-id="63163-114">No es necesario escribir código para recuperar la información de dirección o enlace desde el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="63163-114">You aren't required to write code to retrieve the address or binding information from the configuration file.</span></span>

   [!code-csharp[c_HowTo_CreateReliableSessionHTTPS#1122](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/service.cs#1122)]

1. <span data-ttu-id="63163-115">Crear un *Web.config* archivo para configurar un extremo para la `CalculatorService` con un enlace personalizado denominado `reliableSessionOverHttps` que utiliza una sesión confiable y el transporte HTTPS.</span><span class="sxs-lookup"><span data-stu-id="63163-115">Create a *Web.config* file to configure an endpoint for the `CalculatorService` with a custom binding named `reliableSessionOverHttps` that uses a reliable session and the HTTPS transport.</span></span>

   [!code-xml[c_HowTo_CreateReliableSessionHTTPS#2111](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/common/web.config#2111)]

1. <span data-ttu-id="63163-116">Crear un *Service.svc* archivo que contiene la línea:</span><span class="sxs-lookup"><span data-stu-id="63163-116">Create a *Service.svc* file that contains the line:</span></span>

   ```
   <%@ServiceHost language=c# Service="CalculatorService" %>
   ```

1. <span data-ttu-id="63163-117">Lugar la *Service.svc* archivo en el directorio virtual de Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="63163-117">Place the *Service.svc* file in your Internet Information Services (IIS) virtual directory.</span></span>

### <a name="configure-the-client-with-a-custombinding-to-use-a-reliable-session-with-https"></a><span data-ttu-id="63163-118">Configurar al cliente con un CustomBinding para utilizar una sesión confiable con HTTPS</span><span class="sxs-lookup"><span data-stu-id="63163-118">Configure the client with a CustomBinding to use a reliable session with HTTPS</span></span>

1. <span data-ttu-id="63163-119">Use la [ServiceModel Metadata Utility Tool (*Svcutil.exe*)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) desde la línea de comandos para generar código a partir de metadatos del servicio.</span><span class="sxs-lookup"><span data-stu-id="63163-119">Use the [ServiceModel Metadata Utility Tool (*Svcutil.exe*)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) from the command line to generate code from service metadata.</span></span>

   ```console
   Svcutil.exe <Metadata Exchange (MEX) address or HTTP GET address>
   ```

1. <span data-ttu-id="63163-120">El cliente que se genera contiene la `ICalculator` interfaz que define el contrato de servicio que debe satisfacer la implementación del cliente.</span><span class="sxs-lookup"><span data-stu-id="63163-120">The client that's generated contains the `ICalculator` interface that defines the service contract that the client implementation must satisfy.</span></span>

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1221](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1221)]

1. <span data-ttu-id="63163-121">La aplicación de cliente generada también contiene la implementación de `ClientCalculator`.</span><span class="sxs-lookup"><span data-stu-id="63163-121">The generated client application also contains the implementation of the `ClientCalculator`.</span></span> <span data-ttu-id="63163-122">Tenga en cuenta que no se especifica la información de enlace y dirección de la implementación del servicio.</span><span class="sxs-lookup"><span data-stu-id="63163-122">Note that the address and binding information isn't specified inside the implementation of the service.</span></span> <span data-ttu-id="63163-123">No es necesario escribir código para recuperar la información de enlace y la dirección del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="63163-123">You aren't required to write code to retrieve the address and binding information from the configuration file.</span></span>

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1222](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1222)]

1. <span data-ttu-id="63163-124">Configurar un enlace personalizado denominado `reliableSessionOverHttps` para usar el transporte HTTPS y sesiones confiables.</span><span class="sxs-lookup"><span data-stu-id="63163-124">Configure a custom binding named `reliableSessionOverHttps` to use the HTTPS transport and reliable sessions.</span></span>

   [!code-xml[C_HowTo_CreateReliableSessionHTTPS#2211](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/common/app.config#2211)]

1. <span data-ttu-id="63163-125">Cree una instancia de `ClientCalculator` en una aplicación y, a continuación, llame a las operaciones del servicio.</span><span class="sxs-lookup"><span data-stu-id="63163-125">Create an instance of the `ClientCalculator` in an application and then call the service operations.</span></span>

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1223](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1223)]

1. <span data-ttu-id="63163-126">Compile y ejecute el cliente.</span><span class="sxs-lookup"><span data-stu-id="63163-126">Compile and run the client.</span></span>  

## <a name="net-framework-security"></a><span data-ttu-id="63163-127">seguridad en .NET Framework</span><span class="sxs-lookup"><span data-stu-id="63163-127">.NET Framework security</span></span>

<span data-ttu-id="63163-128">Dado que el certificado utilizado en este ejemplo es un certificado de prueba creado con *Makecert.exe*, aparecerá una alerta de seguridad cuando intenta tener acceso a una dirección HTTPS, como `https://localhost/servicemodelsamples/service.svc`, desde el explorador.</span><span class="sxs-lookup"><span data-stu-id="63163-128">Because the certificate used in this sample is a test certificate created with *Makecert.exe*, a security alert appears when you try to access an HTTPS address, such as `https://localhost/servicemodelsamples/service.svc`, from your browser.</span></span>

## <a name="see-also"></a><span data-ttu-id="63163-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="63163-129">See also</span></span>

[<span data-ttu-id="63163-130">Sesiones confiables</span><span class="sxs-lookup"><span data-stu-id="63163-130">Reliable Sessions</span></span>](../../../../docs/framework/wcf/feature-details/reliable-sessions.md)
