---
title: "ICorProfilerInfo::SetILFunctionBody (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerInfo.SetILFunctionBody
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetILFunctionBody
helpviewer_keywords:
- ICorProfilerInfo::SetILFunctionBody method [.NET Framework profiling]
- SetILFunctionBody method [.NET Framework profiling]
ms.assetid: b159c712-00f4-4fc7-a990-40bf9f642e8f
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c44fa89ba66a306792f1ffed162447a6305a0347
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfosetilfunctionbody-method"></a><span data-ttu-id="5c3ab-102">ICorProfilerInfo::SetILFunctionBody (Método)</span><span class="sxs-lookup"><span data-stu-id="5c3ab-102">ICorProfilerInfo::SetILFunctionBody Method</span></span>
<span data-ttu-id="5c3ab-103">Reemplaza el cuerpo de la función especificada en el módulo especificado.</span><span class="sxs-lookup"><span data-stu-id="5c3ab-103">Replaces the body of the specified function in the specified module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c3ab-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5c3ab-104">Syntax</span></span>  
  
```  
HRESULT SetILFunctionBody(  
    [in] ModuleID    moduleId,  
    [in] mdMethodDef methodid,  
    [in] LPCBYTE     pbNewILMethodHeader);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5c3ab-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5c3ab-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="5c3ab-106">[in] El identificador del módulo en el que reside la función.</span><span class="sxs-lookup"><span data-stu-id="5c3ab-106">[in] The ID of the module in which the function resides.</span></span>  
  
 `methodid`  
 <span data-ttu-id="5c3ab-107">[in] El token de la función para la que se va a reemplazar el cuerpo.</span><span class="sxs-lookup"><span data-stu-id="5c3ab-107">[in] The token of the function for which to replace the body.</span></span>  
  
 `pbNewILMethodHeader`  
 <span data-ttu-id="5c3ab-108">[in] El nuevo encabezado de la función.</span><span class="sxs-lookup"><span data-stu-id="5c3ab-108">[in] The new header for the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5c3ab-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5c3ab-109">Remarks</span></span>  
 <span data-ttu-id="5c3ab-110">El `SetILFunctionBody` método reemplaza la dirección virtual relativa de la función en los metadatos para que apunte al nuevo cuerpo de función y ajusta las estructuras de datos internas según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="5c3ab-110">The `SetILFunctionBody` method replaces the relative virtual address of the function in the metadata so that it points to the new function body, and adjusts any internal data structures as required.</span></span>  
  
 <span data-ttu-id="5c3ab-111">El `SetILFunctionBody` método puede llamarse en sólo aquellas funciones que nunca se han compilado mediante un compilador just-in-time (JIT).</span><span class="sxs-lookup"><span data-stu-id="5c3ab-111">The `SetILFunctionBody` method can be called on only those functions that have never been compiled by a just-in-time (JIT) compiler.</span></span>  
  
 <span data-ttu-id="5c3ab-112">Use la [ICorProfilerInfo:: GetILFunctionBodyAllocator](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getilfunctionbodyallocator-method.md) método para asignar espacio para el nuevo método para asegurarse de que el búfer es compatible.</span><span class="sxs-lookup"><span data-stu-id="5c3ab-112">Use the [ICorProfilerInfo::GetILFunctionBodyAllocator](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getilfunctionbodyallocator-method.md) method to allocate space for the new method to ensure that the buffer is compatible.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c3ab-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5c3ab-113">Requirements</span></span>  
 <span data-ttu-id="5c3ab-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c3ab-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c3ab-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5c3ab-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5c3ab-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5c3ab-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5c3ab-117">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c3ab-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c3ab-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="5c3ab-118">See Also</span></span>  
 [<span data-ttu-id="5c3ab-119">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5c3ab-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
