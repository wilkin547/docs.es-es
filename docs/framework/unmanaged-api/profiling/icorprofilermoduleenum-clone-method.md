---
description: 'Más información acerca de: ICorProfilerModuleEnum:: Clone (método)'
title: ICorProfilerModuleEnum::Clone (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerModuleEnum.Clone Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerModuleEnum::Clone
helpviewer_keywords:
- Clone method, ICorProfilerModuleEnum interface [.NET Framework profiling]
- ICorProfilerModuleEnum::Clone method [.NET Framework profiling]
ms.assetid: 7dec7e36-8d88-416d-b437-abf98b76c1df
topic_type:
- apiref
ms.openlocfilehash: 0d2a235def6d3b16d661e51979742426ebe1942f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99736945"
---
# <a name="icorprofilermoduleenumclone-method"></a><span data-ttu-id="a84fb-103">ICorProfilerModuleEnum::Clone (Método)</span><span class="sxs-lookup"><span data-stu-id="a84fb-103">ICorProfilerModuleEnum::Clone Method</span></span>

<span data-ttu-id="a84fb-104">Obtiene un puntero de interfaz a una copia de esta interfaz [ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="a84fb-104">Gets an interface pointer to a copy of this [ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a84fb-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a84fb-105">Syntax</span></span>  
  
```cpp  
HRESULT Clone([out] ICorProfilerObjectEnum **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a84fb-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a84fb-106">Parameters</span></span>  

 `ppEnum`  
 <span data-ttu-id="a84fb-107">enuncia Puntero al puntero de interfaz que a su vez apunta a la copia de esta interfaz [ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="a84fb-107">[out] A pointer to the interface pointer that in turn points to the copy of this [ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md) interface.</span></span> <span data-ttu-id="a84fb-108">La copia del enumerador mantiene su propio estado de enumeración por separado de este enumerador.</span><span class="sxs-lookup"><span data-stu-id="a84fb-108">The copy of the enumerator maintains its own enumeration state separately from this enumerator.</span></span> <span data-ttu-id="a84fb-109">Sin embargo, la posición inicial del cursor de la copia es la misma que la posición actual del cursor de este enumerador.</span><span class="sxs-lookup"><span data-stu-id="a84fb-109">However, the copy's initial cursor position is the same as this enumerator's current cursor position.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a84fb-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a84fb-110">Requirements</span></span>  

 <span data-ttu-id="a84fb-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a84fb-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a84fb-112">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a84fb-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a84fb-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a84fb-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a84fb-114">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a84fb-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a84fb-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="a84fb-115">See also</span></span>

- [<span data-ttu-id="a84fb-116">ICorProfilerModuleEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a84fb-116">ICorProfilerModuleEnum Interface</span></span>](icorprofilermoduleenum-interface.md)
- [<span data-ttu-id="a84fb-117">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="a84fb-117">Profiling Interfaces</span></span>](profiling-interfaces.md)
