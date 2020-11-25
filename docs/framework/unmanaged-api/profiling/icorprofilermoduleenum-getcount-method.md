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
ms.openlocfilehash: 53009a1805056b83047299ebdca8f21d98ad5137
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732988"
---
# <a name="icorprofilermoduleenumgetcount-method"></a><span data-ttu-id="75d8e-102">ICorProfilerModuleEnum::GetCount (Método)</span><span class="sxs-lookup"><span data-stu-id="75d8e-102">ICorProfilerModuleEnum::GetCount Method</span></span>

<span data-ttu-id="75d8e-103">Obtiene el número de módulos administrados que se cargaron en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="75d8e-103">Gets the number of managed modules that were loaded into the application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75d8e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="75d8e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount([out] ULONG * pcelt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="75d8e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="75d8e-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="75d8e-106">enuncia El número de módulos en tiempo de ejecución de la colección.</span><span class="sxs-lookup"><span data-stu-id="75d8e-106">[out] The number of runtime modules in the collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75d8e-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="75d8e-107">Requirements</span></span>  

 <span data-ttu-id="75d8e-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="75d8e-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75d8e-109">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="75d8e-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="75d8e-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="75d8e-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="75d8e-111">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75d8e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75d8e-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="75d8e-112">See also</span></span>

- [<span data-ttu-id="75d8e-113">ICorProfilerModuleEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="75d8e-113">ICorProfilerModuleEnum Interface</span></span>](icorprofilermoduleenum-interface.md)
- [<span data-ttu-id="75d8e-114">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="75d8e-114">Profiling Interfaces</span></span>](profiling-interfaces.md)
