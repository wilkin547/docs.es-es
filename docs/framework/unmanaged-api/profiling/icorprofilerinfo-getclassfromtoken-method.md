---
title: "ICorProfilerInfo::GetClassFromToken (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.GetClassFromToken
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::GetClassFromToken
helpviewer_keywords:
- ICorProfilerInfo::GetClassFromToken method [.NET Framework profiling]
- GetClassFromToken method, ICorProfilerInfo interface [.NET Framework profiling]
ms.assetid: 0afc1197-2a5b-424f-8b82-9cb59a7e00db
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 761c537f0b3aba529a8a3a862a1a975ddd1c6303
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfogetclassfromtoken-method"></a><span data-ttu-id="976f3-102">ICorProfilerInfo::GetClassFromToken (Método)</span><span class="sxs-lookup"><span data-stu-id="976f3-102">ICorProfilerInfo::GetClassFromToken Method</span></span>
<span data-ttu-id="976f3-103">Obtiene el identificador de la clase, dado el token de metadatos.</span><span class="sxs-lookup"><span data-stu-id="976f3-103">Gets the ID of the class, given the metadata token.</span></span> <span data-ttu-id="976f3-104">Este método está obsoleto en la versión 2.0 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="976f3-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="976f3-105">Use [ICorProfilerInfo2:: GetClassFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="976f3-105">Use [ICorProfilerInfo2::GetClassFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="976f3-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="976f3-106">Syntax</span></span>  
  
```  
HRESULT GetClassFromToken(  
    [in]  ModuleID  moduleId,  
    [in]  mdTypeDef typeDef,  
    [out] ClassID   *pClassId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="976f3-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="976f3-107">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="976f3-108">[in] El identificador del módulo que contiene la clase.</span><span class="sxs-lookup"><span data-stu-id="976f3-108">[in] The ID of the module that contains the class.</span></span>  
  
 `typeDef`  
 <span data-ttu-id="976f3-109">[in] Un `mdTypeDef` símbolo (token) de metadatos que hace referencia a la clase.</span><span class="sxs-lookup"><span data-stu-id="976f3-109">[in] An `mdTypeDef` metadata token that references the class.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="976f3-110">[out] Un puntero al identificador de clase.</span><span class="sxs-lookup"><span data-stu-id="976f3-110">[out] A pointer to the class ID.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="976f3-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="976f3-111">Remarks</span></span>  
 <span data-ttu-id="976f3-112">Este método está obsoleto; en su lugar, use `ICorProfilerInfo2::GetClassFromTokenAndTypeArgs` para todos los tipos.</span><span class="sxs-lookup"><span data-stu-id="976f3-112">This method is obsolete; instead, use `ICorProfilerInfo2::GetClassFromTokenAndTypeArgs` for all types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="976f3-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="976f3-113">Requirements</span></span>  
 <span data-ttu-id="976f3-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="976f3-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="976f3-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="976f3-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="976f3-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="976f3-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="976f3-117">**Versiones de .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="976f3-117">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="976f3-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="976f3-118">See Also</span></span>  
 [<span data-ttu-id="976f3-119">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="976f3-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
