---
description: 'Más información acerca de: ICorProfilerInfo:: Getclassfromobject ((método)'
title: ICorProfilerInfo::GetClassFromObject (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetClassFromObject
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetClassFromObject
helpviewer_keywords:
- GetClassFromObject method [.NET Framework profiling]
- ICorProfilerInfo::GetClassFromObject method [.NET Framework profiling]
ms.assetid: b97493fb-713e-49d5-a73e-5688b2ad0700
topic_type:
- apiref
ms.openlocfilehash: 1c0224137c839d167263eefb17e3ae0b3ac29ef3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99647822"
---
# <a name="icorprofilerinfogetclassfromobject-method"></a><span data-ttu-id="951f6-103">ICorProfilerInfo::GetClassFromObject (Método)</span><span class="sxs-lookup"><span data-stu-id="951f6-103">ICorProfilerInfo::GetClassFromObject Method</span></span>

<span data-ttu-id="951f6-104">Obtiene el `ClassID` de un objeto, dado su `ObjectID` .</span><span class="sxs-lookup"><span data-stu-id="951f6-104">Gets the `ClassID` of an object, given its `ObjectID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="951f6-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="951f6-105">Syntax</span></span>  
  
```cpp  
HRESULT GetClassFromObject(  
    [in]  ObjectID objectId,  
    [out] ClassID *pClassId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="951f6-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="951f6-106">Parameters</span></span>  

 `objectId`  
 <span data-ttu-id="951f6-107">de IDENTIFICADOR del objeto para el que se va a obtener `ClassID` .</span><span class="sxs-lookup"><span data-stu-id="951f6-107">[in] The ID of the object for which to get the `ClassID`.</span></span>  
  
 `pClassId`  
 <span data-ttu-id="951f6-108">enuncia Puntero al devuelto `ClassID` .</span><span class="sxs-lookup"><span data-stu-id="951f6-108">[out] A pointer to the returned `ClassID`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="951f6-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="951f6-109">Remarks</span></span>  

 <span data-ttu-id="951f6-110">Un valor null `pClassId` indica que `objectId` tiene un tipo que se está descargando.</span><span class="sxs-lookup"><span data-stu-id="951f6-110">A null `pClassId` indicates that `objectId` has a type that is unloading.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="951f6-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="951f6-111">Requirements</span></span>  

 <span data-ttu-id="951f6-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="951f6-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="951f6-113">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="951f6-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="951f6-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="951f6-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="951f6-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="951f6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="951f6-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="951f6-116">See also</span></span>

- [<span data-ttu-id="951f6-117">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="951f6-117">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
