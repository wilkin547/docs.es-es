---
title: ChannelPoolSettings
ms.date: 03/30/2017
ms.assetid: d3f475bd-f780-4bbe-b291-339387322964
ms.openlocfilehash: 48b41d2f3f45cd9c590f87151253450962b994de
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33485302"
---
# <a name="channelpoolsettings"></a><span data-ttu-id="fd316-102">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="fd316-102">ChannelPoolSettings</span></span>
<span data-ttu-id="fd316-103">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="fd316-103">ChannelPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd316-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fd316-104">Syntax</span></span>  
  
```  
class ChannelPoolSettings  
{  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundChannelsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="fd316-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="fd316-105">Methods</span></span>  
 <span data-ttu-id="fd316-106">La clase ChannelPoolSettings no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="fd316-106">The ChannelPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="fd316-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="fd316-107">Properties</span></span>  
 <span data-ttu-id="fd316-108">La clase ChannelPoolSettings tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="fd316-108">The ChannelPoolSettings class has the following properties:</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="fd316-109">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="fd316-109">IdleTimeout</span></span>  
 <span data-ttu-id="fd316-110">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="fd316-110">Data type: datetime</span></span>  
  
 <span data-ttu-id="fd316-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="fd316-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fd316-112">El tiempo máximo que la conexión puede estar inactiva antes de desconectarse.</span><span class="sxs-lookup"><span data-stu-id="fd316-112">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="leasetimeout"></a><span data-ttu-id="fd316-113">LeaseTimeout</span><span class="sxs-lookup"><span data-stu-id="fd316-113">LeaseTimeout</span></span>  
 <span data-ttu-id="fd316-114">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="fd316-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="fd316-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="fd316-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fd316-116">El tiempo máximo para que la operación de concesión se complete antes de que se agote el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="fd316-116">The maximum time for a lease operation to complete before timing out.</span></span>  
  
### <a name="maxoutboundchannelsperendpoint"></a><span data-ttu-id="fd316-117">MaxOutboundChannelsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="fd316-117">MaxOutboundChannelsPerEndpoint</span></span>  
 <span data-ttu-id="fd316-118">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="fd316-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="fd316-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="fd316-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fd316-120">El número máximo de canales de salida para cada extremo.</span><span class="sxs-lookup"><span data-stu-id="fd316-120">The maximum number of outbound channels for each endpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd316-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fd316-121">Requirements</span></span>  
  
|<span data-ttu-id="fd316-122">MOF</span><span class="sxs-lookup"><span data-stu-id="fd316-122">MOF</span></span>|<span data-ttu-id="fd316-123">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="fd316-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="fd316-124">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="fd316-124">Namespace</span></span>|<span data-ttu-id="fd316-125">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="fd316-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fd316-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="fd316-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.ChannelPoolSettings>
