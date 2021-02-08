---
description: 'Más información acerca de: ICorDebugMDA (interfaz)'
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
ms.openlocfilehash: 8e6e779c58d71b07edc9b63dff72aef728ebe050
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801131"
---
# <a name="icordebugmda-interface"></a><span data-ttu-id="10807-103">ICorDebugMDA (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="10807-103">ICorDebugMDA Interface</span></span>

<span data-ttu-id="10807-104">Representa un mensaje del asistente para la depuración administrada (MDA).</span><span class="sxs-lookup"><span data-stu-id="10807-104">Represents a managed debugging assistant (MDA) message.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="10807-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="10807-105">Methods</span></span>  
  
|<span data-ttu-id="10807-106">Método</span><span class="sxs-lookup"><span data-stu-id="10807-106">Method</span></span>|<span data-ttu-id="10807-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="10807-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="10807-108">Método GetDescription</span><span class="sxs-lookup"><span data-stu-id="10807-108">GetDescription Method</span></span>](icordebugmda-getdescription-method.md)|<span data-ttu-id="10807-109">Obtiene una cadena que contiene una descripción de este MDA.</span><span class="sxs-lookup"><span data-stu-id="10807-109">Gets a string containing a description of this MDA.</span></span>|  
|[<span data-ttu-id="10807-110">Método GetFlags</span><span class="sxs-lookup"><span data-stu-id="10807-110">GetFlags Method</span></span>](icordebugmda-getflags-method.md)|<span data-ttu-id="10807-111">Obtiene las marcas asociadas a este MDA.</span><span class="sxs-lookup"><span data-stu-id="10807-111">Gets the flags associated with this MDA.</span></span>|  
|[<span data-ttu-id="10807-112">Método GetName</span><span class="sxs-lookup"><span data-stu-id="10807-112">GetName Method</span></span>](icordebugmda-getname-method.md)|<span data-ttu-id="10807-113">Obtiene una cadena que contiene el nombre de este MDA.</span><span class="sxs-lookup"><span data-stu-id="10807-113">Gets a string containing the name of this MDA.</span></span>|  
|[<span data-ttu-id="10807-114">Método GetOSThreadId</span><span class="sxs-lookup"><span data-stu-id="10807-114">GetOSThreadId Method</span></span>](icordebugmda-getosthreadid-method.md)|<span data-ttu-id="10807-115">Obtiene el identificador del subproceso del sistema operativo en el que se ejecuta este MDA.</span><span class="sxs-lookup"><span data-stu-id="10807-115">Gets the operating system thread identifier upon which this MDA is executing.</span></span>|  
|[<span data-ttu-id="10807-116">Método GetXML</span><span class="sxs-lookup"><span data-stu-id="10807-116">GetXML Method</span></span>](icordebugmda-getxml-method.md)|<span data-ttu-id="10807-117">Obtiene la secuencia XML completa asociada a este MDA.</span><span class="sxs-lookup"><span data-stu-id="10807-117">Gets the full XML stream associated with this MDA.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="10807-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="10807-118">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="10807-119">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="10807-119">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10807-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="10807-120">Requirements</span></span>  

 <span data-ttu-id="10807-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="10807-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10807-122">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="10807-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="10807-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="10807-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="10807-124">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10807-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10807-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="10807-125">See also</span></span>

- [<span data-ttu-id="10807-126">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="10807-126">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="10807-127">Diagnóstico de errores con asistentes de depuraciones administradas</span><span class="sxs-lookup"><span data-stu-id="10807-127">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
