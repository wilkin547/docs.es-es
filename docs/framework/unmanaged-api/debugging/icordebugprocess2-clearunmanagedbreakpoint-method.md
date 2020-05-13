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
ms.openlocfilehash: 2b228383c3b393fe43f60d39e59cca37af36233f
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212499"
---
# <a name="icordebugprocess2clearunmanagedbreakpoint-method"></a><span data-ttu-id="2d1fc-102">ICorDebugProcess2::ClearUnmanagedBreakpoint (Método)</span><span class="sxs-lookup"><span data-stu-id="2d1fc-102">ICorDebugProcess2::ClearUnmanagedBreakpoint Method</span></span>
<span data-ttu-id="2d1fc-103">Quita un punto de interrupción establecido previamente en la dirección especificada.</span><span class="sxs-lookup"><span data-stu-id="2d1fc-103">Removes a previously set breakpoint at the given address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d1fc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2d1fc-104">Syntax</span></span>  
  
```cpp  
HRESULT ClearUnmanagedBreakpoint (  
    [in] CORDB_ADDRESS   address  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2d1fc-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2d1fc-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="2d1fc-106">de `CORDB_ADDRESS`Valor que especifica la dirección en la que se estableció el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="2d1fc-106">[in] A `CORDB_ADDRESS` value that specifies the address at which the breakpoint was set.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2d1fc-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2d1fc-107">Remarks</span></span>  
 <span data-ttu-id="2d1fc-108">El punto de interrupción especificado se habría establecido previamente mediante una llamada anterior a [ICorDebugProcess2:: SetUnmanagedBreakpoint (](icordebugprocess2-setunmanagedbreakpoint-method.md).</span><span class="sxs-lookup"><span data-stu-id="2d1fc-108">The specified breakpoint would have been previously set by an earlier call to [ICorDebugProcess2::SetUnmanagedBreakpoint](icordebugprocess2-setunmanagedbreakpoint-method.md).</span></span>  
  
 <span data-ttu-id="2d1fc-109">Se `ClearUnmanagedBreakpoint` puede llamar al método mientras se está ejecutando el proceso que se está depurando.</span><span class="sxs-lookup"><span data-stu-id="2d1fc-109">The `ClearUnmanagedBreakpoint` method can be called while the process being debugged is running.</span></span>  
  
 <span data-ttu-id="2d1fc-110">El `ClearUnmanagedBreakpoint` método devuelve un código de error si el depurador está asociado en modo de solo administración o si no existe ningún punto de interrupción en la dirección especificada.</span><span class="sxs-lookup"><span data-stu-id="2d1fc-110">The `ClearUnmanagedBreakpoint` method returns a failure code if the debugger is attached in managed-only mode or if no breakpoint exists at the specified address.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d1fc-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2d1fc-111">Requirements</span></span>  
 <span data-ttu-id="2d1fc-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2d1fc-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d1fc-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2d1fc-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2d1fc-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2d1fc-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2d1fc-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d1fc-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
