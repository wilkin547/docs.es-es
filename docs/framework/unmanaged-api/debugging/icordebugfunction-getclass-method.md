---
description: 'Más información acerca de: ICorDebugFunction:: GetClass (método)'
title: ICorDebugFunction::GetClass (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetClass
helpviewer_keywords:
- GetClass method, ICorDebugFunction interface [.NET Framework debugging]
- ICorDebugFunction::GetClass method [.NET Framework debugging]
ms.assetid: 27967230-144f-40d3-9e23-961d0241abd9
topic_type:
- apiref
ms.openlocfilehash: 09049962082bc51cc47a56b0de591a26c2ef93fc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99692594"
---
# <a name="icordebugfunctiongetclass-method"></a><span data-ttu-id="1c9cd-103">ICorDebugFunction::GetClass (Método)</span><span class="sxs-lookup"><span data-stu-id="1c9cd-103">ICorDebugFunction::GetClass Method</span></span>

<span data-ttu-id="1c9cd-104">Obtiene un objeto ICorDebugClass que representa la clase de la que es miembro esta función.</span><span class="sxs-lookup"><span data-stu-id="1c9cd-104">Gets an ICorDebugClass object that represents the class this function is a member of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c9cd-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1c9cd-105">Syntax</span></span>  
  
```cpp  
HRESULT GetClass (  
    [out] ICorDebugClass **ppClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1c9cd-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1c9cd-106">Parameters</span></span>  

 `ppClass`  
 <span data-ttu-id="1c9cd-107">enuncia Puntero a la dirección del `ICorDebugClass` objeto que representa la clase, o null si esta función no es un miembro de una clase.</span><span class="sxs-lookup"><span data-stu-id="1c9cd-107">[out] A pointer to the address of the `ICorDebugClass` object that represents the class, or null, if this function is not a member of a class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c9cd-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1c9cd-108">Requirements</span></span>  

 <span data-ttu-id="1c9cd-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c9cd-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c9cd-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1c9cd-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1c9cd-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1c9cd-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1c9cd-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c9cd-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
