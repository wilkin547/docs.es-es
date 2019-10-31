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
ms.openlocfilehash: a862dd3f6a9c10c6b3a5a0bb41208d351c4ca9f1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125693"
---
# <a name="icordebugclass2setjmcstatus-method"></a><span data-ttu-id="b885a-102">ICorDebugClass2::SetJMCStatus (Método)</span><span class="sxs-lookup"><span data-stu-id="b885a-102">ICorDebugClass2::SetJMCStatus Method</span></span>
<span data-ttu-id="b885a-103">Para cada método de la clase, establece un valor que indica si el método es código definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="b885a-103">For each method of the class, sets a value that indicates whether the method is user-defined code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b885a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b885a-104">Syntax</span></span>  
  
```cpp  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b885a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b885a-105">Parameters</span></span>  
 `bIsJustMyCode`  
 <span data-ttu-id="b885a-106">de Se establece en `true` para indicar que el método es código definido por el usuario; de lo contrario, establézcalo en `false`.</span><span class="sxs-lookup"><span data-stu-id="b885a-106">[in] Set to `true` to indicate that the method is user-defined code; otherwise, set to `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b885a-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b885a-107">Remarks</span></span>  
 <span data-ttu-id="b885a-108">Un stepper de solo mi código (JMC) omitirá el código no definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="b885a-108">A just-my-code (JMC) stepper will skip non-user-defined code.</span></span> <span data-ttu-id="b885a-109">El código definido por el usuario debe ser un subconjunto del código depurable.</span><span class="sxs-lookup"><span data-stu-id="b885a-109">User-defined code must be a subset of debuggable code.</span></span>  
  
 <span data-ttu-id="b885a-110">`SetJMCStatus` devuelve un valor HRESULT de S_FALSE si no puede establecer el valor para ningún método, aunque establezca correctamente el valor de todos los demás métodos.</span><span class="sxs-lookup"><span data-stu-id="b885a-110">`SetJMCStatus` returns an HRESULT value of S_FALSE if it fails to set the value for any method, even if it successfully sets the value for all other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b885a-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b885a-111">Requirements</span></span>  
 <span data-ttu-id="b885a-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b885a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b885a-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b885a-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b885a-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b885a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b885a-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b885a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
