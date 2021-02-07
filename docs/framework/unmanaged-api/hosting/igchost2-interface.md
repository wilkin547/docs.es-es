---
description: 'Más información acerca de: interfaz Igchost2 ('
title: IGCHost2 (Interfaz)
ms.date: 03/30/2017
api_name:
- IGCHost2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IGCHost2
helpviewer_keywords:
- IGCHost2 interface [.NET Framework hosting]
ms.assetid: e5323fa4-18ac-424d-859d-a65a550d08d9
topic_type:
- apiref
ms.openlocfilehash: e32a4894fcff3600c9385f0f559443e23b2bc307
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99709326"
---
# <a name="igchost2-interface"></a><span data-ttu-id="0db0a-103">IGCHost2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0db0a-103">IGCHost2 Interface</span></span>

<span data-ttu-id="0db0a-104">Proporciona métodos para obtener información sobre el sistema de recolección de elementos no utilizados y para controlar algunos aspectos de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="0db0a-104">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0db0a-105">En el caso del nuevo desarrollo, se recomienda utilizar la interfaz [iclrgcmanager2 (](iclrgcmanager2-interface.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="0db0a-105">For new development, we recommend that you use the [ICLRGCManager2](iclrgcmanager2-interface.md) interface instead.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0db0a-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="0db0a-106">Methods</span></span>  
  
|<span data-ttu-id="0db0a-107">Método</span><span class="sxs-lookup"><span data-stu-id="0db0a-107">Method</span></span>|<span data-ttu-id="0db0a-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="0db0a-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0db0a-109">SetGCStartupLimitsEx (Método)</span><span class="sxs-lookup"><span data-stu-id="0db0a-109">SetGCStartupLimitsEx Method</span></span>](igchost2-setgcstartuplimitsex-method.md)|<span data-ttu-id="0db0a-110">Establece el tamaño del segmento y el tamaño máximo de la generación 0.</span><span class="sxs-lookup"><span data-stu-id="0db0a-110">Sets the segment size and the maximum size for generation 0.</span></span> <span data-ttu-id="0db0a-111">Habilita la generación 0 y los tamaños de segmento mayores que `DWORD` .</span><span class="sxs-lookup"><span data-stu-id="0db0a-111">Enables generation 0 and segment sizes larger than `DWORD`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0db0a-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0db0a-112">Requirements</span></span>  

 <span data-ttu-id="0db0a-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0db0a-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0db0a-114">**Encabezado:** GCHost. idl, GCHost. h</span><span class="sxs-lookup"><span data-stu-id="0db0a-114">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="0db0a-115">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0db0a-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0db0a-116">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0db0a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0db0a-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="0db0a-117">See also</span></span>

- [<span data-ttu-id="0db0a-118">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="0db0a-118">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="0db0a-119">Interfaces de hospedaje de CLR</span><span class="sxs-lookup"><span data-stu-id="0db0a-119">CLR Hosting Interfaces</span></span>](clr-hosting-interfaces.md)
- [<span data-ttu-id="0db0a-120">CorRuntimeHost (Coclase)</span><span class="sxs-lookup"><span data-stu-id="0db0a-120">CorRuntimeHost Coclass</span></span>](corruntimehost-coclass.md)
