---
title: ICorDebugAppDomain::EnumerateSteppers (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.EnumerateSteppers
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::EnumerateSteppers
helpviewer_keywords:
- ICorDebugAppDomain::EnumerateSteppers method [.NET Framework debugging]
- EnumerateSteppers method [.NET Framework debugging]
ms.assetid: 3f3c4503-570e-44c1-ae6a-a3c6b840c732
topic_type:
- apiref
ms.openlocfilehash: fd9243d9e0c12b572613694538661fd553e8a487
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715932"
---
# <a name="icordebugappdomainenumeratesteppers-method"></a><span data-ttu-id="4120a-102">ICorDebugAppDomain::EnumerateSteppers (Método)</span><span class="sxs-lookup"><span data-stu-id="4120a-102">ICorDebugAppDomain::EnumerateSteppers Method</span></span>

<span data-ttu-id="4120a-103">Obtiene un enumerador para todos los steppers activos en el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="4120a-103">Gets an enumerator for all active steppers in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4120a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4120a-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateSteppers (  
    [out] ICorDebugStepperEnum   **ppSteppers  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4120a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4120a-105">Parameters</span></span>  

 `ppSteppers`  
 <span data-ttu-id="4120a-106">enuncia Un puntero a la dirección de un objeto ICorDebugStepperEnum (que es el enumerador de todos los steppers activos en el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="4120a-106">[out] A pointer to the address of an ICorDebugStepperEnum object that is the enumerator for all active steppers in the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4120a-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4120a-107">Requirements</span></span>  

 <span data-ttu-id="4120a-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4120a-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4120a-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4120a-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4120a-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4120a-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4120a-111">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4120a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
