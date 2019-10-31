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
ms.openlocfilehash: 3611684a17d51fc4fdba31dd4049540039b43e8b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73110523"
---
# <a name="icordebugappdomainenumeratebreakpoints-method"></a><span data-ttu-id="7c8e9-102">ICorDebugAppDomain::EnumerateBreakpoints (Método)</span><span class="sxs-lookup"><span data-stu-id="7c8e9-102">ICorDebugAppDomain::EnumerateBreakpoints Method</span></span>
<span data-ttu-id="7c8e9-103">Obtiene un enumerador para todos los puntos de interrupción activos en el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="7c8e9-103">Gets an enumerator for all active breakpoints in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c8e9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7c8e9-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateBreakpoints (  
    [out] ICorDebugBreakpointEnum   **ppBreakpoints  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7c8e9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7c8e9-105">Parameters</span></span>  
 `ppBreakpoints`  
 <span data-ttu-id="7c8e9-106">enuncia Puntero a la dirección de un objeto ICorDebugBreakpointEnum (que es el enumerador de todos los puntos de interrupción activos en el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="7c8e9-106">[out] A pointer to the address of an ICorDebugBreakpointEnum object that is the enumerator for all active breakpoints in the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7c8e9-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7c8e9-107">Remarks</span></span>  
 <span data-ttu-id="7c8e9-108">El enumerador incluye todos los tipos de puntos de interrupción, incluidos los puntos de interrupción de función y los puntos de interrupción de datos.</span><span class="sxs-lookup"><span data-stu-id="7c8e9-108">The enumerator includes all types of breakpoints, including function breakpoints and data breakpoints.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c8e9-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7c8e9-109">Requirements</span></span>  
 <span data-ttu-id="7c8e9-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c8e9-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c8e9-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7c8e9-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7c8e9-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7c8e9-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7c8e9-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c8e9-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
