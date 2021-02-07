---
description: 'Más información acerca de cómo: crear un enlace de sesión confiable personalizado con HTTPS'
title: Procedimiento para crear un enlace personalizado de sesión confiable con HTTPS
ms.date: 03/30/2017
ms.assetid: fa772232-da1f-4c66-8c94-e36c0584b549
ms.openlocfilehash: 97e0386c3694552099a623a319f566fa4db2a39b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99756180"
---
# <a name="how-to-create-a-custom-reliable-session-binding-with-https"></a><span data-ttu-id="01e0a-103">Procedimiento para crear un enlace personalizado de sesión confiable con HTTPS</span><span class="sxs-lookup"><span data-stu-id="01e0a-103">How to: Create a Custom Reliable Session Binding with HTTPS</span></span>

<span data-ttu-id="01e0a-104">En este tema se muestra el uso de la seguridad de transporte de capa de sockets seguros (SSL) con sesiones confiables.</span><span class="sxs-lookup"><span data-stu-id="01e0a-104">This topic demonstrates the use of Secure Sockets Layer (SSL) transport security with reliable sessions.</span></span> <span data-ttu-id="01e0a-105">Para utilizar una sesión confiable sobre HTTPS, debe crear un enlace personalizado que utilice una sesión confiable y el transporte de HTTPS.</span><span class="sxs-lookup"><span data-stu-id="01e0a-105">To use a reliable session over HTTPS, you must create a custom binding that uses a reliable session and the HTTPS transport.</span></span> <span data-ttu-id="01e0a-106">Puede habilitar la sesión confiable de manera imperativa mediante el uso de código o mediante declaración en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="01e0a-106">You enable the reliable session either imperatively by using code or declaratively in the configuration file.</span></span> <span data-ttu-id="01e0a-107">Este procedimiento utiliza los archivos de configuración de servicio y cliente para habilitar la sesión confiable y el [**\<httpsTransport>**](../../configure-apps/file-schema/wcf/httpstransport.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="01e0a-107">This procedure uses the client and service configuration files to enable the reliable session and the [**\<httpsTransport>**](../../configure-apps/file-schema/wcf/httpstransport.md) element.</span></span>

<span data-ttu-id="01e0a-108">La parte clave de este procedimiento es que el **\<endpoint>** elemento de configuración contiene un `bindingConfiguration` atributo que hace referencia a una configuración de enlace personalizada denominada `reliableSessionOverHttps` .</span><span class="sxs-lookup"><span data-stu-id="01e0a-108">The key part of this procedure is that the **\<endpoint>** configuration element contain a `bindingConfiguration` attribute that references a custom binding configuration named `reliableSessionOverHttps`.</span></span> <span data-ttu-id="01e0a-109">El [**\<binding>**](../../configure-apps/file-schema/wcf/bindings.md) elemento de configuración hace referencia a este nombre para especificar que se utilizan una sesión confiable y el transporte https mediante la inclusión **\<reliableSession>** de **\<httpsTransport>** los elementos y.</span><span class="sxs-lookup"><span data-stu-id="01e0a-109">The [**\<binding>**](../../configure-apps/file-schema/wcf/bindings.md) configuration element references this name to specify that a reliable session and the HTTPS transport are used by including **\<reliableSession>** and **\<httpsTransport>** elements.</span></span>

<span data-ttu-id="01e0a-110">Para la copia de origen de este ejemplo, consulte el [enlace personalizado de la sesión confiable sobre https](../samples/custom-binding-reliable-session-over-https.md).</span><span class="sxs-lookup"><span data-stu-id="01e0a-110">For the source copy of this example, see [Custom Binding Reliable Session over HTTPS](../samples/custom-binding-reliable-session-over-https.md).</span></span>

### <a name="configure-the-service-with-a-custombinding-to-use-a-reliable-session-with-https"></a><span data-ttu-id="01e0a-111">Configurar el servicio con un CustomBinding para utilizar una sesión confiable con HTTPS</span><span class="sxs-lookup"><span data-stu-id="01e0a-111">Configure the service with a CustomBinding to use a reliable session with HTTPS</span></span>

1. <span data-ttu-id="01e0a-112">Defina un contrato de servicios para el tipo de servicio.</span><span class="sxs-lookup"><span data-stu-id="01e0a-112">Define a service contract for the type of service.</span></span>

   [!code-csharp[c_HowTo_CreateReliableSessionHTTPS#1121](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/service.cs#1121)]

1. <span data-ttu-id="01e0a-113">Implemente el contrato de servicios en una clase de servicio.</span><span class="sxs-lookup"><span data-stu-id="01e0a-113">Implement the service contract in a service class.</span></span> <span data-ttu-id="01e0a-114">Tenga en cuenta que la información de dirección o enlace no se especifica dentro de la implementación del servicio.</span><span class="sxs-lookup"><span data-stu-id="01e0a-114">Note that the address or binding information isn't specified inside the implementation of the service.</span></span> <span data-ttu-id="01e0a-115">No es necesario escribir código para recuperar la dirección o la información de enlace del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="01e0a-115">You aren't required to write code to retrieve the address or binding information from the configuration file.</span></span>

   [!code-csharp[c_HowTo_CreateReliableSessionHTTPS#1122](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/service.cs#1122)]

1. <span data-ttu-id="01e0a-116">Cree un archivo de *Web.config* para configurar un extremo para el `CalculatorService` con un enlace personalizado denominado `reliableSessionOverHttps` que utiliza una sesión confiable y el transporte https.</span><span class="sxs-lookup"><span data-stu-id="01e0a-116">Create a *Web.config* file to configure an endpoint for the `CalculatorService` with a custom binding named `reliableSessionOverHttps` that uses a reliable session and the HTTPS transport.</span></span>

   [!code-xml[c_HowTo_CreateReliableSessionHTTPS#2111](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/common/web.config#2111)]

1. <span data-ttu-id="01e0a-117">Cree un archivo *Service. SVC* que contenga la línea:</span><span class="sxs-lookup"><span data-stu-id="01e0a-117">Create a *Service.svc* file that contains the line:</span></span>

   `<%@ServiceHost language=c# Service="CalculatorService" %>`

1. <span data-ttu-id="01e0a-118">Coloque el archivo *Service. SVC* en el directorio virtual de Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="01e0a-118">Place the *Service.svc* file in your Internet Information Services (IIS) virtual directory.</span></span>

### <a name="configure-the-client-with-a-custombinding-to-use-a-reliable-session-with-https"></a><span data-ttu-id="01e0a-119">Configurar el cliente con un CustomBinding para utilizar una sesión confiable con HTTPS</span><span class="sxs-lookup"><span data-stu-id="01e0a-119">Configure the client with a CustomBinding to use a reliable session with HTTPS</span></span>

1. <span data-ttu-id="01e0a-120">Use la [herramienta de utilidad de metadatos de ServiceModel (*Svcutil.exe*)](../servicemodel-metadata-utility-tool-svcutil-exe.md) desde la línea de comandos para generar código a partir de los metadatos del servicio.</span><span class="sxs-lookup"><span data-stu-id="01e0a-120">Use the [ServiceModel Metadata Utility Tool (*Svcutil.exe*)](../servicemodel-metadata-utility-tool-svcutil-exe.md) from the command line to generate code from service metadata.</span></span>

   ```console
   Svcutil.exe <Metadata Exchange (MEX) address or HTTP GET address>
   ```

1. <span data-ttu-id="01e0a-121">El cliente que se genera contiene la `ICalculator` interfaz que define el contrato de servicio que la implementación del cliente debe cumplir.</span><span class="sxs-lookup"><span data-stu-id="01e0a-121">The client that's generated contains the `ICalculator` interface that defines the service contract that the client implementation must satisfy.</span></span>

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1221](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1221)]

1. <span data-ttu-id="01e0a-122">La aplicación de cliente generada también contiene la implementación de `ClientCalculator`.</span><span class="sxs-lookup"><span data-stu-id="01e0a-122">The generated client application also contains the implementation of the `ClientCalculator`.</span></span> <span data-ttu-id="01e0a-123">Tenga en cuenta que la información de dirección y enlace no se especifica dentro de la implementación del servicio.</span><span class="sxs-lookup"><span data-stu-id="01e0a-123">Note that the address and binding information isn't specified inside the implementation of the service.</span></span> <span data-ttu-id="01e0a-124">No es necesario escribir código para recuperar la dirección y la información de enlace del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="01e0a-124">You aren't required to write code to retrieve the address and binding information from the configuration file.</span></span>

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1222](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1222)]

1. <span data-ttu-id="01e0a-125">Configure un enlace personalizado denominado `reliableSessionOverHttps` para usar el transporte https y las sesiones de confianza.</span><span class="sxs-lookup"><span data-stu-id="01e0a-125">Configure a custom binding named `reliableSessionOverHttps` to use the HTTPS transport and reliable sessions.</span></span>

   [!code-xml[C_HowTo_CreateReliableSessionHTTPS#2211](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/common/app.config#2211)]

1. <span data-ttu-id="01e0a-126">Cree una instancia de `ClientCalculator` en una aplicación y, a continuación, llame a las operaciones del servicio.</span><span class="sxs-lookup"><span data-stu-id="01e0a-126">Create an instance of the `ClientCalculator` in an application and then call the service operations.</span></span>

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1223](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1223)]

1. <span data-ttu-id="01e0a-127">Compile y ejecute el cliente.</span><span class="sxs-lookup"><span data-stu-id="01e0a-127">Compile and run the client.</span></span>  

## <a name="net-framework-security"></a><span data-ttu-id="01e0a-128">seguridad en .NET Framework</span><span class="sxs-lookup"><span data-stu-id="01e0a-128">.NET Framework security</span></span>

<span data-ttu-id="01e0a-129">Dado que el certificado utilizado en este ejemplo es un certificado de prueba creado con *Makecert.exe*, aparece una alerta de seguridad al intentar obtener acceso a una dirección https, como `https://localhost/servicemodelsamples/service.svc` , desde el explorador.</span><span class="sxs-lookup"><span data-stu-id="01e0a-129">Because the certificate used in this sample is a test certificate created with *Makecert.exe*, a security alert appears when you try to access an HTTPS address, such as `https://localhost/servicemodelsamples/service.svc`, from your browser.</span></span>

## <a name="see-also"></a><span data-ttu-id="01e0a-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="01e0a-130">See also</span></span>

- [<span data-ttu-id="01e0a-131">Sesiones de confianza</span><span class="sxs-lookup"><span data-stu-id="01e0a-131">Reliable Sessions</span></span>](reliable-sessions.md)
