---
title: IGCHost2::SetGCStartupLimitsEx (Método)
ms.date: 03/30/2017
api_name:
- IGCHost2.SetGCStartupLimitsEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IGCHost2::SetGCStartupLimitsEx
helpviewer_keywords:
- IGCHost2::SetGCStartupLimitsEx method [.NET Framework hosting]
- SetGCStartupLimitsEx method, IGCHost2 interface [.NET Framework hosting]
ms.assetid: bba941c2-1c57-46d3-bbf5-5fb92700c490
topic_type:
- apiref
ms.openlocfilehash: 4dca62903a123765ceb8bb251b79455ad0e4730a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726813"
---
# <a name="igchost2setgcstartuplimitsex-method"></a><span data-ttu-id="5396a-102">IGCHost2::SetGCStartupLimitsEx (Método)</span><span class="sxs-lookup"><span data-stu-id="5396a-102">IGCHost2::SetGCStartupLimitsEx Method</span></span>

<span data-ttu-id="5396a-103">Establece el tamaño del segmento y el tamaño máximo de la generación 0.</span><span class="sxs-lookup"><span data-stu-id="5396a-103">Sets the segment size and the maximum size for generation 0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5396a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5396a-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGCStartupLimitsEx (  
    [in] SIZE_T SegmentSize,  
    [in] SIZE_T MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5396a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5396a-105">Parameters</span></span>  

 `SegmentSize`  
 <span data-ttu-id="5396a-106">de Tamaño del segmento utilizado por el sistema de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="5396a-106">[in] The size of the segment used by the garbage collection system.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="5396a-107">de Tamaño máximo de la generación 0.</span><span class="sxs-lookup"><span data-stu-id="5396a-107">[in] The maximum size for generation 0.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5396a-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5396a-108">Remarks</span></span>  

 <span data-ttu-id="5396a-109">Los valores que `SetGCStartupLimitsEx` establece se pueden especificar solo antes de que se inicie el host.</span><span class="sxs-lookup"><span data-stu-id="5396a-109">The values that `SetGCStartupLimitsEx` sets can be specified only before the host is started.</span></span> <span data-ttu-id="5396a-110">Estos valores no se pueden cambiar más adelante.</span><span class="sxs-lookup"><span data-stu-id="5396a-110">These values cannot be changed later.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5396a-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5396a-111">Requirements</span></span>  

 <span data-ttu-id="5396a-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5396a-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5396a-113">**Encabezado:** GCHost. idl, GCHost. h</span><span class="sxs-lookup"><span data-stu-id="5396a-113">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="5396a-114">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5396a-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5396a-115">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5396a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5396a-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5396a-116">See also</span></span>

- [<span data-ttu-id="5396a-117">IGCHost2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5396a-117">IGCHost2 Interface</span></span>](igchost2-interface.md)
