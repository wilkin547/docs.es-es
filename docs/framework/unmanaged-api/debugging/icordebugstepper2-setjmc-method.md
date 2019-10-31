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
ms.openlocfilehash: 6c076dd2912a22e4f9492492a2d7a9fb73db88e8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139037"
---
# <a name="icordebugstepper2setjmc-method"></a><span data-ttu-id="e43db-102">ICorDebugStepper2::SetJMC (Método)</span><span class="sxs-lookup"><span data-stu-id="e43db-102">ICorDebugStepper2::SetJMC Method</span></span>
<span data-ttu-id="e43db-103">Establece un valor que especifica si esta ICorDebugStepper solo se realiza a través del código creado por el desarrollador de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="e43db-103">Sets a value that specifies whether this ICorDebugStepper steps only through code that is authored by an application's developer.</span></span> <span data-ttu-id="e43db-104">Este proceso también se conoce como depuración solo mi código (JMC).</span><span class="sxs-lookup"><span data-stu-id="e43db-104">This process is also known as just my code (JMC) debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e43db-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e43db-105">Syntax</span></span>  
  
```cpp  
HRESULT SetJMC (  
    [in] BOOL    fIsJMCStepper  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e43db-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e43db-106">Parameters</span></span>  
 `fIsJMCStepper`  
 <span data-ttu-id="e43db-107">de Se establece en `true` para el paso solo a través del código creado por el desarrollador de una aplicación. de lo contrario, establézcalo en `false`.</span><span class="sxs-lookup"><span data-stu-id="e43db-107">[in] Set to `true` to step only through code that is authored by an application's developer; otherwise, set to `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e43db-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e43db-108">Requirements</span></span>  
 <span data-ttu-id="e43db-109">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e43db-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e43db-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e43db-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e43db-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e43db-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e43db-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e43db-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
