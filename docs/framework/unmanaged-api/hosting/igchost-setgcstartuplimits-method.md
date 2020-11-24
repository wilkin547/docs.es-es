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
ms.openlocfilehash: 0eea9dba57886edfef13c31948a9cff94c6c1bfd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687891"
---
# <a name="igchostsetgcstartuplimits-method"></a><span data-ttu-id="8eaf7-102">IGCHost::SetGCStartupLimits (Método)</span><span class="sxs-lookup"><span data-stu-id="8eaf7-102">IGCHost::SetGCStartupLimits Method</span></span>

<span data-ttu-id="8eaf7-103">Establece el tamaño del segmento y el tamaño máximo de la generación 0.</span><span class="sxs-lookup"><span data-stu-id="8eaf7-103">Sets the segment size and the maximum size for generation 0.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="8eaf7-104">A partir del .NET Framework 4,5, puede establecer el tamaño del segmento y el tamaño máximo de la generación 0 en valores mayores que mediante `DWORD` el método [igchost2 (:: setgcstartuplimitsex (](igchost2-setgcstartuplimitsex-method.md) .</span><span class="sxs-lookup"><span data-stu-id="8eaf7-104">Starting with the .NET Framework 4.5, you can set segment size and maximum generation 0 size to values greater than `DWORD` by using the [IGCHost2::SetGCStartupLimitsEx](igchost2-setgcstartuplimitsex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8eaf7-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8eaf7-105">Syntax</span></span>  
  
```cpp  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,  
    [in] DWORD MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8eaf7-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8eaf7-106">Parameters</span></span>  

 `SegmentSize`  
 <span data-ttu-id="8eaf7-107">de Tamaño del segmento utilizado por el sistema de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="8eaf7-107">[in] The size of the segment used by the garbage collection system.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="8eaf7-108">de Tamaño máximo de la generación 0.</span><span class="sxs-lookup"><span data-stu-id="8eaf7-108">[in] The maximum size for generation 0.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8eaf7-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8eaf7-109">Remarks</span></span>  

 <span data-ttu-id="8eaf7-110">`SetGCStartupLimits`Solo se puede llamar una vez al método.</span><span class="sxs-lookup"><span data-stu-id="8eaf7-110">The `SetGCStartupLimits` method may be called only once.</span></span> <span data-ttu-id="8eaf7-111">Estos valores no se pueden cambiar más adelante.</span><span class="sxs-lookup"><span data-stu-id="8eaf7-111">These values cannot be changed later.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8eaf7-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8eaf7-112">Requirements</span></span>  

 <span data-ttu-id="8eaf7-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8eaf7-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8eaf7-114">**Encabezado:** GCHost. idl, GCHost. h</span><span class="sxs-lookup"><span data-stu-id="8eaf7-114">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="8eaf7-115">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8eaf7-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8eaf7-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8eaf7-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8eaf7-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8eaf7-117">See also</span></span>

- [<span data-ttu-id="8eaf7-118">IGCHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8eaf7-118">IGCHost Interface</span></span>](igchost-interface.md)
