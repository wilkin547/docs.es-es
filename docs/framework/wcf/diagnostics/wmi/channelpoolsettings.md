---
title: ChannelPoolSettings
ms.date: 03/30/2017
ms.assetid: d3f475bd-f780-4bbe-b291-339387322964
ms.openlocfilehash: 3dcc1f3b27d93d5641a4bb2d8082aa3fa88882dc
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96274223"
---
# <a name="channelpoolsettings"></a><span data-ttu-id="55408-102">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="55408-102">ChannelPoolSettings</span></span>

<span data-ttu-id="55408-103">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="55408-103">ChannelPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55408-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="55408-104">Syntax</span></span>  
  
```csharp
class ChannelPoolSettings  
{  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundChannelsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="55408-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="55408-105">Methods</span></span>  

 <span data-ttu-id="55408-106">La clase ChannelPoolSettings no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="55408-106">The ChannelPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="55408-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="55408-107">Properties</span></span>  

 <span data-ttu-id="55408-108">La clase ChannelPoolSettings tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="55408-108">The ChannelPoolSettings class has the following properties:</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="55408-109">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="55408-109">IdleTimeout</span></span>  

 <span data-ttu-id="55408-110">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="55408-110">Data type: datetime</span></span>  
  
 <span data-ttu-id="55408-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="55408-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="55408-112">El tiempo máximo que la conexión puede estar inactiva antes de desconectarse.</span><span class="sxs-lookup"><span data-stu-id="55408-112">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="leasetimeout"></a><span data-ttu-id="55408-113">LeaseTimeout</span><span class="sxs-lookup"><span data-stu-id="55408-113">LeaseTimeout</span></span>  

 <span data-ttu-id="55408-114">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="55408-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="55408-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="55408-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="55408-116">El tiempo máximo para que la operación de concesión se complete antes de que se agote el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="55408-116">The maximum time for a lease operation to complete before timing out.</span></span>  
  
### <a name="maxoutboundchannelsperendpoint"></a><span data-ttu-id="55408-117">MaxOutboundChannelsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="55408-117">MaxOutboundChannelsPerEndpoint</span></span>  

 <span data-ttu-id="55408-118">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="55408-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="55408-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="55408-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="55408-120">El número máximo de canales de salida para cada punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="55408-120">The maximum number of outbound channels for each endpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55408-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="55408-121">Requirements</span></span>  
  
|<span data-ttu-id="55408-122">MOF</span><span class="sxs-lookup"><span data-stu-id="55408-122">MOF</span></span>|<span data-ttu-id="55408-123">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="55408-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="55408-124">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="55408-124">Namespace</span></span>|<span data-ttu-id="55408-125">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="55408-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="55408-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="55408-126">See also</span></span>

- <xref:System.ServiceModel.Channels.ChannelPoolSettings>
