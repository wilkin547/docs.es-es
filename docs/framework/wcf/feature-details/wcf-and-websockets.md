---
description: 'Más información sobre: WCF y WebSockets'
title: WCF y WebSockets
ms.date: 03/30/2017
ms.assetid: 1e53b49e-022c-49c7-8984-4b21b53c05b3
ms.openlocfilehash: 6b0d8c33000a65bf3bbf834f66119d65768b3cb6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99755985"
---
# <a name="wcf-and-websockets"></a><span data-ttu-id="0af2f-103">WCF y WebSockets</span><span class="sxs-lookup"><span data-stu-id="0af2f-103">WCF and WebSockets</span></span>

<span data-ttu-id="0af2f-104">.NET Framework 4.5 presenta compatibilidad con WebSockets en Windows Communication Foundation.</span><span class="sxs-lookup"><span data-stu-id="0af2f-104">The .NET Framework 4.5 introduces support for WebSockets in Windows Communication Foundation.</span></span>  <span data-ttu-id="0af2f-105">WebSockets es una tecnología eficaz basada en estándares que permite la comunicación bidireccional a través de los puertos estándar 80 y 443 de HTTP.</span><span class="sxs-lookup"><span data-stu-id="0af2f-105">WebSockets is an efficient, standards-based technology that enables bidirectional communication over the standard HTTP ports 80 and 443.</span></span> <span data-ttu-id="0af2f-106">El uso de los puertos HTTP estándar permite que WebSockets se comunique a través de la Web mediante intermediarios.</span><span class="sxs-lookup"><span data-stu-id="0af2f-106">The use of the standard HTTP ports allow WebSockets to communicate across the web through intermediaries.</span></span>  <span data-ttu-id="0af2f-107">Se han agregado dos nuevos enlaces estándar para admitir la comunicación a través de un transporte WebSocket.</span><span class="sxs-lookup"><span data-stu-id="0af2f-107">Two new standard bindings have been added to support communication over a WebSocket transport.</span></span> <span data-ttu-id="0af2f-108"><xref:System.ServiceModel.NetHttpBinding> y <xref:System.ServiceModel.NetHttpsBinding>.</span><span class="sxs-lookup"><span data-stu-id="0af2f-108"><xref:System.ServiceModel.NetHttpBinding> and <xref:System.ServiceModel.NetHttpsBinding>.</span></span> <span data-ttu-id="0af2f-109">La configuración específica de WebSockets puede configurarse en <xref:System.ServiceModel.Channels.HttpTransportBindingElement> mediante el acceso a la <xref:System.ServiceModel.Channels.HttpTransportBindingElement.WebSocketSettings%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="0af2f-109">WebSockets-specific settings can be configured on the <xref:System.ServiceModel.Channels.HttpTransportBindingElement> by accessing the <xref:System.ServiceModel.Channels.HttpTransportBindingElement.WebSocketSettings%2A> property.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="0af2f-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="0af2f-110">In This Section</span></span>  

 [<span data-ttu-id="0af2f-111">Usar NetHttpBinding</span><span class="sxs-lookup"><span data-stu-id="0af2f-111">Using the NetHttpBinding</span></span>](using-the-nethttpbinding.md)  
 <span data-ttu-id="0af2f-112">Describe <xref:System.ServiceModel.NetHttpBinding> y su configuración.</span><span class="sxs-lookup"><span data-stu-id="0af2f-112">Discusses the <xref:System.ServiceModel.NetHttpBinding> and how to configure it.</span></span>  
  
 [<span data-ttu-id="0af2f-113">Procedimiento para crear un servicio WCF que se comunique a través de WebSockets</span><span class="sxs-lookup"><span data-stu-id="0af2f-113">How to: Create a WCF Service that Communicates over WebSockets</span></span>](how-to-create-a-wcf-service-that-communicates-over-websockets.md)  
 <span data-ttu-id="0af2f-114">Describe cómo crear un servicio WCF que se comunique a través de Websockets.</span><span class="sxs-lookup"><span data-stu-id="0af2f-114">Describes how to create a WCF service that communicates over Websockets.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="0af2f-115">Referencia</span><span class="sxs-lookup"><span data-stu-id="0af2f-115">Reference</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="0af2f-116">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="0af2f-116">Related Sections</span></span>
