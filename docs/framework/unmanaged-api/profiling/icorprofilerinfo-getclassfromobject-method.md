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
ms.openlocfilehash: a5573765486112a83f5ea7cc9258447692f72166
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76864079"
---
# <a name="icorprofilerinfogetclassfromobject-method"></a><span data-ttu-id="14f68-102">ICorProfilerInfo::GetClassFromObject (Método)</span><span class="sxs-lookup"><span data-stu-id="14f68-102">ICorProfilerInfo::GetClassFromObject Method</span></span>
<span data-ttu-id="14f68-103">Obtiene el `ClassID` de un objeto, dado su `ObjectID`.</span><span class="sxs-lookup"><span data-stu-id="14f68-103">Gets the `ClassID` of an object, given its `ObjectID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14f68-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="14f68-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClassFromObject(  
    [in]  ObjectID objectId,  
    [out] ClassID *pClassId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="14f68-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="14f68-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="14f68-106">de IDENTIFICADOR del objeto para el que se va a obtener el `ClassID`.</span><span class="sxs-lookup"><span data-stu-id="14f68-106">[in] The ID of the object for which to get the `ClassID`.</span></span>  
  
 `pClassId`  
 <span data-ttu-id="14f68-107">enuncia Puntero al `ClassID`devuelto.</span><span class="sxs-lookup"><span data-stu-id="14f68-107">[out] A pointer to the returned `ClassID`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="14f68-108">Notas</span><span class="sxs-lookup"><span data-stu-id="14f68-108">Remarks</span></span>  
 <span data-ttu-id="14f68-109">Un valor null `pClassId` indica que `objectId` tiene un tipo que se está descargando.</span><span class="sxs-lookup"><span data-stu-id="14f68-109">A null `pClassId` indicates that `objectId` has a type that is unloading.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14f68-110">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="14f68-110">Requirements</span></span>  
 <span data-ttu-id="14f68-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="14f68-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14f68-112">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="14f68-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="14f68-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="14f68-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="14f68-114">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14f68-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14f68-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="14f68-115">See also</span></span>

- [<span data-ttu-id="14f68-116">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="14f68-116">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
