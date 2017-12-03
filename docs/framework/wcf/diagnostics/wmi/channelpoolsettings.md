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
ms.openlocfilehash: e97e934673efbc6d0f72751c7cb1de6fba84a141
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="channelpoolsettings"></a><span data-ttu-id="d825d-102">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="d825d-102">ChannelPoolSettings</span></span>
<span data-ttu-id="d825d-103">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="d825d-103">ChannelPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d825d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d825d-104">Syntax</span></span>  
  
```  
class ChannelPoolSettings  
{  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundChannelsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="d825d-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="d825d-105">Methods</span></span>  
 <span data-ttu-id="d825d-106">La clase ChannelPoolSettings no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="d825d-106">The ChannelPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="d825d-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="d825d-107">Properties</span></span>  
 <span data-ttu-id="d825d-108">La clase ChannelPoolSettings tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="d825d-108">The ChannelPoolSettings class has the following properties:</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="d825d-109">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="d825d-109">IdleTimeout</span></span>  
 <span data-ttu-id="d825d-110">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="d825d-110">Data type: datetime</span></span>  
  
 <span data-ttu-id="d825d-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="d825d-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d825d-112">El tiempo máximo que la conexión puede estar inactiva antes de desconectarse.</span><span class="sxs-lookup"><span data-stu-id="d825d-112">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="leasetimeout"></a><span data-ttu-id="d825d-113">LeaseTimeout</span><span class="sxs-lookup"><span data-stu-id="d825d-113">LeaseTimeout</span></span>  
 <span data-ttu-id="d825d-114">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="d825d-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="d825d-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="d825d-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d825d-116">El tiempo máximo para que la operación de concesión se complete antes de que se agote el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="d825d-116">The maximum time for a lease operation to complete before timing out.</span></span>  
  
### <a name="maxoutboundchannelsperendpoint"></a><span data-ttu-id="d825d-117">MaxOutboundChannelsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="d825d-117">MaxOutboundChannelsPerEndpoint</span></span>  
 <span data-ttu-id="d825d-118">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="d825d-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="d825d-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="d825d-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d825d-120">El número máximo de canales de salida para cada extremo.</span><span class="sxs-lookup"><span data-stu-id="d825d-120">The maximum number of outbound channels for each endpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d825d-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d825d-121">Requirements</span></span>  
  
|<span data-ttu-id="d825d-122">MOF</span><span class="sxs-lookup"><span data-stu-id="d825d-122">MOF</span></span>|<span data-ttu-id="d825d-123">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="d825d-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="d825d-124">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="d825d-124">Namespace</span></span>|<span data-ttu-id="d825d-125">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="d825d-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d825d-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="d825d-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.ChannelPoolSettings>
