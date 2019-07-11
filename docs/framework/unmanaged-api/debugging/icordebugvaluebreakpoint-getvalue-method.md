---
title: ICorDebugValueBreakpoint::GetValue (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugValueBreakpoint.GetValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValueBreakpoint::GetValue
helpviewer_keywords:
- GetValue method, ICorDebugValueBreakpoint interface [.NET Framework debugging]
- ICorDebugValueBreakpoint::GetValue method [.NET Framework debugging]
ms.assetid: 52a73654-bc47-48b6-b2b1-a4456b10140c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 639b34093e79933b4daaa0e3ae5223f1a1a51bf6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67773781"
---
# <a name="icordebugvaluebreakpointgetvalue-method"></a><span data-ttu-id="f5e13-102">ICorDebugValueBreakpoint::GetValue (Método)</span><span class="sxs-lookup"><span data-stu-id="f5e13-102">ICorDebugValueBreakpoint::GetValue Method</span></span>
<span data-ttu-id="f5e13-103">Obtiene un puntero de interfaz a un objeto "ICorDebugValue" que representa el valor del objeto en el que se establece el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="f5e13-103">Gets an interface pointer to an "ICorDebugValue" object that represents the value of the object on which the breakpoint is set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5e13-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f5e13-104">Syntax</span></span>  
  
```cpp  
HRESULT GetValue (  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f5e13-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f5e13-105">Parameters</span></span>  
 `ppValue`  
 <span data-ttu-id="f5e13-106">[out] Un puntero a la dirección de un `ICorDebugValue` objeto.</span><span class="sxs-lookup"><span data-stu-id="f5e13-106">[out] A pointer to the address of an `ICorDebugValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5e13-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f5e13-107">Requirements</span></span>  
 <span data-ttu-id="f5e13-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f5e13-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5e13-109">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f5e13-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f5e13-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f5e13-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f5e13-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5e13-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5e13-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="f5e13-112">See also</span></span>
