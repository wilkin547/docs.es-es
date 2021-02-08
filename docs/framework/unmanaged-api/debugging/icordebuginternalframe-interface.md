---
description: 'Más información acerca de: interfaz ICorDebugInternalFrame ('
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
ms.openlocfilehash: 7143f270b97e10fb9664aa7f7387749ddecbbcc5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791145"
---
# <a name="icordebuginternalframe-interface"></a><span data-ttu-id="22ce6-103">Interfaz ICorDebugInternalFrame</span><span class="sxs-lookup"><span data-stu-id="22ce6-103">ICorDebugInternalFrame Interface</span></span>

<span data-ttu-id="22ce6-104">Representa un marco interno en tiempo de ejecución en la pila.</span><span class="sxs-lookup"><span data-stu-id="22ce6-104">Represents a runtime-internal frame on the stack.</span></span> <span data-ttu-id="22ce6-105">Esta interfaz es una subclase de la interfaz ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="22ce6-105">This interface is a subclass of the ICorDebugFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="22ce6-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="22ce6-106">Methods</span></span>  
  
|<span data-ttu-id="22ce6-107">Método</span><span class="sxs-lookup"><span data-stu-id="22ce6-107">Method</span></span>|<span data-ttu-id="22ce6-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="22ce6-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="22ce6-109">Método GetFrameType</span><span class="sxs-lookup"><span data-stu-id="22ce6-109">GetFrameType Method</span></span>](icordebuginternalframe-getframetype-method.md)|<span data-ttu-id="22ce6-110">Obtiene el tipo de este marco interno.</span><span class="sxs-lookup"><span data-stu-id="22ce6-110">Gets the type of this internal frame.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="22ce6-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="22ce6-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="22ce6-112">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="22ce6-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22ce6-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="22ce6-113">Requirements</span></span>  

 <span data-ttu-id="22ce6-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22ce6-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22ce6-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="22ce6-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="22ce6-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="22ce6-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="22ce6-117">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22ce6-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22ce6-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="22ce6-118">See also</span></span>

- [<span data-ttu-id="22ce6-119">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="22ce6-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
