---
title: ICorDebugFunction::CreateBreakpoint (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.CreateBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::CreateBreakpoint
helpviewer_keywords:
- ICorDebugFunction::CreateBreakpoint method [.NET Framework debugging]
- CreateBreakpoint method, ICorDebugFunction interface [.NET Framework debugging]
ms.assetid: ffd0f708-0d21-4fae-a395-63b6c45828fa
topic_type:
- apiref
ms.openlocfilehash: 64304b671532325bdc2f8841a2702d537d143330
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124046"
---
# <a name="icordebugfunctioncreatebreakpoint-method"></a><span data-ttu-id="01619-102">ICorDebugFunction::CreateBreakpoint (Método)</span><span class="sxs-lookup"><span data-stu-id="01619-102">ICorDebugFunction::CreateBreakpoint Method</span></span>
<span data-ttu-id="01619-103">Crea un punto de interrupción al principio de esta función.</span><span class="sxs-lookup"><span data-stu-id="01619-103">Creates a breakpoint at the beginning of this function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01619-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="01619-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateBreakpoint (  
    [out] ICorDebugFunctionBreakpoint **ppBreakpoint  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="01619-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="01619-105">Parameters</span></span>  
 `ppBreakpoint`  
 <span data-ttu-id="01619-106">enuncia Puntero a la dirección de un objeto ICorDebugFunctionBreakpoint que representa el nuevo punto de interrupción de la función.</span><span class="sxs-lookup"><span data-stu-id="01619-106">[out] A pointer to the address of an ICorDebugFunctionBreakpoint object that represents the new breakpoint for the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01619-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="01619-107">Requirements</span></span>  
 <span data-ttu-id="01619-108">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="01619-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01619-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="01619-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="01619-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="01619-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="01619-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01619-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
