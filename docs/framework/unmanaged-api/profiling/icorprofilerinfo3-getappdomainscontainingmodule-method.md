---
description: 'Más información sobre: ICorProfilerInfo3:: GetAppDomainsContainingModule ((método)'
title: ICorProfilerInfo3::GetAppDomainsContainingModule (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetAppDomainsContainingModule Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetAppDomainsContainingModule
helpviewer_keywords:
- GetAppDomainsContainingModule method [.NET Framework profiling]
- ICorProfilerInfo3::GetAppDomainsContainingModule method [.NET Framework profiling]
ms.assetid: 603b3881-ea94-4dca-95cd-91eebac873a0
topic_type:
- apiref
ms.openlocfilehash: 0f0fea5b01b80b110d7ab041574dc195162cb508
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99646847"
---
# <a name="icorprofilerinfo3getappdomainscontainingmodule-method"></a><span data-ttu-id="82a71-103">ICorProfilerInfo3::GetAppDomainsContainingModule (Método)</span><span class="sxs-lookup"><span data-stu-id="82a71-103">ICorProfilerInfo3::GetAppDomainsContainingModule Method</span></span>

<span data-ttu-id="82a71-104">Obtiene los identificadores de los dominios de la aplicación en la que se cargó el módulo especificado.</span><span class="sxs-lookup"><span data-stu-id="82a71-104">Gets the identifiers of the application domains in which the given module has been loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82a71-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="82a71-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAppDomainsContainingModule(  
            [in] ModuleID moduleId,  
            [in] ULONG32 cAppDomainIds,  
            [out] ULONG32 *pcAppDomainIds,  
            [out, size_is(cAppDomainIds), length_is(*pcAppDomainIds)]  
                    AppDomainID appDomainIds[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="82a71-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="82a71-106">Parameters</span></span>  

 `moduleId`  
 <span data-ttu-id="82a71-107">[in] Identificador del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="82a71-107">[in] The ID of the loaded module.</span></span>  
  
 `cAppDomainIds`  
 <span data-ttu-id="82a71-108">[in] Tamaño de la matriz `appDomainIds`.</span><span class="sxs-lookup"><span data-stu-id="82a71-108">[in] The size of the `appDomainIds` array.</span></span>  
  
 `pcAppDomainIds`  
 <span data-ttu-id="82a71-109">[out] Puntero al número total de elementos devueltos.</span><span class="sxs-lookup"><span data-stu-id="82a71-109">[out] A pointer to the total number of returned elements.</span></span>  
  
 `appDomainIds`  
 <span data-ttu-id="82a71-110">[out] Matriz de valores de identificador de dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="82a71-110">[out] An array of application domain ID values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="82a71-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="82a71-111">Remarks</span></span>  

 <span data-ttu-id="82a71-112">El método usa búferes asignados al llamador.</span><span class="sxs-lookup"><span data-stu-id="82a71-112">The method uses caller allocated buffers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82a71-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="82a71-113">Requirements</span></span>  

 <span data-ttu-id="82a71-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="82a71-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82a71-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="82a71-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="82a71-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="82a71-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="82a71-117">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82a71-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82a71-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="82a71-118">See also</span></span>

- [<span data-ttu-id="82a71-119">ICorProfilerFunctionEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="82a71-119">ICorProfilerFunctionEnum Interface</span></span>](icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="82a71-120">ICorProfilerInfo3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="82a71-120">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="82a71-121">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="82a71-121">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="82a71-122">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="82a71-122">Profiling</span></span>](index.md)
