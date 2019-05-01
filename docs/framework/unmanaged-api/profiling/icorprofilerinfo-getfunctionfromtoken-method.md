---
title: ICorProfilerInfo::GetFunctionFromToken (Método)
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5f4fb2292154a2660a2db3f0b3962fcf2114e385
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049614"
---
# <a name="icorprofilerinfogetfunctionfromtoken-method"></a><span data-ttu-id="23693-102">ICorProfilerInfo::GetFunctionFromToken (Método)</span><span class="sxs-lookup"><span data-stu-id="23693-102">ICorProfilerInfo::GetFunctionFromToken Method</span></span>
<span data-ttu-id="23693-103">Obtiene el identificador de una función.</span><span class="sxs-lookup"><span data-stu-id="23693-103">Gets the ID of a function.</span></span> <span data-ttu-id="23693-104">Este método está obsoleto en .NET Framework versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="23693-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="23693-105">Use la [ICorProfilerInfo2:: GetFunctionFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md) método en su lugar.</span><span class="sxs-lookup"><span data-stu-id="23693-105">Use the [ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23693-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="23693-106">Syntax</span></span>  
  
```  
HRESULT GetFunctionFromToken(  
    [in]  ModuleID   moduleId,  
    [in]  mdToken    token,  
    [out] FunctionID *pFunctionId);  
```  
  
## <a name="remarks"></a><span data-ttu-id="23693-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="23693-107">Remarks</span></span>  
 <span data-ttu-id="23693-108">El `GetFunctionFromToken` método no funcionará para funciones en tipos genéricos o funciones genéricas; ahora está obsoleto.</span><span class="sxs-lookup"><span data-stu-id="23693-108">The `GetFunctionFromToken` method will not work for generic functions or functions in generic types; it is now obsolete.</span></span> <span data-ttu-id="23693-109">Use `ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs` para todas las funciones.</span><span class="sxs-lookup"><span data-stu-id="23693-109">Use `ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs` for all functions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23693-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="23693-110">Requirements</span></span>  
 <span data-ttu-id="23693-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="23693-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23693-112">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="23693-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="23693-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="23693-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="23693-114">**Versiones de .NET framework:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="23693-114">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23693-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="23693-115">See also</span></span>

- [<span data-ttu-id="23693-116">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="23693-116">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
