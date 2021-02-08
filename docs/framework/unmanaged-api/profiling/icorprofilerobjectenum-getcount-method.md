---
description: 'Más información acerca de: ICorProfilerObjectEnum:: GetCount (método)'
title: ICorProfilerObjectEnum::GetCount (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerObjectEnum.GetCount
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerObjectEnum::GetCount
helpviewer_keywords:
- ICorProfilerObjectEnum::GetCount method [.NET Framework profiling]
- GetCount method, ICorProfilerObjectEnum interface [.NET Framework profiling]
ms.assetid: 166b0761-ed80-4ccd-9973-dc20e61bf8fa
topic_type:
- apiref
ms.openlocfilehash: b1bedfca913a099f88780807021497d15f75fcd8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99798945"
---
# <a name="icorprofilerobjectenumgetcount-method"></a><span data-ttu-id="7b5fb-103">ICorProfilerObjectEnum::GetCount (Método)</span><span class="sxs-lookup"><span data-stu-id="7b5fb-103">ICorProfilerObjectEnum::GetCount Method</span></span>

<span data-ttu-id="7b5fb-104">Obtiene el número total de objetos inmovilizados de la colección.</span><span class="sxs-lookup"><span data-stu-id="7b5fb-104">Gets the total number of frozen objects in the collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b5fb-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7b5fb-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCount (  
    [out] ULONG   *pcelt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7b5fb-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7b5fb-106">Parameters</span></span>  

 `pcelt`  
 <span data-ttu-id="7b5fb-107">enuncia Puntero al número de objetos inmovilizados de la colección.</span><span class="sxs-lookup"><span data-stu-id="7b5fb-107">[out] A pointer to the number of frozen objects in the collection.</span></span>  
  
 <span data-ttu-id="7b5fb-108">Este método siempre devolverá cero en la .NET Framework versión 3,5 Service Pack 1 (SP1) y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="7b5fb-108">This method will always return zero in the .NET Framework version 3.5 Service Pack 1 (SP1) and later versions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b5fb-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7b5fb-109">Requirements</span></span>  

 <span data-ttu-id="7b5fb-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b5fb-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b5fb-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7b5fb-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7b5fb-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7b5fb-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7b5fb-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b5fb-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b5fb-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="7b5fb-114">See also</span></span>

- [<span data-ttu-id="7b5fb-115">ICorProfilerObjectEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7b5fb-115">ICorProfilerObjectEnum Interface</span></span>](icorprofilerobjectenum-interface.md)
