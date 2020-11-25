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
ms.openlocfilehash: 1db2c9b5e65ae150f05242172f5ea16db433bbb5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717830"
---
# <a name="icordebugclass2setjmcstatus-method"></a><span data-ttu-id="cf016-102">ICorDebugClass2::SetJMCStatus (Método)</span><span class="sxs-lookup"><span data-stu-id="cf016-102">ICorDebugClass2::SetJMCStatus Method</span></span>

<span data-ttu-id="cf016-103">Para cada método de la clase, establece un valor que indica si el método es código definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="cf016-103">For each method of the class, sets a value that indicates whether the method is user-defined code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf016-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cf016-104">Syntax</span></span>  
  
```cpp  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cf016-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cf016-105">Parameters</span></span>  

 `bIsJustMyCode`  
 <span data-ttu-id="cf016-106">de Se establece en `true` para indicar que el método es código definido por el usuario; de lo contrario, se establece en `false` .</span><span class="sxs-lookup"><span data-stu-id="cf016-106">[in] Set to `true` to indicate that the method is user-defined code; otherwise, set to `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cf016-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cf016-107">Remarks</span></span>  

 <span data-ttu-id="cf016-108">Un stepper de solo mi código (JMC) omitirá el código no definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="cf016-108">A just-my-code (JMC) stepper will skip non-user-defined code.</span></span> <span data-ttu-id="cf016-109">El código definido por el usuario debe ser un subconjunto del código depurable.</span><span class="sxs-lookup"><span data-stu-id="cf016-109">User-defined code must be a subset of debuggable code.</span></span>  
  
 <span data-ttu-id="cf016-110">`SetJMCStatus` Devuelve un valor HRESULT de S_FALSE si no puede establecer el valor para ningún método, aunque establezca correctamente el valor de todos los demás métodos.</span><span class="sxs-lookup"><span data-stu-id="cf016-110">`SetJMCStatus` returns an HRESULT value of S_FALSE if it fails to set the value for any method, even if it successfully sets the value for all other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf016-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cf016-111">Requirements</span></span>  

 <span data-ttu-id="cf016-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf016-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf016-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cf016-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cf016-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cf016-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cf016-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf016-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
