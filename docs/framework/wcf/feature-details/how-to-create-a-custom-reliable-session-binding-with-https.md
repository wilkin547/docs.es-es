---
title: Procedimiento para crear un enlace personalizado de sesión confiable con HTTPS
ms.date: 03/30/2017
ms.assetid: fa772232-da1f-4c66-8c94-e36c0584b549
ms.openlocfilehash: 7f22eeaae39b4d9a83c77c7f3e9db1d7d3f04e8e
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/11/2019
ms.locfileid: "70895201"
---
# <a name="how-to-create-a-custom-reliable-session-binding-with-https"></a><span data-ttu-id="0b4ea-102">Procedimiento para crear un enlace personalizado de sesión confiable con HTTPS</span><span class="sxs-lookup"><span data-stu-id="0b4ea-102">How to: Create a Custom Reliable Session Binding with HTTPS</span></span>

<span data-ttu-id="0b4ea-103">En este tema se muestra el uso de la seguridad de transporte de capa de sockets seguros (SSL) con sesiones confiables.</span><span class="sxs-lookup"><span data-stu-id="0b4ea-103">This topic demonstrates the use of Secure Sockets Layer (SSL) transport security with reliable sessions.</span></span> <span data-ttu-id="0b4ea-104">Para utilizar una sesión confiable sobre HTTPS, debe crear un enlace personalizado que utilice una sesión confiable y el transporte de HTTPS.</span><span class="sxs-lookup"><span data-stu-id="0b4ea-104">To use a reliable session over HTTPS, you must create a custom binding that uses a reliable session and the HTTPS transport.</span></span> <span data-ttu-id="0b4ea-105">Puede habilitar la sesión confiable de manera imperativa mediante el uso de código o mediante declaración en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="0b4ea-105">You enable the reliable session either imperatively by using code or declaratively in the configuration file.</span></span> <span data-ttu-id="0b4ea-106">Este procedimiento utiliza los archivos de configuración de servicio y cliente para habilitar la sesión confiable y el elemento [ **\<> de httpsTransport**](../../../../docs/framework/configure-apps/file-schema/wcf/httpstransport.md) .</span><span class="sxs-lookup"><span data-stu-id="0b4ea-106">This procedure uses the client and service configuration files to enable the reliable session and the [**\<httpsTransport>**](../../../../docs/framework/configure-apps/file-schema/wcf/httpstransport.md) element.</span></span>

<span data-ttu-id="0b4ea-107">La parte clave de este procedimiento es que el  **\<punto de conexión >** elemento de `bindingConfiguration` configuración contiene un atributo que hace referencia a `reliableSessionOverHttps`una configuración de enlace personalizada denominada.</span><span class="sxs-lookup"><span data-stu-id="0b4ea-107">The key part of this procedure is that the **\<endpoint>** configuration element contain a `bindingConfiguration` attribute that references a custom binding configuration named `reliableSessionOverHttps`.</span></span> <span data-ttu-id="0b4ea-108">El elemento de configuración de [ **\<enlace >** ](../../../../docs/framework/misc/binding.md) hace referencia a este nombre para especificar que se usan una sesión confiable y el transporte https incluyendo  **\<reliableSession >** y **\<httpsTransport >** elementos.</span><span class="sxs-lookup"><span data-stu-id="0b4ea-108">The [**\<binding>**](../../../../docs/framework/misc/binding.md) configuration element references this name to specify that a reliable session and the HTTPS transport are used by including **\<reliableSession>** and **\<httpsTransport>** elements.</span></span>

<span data-ttu-id="0b4ea-109">Para la copia de origen de este ejemplo, consulte el [enlace personalizado de la sesión confiable sobre https](../../../../docs/framework/wcf/samples/custom-binding-reliable-session-over-https.md).</span><span class="sxs-lookup"><span data-stu-id="0b4ea-109">For the source copy of this example, see [Custom Binding Reliable Session over HTTPS](../../../../docs/framework/wcf/samples/custom-binding-reliable-session-over-https.md).</span></span>

### <a name="configure-the-service-with-a-custombinding-to-use-a-reliable-session-with-https"></a><span data-ttu-id="0b4ea-110">Configurar el servicio con un CustomBinding para utilizar una sesión confiable con HTTPS</span><span class="sxs-lookup"><span data-stu-id="0b4ea-110">Configure the service with a CustomBinding to use a reliable session with HTTPS</span></span>

