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
ms.openlocfilehash: cbe94aa67c9cf9ac587b7fca9f5cbeca4870506b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33437214"
---
# <a name="igchostsetgcstartuplimits-method"></a><span data-ttu-id="58bce-102">IGCHost::SetGCStartupLimits (Método)</span><span class="sxs-lookup"><span data-stu-id="58bce-102">IGCHost::SetGCStartupLimits Method</span></span>
<span data-ttu-id="58bce-103">Establece el tamaño del segmento y el tamaño máximo para la generación 0.</span><span class="sxs-lookup"><span data-stu-id="58bce-103">Sets the segment size and the maximum size for generation 0.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="58bce-104">A partir de la [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], puede establecer un tamaño de segmento y mayor que los valores de tamaño máximo de generación 0 a `DWORD` mediante el uso de la [igchost2:: Setgcstartuplimitsex](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="58bce-104">Starting with the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], you can set segment size and maximum generation 0 size to values greater than `DWORD` by using the [IGCHost2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58bce-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="58bce-105">Syntax</span></span>  
  
```  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,  
    [in] DWORD MaxGen0Size  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="58bce-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="58bce-106">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="58bce-107">[in] El tamaño del segmento utilizado por el sistema de recopilación de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="58bce-107">[in] The size of the segment used by the garbage collection system.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="58bce-108">[in] El tamaño máximo para la generación 0.</span><span class="sxs-lookup"><span data-stu-id="58bce-108">[in] The maximum size for generation 0.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="58bce-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="58bce-109">Remarks</span></span>  
 <span data-ttu-id="58bce-110">El `SetGCStartupLimits` sólo una vez puede llamar al método.</span><span class="sxs-lookup"><span data-stu-id="58bce-110">The `SetGCStartupLimits` method may be called only once.</span></span> <span data-ttu-id="58bce-111">Estos valores no se puede cambiar más adelante.</span><span class="sxs-lookup"><span data-stu-id="58bce-111">These values cannot be changed later.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58bce-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="58bce-112">Requirements</span></span>  
 <span data-ttu-id="58bce-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="58bce-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58bce-114">**Encabezado:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="58bce-114">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="58bce-115">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="58bce-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="58bce-116">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58bce-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58bce-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="58bce-117">See Also</span></span>  
 [<span data-ttu-id="58bce-118">IGCHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="58bce-118">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
