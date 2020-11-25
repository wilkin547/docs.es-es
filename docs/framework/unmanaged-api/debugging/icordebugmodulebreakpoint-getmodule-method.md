---
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
ms.openlocfilehash: b6363ef901d5297862ca46e685bb783aaaeb4123
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709627"
---
# <a name="icordebugmodulebreakpointgetmodule-method"></a><span data-ttu-id="bcd3f-102">ICorDebugModuleBreakpoint::GetModule (Método)</span><span class="sxs-lookup"><span data-stu-id="bcd3f-102">ICorDebugModuleBreakpoint::GetModule Method</span></span>

<span data-ttu-id="bcd3f-103">Obtiene un puntero de interfaz a un "ICorDebugModule" que hace referencia al módulo en el que se establece este punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="bcd3f-103">Gets an interface pointer to an "ICorDebugModule" that references the module in which this breakpoint is set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bcd3f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bcd3f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModule (  
    [out] ICorDebugModule   **ppModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bcd3f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bcd3f-105">Parameters</span></span>  

 `ppModule`  
 <span data-ttu-id="bcd3f-106">enuncia Puntero a la dirección de una `ICorDebugModule` interfaz que hace referencia al módulo en el que se establece el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="bcd3f-106">[out] A pointer to the address of an `ICorDebugModule` interface that references the module in which the breakpoint is set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bcd3f-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bcd3f-107">Requirements</span></span>  

 <span data-ttu-id="bcd3f-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bcd3f-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bcd3f-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bcd3f-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bcd3f-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bcd3f-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bcd3f-111">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bcd3f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcd3f-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bcd3f-112">See also</span></span>
