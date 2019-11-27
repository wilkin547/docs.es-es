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
ms.openlocfilehash: 72531dc4fa7a8afc3bd719d73389fac94e3363bb
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74439140"
---
# <a name="icorprofilerinfogetfunctionfromtoken-method"></a><span data-ttu-id="c34a2-102">ICorProfilerInfo::GetFunctionFromToken (Método)</span><span class="sxs-lookup"><span data-stu-id="c34a2-102">ICorProfilerInfo::GetFunctionFromToken Method</span></span>
<span data-ttu-id="c34a2-103">Obtiene el identificador de una función.</span><span class="sxs-lookup"><span data-stu-id="c34a2-103">Gets the ID of a function.</span></span> <span data-ttu-id="c34a2-104">Este método está obsoleto en la .NET Framework versión 2,0.</span><span class="sxs-lookup"><span data-stu-id="c34a2-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="c34a2-105">Use en su lugar el método [ICorProfilerInfo2:: GetFunctionFromTokenAndTypeArgs (](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md) .</span><span class="sxs-lookup"><span data-stu-id="c34a2-105">Use the [ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c34a2-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c34a2-106">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionFromToken(  
    [in]  ModuleID   moduleId,  
    [in]  mdToken    token,  
    [out] FunctionID *pFunctionId);  
```  
  
## <a name="remarks"></a><span data-ttu-id="c34a2-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c34a2-107">Remarks</span></span>  
 <span data-ttu-id="c34a2-108">El método `GetFunctionFromToken` no funcionará con funciones o funciones genéricas en tipos genéricos. ahora está obsoleto.</span><span class="sxs-lookup"><span data-stu-id="c34a2-108">The `GetFunctionFromToken` method will not work for generic functions or functions in generic types; it is now obsolete.</span></span> <span data-ttu-id="c34a2-109">Use `ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs` para todas las funciones.</span><span class="sxs-lookup"><span data-stu-id="c34a2-109">Use `ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs` for all functions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c34a2-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c34a2-110">Requirements</span></span>  
 <span data-ttu-id="c34a2-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c34a2-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c34a2-112">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c34a2-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c34a2-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c34a2-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c34a2-114">**.NET Framework versiones:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="c34a2-114">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c34a2-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="c34a2-115">See also</span></span>

- [<span data-ttu-id="c34a2-116">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c34a2-116">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
