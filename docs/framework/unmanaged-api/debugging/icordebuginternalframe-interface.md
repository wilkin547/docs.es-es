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
ms.openlocfilehash: a05ba891e734fbf5a94b2a1f91e29d484e1c788b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebuginternalframe-interface1"></a><span data-ttu-id="585cd-102">ICorDebugInternalFrame Interfaz1</span><span class="sxs-lookup"><span data-stu-id="585cd-102">ICorDebugInternalFrame Interface1</span></span>
<span data-ttu-id="585cd-103">Representa un marco de tiempo de ejecución interno en la pila.</span><span class="sxs-lookup"><span data-stu-id="585cd-103">Represents a runtime-internal frame on the stack.</span></span> <span data-ttu-id="585cd-104">Esta interfaz es una subclase de ICorDebugFrame (interfaz).</span><span class="sxs-lookup"><span data-stu-id="585cd-104">This interface is a subclass of the ICorDebugFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="585cd-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="585cd-105">Methods</span></span>  
  
|<span data-ttu-id="585cd-106">Método</span><span class="sxs-lookup"><span data-stu-id="585cd-106">Method</span></span>|<span data-ttu-id="585cd-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="585cd-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="585cd-108">GetFrameType (método)</span><span class="sxs-lookup"><span data-stu-id="585cd-108">GetFrameType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe-getframetype-method.md)|<span data-ttu-id="585cd-109">Obtiene el tipo de este marco interno.</span><span class="sxs-lookup"><span data-stu-id="585cd-109">Gets the type of this internal frame.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="585cd-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="585cd-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="585cd-111">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="585cd-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="585cd-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="585cd-112">Requirements</span></span>  
 <span data-ttu-id="585cd-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="585cd-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="585cd-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="585cd-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="585cd-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="585cd-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="585cd-116">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="585cd-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="585cd-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="585cd-117">See Also</span></span>  
 [<span data-ttu-id="585cd-118">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="585cd-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
