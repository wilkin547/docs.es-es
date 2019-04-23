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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: da5e90055a08227ea7cb7fa1b459fe6f5f3a81fc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59127340"
---
# <a name="igchost2setgcstartuplimitsex-method"></a><span data-ttu-id="b10c1-102">IGCHost2::SetGCStartupLimitsEx (Método)</span><span class="sxs-lookup"><span data-stu-id="b10c1-102">IGCHost2::SetGCStartupLimitsEx Method</span></span>
<span data-ttu-id="b10c1-103">Establece el tamaño del segmento y el tamaño máximo para la generación 0.</span><span class="sxs-lookup"><span data-stu-id="b10c1-103">Sets the segment size and the maximum size for generation 0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b10c1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b10c1-104">Syntax</span></span>  
  
```  
HRESULT SetGCStartupLimitsEx (  
    [in] SIZE_T SegmentSize,  
    [in] SIZE_T MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b10c1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b10c1-105">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="b10c1-106">[in] El tamaño del segmento utilizado por el sistema de recopilación de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="b10c1-106">[in] The size of the segment used by the garbage collection system.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="b10c1-107">[in] El tamaño máximo para la generación 0.</span><span class="sxs-lookup"><span data-stu-id="b10c1-107">[in] The maximum size for generation 0.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b10c1-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b10c1-108">Remarks</span></span>  
 <span data-ttu-id="b10c1-109">Los valores que `SetGCStartupLimitsEx` se pueden especificar conjuntos antes de iniciar el host.</span><span class="sxs-lookup"><span data-stu-id="b10c1-109">The values that `SetGCStartupLimitsEx` sets can be specified only before the host is started.</span></span> <span data-ttu-id="b10c1-110">No se puede cambiar estos valores más adelante.</span><span class="sxs-lookup"><span data-stu-id="b10c1-110">These values cannot be changed later.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b10c1-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b10c1-111">Requirements</span></span>  
 <span data-ttu-id="b10c1-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b10c1-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b10c1-113">**Encabezado**: GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="b10c1-113">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="b10c1-114">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b10c1-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b10c1-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b10c1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b10c1-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="b10c1-116">See also</span></span>

- [<span data-ttu-id="b10c1-117">IGCHost2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b10c1-117">IGCHost2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost2-interface.md)
