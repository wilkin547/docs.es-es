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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d246acbf314a83ca3f8113e9a2fb223ac0ebcafe
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59223711"
---
# <a name="icorprofilermoduleenumgetcount-method"></a><span data-ttu-id="8e397-102">ICorProfilerModuleEnum::GetCount (Método)</span><span class="sxs-lookup"><span data-stu-id="8e397-102">ICorProfilerModuleEnum::GetCount Method</span></span>
<span data-ttu-id="8e397-103">Obtiene el número de módulos administrados que se cargaron en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8e397-103">Gets the number of managed modules that were loaded into the application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e397-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8e397-104">Syntax</span></span>  
  
```  
HRESULT GetCount([out] ULONG * pcelt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8e397-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8e397-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="8e397-106">[out] El número de módulos en tiempo de ejecución de la colección.</span><span class="sxs-lookup"><span data-stu-id="8e397-106">[out] The number of runtime modules in the collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e397-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8e397-107">Requirements</span></span>  
 <span data-ttu-id="8e397-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8e397-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e397-109">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8e397-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8e397-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8e397-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8e397-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e397-111">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e397-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="8e397-112">See also</span></span>

- [<span data-ttu-id="8e397-113">ICorProfilerModuleEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8e397-113">ICorProfilerModuleEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)
- [<span data-ttu-id="8e397-114">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="8e397-114">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
