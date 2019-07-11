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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f4f9ea741e545cc424dff450325c3f8d271c8554
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67755579"
---
# <a name="icordebugfunctionbreakpointgetfunction-method"></a><span data-ttu-id="754eb-102">ICorDebugFunctionBreakpoint::GetFunction (Método)</span><span class="sxs-lookup"><span data-stu-id="754eb-102">ICorDebugFunctionBreakpoint::GetFunction Method</span></span>
<span data-ttu-id="754eb-103">Obtiene un puntero de interfaz a un ICorDebugFunction que hace referencia a la función en el que se establece el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="754eb-103">Gets an interface pointer to an ICorDebugFunction that references the function in which the breakpoint is set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="754eb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="754eb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunction (  
    [out] ICorDebugFunction  **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="754eb-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="754eb-105">Parameters</span></span>  
 `ppFunction`  
 <span data-ttu-id="754eb-106">[out] Un puntero a la dirección de la función en el que se establece el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="754eb-106">[out] A pointer to the address of the function in which the breakpoint is set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="754eb-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="754eb-107">Requirements</span></span>  
 <span data-ttu-id="754eb-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="754eb-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="754eb-109">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="754eb-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="754eb-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="754eb-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="754eb-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="754eb-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
