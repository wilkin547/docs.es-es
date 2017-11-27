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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 0a56616e97526b2d410d18d97dc1391c6fc32cc3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="channelpoolsettings"></a><span data-ttu-id="26a5a-102">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="26a5a-102">ChannelPoolSettings</span></span>
<span data-ttu-id="26a5a-103">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="26a5a-103">ChannelPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26a5a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="26a5a-104">Syntax</span></span>  
  
```  
class ChannelPoolSettings  
{  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundChannelsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="26a5a-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="26a5a-105">Methods</span></span>  
 <span data-ttu-id="26a5a-106">La clase ChannelPoolSettings no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="26a5a-106">The ChannelPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="26a5a-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="26a5a-107">Properties</span></span>  
 <span data-ttu-id="26a5a-108">La clase ChannelPoolSettings tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="26a5a-108">The ChannelPoolSettings class has the following properties:</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="26a5a-109">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="26a5a-109">IdleTimeout</span></span>  
 <span data-ttu-id="26a5a-110">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="26a5a-110">Data type: datetime</span></span>  
  
 <span data-ttu-id="26a5a-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="26a5a-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="26a5a-112">El tiempo máximo que la conexión puede estar inactiva antes de desconectarse.</span><span class="sxs-lookup"><span data-stu-id="26a5a-112">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="leasetimeout"></a><span data-ttu-id="26a5a-113">LeaseTimeout</span><span class="sxs-lookup"><span data-stu-id="26a5a-113">LeaseTimeout</span></span>  
 <span data-ttu-id="26a5a-114">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="26a5a-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="26a5a-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="26a5a-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="26a5a-116">El tiempo máximo para que la operación de concesión se complete antes de que se agote el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="26a5a-116">The maximum time for a lease operation to complete before timing out.</span></span>  
  
### <a name="maxoutboundchannelsperendpoint"></a><span data-ttu-id="26a5a-117">MaxOutboundChannelsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="26a5a-117">MaxOutboundChannelsPerEndpoint</span></span>  
 <span data-ttu-id="26a5a-118">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="26a5a-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="26a5a-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="26a5a-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="26a5a-120">El número máximo de canales de salida para cada extremo.</span><span class="sxs-lookup"><span data-stu-id="26a5a-120">The maximum number of outbound channels for each endpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26a5a-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="26a5a-121">Requirements</span></span>  
  
|<span data-ttu-id="26a5a-122">MOF</span><span class="sxs-lookup"><span data-stu-id="26a5a-122">MOF</span></span>|<span data-ttu-id="26a5a-123">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="26a5a-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="26a5a-124">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="26a5a-124">Namespace</span></span>|<span data-ttu-id="26a5a-125">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="26a5a-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="26a5a-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="26a5a-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.ChannelPoolSettings>
