---
title: ChannelPoolSettings
ms.date: 03/30/2017
ms.assetid: d3f475bd-f780-4bbe-b291-339387322964
ms.openlocfilehash: 4a3e45140765f99f4a30b77fc9d02b167601b50b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54591489"
---
# <a name="channelpoolsettings"></a><span data-ttu-id="23f49-102">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="23f49-102">ChannelPoolSettings</span></span>
<span data-ttu-id="23f49-103">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="23f49-103">ChannelPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23f49-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="23f49-104">Syntax</span></span>  
  
```csharp
class ChannelPoolSettings  
{  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundChannelsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="23f49-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="23f49-105">Methods</span></span>  
 <span data-ttu-id="23f49-106">La clase ChannelPoolSettings no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="23f49-106">The ChannelPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="23f49-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="23f49-107">Properties</span></span>  
 <span data-ttu-id="23f49-108">La clase ChannelPoolSettings tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="23f49-108">The ChannelPoolSettings class has the following properties:</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="23f49-109">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="23f49-109">IdleTimeout</span></span>  
 <span data-ttu-id="23f49-110">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="23f49-110">Data type: datetime</span></span>  
  
 <span data-ttu-id="23f49-111">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="23f49-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="23f49-112">El tiempo máximo que la conexión puede estar inactiva antes de desconectarse.</span><span class="sxs-lookup"><span data-stu-id="23f49-112">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="leasetimeout"></a><span data-ttu-id="23f49-113">LeaseTimeout</span><span class="sxs-lookup"><span data-stu-id="23f49-113">LeaseTimeout</span></span>  
 <span data-ttu-id="23f49-114">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="23f49-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="23f49-115">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="23f49-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="23f49-116">El tiempo máximo para que la operación de concesión se complete antes de que se agote el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="23f49-116">The maximum time for a lease operation to complete before timing out.</span></span>  
  
### <a name="maxoutboundchannelsperendpoint"></a><span data-ttu-id="23f49-117">MaxOutboundChannelsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="23f49-117">MaxOutboundChannelsPerEndpoint</span></span>  
 <span data-ttu-id="23f49-118">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="23f49-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="23f49-119">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="23f49-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="23f49-120">El número máximo de canales de salida para cada punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="23f49-120">The maximum number of outbound channels for each endpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23f49-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="23f49-121">Requirements</span></span>  
  
|<span data-ttu-id="23f49-122">MOF</span><span class="sxs-lookup"><span data-stu-id="23f49-122">MOF</span></span>|<span data-ttu-id="23f49-123">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="23f49-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="23f49-124">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="23f49-124">Namespace</span></span>|<span data-ttu-id="23f49-125">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="23f49-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="23f49-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="23f49-126">See also</span></span>
- <xref:System.ServiceModel.Channels.ChannelPoolSettings>
