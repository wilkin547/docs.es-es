---
description: 'Más información sobre: Icordebugstepper2 (:: Setjmc ((método)'
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
ms.openlocfilehash: 07178ab90bb392e64c9d8a8fddf961efbb268002
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99717542"
---
# <a name="icordebugstepper2setjmc-method"></a><span data-ttu-id="52178-103">ICorDebugStepper2::SetJMC (Método)</span><span class="sxs-lookup"><span data-stu-id="52178-103">ICorDebugStepper2::SetJMC Method</span></span>

<span data-ttu-id="52178-104">Establece un valor que especifica si esta ICorDebugStepper solo se realiza a través del código creado por el desarrollador de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="52178-104">Sets a value that specifies whether this ICorDebugStepper steps only through code that is authored by an application's developer.</span></span> <span data-ttu-id="52178-105">Este proceso también se conoce como depuración solo mi código (JMC).</span><span class="sxs-lookup"><span data-stu-id="52178-105">This process is also known as just my code (JMC) debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52178-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="52178-106">Syntax</span></span>  
  
```cpp  
HRESULT SetJMC (  
    [in] BOOL    fIsJMCStepper  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="52178-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="52178-107">Parameters</span></span>  

 `fIsJMCStepper`  
 <span data-ttu-id="52178-108">de Establezca en `true` para recorrer solo el código creado por el desarrollador de la aplicación; de lo contrario, establézcalo en `false` .</span><span class="sxs-lookup"><span data-stu-id="52178-108">[in] Set to `true` to step only through code that is authored by an application's developer; otherwise, set to `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52178-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="52178-109">Requirements</span></span>  

 <span data-ttu-id="52178-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="52178-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52178-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="52178-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="52178-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="52178-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="52178-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52178-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
