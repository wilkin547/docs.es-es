---
description: 'Más información sobre: IGCHost:: Setgcstartuplimits ((método)'
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
ms.openlocfilehash: 91c74d54189bbfb7e9f208e507fe6e75b7023e00
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99709508"
---
# <a name="igchostsetgcstartuplimits-method"></a><span data-ttu-id="48012-103">IGCHost::SetGCStartupLimits (Método)</span><span class="sxs-lookup"><span data-stu-id="48012-103">IGCHost::SetGCStartupLimits Method</span></span>

<span data-ttu-id="48012-104">Establece el tamaño del segmento y el tamaño máximo de la generación 0.</span><span class="sxs-lookup"><span data-stu-id="48012-104">Sets the segment size and the maximum size for generation 0.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="48012-105">A partir del .NET Framework 4,5, puede establecer el tamaño del segmento y el tamaño máximo de la generación 0 en valores mayores que mediante `DWORD` el método [igchost2 (:: setgcstartuplimitsex (](igchost2-setgcstartuplimitsex-method.md) .</span><span class="sxs-lookup"><span data-stu-id="48012-105">Starting with the .NET Framework 4.5, you can set segment size and maximum generation 0 size to values greater than `DWORD` by using the [IGCHost2::SetGCStartupLimitsEx](igchost2-setgcstartuplimitsex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48012-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="48012-106">Syntax</span></span>  
  
```cpp  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,  
    [in] DWORD MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="48012-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="48012-107">Parameters</span></span>  

 `SegmentSize`  
 <span data-ttu-id="48012-108">de Tamaño del segmento utilizado por el sistema de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="48012-108">[in] The size of the segment used by the garbage collection system.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="48012-109">de Tamaño máximo de la generación 0.</span><span class="sxs-lookup"><span data-stu-id="48012-109">[in] The maximum size for generation 0.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="48012-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="48012-110">Remarks</span></span>  

 <span data-ttu-id="48012-111">`SetGCStartupLimits`Solo se puede llamar una vez al método.</span><span class="sxs-lookup"><span data-stu-id="48012-111">The `SetGCStartupLimits` method may be called only once.</span></span> <span data-ttu-id="48012-112">Estos valores no se pueden cambiar más adelante.</span><span class="sxs-lookup"><span data-stu-id="48012-112">These values cannot be changed later.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48012-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="48012-113">Requirements</span></span>  

 <span data-ttu-id="48012-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48012-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48012-115">**Encabezado:** GCHost. idl, GCHost. h</span><span class="sxs-lookup"><span data-stu-id="48012-115">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="48012-116">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="48012-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="48012-117">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48012-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48012-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="48012-118">See also</span></span>

- [<span data-ttu-id="48012-119">IGCHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="48012-119">IGCHost Interface</span></span>](igchost-interface.md)
