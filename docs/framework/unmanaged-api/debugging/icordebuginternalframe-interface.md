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
ms.openlocfilehash: 6bc24450cdda2e3ed324256b53b2d137d1eb90e4
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788482"
---
# <a name="icordebuginternalframe-interface"></a><span data-ttu-id="6d4a2-102">Interfaz ICorDebugInternalFrame</span><span class="sxs-lookup"><span data-stu-id="6d4a2-102">ICorDebugInternalFrame Interface</span></span>

<span data-ttu-id="6d4a2-103">Representa un marco interno en tiempo de ejecución en la pila.</span><span class="sxs-lookup"><span data-stu-id="6d4a2-103">Represents a runtime-internal frame on the stack.</span></span> <span data-ttu-id="6d4a2-104">Esta interfaz es una subclase de la interfaz ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="6d4a2-104">This interface is a subclass of the ICorDebugFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6d4a2-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="6d4a2-105">Methods</span></span>  
  
|<span data-ttu-id="6d4a2-106">Método</span><span class="sxs-lookup"><span data-stu-id="6d4a2-106">Method</span></span>|<span data-ttu-id="6d4a2-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="6d4a2-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6d4a2-108">GetFrameType (método)</span><span class="sxs-lookup"><span data-stu-id="6d4a2-108">GetFrameType Method</span></span>](icordebuginternalframe-getframetype-method.md)|<span data-ttu-id="6d4a2-109">Obtiene el tipo de este marco interno.</span><span class="sxs-lookup"><span data-stu-id="6d4a2-109">Gets the type of this internal frame.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6d4a2-110">Notas</span><span class="sxs-lookup"><span data-stu-id="6d4a2-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6d4a2-111">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="6d4a2-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d4a2-112">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="6d4a2-112">Requirements</span></span>  
 <span data-ttu-id="6d4a2-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6d4a2-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d4a2-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6d4a2-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6d4a2-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6d4a2-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6d4a2-116">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d4a2-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d4a2-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="6d4a2-117">See also</span></span>

- [<span data-ttu-id="6d4a2-118">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="6d4a2-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
