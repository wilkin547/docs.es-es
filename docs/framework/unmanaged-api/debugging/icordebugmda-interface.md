---
title: ICorDebugMDA (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugMDA
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA
helpviewer_keywords:
- ICorDebugMDA interface [.NET Framework debugging]
ms.assetid: 8ecbb854-295c-4dd4-b9fc-01ebeac46e06
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a662185bb84e9a66573b43b26ffcd256ecb943f5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69909853"
---
# <a name="icordebugmda-interface"></a><span data-ttu-id="34e89-102">ICorDebugMDA (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="34e89-102">ICorDebugMDA Interface</span></span>
<span data-ttu-id="34e89-103">Representa un mensaje del asistente para la depuración administrada (MDA).</span><span class="sxs-lookup"><span data-stu-id="34e89-103">Represents a managed debugging assistant (MDA) message.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="34e89-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="34e89-104">Methods</span></span>  
  
|<span data-ttu-id="34e89-105">Método</span><span class="sxs-lookup"><span data-stu-id="34e89-105">Method</span></span>|<span data-ttu-id="34e89-106">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="34e89-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="34e89-107">GetDescription (método)</span><span class="sxs-lookup"><span data-stu-id="34e89-107">GetDescription Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getdescription-method.md)|<span data-ttu-id="34e89-108">Obtiene una cadena que contiene una descripción de este MDA.</span><span class="sxs-lookup"><span data-stu-id="34e89-108">Gets a string containing a description of this MDA.</span></span>|  
|[<span data-ttu-id="34e89-109">GetFlags (método)</span><span class="sxs-lookup"><span data-stu-id="34e89-109">GetFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getflags-method.md)|<span data-ttu-id="34e89-110">Obtiene las marcas asociadas a este MDA.</span><span class="sxs-lookup"><span data-stu-id="34e89-110">Gets the flags associated with this MDA.</span></span>|  
|[<span data-ttu-id="34e89-111">GetName (método)</span><span class="sxs-lookup"><span data-stu-id="34e89-111">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getname-method.md)|<span data-ttu-id="34e89-112">Obtiene una cadena que contiene el nombre de este MDA.</span><span class="sxs-lookup"><span data-stu-id="34e89-112">Gets a string containing the name of this MDA.</span></span>|  
|[<span data-ttu-id="34e89-113">GetOSThreadId (método)</span><span class="sxs-lookup"><span data-stu-id="34e89-113">GetOSThreadId Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getosthreadid-method.md)|<span data-ttu-id="34e89-114">Obtiene el identificador del subproceso del sistema operativo en el que se ejecuta este MDA.</span><span class="sxs-lookup"><span data-stu-id="34e89-114">Gets the operating system thread identifier upon which this MDA is executing.</span></span>|  
|[<span data-ttu-id="34e89-115">GetXML (método)</span><span class="sxs-lookup"><span data-stu-id="34e89-115">GetXML Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getxml-method.md)|<span data-ttu-id="34e89-116">Obtiene la secuencia XML completa asociada a este MDA.</span><span class="sxs-lookup"><span data-stu-id="34e89-116">Gets the full XML stream associated with this MDA.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="34e89-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="34e89-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="34e89-118">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="34e89-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34e89-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="34e89-119">Requirements</span></span>  
 <span data-ttu-id="34e89-120">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="34e89-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34e89-121">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="34e89-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="34e89-122">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="34e89-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="34e89-123">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34e89-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34e89-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="34e89-124">See also</span></span>

- [<span data-ttu-id="34e89-125">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="34e89-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="34e89-126">Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)</span><span class="sxs-lookup"><span data-stu-id="34e89-126">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
