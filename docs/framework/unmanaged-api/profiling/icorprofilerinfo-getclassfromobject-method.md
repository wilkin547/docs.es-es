---
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
ms.openlocfilehash: 5a7edc6045969861679d1b80c0563e99f48932cf
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680254"
---
# <a name="icorprofilerinfogetclassfromobject-method"></a><span data-ttu-id="e7f5b-102">ICorProfilerInfo::GetClassFromObject (Método)</span><span class="sxs-lookup"><span data-stu-id="e7f5b-102">ICorProfilerInfo::GetClassFromObject Method</span></span>

<span data-ttu-id="e7f5b-103">Obtiene el `ClassID` de un objeto, dado su `ObjectID` .</span><span class="sxs-lookup"><span data-stu-id="e7f5b-103">Gets the `ClassID` of an object, given its `ObjectID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7f5b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e7f5b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClassFromObject(  
    [in]  ObjectID objectId,  
    [out] ClassID *pClassId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e7f5b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e7f5b-105">Parameters</span></span>  

 `objectId`  
 <span data-ttu-id="e7f5b-106">de IDENTIFICADOR del objeto para el que se va a obtener `ClassID` .</span><span class="sxs-lookup"><span data-stu-id="e7f5b-106">[in] The ID of the object for which to get the `ClassID`.</span></span>  
  
 `pClassId`  
 <span data-ttu-id="e7f5b-107">enuncia Puntero al devuelto `ClassID` .</span><span class="sxs-lookup"><span data-stu-id="e7f5b-107">[out] A pointer to the returned `ClassID`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e7f5b-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e7f5b-108">Remarks</span></span>  

 <span data-ttu-id="e7f5b-109">Un valor null `pClassId` indica que `objectId` tiene un tipo que se está descargando.</span><span class="sxs-lookup"><span data-stu-id="e7f5b-109">A null `pClassId` indicates that `objectId` has a type that is unloading.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7f5b-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e7f5b-110">Requirements</span></span>  

 <span data-ttu-id="e7f5b-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e7f5b-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7f5b-112">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e7f5b-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e7f5b-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e7f5b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e7f5b-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7f5b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7f5b-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e7f5b-115">See also</span></span>

- [<span data-ttu-id="e7f5b-116">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e7f5b-116">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
