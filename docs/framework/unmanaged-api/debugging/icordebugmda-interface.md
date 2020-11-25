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
ms.openlocfilehash: c4ff28ff1019b5314902a4e71f6d02b5a2fd8d70
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710849"
---
# <a name="icordebugmda-interface"></a><span data-ttu-id="9ed48-102">ICorDebugMDA (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9ed48-102">ICorDebugMDA Interface</span></span>

<span data-ttu-id="9ed48-103">Representa un mensaje del asistente para la depuración administrada (MDA).</span><span class="sxs-lookup"><span data-stu-id="9ed48-103">Represents a managed debugging assistant (MDA) message.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9ed48-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="9ed48-104">Methods</span></span>  
  
|<span data-ttu-id="9ed48-105">Método</span><span class="sxs-lookup"><span data-stu-id="9ed48-105">Method</span></span>|<span data-ttu-id="9ed48-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="9ed48-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9ed48-107">Método GetDescription</span><span class="sxs-lookup"><span data-stu-id="9ed48-107">GetDescription Method</span></span>](icordebugmda-getdescription-method.md)|<span data-ttu-id="9ed48-108">Obtiene una cadena que contiene una descripción de este MDA.</span><span class="sxs-lookup"><span data-stu-id="9ed48-108">Gets a string containing a description of this MDA.</span></span>|  
|[<span data-ttu-id="9ed48-109">Método GetFlags</span><span class="sxs-lookup"><span data-stu-id="9ed48-109">GetFlags Method</span></span>](icordebugmda-getflags-method.md)|<span data-ttu-id="9ed48-110">Obtiene las marcas asociadas a este MDA.</span><span class="sxs-lookup"><span data-stu-id="9ed48-110">Gets the flags associated with this MDA.</span></span>|  
|[<span data-ttu-id="9ed48-111">GetName (Método)</span><span class="sxs-lookup"><span data-stu-id="9ed48-111">GetName Method</span></span>](icordebugmda-getname-method.md)|<span data-ttu-id="9ed48-112">Obtiene una cadena que contiene el nombre de este MDA.</span><span class="sxs-lookup"><span data-stu-id="9ed48-112">Gets a string containing the name of this MDA.</span></span>|  
|[<span data-ttu-id="9ed48-113">Método GetOSThreadId</span><span class="sxs-lookup"><span data-stu-id="9ed48-113">GetOSThreadId Method</span></span>](icordebugmda-getosthreadid-method.md)|<span data-ttu-id="9ed48-114">Obtiene el identificador del subproceso del sistema operativo en el que se ejecuta este MDA.</span><span class="sxs-lookup"><span data-stu-id="9ed48-114">Gets the operating system thread identifier upon which this MDA is executing.</span></span>|  
|[<span data-ttu-id="9ed48-115">Método GetXML</span><span class="sxs-lookup"><span data-stu-id="9ed48-115">GetXML Method</span></span>](icordebugmda-getxml-method.md)|<span data-ttu-id="9ed48-116">Obtiene la secuencia XML completa asociada a este MDA.</span><span class="sxs-lookup"><span data-stu-id="9ed48-116">Gets the full XML stream associated with this MDA.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9ed48-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9ed48-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9ed48-118">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="9ed48-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ed48-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9ed48-119">Requirements</span></span>  

 <span data-ttu-id="9ed48-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9ed48-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ed48-121">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9ed48-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9ed48-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9ed48-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9ed48-123">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ed48-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ed48-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9ed48-124">See also</span></span>

- [<span data-ttu-id="9ed48-125">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="9ed48-125">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="9ed48-126">Diagnóstico de errores con asistentes de depuraciones administradas</span><span class="sxs-lookup"><span data-stu-id="9ed48-126">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
