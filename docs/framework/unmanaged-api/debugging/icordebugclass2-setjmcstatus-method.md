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
ms.openlocfilehash: 9fb2f960098e970b4d3d9f0be499f4d9fda6558e
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "82893898"
---
# <a name="icordebugclass2setjmcstatus-method"></a><span data-ttu-id="d1166-102">ICorDebugClass2::SetJMCStatus (Método)</span><span class="sxs-lookup"><span data-stu-id="d1166-102">ICorDebugClass2::SetJMCStatus Method</span></span>
<span data-ttu-id="d1166-103">Para cada método de la clase, establece un valor que indica si el método es código definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="d1166-103">For each method of the class, sets a value that indicates whether the method is user-defined code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1166-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d1166-104">Syntax</span></span>  
  
```cpp  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d1166-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d1166-105">Parameters</span></span>  
 `bIsJustMyCode`  
 <span data-ttu-id="d1166-106">de Se establece `true` en para indicar que el método es código definido por el usuario; en caso contrario, `false`establezca en.</span><span class="sxs-lookup"><span data-stu-id="d1166-106">[in] Set to `true` to indicate that the method is user-defined code; otherwise, set to `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d1166-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d1166-107">Remarks</span></span>  
 <span data-ttu-id="d1166-108">Un stepper de solo mi código (JMC) omitirá el código no definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="d1166-108">A just-my-code (JMC) stepper will skip non-user-defined code.</span></span> <span data-ttu-id="d1166-109">El código definido por el usuario debe ser un subconjunto del código depurable.</span><span class="sxs-lookup"><span data-stu-id="d1166-109">User-defined code must be a subset of debuggable code.</span></span>  
  
 <span data-ttu-id="d1166-110">`SetJMCStatus`Devuelve un valor HRESULT de S_FALSE si no puede establecer el valor para ningún método, aunque establezca correctamente el valor de todos los demás métodos.</span><span class="sxs-lookup"><span data-stu-id="d1166-110">`SetJMCStatus` returns an HRESULT value of S_FALSE if it fails to set the value for any method, even if it successfully sets the value for all other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1166-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d1166-111">Requirements</span></span>  
 <span data-ttu-id="d1166-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d1166-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1166-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d1166-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d1166-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d1166-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d1166-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1166-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
