---
title: WCF y WebSockets
ms.date: 03/30/2017
ms.assetid: 1e53b49e-022c-49c7-8984-4b21b53c05b3
ms.openlocfilehash: ac888db14ebd21c4aed2f717c1f71bed310b8388
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61768737"
---
# <a name="wcf-and-websockets"></a><span data-ttu-id="8ba9a-102">WCF y WebSockets</span><span class="sxs-lookup"><span data-stu-id="8ba9a-102">WCF and WebSockets</span></span>
<span data-ttu-id="8ba9a-103">.NET Framework 4.5 presenta compatibilidad con WebSockets en Windows Communication Foundation.</span><span class="sxs-lookup"><span data-stu-id="8ba9a-103">The .NET Framework 4.5 introduces support for WebSockets in Windows Communication Foundation.</span></span>  <span data-ttu-id="8ba9a-104">WebSockets es una tecnología eficaz basada en estándares que permite la comunicación bidireccional a través de los puertos estándar 80 y 443 de HTTP.</span><span class="sxs-lookup"><span data-stu-id="8ba9a-104">WebSockets is an efficient, standards-based technology that enables bidirectional communication over the standard HTTP ports 80 and 443.</span></span> <span data-ttu-id="8ba9a-105">El uso de los puertos HTTP estándar permite que WebSockets se comunique a través de la Web mediante intermediarios.</span><span class="sxs-lookup"><span data-stu-id="8ba9a-105">The use of the standard HTTP ports allow WebSockets to communicate across the web through intermediaries.</span></span>  <span data-ttu-id="8ba9a-106">Se han agregado dos nuevos enlaces estándar para admitir la comunicación a través de un transporte WebSocket.</span><span class="sxs-lookup"><span data-stu-id="8ba9a-106">Two new standard bindings have been added to support communication over a WebSocket transport.</span></span> <span data-ttu-id="8ba9a-107"><xref:System.ServiceModel.NetHttpBinding> y <xref:System.ServiceModel.NetHttpsBinding>.</span><span class="sxs-lookup"><span data-stu-id="8ba9a-107"><xref:System.ServiceModel.NetHttpBinding> and <xref:System.ServiceModel.NetHttpsBinding>.</span></span> <span data-ttu-id="8ba9a-108">Se pueden configurar valores específicos de WebSockets en el <xref:System.ServiceModel.Channels.HttpTransportBindingElement> mediante el acceso a la <xref:System.ServiceModel.Channels.HttpTransportBindingElement.WebSocketSettings%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="8ba9a-108">WebSockets-specific settings can be configured on the <xref:System.ServiceModel.Channels.HttpTransportBindingElement> by accessing the <xref:System.ServiceModel.Channels.HttpTransportBindingElement.WebSocketSettings%2A> property.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="8ba9a-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="8ba9a-109">In This Section</span></span>  
 [<span data-ttu-id="8ba9a-110">Uso de NetHttpBinding</span><span class="sxs-lookup"><span data-stu-id="8ba9a-110">Using the NetHttpBinding</span></span>](../../../../docs/framework/wcf/feature-details/using-the-nethttpbinding.md)  
 <span data-ttu-id="8ba9a-111">Describe <xref:System.ServiceModel.NetHttpBinding> y su configuración.</span><span class="sxs-lookup"><span data-stu-id="8ba9a-111">Discusses the <xref:System.ServiceModel.NetHttpBinding> and how to configure it.</span></span>  
  
 [<span data-ttu-id="8ba9a-112">Cómo: Crear un servicio WCF que se comunica a través de WebSockets</span><span class="sxs-lookup"><span data-stu-id="8ba9a-112">How to: Create a WCF Service that Communicates over WebSockets</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-wcf-service-that-communicates-over-websockets.md)  
 <span data-ttu-id="8ba9a-113">Describe cómo crear un servicio WCF que se comunique a través de Websockets.</span><span class="sxs-lookup"><span data-stu-id="8ba9a-113">Describes how to create a WCF service that communicates over Websockets.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="8ba9a-114">Referencia</span><span class="sxs-lookup"><span data-stu-id="8ba9a-114">Reference</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="8ba9a-115">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="8ba9a-115">Related Sections</span></span>
