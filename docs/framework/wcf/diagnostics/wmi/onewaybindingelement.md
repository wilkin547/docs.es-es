---
title: OneWayBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5c7e17c3-39b9-4214-ae08-9e6141734305
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: abaacfb6541d41019a8d0cd6df53913c6b7911f2
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="onewaybindingelement"></a><span data-ttu-id="af751-102">OneWayBindingElement</span><span class="sxs-lookup"><span data-stu-id="af751-102">OneWayBindingElement</span></span>
<span data-ttu-id="af751-103">OneWayBindingElement</span><span class="sxs-lookup"><span data-stu-id="af751-103">OneWayBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af751-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="af751-104">Syntax</span></span>  
  
```  
class OneWayBindingElement : BindingElement  
{  
  ChannelPoolSettings ChannelPoolSettings;  
  sint32 MaxAcceptedChannels;  
  boolean PacketRoutable;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="af751-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="af751-105">Methods</span></span>  
 <span data-ttu-id="af751-106">La clase OneWayBindingElement no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="af751-106">The OneWayBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="af751-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="af751-107">Properties</span></span>  
 <span data-ttu-id="af751-108">La clase OneWayBindingElement tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="af751-108">The OneWayBindingElement class has the following properties:</span></span>  
  
### <a name="channelpoolsettings"></a><span data-ttu-id="af751-109">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="af751-109">ChannelPoolSettings</span></span>  
 <span data-ttu-id="af751-110">Tipo de datos: ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="af751-110">Data type: ChannelPoolSettings</span></span>  
  
 <span data-ttu-id="af751-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="af751-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="af751-112">La configuración del grupo de canales.</span><span class="sxs-lookup"><span data-stu-id="af751-112">The channel pool settings.</span></span>  
  
### <a name="maxacceptedchannels"></a><span data-ttu-id="af751-113">MaxAcceptedChannels</span><span class="sxs-lookup"><span data-stu-id="af751-113">MaxAcceptedChannels</span></span>  
 <span data-ttu-id="af751-114">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="af751-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="af751-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="af751-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="af751-116">El número máximo de canales aceptados.</span><span class="sxs-lookup"><span data-stu-id="af751-116">The maximum number of accepted channels.</span></span>  
  
### <a name="packetroutable"></a><span data-ttu-id="af751-117">PacketRoutable</span><span class="sxs-lookup"><span data-stu-id="af751-117">PacketRoutable</span></span>  
 <span data-ttu-id="af751-118">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="af751-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="af751-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="af751-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="af751-120">Valor que indica si el paquete se puede enrutar.</span><span class="sxs-lookup"><span data-stu-id="af751-120">A value that indicates whether the packet is routable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af751-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="af751-121">Requirements</span></span>  
  
|<span data-ttu-id="af751-122">MOF</span><span class="sxs-lookup"><span data-stu-id="af751-122">MOF</span></span>|<span data-ttu-id="af751-123">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="af751-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="af751-124">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="af751-124">Namespace</span></span>|<span data-ttu-id="af751-125">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="af751-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="af751-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="af751-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.OneWayBindingElement>
