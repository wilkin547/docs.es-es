---
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
ms.openlocfilehash: df1d5881bccdb357b16c7f02cd090388e0f66273
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722809"
---
# <a name="icorprofilerobjectenumclone-method"></a><span data-ttu-id="eb687-102">ICorProfilerObjectEnum::Clone (Método)</span><span class="sxs-lookup"><span data-stu-id="eb687-102">ICorProfilerObjectEnum::Clone Method</span></span>

<span data-ttu-id="eb687-103">Obtiene un puntero de interfaz a una copia de esta interfaz [ICorProfilerObjectEnum](icorprofilerobjectenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="eb687-103">Gets an interface pointer to a copy of this [ICorProfilerObjectEnum](icorprofilerobjectenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb687-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="eb687-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone (  
    [out] ICorProfilerObjectEnum   **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eb687-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="eb687-105">Parameters</span></span>  

 `ppEnum`  
 <span data-ttu-id="eb687-106">enuncia Puntero al puntero de interfaz que a su vez apunta a la copia de esta `ICorProfilerObjectEnum` interfaz.</span><span class="sxs-lookup"><span data-stu-id="eb687-106">[out] A pointer to the interface pointer that in turn points to the copy of this `ICorProfilerObjectEnum` interface.</span></span> <span data-ttu-id="eb687-107">La copia mantiene su propio estado de enumeración independiente de este.</span><span class="sxs-lookup"><span data-stu-id="eb687-107">The copy maintains its own enumeration state separately from this one.</span></span> <span data-ttu-id="eb687-108">Sin embargo, la posición inicial del cursor de la copia será la misma que la posición actual del cursor de este enumerador.</span><span class="sxs-lookup"><span data-stu-id="eb687-108">However, the copy's initial cursor position will be the same as this enumerator's current cursor position.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb687-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="eb687-109">Requirements</span></span>  

 <span data-ttu-id="eb687-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eb687-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb687-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="eb687-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="eb687-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eb687-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eb687-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb687-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb687-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="eb687-114">See also</span></span>

- [<span data-ttu-id="eb687-115">ICorProfilerObjectEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="eb687-115">ICorProfilerObjectEnum Interface</span></span>](icorprofilerobjectenum-interface.md)
