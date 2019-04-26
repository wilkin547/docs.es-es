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
ms.openlocfilehash: cea8f6827d3e361b3f6498e6612d8b11a2357285
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61916674"
---
# <a name="icordebugmda-interface"></a><span data-ttu-id="3e3f1-102">ICorDebugMDA (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3e3f1-102">ICorDebugMDA Interface</span></span>
<span data-ttu-id="3e3f1-103">Representa un mensaje del asistente para la depuración administrada (MDA).</span><span class="sxs-lookup"><span data-stu-id="3e3f1-103">Represents a managed debugging assistant (MDA) message.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3e3f1-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="3e3f1-104">Methods</span></span>  
  
|<span data-ttu-id="3e3f1-105">Método</span><span class="sxs-lookup"><span data-stu-id="3e3f1-105">Method</span></span>|<span data-ttu-id="3e3f1-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="3e3f1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3e3f1-107">GetDescription (método)</span><span class="sxs-lookup"><span data-stu-id="3e3f1-107">GetDescription Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getdescription-method.md)|<span data-ttu-id="3e3f1-108">Obtiene una cadena que contiene una descripción de este MDA.</span><span class="sxs-lookup"><span data-stu-id="3e3f1-108">Gets a string containing a description of this MDA.</span></span>|  
|[<span data-ttu-id="3e3f1-109">GetFlags (método)</span><span class="sxs-lookup"><span data-stu-id="3e3f1-109">GetFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getflags-method.md)|<span data-ttu-id="3e3f1-110">Obtiene las marcas asociadas a este MDA.</span><span class="sxs-lookup"><span data-stu-id="3e3f1-110">Gets the flags associated with this MDA.</span></span>|  
|[<span data-ttu-id="3e3f1-111">GetName (método)</span><span class="sxs-lookup"><span data-stu-id="3e3f1-111">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getname-method.md)|<span data-ttu-id="3e3f1-112">Obtiene una cadena que contiene el nombre de este MDA.</span><span class="sxs-lookup"><span data-stu-id="3e3f1-112">Gets a string containing the name of this MDA.</span></span>|  
|[<span data-ttu-id="3e3f1-113">GetOSThreadId (método)</span><span class="sxs-lookup"><span data-stu-id="3e3f1-113">GetOSThreadId Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getosthreadid-method.md)|<span data-ttu-id="3e3f1-114">Obtiene el identificador de subproceso del sistema operativo en el que se está ejecutando este MDA.</span><span class="sxs-lookup"><span data-stu-id="3e3f1-114">Gets the operating system thread identifier upon which this MDA is executing.</span></span>|  
|[<span data-ttu-id="3e3f1-115">GetXML (método)</span><span class="sxs-lookup"><span data-stu-id="3e3f1-115">GetXML Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getxml-method.md)|<span data-ttu-id="3e3f1-116">Obtiene la secuencia XML completa asociada a este MDA.</span><span class="sxs-lookup"><span data-stu-id="3e3f1-116">Gets the full XML stream associated with this MDA.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3e3f1-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3e3f1-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3e3f1-118">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="3e3f1-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e3f1-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3e3f1-119">Requirements</span></span>  
 <span data-ttu-id="3e3f1-120">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3e3f1-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e3f1-121">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3e3f1-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3e3f1-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3e3f1-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3e3f1-123">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e3f1-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e3f1-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="3e3f1-124">See also</span></span>

- [<span data-ttu-id="3e3f1-125">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="3e3f1-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="3e3f1-126">Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)</span><span class="sxs-lookup"><span data-stu-id="3e3f1-126">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
