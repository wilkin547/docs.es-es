---
description: 'Más información acerca de: ICorProfilerInfo2:: Enummodulefrozenobjects ((método)'
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
ms.openlocfilehash: b68571544c00c8c234a73404a95433e91f0cfdcf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753216"
---
# <a name="icorprofilerinfo2enummodulefrozenobjects-method"></a><span data-ttu-id="aae96-103">ICorProfilerInfo2::EnumModuleFrozenObjects (Método)</span><span class="sxs-lookup"><span data-stu-id="aae96-103">ICorProfilerInfo2::EnumModuleFrozenObjects Method</span></span>

<span data-ttu-id="aae96-104">Obtiene un enumerador que permite la iteración sobre los objetos inmovilizados en el módulo especificado. Este método está obsoleto.</span><span class="sxs-lookup"><span data-stu-id="aae96-104">Gets an enumerator that allows iteration over the frozen objects in the specified module.This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aae96-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aae96-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumModuleFrozenObjects(  
    [in] ModuleID moduleID,  
    [out] ICorProfilerObjectEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aae96-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="aae96-106">Parameters</span></span>  

 `moduleID`  
 <span data-ttu-id="aae96-107">de IDENTIFICADOR del módulo que contiene los objetos inmovilizados que se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="aae96-107">[in] The ID of the module that contains the frozen objects to be enumerated.</span></span>  
  
 `ppEnum`  
 <span data-ttu-id="aae96-108">enuncia Puntero a la dirección de una interfaz [ICorProfilerObjectEnum](icorprofilerobjectenum-interface.md) , que enumera los objetos inmovilizados.</span><span class="sxs-lookup"><span data-stu-id="aae96-108">[out] A pointer to the address of an [ICorProfilerObjectEnum](icorprofilerobjectenum-interface.md) interface, which enumerates the frozen objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aae96-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="aae96-109">Requirements</span></span>  

 <span data-ttu-id="aae96-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aae96-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aae96-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="aae96-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="aae96-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aae96-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aae96-113">**.NET Framework versiones:** 3,5, 3,0 sp1, 3,0, 2,0 sp1, 2,0</span><span class="sxs-lookup"><span data-stu-id="aae96-113">**.NET Framework Versions:** 3.5, 3.0 SP1, 3.0, 2.0 SP1, 2.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aae96-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="aae96-114">See also</span></span>

- [<span data-ttu-id="aae96-115">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="aae96-115">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="aae96-116">ICorProfilerInfo2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="aae96-116">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
