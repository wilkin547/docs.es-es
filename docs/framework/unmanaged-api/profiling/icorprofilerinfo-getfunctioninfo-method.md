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
ms.openlocfilehash: 00b20134c0134aa30d2056b634c8525f66ed8cf5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54602461"
---
# <a name="icorprofilerinfogetfunctioninfo-method"></a><span data-ttu-id="3c4b8-102">ICorProfilerInfo::GetFunctionInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="3c4b8-102">ICorProfilerInfo::GetFunctionInfo Method</span></span>
<span data-ttu-id="3c4b8-103">Obtiene la clase primaria y los metadatos de token para la función especificada.</span><span class="sxs-lookup"><span data-stu-id="3c4b8-103">Gets the parent class and metadata token for the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c4b8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3c4b8-104">Syntax</span></span>  
  
```  
HRESULT GetFunctionInfo(  
    [in]  FunctionID functionId,  
    [out] ClassID    *pClassId,  
    [out] ModuleID   *pModuleId,  
    [out] mdToken    *pToken);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3c4b8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3c4b8-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="3c4b8-106">[in] El identificador de la función que se va a obtener el token de la clase primaria y los metadatos.</span><span class="sxs-lookup"><span data-stu-id="3c4b8-106">[in] The ID of the function for which to get the parent class and metadata token.</span></span>  
  
 `pClassId`  
 <span data-ttu-id="3c4b8-107">[out] Puntero a la clase primaria de la función.</span><span class="sxs-lookup"><span data-stu-id="3c4b8-107">[out] A pointer to the parent class of the function.</span></span>  
  
 `pModuleId`  
 <span data-ttu-id="3c4b8-108">[out] Puntero al módulo en el que se define la clase primaria de la función.</span><span class="sxs-lookup"><span data-stu-id="3c4b8-108">[out] A pointer to the module in which the function's parent class is defined.</span></span>  
  
 `pToken`  
 <span data-ttu-id="3c4b8-109">[out] Puntero al token de metadatos para la función.</span><span class="sxs-lookup"><span data-stu-id="3c4b8-109">[out] A pointer to the metadata token for the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3c4b8-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3c4b8-110">Remarks</span></span>  
 <span data-ttu-id="3c4b8-111">El código del generador de perfiles puede llamar a [GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) para obtener una interfaz de metadatos para un módulo determinado.</span><span class="sxs-lookup"><span data-stu-id="3c4b8-111">The profiler code can call [ICorProfilerInfo::GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) to obtain a metadata interface for a given module.</span></span> <span data-ttu-id="3c4b8-112">Después, el token de metadatos que se devuelve a la ubicación a la que `pToken` hace referencia puede usarse para acceder a los metadatos de la función.</span><span class="sxs-lookup"><span data-stu-id="3c4b8-112">The metadata token that is returned to the location referenced by `pToken` can then be used to access the metadata for the function.</span></span>  
  
 <span data-ttu-id="3c4b8-113">El `ClassID` de una función en una clase genérica es posible que no pueda obtenerse sin más información contextual sobre el uso de la función.</span><span class="sxs-lookup"><span data-stu-id="3c4b8-113">The `ClassID` of a function on a generic class might not be obtainable without more contextual information about the use of the function.</span></span> <span data-ttu-id="3c4b8-114">En este caso, `pClassId` será 0.</span><span class="sxs-lookup"><span data-stu-id="3c4b8-114">In this case, `pClassId` will be 0.</span></span> <span data-ttu-id="3c4b8-115">Debe usar código Profiler [ICorProfilerInfo2:: Getfunctioninfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) con un valor COR_PRF_FRAME_INFO para proporcionar más contexto.</span><span class="sxs-lookup"><span data-stu-id="3c4b8-115">Profiler code should use [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) with a COR_PRF_FRAME_INFO value to provide more context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c4b8-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3c4b8-116">Requirements</span></span>  
 <span data-ttu-id="3c4b8-117">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c4b8-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c4b8-118">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3c4b8-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3c4b8-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3c4b8-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3c4b8-120">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c4b8-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c4b8-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="3c4b8-121">See also</span></span>
- [<span data-ttu-id="3c4b8-122">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3c4b8-122">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
