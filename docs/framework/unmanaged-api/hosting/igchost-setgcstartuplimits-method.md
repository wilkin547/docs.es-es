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
ms.openlocfilehash: 1ae50fb3ff15097f9a6ca5839f3832bcfc58d3f3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134852"
---
# <a name="igchostsetgcstartuplimits-method"></a><span data-ttu-id="5ccfe-102">IGCHost::SetGCStartupLimits (Método)</span><span class="sxs-lookup"><span data-stu-id="5ccfe-102">IGCHost::SetGCStartupLimits Method</span></span>
<span data-ttu-id="5ccfe-103">Establece el tamaño del segmento y el tamaño máximo de la generación 0.</span><span class="sxs-lookup"><span data-stu-id="5ccfe-103">Sets the segment size and the maximum size for generation 0.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="5ccfe-104">A partir del .NET Framework 4,5, puede establecer el tamaño del segmento y el tamaño máximo de la generación 0 en valores mayores que `DWORD` mediante el método [igchost2 (:: setgcstartuplimitsex (](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) .</span><span class="sxs-lookup"><span data-stu-id="5ccfe-104">Starting with the .NET Framework 4.5, you can set segment size and maximum generation 0 size to values greater than `DWORD` by using the [IGCHost2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ccfe-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5ccfe-105">Syntax</span></span>  
  
```cpp  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,  
    [in] DWORD MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5ccfe-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5ccfe-106">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="5ccfe-107">de Tamaño del segmento utilizado por el sistema de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="5ccfe-107">[in] The size of the segment used by the garbage collection system.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="5ccfe-108">de Tamaño máximo de la generación 0.</span><span class="sxs-lookup"><span data-stu-id="5ccfe-108">[in] The maximum size for generation 0.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5ccfe-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5ccfe-109">Remarks</span></span>  
 <span data-ttu-id="5ccfe-110">Solo se puede llamar una vez al método `SetGCStartupLimits`.</span><span class="sxs-lookup"><span data-stu-id="5ccfe-110">The `SetGCStartupLimits` method may be called only once.</span></span> <span data-ttu-id="5ccfe-111">Estos valores no se pueden cambiar más adelante.</span><span class="sxs-lookup"><span data-stu-id="5ccfe-111">These values cannot be changed later.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ccfe-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5ccfe-112">Requirements</span></span>  
 <span data-ttu-id="5ccfe-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5ccfe-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ccfe-114">**Encabezado:** GCHost. idl, GCHost. h</span><span class="sxs-lookup"><span data-stu-id="5ccfe-114">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="5ccfe-115">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="5ccfe-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5ccfe-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ccfe-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ccfe-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="5ccfe-117">See also</span></span>

- [<span data-ttu-id="5ccfe-118">IGCHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5ccfe-118">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
