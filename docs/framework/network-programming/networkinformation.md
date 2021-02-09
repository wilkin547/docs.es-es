---
description: 'Más información acerca de: NetworkInformation'
title: NetworkInformation
ms.date: 03/30/2017
helpviewer_keywords:
- Network
ms.assetid: 31b44dd3-b903-4a48-8419-40419a3e4038
ms.openlocfilehash: 9092fd0593d9046f419018b882c08066a6bc654c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785710"
---
# <a name="networkinformation"></a><span data-ttu-id="2b205-103">NetworkInformation</span><span class="sxs-lookup"><span data-stu-id="2b205-103">NetworkInformation</span></span>

<span data-ttu-id="2b205-104">El espacio de nombres <xref:System.Net.NetworkInformation> permite recopilar información sobre eventos, cambios, estadísticas y propiedades de red.</span><span class="sxs-lookup"><span data-stu-id="2b205-104">The <xref:System.Net.NetworkInformation> namespace enables you to gather information about network events, changes, statistics, and properties.</span></span> <span data-ttu-id="2b205-105">También se puede determinar si un host remoto es accesible mediante la clase <xref:System.Net.NetworkInformation.Ping?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2b205-105">You can also determine whether a remote host is reachable by using the <xref:System.Net.NetworkInformation.Ping?displayProperty=nameWithType> class.</span></span>  
  
## <a name="network-availability-and-events"></a><span data-ttu-id="2b205-106">Disponibilidad de la red y eventos</span><span class="sxs-lookup"><span data-stu-id="2b205-106">Network Availability and Events</span></span>  

 <span data-ttu-id="2b205-107">La clase <xref:System.Net.NetworkInformation.NetworkChange?displayProperty=nameWithType> permite determinar si se ha cambiado la dirección de red o la disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="2b205-107">The <xref:System.Net.NetworkInformation.NetworkChange?displayProperty=nameWithType> class enables you to determine whether the network address or availability has changed.</span></span> <span data-ttu-id="2b205-108">Para usar esta clase, cree un controlador de eventos para procesar el cambio y asócielo con un <xref:System.Net.NetworkInformation.NetworkAddressChangedEventHandler> o un <xref:System.Net.NetworkInformation.NetworkAvailabilityChangedEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="2b205-108">To use this class, create an event handler to process the change, and associate it with a <xref:System.Net.NetworkInformation.NetworkAddressChangedEventHandler> or a <xref:System.Net.NetworkInformation.NetworkAvailabilityChangedEventHandler>.</span></span> <span data-ttu-id="2b205-109">Para más información, vea [Cómo: Detectar la disponibilidad de la red y los cambios de dirección](how-to-detect-network-availability-and-address-changes.md).</span><span class="sxs-lookup"><span data-stu-id="2b205-109">For more information, see [How to: Detect Network Availability and Address Changes](how-to-detect-network-availability-and-address-changes.md).</span></span>  
  
## <a name="network-statistics-and-properties"></a><span data-ttu-id="2b205-110">Estadísticas y propiedades de red</span><span class="sxs-lookup"><span data-stu-id="2b205-110">Network Statistics and Properties</span></span>  

 <span data-ttu-id="2b205-111">Puede recopilar estadísticas y propiedades de red por interfaz o protocolo.</span><span class="sxs-lookup"><span data-stu-id="2b205-111">You can gather network statistics and properties on an interface or protocol basis.</span></span> <span data-ttu-id="2b205-112">Las clases <xref:System.Net.NetworkInformation.NetworkInterface>, <xref:System.Net.NetworkInformation.NetworkInterfaceType> y <xref:System.Net.NetworkInformation.PhysicalAddress> ofrecen información sobre una interfaz de red determinada, mientras que las clases <xref:System.Net.NetworkInformation.IPInterfaceProperties>, <xref:System.Net.NetworkInformation.IPGlobalProperties>, <xref:System.Net.NetworkInformation.IPGlobalStatistics>, <xref:System.Net.NetworkInformation.TcpStatistics> y <xref:System.Net.NetworkInformation.UdpStatistics> proporcionan información sobre los paquetes de la capa 3 y la capa 4.</span><span class="sxs-lookup"><span data-stu-id="2b205-112">The <xref:System.Net.NetworkInformation.NetworkInterface>, <xref:System.Net.NetworkInformation.NetworkInterfaceType>, and <xref:System.Net.NetworkInformation.PhysicalAddress> classes give information about a particular network interface, while the <xref:System.Net.NetworkInformation.IPInterfaceProperties>, <xref:System.Net.NetworkInformation.IPGlobalProperties>, <xref:System.Net.NetworkInformation.IPGlobalStatistics>, <xref:System.Net.NetworkInformation.TcpStatistics>, and <xref:System.Net.NetworkInformation.UdpStatistics> classes give information about layer 3 and layer 4 packets.</span></span> <span data-ttu-id="2b205-113">Para más información, vea [Cómo: Obtener información sobre el protocolo y la interfaz](how-to-get-interface-and-protocol-information.md).</span><span class="sxs-lookup"><span data-stu-id="2b205-113">For more information, see [How to: Get Interface and Protocol Information](how-to-get-interface-and-protocol-information.md).</span></span>  
  
## <a name="determine-if-a-remote-host-is-reachable"></a><span data-ttu-id="2b205-114">Determinar si un host remoto es accesible</span><span class="sxs-lookup"><span data-stu-id="2b205-114">Determine if a Remote Host is Reachable</span></span>  

 <span data-ttu-id="2b205-115">Puede usar la clase <xref:System.Net.NetworkInformation.Ping> para determinar si un host remoto está funcionando en la red y es accesible.</span><span class="sxs-lookup"><span data-stu-id="2b205-115">You can use the <xref:System.Net.NetworkInformation.Ping> class to determine whether a Remote Host is up, on the network, and reachable.</span></span> <span data-ttu-id="2b205-116">Para más información, vea [How to: Ping a Host](how-to-ping-a-host.md) (Cómo: hacer ping a un host).</span><span class="sxs-lookup"><span data-stu-id="2b205-116">For more information, see [How to: Ping a Host](how-to-ping-a-host.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b205-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="2b205-117">See also</span></span>

- [<span data-ttu-id="2b205-118">Network Programming Samples (Ejemplos de programación de red)</span><span class="sxs-lookup"><span data-stu-id="2b205-118">Network Programming Samples</span></span>](network-programming-samples.md)

<!-- to-do: review sample links
- [Network Information Technology Sample](https://archive.msdn.microsoft.com/nclsamples/Wiki/View.aspx?title=Network%20Information)
- [NetStat Tool Technology Sample](https://archive.msdn.microsoft.com/nclsamples/Wiki/View.aspx?title=NetStat%20Tool)
- [Ping Client Technology Sample](https://archive.msdn.microsoft.com/nclsamples/Wiki/View.aspx?title=Ping%20Client)
-->
