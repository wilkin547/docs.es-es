---
title: ICorDebugAppDomain::EnumerateBreakpoints (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.EnumerateBreakpoints
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::EnumerateBreakpoints
helpviewer_keywords:
- ICorDebugAppDomain::EnumerateBreakpoints method [.NET Framework debugging]
- EnumerateBreakpoints method [.NET Framework debugging]
ms.assetid: 206069c5-25cb-4794-9d69-67c5aa7ed0af
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a683f1531ed28fbd8ef085414bb7cb365762ffde
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67738042"
---
# <a name="icordebugappdomainenumeratebreakpoints-method"></a><span data-ttu-id="e7cda-102">ICorDebugAppDomain::EnumerateBreakpoints (Método)</span><span class="sxs-lookup"><span data-stu-id="e7cda-102">ICorDebugAppDomain::EnumerateBreakpoints Method</span></span>
<span data-ttu-id="e7cda-103">Obtiene un enumerador para todos los puntos de interrupción activos en el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="e7cda-103">Gets an enumerator for all active breakpoints in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7cda-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e7cda-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateBreakpoints (  
    [out] ICorDebugBreakpointEnum   **ppBreakpoints  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e7cda-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e7cda-105">Parameters</span></span>  
 `ppBreakpoints`  
 <span data-ttu-id="e7cda-106">[out] Un puntero a la dirección de un objeto ICorDebugBreakpointEnum que es el enumerador de todos los puntos de interrupción activos en el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="e7cda-106">[out] A pointer to the address of an ICorDebugBreakpointEnum object that is the enumerator for all active breakpoints in the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e7cda-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e7cda-107">Remarks</span></span>  
 <span data-ttu-id="e7cda-108">El enumerador incluye todos los tipos de puntos de interrupción, incluidos los puntos de interrupción de función y los puntos de interrupción de datos.</span><span class="sxs-lookup"><span data-stu-id="e7cda-108">The enumerator includes all types of breakpoints, including function breakpoints and data breakpoints.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7cda-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e7cda-109">Requirements</span></span>  
 <span data-ttu-id="e7cda-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e7cda-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7cda-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e7cda-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e7cda-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e7cda-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e7cda-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7cda-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
