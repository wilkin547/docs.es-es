---
title: "ICorProfilerInfo::GetFunctionFromToken (Método)"
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
- ICorProfilerInfo.GetFunctionFromToken
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetFunctionFromToken
helpviewer_keywords:
- ICorProfilerInfo::GetFunctionFromToken method [.NET Framework profiling]
- GetFunctionFromToken method, ICorProfilerInfo interface [.NET Framework profiling]
ms.assetid: 0eed759f-cce8-405d-88dc-9ee293a38928
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0c90a63f075c392ca3ff02a47190f9c4dfe6aad5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfogetfunctionfromtoken-method"></a><span data-ttu-id="190aa-102">ICorProfilerInfo::GetFunctionFromToken (Método)</span><span class="sxs-lookup"><span data-stu-id="190aa-102">ICorProfilerInfo::GetFunctionFromToken Method</span></span>
<span data-ttu-id="190aa-103">Obtiene el identificador de una función.</span><span class="sxs-lookup"><span data-stu-id="190aa-103">Gets the ID of a function.</span></span> <span data-ttu-id="190aa-104">Este método está obsoleto en la versión 2.0 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="190aa-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="190aa-105">Use la [ICorProfilerInfo2:: GetFunctionFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md) método en su lugar.</span><span class="sxs-lookup"><span data-stu-id="190aa-105">Use the [ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="190aa-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="190aa-106">Syntax</span></span>  
  
```  
HRESULT GetFunctionFromToken(  
    [in]  ModuleID   moduleId,  
    [in]  mdToken    token,  
    [out] FunctionID *pFunctionId);  
```  
  
## <a name="remarks"></a><span data-ttu-id="190aa-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="190aa-107">Remarks</span></span>  
 <span data-ttu-id="190aa-108">El `GetFunctionFromToken` método no funcionará para las funciones genéricas o las funciones de tipos genéricos; ahora está obsoleta.</span><span class="sxs-lookup"><span data-stu-id="190aa-108">The `GetFunctionFromToken` method will not work for generic functions or functions in generic types; it is now obsolete.</span></span> <span data-ttu-id="190aa-109">Use `ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs` para todas las funciones.</span><span class="sxs-lookup"><span data-stu-id="190aa-109">Use `ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs` for all functions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="190aa-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="190aa-110">Requirements</span></span>  
 <span data-ttu-id="190aa-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="190aa-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="190aa-112">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="190aa-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="190aa-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="190aa-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="190aa-114">**Versiones de .NET framework:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="190aa-114">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="190aa-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="190aa-115">See Also</span></span>  
 [<span data-ttu-id="190aa-116">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="190aa-116">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
