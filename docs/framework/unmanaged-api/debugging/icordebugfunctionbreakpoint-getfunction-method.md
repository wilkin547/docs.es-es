---
description: 'Más información sobre: ICorDebugFunctionBreakpoint:: GetFunction ((método)'
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
ms.openlocfilehash: 1e407acda81e5e6397da003a9b91a48d4d171e5d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754100"
---
# <a name="icordebugfunctionbreakpointgetfunction-method"></a><span data-ttu-id="63f17-103">ICorDebugFunctionBreakpoint::GetFunction (Método)</span><span class="sxs-lookup"><span data-stu-id="63f17-103">ICorDebugFunctionBreakpoint::GetFunction Method</span></span>

<span data-ttu-id="63f17-104">Obtiene un puntero de interfaz a una ICorDebugFunction que hace referencia a la función en la que se establece el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="63f17-104">Gets an interface pointer to an ICorDebugFunction that references the function in which the breakpoint is set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63f17-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="63f17-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFunction (  
    [out] ICorDebugFunction  **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="63f17-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="63f17-106">Parameters</span></span>  

 `ppFunction`  
 <span data-ttu-id="63f17-107">enuncia Puntero a la dirección de la función en la que se establece el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="63f17-107">[out] A pointer to the address of the function in which the breakpoint is set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63f17-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="63f17-108">Requirements</span></span>  

 <span data-ttu-id="63f17-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63f17-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63f17-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="63f17-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="63f17-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="63f17-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="63f17-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63f17-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
