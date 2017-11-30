---
title: "ICorDebugStepper2::SetJMC (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStepper2.SetJMC
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStepper2::SetJMC
helpviewer_keywords:
- ICorDebugStepper2::SetJMC method [.NET Framework debugging]
- SetJMC method [.NET Framework debugging]
ms.assetid: f5cdc135-6db4-4b32-9dd1-260ec58b774f
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4b34e0d612957da1ec1ca3535bfa1a0d7a5bae5f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugstepper2setjmc-method"></a><span data-ttu-id="3f6a3-102">ICorDebugStepper2::SetJMC (Método)</span><span class="sxs-lookup"><span data-stu-id="3f6a3-102">ICorDebugStepper2::SetJMC Method</span></span>
<span data-ttu-id="3f6a3-103">Establece un valor que especifica si este ICorDebugStepper recorre paso a paso solo código creado por el desarrollador de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="3f6a3-103">Sets a value that specifies whether this ICorDebugStepper steps only through code that is authored by an application's developer.</span></span> <span data-ttu-id="3f6a3-104">Este proceso también se conoce como depuración mi código ("JMC).</span><span class="sxs-lookup"><span data-stu-id="3f6a3-104">This process is also known as just my code (JMC) debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f6a3-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3f6a3-105">Syntax</span></span>  
  
```  
HRESULT SetJMC (  
    [in] BOOL    fIsJMCStepper  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3f6a3-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3f6a3-106">Parameters</span></span>  
 `fIsJMCStepper`  
 <span data-ttu-id="3f6a3-107">[in] Establecido en `true` al paso solo a través de código que es creado por el desarrollador de la aplicación; en caso contrario, establézcalo en `false`.</span><span class="sxs-lookup"><span data-stu-id="3f6a3-107">[in] Set to `true` to step only through code that is authored by an application's developer; otherwise, set to `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f6a3-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3f6a3-108">Requirements</span></span>  
 <span data-ttu-id="3f6a3-109">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3f6a3-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f6a3-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3f6a3-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3f6a3-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3f6a3-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3f6a3-112">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f6a3-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
