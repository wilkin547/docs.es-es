---
description: Más información acerca de cómo crear servicios interoperables de WS-I Basic Profile 1,1
title: Creación de servicios interoperables de WS-I Basic Profile 1.1
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- configuration [WCF], interoperable services
ms.assetid: 91b70a21-8f5c-4679-808c-2ed5fa6b2013
ms.openlocfilehash: 46e2d925dfe431957198b1d53b40d28adf6fb1c4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99646184"
---
# <a name="creating-ws-i-basic-profile-11-interoperable-services"></a><span data-ttu-id="f1800-103">Creación de servicios interoperables de WS-I Basic Profile 1.1</span><span class="sxs-lookup"><span data-stu-id="f1800-103">Creating WS-I Basic Profile 1.1 Interoperable Services</span></span>

<span data-ttu-id="f1800-104">Para configurar un extremo de servicio WCF para que sea interoperable con clientes de servicios Web de ASP.NET:</span><span class="sxs-lookup"><span data-stu-id="f1800-104">To configure a WCF service endpoint to be interoperable with ASP.NET Web service clients:</span></span>  
  
- <span data-ttu-id="f1800-105">Utilice el tipo <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType> como tipo de enlace para su extremo de servicio.</span><span class="sxs-lookup"><span data-stu-id="f1800-105">Use the <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType> type as the binding type for your service endpoint.</span></span>  
  
- <span data-ttu-id="f1800-106">No utilice devolución de llamada sino características de contrato de sesión o comportamientos de transacción en su extremo de servicio</span><span class="sxs-lookup"><span data-stu-id="f1800-106">Do not use callback and session contract features or transaction behaviors on your service endpoint</span></span>  
  
<span data-ttu-id="f1800-107">Puede habilitar opcionalmente el soporte para HTTPS y la autenticación del cliente del nivel de transporte en el enlace.</span><span class="sxs-lookup"><span data-stu-id="f1800-107">You can optionally enable support for HTTPS and transport-level client authentication on the binding.</span></span>  
  
<span data-ttu-id="f1800-108">Las características siguientes de la clase <xref:System.ServiceModel.BasicHttpBinding> requieren la funcionalidad más allá de WS-I Basic Profile 1.1:</span><span class="sxs-lookup"><span data-stu-id="f1800-108">The following features of the <xref:System.ServiceModel.BasicHttpBinding> class require functionality beyond WS-I Basic Profile 1.1:</span></span>  
  
- <span data-ttu-id="f1800-109">Codificación de mensajes del Mecanismo de optimización de transmisión del mensajes (MTOM) controlada por la propiedad <xref:System.ServiceModel.BasicHttpBinding.MessageEncoding%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f1800-109">Message Transmission Optimization Mechanism (MTOM) message encoding controlled by the <xref:System.ServiceModel.BasicHttpBinding.MessageEncoding%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="f1800-110">Deje esta propiedad en su valor predeterminado, que es <xref:System.ServiceModel.WSMessageEncoding.Text?displayProperty=nameWithType> para no utilizar MTOM.</span><span class="sxs-lookup"><span data-stu-id="f1800-110">Leave  this property at its default value, which is <xref:System.ServiceModel.WSMessageEncoding.Text?displayProperty=nameWithType> to not use MTOM.</span></span>  
  
- <span data-ttu-id="f1800-111">La seguridad de mensaje que controla el valor <xref:System.ServiceModel.BasicHttpBinding.Security%2A?displayProperty=nameWithType> proporciona compatibilidad con WS-Security conforme a WS-I Basic Security Profile 1.0.</span><span class="sxs-lookup"><span data-stu-id="f1800-111">Message security controlled by the <xref:System.ServiceModel.BasicHttpBinding.Security%2A?displayProperty=nameWithType> value provides WS-Security support compliant with WS-I Basic Security Profile 1.0.</span></span> <span data-ttu-id="f1800-112">Deje esta propiedad en su valor predeterminado, que es <xref:System.ServiceModel.SecurityMode.Transport?displayProperty=nameWithType>, para no usar WS-Security.</span><span class="sxs-lookup"><span data-stu-id="f1800-112">Leave this property at its default value, which is <xref:System.ServiceModel.SecurityMode.Transport?displayProperty=nameWithType> to not use WS-Security.</span></span>  
  
<span data-ttu-id="f1800-113">Para que los metadatos de un servicio WCF estén disponibles para ASP.NET, use las herramientas de generación de cliente de servicio Web: [herramienta lenguaje de descripción de servicios web (Wsdl.exe)](/previous-versions/dotnet/netframework-4.0/7h3ystb6(v=vs.100)), [herramienta de detección de servicios web (Disco.exe)](/previous-versions/dotnet/netframework-4.0/cy2a3ybs(v=vs.100))y la característica **Agregar referencia Web** en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f1800-113">To make the metadata for a WCF service available to ASP.NET, use the Web service client generation tools: [Web Services Description Language Tool (Wsdl.exe)](/previous-versions/dotnet/netframework-4.0/7h3ystb6(v=vs.100)), [Web Services Discovery Tool (Disco.exe)](/previous-versions/dotnet/netframework-4.0/cy2a3ybs(v=vs.100)), and the **Add Web Reference** feature in Visual Studio.</span></span> <span data-ttu-id="f1800-114">Habilitar la publicación de metadatos.</span><span class="sxs-lookup"><span data-stu-id="f1800-114">Enable metadata publication.</span></span> <span data-ttu-id="f1800-115">Para obtener más información, consulte [publicación de puntos de conexión de metadatos](publishing-metadata-endpoints.md).</span><span class="sxs-lookup"><span data-stu-id="f1800-115">For more information, see [Publishing Metadata Endpoints](publishing-metadata-endpoints.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f1800-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f1800-116">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="f1800-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="f1800-117">Description</span></span>  

 <span data-ttu-id="f1800-118">En el código de ejemplo siguiente se muestra cómo agregar un punto de conexión de WCF que es compatible con los clientes del servicio Web ASP.NET en el código y, como alternativa, en un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="f1800-118">The following example code demonstrates how to add a WCF endpoint that is compatible with ASP.NET Web service clients in code and, alternatively, in a configuration file.</span></span>  
  
### <a name="code"></a><span data-ttu-id="f1800-119">Código</span><span class="sxs-lookup"><span data-stu-id="f1800-119">Code</span></span>  

 [!code-csharp[C_HowTo-WCFServiceAndASMXClient#0](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/cs/program.cs#0)]
 [!code-vb[C_HowTo-WCFServiceAndASMXClient#0](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/vb/program.vb#0)]  
 [!code-xml[C_HowTo-WCFServiceAndASMXClient#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/common/app.config#1)]  
  
## <a name="see-also"></a><span data-ttu-id="f1800-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f1800-120">See also</span></span>

- [<span data-ttu-id="f1800-121">Interoperabilidad con servicios web ASP.NET</span><span class="sxs-lookup"><span data-stu-id="f1800-121">Interoperability with ASP.NET Web Services</span></span>](./feature-details/interop-with-aspnet-web-services.md)
