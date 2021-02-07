---
description: 'Más información sobre: ICorDebugProcess2:: ClearUnmanagedBreakpoint ((método)'
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
ms.openlocfilehash: fba31a479e9bac525109e14c02995e78918d4c17
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99746638"
---
# <a name="icordebugprocess2clearunmanagedbreakpoint-method"></a><span data-ttu-id="dde7b-103">ICorDebugProcess2::ClearUnmanagedBreakpoint (Método)</span><span class="sxs-lookup"><span data-stu-id="dde7b-103">ICorDebugProcess2::ClearUnmanagedBreakpoint Method</span></span>

<span data-ttu-id="dde7b-104">Quita un punto de interrupción establecido previamente en la dirección especificada.</span><span class="sxs-lookup"><span data-stu-id="dde7b-104">Removes a previously set breakpoint at the given address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dde7b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dde7b-105">Syntax</span></span>  
  
```cpp  
HRESULT ClearUnmanagedBreakpoint (  
    [in] CORDB_ADDRESS   address  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dde7b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="dde7b-106">Parameters</span></span>  

 `address`  
 <span data-ttu-id="dde7b-107">de `CORDB_ADDRESS` Valor que especifica la dirección en la que se estableció el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="dde7b-107">[in] A `CORDB_ADDRESS` value that specifies the address at which the breakpoint was set.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dde7b-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="dde7b-108">Remarks</span></span>  

 <span data-ttu-id="dde7b-109">El punto de interrupción especificado se habría establecido previamente mediante una llamada anterior a [ICorDebugProcess2:: SetUnmanagedBreakpoint (](icordebugprocess2-setunmanagedbreakpoint-method.md).</span><span class="sxs-lookup"><span data-stu-id="dde7b-109">The specified breakpoint would have been previously set by an earlier call to [ICorDebugProcess2::SetUnmanagedBreakpoint](icordebugprocess2-setunmanagedbreakpoint-method.md).</span></span>  
  
 <span data-ttu-id="dde7b-110">Se `ClearUnmanagedBreakpoint` puede llamar al método mientras se está ejecutando el proceso que se está depurando.</span><span class="sxs-lookup"><span data-stu-id="dde7b-110">The `ClearUnmanagedBreakpoint` method can be called while the process being debugged is running.</span></span>  
  
 <span data-ttu-id="dde7b-111">El `ClearUnmanagedBreakpoint` método devuelve un código de error si el depurador está asociado en modo de solo administración o si no existe ningún punto de interrupción en la dirección especificada.</span><span class="sxs-lookup"><span data-stu-id="dde7b-111">The `ClearUnmanagedBreakpoint` method returns a failure code if the debugger is attached in managed-only mode or if no breakpoint exists at the specified address.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dde7b-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dde7b-112">Requirements</span></span>  

 <span data-ttu-id="dde7b-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dde7b-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dde7b-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dde7b-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dde7b-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dde7b-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dde7b-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dde7b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
