---
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
ms.openlocfilehash: ae9f6b7865a80e3edc4cae8fd1298e5eed864377
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722835"
---
# <a name="icorprofilermoduleenumclone-method"></a><span data-ttu-id="bd93b-102">ICorProfilerModuleEnum::Clone (Método)</span><span class="sxs-lookup"><span data-stu-id="bd93b-102">ICorProfilerModuleEnum::Clone Method</span></span>

<span data-ttu-id="bd93b-103">Obtiene un puntero de interfaz a una copia de esta interfaz [ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="bd93b-103">Gets an interface pointer to a copy of this [ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd93b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bd93b-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone([out] ICorProfilerObjectEnum **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bd93b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bd93b-105">Parameters</span></span>  

 `ppEnum`  
 <span data-ttu-id="bd93b-106">enuncia Puntero al puntero de interfaz que a su vez apunta a la copia de esta interfaz [ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="bd93b-106">[out] A pointer to the interface pointer that in turn points to the copy of this [ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md) interface.</span></span> <span data-ttu-id="bd93b-107">La copia del enumerador mantiene su propio estado de enumeración por separado de este enumerador.</span><span class="sxs-lookup"><span data-stu-id="bd93b-107">The copy of the enumerator maintains its own enumeration state separately from this enumerator.</span></span> <span data-ttu-id="bd93b-108">Sin embargo, la posición inicial del cursor de la copia es la misma que la posición actual del cursor de este enumerador.</span><span class="sxs-lookup"><span data-stu-id="bd93b-108">However, the copy's initial cursor position is the same as this enumerator's current cursor position.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd93b-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bd93b-109">Requirements</span></span>  

 <span data-ttu-id="bd93b-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bd93b-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd93b-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bd93b-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bd93b-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bd93b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bd93b-113">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd93b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd93b-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bd93b-114">See also</span></span>

- [<span data-ttu-id="bd93b-115">ICorProfilerModuleEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bd93b-115">ICorProfilerModuleEnum Interface</span></span>](icorprofilermoduleenum-interface.md)
- [<span data-ttu-id="bd93b-116">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="bd93b-116">Profiling Interfaces</span></span>](profiling-interfaces.md)
