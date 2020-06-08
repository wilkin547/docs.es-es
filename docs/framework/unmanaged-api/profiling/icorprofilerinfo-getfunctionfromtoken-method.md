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
ms.openlocfilehash: 18c3b6e840ec1f6cb1481c8d752e6399dcdae077
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84498146"
---
# <a name="icorprofilerinfogetfunctionfromtoken-method"></a><span data-ttu-id="7b989-102">ICorProfilerInfo::GetFunctionFromToken (Método)</span><span class="sxs-lookup"><span data-stu-id="7b989-102">ICorProfilerInfo::GetFunctionFromToken Method</span></span>
<span data-ttu-id="7b989-103">Obtiene el identificador de una función.</span><span class="sxs-lookup"><span data-stu-id="7b989-103">Gets the ID of a function.</span></span> <span data-ttu-id="7b989-104">Este método está obsoleto en la .NET Framework versión 2,0.</span><span class="sxs-lookup"><span data-stu-id="7b989-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="7b989-105">Use en su lugar el método [ICorProfilerInfo2:: GetFunctionFromTokenAndTypeArgs (](icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md) .</span><span class="sxs-lookup"><span data-stu-id="7b989-105">Use the [ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs](icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b989-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7b989-106">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionFromToken(  
    [in]  ModuleID   moduleId,  
    [in]  mdToken    token,  
    [out] FunctionID *pFunctionId);  
```  
  
## <a name="remarks"></a><span data-ttu-id="7b989-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7b989-107">Remarks</span></span>  
 <span data-ttu-id="7b989-108">El `GetFunctionFromToken` método no funcionará para funciones o funciones genéricas en tipos genéricos; ahora está obsoleto.</span><span class="sxs-lookup"><span data-stu-id="7b989-108">The `GetFunctionFromToken` method will not work for generic functions or functions in generic types; it is now obsolete.</span></span> <span data-ttu-id="7b989-109">Se usa `ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs` para todas las funciones.</span><span class="sxs-lookup"><span data-stu-id="7b989-109">Use `ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs` for all functions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b989-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7b989-110">Requirements</span></span>  
 <span data-ttu-id="7b989-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b989-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b989-112">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7b989-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7b989-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7b989-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7b989-114">**.NET Framework versiones:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="7b989-114">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b989-115">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="7b989-115">See also</span></span>

- [<span data-ttu-id="7b989-116">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7b989-116">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
