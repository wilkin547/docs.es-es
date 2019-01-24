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
ms.openlocfilehash: 12524de994264d83abf5b5338654e89a0964adff
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54667705"
---
# <a name="icorprofilerinfogetclassfromtoken-method"></a><span data-ttu-id="bf9f2-102">ICorProfilerInfo::GetClassFromToken (Método)</span><span class="sxs-lookup"><span data-stu-id="bf9f2-102">ICorProfilerInfo::GetClassFromToken Method</span></span>
<span data-ttu-id="bf9f2-103">Obtiene el identificador de la clase, dado el token de metadatos.</span><span class="sxs-lookup"><span data-stu-id="bf9f2-103">Gets the ID of the class, given the metadata token.</span></span> <span data-ttu-id="bf9f2-104">Este método está obsoleto en .NET Framework versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="bf9f2-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="bf9f2-105">Use [ICorProfilerInfo2:: GetClassFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="bf9f2-105">Use [ICorProfilerInfo2::GetClassFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf9f2-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bf9f2-106">Syntax</span></span>  
  
```  
HRESULT GetClassFromToken(  
    [in]  ModuleID  moduleId,  
    [in]  mdTypeDef typeDef,  
    [out] ClassID   *pClassId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bf9f2-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bf9f2-107">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="bf9f2-108">[in] El identificador del módulo que contiene la clase.</span><span class="sxs-lookup"><span data-stu-id="bf9f2-108">[in] The ID of the module that contains the class.</span></span>  
  
 `typeDef`  
 <span data-ttu-id="bf9f2-109">[in] Un `mdTypeDef` token de metadatos que hace referencia a la clase.</span><span class="sxs-lookup"><span data-stu-id="bf9f2-109">[in] An `mdTypeDef` metadata token that references the class.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="bf9f2-110">[out] Un puntero al identificador de clase.</span><span class="sxs-lookup"><span data-stu-id="bf9f2-110">[out] A pointer to the class ID.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bf9f2-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bf9f2-111">Remarks</span></span>  
 <span data-ttu-id="bf9f2-112">Este método está obsoleto; en su lugar, use `ICorProfilerInfo2::GetClassFromTokenAndTypeArgs` para todos los tipos.</span><span class="sxs-lookup"><span data-stu-id="bf9f2-112">This method is obsolete; instead, use `ICorProfilerInfo2::GetClassFromTokenAndTypeArgs` for all types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf9f2-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bf9f2-113">Requirements</span></span>  
 <span data-ttu-id="bf9f2-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf9f2-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf9f2-115">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bf9f2-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bf9f2-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bf9f2-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bf9f2-117">**Versiones de .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="bf9f2-117">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf9f2-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="bf9f2-118">See also</span></span>
- [<span data-ttu-id="bf9f2-119">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="bf9f2-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
