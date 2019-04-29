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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61750623"
---
# <a name="icordebugclass2setjmcstatus-method"></a><span data-ttu-id="94a02-102">ICorDebugClass2::SetJMCStatus (Método)</span><span class="sxs-lookup"><span data-stu-id="94a02-102">ICorDebugClass2::SetJMCStatus Method</span></span>
<span data-ttu-id="94a02-103">Para cada método de la clase, establece un valor que indica si el método es código definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="94a02-103">For each method of the class, sets a value that indicates whether the method is user-defined code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94a02-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="94a02-104">Syntax</span></span>  
  
```  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="94a02-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="94a02-105">Parameters</span></span>  
 `bIsJustMyCode`  
 <span data-ttu-id="94a02-106">[in] Establecido en `true` para indicar que el método está definido por el usuario de código; de lo contrario, establézcalo en `false`.</span><span class="sxs-lookup"><span data-stu-id="94a02-106">[in] Set to `true` to indicate that the method is user-defined code; otherwise, set to `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="94a02-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="94a02-107">Remarks</span></span>  
 <span data-ttu-id="94a02-108">Un motor paso a paso solo mi código (JMC) omitirá el código no definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="94a02-108">A just-my-code (JMC) stepper will skip non-user-defined code.</span></span> <span data-ttu-id="94a02-109">Código definido por el usuario debe ser un subconjunto del código depurable.</span><span class="sxs-lookup"><span data-stu-id="94a02-109">User-defined code must be a subset of debuggable code.</span></span>  
  
 <span data-ttu-id="94a02-110">`SetJMCStatus` Devuelve un valor HRESULT de S_FALSE si no se establezca el valor de cualquier método, incluso si establece correctamente el valor para todos los demás métodos.</span><span class="sxs-lookup"><span data-stu-id="94a02-110">`SetJMCStatus` returns an HRESULT value of S_FALSE if it fails to set the value for any method, even if it successfully sets the value for all other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94a02-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="94a02-111">Requirements</span></span>  
 <span data-ttu-id="94a02-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94a02-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94a02-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="94a02-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="94a02-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="94a02-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="94a02-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94a02-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
