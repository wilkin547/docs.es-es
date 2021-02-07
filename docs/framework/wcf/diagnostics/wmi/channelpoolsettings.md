---
description: 'Más información acerca de: ChannelPoolSettings'
title: ChannelPoolSettings
ms.date: 03/30/2017
ms.assetid: d3f475bd-f780-4bbe-b291-339387322964
ms.openlocfilehash: b08c5483e7a0c918393795b4608b9eef16b18341
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99757688"
---
# <a name="channelpoolsettings"></a><span data-ttu-id="f854e-103">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="f854e-103">ChannelPoolSettings</span></span>

<span data-ttu-id="f854e-104">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="f854e-104">ChannelPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f854e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f854e-105">Syntax</span></span>  
  
```csharp
class ChannelPoolSettings  
{  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundChannelsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="f854e-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="f854e-106">Methods</span></span>  

 <span data-ttu-id="f854e-107">La clase ChannelPoolSettings no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="f854e-107">The ChannelPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="f854e-108">Propiedades</span><span class="sxs-lookup"><span data-stu-id="f854e-108">Properties</span></span>  

 <span data-ttu-id="f854e-109">La clase ChannelPoolSettings tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="f854e-109">The ChannelPoolSettings class has the following properties:</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="f854e-110">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="f854e-110">IdleTimeout</span></span>  

 <span data-ttu-id="f854e-111">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="f854e-111">Data type: datetime</span></span>  
  
 <span data-ttu-id="f854e-112">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="f854e-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f854e-113">El tiempo máximo que la conexión puede estar inactiva antes de desconectarse.</span><span class="sxs-lookup"><span data-stu-id="f854e-113">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="leasetimeout"></a><span data-ttu-id="f854e-114">LeaseTimeout</span><span class="sxs-lookup"><span data-stu-id="f854e-114">LeaseTimeout</span></span>  

 <span data-ttu-id="f854e-115">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="f854e-115">Data type: datetime</span></span>  
  
 <span data-ttu-id="f854e-116">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="f854e-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f854e-117">El tiempo máximo para que la operación de concesión se complete antes de que se agote el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="f854e-117">The maximum time for a lease operation to complete before timing out.</span></span>  
  
### <a name="maxoutboundchannelsperendpoint"></a><span data-ttu-id="f854e-118">MaxOutboundChannelsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="f854e-118">MaxOutboundChannelsPerEndpoint</span></span>  

 <span data-ttu-id="f854e-119">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="f854e-119">Data type: sint32</span></span>  
  
 <span data-ttu-id="f854e-120">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="f854e-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f854e-121">El número máximo de canales de salida para cada punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="f854e-121">The maximum number of outbound channels for each endpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f854e-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f854e-122">Requirements</span></span>  
  
|<span data-ttu-id="f854e-123">MOF</span><span class="sxs-lookup"><span data-stu-id="f854e-123">MOF</span></span>|<span data-ttu-id="f854e-124">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="f854e-124">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="f854e-125">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="f854e-125">Namespace</span></span>|<span data-ttu-id="f854e-126">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="f854e-126">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f854e-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="f854e-127">See also</span></span>

- <xref:System.ServiceModel.Channels.ChannelPoolSettings>
