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
ms.openlocfilehash: 9aaf1a282435e3f52b2c2d8f3d17254b877e61cc
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442767"
---
# <a name="icorprofilermoduleenumgetcount-method"></a><span data-ttu-id="f4f0b-102">ICorProfilerModuleEnum::GetCount (Método)</span><span class="sxs-lookup"><span data-stu-id="f4f0b-102">ICorProfilerModuleEnum::GetCount Method</span></span>
<span data-ttu-id="f4f0b-103">Obtiene el número de módulos administrados que se cargaron en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f4f0b-103">Gets the number of managed modules that were loaded into the application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4f0b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f4f0b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount([out] ULONG * pcelt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f4f0b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f4f0b-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="f4f0b-106">[out] The number of runtime modules in the collection.</span><span class="sxs-lookup"><span data-stu-id="f4f0b-106">[out] The number of runtime modules in the collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4f0b-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f4f0b-107">Requirements</span></span>  
 <span data-ttu-id="f4f0b-108">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4f0b-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4f0b-109">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f4f0b-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f4f0b-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f4f0b-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f4f0b-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4f0b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4f0b-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="f4f0b-112">See also</span></span>

- [<span data-ttu-id="f4f0b-113">ICorProfilerModuleEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f4f0b-113">ICorProfilerModuleEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)
- [<span data-ttu-id="f4f0b-114">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="f4f0b-114">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
