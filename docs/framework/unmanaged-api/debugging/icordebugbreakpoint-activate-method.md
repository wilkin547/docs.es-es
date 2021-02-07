---
description: 'Más información acerca de: ICorDebugBreakpoint:: Activate (método)'
title: ICorDebugBreakpoint::Activate (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugBreakpoint.Activate
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBreakpoint::Activate
helpviewer_keywords:
- ICorDebugBreakpoint::Activate method [.NET Framework debugging]
- Activate method [.NET Framework debugging]
ms.assetid: e30c29f7-3f19-4081-b572-a731aa14cd44
topic_type:
- apiref
ms.openlocfilehash: 1a3613ae071b3fc6c4f1005eafd515946d6b2685
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99711874"
---
# <a name="icordebugbreakpointactivate-method"></a><span data-ttu-id="1b811-103">ICorDebugBreakpoint::Activate (Método)</span><span class="sxs-lookup"><span data-stu-id="1b811-103">ICorDebugBreakpoint::Activate Method</span></span>

<span data-ttu-id="1b811-104">Establece el estado activo de este `ICorDebugBreakpoint` .</span><span class="sxs-lookup"><span data-stu-id="1b811-104">Sets the active state of this `ICorDebugBreakpoint`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b811-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1b811-105">Syntax</span></span>  
  
```cpp  
HRESULT Activate (  
    [in] BOOL bActive  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1b811-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1b811-106">Parameters</span></span>  

 `bActive`  
 <span data-ttu-id="1b811-107">de Establezca este valor en `true` para especificar el estado como activo; de lo contrario, establezca este valor en `false` .</span><span class="sxs-lookup"><span data-stu-id="1b811-107">[in] Set this value to `true` to specify the state as active; otherwise, set this value to `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b811-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1b811-108">Requirements</span></span>  

 <span data-ttu-id="1b811-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b811-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b811-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1b811-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1b811-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1b811-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1b811-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b811-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
