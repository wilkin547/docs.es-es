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
ms.openlocfilehash: a736990188023031eb8df5a76dd16fcc289cfe20
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134033"
---
# <a name="icordebugappdomainenumeratesteppers-method"></a><span data-ttu-id="96571-102">ICorDebugAppDomain::EnumerateSteppers (Método)</span><span class="sxs-lookup"><span data-stu-id="96571-102">ICorDebugAppDomain::EnumerateSteppers Method</span></span>
<span data-ttu-id="96571-103">Obtiene un enumerador para todos los steppers activos en el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="96571-103">Gets an enumerator for all active steppers in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96571-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="96571-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateSteppers (  
    [out] ICorDebugStepperEnum   **ppSteppers  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="96571-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="96571-105">Parameters</span></span>  
 `ppSteppers`  
 <span data-ttu-id="96571-106">enuncia Un puntero a la dirección de un objeto ICorDebugStepperEnum (que es el enumerador de todos los steppers activos en el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="96571-106">[out] A pointer to the address of an ICorDebugStepperEnum object that is the enumerator for all active steppers in the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96571-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="96571-107">Requirements</span></span>  
 <span data-ttu-id="96571-108">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="96571-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96571-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="96571-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="96571-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="96571-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="96571-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96571-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
