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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f4dcfb977f5ca87f2219fd3ed8ef87d16c2defd2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61948985"
---
# <a name="icordebugprocess2clearunmanagedbreakpoint-method"></a><span data-ttu-id="28ddf-102">ICorDebugProcess2::ClearUnmanagedBreakpoint (Método)</span><span class="sxs-lookup"><span data-stu-id="28ddf-102">ICorDebugProcess2::ClearUnmanagedBreakpoint Method</span></span>
<span data-ttu-id="28ddf-103">Quita establecida previamente un punto de interrupción en la dirección indicada.</span><span class="sxs-lookup"><span data-stu-id="28ddf-103">Removes a previously set breakpoint at the given address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28ddf-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="28ddf-104">Syntax</span></span>  
  
```  
HRESULT ClearUnmanagedBreakpoint (  
    [in] CORDB_ADDRESS   address  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="28ddf-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="28ddf-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="28ddf-106">[in] Un `CORDB_ADDRESS` valor que especifica la dirección en la que se estableció el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="28ddf-106">[in] A `CORDB_ADDRESS` value that specifies the address at which the breakpoint was set.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="28ddf-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="28ddf-107">Remarks</span></span>  
 <span data-ttu-id="28ddf-108">El punto de interrupción especificado se habría establecido previamente mediante una llamada anterior a [ICorDebugProcess2:: SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md).</span><span class="sxs-lookup"><span data-stu-id="28ddf-108">The specified breakpoint would have been previously set by an earlier call to [ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md).</span></span>  
  
 <span data-ttu-id="28ddf-109">El `ClearUnmanagedBreakpoint` puede llamarse al método mientras se está ejecutando el proceso que se está depurando.</span><span class="sxs-lookup"><span data-stu-id="28ddf-109">The `ClearUnmanagedBreakpoint` method can be called while the process being debugged is running.</span></span>  
  
 <span data-ttu-id="28ddf-110">El `ClearUnmanagedBreakpoint` método devuelve un código de error si el depurador se adjunta en modo de solo administrados o si no existe ningún punto de interrupción en la dirección especificada.</span><span class="sxs-lookup"><span data-stu-id="28ddf-110">The `ClearUnmanagedBreakpoint` method returns a failure code if the debugger is attached in managed-only mode or if no breakpoint exists at the specified address.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28ddf-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="28ddf-111">Requirements</span></span>  
 <span data-ttu-id="28ddf-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="28ddf-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28ddf-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="28ddf-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="28ddf-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="28ddf-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="28ddf-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28ddf-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
