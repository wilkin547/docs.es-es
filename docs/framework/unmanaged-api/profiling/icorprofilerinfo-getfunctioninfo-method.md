---
title: ICorProfilerInfo::GetFunctionInfo (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetFunctionInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetFunctionInfo
helpviewer_keywords:
- ICorProfilerInfo::GetFunctionInfo method [.NET Framework profiling]
- GetFunctionInfo method [.NET Framework profiling]
ms.assetid: c42b5891-019d-46b3-b551-4606295b75b8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 19736d177639b00c9563462f10e33e4c122297c6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33456018"
---
# <a name="icorprofilerinfogetfunctioninfo-method"></a><span data-ttu-id="d3c48-102">ICorProfilerInfo::GetFunctionInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="d3c48-102">ICorProfilerInfo::GetFunctionInfo Method</span></span>
<span data-ttu-id="d3c48-103">Obtiene la clase primaria y los metadatos (token) para la función especificada.</span><span class="sxs-lookup"><span data-stu-id="d3c48-103">Gets the parent class and metadata token for the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3c48-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d3c48-104">Syntax</span></span>  
  
```  
HRESULT GetFunctionInfo(  
    [in]  FunctionID functionId,  
    [out] ClassID    *pClassId,  
    [out] ModuleID   *pModuleId,  
    [out] mdToken    *pToken);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d3c48-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d3c48-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="d3c48-106">[in] El identificador de la función para la que se va a obtener el token de la clase primaria y los metadatos.</span><span class="sxs-lookup"><span data-stu-id="d3c48-106">[in] The ID of the function for which to get the parent class and metadata token.</span></span>  
  
 `pClassId`  
 <span data-ttu-id="d3c48-107">[out] Puntero a la clase primaria de la función.</span><span class="sxs-lookup"><span data-stu-id="d3c48-107">[out] A pointer to the parent class of the function.</span></span>  
  
 `pModuleId`  
 <span data-ttu-id="d3c48-108">[out] Puntero al módulo en el que se define la clase primaria de la función.</span><span class="sxs-lookup"><span data-stu-id="d3c48-108">[out] A pointer to the module in which the function's parent class is defined.</span></span>  
  
 `pToken`  
 <span data-ttu-id="d3c48-109">[out] Puntero al token de metadatos para la función.</span><span class="sxs-lookup"><span data-stu-id="d3c48-109">[out] A pointer to the metadata token for the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d3c48-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d3c48-110">Remarks</span></span>  
 <span data-ttu-id="d3c48-111">El código del generador de perfiles puede llamar a [ICorProfilerInfo:: GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) para obtener una interfaz de metadatos para un módulo determinado.</span><span class="sxs-lookup"><span data-stu-id="d3c48-111">The profiler code can call [ICorProfilerInfo::GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) to obtain a metadata interface for a given module.</span></span> <span data-ttu-id="d3c48-112">Después, el token de metadatos que se devuelve a la ubicación a la que `pToken` hace referencia puede usarse para acceder a los metadatos de la función.</span><span class="sxs-lookup"><span data-stu-id="d3c48-112">The metadata token that is returned to the location referenced by `pToken` can then be used to access the metadata for the function.</span></span>  
  
 <span data-ttu-id="d3c48-113">El `ClassID` de una función en una clase genérica no estén puede obtenerse sin más información contextual sobre el uso de la función.</span><span class="sxs-lookup"><span data-stu-id="d3c48-113">The `ClassID` of a function on a generic class might not be obtainable without more contextual information about the use of the function.</span></span> <span data-ttu-id="d3c48-114">En este caso, `pClassId` será 0.</span><span class="sxs-lookup"><span data-stu-id="d3c48-114">In this case, `pClassId` will be 0.</span></span> <span data-ttu-id="d3c48-115">Código del generador de perfiles debe usar [ICorProfilerInfo2:: Getfunctioninfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) con un valor COR_PRF_FRAME_INFO para proporcionar un contexto más.</span><span class="sxs-lookup"><span data-stu-id="d3c48-115">Profiler code should use [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) with a COR_PRF_FRAME_INFO value to provide more context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3c48-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d3c48-116">Requirements</span></span>  
 <span data-ttu-id="d3c48-117">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d3c48-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3c48-118">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d3c48-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d3c48-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d3c48-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d3c48-120">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3c48-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3c48-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="d3c48-121">See Also</span></span>  
 [<span data-ttu-id="d3c48-122">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d3c48-122">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
