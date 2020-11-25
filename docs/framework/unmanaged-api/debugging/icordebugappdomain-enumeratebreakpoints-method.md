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
ms.openlocfilehash: 20c8a1987e48a88a3b8c92cf9f36fb58166cda9e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715991"
---
# <a name="icordebugappdomainenumeratebreakpoints-method"></a><span data-ttu-id="7f9e3-102">ICorDebugAppDomain::EnumerateBreakpoints (Método)</span><span class="sxs-lookup"><span data-stu-id="7f9e3-102">ICorDebugAppDomain::EnumerateBreakpoints Method</span></span>

<span data-ttu-id="7f9e3-103">Obtiene un enumerador para todos los puntos de interrupción activos en el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="7f9e3-103">Gets an enumerator for all active breakpoints in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f9e3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7f9e3-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateBreakpoints (  
    [out] ICorDebugBreakpointEnum   **ppBreakpoints  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7f9e3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7f9e3-105">Parameters</span></span>  

 `ppBreakpoints`  
 <span data-ttu-id="7f9e3-106">enuncia Puntero a la dirección de un objeto ICorDebugBreakpointEnum (que es el enumerador de todos los puntos de interrupción activos en el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="7f9e3-106">[out] A pointer to the address of an ICorDebugBreakpointEnum object that is the enumerator for all active breakpoints in the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7f9e3-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7f9e3-107">Remarks</span></span>  

 <span data-ttu-id="7f9e3-108">El enumerador incluye todos los tipos de puntos de interrupción, incluidos los puntos de interrupción de función y los puntos de interrupción de datos.</span><span class="sxs-lookup"><span data-stu-id="7f9e3-108">The enumerator includes all types of breakpoints, including function breakpoints and data breakpoints.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f9e3-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7f9e3-109">Requirements</span></span>  

 <span data-ttu-id="7f9e3-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7f9e3-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f9e3-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7f9e3-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7f9e3-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7f9e3-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7f9e3-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f9e3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
