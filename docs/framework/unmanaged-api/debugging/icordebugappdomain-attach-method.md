---
title: ICorDebugAppDomain::Attach (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.Attach
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::Attach
helpviewer_keywords:
- ICorDebugAppDomain::Attach method [.NET Framework debugging]
- Attach method [.NET Framework debugging]
ms.assetid: 0358b84a-4236-4c34-945b-4babff7df570
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9d30b6cb083cc2f92bcbe089bf8e990fedd8e8f7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67738095"
---
# <a name="icordebugappdomainattach-method"></a><span data-ttu-id="efa83-102">ICorDebugAppDomain::Attach (Método)</span><span class="sxs-lookup"><span data-stu-id="efa83-102">ICorDebugAppDomain::Attach Method</span></span>
<span data-ttu-id="efa83-103">Asocia al depurador al dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="efa83-103">Attaches the debugger to the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efa83-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="efa83-104">Syntax</span></span>  
  
```cpp  
HRESULT Attach ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="efa83-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="efa83-105">Remarks</span></span>  
 <span data-ttu-id="efa83-106">El depurador debe asociarse al dominio de aplicación para recibir eventos y para habilitar la depuración del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="efa83-106">The debugger must be attached to the application domain to receive events and to enable debugging of the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="efa83-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="efa83-107">Requirements</span></span>  
 <span data-ttu-id="efa83-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="efa83-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="efa83-109">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="efa83-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="efa83-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="efa83-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="efa83-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="efa83-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
