---
title: ICorDebugExceptionObjectValue (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugExceptionObjectValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugExceptionObjectValue
helpviewer_keywords: ICorDebugExceptionObjectValue interface [.NET Framework debugging]
ms.assetid: 43416dd5-8892-4106-9f59-f9143b19ddb4
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 47733a6af18d42d0d9db1e50cf21646289ef1443
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugexceptionobjectvalue-interface"></a><span data-ttu-id="dd00e-102">ICorDebugExceptionObjectValue (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="dd00e-102">ICorDebugExceptionObjectValue Interface</span></span>
<span data-ttu-id="dd00e-103">Extiende la interfaz "ICorDebugObjectValue" para proporcionar información de seguimiento de pila de un objeto de excepción administrada.</span><span class="sxs-lookup"><span data-stu-id="dd00e-103">Extends the "ICorDebugObjectValue" interface to provide stack trace information from a managed exception object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="dd00e-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="dd00e-104">Methods</span></span>  
  
|<span data-ttu-id="dd00e-105">Método</span><span class="sxs-lookup"><span data-stu-id="dd00e-105">Method</span></span>|<span data-ttu-id="dd00e-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="dd00e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="dd00e-107">EnumerateExceptionCallStack (método)</span><span class="sxs-lookup"><span data-stu-id="dd00e-107">EnumerateExceptionCallStack Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md)|<span data-ttu-id="dd00e-108">Obtiene un enumerador para la pila de llamadas que se incrustan en un objeto de excepción.</span><span class="sxs-lookup"><span data-stu-id="dd00e-108">Gets an enumerator to the call stack embedded in an exception object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dd00e-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="dd00e-109">Remarks</span></span>  
 <span data-ttu-id="dd00e-110">La llamada a `QueryInterface` se realizará correctamente para objetos administrados que se derivan de <xref:System.Exception?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="dd00e-110">The call to `QueryInterface` will succeed for managed objects that derive from <xref:System.Exception?displayProperty=nameWithType>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd00e-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dd00e-111">Requirements</span></span>  
 <span data-ttu-id="dd00e-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dd00e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd00e-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dd00e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dd00e-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dd00e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dd00e-115">**Versiones de .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd00e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd00e-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="dd00e-116">See Also</span></span>  
 [<span data-ttu-id="dd00e-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="dd00e-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="dd00e-118">Depuración</span><span class="sxs-lookup"><span data-stu-id="dd00e-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)  
 
