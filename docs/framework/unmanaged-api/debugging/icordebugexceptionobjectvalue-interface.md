---
title: ICorDebugExceptionObjectValue (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugExceptionObjectValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugExceptionObjectValue
helpviewer_keywords:
- ICorDebugExceptionObjectValue interface [.NET Framework debugging]
ms.assetid: 43416dd5-8892-4106-9f59-f9143b19ddb4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b5328442ceaee05b3f81466b785f04a361d456a8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61995922"
---
# <a name="icordebugexceptionobjectvalue-interface"></a><span data-ttu-id="08b71-102">ICorDebugExceptionObjectValue (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="08b71-102">ICorDebugExceptionObjectValue Interface</span></span>
<span data-ttu-id="08b71-103">Extiende la interfaz "ICorDebugObjectValue" para proporcionar información de seguimiento de pila de un objeto de excepción administrado.</span><span class="sxs-lookup"><span data-stu-id="08b71-103">Extends the "ICorDebugObjectValue" interface to provide stack trace information from a managed exception object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="08b71-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="08b71-104">Methods</span></span>  
  
|<span data-ttu-id="08b71-105">Método</span><span class="sxs-lookup"><span data-stu-id="08b71-105">Method</span></span>|<span data-ttu-id="08b71-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="08b71-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="08b71-107">EnumerateExceptionCallStack (método)</span><span class="sxs-lookup"><span data-stu-id="08b71-107">EnumerateExceptionCallStack Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md)|<span data-ttu-id="08b71-108">Obtiene un enumerador para la pila de llamadas incrustada en un objeto de excepción.</span><span class="sxs-lookup"><span data-stu-id="08b71-108">Gets an enumerator to the call stack embedded in an exception object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="08b71-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="08b71-109">Remarks</span></span>  
 <span data-ttu-id="08b71-110">La llamada a `QueryInterface` surtirá efecto para objetos administrados que se derivan de <xref:System.Exception?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="08b71-110">The call to `QueryInterface` will succeed for managed objects that derive from <xref:System.Exception?displayProperty=nameWithType>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08b71-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="08b71-111">Requirements</span></span>  
 <span data-ttu-id="08b71-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08b71-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08b71-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="08b71-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="08b71-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="08b71-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="08b71-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08b71-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08b71-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="08b71-116">See also</span></span>

- [<span data-ttu-id="08b71-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="08b71-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="08b71-118">Depuración</span><span class="sxs-lookup"><span data-stu-id="08b71-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
