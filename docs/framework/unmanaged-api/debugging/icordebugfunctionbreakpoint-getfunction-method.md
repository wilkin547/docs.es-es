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
ms.openlocfilehash: 79a6c70399d5059d6959ac6127f22807138c00fa
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213119"
---
# <a name="icordebugfunctionbreakpointgetfunction-method"></a><span data-ttu-id="9eb33-102">ICorDebugFunctionBreakpoint::GetFunction (Método)</span><span class="sxs-lookup"><span data-stu-id="9eb33-102">ICorDebugFunctionBreakpoint::GetFunction Method</span></span>
<span data-ttu-id="9eb33-103">Obtiene un puntero de interfaz a una ICorDebugFunction que hace referencia a la función en la que se establece el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="9eb33-103">Gets an interface pointer to an ICorDebugFunction that references the function in which the breakpoint is set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9eb33-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9eb33-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunction (  
    [out] ICorDebugFunction  **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9eb33-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9eb33-105">Parameters</span></span>  
 `ppFunction`  
 <span data-ttu-id="9eb33-106">enuncia Puntero a la dirección de la función en la que se establece el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="9eb33-106">[out] A pointer to the address of the function in which the breakpoint is set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9eb33-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9eb33-107">Requirements</span></span>  
 <span data-ttu-id="9eb33-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9eb33-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9eb33-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9eb33-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9eb33-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9eb33-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9eb33-111">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9eb33-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
