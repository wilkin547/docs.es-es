---
description: 'Más información acerca de: ICorDebugModuleBreakpoint (:: GetModule (método)'
title: ICorDebugModuleBreakpoint::GetModule (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugModuleBreakpoint.GetModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModuleBreakpoint::GetModule
helpviewer_keywords:
- ICorDebugModuleBreakpoint::GetModule method [.NET Framework debugging]
- GetModule method, ICorDebugModuleBreakpoint interface [.NET Framework debugging]
ms.assetid: ffd5d9ec-4564-4200-b625-b306eec0ebd7
topic_type:
- apiref
ms.openlocfilehash: 3498f9d644d6195f2cd0f83d30417c447d200f3e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790794"
---
# <a name="icordebugmodulebreakpointgetmodule-method"></a><span data-ttu-id="f7c1b-103">ICorDebugModuleBreakpoint::GetModule (Método)</span><span class="sxs-lookup"><span data-stu-id="f7c1b-103">ICorDebugModuleBreakpoint::GetModule Method</span></span>

<span data-ttu-id="f7c1b-104">Obtiene un puntero de interfaz a un "ICorDebugModule" que hace referencia al módulo en el que se establece este punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="f7c1b-104">Gets an interface pointer to an "ICorDebugModule" that references the module in which this breakpoint is set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7c1b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f7c1b-105">Syntax</span></span>  
  
```cpp  
HRESULT GetModule (  
    [out] ICorDebugModule   **ppModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f7c1b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f7c1b-106">Parameters</span></span>  

 `ppModule`  
 <span data-ttu-id="f7c1b-107">enuncia Puntero a la dirección de una `ICorDebugModule` interfaz que hace referencia al módulo en el que se establece el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="f7c1b-107">[out] A pointer to the address of an `ICorDebugModule` interface that references the module in which the breakpoint is set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7c1b-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f7c1b-108">Requirements</span></span>  

 <span data-ttu-id="f7c1b-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f7c1b-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7c1b-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f7c1b-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f7c1b-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f7c1b-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f7c1b-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7c1b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7c1b-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="f7c1b-113">See also</span></span>
