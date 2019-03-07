---
title: ICorDebugStepper2::SetJMC (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugStepper2.SetJMC
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper2::SetJMC
helpviewer_keywords:
- ICorDebugStepper2::SetJMC method [.NET Framework debugging]
- SetJMC method [.NET Framework debugging]
ms.assetid: f5cdc135-6db4-4b32-9dd1-260ec58b774f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 129bf04a097b2019b080f813bf049d41b501f8fd
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57474220"
---
# <a name="icordebugstepper2setjmc-method"></a><span data-ttu-id="7e1af-102">ICorDebugStepper2::SetJMC (Método)</span><span class="sxs-lookup"><span data-stu-id="7e1af-102">ICorDebugStepper2::SetJMC Method</span></span>
<span data-ttu-id="7e1af-103">Establece un valor que especifica si los pasos de este ICorDebugStepper únicamente a través del código creado por el desarrollador de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="7e1af-103">Sets a value that specifies whether this ICorDebugStepper steps only through code that is authored by an application's developer.</span></span> <span data-ttu-id="7e1af-104">Este proceso también se conoce como depuración mi código (JMC).</span><span class="sxs-lookup"><span data-stu-id="7e1af-104">This process is also known as just my code (JMC) debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e1af-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7e1af-105">Syntax</span></span>  
  
```  
HRESULT SetJMC (  
    [in] BOOL    fIsJMCStepper  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7e1af-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7e1af-106">Parameters</span></span>  
 `fIsJMCStepper`  
 <span data-ttu-id="7e1af-107">[in] Establecido en `true` al paso únicamente a través de código que es creado por el desarrollador de la aplicación; en caso contrario, establézcalo en `false`.</span><span class="sxs-lookup"><span data-stu-id="7e1af-107">[in] Set to `true` to step only through code that is authored by an application's developer; otherwise, set to `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e1af-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7e1af-108">Requirements</span></span>  
 <span data-ttu-id="7e1af-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7e1af-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e1af-110">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7e1af-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7e1af-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7e1af-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7e1af-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e1af-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
