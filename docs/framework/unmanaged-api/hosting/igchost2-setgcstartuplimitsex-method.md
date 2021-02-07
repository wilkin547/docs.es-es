---
description: 'Más información sobre: Igchost2 (:: Setgcstartuplimitsex ((método)'
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
ms.openlocfilehash: 32d3bcbb467a1a418c7123779c881c46e983edef
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99709313"
---
# <a name="igchost2setgcstartuplimitsex-method"></a><span data-ttu-id="15f84-103">IGCHost2::SetGCStartupLimitsEx (Método)</span><span class="sxs-lookup"><span data-stu-id="15f84-103">IGCHost2::SetGCStartupLimitsEx Method</span></span>

<span data-ttu-id="15f84-104">Establece el tamaño del segmento y el tamaño máximo de la generación 0.</span><span class="sxs-lookup"><span data-stu-id="15f84-104">Sets the segment size and the maximum size for generation 0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15f84-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="15f84-105">Syntax</span></span>  
  
```cpp  
HRESULT SetGCStartupLimitsEx (  
    [in] SIZE_T SegmentSize,  
    [in] SIZE_T MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="15f84-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="15f84-106">Parameters</span></span>  

 `SegmentSize`  
 <span data-ttu-id="15f84-107">de Tamaño del segmento utilizado por el sistema de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="15f84-107">[in] The size of the segment used by the garbage collection system.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="15f84-108">de Tamaño máximo de la generación 0.</span><span class="sxs-lookup"><span data-stu-id="15f84-108">[in] The maximum size for generation 0.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="15f84-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="15f84-109">Remarks</span></span>  

 <span data-ttu-id="15f84-110">Los valores que `SetGCStartupLimitsEx` establece se pueden especificar solo antes de que se inicie el host.</span><span class="sxs-lookup"><span data-stu-id="15f84-110">The values that `SetGCStartupLimitsEx` sets can be specified only before the host is started.</span></span> <span data-ttu-id="15f84-111">Estos valores no se pueden cambiar más adelante.</span><span class="sxs-lookup"><span data-stu-id="15f84-111">These values cannot be changed later.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15f84-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="15f84-112">Requirements</span></span>  

 <span data-ttu-id="15f84-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15f84-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15f84-114">**Encabezado:** GCHost. idl, GCHost. h</span><span class="sxs-lookup"><span data-stu-id="15f84-114">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="15f84-115">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="15f84-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="15f84-116">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15f84-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15f84-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="15f84-117">See also</span></span>

- [<span data-ttu-id="15f84-118">IGCHost2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="15f84-118">IGCHost2 Interface</span></span>](igchost2-interface.md)
