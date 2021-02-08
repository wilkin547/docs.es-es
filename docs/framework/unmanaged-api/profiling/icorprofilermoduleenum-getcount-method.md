---
description: 'Más información acerca de: ICorProfilerModuleEnum:: GetCount (método)'
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
ms.openlocfilehash: efdd812795002c25aaeb7634e7a4f4e4287553e8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99781394"
---
# <a name="icorprofilermoduleenumgetcount-method"></a><span data-ttu-id="6c723-103">ICorProfilerModuleEnum::GetCount (Método)</span><span class="sxs-lookup"><span data-stu-id="6c723-103">ICorProfilerModuleEnum::GetCount Method</span></span>

<span data-ttu-id="6c723-104">Obtiene el número de módulos administrados que se cargaron en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6c723-104">Gets the number of managed modules that were loaded into the application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c723-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6c723-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCount([out] ULONG * pcelt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6c723-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6c723-106">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="6c723-107">enuncia El número de módulos en tiempo de ejecución de la colección.</span><span class="sxs-lookup"><span data-stu-id="6c723-107">[out] The number of runtime modules in the collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c723-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6c723-108">Requirements</span></span>  

 <span data-ttu-id="6c723-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6c723-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c723-110">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6c723-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6c723-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6c723-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6c723-112">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c723-112">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c723-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="6c723-113">See also</span></span>

- [<span data-ttu-id="6c723-114">ICorProfilerModuleEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c723-114">ICorProfilerModuleEnum Interface</span></span>](icorprofilermoduleenum-interface.md)
- [<span data-ttu-id="6c723-115">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="6c723-115">Profiling Interfaces</span></span>](profiling-interfaces.md)
