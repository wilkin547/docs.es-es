---
title: ChannelPoolSettings
ms.date: 03/30/2017
ms.assetid: d3f475bd-f780-4bbe-b291-339387322964
ms.openlocfilehash: d763be92243768bce9fdaefcd3e3575effac464b
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2018
ms.locfileid: "50200488"
---
# <a name="channelpoolsettings"></a><span data-ttu-id="fc820-102">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="fc820-102">ChannelPoolSettings</span></span>
<span data-ttu-id="fc820-103">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="fc820-103">ChannelPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc820-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fc820-104">Syntax</span></span>  
  
```csharp
class ChannelPoolSettings  
{  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundChannelsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="fc820-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="fc820-105">Methods</span></span>  
 <span data-ttu-id="fc820-106">La clase ChannelPoolSettings no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="fc820-106">The ChannelPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="fc820-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="fc820-107">Properties</span></span>  
 <span data-ttu-id="fc820-108">La clase ChannelPoolSettings tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="fc820-108">The ChannelPoolSettings class has the following properties:</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="fc820-109">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="fc820-109">IdleTimeout</span></span>  
 <span data-ttu-id="fc820-110">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="fc820-110">Data type: datetime</span></span>  
  
 <span data-ttu-id="fc820-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="fc820-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fc820-112">El tiempo máximo que la conexión puede estar inactiva antes de desconectarse.</span><span class="sxs-lookup"><span data-stu-id="fc820-112">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="leasetimeout"></a><span data-ttu-id="fc820-113">LeaseTimeout</span><span class="sxs-lookup"><span data-stu-id="fc820-113">LeaseTimeout</span></span>  
 <span data-ttu-id="fc820-114">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="fc820-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="fc820-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="fc820-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fc820-116">El tiempo máximo para que la operación de concesión se complete antes de que se agote el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="fc820-116">The maximum time for a lease operation to complete before timing out.</span></span>  
  
### <a name="maxoutboundchannelsperendpoint"></a><span data-ttu-id="fc820-117">MaxOutboundChannelsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="fc820-117">MaxOutboundChannelsPerEndpoint</span></span>  
 <span data-ttu-id="fc820-118">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="fc820-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="fc820-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="fc820-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fc820-120">El número máximo de canales de salida para cada extremo.</span><span class="sxs-lookup"><span data-stu-id="fc820-120">The maximum number of outbound channels for each endpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc820-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fc820-121">Requirements</span></span>  
  
|<span data-ttu-id="fc820-122">MOF</span><span class="sxs-lookup"><span data-stu-id="fc820-122">MOF</span></span>|<span data-ttu-id="fc820-123">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="fc820-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="fc820-124">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="fc820-124">Namespace</span></span>|<span data-ttu-id="fc820-125">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="fc820-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fc820-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="fc820-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.ChannelPoolSettings>
