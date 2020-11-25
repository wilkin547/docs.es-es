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
ms.openlocfilehash: de2584b56701f4cffb6a108a5872641ec40e5762
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702529"
---
# <a name="icorprofilerthreadenumclone-method"></a><span data-ttu-id="ae2be-102">ICorProfilerThreadEnum::Clone (Método)</span><span class="sxs-lookup"><span data-stu-id="ae2be-102">ICorProfilerThreadEnum::Clone Method</span></span>

<span data-ttu-id="ae2be-103">Obtiene un puntero de interfaz a una copia de esta interfaz [ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="ae2be-103">Gets an interface pointer to a copy of this [ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae2be-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ae2be-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone (    [out] ICorProfilerThreadEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ae2be-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ae2be-105">Parameters</span></span>  

 `ppEnum`  
 <span data-ttu-id="ae2be-106">enuncia Puntero al puntero de interfaz, que, a su vez, apunta a la copia de esta interfaz [ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="ae2be-106">[out] A pointer to the interface pointer, which, in turn, points to the copy of this [ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md) interface.</span></span> <span data-ttu-id="ae2be-107">La copia del enumerador mantiene su propio estado de enumeración por separado de este enumerador.</span><span class="sxs-lookup"><span data-stu-id="ae2be-107">The copy of the enumerator maintains its own enumeration state separately from this enumerator.</span></span> <span data-ttu-id="ae2be-108">Sin embargo, la posición inicial del cursor de la copia es la misma que la posición actual del cursor del enumerador.</span><span class="sxs-lookup"><span data-stu-id="ae2be-108">However, the initial cursor position of the copy is the same as this current cursor position of the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae2be-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ae2be-109">Requirements</span></span>  

 <span data-ttu-id="ae2be-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ae2be-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae2be-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ae2be-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ae2be-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ae2be-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ae2be-113">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae2be-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae2be-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ae2be-114">See also</span></span>

- [<span data-ttu-id="ae2be-115">ICorProfilerThreadEnum</span><span class="sxs-lookup"><span data-stu-id="ae2be-115">ICorProfilerThreadEnum</span></span>](icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="ae2be-116">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="ae2be-116">Profiling Interfaces</span></span>](profiling-interfaces.md)
