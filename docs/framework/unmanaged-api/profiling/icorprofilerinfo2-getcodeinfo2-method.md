---
title: "ICorProfilerInfo2::GetCodeInfo2 (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetCodeInfo2
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetCodeInfo2
helpviewer_keywords:
- ICorProfilerInfo2::GetCodeInfo2 method [.NET Framework profiling]
- GetCodeInfo2 method [.NET Framework profiling]
ms.assetid: 532da6ee-7f0a-401b-a61e-fc47ec235d2e
topic_type: apiref
caps.latest.revision: "17"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 6c2526c286e4014b32e63ec34f9d212a5f657756
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo2getcodeinfo2-method"></a><span data-ttu-id="58042-102">ICorProfilerInfo2::GetCodeInfo2 (Método)</span><span class="sxs-lookup"><span data-stu-id="58042-102">ICorProfilerInfo2::GetCodeInfo2 Method</span></span>
<span data-ttu-id="58042-103">Obtiene las extensiones del código nativo asociado al `FunctionID` especificado.</span><span class="sxs-lookup"><span data-stu-id="58042-103">Gets the extents of native code associated with the specified `FunctionID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58042-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="58042-104">Syntax</span></span>  
  
```  
HRESULT GetCodeInfo2(  
    [in]  FunctionID functionID,  
    [in]  ULONG32 cCodeInfos,  
    [out] ULONG32 *pcCodeInfos,  
    [out, size_is(cCodeInfos), length_is(*pcCodeInfos)]  
    COR_PRF_CODE_INFO codeInfos[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="58042-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="58042-105">Parameters</span></span>  
 `functionID`  
 <span data-ttu-id="58042-106">[in] Identificador de función con la que está asociado el código nativo.</span><span class="sxs-lookup"><span data-stu-id="58042-106">[in] The ID of the function with which the native code is associated.</span></span>  
  
 `cCodeInfos`  
 <span data-ttu-id="58042-107">[in] Tamaño de la matriz `codeInfos`.</span><span class="sxs-lookup"><span data-stu-id="58042-107">[in] The size of the `codeInfos` array.</span></span>  
  
 `pcCodeInfos`  
 <span data-ttu-id="58042-108">[out] Un puntero al número total de [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) estructuras disponibles.</span><span class="sxs-lookup"><span data-stu-id="58042-108">[out] A pointer to the total number of [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structures available.</span></span>  
  
 `codeInfos`  
 <span data-ttu-id="58042-109">[out] Búfer proporcionado por el llamador.</span><span class="sxs-lookup"><span data-stu-id="58042-109">[out] A caller-provided buffer.</span></span> <span data-ttu-id="58042-110">Después de que el método vuelva, contiene una matriz de estructuras `COR_PRF_CODE_INFO`, cada una de las cuales describe un bloque de código nativo.</span><span class="sxs-lookup"><span data-stu-id="58042-110">After the method returns, it contains an array of `COR_PRF_CODE_INFO` structures, each of which describes a block of native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="58042-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="58042-111">Remarks</span></span>  
 <span data-ttu-id="58042-112">Las extensiones se clasifican por orden de desplazamiento creciente del lenguaje intermedio de Microsoft (MSIL).</span><span class="sxs-lookup"><span data-stu-id="58042-112">The extents are sorted in order of increasing Microsoft intermediate language (MSIL) offset.</span></span>  
  
 <span data-ttu-id="58042-113">Después de la devolución de `GetCodeInfo2`, debe comprobar que el búfer `codeInfos` era lo suficientemente grande como para contener todas las estructuras `COR_PRF_CODE_INFO`.</span><span class="sxs-lookup"><span data-stu-id="58042-113">After `GetCodeInfo2` returns, you must verify that the `codeInfos` buffer was large enough to contain all the `COR_PRF_CODE_INFO` structures.</span></span> <span data-ttu-id="58042-114">Para ello, compare el valor de `cCodeInfos` con el valor del parámetro `cchName`.</span><span class="sxs-lookup"><span data-stu-id="58042-114">To do this, compare the value of `cCodeInfos` with the value of the `cchName` parameter.</span></span> <span data-ttu-id="58042-115">Si `cCodeInfos` dividido entre el tamaño de una estructura `COR_PRF_CODE_INFO` es menor que `pcCodeInfos`, asigne un búfer `codeInfos` mayor, actualice `cCodeInfos` con el nuevo tamaño de mayores dimensiones y vuelva a llamar a `GetCodeInfo2`.</span><span class="sxs-lookup"><span data-stu-id="58042-115">If `cCodeInfos` divided by the size of a `COR_PRF_CODE_INFO` structure is smaller than `pcCodeInfos`, allocate a larger `codeInfos` buffer, update `cCodeInfos` with the new, larger size, and call `GetCodeInfo2` again.</span></span>  
  
 <span data-ttu-id="58042-116">También tiene la opción de llamar primero a `GetCodeInfo2` con un búfer `codeInfos` de longitud de cero para obtener el tamaño de búfer correcto.</span><span class="sxs-lookup"><span data-stu-id="58042-116">Alternatively, you can first call `GetCodeInfo2` with a zero-length `codeInfos` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="58042-117">A continuación, puede establecer el tamaño del búfer `codeInfos` para el valor devuelto en `pcCodeInfos` multiplicándolo por el tamaño de una estructura `COR_PRF_CODE_INFO` y volver a llamar a `GetCodeInfo2`.</span><span class="sxs-lookup"><span data-stu-id="58042-117">You can then set the `codeInfos` buffer size to the value returned in `pcCodeInfos`, multiplied by the size of a `COR_PRF_CODE_INFO` structure, and call `GetCodeInfo2` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58042-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="58042-118">Requirements</span></span>  
 <span data-ttu-id="58042-119">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="58042-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58042-120">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="58042-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="58042-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="58042-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="58042-122">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58042-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58042-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="58042-123">See Also</span></span>  
 [<span data-ttu-id="58042-124">Getcodeinfo3 (método)</span><span class="sxs-lookup"><span data-stu-id="58042-124">GetCodeInfo3 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getcodeinfo3-method.md)  
 [<span data-ttu-id="58042-125">ICorProfilerInfo2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="58042-125">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)  
 [<span data-ttu-id="58042-126">Interfaces de generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="58042-126">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="58042-127">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="58042-127">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
