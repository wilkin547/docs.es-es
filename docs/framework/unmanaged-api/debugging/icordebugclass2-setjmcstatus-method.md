---
title: "ICorDebugClass2::SetJMCStatus (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugClass2.SetJMCStatus
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugClass2::SetJMCStatus
helpviewer_keywords:
- ICorDebugClass2::SetJMCStatus method [.NET Framework debugging]
- SetJMCStatus method, ICorDebugClass2 interface [.NET Framework debugging]
ms.assetid: 077e6c7f-f857-480c-bebb-76ee1de4e8fc
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5fa9de4482b674173dba6a8316491507330f6376
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugclass2setjmcstatus-method"></a><span data-ttu-id="5e279-102">ICorDebugClass2::SetJMCStatus (Método)</span><span class="sxs-lookup"><span data-stu-id="5e279-102">ICorDebugClass2::SetJMCStatus Method</span></span>
<span data-ttu-id="5e279-103">Para cada método de la clase, establece un valor que indica si el método es código definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="5e279-103">For each method of the class, sets a value that indicates whether the method is user-defined code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e279-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5e279-104">Syntax</span></span>  
  
```  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5e279-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5e279-105">Parameters</span></span>  
 `bIsJustMyCode`  
 <span data-ttu-id="5e279-106">[in] Establecido en `true` para indicar que el método es definido por el usuario de código; en caso contrario, establézcalo en `false`.</span><span class="sxs-lookup"><span data-stu-id="5e279-106">[in] Set to `true` to indicate that the method is user-defined code; otherwise, set to `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5e279-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5e279-107">Remarks</span></span>  
 <span data-ttu-id="5e279-108">Un paso a paso desencadene solo mi código ("JMC) omitirá el código no definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="5e279-108">A just-my-code (JMC) stepper will skip non-user-defined code.</span></span> <span data-ttu-id="5e279-109">Código definido por el usuario debe ser un subconjunto del código depurable.</span><span class="sxs-lookup"><span data-stu-id="5e279-109">User-defined code must be a subset of debuggable code.</span></span>  
  
 <span data-ttu-id="5e279-110">`SetJMCStatus`Devuelve un valor HRESULT de S_FALSE si no puede establecer el valor de cualquier método, incluso si establece correctamente el valor de todos los demás métodos.</span><span class="sxs-lookup"><span data-stu-id="5e279-110">`SetJMCStatus` returns an HRESULT value of S_FALSE if it fails to set the value for any method, even if it successfully sets the value for all other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e279-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5e279-111">Requirements</span></span>  
 <span data-ttu-id="5e279-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5e279-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e279-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5e279-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5e279-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5e279-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5e279-115">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e279-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