1. <span data-ttu-id="0b4ea-111">Defina un contrato de servicios para el tipo de servicio.</span><span class="sxs-lookup"><span data-stu-id="0b4ea-111">Define a service contract for the type of service.</span></span>

   [!code-csharp[c_HowTo_CreateReliableSessionHTTPS#1121](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/service.cs#1121)]

1. <span data-ttu-id="0b4ea-112">Implemente el contrato de servicios en una clase de servicio.</span><span class="sxs-lookup"><span data-stu-id="0b4ea-112">Implement the service contract in a service class.</span></span> <span data-ttu-id="0b4ea-113">Tenga en cuenta que la información de dirección o enlace no se especifica dentro de la implementación del servicio.</span><span class="sxs-lookup"><span data-stu-id="0b4ea-113">Note that the address or binding information isn't specified inside the implementation of the service.</span></span> <span data-ttu-id="0b4ea-114">No es necesario escribir código para recuperar la dirección o la información de enlace del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="0b4ea-114">You aren't required to write code to retrieve the address or binding information from the configuration file.</span></span>

   [!code-csharp[c_HowTo_CreateReliableSessionHTTPS#1122](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/service.cs#1122)]

1. <span data-ttu-id="0b4ea-115">Cree un archivo *Web. config* para configurar un extremo para el `CalculatorService` con un enlace personalizado denominado `reliableSessionOverHttps` que use una sesión confiable y el transporte https.</span><span class="sxs-lookup"><span data-stu-id="0b4ea-115">Create a *Web.config* file to configure an endpoint for the `CalculatorService` with a custom binding named `reliableSessionOverHttps` that uses a reliable session and the HTTPS transport.</span></span>

   [!code-xml[c_HowTo_CreateReliableSessionHTTPS#2111](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/common/web.config#2111)]

1. <span data-ttu-id="0b4ea-116">Cree un archivo *Service. SVC* que contenga la línea:</span><span class="sxs-lookup"><span data-stu-id="0b4ea-116">Create a *Service.svc* file that contains the line:</span></span>

   `<%@ServiceHost language=c# Service="CalculatorService" %>`

1. <span data-ttu-id="0b4ea-117">Coloque el archivo *Service. SVC* en el directorio virtual de Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="0b4ea-117">Place the *Service.svc* file in your Internet Information Services (IIS) virtual directory.</span></span>

### <a name="configure-the-client-with-a-custombinding-to-use-a-reliable-session-with-https"></a><span data-ttu-id="0b4ea-118">Configurar el cliente con un CustomBinding para utilizar una sesión confiable con HTTPS</span><span class="sxs-lookup"><span data-stu-id="0b4ea-118">Configure the client with a CustomBinding to use a reliable session with HTTPS</span></span>

1. <span data-ttu-id="0b4ea-119">Use la [herramienta de utilidad de metadatos de ServiceModel (*SvcUtil. exe*)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) desde la línea de comandos para generar código a partir de los metadatos del servicio.</span><span class="sxs-lookup"><span data-stu-id="0b4ea-119">Use the [ServiceModel Metadata Utility Tool (*Svcutil.exe*)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) from the command line to generate code from service metadata.</span></span>

   ```console
   Svcutil.exe <Metadata Exchange (MEX) address or HTTP GET address>
   ```

1. <span data-ttu-id="0b4ea-120">El cliente que se genera contiene la `ICalculator` interfaz que define el contrato de servicio que la implementación del cliente debe cumplir.</span><span class="sxs-lookup"><span data-stu-id="0b4ea-120">The client that's generated contains the `ICalculator` interface that defines the service contract that the client implementation must satisfy.</span></span>

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1221](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1221)]

1. <span data-ttu-id="0b4ea-121">La aplicación de cliente generada también contiene la implementación de `ClientCalculator`.</span><span class="sxs-lookup"><span data-stu-id="0b4ea-121">The generated client application also contains the implementation of the `ClientCalculator`.</span></span> <span data-ttu-id="0b4ea-122">Tenga en cuenta que la información de dirección y enlace no se especifica dentro de la implementación del servicio.</span><span class="sxs-lookup"><span data-stu-id="0b4ea-122">Note that the address and binding information isn't specified inside the implementation of the service.</span></span> <span data-ttu-id="0b4ea-123">No es necesario escribir código para recuperar la dirección y la información de enlace del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="0b4ea-123">You aren't required to write code to retrieve the address and binding information from the configuration file.</span></span>

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1222](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1222)]

1. <span data-ttu-id="0b4ea-124">Configure un enlace personalizado `reliableSessionOverHttps` denominado para usar el transporte https y las sesiones de confianza.</span><span class="sxs-lookup"><span data-stu-id="0b4ea-124">Configure a custom binding named `reliableSessionOverHttps` to use the HTTPS transport and reliable sessions.</span></span>

   [!code-xml[C_HowTo_CreateReliableSessionHTTPS#2211](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/common/app.config#2211)]

1. <span data-ttu-id="0b4ea-125">Cree una instancia de `ClientCalculator` en una aplicación y, a continuación, llame a las operaciones del servicio.</span><span class="sxs-lookup"><span data-stu-id="0b4ea-125">Create an instance of the `ClientCalculator` in an application and then call the service operations.</span></span>

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1223](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1223)]

1. <span data-ttu-id="0b4ea-126">Compile y ejecute el cliente.</span><span class="sxs-lookup"><span data-stu-id="0b4ea-126">Compile and run the client.</span></span>  

## <a name="net-framework-security"></a><span data-ttu-id="0b4ea-127">seguridad en .NET Framework</span><span class="sxs-lookup"><span data-stu-id="0b4ea-127">.NET Framework security</span></span>

<span data-ttu-id="0b4ea-128">Dado que el certificado utilizado en este ejemplo es un certificado de prueba creado con *Makecert. exe*, aparecerá una alerta de seguridad al intentar obtener acceso a una dirección https `https://localhost/servicemodelsamples/service.svc`, como, desde el explorador.</span><span class="sxs-lookup"><span data-stu-id="0b4ea-128">Because the certificate used in this sample is a test certificate created with *Makecert.exe*, a security alert appears when you try to access an HTTPS address, such as `https://localhost/servicemodelsamples/service.svc`, from your browser.</span></span>

## <a name="see-also"></a><span data-ttu-id="0b4ea-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="0b4ea-129">See also</span></span>

- [<span data-ttu-id="0b4ea-130">Sesiones de confianza</span><span class="sxs-lookup"><span data-stu-id="0b4ea-130">Reliable Sessions</span></span>](../../../../docs/framework/wcf/feature-details/reliable-sessions.md)
