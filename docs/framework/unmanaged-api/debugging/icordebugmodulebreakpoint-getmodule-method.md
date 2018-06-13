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
ms.openlocfilehash: 5cbb1aa9c81101eb818a9e7829c777efd3923b5f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33416158"
---
# <a name="icordebugmodulebreakpointgetmodule-method"></a><span data-ttu-id="3d1e9-102">ICorDebugModuleBreakpoint::GetModule (Método)</span><span class="sxs-lookup"><span data-stu-id="3d1e9-102">ICorDebugModuleBreakpoint::GetModule Method</span></span>
<span data-ttu-id="3d1e9-103">Obtiene un puntero de interfaz a un "ICorDebugModule" que hace referencia el módulo en el que se ha establecido este punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="3d1e9-103">Gets an interface pointer to an "ICorDebugModule" that references the module in which this breakpoint is set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d1e9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3d1e9-104">Syntax</span></span>  
  
```  
HRESULT GetModule (  
    [out] ICorDebugModule   **ppModule  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3d1e9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3d1e9-105">Parameters</span></span>  
 `ppModule`  
 <span data-ttu-id="3d1e9-106">[out] Un puntero a la dirección de un `ICorDebugModule` interfaz que hace referencia al módulo en el que se establece el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="3d1e9-106">[out] A pointer to the address of an `ICorDebugModule` interface that references the module in which the breakpoint is set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d1e9-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3d1e9-107">Requirements</span></span>  
 <span data-ttu-id="3d1e9-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d1e9-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d1e9-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3d1e9-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3d1e9-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3d1e9-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3d1e9-111">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d1e9-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d1e9-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="3d1e9-112">See Also</span></span>  
 
