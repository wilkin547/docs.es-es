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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 580c554c968819ba4ef2ba52edeb5e754d33ac1b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61991905"
---
# <a name="icorprofilerinfogetclassfromtoken-method"></a><span data-ttu-id="feeaf-102">ICorProfilerInfo::GetClassFromToken (Método)</span><span class="sxs-lookup"><span data-stu-id="feeaf-102">ICorProfilerInfo::GetClassFromToken Method</span></span>
<span data-ttu-id="feeaf-103">Obtiene el identificador de la clase, dado el token de metadatos.</span><span class="sxs-lookup"><span data-stu-id="feeaf-103">Gets the ID of the class, given the metadata token.</span></span> <span data-ttu-id="feeaf-104">Este método está obsoleto en .NET Framework versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="feeaf-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="feeaf-105">Use [ICorProfilerInfo2:: GetClassFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="feeaf-105">Use [ICorProfilerInfo2::GetClassFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="feeaf-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="feeaf-106">Syntax</span></span>  
  
```  
HRESULT GetClassFromToken(  
    [in]  ModuleID  moduleId,  
    [in]  mdTypeDef typeDef,  
    [out] ClassID   *pClassId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="feeaf-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="feeaf-107">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="feeaf-108">[in] El identificador del módulo que contiene la clase.</span><span class="sxs-lookup"><span data-stu-id="feeaf-108">[in] The ID of the module that contains the class.</span></span>  
  
 `typeDef`  
 <span data-ttu-id="feeaf-109">[in] Un `mdTypeDef` token de metadatos que hace referencia a la clase.</span><span class="sxs-lookup"><span data-stu-id="feeaf-109">[in] An `mdTypeDef` metadata token that references the class.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="feeaf-110">[out] Un puntero al identificador de clase.</span><span class="sxs-lookup"><span data-stu-id="feeaf-110">[out] A pointer to the class ID.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="feeaf-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="feeaf-111">Remarks</span></span>  
 <span data-ttu-id="feeaf-112">Este método está obsoleto; en su lugar, use `ICorProfilerInfo2::GetClassFromTokenAndTypeArgs` para todos los tipos.</span><span class="sxs-lookup"><span data-stu-id="feeaf-112">This method is obsolete; instead, use `ICorProfilerInfo2::GetClassFromTokenAndTypeArgs` for all types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="feeaf-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="feeaf-113">Requirements</span></span>  
 <span data-ttu-id="feeaf-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="feeaf-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="feeaf-115">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="feeaf-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="feeaf-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="feeaf-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="feeaf-117">**Versiones de .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="feeaf-117">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="feeaf-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="feeaf-118">See also</span></span>

- [<span data-ttu-id="feeaf-119">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="feeaf-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
