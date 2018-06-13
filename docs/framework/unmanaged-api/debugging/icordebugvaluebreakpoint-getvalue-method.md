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
ms.openlocfilehash: b8ff07c483ef1bcbf9d5141b7180cea08454ebef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33417104"
---
# <a name="icordebugvaluebreakpointgetvalue-method"></a><span data-ttu-id="e61f5-102">ICorDebugValueBreakpoint::GetValue (Método)</span><span class="sxs-lookup"><span data-stu-id="e61f5-102">ICorDebugValueBreakpoint::GetValue Method</span></span>
<span data-ttu-id="e61f5-103">Obtiene un puntero de interfaz a un objeto de "ICorDebugValue" que representa el valor del objeto en el que se ha establecido el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="e61f5-103">Gets an interface pointer to an "ICorDebugValue" object that represents the value of the object on which the breakpoint is set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e61f5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e61f5-104">Syntax</span></span>  
  
```  
HRESULT GetValue (  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e61f5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e61f5-105">Parameters</span></span>  
 `ppValue`  
 <span data-ttu-id="e61f5-106">[out] Un puntero a la dirección de un `ICorDebugValue` objeto.</span><span class="sxs-lookup"><span data-stu-id="e61f5-106">[out] A pointer to the address of an `ICorDebugValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e61f5-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e61f5-107">Requirements</span></span>  
 <span data-ttu-id="e61f5-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e61f5-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e61f5-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e61f5-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e61f5-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e61f5-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e61f5-111">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e61f5-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e61f5-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="e61f5-112">See Also</span></span>  
 
