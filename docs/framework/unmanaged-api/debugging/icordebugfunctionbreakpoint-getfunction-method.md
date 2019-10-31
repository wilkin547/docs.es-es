---
title: ICorDebugFunctionBreakpoint::GetFunction (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugFunctionBreakpoint.GetFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunctionBreakpoint::GetFunction
helpviewer_keywords:
- ICorDebugFunctionBreakpoint::GetFunction method [.NET Framework debugging]
- GetFunction method, ICorDebugFunctionBreakpoint interface [.NET Framework debugging]
ms.assetid: 2a62dae5-dd8a-4696-b817-0e1e586c24a0
topic_type:
- apiref
ms.openlocfilehash: 0b53c80157bfd99a766eb691e8a8a2e6b9659a95
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137746"
---
# <a name="icordebugfunctionbreakpointgetfunction-method"></a><span data-ttu-id="af39c-102">ICorDebugFunctionBreakpoint::GetFunction (Método)</span><span class="sxs-lookup"><span data-stu-id="af39c-102">ICorDebugFunctionBreakpoint::GetFunction Method</span></span>
<span data-ttu-id="af39c-103">Obtiene un puntero de interfaz a una ICorDebugFunction que hace referencia a la función en la que se establece el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="af39c-103">Gets an interface pointer to an ICorDebugFunction that references the function in which the breakpoint is set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af39c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="af39c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunction (  
    [out] ICorDebugFunction  **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="af39c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="af39c-105">Parameters</span></span>  
 `ppFunction`  
 <span data-ttu-id="af39c-106">enuncia Puntero a la dirección de la función en la que se establece el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="af39c-106">[out] A pointer to the address of the function in which the breakpoint is set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af39c-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="af39c-107">Requirements</span></span>  
 <span data-ttu-id="af39c-108">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="af39c-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af39c-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="af39c-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="af39c-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="af39c-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="af39c-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af39c-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
