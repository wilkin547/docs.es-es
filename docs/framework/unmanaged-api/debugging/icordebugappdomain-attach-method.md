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
ms.openlocfilehash: a290ca162e5ab71b4184d166bcd00f1d0217cb94
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402501"
---
# <a name="icordebugappdomainattach-method"></a><span data-ttu-id="a083a-102">ICorDebugAppDomain::Attach (Método)</span><span class="sxs-lookup"><span data-stu-id="a083a-102">ICorDebugAppDomain::Attach Method</span></span>
<span data-ttu-id="a083a-103">Asocia al depurador al dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="a083a-103">Attaches the debugger to the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a083a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a083a-104">Syntax</span></span>  
  
```  
HRESULT Attach ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="a083a-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a083a-105">Remarks</span></span>  
 <span data-ttu-id="a083a-106">El depurador debe asociarse al dominio de aplicación para recibir eventos y para habilitar la depuración del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="a083a-106">The debugger must be attached to the application domain to receive events and to enable debugging of the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a083a-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a083a-107">Requirements</span></span>  
 <span data-ttu-id="a083a-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a083a-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a083a-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a083a-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a083a-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a083a-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a083a-111">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a083a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
