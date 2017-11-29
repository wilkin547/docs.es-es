---
title: "ICorProfilerInfo2::EnumModuleFrozenObjects (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.EnumModuleFrozenObjects
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::EnumModuleFrozenObjects
helpviewer_keywords:
- EnumModuleFrozenObjects method [.NET Framework profiling]
- ICorProfilerInfo2::EnumModuleFrozenObjects method [.NET Framework profiling]
ms.assetid: 920b6483-7064-4d64-8613-fcc38ccf9b1e
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 3214468045e98d83e2fb0f9c14c851abb45e217b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo2enummodulefrozenobjects-method"></a><span data-ttu-id="e0bf6-102">ICorProfilerInfo2::EnumModuleFrozenObjects (Método)</span><span class="sxs-lookup"><span data-stu-id="e0bf6-102">ICorProfilerInfo2::EnumModuleFrozenObjects Method</span></span>
<span data-ttu-id="e0bf6-103">Obtiene un enumerador que permite la iteración sobre los objetos inmovilizados en el módulo especificado. Este método está obsoleto.</span><span class="sxs-lookup"><span data-stu-id="e0bf6-103">Gets an enumerator that allows iteration over the frozen objects in the specified module.This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0bf6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e0bf6-104">Syntax</span></span>  
  
```  
HRESULT EnumModuleFrozenObjects(  
    [in] ModuleID moduleID,  
    [out] ICorProfilerObjectEnum** ppEnum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e0bf6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e0bf6-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="e0bf6-106">[in] El identificador del módulo que contiene los objetos inmovilizados que hay que enumerar.</span><span class="sxs-lookup"><span data-stu-id="e0bf6-106">[in] The ID of the module that contains the frozen objects to be enumerated.</span></span>  
  
 `ppEnum`  
 <span data-ttu-id="e0bf6-107">[out] Un puntero a la dirección de un [ICorProfilerObjectEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md) interfaz, que enumera los objetos inmovilizados.</span><span class="sxs-lookup"><span data-stu-id="e0bf6-107">[out] A pointer to the address of an [ICorProfilerObjectEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md) interface, which enumerates the frozen objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0bf6-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e0bf6-108">Requirements</span></span>  
 <span data-ttu-id="e0bf6-109">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e0bf6-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0bf6-110">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e0bf6-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e0bf6-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e0bf6-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e0bf6-112">**Versiones de .NET framework:** 3.5, 3.0 SP1, 3.0, 2.0 SP1, 2.0</span><span class="sxs-lookup"><span data-stu-id="e0bf6-112">**.NET Framework Versions:** 3.5, 3.0 SP1, 3.0, 2.0 SP1, 2.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0bf6-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="e0bf6-113">See Also</span></span>  
 [<span data-ttu-id="e0bf6-114">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e0bf6-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="e0bf6-115">ICorProfilerInfo2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e0bf6-115">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
