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
ms.openlocfilehash: b00afc900a27aea94389ee81065ea22ae359440d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61996273"
---
# <a name="icordebugappdomainenumeratebreakpoints-method"></a><span data-ttu-id="6307d-102">ICorDebugAppDomain::EnumerateBreakpoints (Método)</span><span class="sxs-lookup"><span data-stu-id="6307d-102">ICorDebugAppDomain::EnumerateBreakpoints Method</span></span>
<span data-ttu-id="6307d-103">Obtiene un enumerador para todos los puntos de interrupción activos en el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="6307d-103">Gets an enumerator for all active breakpoints in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6307d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6307d-104">Syntax</span></span>  
  
```  
HRESULT EnumerateBreakpoints (  
    [out] ICorDebugBreakpointEnum   **ppBreakpoints  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6307d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6307d-105">Parameters</span></span>  
 `ppBreakpoints`  
 <span data-ttu-id="6307d-106">[out] Un puntero a la dirección de un objeto ICorDebugBreakpointEnum que es el enumerador de todos los puntos de interrupción activos en el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="6307d-106">[out] A pointer to the address of an ICorDebugBreakpointEnum object that is the enumerator for all active breakpoints in the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6307d-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6307d-107">Remarks</span></span>  
 <span data-ttu-id="6307d-108">El enumerador incluye todos los tipos de puntos de interrupción, incluidos los puntos de interrupción de función y los puntos de interrupción de datos.</span><span class="sxs-lookup"><span data-stu-id="6307d-108">The enumerator includes all types of breakpoints, including function breakpoints and data breakpoints.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6307d-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6307d-109">Requirements</span></span>  
 <span data-ttu-id="6307d-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6307d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6307d-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6307d-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6307d-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6307d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6307d-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6307d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
