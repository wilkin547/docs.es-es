---
title: ICorDebugInternalFrame Interfaz1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugInternalFrame
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugInternalFrame
helpviewer_keywords: ICorDebugInternalFrame interface [.NET Framework debugging]
ms.assetid: bb4772ca-0d54-4185-b738-7a6ffe9ea85a
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6e950847764e695f705aeded0e3804db4b872827
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebuginternalframe-interface1"></a><span data-ttu-id="023ac-102">ICorDebugInternalFrame Interfaz1</span><span class="sxs-lookup"><span data-stu-id="023ac-102">ICorDebugInternalFrame Interface1</span></span>
<span data-ttu-id="023ac-103">Representa un marco de tiempo de ejecución interno en la pila.</span><span class="sxs-lookup"><span data-stu-id="023ac-103">Represents a runtime-internal frame on the stack.</span></span> <span data-ttu-id="023ac-104">Esta interfaz es una subclase de ICorDebugFrame (interfaz).</span><span class="sxs-lookup"><span data-stu-id="023ac-104">This interface is a subclass of the ICorDebugFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="023ac-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="023ac-105">Methods</span></span>  
  
|<span data-ttu-id="023ac-106">Método</span><span class="sxs-lookup"><span data-stu-id="023ac-106">Method</span></span>|<span data-ttu-id="023ac-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="023ac-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="023ac-108">GetFrameType (método)</span><span class="sxs-lookup"><span data-stu-id="023ac-108">GetFrameType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe-getframetype-method.md)|<span data-ttu-id="023ac-109">Obtiene el tipo de este marco interno.</span><span class="sxs-lookup"><span data-stu-id="023ac-109">Gets the type of this internal frame.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="023ac-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="023ac-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="023ac-111">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="023ac-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="023ac-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="023ac-112">Requirements</span></span>  
 <span data-ttu-id="023ac-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="023ac-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="023ac-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="023ac-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="023ac-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="023ac-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="023ac-116">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="023ac-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="023ac-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="023ac-117">See Also</span></span>  
 [<span data-ttu-id="023ac-118">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="023ac-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
