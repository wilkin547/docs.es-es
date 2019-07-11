---
title: IGCHost::SetGCStartupLimits (Método)
ms.date: 03/30/2017
api_name:
- IGCHost.SetGCStartupLimits
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetGCStartupLimits
helpviewer_keywords:
- SetGCStartupLimits method, IGCHost interface [.NET Framework hosting]
- IGCHost::SetGCStartupLimits method [.NET Framework hosting]
ms.assetid: cae53926-82ac-4d1d-b297-0bde0bd1bebb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c9104550438a2a066cdf052b8d6592e86b831194
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67749985"
---
# <a name="igchostsetgcstartuplimits-method"></a><span data-ttu-id="d6f4f-102">IGCHost::SetGCStartupLimits (Método)</span><span class="sxs-lookup"><span data-stu-id="d6f4f-102">IGCHost::SetGCStartupLimits Method</span></span>
<span data-ttu-id="d6f4f-103">Establece el tamaño del segmento y el tamaño máximo para la generación 0.</span><span class="sxs-lookup"><span data-stu-id="d6f4f-103">Sets the segment size and the maximum size for generation 0.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d6f4f-104">A partir de .NET Framework 4.5, puede establecer el tamaño de segmento y el tamaño máximo de generación 0 a los valores mayor `DWORD` utilizando el [Igchost2](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="d6f4f-104">Starting with the .NET Framework 4.5, you can set segment size and maximum generation 0 size to values greater than `DWORD` by using the [IGCHost2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6f4f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d6f4f-105">Syntax</span></span>  
  
```cpp  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,  
    [in] DWORD MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d6f4f-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d6f4f-106">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="d6f4f-107">[in] El tamaño del segmento utilizado por el sistema de recopilación de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="d6f4f-107">[in] The size of the segment used by the garbage collection system.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="d6f4f-108">[in] El tamaño máximo para la generación 0.</span><span class="sxs-lookup"><span data-stu-id="d6f4f-108">[in] The maximum size for generation 0.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d6f4f-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d6f4f-109">Remarks</span></span>  
 <span data-ttu-id="d6f4f-110">El `SetGCStartupLimits` puede llamar al método una sola vez.</span><span class="sxs-lookup"><span data-stu-id="d6f4f-110">The `SetGCStartupLimits` method may be called only once.</span></span> <span data-ttu-id="d6f4f-111">No se puede cambiar estos valores más adelante.</span><span class="sxs-lookup"><span data-stu-id="d6f4f-111">These values cannot be changed later.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6f4f-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d6f4f-112">Requirements</span></span>  
 <span data-ttu-id="d6f4f-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d6f4f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6f4f-114">**Encabezado**: GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="d6f4f-114">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="d6f4f-115">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d6f4f-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d6f4f-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6f4f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6f4f-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="d6f4f-117">See also</span></span>

- [<span data-ttu-id="d6f4f-118">IGCHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d6f4f-118">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
