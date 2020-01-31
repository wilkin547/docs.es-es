---
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
ms.openlocfilehash: 56221c6b3ac40595e999f2a2a3739f023441c46d
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862417"
---
# <a name="icorprofilerinfo3getappdomainscontainingmodule-method"></a><span data-ttu-id="b0e94-102">ICorProfilerInfo3::GetAppDomainsContainingModule (Método)</span><span class="sxs-lookup"><span data-stu-id="b0e94-102">ICorProfilerInfo3::GetAppDomainsContainingModule Method</span></span>
<span data-ttu-id="b0e94-103">Obtiene los identificadores de los dominios de la aplicación en la que se cargó el módulo especificado.</span><span class="sxs-lookup"><span data-stu-id="b0e94-103">Gets the identifiers of the application domains in which the given module has been loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0e94-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b0e94-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAppDomainsContainingModule(  
            [in] ModuleID moduleId,  
            [in] ULONG32 cAppDomainIds,  
            [out] ULONG32 *pcAppDomainIds,  
            [out, size_is(cAppDomainIds), length_is(*pcAppDomainIds)]  
                    AppDomainID appDomainIds[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b0e94-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="b0e94-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="b0e94-106">[in] Identificador del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="b0e94-106">[in] The ID of the loaded module.</span></span>  
  
 `cAppDomainIds`  
 <span data-ttu-id="b0e94-107">[in] Tamaño de la matriz `appDomainIds`.</span><span class="sxs-lookup"><span data-stu-id="b0e94-107">[in] The size of the `appDomainIds` array.</span></span>  
  
 `pcAppDomainIds`  
 <span data-ttu-id="b0e94-108">[out] Puntero al número total de elementos devueltos.</span><span class="sxs-lookup"><span data-stu-id="b0e94-108">[out] A pointer to the total number of returned elements.</span></span>  
  
 `appDomainIds`  
 <span data-ttu-id="b0e94-109">[out] Matriz de valores de identificador de dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="b0e94-109">[out] An array of application domain ID values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b0e94-110">Notas</span><span class="sxs-lookup"><span data-stu-id="b0e94-110">Remarks</span></span>  
 <span data-ttu-id="b0e94-111">El método usa búferes asignados al llamador.</span><span class="sxs-lookup"><span data-stu-id="b0e94-111">The method uses caller allocated buffers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0e94-112">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="b0e94-112">Requirements</span></span>  
 <span data-ttu-id="b0e94-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0e94-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0e94-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b0e94-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b0e94-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b0e94-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b0e94-116">**.NET Framework versiones:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0e94-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0e94-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="b0e94-117">See also</span></span>

- [<span data-ttu-id="b0e94-118">ICorProfilerFunctionEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b0e94-118">ICorProfilerFunctionEnum Interface</span></span>](icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="b0e94-119">ICorProfilerInfo3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b0e94-119">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="b0e94-120">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="b0e94-120">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="b0e94-121">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="b0e94-121">Profiling</span></span>](index.md)
