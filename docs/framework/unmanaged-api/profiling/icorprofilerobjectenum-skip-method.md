---
title: ICorProfilerObjectEnum::Skip (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerObjectEnum.Skip
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerObjectEnum::Skip
helpviewer_keywords:
- ICorProfilerObjectEnum::Skip method [.NET Framework profiling]
- Skip method, ICorProfilerObjectEnum interface [.NET Framework profiling]
ms.assetid: f8e498f8-f93a-4b82-bd22-55bdbf5e8d45
topic_type:
- apiref
ms.openlocfilehash: 83c6af74ebc3eb668317bd64628af17513a2aed6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702360"
---
# <a name="icorprofilerobjectenumskip-method"></a><span data-ttu-id="77848-102">ICorProfilerObjectEnum::Skip (Método)</span><span class="sxs-lookup"><span data-stu-id="77848-102">ICorProfilerObjectEnum::Skip Method</span></span>

<span data-ttu-id="77848-103">Hace avanzar el cursor de este enumerador desde su posición actual para que se omita el número especificado de elementos.</span><span class="sxs-lookup"><span data-stu-id="77848-103">Advances the cursor of this enumerator from its current position so that the specified number of elements are skipped.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77848-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="77848-104">Syntax</span></span>  
  
```cpp  
HRESULT Skip (  
    [in] ULONG   celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="77848-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="77848-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="77848-106">de Número de elementos que se van a omitir.</span><span class="sxs-lookup"><span data-stu-id="77848-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="77848-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="77848-107">Remarks</span></span>  

 <span data-ttu-id="77848-108">La nueva posición del cursor de este enumerador es: (posición actual) + `celt` .</span><span class="sxs-lookup"><span data-stu-id="77848-108">The new position of this enumerator's cursor is: (current position) + `celt` .</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77848-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="77848-109">Requirements</span></span>  

 <span data-ttu-id="77848-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="77848-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77848-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="77848-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="77848-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="77848-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="77848-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77848-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77848-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="77848-114">See also</span></span>

- [<span data-ttu-id="77848-115">ICorProfilerObjectEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="77848-115">ICorProfilerObjectEnum Interface</span></span>](icorprofilerobjectenum-interface.md)
