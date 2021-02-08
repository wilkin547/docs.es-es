---
description: 'Más información acerca de: ICorProfilerObjectEnum:: Skip (método)'
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
ms.openlocfilehash: 8a2aa5dd2b905931b97fafa4db6709aab16aacc4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99781264"
---
# <a name="icorprofilerobjectenumskip-method"></a><span data-ttu-id="5bc06-103">ICorProfilerObjectEnum::Skip (Método)</span><span class="sxs-lookup"><span data-stu-id="5bc06-103">ICorProfilerObjectEnum::Skip Method</span></span>

<span data-ttu-id="5bc06-104">Hace avanzar el cursor de este enumerador desde su posición actual para que se omita el número especificado de elementos.</span><span class="sxs-lookup"><span data-stu-id="5bc06-104">Advances the cursor of this enumerator from its current position so that the specified number of elements are skipped.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bc06-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5bc06-105">Syntax</span></span>  
  
```cpp  
HRESULT Skip (  
    [in] ULONG   celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5bc06-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5bc06-106">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="5bc06-107">de Número de elementos que se van a omitir.</span><span class="sxs-lookup"><span data-stu-id="5bc06-107">[in] The number of elements to be skipped.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5bc06-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5bc06-108">Remarks</span></span>  

 <span data-ttu-id="5bc06-109">La nueva posición del cursor de este enumerador es: (posición actual) + `celt` .</span><span class="sxs-lookup"><span data-stu-id="5bc06-109">The new position of this enumerator's cursor is: (current position) + `celt` .</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5bc06-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5bc06-110">Requirements</span></span>  

 <span data-ttu-id="5bc06-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5bc06-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5bc06-112">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5bc06-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5bc06-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5bc06-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5bc06-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5bc06-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bc06-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="5bc06-115">See also</span></span>

- [<span data-ttu-id="5bc06-116">ICorProfilerObjectEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5bc06-116">ICorProfilerObjectEnum Interface</span></span>](icorprofilerobjectenum-interface.md)
