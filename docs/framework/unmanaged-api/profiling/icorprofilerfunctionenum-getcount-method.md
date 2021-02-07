---
description: 'Más información acerca de: ICorProfilerFunctionEnum:: GetCount (método)'
title: ICorProfilerFunctionEnum::GetCount (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionEnum.GetCount Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionEnum::GetCount
helpviewer_keywords:
- ICorProfilerFunctionEnum::GetCount method [.NET Framework profiling]
- GetCount method, ICorProfilerFunctionEnum interface [.NET Framework profiling]
ms.assetid: 62ec65e3-3e9d-400b-ae61-d24b8963995b
topic_type:
- apiref
ms.openlocfilehash: a3eccfa31676636aff7379b4080bcb85a268df6c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99737628"
---
# <a name="icorprofilerfunctionenumgetcount-method"></a><span data-ttu-id="50c78-103">ICorProfilerFunctionEnum::GetCount (Método)</span><span class="sxs-lookup"><span data-stu-id="50c78-103">ICorProfilerFunctionEnum::GetCount Method</span></span>

<span data-ttu-id="50c78-104">Obtiene el número de funciones que la aplicación cargó o que el generador de perfiles cargó forzosamente.</span><span class="sxs-lookup"><span data-stu-id="50c78-104">Gets the number of functions that were loaded by the application or forcibly loaded by the profiler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50c78-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="50c78-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCount([out] ULONG * pcelt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="50c78-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="50c78-106">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="50c78-107">enuncia El número de funciones que se cargaron.</span><span class="sxs-lookup"><span data-stu-id="50c78-107">[out] The number of functions that were loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50c78-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="50c78-108">Requirements</span></span>  

 <span data-ttu-id="50c78-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="50c78-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50c78-110">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="50c78-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="50c78-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="50c78-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="50c78-112">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50c78-112">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50c78-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="50c78-113">See also</span></span>

- [<span data-ttu-id="50c78-114">ICorProfilerFunctionEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="50c78-114">ICorProfilerFunctionEnum Interface</span></span>](icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="50c78-115">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="50c78-115">Profiling Interfaces</span></span>](profiling-interfaces.md)
