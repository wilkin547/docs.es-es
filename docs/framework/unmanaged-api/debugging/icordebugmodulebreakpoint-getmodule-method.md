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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 51403c52d7f8a216e83b817f157979f4af1c433a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59162873"
---
# <a name="icordebugmodulebreakpointgetmodule-method"></a><span data-ttu-id="32002-102">ICorDebugModuleBreakpoint::GetModule (Método)</span><span class="sxs-lookup"><span data-stu-id="32002-102">ICorDebugModuleBreakpoint::GetModule Method</span></span>
<span data-ttu-id="32002-103">Obtiene un puntero de interfaz a un "ICorDebugModule" que hace referencia al módulo en el que se establece este punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="32002-103">Gets an interface pointer to an "ICorDebugModule" that references the module in which this breakpoint is set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32002-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="32002-104">Syntax</span></span>  
  
```  
HRESULT GetModule (  
    [out] ICorDebugModule   **ppModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="32002-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="32002-105">Parameters</span></span>  
 `ppModule`  
 <span data-ttu-id="32002-106">[out] Un puntero a la dirección de un `ICorDebugModule` interfaz que hace referencia al módulo en el que se establece el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="32002-106">[out] A pointer to the address of an `ICorDebugModule` interface that references the module in which the breakpoint is set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32002-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="32002-107">Requirements</span></span>  
 <span data-ttu-id="32002-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="32002-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32002-109">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="32002-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="32002-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="32002-110">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="32002-111">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="32002-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="32002-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="32002-112">See also</span></span>
