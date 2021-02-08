---
description: 'Más información sobre: ICorProfilerThreadEnum:: Clone (método)'
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
ms.openlocfilehash: 00920484ed6f089f40281ea2590e6d9c27cd3268
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99783799"
---
# <a name="icorprofilerthreadenumclone-method"></a><span data-ttu-id="bda0c-103">ICorProfilerThreadEnum::Clone (Método)</span><span class="sxs-lookup"><span data-stu-id="bda0c-103">ICorProfilerThreadEnum::Clone Method</span></span>

<span data-ttu-id="bda0c-104">Obtiene un puntero de interfaz a una copia de esta interfaz [ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="bda0c-104">Gets an interface pointer to a copy of this [ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bda0c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bda0c-105">Syntax</span></span>  
  
```cpp  
HRESULT Clone (    [out] ICorProfilerThreadEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bda0c-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bda0c-106">Parameters</span></span>  

 `ppEnum`  
 <span data-ttu-id="bda0c-107">enuncia Puntero al puntero de interfaz, que, a su vez, apunta a la copia de esta interfaz [ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="bda0c-107">[out] A pointer to the interface pointer, which, in turn, points to the copy of this [ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md) interface.</span></span> <span data-ttu-id="bda0c-108">La copia del enumerador mantiene su propio estado de enumeración por separado de este enumerador.</span><span class="sxs-lookup"><span data-stu-id="bda0c-108">The copy of the enumerator maintains its own enumeration state separately from this enumerator.</span></span> <span data-ttu-id="bda0c-109">Sin embargo, la posición inicial del cursor de la copia es la misma que la posición actual del cursor del enumerador.</span><span class="sxs-lookup"><span data-stu-id="bda0c-109">However, the initial cursor position of the copy is the same as this current cursor position of the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bda0c-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bda0c-110">Requirements</span></span>  

 <span data-ttu-id="bda0c-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bda0c-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bda0c-112">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bda0c-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bda0c-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bda0c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bda0c-114">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bda0c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bda0c-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="bda0c-115">See also</span></span>

- [<span data-ttu-id="bda0c-116">ICorProfilerThreadEnum</span><span class="sxs-lookup"><span data-stu-id="bda0c-116">ICorProfilerThreadEnum</span></span>](icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="bda0c-117">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="bda0c-117">Profiling Interfaces</span></span>](profiling-interfaces.md)
