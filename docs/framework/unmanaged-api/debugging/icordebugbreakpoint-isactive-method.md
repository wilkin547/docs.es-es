---
title: "ICorDebugBreakpoint::IsActive (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugBreakpoint.IsActive
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugBreakpoint::IsActive
helpviewer_keywords:
- ICorDebugBreakpoint::IsActive method [.NET Framework debugging]
- IsActive method, ICorDebugBreakpoint interface [.NET Framework debugging]
ms.assetid: 06e583d6-d88a-4ff5-bb95-5c48618a461c
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ebb5c448da6a2ff47bc7c2451c4270677eeb93a8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugbreakpointisactive-method"></a><span data-ttu-id="b6635-102">ICorDebugBreakpoint::IsActive (Método)</span><span class="sxs-lookup"><span data-stu-id="b6635-102">ICorDebugBreakpoint::IsActive Method</span></span>
<span data-ttu-id="b6635-103">Obtiene un valor que indica si este `ICorDebugBreakpoint` está activo.</span><span class="sxs-lookup"><span data-stu-id="b6635-103">Gets a value that indicates whether this `ICorDebugBreakpoint` is active.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6635-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b6635-104">Syntax</span></span>  
  
```  
HRESULT IsActive (  
    [out] BOOL *pbActive  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b6635-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b6635-105">Parameters</span></span>  
 `pbActive`  
 <span data-ttu-id="b6635-106">[out] `true` si este punto de interrupción está activo; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="b6635-106">[out] `true` if this breakpoint is active; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6635-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b6635-107">Requirements</span></span>  
 <span data-ttu-id="b6635-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b6635-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6635-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b6635-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b6635-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b6635-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b6635-111">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6635-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
