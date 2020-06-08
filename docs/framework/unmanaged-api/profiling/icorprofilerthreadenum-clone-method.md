---
title: ICorProfilerThreadEnum::Clone (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerThreadEnum.Clone
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerThreadEnum::Clone
helpviewer_keywords:
- Clone method, ICorProfilerThreadEnum interface [.NET Framework profiling]
- ICorProfilerThreadEnum::Clone method [.NET Framework profiling]
ms.assetid: 5a278bc9-88e2-4c69-b035-9d550dd77081
topic_type:
- apiref
ms.openlocfilehash: 890bb9bdd3b639d38f4f290eed86ad72b6a53f0f
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84494454"
---
# <a name="icorprofilerthreadenumclone-method"></a><span data-ttu-id="d78ba-102">ICorProfilerThreadEnum::Clone (Método)</span><span class="sxs-lookup"><span data-stu-id="d78ba-102">ICorProfilerThreadEnum::Clone Method</span></span>
<span data-ttu-id="d78ba-103">Obtiene un puntero de interfaz a una copia de esta interfaz [ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="d78ba-103">Gets an interface pointer to a copy of this [ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d78ba-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d78ba-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone (    [out] ICorProfilerThreadEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d78ba-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d78ba-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="d78ba-106">enuncia Puntero al puntero de interfaz, que, a su vez, apunta a la copia de esta interfaz [ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="d78ba-106">[out] A pointer to the interface pointer, which, in turn, points to the copy of this [ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md) interface.</span></span> <span data-ttu-id="d78ba-107">La copia del enumerador mantiene su propio estado de enumeración por separado de este enumerador.</span><span class="sxs-lookup"><span data-stu-id="d78ba-107">The copy of the enumerator maintains its own enumeration state separately from this enumerator.</span></span> <span data-ttu-id="d78ba-108">Sin embargo, la posición inicial del cursor de la copia es la misma que la posición actual del cursor del enumerador.</span><span class="sxs-lookup"><span data-stu-id="d78ba-108">However, the initial cursor position of the copy is the same as this current cursor position of the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d78ba-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d78ba-109">Requirements</span></span>  
 <span data-ttu-id="d78ba-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d78ba-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d78ba-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d78ba-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d78ba-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d78ba-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d78ba-113">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d78ba-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d78ba-114">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="d78ba-114">See also</span></span>

- [<span data-ttu-id="d78ba-115">ICorProfilerThreadEnum</span><span class="sxs-lookup"><span data-stu-id="d78ba-115">ICorProfilerThreadEnum</span></span>](icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="d78ba-116">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="d78ba-116">Profiling Interfaces</span></span>](profiling-interfaces.md)
