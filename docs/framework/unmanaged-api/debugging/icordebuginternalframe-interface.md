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
ms.openlocfilehash: b7e738f06f9a9a06caedec2bdd0de4ab57f6d9b3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719728"
---
# <a name="icordebuginternalframe-interface"></a><span data-ttu-id="18cb9-102">Interfaz ICorDebugInternalFrame</span><span class="sxs-lookup"><span data-stu-id="18cb9-102">ICorDebugInternalFrame Interface</span></span>

<span data-ttu-id="18cb9-103">Representa un marco interno en tiempo de ejecución en la pila.</span><span class="sxs-lookup"><span data-stu-id="18cb9-103">Represents a runtime-internal frame on the stack.</span></span> <span data-ttu-id="18cb9-104">Esta interfaz es una subclase de la interfaz ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="18cb9-104">This interface is a subclass of the ICorDebugFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="18cb9-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="18cb9-105">Methods</span></span>  
  
|<span data-ttu-id="18cb9-106">Método</span><span class="sxs-lookup"><span data-stu-id="18cb9-106">Method</span></span>|<span data-ttu-id="18cb9-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="18cb9-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="18cb9-108">Método GetFrameType</span><span class="sxs-lookup"><span data-stu-id="18cb9-108">GetFrameType Method</span></span>](icordebuginternalframe-getframetype-method.md)|<span data-ttu-id="18cb9-109">Obtiene el tipo de este marco interno.</span><span class="sxs-lookup"><span data-stu-id="18cb9-109">Gets the type of this internal frame.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="18cb9-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="18cb9-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="18cb9-111">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="18cb9-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18cb9-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="18cb9-112">Requirements</span></span>  

 <span data-ttu-id="18cb9-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="18cb9-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18cb9-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="18cb9-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="18cb9-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="18cb9-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="18cb9-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18cb9-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18cb9-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="18cb9-117">See also</span></span>

- [<span data-ttu-id="18cb9-118">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="18cb9-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
