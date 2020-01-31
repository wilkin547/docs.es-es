---
title: ICorDebugProcess2::ClearUnmanagedBreakpoint (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.ClearUnmanagedBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::ClearUnmanagedBreakpoint
helpviewer_keywords:
- ClearUnmanagedBreakpoint method [.NET Framework debugging]
- ICorDebugProcess2::ClearUnmanagedBreakpoint method [.NET Framework debugging]
ms.assetid: 12ed0fff-7f0e-4d7a-bb70-b3376371f36c
topic_type:
- apiref
ms.openlocfilehash: e2aaf902afd71a4a81f7d64ef3fec046aacc91fc
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792531"
---
# <a name="icordebugprocess2clearunmanagedbreakpoint-method"></a><span data-ttu-id="24a9d-102">ICorDebugProcess2::ClearUnmanagedBreakpoint (Método)</span><span class="sxs-lookup"><span data-stu-id="24a9d-102">ICorDebugProcess2::ClearUnmanagedBreakpoint Method</span></span>
<span data-ttu-id="24a9d-103">Quita un punto de interrupción establecido previamente en la dirección especificada.</span><span class="sxs-lookup"><span data-stu-id="24a9d-103">Removes a previously set breakpoint at the given address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24a9d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="24a9d-104">Syntax</span></span>  
  
```cpp  
HRESULT ClearUnmanagedBreakpoint (  
    [in] CORDB_ADDRESS   address  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="24a9d-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="24a9d-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="24a9d-106">de `CORDB_ADDRESS` valor que especifica la dirección en la que se estableció el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="24a9d-106">[in] A `CORDB_ADDRESS` value that specifies the address at which the breakpoint was set.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="24a9d-107">Notas</span><span class="sxs-lookup"><span data-stu-id="24a9d-107">Remarks</span></span>  
 <span data-ttu-id="24a9d-108">El punto de interrupción especificado se habría establecido previamente mediante una llamada anterior a [ICorDebugProcess2:: SetUnmanagedBreakpoint (](icordebugprocess2-setunmanagedbreakpoint-method.md).</span><span class="sxs-lookup"><span data-stu-id="24a9d-108">The specified breakpoint would have been previously set by an earlier call to [ICorDebugProcess2::SetUnmanagedBreakpoint](icordebugprocess2-setunmanagedbreakpoint-method.md).</span></span>  
  
 <span data-ttu-id="24a9d-109">Se puede llamar al método `ClearUnmanagedBreakpoint` mientras se está ejecutando el proceso que se está depurando.</span><span class="sxs-lookup"><span data-stu-id="24a9d-109">The `ClearUnmanagedBreakpoint` method can be called while the process being debugged is running.</span></span>  
  
 <span data-ttu-id="24a9d-110">El método `ClearUnmanagedBreakpoint` devuelve un código de error si el depurador está asociado en modo de solo administración o si no existe ningún punto de interrupción en la dirección especificada.</span><span class="sxs-lookup"><span data-stu-id="24a9d-110">The `ClearUnmanagedBreakpoint` method returns a failure code if the debugger is attached in managed-only mode or if no breakpoint exists at the specified address.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24a9d-111">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="24a9d-111">Requirements</span></span>  
 <span data-ttu-id="24a9d-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="24a9d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24a9d-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="24a9d-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="24a9d-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="24a9d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="24a9d-115">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24a9d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
