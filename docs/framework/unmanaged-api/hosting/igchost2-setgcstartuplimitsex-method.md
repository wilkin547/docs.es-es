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
ms.openlocfilehash: d78f81093e61c40eaec334f957d8583eeb593f5e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134814"
---
# <a name="igchost2setgcstartuplimitsex-method"></a><span data-ttu-id="0388a-102">IGCHost2::SetGCStartupLimitsEx (Método)</span><span class="sxs-lookup"><span data-stu-id="0388a-102">IGCHost2::SetGCStartupLimitsEx Method</span></span>
<span data-ttu-id="0388a-103">Establece el tamaño del segmento y el tamaño máximo de la generación 0.</span><span class="sxs-lookup"><span data-stu-id="0388a-103">Sets the segment size and the maximum size for generation 0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0388a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0388a-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGCStartupLimitsEx (  
    [in] SIZE_T SegmentSize,  
    [in] SIZE_T MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0388a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0388a-105">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="0388a-106">de Tamaño del segmento utilizado por el sistema de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="0388a-106">[in] The size of the segment used by the garbage collection system.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="0388a-107">de Tamaño máximo de la generación 0.</span><span class="sxs-lookup"><span data-stu-id="0388a-107">[in] The maximum size for generation 0.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0388a-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0388a-108">Remarks</span></span>  
 <span data-ttu-id="0388a-109">Los valores que `SetGCStartupLimitsEx` establece solo se pueden especificar antes de que se inicie el host.</span><span class="sxs-lookup"><span data-stu-id="0388a-109">The values that `SetGCStartupLimitsEx` sets can be specified only before the host is started.</span></span> <span data-ttu-id="0388a-110">Estos valores no se pueden cambiar más adelante.</span><span class="sxs-lookup"><span data-stu-id="0388a-110">These values cannot be changed later.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0388a-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0388a-111">Requirements</span></span>  
 <span data-ttu-id="0388a-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0388a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0388a-113">**Encabezado:** GCHost. idl, GCHost. h</span><span class="sxs-lookup"><span data-stu-id="0388a-113">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="0388a-114">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="0388a-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0388a-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0388a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0388a-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="0388a-116">See also</span></span>

- [<span data-ttu-id="0388a-117">IGCHost2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0388a-117">IGCHost2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost2-interface.md)
