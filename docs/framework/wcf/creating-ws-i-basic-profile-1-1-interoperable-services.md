---
title: Creación de servicios interoperables de WS-I Basic Profile 1.1
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- configuration [WCF], interoperable services
ms.assetid: 91b70a21-8f5c-4679-808c-2ed5fa6b2013
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: fa561e5019bcf90e93da669f93cbce51d02e89dc
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2018
---
# <a name="creating-ws-i-basic-profile-11-interoperable-services"></a><span data-ttu-id="066ed-102">Creación de servicios interoperables de WS-I Basic Profile 1.1</span><span class="sxs-lookup"><span data-stu-id="066ed-102">Creating WS-I Basic Profile 1.1 Interoperable Services</span></span>
<span data-ttu-id="066ed-103">Para configurar un extremo del servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] para ser interoperable con clientes de servicios Web [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="066ed-103">To configure a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service endpoint to be interoperable with [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] Web service clients:</span></span>  
  
-   <span data-ttu-id="066ed-104">Utilice el tipo <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType> como tipo de enlace para su extremo de servicio.</span><span class="sxs-lookup"><span data-stu-id="066ed-104">Use the <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType> type as the binding type for your service endpoint.</span></span>  
  
-   <span data-ttu-id="066ed-105">No utilice devolución de llamada sino características de contrato de sesión o comportamientos de transacción en su punto de conexión de servicio</span><span class="sxs-lookup"><span data-stu-id="066ed-105">Do not use callback and session contract features or transaction behaviors on your service endpoint</span></span>  
  
 <span data-ttu-id="066ed-106">Puede habilitar opcionalmente el soporte para HTTPS y la autenticación del cliente del nivel de transporte en el enlace.</span><span class="sxs-lookup"><span data-stu-id="066ed-106">You can optionally enable support for HTTPS and transport-level client authentication on the binding.</span></span>  
  
 <span data-ttu-id="066ed-107">Las características siguientes de la clase <xref:System.ServiceModel.BasicHttpBinding> requieren la funcionalidad más allá de WS-I Basic Profile 1.1:</span><span class="sxs-lookup"><span data-stu-id="066ed-107">The following features of the <xref:System.ServiceModel.BasicHttpBinding> class require functionality beyond WS-I Basic Profile 1.1:</span></span>  
  
-   <span data-ttu-id="066ed-108">Codificación de mensajes del Mecanismo de optimización de transmisión del mensajes (MTOM) controlada por la propiedad <xref:System.ServiceModel.BasicHttpBinding.MessageEncoding%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="066ed-108">Message Transmission Optimization Mechanism (MTOM) message encoding controlled by the <xref:System.ServiceModel.BasicHttpBinding.MessageEncoding%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="066ed-109">Deje esta propiedad en su valor predeterminado, que es <xref:System.ServiceModel.WSMessageEncoding.Text?displayProperty=nameWithType> para no utilizar MTOM.</span><span class="sxs-lookup"><span data-stu-id="066ed-109">Leave  this property at its default value, which is <xref:System.ServiceModel.WSMessageEncoding.Text?displayProperty=nameWithType> to not use MTOM.</span></span>  
  
-   <span data-ttu-id="066ed-110">La seguridad de mensaje que controla el valor <xref:System.ServiceModel.BasicHttpBinding.Security%2A?displayProperty=nameWithType> proporciona compatibilidad con WS-Security conforme a WS-I Basic Security Profile 1.0.</span><span class="sxs-lookup"><span data-stu-id="066ed-110">Message security controlled by the <xref:System.ServiceModel.BasicHttpBinding.Security%2A?displayProperty=nameWithType> value provides WS-Security support compliant with WS-I Basic Security Profile 1.0.</span></span> <span data-ttu-id="066ed-111">Deje esta propiedad en su valor predeterminado, que es <xref:System.ServiceModel.SecurityMode.Transport?displayProperty=nameWithType>, para no usar WS-Security.</span><span class="sxs-lookup"><span data-stu-id="066ed-111">Leave this property at its default value, which is <xref:System.ServiceModel.SecurityMode.Transport?displayProperty=nameWithType> to not use WS-Security.</span></span>  
  
 <span data-ttu-id="066ed-112">Para que los metadatos una [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] servicio disponible para [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)], use las herramientas de generación de cliente de servicio Web: [Web Services Description Language Tool (Wsdl.exe)](http://msdn.microsoft.com/library/b9210348-8bc2-4367-8c91-d1a04b403e88), [(Web Services Discovery Tool Disco.exe)](http://msdn.microsoft.com/library/acd88078-c581-42bc-94ca-6633e2851979)y el `Add Web Reference` característica en Visual Studio; también debe habilitar la publicación de metadatos.</span><span class="sxs-lookup"><span data-stu-id="066ed-112">To make the metadata for a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service available to [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)], use the Web service client generation tools: [Web Services Description Language Tool (Wsdl.exe)](http://msdn.microsoft.com/library/b9210348-8bc2-4367-8c91-d1a04b403e88), [Web Services Discovery Tool (Disco.exe)](http://msdn.microsoft.com/library/acd88078-c581-42bc-94ca-6633e2851979), and the `Add Web Reference` feature in Visual Studio; you must enable metadata publication.</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="066ed-113"> [Extremos de metadatos de publicación](../../../docs/framework/wcf/publishing-metadata-endpoints.md).</span><span class="sxs-lookup"><span data-stu-id="066ed-113"> [Publishing Metadata Endpoints](../../../docs/framework/wcf/publishing-metadata-endpoints.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="066ed-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="066ed-114">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="066ed-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="066ed-115">Description</span></span>  
 <span data-ttu-id="066ed-116">Ejemplo de código siguiente muestra cómo agregar un [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] punto de conexión que es compatible con [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] clientes de servicios en código y, o bien, en un archivo de configuración Web.</span><span class="sxs-lookup"><span data-stu-id="066ed-116">The following example code demonstrates how to add a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] endpoint that is compatible with [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] Web service clients in code and, alternatively, in a configuration file.</span></span>  
  
### <a name="code"></a><span data-ttu-id="066ed-117">Código</span><span class="sxs-lookup"><span data-stu-id="066ed-117">Code</span></span>  
 [!code-csharp[C_HowTo-WCFServiceAndASMXClient#0](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/cs/program.cs#0)]
 [!code-vb[C_HowTo-WCFServiceAndASMXClient#0](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/vb/program.vb#0)]  
 [!code-xml[C_HowTo-WCFServiceAndASMXClient#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/common/app.config#1)]  
  
## <a name="see-also"></a><span data-ttu-id="066ed-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="066ed-118">See Also</span></span>  
 [<span data-ttu-id="066ed-119">Interoperabilidad con servicios web ASP.NET</span><span class="sxs-lookup"><span data-stu-id="066ed-119">Interoperability with ASP.NET Web Services</span></span>](../../../docs/framework/wcf/feature-details/interop-with-aspnet-web-services.md)
