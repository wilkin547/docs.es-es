---
title: ICorProfilerModuleEnum::GetCount (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerModuleEnum.GetCount Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerModuleEnum::GetCount
helpviewer_keywords:
- ICorProfilerModuleEnum::GetCount method [.NET Framework profiling]
- GetCount method, ICorProfilerModuleEnum interface [.NET Framework profiling]
ms.assetid: f0a4a5e0-4689-474b-b0f4-37ca0639c918
topic_type:
- apiref
ms.openlocfilehash: 604ecb2122cce6e24f0e5168fa286a523d8bb4f7
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84495078"
---
# <a name="icorprofilermoduleenumgetcount-method"></a><span data-ttu-id="4de66-102">ICorProfilerModuleEnum::GetCount (Método)</span><span class="sxs-lookup"><span data-stu-id="4de66-102">ICorProfilerModuleEnum::GetCount Method</span></span>
<span data-ttu-id="4de66-103">Obtiene el número de módulos administrados que se cargaron en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4de66-103">Gets the number of managed modules that were loaded into the application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4de66-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4de66-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount([out] ULONG * pcelt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4de66-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4de66-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="4de66-106">enuncia El número de módulos en tiempo de ejecución de la colección.</span><span class="sxs-lookup"><span data-stu-id="4de66-106">[out] The number of runtime modules in the collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4de66-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4de66-107">Requirements</span></span>  
 <span data-ttu-id="4de66-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4de66-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4de66-109">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4de66-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4de66-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4de66-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4de66-111">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4de66-111">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4de66-112">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="4de66-112">See also</span></span>

- [<span data-ttu-id="4de66-113">ICorProfilerModuleEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4de66-113">ICorProfilerModuleEnum Interface</span></span>](icorprofilermoduleenum-interface.md)
- [<span data-ttu-id="4de66-114">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="4de66-114">Profiling Interfaces</span></span>](profiling-interfaces.md)
