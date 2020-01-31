---
title: ICorProfilerInfo::GetClassFromToken (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetClassFromToken
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetClassFromToken
helpviewer_keywords:
- ICorProfilerInfo::GetClassFromToken method [.NET Framework profiling]
- GetClassFromToken method, ICorProfilerInfo interface [.NET Framework profiling]
ms.assetid: 0afc1197-2a5b-424f-8b82-9cb59a7e00db
topic_type:
- apiref
ms.openlocfilehash: 841953625235406f013e9f140ad91c7b65680e47
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863958"
---
# <a name="icorprofilerinfogetclassfromtoken-method"></a><span data-ttu-id="5434f-102">ICorProfilerInfo::GetClassFromToken (Método)</span><span class="sxs-lookup"><span data-stu-id="5434f-102">ICorProfilerInfo::GetClassFromToken Method</span></span>
<span data-ttu-id="5434f-103">Obtiene el identificador de la clase, dado el token de metadatos.</span><span class="sxs-lookup"><span data-stu-id="5434f-103">Gets the ID of the class, given the metadata token.</span></span> <span data-ttu-id="5434f-104">Este método está obsoleto en la .NET Framework versión 2,0.</span><span class="sxs-lookup"><span data-stu-id="5434f-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="5434f-105">Use [ICorProfilerInfo2:: GetClassFromTokenAndTypeArgs (](icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="5434f-105">Use [ICorProfilerInfo2::GetClassFromTokenAndTypeArgs](icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5434f-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5434f-106">Syntax</span></span>  
  
```cpp  
HRESULT GetClassFromToken(  
    [in]  ModuleID  moduleId,  
    [in]  mdTypeDef typeDef,  
    [out] ClassID   *pClassId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5434f-107">Parameters</span><span class="sxs-lookup"><span data-stu-id="5434f-107">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="5434f-108">de IDENTIFICADOR del módulo que contiene la clase.</span><span class="sxs-lookup"><span data-stu-id="5434f-108">[in] The ID of the module that contains the class.</span></span>  
  
 `typeDef`  
 <span data-ttu-id="5434f-109">de Un token de metadatos de `mdTypeDef` que hace referencia a la clase.</span><span class="sxs-lookup"><span data-stu-id="5434f-109">[in] An `mdTypeDef` metadata token that references the class.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="5434f-110">enuncia Puntero al identificador de clase.</span><span class="sxs-lookup"><span data-stu-id="5434f-110">[out] A pointer to the class ID.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5434f-111">Notas</span><span class="sxs-lookup"><span data-stu-id="5434f-111">Remarks</span></span>  
 <span data-ttu-id="5434f-112">Este método está obsoleto; en su lugar, use `ICorProfilerInfo2::GetClassFromTokenAndTypeArgs` para todos los tipos.</span><span class="sxs-lookup"><span data-stu-id="5434f-112">This method is obsolete; instead, use `ICorProfilerInfo2::GetClassFromTokenAndTypeArgs` for all types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5434f-113">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="5434f-113">Requirements</span></span>  
 <span data-ttu-id="5434f-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5434f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5434f-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5434f-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5434f-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5434f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5434f-117">**.NET Framework versiones:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="5434f-117">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5434f-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="5434f-118">See also</span></span>

- [<span data-ttu-id="5434f-119">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5434f-119">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
