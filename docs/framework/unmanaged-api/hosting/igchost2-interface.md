---
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
ms.openlocfilehash: 7529ecd215d74eb0eedbec8b90eba367ed20d56f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687748"
---
# <a name="igchost2-interface"></a><span data-ttu-id="a1509-102">IGCHost2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a1509-102">IGCHost2 Interface</span></span>

<span data-ttu-id="a1509-103">Proporciona métodos para obtener información sobre el sistema de recolección de elementos no utilizados y para controlar algunos aspectos de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="a1509-103">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a1509-104">En el caso del nuevo desarrollo, se recomienda utilizar la interfaz [iclrgcmanager2 (](iclrgcmanager2-interface.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="a1509-104">For new development, we recommend that you use the [ICLRGCManager2](iclrgcmanager2-interface.md) interface instead.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a1509-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="a1509-105">Methods</span></span>  
  
|<span data-ttu-id="a1509-106">Método</span><span class="sxs-lookup"><span data-stu-id="a1509-106">Method</span></span>|<span data-ttu-id="a1509-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="a1509-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a1509-108">SetGCStartupLimitsEx (Método)</span><span class="sxs-lookup"><span data-stu-id="a1509-108">SetGCStartupLimitsEx Method</span></span>](igchost2-setgcstartuplimitsex-method.md)|<span data-ttu-id="a1509-109">Establece el tamaño del segmento y el tamaño máximo de la generación 0.</span><span class="sxs-lookup"><span data-stu-id="a1509-109">Sets the segment size and the maximum size for generation 0.</span></span> <span data-ttu-id="a1509-110">Habilita la generación 0 y los tamaños de segmento mayores que `DWORD` .</span><span class="sxs-lookup"><span data-stu-id="a1509-110">Enables generation 0 and segment sizes larger than `DWORD`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a1509-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a1509-111">Requirements</span></span>  

 <span data-ttu-id="a1509-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1509-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1509-113">**Encabezado:** GCHost. idl, GCHost. h</span><span class="sxs-lookup"><span data-stu-id="a1509-113">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="a1509-114">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a1509-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a1509-115">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1509-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1509-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a1509-116">See also</span></span>

- [<span data-ttu-id="a1509-117">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="a1509-117">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="a1509-118">Interfaces de hospedaje de CLR</span><span class="sxs-lookup"><span data-stu-id="a1509-118">CLR Hosting Interfaces</span></span>](clr-hosting-interfaces.md)
- [<span data-ttu-id="a1509-119">CorRuntimeHost (Coclase)</span><span class="sxs-lookup"><span data-stu-id="a1509-119">CorRuntimeHost Coclass</span></span>](corruntimehost-coclass.md)
