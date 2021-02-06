---
description: 'Más información acerca de: ICorProfilerInfo:: GetFunctionFromToken ((método)'
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
ms.openlocfilehash: 58dea413539d6e3a625f515aa7e8d5123152c90a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99647458"
---
# <a name="icorprofilerinfogetfunctionfromtoken-method"></a><span data-ttu-id="a3841-103">ICorProfilerInfo::GetFunctionFromToken (Método)</span><span class="sxs-lookup"><span data-stu-id="a3841-103">ICorProfilerInfo::GetFunctionFromToken Method</span></span>

<span data-ttu-id="a3841-104">Obtiene el identificador de una función.</span><span class="sxs-lookup"><span data-stu-id="a3841-104">Gets the ID of a function.</span></span> <span data-ttu-id="a3841-105">Este método está obsoleto en la .NET Framework versión 2,0.</span><span class="sxs-lookup"><span data-stu-id="a3841-105">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="a3841-106">Use en su lugar el método [ICorProfilerInfo2:: GetFunctionFromTokenAndTypeArgs (](icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md) .</span><span class="sxs-lookup"><span data-stu-id="a3841-106">Use the [ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs](icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3841-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a3841-107">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionFromToken(  
    [in]  ModuleID   moduleId,  
    [in]  mdToken    token,  
    [out] FunctionID *pFunctionId);  
```  
  
## <a name="remarks"></a><span data-ttu-id="a3841-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a3841-108">Remarks</span></span>  

 <span data-ttu-id="a3841-109">El `GetFunctionFromToken` método no funcionará para funciones o funciones genéricas en tipos genéricos; ahora está obsoleto.</span><span class="sxs-lookup"><span data-stu-id="a3841-109">The `GetFunctionFromToken` method will not work for generic functions or functions in generic types; it is now obsolete.</span></span> <span data-ttu-id="a3841-110">Se usa `ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs` para todas las funciones.</span><span class="sxs-lookup"><span data-stu-id="a3841-110">Use `ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs` for all functions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3841-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a3841-111">Requirements</span></span>  

 <span data-ttu-id="a3841-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a3841-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3841-113">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a3841-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a3841-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a3841-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a3841-115">**.NET Framework versiones:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="a3841-115">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3841-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="a3841-116">See also</span></span>

- [<span data-ttu-id="a3841-117">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a3841-117">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
