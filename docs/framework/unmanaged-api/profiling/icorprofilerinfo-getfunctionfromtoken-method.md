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
ms.openlocfilehash: 2b2d619c5940376806e9873a528b4f08886593e9
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863561"
---
# <a name="icorprofilerinfogetfunctionfromtoken-method"></a><span data-ttu-id="2d3b5-102">ICorProfilerInfo::GetFunctionFromToken (Método)</span><span class="sxs-lookup"><span data-stu-id="2d3b5-102">ICorProfilerInfo::GetFunctionFromToken Method</span></span>
<span data-ttu-id="2d3b5-103">Obtiene el identificador de una función.</span><span class="sxs-lookup"><span data-stu-id="2d3b5-103">Gets the ID of a function.</span></span> <span data-ttu-id="2d3b5-104">Este método está obsoleto en la .NET Framework versión 2,0.</span><span class="sxs-lookup"><span data-stu-id="2d3b5-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="2d3b5-105">Use en su lugar el método [ICorProfilerInfo2:: GetFunctionFromTokenAndTypeArgs (](icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md) .</span><span class="sxs-lookup"><span data-stu-id="2d3b5-105">Use the [ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs](icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d3b5-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2d3b5-106">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionFromToken(  
    [in]  ModuleID   moduleId,  
    [in]  mdToken    token,  
    [out] FunctionID *pFunctionId);  
```  
  
## <a name="remarks"></a><span data-ttu-id="2d3b5-107">Notas</span><span class="sxs-lookup"><span data-stu-id="2d3b5-107">Remarks</span></span>  
 <span data-ttu-id="2d3b5-108">El método `GetFunctionFromToken` no funcionará con funciones o funciones genéricas en tipos genéricos. ahora está obsoleto.</span><span class="sxs-lookup"><span data-stu-id="2d3b5-108">The `GetFunctionFromToken` method will not work for generic functions or functions in generic types; it is now obsolete.</span></span> <span data-ttu-id="2d3b5-109">Use `ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs` para todas las funciones.</span><span class="sxs-lookup"><span data-stu-id="2d3b5-109">Use `ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs` for all functions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d3b5-110">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="2d3b5-110">Requirements</span></span>  
 <span data-ttu-id="2d3b5-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2d3b5-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d3b5-112">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2d3b5-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2d3b5-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2d3b5-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2d3b5-114">**.NET Framework versiones:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="2d3b5-114">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d3b5-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="2d3b5-115">See also</span></span>

- [<span data-ttu-id="2d3b5-116">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2d3b5-116">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
