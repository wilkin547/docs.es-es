---
title: ICorDebugClass2::SetJMCStatus (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugClass2.SetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass2::SetJMCStatus
helpviewer_keywords:
- ICorDebugClass2::SetJMCStatus method [.NET Framework debugging]
- SetJMCStatus method, ICorDebugClass2 interface [.NET Framework debugging]
ms.assetid: 077e6c7f-f857-480c-bebb-76ee1de4e8fc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6ed6570e11008e52d4b1f97c2dc90e2ccbef2e35
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471392"
---
# <a name="icordebugclass2setjmcstatus-method"></a><span data-ttu-id="b4f58-102">ICorDebugClass2::SetJMCStatus (Método)</span><span class="sxs-lookup"><span data-stu-id="b4f58-102">ICorDebugClass2::SetJMCStatus Method</span></span>
<span data-ttu-id="b4f58-103">Para cada método de la clase, establece un valor que indica si el método es código definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="b4f58-103">For each method of the class, sets a value that indicates whether the method is user-defined code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4f58-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b4f58-104">Syntax</span></span>  
  
```  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b4f58-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b4f58-105">Parameters</span></span>  
 `bIsJustMyCode`  
 <span data-ttu-id="b4f58-106">[in] Establecido en `true` para indicar que el método está definido por el usuario de código; de lo contrario, establézcalo en `false`.</span><span class="sxs-lookup"><span data-stu-id="b4f58-106">[in] Set to `true` to indicate that the method is user-defined code; otherwise, set to `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b4f58-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b4f58-107">Remarks</span></span>  
 <span data-ttu-id="b4f58-108">Un motor paso a paso solo mi código (JMC) omitirá el código no definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="b4f58-108">A just-my-code (JMC) stepper will skip non-user-defined code.</span></span> <span data-ttu-id="b4f58-109">Código definido por el usuario debe ser un subconjunto del código depurable.</span><span class="sxs-lookup"><span data-stu-id="b4f58-109">User-defined code must be a subset of debuggable code.</span></span>  
  
 <span data-ttu-id="b4f58-110">`SetJMCStatus` Devuelve un valor HRESULT de S_FALSE si no se establezca el valor de cualquier método, incluso si establece correctamente el valor para todos los demás métodos.</span><span class="sxs-lookup"><span data-stu-id="b4f58-110">`SetJMCStatus` returns an HRESULT value of S_FALSE if it fails to set the value for any method, even if it successfully sets the value for all other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4f58-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b4f58-111">Requirements</span></span>  
 <span data-ttu-id="b4f58-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4f58-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4f58-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b4f58-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b4f58-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b4f58-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b4f58-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4f58-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
