---
title: Creación de servicios interoperables de WS-I Basic Profile 1.1
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- configuration [WCF], interoperable services
ms.assetid: 91b70a21-8f5c-4679-808c-2ed5fa6b2013
ms.openlocfilehash: fd7828cccb1a19a17e899525d863021d3670fbdd
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389760"
---
# <a name="creating-ws-i-basic-profile-11-interoperable-services"></a><span data-ttu-id="ce2d9-102">Creación de servicios interoperables de WS-I Basic Profile 1.1</span><span class="sxs-lookup"><span data-stu-id="ce2d9-102">Creating WS-I Basic Profile 1.1 Interoperable Services</span></span>
<span data-ttu-id="ce2d9-103">Para configurar un extremo de servicio WCF para que sea interoperable con ASP.NET clientes de servicio Web:</span><span class="sxs-lookup"><span data-stu-id="ce2d9-103">To configure a WCF service endpoint to be interoperable with ASP.NET Web service clients:</span></span>  
  
- <span data-ttu-id="ce2d9-104">Utilice el tipo <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType> como tipo de enlace para su extremo de servicio.</span><span class="sxs-lookup"><span data-stu-id="ce2d9-104">Use the <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType> type as the binding type for your service endpoint.</span></span>  
  
- <span data-ttu-id="ce2d9-105">No utilice devolución de llamada sino características de contrato de sesión o comportamientos de transacción en su extremo de servicio</span><span class="sxs-lookup"><span data-stu-id="ce2d9-105">Do not use callback and session contract features or transaction behaviors on your service endpoint</span></span>  
  
<span data-ttu-id="ce2d9-106">Puede habilitar opcionalmente el soporte para HTTPS y la autenticación del cliente del nivel de transporte en el enlace.</span><span class="sxs-lookup"><span data-stu-id="ce2d9-106">You can optionally enable support for HTTPS and transport-level client authentication on the binding.</span></span>  
  
<span data-ttu-id="ce2d9-107">Las características siguientes de la clase <xref:System.ServiceModel.BasicHttpBinding> requieren la funcionalidad más allá de WS-I Basic Profile 1.1:</span><span class="sxs-lookup"><span data-stu-id="ce2d9-107">The following features of the <xref:System.ServiceModel.BasicHttpBinding> class require functionality beyond WS-I Basic Profile 1.1:</span></span>  
  
- <span data-ttu-id="ce2d9-108">Codificación de mensajes del Mecanismo de optimización de transmisión del mensajes (MTOM) controlada por la propiedad <xref:System.ServiceModel.BasicHttpBinding.MessageEncoding%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ce2d9-108">Message Transmission Optimization Mechanism (MTOM) message encoding controlled by the <xref:System.ServiceModel.BasicHttpBinding.MessageEncoding%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="ce2d9-109">Deje esta propiedad en su valor predeterminado, que es <xref:System.ServiceModel.WSMessageEncoding.Text?displayProperty=nameWithType> para no utilizar MTOM.</span><span class="sxs-lookup"><span data-stu-id="ce2d9-109">Leave  this property at its default value, which is <xref:System.ServiceModel.WSMessageEncoding.Text?displayProperty=nameWithType> to not use MTOM.</span></span>  
  
- <span data-ttu-id="ce2d9-110">La seguridad de mensaje que controla el valor <xref:System.ServiceModel.BasicHttpBinding.Security%2A?displayProperty=nameWithType> proporciona compatibilidad con WS-Security conforme a WS-I Basic Security Profile 1.0.</span><span class="sxs-lookup"><span data-stu-id="ce2d9-110">Message security controlled by the <xref:System.ServiceModel.BasicHttpBinding.Security%2A?displayProperty=nameWithType> value provides WS-Security support compliant with WS-I Basic Security Profile 1.0.</span></span> <span data-ttu-id="ce2d9-111">Deje esta propiedad en su valor predeterminado, que es <xref:System.ServiceModel.SecurityMode.Transport?displayProperty=nameWithType>, para no usar WS-Security.</span><span class="sxs-lookup"><span data-stu-id="ce2d9-111">Leave this property at its default value, which is <xref:System.ServiceModel.SecurityMode.Transport?displayProperty=nameWithType> to not use WS-Security.</span></span>  
  
<span data-ttu-id="ce2d9-112">Para que los metadatos de un servicio WCF estén disponibles para ASP.NET, use las herramientas de generación de cliente de servicio web: Herramienta de lenguaje de descripción de [servicios web (Wsdl.exe),](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7h3ystb6%28v=vs.100%29)Herramienta de detección de [servicios web (Disco.exe)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cy2a3ybs%28v=vs.100%29)y la característica **Agregar referencia web** en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ce2d9-112">To make the metadata for a WCF service available to ASP.NET, use the Web service client generation tools: [Web Services Description Language Tool (Wsdl.exe)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7h3ystb6%28v=vs.100%29), [Web Services Discovery Tool (Disco.exe)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cy2a3ybs%28v=vs.100%29), and the **Add Web Reference** feature in Visual Studio.</span></span> <span data-ttu-id="ce2d9-113">Habilite la publicación de metadatos.</span><span class="sxs-lookup"><span data-stu-id="ce2d9-113">Enable metadata publication.</span></span> <span data-ttu-id="ce2d9-114">Para obtener más información, consulte Publicación de [extremos](publishing-metadata-endpoints.md)de metadatos .</span><span class="sxs-lookup"><span data-stu-id="ce2d9-114">For more information, see [Publishing Metadata Endpoints](publishing-metadata-endpoints.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ce2d9-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ce2d9-115">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="ce2d9-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="ce2d9-116">Description</span></span>  
 <span data-ttu-id="ce2d9-117">En el código de ejemplo siguiente se muestra cómo agregar un extremo WCF que es compatible con ASP.NET clientes de servicio Web en código y, alternativamente, en un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="ce2d9-117">The following example code demonstrates how to add a WCF endpoint that is compatible with ASP.NET Web service clients in code and, alternatively, in a configuration file.</span></span>  
  
### <a name="code"></a><span data-ttu-id="ce2d9-118">Código</span><span class="sxs-lookup"><span data-stu-id="ce2d9-118">Code</span></span>  
 [!code-csharp[C_HowTo-WCFServiceAndASMXClient#0](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/cs/program.cs#0)]
 [!code-vb[C_HowTo-WCFServiceAndASMXClient#0](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/vb/program.vb#0)]  
 [!code-xml[C_HowTo-WCFServiceAndASMXClient#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/common/app.config#1)]  
  
## <a name="see-also"></a><span data-ttu-id="ce2d9-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ce2d9-119">See also</span></span>

- [<span data-ttu-id="ce2d9-120">Interoperabilidad con servicios web ASP.NET</span><span class="sxs-lookup"><span data-stu-id="ce2d9-120">Interoperability with ASP.NET Web Services</span></span>](./feature-details/interop-with-aspnet-web-services.md)
