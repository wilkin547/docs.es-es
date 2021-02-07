---
description: 'Más información acerca de: ICorDebugBreakpoint:: IsActive (método)'
title: ICorDebugBreakpoint::IsActive (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugBreakpoint.IsActive
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBreakpoint::IsActive
helpviewer_keywords:
- ICorDebugBreakpoint::IsActive method [.NET Framework debugging]
- IsActive method, ICorDebugBreakpoint interface [.NET Framework debugging]
ms.assetid: 06e583d6-d88a-4ff5-bb95-5c48618a461c
topic_type:
- apiref
ms.openlocfilehash: 49e98ccc3722c37b3ff5968215ef3f658601ea10
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99711796"
---
# <a name="icordebugbreakpointisactive-method"></a><span data-ttu-id="67819-103">ICorDebugBreakpoint::IsActive (Método)</span><span class="sxs-lookup"><span data-stu-id="67819-103">ICorDebugBreakpoint::IsActive Method</span></span>

<span data-ttu-id="67819-104">Obtiene un valor que indica si este `ICorDebugBreakpoint` está activo.</span><span class="sxs-lookup"><span data-stu-id="67819-104">Gets a value that indicates whether this `ICorDebugBreakpoint` is active.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67819-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="67819-105">Syntax</span></span>  
  
```cpp  
HRESULT IsActive (  
    [out] BOOL *pbActive  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="67819-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="67819-106">Parameters</span></span>  

 `pbActive`  
 <span data-ttu-id="67819-107">[out] `true` Si este punto de interrupción está activo; en caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="67819-107">[out] `true` if this breakpoint is active; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67819-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="67819-108">Requirements</span></span>  

 <span data-ttu-id="67819-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67819-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67819-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="67819-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="67819-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="67819-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="67819-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67819-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
