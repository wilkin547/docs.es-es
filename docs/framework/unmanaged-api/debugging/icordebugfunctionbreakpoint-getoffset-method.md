---
title: ICorDebugFunctionBreakpoint::GetOffset (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugFunctionBreakpoint.GetOffset
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunctionBreakpoint::GetOffset
helpviewer_keywords:
- ICorDebugFunctionBreakpoint::GetOffset method [.NET Framework debugging]
- GetOffset method, ICorDebugFunctionBreakpoint interface [.NET Framework debugging]
ms.assetid: e619eae4-3ac3-4c37-bba4-55e59989b9cb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 67e71002a78023ad6e8ef89c7a57d484a65aaeb3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67756384"
---
# <a name="icordebugfunctionbreakpointgetoffset-method"></a><span data-ttu-id="40aac-102">ICorDebugFunctionBreakpoint::GetOffset (Método)</span><span class="sxs-lookup"><span data-stu-id="40aac-102">ICorDebugFunctionBreakpoint::GetOffset Method</span></span>
<span data-ttu-id="40aac-103">Obtiene el desplazamiento del punto de interrupción dentro de la función.</span><span class="sxs-lookup"><span data-stu-id="40aac-103">Gets the offset of the breakpoint within the function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40aac-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="40aac-104">Syntax</span></span>  
  
```cpp  
HRESULT GetOffset (  
    [out] ULONG32  *pnOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="40aac-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="40aac-105">Parameters</span></span>  
 `pnOffset`  
 <span data-ttu-id="40aac-106">[out] Un puntero al desplazamiento del punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="40aac-106">[out] A pointer to the offset of the breakpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40aac-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="40aac-107">Requirements</span></span>  
 <span data-ttu-id="40aac-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="40aac-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40aac-109">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="40aac-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="40aac-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="40aac-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="40aac-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40aac-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
