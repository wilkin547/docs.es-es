---
description: 'Más información acerca de: ICorProfilerFunctionEnum:: Clone (método)'
title: ICorProfilerFunctionEnum::Clone (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionEnum.Clone Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionEnum::Clone
helpviewer_keywords:
- ICorProfilerFunctionEnum::Clone method [.NET Framework profiling]
- Clone method, ICorProfilerFunctionEnum interface [.NET Framework profiling]
ms.assetid: 0c3d4835-e111-4e82-af6d-53f140b8f2c9
topic_type:
- apiref
ms.openlocfilehash: 6cadadd98f64a27de0cd4e7d264fe797d22c33a0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99737680"
---
# <a name="icorprofilerfunctionenumclone-method"></a><span data-ttu-id="d6cea-103">ICorProfilerFunctionEnum::Clone (Método)</span><span class="sxs-lookup"><span data-stu-id="d6cea-103">ICorProfilerFunctionEnum::Clone Method</span></span>

<span data-ttu-id="d6cea-104">Obtiene un puntero de interfaz a una copia de esta interfaz [ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="d6cea-104">Gets an interface pointer to a copy of this [ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6cea-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d6cea-105">Syntax</span></span>  
  
```cpp  
HRESULT Clone([out] ICorProfilerFunctionEnum **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d6cea-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d6cea-106">Parameters</span></span>  

 `ppEnum`  
 <span data-ttu-id="d6cea-107">enuncia Un puntero al puntero de interfaz, que, a su vez, apunta a la copia de esta interfaz [ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="d6cea-107">[out] A pointer to the interface pointer, which, in turn, points to the copy of this [ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md) interface.</span></span> <span data-ttu-id="d6cea-108">La copia del enumerador mantiene su propio estado de enumeración por separado de este enumerador.</span><span class="sxs-lookup"><span data-stu-id="d6cea-108">The copy of the enumerator maintains its own enumeration state separately from this enumerator.</span></span> <span data-ttu-id="d6cea-109">Sin embargo, la posición inicial del cursor de la copia es la misma que la posición actual del cursor de este enumerador.</span><span class="sxs-lookup"><span data-stu-id="d6cea-109">However, the copy's initial cursor position is the same as this enumerator's current cursor position.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6cea-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d6cea-110">Requirements</span></span>  

 <span data-ttu-id="d6cea-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d6cea-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6cea-112">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d6cea-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d6cea-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d6cea-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d6cea-114">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6cea-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6cea-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="d6cea-115">See also</span></span>

- [<span data-ttu-id="d6cea-116">ICorProfilerFunctionEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d6cea-116">ICorProfilerFunctionEnum Interface</span></span>](icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="d6cea-117">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="d6cea-117">Profiling Interfaces</span></span>](profiling-interfaces.md)
