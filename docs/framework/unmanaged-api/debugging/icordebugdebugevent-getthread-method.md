---
title: "Método ICorDebugDebugEvent::GetThread"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 4f2e9a2c-8369-4a07-a881-ad5422626353
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: faf1ace6c65f38e9a1d5b958b633c95dbcd3dcf8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugdebugeventgetthread-method"></a><span data-ttu-id="d8c24-102">Método ICorDebugDebugEvent::GetThread</span><span class="sxs-lookup"><span data-stu-id="d8c24-102">ICorDebugDebugEvent::GetThread Method</span></span>
<span data-ttu-id="d8c24-103">Obtiene el subproceso en el que se produjo el evento.</span><span class="sxs-lookup"><span data-stu-id="d8c24-103">Gets the thread on which the event occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8c24-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d8c24-104">Syntax</span></span>  
  
```  
HRESULT GetThread(  
        [out]ICorDebugThread **ppThread  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d8c24-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d8c24-105">Parameters</span></span>  
 <span data-ttu-id="d8c24-106">ppThread</span><span class="sxs-lookup"><span data-stu-id="d8c24-106">ppThread</span></span>  
 <span data-ttu-id="d8c24-107">[out] Un puntero a la dirección de un objeto ICorDebugThread que representa el subproceso en el que se produjo el evento.</span><span class="sxs-lookup"><span data-stu-id="d8c24-107">[out] A pointer to the address of an ICorDebugThread object that represents the thread on which the event occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d8c24-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d8c24-108">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d8c24-109">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="d8c24-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8c24-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d8c24-110">Requirements</span></span>  
 <span data-ttu-id="d8c24-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8c24-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8c24-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d8c24-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d8c24-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d8c24-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d8c24-114">**Versiones de .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8c24-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8c24-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="d8c24-115">See Also</span></span>  
 [<span data-ttu-id="d8c24-116">ICorDebugDebugEvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d8c24-116">ICorDebugDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)  
 [<span data-ttu-id="d8c24-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="d8c24-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
