---
title: ChannelPoolSettings
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d3f475bd-f780-4bbe-b291-339387322964
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3995b517b27a5565f7fcb9c11da27c9e1bb40887
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="channelpoolsettings"></a><span data-ttu-id="ff495-102">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="ff495-102">ChannelPoolSettings</span></span>
<span data-ttu-id="ff495-103">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="ff495-103">ChannelPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff495-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ff495-104">Syntax</span></span>  
  
```  
class ChannelPoolSettings  
{  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundChannelsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="ff495-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="ff495-105">Methods</span></span>  
 <span data-ttu-id="ff495-106">La clase ChannelPoolSettings no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="ff495-106">The ChannelPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="ff495-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="ff495-107">Properties</span></span>  
 <span data-ttu-id="ff495-108">La clase ChannelPoolSettings tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="ff495-108">The ChannelPoolSettings class has the following properties:</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="ff495-109">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="ff495-109">IdleTimeout</span></span>  
 <span data-ttu-id="ff495-110">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="ff495-110">Data type: datetime</span></span>  
  
 <span data-ttu-id="ff495-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="ff495-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ff495-112">El tiempo máximo que la conexión puede estar inactiva antes de desconectarse.</span><span class="sxs-lookup"><span data-stu-id="ff495-112">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="leasetimeout"></a><span data-ttu-id="ff495-113">LeaseTimeout</span><span class="sxs-lookup"><span data-stu-id="ff495-113">LeaseTimeout</span></span>  
 <span data-ttu-id="ff495-114">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="ff495-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="ff495-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="ff495-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ff495-116">El tiempo máximo para que la operación de concesión se complete antes de que se agote el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="ff495-116">The maximum time for a lease operation to complete before timing out.</span></span>  
  
### <a name="maxoutboundchannelsperendpoint"></a><span data-ttu-id="ff495-117">MaxOutboundChannelsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="ff495-117">MaxOutboundChannelsPerEndpoint</span></span>  
 <span data-ttu-id="ff495-118">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="ff495-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="ff495-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="ff495-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ff495-120">El número máximo de canales de salida para cada extremo.</span><span class="sxs-lookup"><span data-stu-id="ff495-120">The maximum number of outbound channels for each endpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff495-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ff495-121">Requirements</span></span>  
  
|<span data-ttu-id="ff495-122">MOF</span><span class="sxs-lookup"><span data-stu-id="ff495-122">MOF</span></span>|<span data-ttu-id="ff495-123">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="ff495-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="ff495-124">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="ff495-124">Namespace</span></span>|<span data-ttu-id="ff495-125">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="ff495-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ff495-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="ff495-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.ChannelPoolSettings>
