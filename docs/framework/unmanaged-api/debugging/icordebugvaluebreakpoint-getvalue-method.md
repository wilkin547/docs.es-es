---
title: "ICorDebugValueBreakpoint::GetValue (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugValueBreakpoint.GetValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugValueBreakpoint::GetValue
helpviewer_keywords:
- GetValue method, ICorDebugValueBreakpoint interface [.NET Framework debugging]
- ICorDebugValueBreakpoint::GetValue method [.NET Framework debugging]
ms.assetid: 52a73654-bc47-48b6-b2b1-a4456b10140c
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 68f918b74a5a4abd9820071b4a4772f9b57b9c88
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugvaluebreakpointgetvalue-method"></a><span data-ttu-id="e62e8-102">ICorDebugValueBreakpoint::GetValue (Método)</span><span class="sxs-lookup"><span data-stu-id="e62e8-102">ICorDebugValueBreakpoint::GetValue Method</span></span>
<span data-ttu-id="e62e8-103">Obtiene un puntero de interfaz a un objeto de "ICorDebugValue" que representa el valor del objeto en el que se ha establecido el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="e62e8-103">Gets an interface pointer to an "ICorDebugValue" object that represents the value of the object on which the breakpoint is set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e62e8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e62e8-104">Syntax</span></span>  
  
```  
HRESULT GetValue (  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e62e8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e62e8-105">Parameters</span></span>  
 `ppValue`  
 <span data-ttu-id="e62e8-106">[out] Un puntero a la dirección de un `ICorDebugValue` objeto.</span><span class="sxs-lookup"><span data-stu-id="e62e8-106">[out] A pointer to the address of an `ICorDebugValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e62e8-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e62e8-107">Requirements</span></span>  
 <span data-ttu-id="e62e8-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e62e8-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e62e8-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e62e8-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e62e8-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e62e8-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e62e8-111">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e62e8-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e62e8-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="e62e8-112">See Also</span></span>  
 
