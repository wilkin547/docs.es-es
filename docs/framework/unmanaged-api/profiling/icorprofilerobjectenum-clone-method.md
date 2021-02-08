---
description: 'Más información acerca de: ICorProfilerObjectEnum:: Clone (método)'
title: ICorProfilerObjectEnum::Clone (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerObjectEnum.Clone
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerObjectEnum::Clone
helpviewer_keywords:
- Clone method, ICorProfilerObjectEnum interface [.NET Framework profiling]
- ICorProfilerObjectEnum::Clone method [.NET Framework profiling]
ms.assetid: b0b2facd-5991-4f4c-932d-c4937f45cef9
topic_type:
- apiref
ms.openlocfilehash: 59971f6f6e7edab4b4c4f796ee7bea3c4d8b4e91
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99798958"
---
# <a name="icorprofilerobjectenumclone-method"></a><span data-ttu-id="5aeb0-103">ICorProfilerObjectEnum::Clone (Método)</span><span class="sxs-lookup"><span data-stu-id="5aeb0-103">ICorProfilerObjectEnum::Clone Method</span></span>

<span data-ttu-id="5aeb0-104">Obtiene un puntero de interfaz a una copia de esta interfaz [ICorProfilerObjectEnum](icorprofilerobjectenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="5aeb0-104">Gets an interface pointer to a copy of this [ICorProfilerObjectEnum](icorprofilerobjectenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5aeb0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5aeb0-105">Syntax</span></span>  
  
```cpp  
HRESULT Clone (  
    [out] ICorProfilerObjectEnum   **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5aeb0-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5aeb0-106">Parameters</span></span>  

 `ppEnum`  
 <span data-ttu-id="5aeb0-107">enuncia Puntero al puntero de interfaz que a su vez apunta a la copia de esta `ICorProfilerObjectEnum` interfaz.</span><span class="sxs-lookup"><span data-stu-id="5aeb0-107">[out] A pointer to the interface pointer that in turn points to the copy of this `ICorProfilerObjectEnum` interface.</span></span> <span data-ttu-id="5aeb0-108">La copia mantiene su propio estado de enumeración independiente de este.</span><span class="sxs-lookup"><span data-stu-id="5aeb0-108">The copy maintains its own enumeration state separately from this one.</span></span> <span data-ttu-id="5aeb0-109">Sin embargo, la posición inicial del cursor de la copia será la misma que la posición actual del cursor de este enumerador.</span><span class="sxs-lookup"><span data-stu-id="5aeb0-109">However, the copy's initial cursor position will be the same as this enumerator's current cursor position.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5aeb0-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5aeb0-110">Requirements</span></span>  

 <span data-ttu-id="5aeb0-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5aeb0-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5aeb0-112">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5aeb0-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5aeb0-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5aeb0-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5aeb0-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5aeb0-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5aeb0-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="5aeb0-115">See also</span></span>

- [<span data-ttu-id="5aeb0-116">ICorProfilerObjectEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5aeb0-116">ICorProfilerObjectEnum Interface</span></span>](icorprofilerobjectenum-interface.md)
