---
title: WCF y WebSockets
ms.date: 03/30/2017
ms.assetid: 1e53b49e-022c-49c7-8984-4b21b53c05b3
ms.openlocfilehash: 2ee27eef015ee8c2fbee8360b444343a1c757097
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96281591"
---
# <a name="wcf-and-websockets"></a><span data-ttu-id="3bd9f-102">WCF y WebSockets</span><span class="sxs-lookup"><span data-stu-id="3bd9f-102">WCF and WebSockets</span></span>

<span data-ttu-id="3bd9f-103">.NET Framework 4.5 presenta compatibilidad con WebSockets en Windows Communication Foundation.</span><span class="sxs-lookup"><span data-stu-id="3bd9f-103">The .NET Framework 4.5 introduces support for WebSockets in Windows Communication Foundation.</span></span>  <span data-ttu-id="3bd9f-104">WebSockets es una tecnología eficaz basada en estándares que permite la comunicación bidireccional a través de los puertos estándar 80 y 443 de HTTP.</span><span class="sxs-lookup"><span data-stu-id="3bd9f-104">WebSockets is an efficient, standards-based technology that enables bidirectional communication over the standard HTTP ports 80 and 443.</span></span> <span data-ttu-id="3bd9f-105">El uso de los puertos HTTP estándar permite que WebSockets se comunique a través de la Web mediante intermediarios.</span><span class="sxs-lookup"><span data-stu-id="3bd9f-105">The use of the standard HTTP ports allow WebSockets to communicate across the web through intermediaries.</span></span>  <span data-ttu-id="3bd9f-106">Se han agregado dos nuevos enlaces estándar para admitir la comunicación a través de un transporte WebSocket.</span><span class="sxs-lookup"><span data-stu-id="3bd9f-106">Two new standard bindings have been added to support communication over a WebSocket transport.</span></span> <span data-ttu-id="3bd9f-107"><xref:System.ServiceModel.NetHttpBinding> y <xref:System.ServiceModel.NetHttpsBinding>.</span><span class="sxs-lookup"><span data-stu-id="3bd9f-107"><xref:System.ServiceModel.NetHttpBinding> and <xref:System.ServiceModel.NetHttpsBinding>.</span></span> <span data-ttu-id="3bd9f-108">La configuración específica de WebSockets puede configurarse en <xref:System.ServiceModel.Channels.HttpTransportBindingElement> mediante el acceso a la <xref:System.ServiceModel.Channels.HttpTransportBindingElement.WebSocketSettings%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="3bd9f-108">WebSockets-specific settings can be configured on the <xref:System.ServiceModel.Channels.HttpTransportBindingElement> by accessing the <xref:System.ServiceModel.Channels.HttpTransportBindingElement.WebSocketSettings%2A> property.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="3bd9f-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="3bd9f-109">In This Section</span></span>  

 [<span data-ttu-id="3bd9f-110">Usar NetHttpBinding</span><span class="sxs-lookup"><span data-stu-id="3bd9f-110">Using the NetHttpBinding</span></span>](using-the-nethttpbinding.md)  
 <span data-ttu-id="3bd9f-111">Describe <xref:System.ServiceModel.NetHttpBinding> y su configuración.</span><span class="sxs-lookup"><span data-stu-id="3bd9f-111">Discusses the <xref:System.ServiceModel.NetHttpBinding> and how to configure it.</span></span>  
  
 [<span data-ttu-id="3bd9f-112">Procedimiento para crear un servicio WCF que se comunique a través de WebSockets</span><span class="sxs-lookup"><span data-stu-id="3bd9f-112">How to: Create a WCF Service that Communicates over WebSockets</span></span>](how-to-create-a-wcf-service-that-communicates-over-websockets.md)  
 <span data-ttu-id="3bd9f-113">Describe cómo crear un servicio WCF que se comunique a través de Websockets.</span><span class="sxs-lookup"><span data-stu-id="3bd9f-113">Describes how to create a WCF service that communicates over Websockets.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="3bd9f-114">Referencia</span><span class="sxs-lookup"><span data-stu-id="3bd9f-114">Reference</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="3bd9f-115">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="3bd9f-115">Related Sections</span></span>
