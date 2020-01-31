---
title: ICorProfilerInfo2::EnumModuleFrozenObjects (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.EnumModuleFrozenObjects
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::EnumModuleFrozenObjects
helpviewer_keywords:
- EnumModuleFrozenObjects method [.NET Framework profiling]
- ICorProfilerInfo2::EnumModuleFrozenObjects method [.NET Framework profiling]
ms.assetid: 920b6483-7064-4d64-8613-fcc38ccf9b1e
topic_type:
- apiref
ms.openlocfilehash: 27b3037459ac4f995e37515f6e96c28449c80a4f
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862950"
---
# <a name="icorprofilerinfo2enummodulefrozenobjects-method"></a><span data-ttu-id="65116-102">ICorProfilerInfo2::EnumModuleFrozenObjects (Método)</span><span class="sxs-lookup"><span data-stu-id="65116-102">ICorProfilerInfo2::EnumModuleFrozenObjects Method</span></span>
<span data-ttu-id="65116-103">Obtiene un enumerador que permite la iteración sobre los objetos inmovilizados en el módulo especificado. Este método está obsoleto.</span><span class="sxs-lookup"><span data-stu-id="65116-103">Gets an enumerator that allows iteration over the frozen objects in the specified module.This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65116-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="65116-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumModuleFrozenObjects(  
    [in] ModuleID moduleID,  
    [out] ICorProfilerObjectEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="65116-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="65116-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="65116-106">de IDENTIFICADOR del módulo que contiene los objetos inmovilizados que se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="65116-106">[in] The ID of the module that contains the frozen objects to be enumerated.</span></span>  
  
 `ppEnum`  
 <span data-ttu-id="65116-107">enuncia Puntero a la dirección de una interfaz [ICorProfilerObjectEnum](icorprofilerobjectenum-interface.md) , que enumera los objetos inmovilizados.</span><span class="sxs-lookup"><span data-stu-id="65116-107">[out] A pointer to the address of an [ICorProfilerObjectEnum](icorprofilerobjectenum-interface.md) interface, which enumerates the frozen objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65116-108">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="65116-108">Requirements</span></span>  
 <span data-ttu-id="65116-109">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="65116-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65116-110">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="65116-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="65116-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="65116-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="65116-112">**.NET Framework versiones:** 3,5, 3,0 sp1, 3,0, 2,0 sp1, 2,0</span><span class="sxs-lookup"><span data-stu-id="65116-112">**.NET Framework Versions:** 3.5, 3.0 SP1, 3.0, 2.0 SP1, 2.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65116-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="65116-113">See also</span></span>

- [<span data-ttu-id="65116-114">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="65116-114">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="65116-115">ICorProfilerInfo2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="65116-115">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
