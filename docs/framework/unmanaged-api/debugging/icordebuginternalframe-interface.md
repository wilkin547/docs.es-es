---
title: Interfaz ICorDebugInternalFrame
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame
helpviewer_keywords:
- ICorDebugInternalFrame interface [.NET Framework debugging]
ms.assetid: bb4772ca-0d54-4185-b738-7a6ffe9ea85a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2f16b4628215bee2410708edeb337b41fbdc0311
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59109829"
---
# <a name="icordebuginternalframe-interface"></a><span data-ttu-id="6d7f7-102">Interfaz ICorDebugInternalFrame</span><span class="sxs-lookup"><span data-stu-id="6d7f7-102">ICorDebugInternalFrame Interface</span></span>

<span data-ttu-id="6d7f7-103">Representa un marco en la pila interna del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="6d7f7-103">Represents a runtime-internal frame on the stack.</span></span> <span data-ttu-id="6d7f7-104">Esta interfaz es una subclase de ICorDebugFrame (interfaz).</span><span class="sxs-lookup"><span data-stu-id="6d7f7-104">This interface is a subclass of the ICorDebugFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6d7f7-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="6d7f7-105">Methods</span></span>  
  
|<span data-ttu-id="6d7f7-106">Método</span><span class="sxs-lookup"><span data-stu-id="6d7f7-106">Method</span></span>|<span data-ttu-id="6d7f7-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="6d7f7-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6d7f7-108">GetFrameType (método)</span><span class="sxs-lookup"><span data-stu-id="6d7f7-108">GetFrameType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe-getframetype-method.md)|<span data-ttu-id="6d7f7-109">Obtiene el tipo de este marco interno.</span><span class="sxs-lookup"><span data-stu-id="6d7f7-109">Gets the type of this internal frame.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6d7f7-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6d7f7-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6d7f7-111">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="6d7f7-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d7f7-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6d7f7-112">Requirements</span></span>  
 <span data-ttu-id="6d7f7-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6d7f7-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d7f7-114">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6d7f7-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6d7f7-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6d7f7-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6d7f7-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d7f7-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d7f7-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="6d7f7-117">See also</span></span>

- [<span data-ttu-id="6d7f7-118">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="6d7f7-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
