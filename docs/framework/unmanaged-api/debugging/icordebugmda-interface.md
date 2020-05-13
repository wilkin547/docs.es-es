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
ms.openlocfilehash: d711f36b4e2071dac9458a023e1d3cf4743e77b3
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212638"
---
# <a name="icordebugmda-interface"></a><span data-ttu-id="e6217-102">ICorDebugMDA (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e6217-102">ICorDebugMDA Interface</span></span>
<span data-ttu-id="e6217-103">Representa un mensaje del asistente para la depuración administrada (MDA).</span><span class="sxs-lookup"><span data-stu-id="e6217-103">Represents a managed debugging assistant (MDA) message.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e6217-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="e6217-104">Methods</span></span>  
  
|<span data-ttu-id="e6217-105">Método</span><span class="sxs-lookup"><span data-stu-id="e6217-105">Method</span></span>|<span data-ttu-id="e6217-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="e6217-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e6217-107">Método GetDescription</span><span class="sxs-lookup"><span data-stu-id="e6217-107">GetDescription Method</span></span>](icordebugmda-getdescription-method.md)|<span data-ttu-id="e6217-108">Obtiene una cadena que contiene una descripción de este MDA.</span><span class="sxs-lookup"><span data-stu-id="e6217-108">Gets a string containing a description of this MDA.</span></span>|  
|[<span data-ttu-id="e6217-109">Método GetFlags</span><span class="sxs-lookup"><span data-stu-id="e6217-109">GetFlags Method</span></span>](icordebugmda-getflags-method.md)|<span data-ttu-id="e6217-110">Obtiene las marcas asociadas a este MDA.</span><span class="sxs-lookup"><span data-stu-id="e6217-110">Gets the flags associated with this MDA.</span></span>|  
|[<span data-ttu-id="e6217-111">Método GetName</span><span class="sxs-lookup"><span data-stu-id="e6217-111">GetName Method</span></span>](icordebugmda-getname-method.md)|<span data-ttu-id="e6217-112">Obtiene una cadena que contiene el nombre de este MDA.</span><span class="sxs-lookup"><span data-stu-id="e6217-112">Gets a string containing the name of this MDA.</span></span>|  
|[<span data-ttu-id="e6217-113">Método GetOSThreadId</span><span class="sxs-lookup"><span data-stu-id="e6217-113">GetOSThreadId Method</span></span>](icordebugmda-getosthreadid-method.md)|<span data-ttu-id="e6217-114">Obtiene el identificador del subproceso del sistema operativo en el que se ejecuta este MDA.</span><span class="sxs-lookup"><span data-stu-id="e6217-114">Gets the operating system thread identifier upon which this MDA is executing.</span></span>|  
|[<span data-ttu-id="e6217-115">Método GetXML</span><span class="sxs-lookup"><span data-stu-id="e6217-115">GetXML Method</span></span>](icordebugmda-getxml-method.md)|<span data-ttu-id="e6217-116">Obtiene la secuencia XML completa asociada a este MDA.</span><span class="sxs-lookup"><span data-stu-id="e6217-116">Gets the full XML stream associated with this MDA.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e6217-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e6217-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e6217-118">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="e6217-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6217-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e6217-119">Requirements</span></span>  
 <span data-ttu-id="e6217-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e6217-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6217-121">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e6217-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e6217-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e6217-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e6217-123">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6217-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6217-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e6217-124">See also</span></span>

- [<span data-ttu-id="e6217-125">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="e6217-125">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="e6217-126">Diagnóstico de errores con asistentes de depuraciones administradas</span><span class="sxs-lookup"><span data-stu-id="e6217-126">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
