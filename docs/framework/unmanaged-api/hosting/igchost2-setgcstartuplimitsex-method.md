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
ms.openlocfilehash: f92667191cad163998d233e1110365de65c0340c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33437695"
---
# <a name="igchost2setgcstartuplimitsex-method"></a><span data-ttu-id="455ff-102">IGCHost2::SetGCStartupLimitsEx (Método)</span><span class="sxs-lookup"><span data-stu-id="455ff-102">IGCHost2::SetGCStartupLimitsEx Method</span></span>
<span data-ttu-id="455ff-103">Establece el tamaño del segmento y el tamaño máximo para la generación 0.</span><span class="sxs-lookup"><span data-stu-id="455ff-103">Sets the segment size and the maximum size for generation 0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="455ff-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="455ff-104">Syntax</span></span>  
  
```  
HRESULT SetGCStartupLimitsEx (  
    [in] SIZE_T SegmentSize,  
    [in] SIZE_T MaxGen0Size  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="455ff-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="455ff-105">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="455ff-106">[in] El tamaño del segmento utilizado por el sistema de recopilación de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="455ff-106">[in] The size of the segment used by the garbage collection system.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="455ff-107">[in] El tamaño máximo para la generación 0.</span><span class="sxs-lookup"><span data-stu-id="455ff-107">[in] The maximum size for generation 0.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="455ff-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="455ff-108">Remarks</span></span>  
 <span data-ttu-id="455ff-109">Los valores que `SetGCStartupLimitsEx` se pueden especificar conjuntos sólo antes de que se inicie el host.</span><span class="sxs-lookup"><span data-stu-id="455ff-109">The values that `SetGCStartupLimitsEx` sets can be specified only before the host is started.</span></span> <span data-ttu-id="455ff-110">Estos valores no se puede cambiar más adelante.</span><span class="sxs-lookup"><span data-stu-id="455ff-110">These values cannot be changed later.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="455ff-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="455ff-111">Requirements</span></span>  
 <span data-ttu-id="455ff-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="455ff-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="455ff-113">**Encabezado:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="455ff-113">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="455ff-114">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="455ff-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="455ff-115">**Versiones de .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="455ff-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="455ff-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="455ff-116">See Also</span></span>  
 [<span data-ttu-id="455ff-117">IGCHost2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="455ff-117">IGCHost2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost2-interface.md)
